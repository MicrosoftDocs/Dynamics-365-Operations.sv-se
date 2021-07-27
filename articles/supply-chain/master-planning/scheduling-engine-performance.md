---
title: Förbättra schemaläggningsmotorns prestanda
description: I det här avsnittet finns information om schemaläggningsmotorn och hur du förbättrar prestandan.
author: ChristianRytt
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: 71aefbc9c041074225b379d90db5cecf3849cb59
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347720"
---
# <a name="improve-scheduling-engine-performance"></a>Förbättra schemaläggningsmotorns prestanda

[!include [banner](../includes/banner.md)]

Resursplaneringsmotorn används när du planerar flöden för planerade och släppta produktionsorder. Motorn släpptes ursprungligen som en del av Dynamics AX 2012 och har genomgått flera förbättringar sedan den släpptes.

[Problemet med finplanering](https://en.wikipedia.org/wiki/Job_shop_scheduling) är ett extremt komplicerat kombinatoriskt problem där lösningstiden växer exponentiellt med antalet beslutsvariabler. Ibland kan kunder ställa in produktionsflöden och relaterade data på ett sätt som leder till ett planeringsproblem som inte kan lösas i rimlig tid, även på den moderna maskinvaran. Det här avsnittet hjälper dig att förstå planeringsmotorn och hur en viss inställning kan påverka prestandan.

När du ska förbättra schemaläggningens prestanda rekommenderar vi allmänna riktlinjer för att minska komplexiteten hos de problem som motorn måste lösa. Några av de viktigaste faktorerna som kan påverka prestanda är:

- Flöden med många operationer
- Flöden med parallella operationer
- Operationer med mer än en resursmängd
- Operationer med många tillämpliga resurser
- Användning av hårda länkar
- Användning av begränsad kapacitet
- Antalet olika kalendrar som används
- Antalet arbetstidsplatser per dag i kalendern
- Flödets totala längd
- Köra flera tidsplaneringsmotorer parallellt

## <a name="overview-of-basic-scheduling-flow"></a>Översikt över grundläggande planeringsflöde

Om du vill förstå hur en viss inställning kan påverka prestanda är det viktigt att du förstår hur processen flödar, både inuti motorn och i X ++-koden som omger den.

Den grundläggande processen för planering av en order består av tre huvudsteg:

- **Läsa in data** – här omvandlas datamodellerna X++ till motorns interna datamodell i form av jobb och begränsningar.
- **Schemaläggning** – Detta är huvudkällan för schemaläggning som bearbetar den givna modellen och begränsningarna och genererar ett resultat. Under den här processen begär motorn information om arbetstid och befintliga kapacitetsreservationer från X++ vid behov.
- **Spara data** – motorresultatet i form av jobbkapacitetens reservationsplatser bearbetas av X++-kod för att spara kapacitetsreservationer och uppdatera start- och sluttiderna för jobben/åtgärden/ordern.

## <a name="load-data-into-the-engine"></a>Läs in data i motorn

Planeringsmotorn har en mer abstrakt datamodell än databasen för Supply Chain Management eftersom den har byggts som en allmän motor som kan hantera olika datakällor. Begreppen flöde, sekundära operationer och körtid måste vara "översatta" till det allmänna jobb och den begränsningsmodell som motorn visar. Logiken för att bygga modellen har en stor mängd affärslogik och varierar beroende på källinformationen. Den ansvariga X++-klassen är `WrkCtrScheduler` och har härlett klasser för planerade produktionsorder, släppta produktionsorder och projektprognoser.

Det kan till exempel vara en väg som visas i följande tabell och bild, vilket verkar vara relativt enkelt.

| Oper. Nr | Prioritet | Ställtid | Körtid | Kötid efter | Kvantitet med resurser | Nästa |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Primär | 1.00 | 2.00 | | 1 | 20 |
| 10 | Sekundär&nbsp;1 | | | | 1 | 20 |
| 20 | Primärt | | 3.00 | 1.00 | 3 | 0 |

![Exempel på flödesdiagram.](media/scheduling-engine-route.png "Exempel på ruttdiagram")

När du skickar detta till motorn delas det upp i åtta jobb, vilket visas i bilden nedan (markera bilden om du vill förstora den).

[![Tidsplanering av motorjobb](media/scheduling-engine-jobs.png "Tidsplanering av motorjobb."](media/scheduling-engine-jobs-large.png)

Standardlänken mellan två jobb är `FinishStart` vilket innebär att sluttiden för ett jobb måste infalla före starttiden för ett annat jobb. Eftersom inställningarna måste utföras av samma resurs som senare kommer att utföra processen, finns det `OnSameResource` begränsningar mellan dem. Mellan jobben för den primära och sekundära operationen för 10, finns `StartStart` och `FinishFinish` länkar, vilket innebär att jobben måste starta och sluta samtidigt och det finns `NotOnSameResource` begränsningar som förhindrar samma resurs för primär och sekundär.

För operation 20, där antalet resurser har ställts in på 3, har process jobbet delats upp i tre skilda jobb där alla jobben måste köras exakt på samma gång.
I det här fallet har flödesgruppen ställts in för att inte reservera kapacitet för kön efter tider, vilket är orsaken till att det bara finns ett enda jobb för kön efter.

Planeringsmotorn förstår bara koncepten för jobben och har inga operationer. Detta innebär att operationerna även delas in i jobb vid grov planering, även om dessa inte kommer att sparas i databasen.

För varje projekt definierar vi också vad jobbkapacitetsbehovet är (antalet sekunder krävs). Beroende på hur resurskraven har definierats kan vi för varje jobb också skicka en lista med alla potentiella tillämpliga resurser som jobbet kan köras på och vilka kapacitetskrav som gäller för den specifika resursen. Även om listan med tillämpliga resurser skickas när modellen skapas måste motorn ändå se till att resurstilldelningen verkligen är giltig för hela jobbets varaktighet.

## <a name="scheduling-engine-internals"></a>Planera motorns intervall

### <a name="scheduling-engine-interface"></a>Planera motorns gränssnitt

För att få en uppfattning om motorn som fungerar internt är det bäst att se vilka funktioner den exponerar externt. I X++ är huvudgränssnittet `WrkCtrSchedulerEngineInterface`. Den har de metoder som beskrivs i följande underavsnitt.

#### <a name="general-engine"></a>Allmän motor

| **Metod** | **Syfte** |
| --- | --- |
| `run` | Schemalägger alla inlästa jobb och returnerar felkoden. |
| `getJobSchedulingSequenceResult` | Hämtar planeringsresultatet och det första feljobbet för den sekvens som anges av ett specifikt jobb. |
| `validateJobCapacityReservations` | Validerar kapacitetsreservationer för alla jobb som lagras i motorn. |
| `setReservationsTimeStamp` | Skickar en tidsstämpel till motoruppsättningen för alla nya kapacitets reservationer för de schemalagda jobben i motorns cache. |
| `addPropertyToGroupAggregation` | Lägger till ett prefix till den uppsättning egenskaper som används när kapaciteten aggregeras. |
| `addResource` | Lägger till en resurs till planeringsmotorns resurspool. |
| `addResourceGroup` | Lägger till en resursgrupp till planeringsmotorns resursgruppool. |
| `addResourceGroupMembership` | Lägger till en resurs som en medlem i en resursgrupp. |
| `addOptimizationGoal` | Lägger till ett planeringsoptimeringsmål (varaktighet eller prioritet). |

#### <a name="individual-jobs"></a>Enskilda jobb

| **Metod** | **Syfte** |
| --- | --- |
| `addJobInfo` | Lägger till en jobbinformationspost som informerar motorn om ett jobb som ska schemaläggas. |
| `addConstraintJobEndsAt` | Lägger till en begränsning som ett jobb ska sluta vid ett angivet datum och en viss tid. |
| `addConstraintJobStartsAt` | Lägger till en begränsning som ett jobb ska starta vid ett angivet datum och en viss tid. |
| `addConstraintMaxJobDays` | Definierar begränsningen som ett jobb kan spänna över ett angivet maximalt antal dagar. |
| `addConstraintResourceRequirement` | Lägger till begränsningen som jobbet måste schemaläggas för en viss resurs. |
| `addJobBindPriority` | Lägger till en prioritet för jobbindning för ett (jobb, begränsningsnivå) par. Ett värde med högre prioritet innebär att jobbschemat binds till tidigare. Jobbet behandlas före jobb med lägre prioritetsvärde i samma ordning. |
| `addJobCapacity` | Lägger till information om kapacitetsbeläggning för ett jobb (t.ex. den nödvändiga jobbkörningen) som är oberoende av vilken resurs som jobbet körs på. |
| `addJobResourceCapacity` | Lägger till en resurs till den uppsättning resurser som kan användas för att utföra ett jobb och anger vilken kapacitet som krävs vid körning på resursen. |
| `addJobGoal` | Lägger till information om jobbmål för en specifik begränsningsnivå (tidigaste sluttid eller senaste starttid). |
| `addJobResourcePriority` | Lägger till den prioritet som ska användas när ett jobb planeras på en resurs. |
| `addJobResourceRuntime` | Anger en jobbtid som är beroende av den resurs som jobbet ska planeras på. |
| `addJobRuntime` | Anger en jobbtid som är oberoende av den resurs som jobbet ska planeras. |
| `scheduleJobOnResourceGroup` | Markerar ett jobb för tidsplanering på resursgruppsnivå. |
| `setJobResourcePreemptionAllowed` | Anger om förköpsrätt är tillåtet för ett jobb på en resurs (om motorn tillåts schemalägga jobbet i icke sammanhängande kapacitetsplatser). |
| `setRequiredNumberOfResources` | Anger antalet resurser som krävs för att tidsplanera ett jobb (endast för grovplanering). |

#### <a name="constraints-between-jobs"></a>Begränsningar mellan jobb

| **Metod** | **Syfte** |
| --- | --- |
| `addJobLink` | Lägger till en länk (t.ex. slutförd\>start) mellan två jobb. |
| `addConstraintEndsDelayed` | Definierar villkoret som ett jobb inte kan sluta före ett annat jobb slut plus en fördröjningstid. |
| `addConstraintJobListWorkingTimeIntersect` | Lägger till en begränsning som de kapacitetsplatser som reserverats för jobben måste ha på den korsande arbetstiden för de två resurserna som används av jobben. |
| `addConstraintJobOverlap` | Lägg till ett villkor som definierar hur jobben ska ordnas när en viss kvantitet av en artikel kan flyttas mellan två resurser medan den första resursen fortfarande inte är slutförd, så att den andra resursen kan påbörja bearbetningen. |
| `addConstraintNotOnSameResource` | Lägger till ett villkor som två jobb inte ska schemaläggas på samma resurs. |
| `addConstraintOnSameResource` | Lägger till ett villkor som två jobb måste använda samma resurs. |
| `addJobSameReservations` | Lägger till en begränsning som ett jobb måste avsluta med kapacitetsreservationer för samma tid som det primära jobbet. |
| `setPrimaryParallelJob` | Lägger till information om vilket jobb som är det primära jobbet i en uppsättning parallella jobb. |

### <a name="solver"></a>Problemlösare

Motorn i sig är i huvudsak en specialiserad begränsningslösare med anpassade heuristik tillagda. Problemlösa ren baseras på två huvudelement: variabler och begränsningar.

#### <a name="variable"></a>Variabel

En variabel representerar en domän med möjliga värden. Det finns två typer av variabler i tidsplaneringsmotorn:

- **DateTime-variabel** - har en domän med alla datum och tider och domänen kan begränsas genom att flytta den nedre och övre gränsen för tiden för variabeln närmare varandra.
- **Resursvariabel** – har en domän med tillämpliga resurser och domänen kan begränsas genom att resurser tas bort från listan.

#### <a name="constraint"></a>Begränsning

Ett villkor gäller för variabler genom att begränsa deras domäner, men det beror också på variabler så att de aktiveras när variabler ändras. Processen med "begränsningsspridning" är när ett villkor utför sin huvudfunktion och rapporterar tillbaka till huvudlogiken om det lyckas.

En variabel betraktas som bunden när den inte kan begränsas ytterligare, vilket för DateTime-variabel innebär att det övre och nedre gränsvärdet är samma och för resursvariabeln att den bara har en enda tillämplig resurs. När alla variabler är bundna hittas en lösning.

### <a name="constraint-levels"></a>Begränsningsnivåer

När planeringen utförs som en del av täckningsfasen för behovsplanering av material (MPS), tidsplaneras orderna bakåt utifrån behovsdatum. Om det inte går att hitta ett schema som börjar i dag eller senare och slutar före behovsdatum ändras planeringsriktningen till framåt från idag.

Den här huvudaffärsregeln hanteras genom att ordna begränsningarna i nivåer. Om ingen lösning hittas när begränsningarna på den högsta nivån används, ignoreras begränsningarna på den nivån och den lägre nivån provas. I praxis innebär detta att modellen för bakåtplanering ska innehålla nivå 1 med jobbmål av den senaste starttiden med en maximal sluttidsbegränsning (behovsdatum) och en nivå 0 med jobb mål för tidigaste sluttid och med en lägsta starttidsbegränsning på idag.

### <a name="algorithm"></a>Algoritm

Huvudstegen för motoralgoritmen är:

1. Sök efter sekvenser (jobbkedjor) som kan lösas separat.
1. Försök hitta en inledande lösning för sekvensen för den högsta begränsningsnivån.
    1. Sortera jobben i sekvensen baserat på jobbmål och prioriteringar, så att ett startjobb kan hittas.
    1. Repetera jobben i följande ordning:
        1. Sök efter alla begränsningar som måste spridas och köra spridning.
        1. Om alla variabler för jobbet har bundits hittades en lösning för det jobbet.
        1. Om en av variablerna inte kunde bindas utan att begränsningarna överskrids, återställer du variabelbindningen, försöker med ett annat värde i domänen (för resursvariabeln) och kör begränsningsspridning igen.
1. Om ingen lösning hittas tas alla begränsningar på den aktuella begränsningsnivån bort, begränsningsnivån sänks (om det finns några lägre nivåer) och nya lösningsförsök görs med den nya uppsättningen med villkor.
1. Om en genomförbar lösning hittas startas optimeringsfasen, som försöker hitta en bättre lösning tills tidsgränsen för optimering har nåtts eller alla resurskombinationer har uttömts.

Problemlösa ren är inte medvetna om tidsplaneringsalgoritmens specifika begränsningar. Den är i definitionen och kombinationen av de olika begränsningar som "magiska" inträffar.

### <a name="determining-working-times"></a>Fastställa arbetstider

En stor del av de (interna) begränsningarna i motorn styr resursens arbetstid och kapacitet. För det andra är uppgiften att passera arbetstidsplatserna för en resurs från en given punkt i en given riktning och hitta ett tillräckligt mycket intervall då jobben som krävs (tiden) kan passa.

För att göra detta måste motorn känna till arbetstiderna för en resurs. Motsatsen till huvudmodelldata är att arbetstiderna är *lazy loaded*, vilket innebär att de läses in i motorn efter behov. Orsaken till det här tillvägagångssättet är att det ofta finns arbetstider i Supply Chain Management för en kalender under en lång period och det finns vanligtvis många kalendrar för dessa data för inläsning.

En kalenderinformation begärs av motorn i segment, genom att klassmetoden X++ anropas `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. Begäran gäller ett visst kalender-ID i ett visst tidsintervall. Beroende på servercachen hantering i Supply Chain Management kan var och en av dessa begäranden avslutas i flera databasanrop, vilket tar lång tid (relativt till den tid som är tidsödande). Om kalendern innehåller mycket avancerade definitioner av arbetstid med många arbetstidsintervall per dag, läggs detta till i den tidpunkt då inläsningen sker.

När arbetstidsdata läses in i planeringsmotorn behålls detta i dess interna cache för den specifika kalendern, vilket innebär att när andra jobb eller resurser använder samma kalender kan nästa sökningar snabbt utföras från minnet. En vanlig orsak till dålig prestanda är om ett separat kalender-ID används för varje resurs eftersom data måste begäras för varje kalender även om innehållet i kalendrarna kan vara detsamma.

### <a name="finite-capacity"></a>Begränsad kapacitet

När du använder begränsad kapacitet delas och minskas arbetstidsplatserna i kalendern utifrån de befintliga kapacitetsreservationerna. Dessa reservationer hämtas också via samma `WrkCtrSchedulingInteropDataProvider` klass som kalendrarna, men använder i stället metoden `getCapacityReservations`. Vid planering under huvudplaneringen beaktas reservationerna för den specifika huvudplanen och om det aktiveras på sidan **huvudplaneringsparametrar** inkluderas även reservationer från fasta produktionsorder. När du planerar en produktionsorder är det även ett alternativ för att inkludera reservationer från befintliga planerade order, även om det inte är lika gemensamt som det andra sättet.

Om du använder begränsad kapacitet kan tidsplaneringen ta längre tid på grund av olika orsaker:

- Hämtning av kapacitetsinformationen från databasen är en långsam åtgärd och cachelagringen av kapacitetsinformation på serversidan är vanligtvis inte lika bra som för arbetstider eftersom de inte delas mellan resurser som vanligtvis kalendrar.
- Antalet arbetstidsplatser för över ökningar på grund av delningar och platser under en längre tidsperiod måste vanligtvis undersökas innan en lösning kan hittas.
- När tidsplaneringen är slutförd måste en kontroll göras för att det ska gå att utföra reservationer (mer information finns i avsnittet "köra tidsplaneringsmotorer parallellt").

### <a name="examining-the-resource-combinations"></a>Undersöka resurskombinationerna

Om jobbkön endast innehåller standard `FinishStart` länkar, vilket innebär att den utgör en enkel kedja utan grenar, kan ett optimalt resultat (ses från den enskilda ordern, inte mellan order) uppnås genom att hitta den bästa lösningen för det första jobbet och sedan flytta på för att hitta den bästa lösningen för nästa jobb. Den bästa lösningen för ett jobb är att hitta den resurs som kan hämta från och till-datum för det jobb som ligger närmast jobbmålet (vid vidarebefordring innebär det att slutdatumet för jobbet blir så tidigt som möjligt) samtidigt som begränsningarna fortfarande respekteras.

När det finns parallella jobb kan du söka efter olika kombinationer av resurser genom att söka efter en lösning. Antalet möjliga resurskombinationer är produkten av antalet tillämpliga resurser för de kopplade parallella jobben. Särskilt när du planerar en order bakåt från ett behovsdatum, kan det ta en stund innan logiken inser att det inte finns någon lösning på problemet som gör att parallella jobben får plats före dagens datum, eftersom det då måste kontrollera alla kombinationer eftersom det kan finnas vissa resurser med högre effektivitet eller en annan kalender som kan ge ett resultat. Detta innebär att om ingen tidsgräns har angetts kommer den att köras under lång tid innan den ändrar riktning till framåt.

Den här kombinatoriska logiken innebär också att om du lägger till mer tillämpliga resurser kan motorn bli långsammare. Om det uppstår prestandaproblem vid parallella operationer och tidsplanering med oändlig kapacitet, kan den delvis fastställas genom att låta ruttdesigner ta ett beslut om vilken resurs som ska användas och sedan tilldela resursen direkt till operationen (eftersom motorn i de flesta fall alltid avslutar samma resurs, så att slutresultatet blir samma).

### <a name="hard-links"></a>Hårda länkar

Att ställa in länktypen mellan två jobb på hår ser till att det inte finns någon tidslucka mellan slutförandet av ett jobb och början på nästa. Detta kan vara användbart i situationer som när metall värms upp i ett jobb och sedan bearbetas i nästa jobb, där det inte är önskvärt att ha den metall som svalnar mellan.

Om flödet utgör en enkel kedja utan filialer med vanliga, mjuka länkar och vidarebefordrings planering kan du söka efter en lösning för det första jobbet som uppfyller sina egna begränsningar och sedan förflytta dig genom kedjan som sprider sluttiden från det tidigare jobbet till nästa jobb. Om det aktuella jobbet inte kan hitta någon kapacitet flyttas starttiden för det vidare, utan att det påverkar tidigare jobb som kan skapa luckor mellan jobben. Med fasta länkar (särskilt i samband med begränsad kapacitet) för samma scenario innebär det faktum att ett jobb senare i kedjan inte kan hitta kapacitet, innebär att alla tidigare schemalagda jobb måste "dras" efter ett och på så sätt att ett antal gånger har schemalagts om. Särskilt i scenarier med hög belastning för flera resurser kan de hårda länkarna orsaka en kedjereaktion där jobben påverkar varandra och ett antal upprepningar måste utföras innan resultatet stabiliseras i ett genomförbart schema.

## <a name="running-scheduling-engines-in-parallel"></a>Köra tidsplaneringsmotorer parallellt

När planering utförs som en del av en huvudplaneringskörning där stödprocesser används, kan alla hjälp trådar för huvudplanering även hämta planeringsuppgifter för produktionsorder. Detta innebär att flera tidsplaneringsmotorer kan köras samtidigt. Även om flertrådsteknik i allmänhet är en mycket viktig prestandaförmån, finns det också vissa funktionsnackdelar när det kommer att schemaläggas.

I MPS är alla produktionsorder för en viss strukturlista tidsplaneras i behovsdatumordning, vilket innebär att dessa order med det tidigaste behovsdatumet ska planeras först och därmed få den högsta chansen att få tillgänglig resurskapacitet. Med flera motorer som kan väljas från listan över ej tidsplanerade order, är det dock inte längre säkert att det går att slutföra sekvensen.

När du planerar att använda begränsad kapacitet och när flera motorinstanser försöker schemalägga order som kan använda samma resurser samtidigt inom samma intervall, kan ett konkurrensvillkor uppstå. Antalet sådana konkurrensvillkor registreras i fältet **planeringskonflikter** på huvudplanens historiksida. Konfliktlösningslogiken är följande:

- Planera en order (låsningsfri) och hämta kapacitetsreservationer.
- Ta låset.
- Kontrollera om det finns nyare kapacitetsreservationer för de schemalagda resurserna i tidsrymd.
  - Om nej, skriv kapaciteten och släpp låset.
  - Om du väljer ja släpper du upp låset och planerar om ordern från början.

När du planerar med flera motorinstanser är resultatet alltså inte helt deterministisk eftersom det beror på den exakta tidpunkten för varje tråd.

## <a name="operation-scheduling-performance"></a>Prestanda vid grovplanering

Även om grovplanering även kallas för grövre kapacitetsplanering, sett från en motorsynpunkt, kan det vara ett svårare problem att lösa om begränsad kapacitet används eftersom mer data behövs för att fastställa genomförbarheten.

Resursgruppens kapacitet beror på vilka och hur många resurser som är medlemmar i resursgruppen. En resursgrupp i sig själv har ingen kapacitet&mdash;endast när resurser är medlemmar i gruppen får den kapacitet. Eftersom resursgrupps medlemskap kan variera över tiden måste kapaciteten utvärderas per dag.

I grovplaneringen används resursgruppens kalender för att bestämma start- och sluttider för varje operation. Det innebär att resursgruppens kalender begränsar hur mycket tid som kan vara tidsplanerad för en operation på en dag i en resursgrupp. Mittemot kalendern för de specifika resurserna ignoreras kalenderns effektivitets data för resursgruppen eftersom det bara anger öppet tider och inte verklig kapacitet.

Om till exempel arbetstiden för en resursgrupp för ett visst datum är mellan 8:00 och 16:00, kan en operation inte lägga till mer belastning i resursgruppen än vad som kan vara i åtta timmar, oavsett hur mycket kapacitet som resursgruppen har som summa den dagen. Tillgänglig kapacitet kan dock begränsa belastningen ytterligare.

Beläggningen från finplaneringen för alla resurser som ingår i resursgruppen för en viss dag beaktas när den tillgängliga kapaciteten för resursgruppen på samma dag beräknas. För varje datum är beräkningen:

*Tillgänglig resursgruppskapacitet = kapacitet för resurser i gruppen baserat på deras kalender &ndash; tidsplanerad jobbeläggning för resurserna i gruppen &ndash; tidsplanerad operationsbeläggning för resurserna i gruppen &ndash; tidsplanerad operationsbeläggning för resursgruppen*

På fliken **resursbehov** i flödesoperationen kan resurskraven anges med antingen en specifik resurs (då tidsplaneringen schemaläggs med hjälp av resursen), för en resursgrupp, för en resurstyp, eller för en eller flera funktioner, kompetens, kurs eller certifikat. När du använder alla dessa alternativ ger det stor flexibilitet i vägens design, men det förstorar också schemaläggningen av motorn eftersom kapaciteten måste redovisas för varje "egenskap" (det abstrakta namn som används i motorn för kapacitet, kvalifikationer och så vidare).

Resursgruppens kapacitet för en kapacitet är summan av kapaciteten för alla resurser i resursgruppen som har kapaciteten i fråga. Om en resurs i gruppen har en funktion kommer den att anses vara oavsett vilken kapacitetsnivå som krävs.

Vid grovplanering reduceras den tillgängliga kapaciteten för en viss kapacitet för en resursgrupp när den läses in med en operation som kräver funktionen i fråga. Om operationen kräver fler än en funktion, reduceras kapaciteten för alla funktioner som krävs.

För varje datum är den krävda beräkningen:

*Tillgänglig kapacitet för en förmåga = kapacitet för en förmåga &ndash; tidsplanerad jobbeläggning för resursen med specifik kapacitet, inkluderad i resursgruppen &ndash; tidsplanerad operationsbeläggning för resurser med specifik kapacitet, inkluderad i resursgruppen &ndash; tidsplanerad operationsbeläggning för själva resursgruppen som kräver den specifika kapaciteten*

Det innebär att om belastningen på en viss resurs laddas, tas beläggningen med i beräkningen av resursgruppens tillgängliga kapacitet per kapacitet, eftersom beläggningen för en viss resurs minskar dess bidrag till resursgruppens kapacitet för en kapacitet oavsett om beläggningen för den specifika resursen är för den specifika funktionen. Om det finns en belastning på resursgruppsnivån beaktas den i beräkningen av resursgruppens tillgängliga kapacitet per möjlighet endast om beläggningen kommer från en åtgärd som kräver den specifika funktionen.

Ovanstående logik är komplicerad, eftersom den är densamma för varje typ av "egenskap", så att du använder grovplanering med begränsad kapacitet kräver att en avsevärd mängd data läses in.

## <a name="viewing-scheduling-engine-input-and-output"></a>Visar schemaläggning av motorinmatning och -utgång

Om du vill få detaljerad information om tids planeringsprocessens inmatning och utmatning, aktiverar du loggning genom att gå till **Organisationsadministration \> Konfigurera \> Schemaläggning \> Schemaläggning av Cockpit för spårning**.

Markera först **Aktivera loggning** i åtgärdsfönstret på den här sidan. Kör planering för tillverkningsordern. När du är klar återgår du till sidan **Schemaläggning av ockpit för spårning** och väljer **inaktivera loggning** i åtgärdsfönstret. Uppdatera sidan så visas en ny rad i rutnätet. Välj ny rad, välj **Hämta** i åtgärdsfönstret. På så sätt får du en .zip-komprimerad mapp med följande filer:

- **Log.txt** – den här loggfilen beskriver de steg som motorn går igenom. Det är mycket avancerat och kan vara lite överväldigande, men när det används som en del av att experimentera med flödesinställningarna för att lösa prestandaproblem är skillnaden mellan den första och sista raden att leta efter den exakta tid som schemaläggaren har lagt ned.
- **XmlModel.xml** - den här modellen innehåller den modell som har skapats i X++ och som motorn körs på. Det `JobId` som används i filen korreleras till den `RecId` från källregistret som innehåller jobben (`ReqRouteJob` eller `ProdRouteJob`). Det vanligaste som du letar efter i den här filen är att de datum som anges i `ConstraintJobStartsAt` och `ConstraintJobEndsAt` är förväntade, att `JobGoal` egenskapen är korrekt inställd och att jobben är relaterade till varandra genom `JobLink` begränsningarna.
- **XmlSlots.xml** - Detta innehåller alla arbetstider och kapacitetsreservationer som motorn har begärt. Kalenderns arbetstider och reservationer kommer endast att begäras av motorn för de tidsperioder då jobben (och en extra buffert) läggs till, så om filen innehåller tider för långt fram i tiden kan det vara en indikation på ett problem med inställningen. `ResourceProperty`-noderna visar för varje resurs vilka resursgrupper och funktioner den är associerad med för vilka perioder.
- **Result.xml** - Detta innehåller resultatet av tidsplaneringskörningen.

Observera att spårningsfunktionen kan lägga till avsevärda resultat, så använd den bara för att undersöka planering av specifika order på ett kontrollerat sätt. Om den aktiveras under en huvudplaneringskörning kommer den snabbt att nå sin storleksgräns och stoppa den.

## <a name="troubleshooting-performance"></a>Felsöka prestanda

Som kan förstås från alla föregående avsnitt finns det några fallgropar när det gäller installation och användning av schemaläggningsmotorn, vilket kan leda till prestandaproblem. Följande checklista kan användas för att felsöka sådana problem. Det är viktigt att titta närmare på alla punkter eftersom det oftast finns en kombination av flera faktorer som leder till problem.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Utför planering som en del av MPS när det inte behövs

Även om flöden används för tillverkningskontroll, t.ex. kostnadsredovisning och rapportering, kanske det inte är nödvändigt att beakta dem under MPS. I vissa fall räcker det med en produktionstid som har angetts som standard för artikeln för planering. Om du vill inaktivera flödesplanering ställer du in kapacitets tidsgränsen på noll. Om schemaläggning ska göras måste kapacitetsstängslet ställas in noggrant eftersom det kanske inte är nödvändigt att överväga rutter för hela MRP tidsgränsen för disponering.

Observera att om ordern inte har tidsplanerats under MPS måste den istället planeras när den planerade ordern bekräftas. Detta innebär att processen tar längre tid, så beroende på hur många av de föreslagna planerade order som har bekräftats prestanda vinsten under MPS kan det gå förlorat i bekräftelsen.

### <a name="route-with-unnecessary-operations"></a>Rutt med onödiga operationer

När du designar flödet är det en frestande att försöka utforma den verkliga världen exakt med alla steg produktionen går igenom. Även om detta kan vara användbart i vissa fall är det inte bra för prestandan eftersom motorn måste arbeta med större (både vad gäller jobb och begränsningar) och fler SQL-satser körs för infogning och uppdatering av jobb och kapacitetsreservationer. Det finns också en efterföljande effekt där du kan rapportera status för jobben, som kan minskas med automatiska bokföringar. Om data inte används för något skapas en onödig belastning.

Vi rekommenderar att du bara skapar åtgärder som är absolut nödvändiga för schemaläggning (som normalt är flaskhalsresurser) och/eller kostnadssyfte. Du bör även gruppera många mindre distinkta operationer i en större operation som representerar en större del av processen.

### <a name="many-applicable-resources-for-an-operation"></a>Många tillämpliga resurser för en operation

Antalet tillämpliga resurser för en operation bestäms av resurskraven som ställts in för operationsrelationen. Kravet kan antingen vara för en viss (enskild) resurs eller så kan den baseras på resursens medlemskap i en resursgrupp eller en funktion.

Om ingen tidsplanering görs med begränsad kapacitet och alla tillämpliga resurser har samma kalender och effektivitet, kommer planeringsmotorn alltid att välja samma resurs för en operation, men bara när du har försökt med alla tillämpliga resurser för att kontrollera om det finns något som är "bättre" än de andra. I det här fallet kan belastningen på tidsplaneringen minskas helt enkelt genom att alltid tilldela en specifik resurs till operationen vid flödets designtid.

### <a name="route-with-parallel-operations"></a>Flöde med parallella operationer

Parallella operationer (primära/sekundära) är ett kraftfullt verktyg för modellscenarier som när en dator och en operatör båda behöver för att utföra en viss uppgift, men den är också källan till många prestandaproblem. Om ett krav för en viss enskild resurs har tilldelats både den primära och den sekundära operationen, är det vanligtvis inget problem. Om det finns många möjliga resurser för varje operation lägger du emellertid till en avsevärd beräkningskomplexitet för tidsplaneringen.

Ett alternativ till att använda parallella operationer är att antingen modellera paren som "virtuella" resurser (som sedan representerar det team som alltid ska kopplas ihop) eller för att helt enkelt inte modellera en av operationerna om de inte representerar en flaskhals.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Rutt med resursmängder högre än 1

Om du ställer in den kvantitet av resurser som behövs för en operation som är högre än en, resulterar detta i ett effektivt resultat som att använda primära/sekundära operationer eftersom flera parallella jobb skickas till motorn. I detta fall kan du dock inte använda specifika resurstilldelningar eftersom en större kvantitet än en kräver att fler än en resurs kan användas för operationen.

### <a name="excessive-use-of-finite-capacity"></a>Överdriven användning av begränsad kapacitet

Användning av begränsad kapacitet kräver att motorn läser in kapacitetsinformationen från en databas och kan ha en beräkningsomgång, eftersom det är svårare att hitta en lösning som är mycket stor i miljöer där resurserna ligger nära sin maximala kapacitet. Det är därför viktigt att noggrant utvärdera om en resurs verkligen behöver använda begränsad kapacitet eller kan bli överbokad. Eftersom det kan finnas en skillnad mellan begränsade kapacitetsresurser i hur viktigt de inte är för att överboka, rekommenderar vi att du använder flaskhalsalternativet på en resurs i kombination med ett separat värde i planen i "Kapacitetsstängsel för flaskhalsresurser". Genom att använda ett flaskhalsbegrepp kan du göra så att den allmänna tidsgränsen för begränsad kapacitet sänks.

### <a name="setting-hard-links"></a>Ställa in hårda länkar

Standardlänktypen för flödet är *mjuk*, vilket innebär att en tidslucka är tillåten mellan sluttiden för en operation och starten på nästa. Att tillåta detta kan ha den olyckliga effekten att om material eller kapacitet inte finns tillgängligt för en av verksamheterna under mycket lång tid, kan produktionen vara inaktiv under ett tag, vilket innebär en möjlig ökning av pågående arbete. Det här händer inte när du tar med hårda länkar, eftersom slut och start måste justeras helt. Om du ställer in hårda länkar blir det svårare att schemalägga, eftersom arbetstid och skärningspunkter för kapacitet måste beräknas för de två resurserna i operationerna. Om det också finns parallella operationer lägger detta till en avsevärd beräkningstid. Om resurserna för de två operationerna har olika kalendrar som inte överlappar varandra kan problemet inte lösas.

Vi rekommenderar att du endast använder hårda länkar om det är absolut nödvändigt och noga fundera över om det är nödvändigt för varje operation av flödet.

Om du vill minska det pågående arbetet utan att använda hårda länkar, kan du schemalägga ordern två gånger och ändra till motsatt riktning för det andra steget. Om det första schemat utfördes bakåt från leveransdatum, ska det andra utföras framåt från det planerade startdatumet. Detta medför att jobben komprimeras så mycket som möjligt så att pågående arbete minimeras.

### <a name="separate-calendar-for-each-resource"></a>Separat kalender för varje resurs

En av huvuddatakällorna för planeringsmotorn är kalenderinformation, som kan vara dyrt att läsa från databasen. Eftersom kalendrar skapas baserat på mallar, skulle det vara frestande att skapa en kalender för varje resurs och sedan justera informationen i den här kalendern när resursen har driftstopp och andra problem. Om du gör detta begränsas i hög grad motorernas kapacitet att cachelagra kalenderdata eftersom det skulle behöva begära nya data för varje resurs och kan bli en stor källa med prestandaproblem. I stället rekommenderar vi att du återanvänder kalendrarna så mycket som möjligt mellan resurserna och sedan kontrollerar ändringar i driftstopp genom att tilldela ett annat kalender-ID för en period.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Högt antal arbetstidsplatser per kalenderdag

Eftersom motorn fungerar genom att undersöka tidsluckor en efter en för kapacitet, är det fördelaktigt att minimera antalet tidsluckor per kalenderdag. Detta kan till exempel göras om det är viktigt för schemat som visar att arbetstagarna har en fem minuters rast varje timme.

### <a name="large-or-none-scheduling-timeouts"></a>Stora (eller inga) tidsgräns för tidsplanering

Planeringsmotorns prestanda kan optimeras med hjälp av de parametrar som finns på sidan **Planeringsparametrar**. Inställningarna **tidsgräns för tidsplanering aktiverad** och **tidsgräns för optimering av tidsplanering aktiverad** bör alltid vara inställda på **Ja**. Om alternativet har värdet **Nej** kan tidsplaneringen köras oändligt om en ogenomförbar väg med många alternativ har skapats.

Värdet för **maximal planeringstid per sekvens** styr hur många sekunder som mest kan ägna sig åt att försöka hitta en lösning för en enskild sekvens (i de flesta fall motsvarar en sekvens en enda order). Vilket värde som ska användas här beror på hur komplex flödet är och vilka inställningar som inte är ändlig, och det är en bra utgångspunkt för maximalt 30 sekunder.

Värdet för **Tidsgräns för optimeringsförsök** styr hur många sekunder som oftast kan användas för att hitta en bättre lösning än den som ursprungligen hittades. Detta påverkar bara vägar som använder parallella operationer eftersom de gör det nödvändigt att testa olika kombinationer.

> [!NOTE]
> De värden som anges för tidsgräns används både för planering av släppta produktionsorder och planerade order som en del av MPS. Det innebär att om du ställer in mycket höga värden kan du markant lägga till produktionstiden för MPS när den körs för en plan med många planerade tillverkningsorder.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]