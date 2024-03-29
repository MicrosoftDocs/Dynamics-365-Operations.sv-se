---
title: Bonusöversikt
description: Denna artikel beskriver lojalitetsfunktioner i Dynamics 365 Commerce och motsvarande inställningssteg för att hjälpa återförsäljaren att snabbt komma igång med sina bonusprogram.
author: josaw1
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.custom: 16201, "intro-internal"
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
ms.openlocfilehash: 17742bb5c0091804fc6f43bb2aabb7af73229890
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2022
ms.locfileid: "9784975"
---
# <a name="loyalty-overview"></a>Lojalitetsöversikt

[!include [banner](includes/banner.md)]

Bonusprogram kan öka kundlojaliteten genom att kunderna belönas för deras samverkan med återförsäljarens varumärke. I Dynamics 365 Commerce kan du konfigurera enkla eller komplexa bonusprogram som gäller för dina juridiska personer i en handelskanal. Denna artikel beskriver lojalitetsfunktioner i Commerce och motsvarande inställningssteg för att hjälpa återförsäljaren att snabbt komma igång med sina bonusprogram.

Du kan konfigurera bonusprogram, så att de omfattar följande alternativ.

- Ställ in flera typer av belöningar som du erbjuder i dina bonusprogram och spåra deltagandet i dina bonusprogram.
- Ställa in bonusprogram för att identifiera de olika bonusersättningar som du erbjuder. Du kan inkludera bonusprogramnivåer om du vill erbjuda vara större och belöningar för kunder som butik vanligare eller håller mer pengar i din butik.
- Definiera intäktsregler för att identifiera aktiviteter som en kund måste utföra för att få bonus. Du kan också definiera befrielseregler att identifiera när och hur en kund kan lösa in belöningar.
- Utfärda förmånskort från någon kanal som deltar i dina bonusprogram och länka bonuskort till ett eller flera bonusprogram som kunden kan delta i. Du kan även länka en kundpost till bonuskortet så att kunden kan slå samman bonuspoäng från flera kort och lösa in dem.
- Justera förmånskort eller överför bonussaldon manuellt från ett kort till ett annat för att kunna lagra eller belöna en kund.

Följande video innehåller en översikt över bedömningar och demo av lojalitetsfunktioner i Dynamics 365 Commerce.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5c2wW]

## <a name="setting-up-loyalty-programs"></a>Ställa in bonusprogram

Du måste konfigurera flera komponenter om du vill aktivera lojalitetsfunktionen i Commerce. I bilden nedan visas lojalitetskomponenterna och hur de är relaterade till varandra.

![Processflöde för bonus.](./media/loyaltyprocess.gif "Förmånskomponenter och hur de relaterar till varandra")

## <a name="loyalty-components"></a>Bonuskomponenter

I tabellen nedan beskrivs varje komponent och var den används i lojalitetinställningarna.

| Komponent                                        | beskrivning | Var detta används |
|--------------------------------------------------|-------------|-----------------|
| Ställa in rabatter (förutsättning)                  | Ställa in rabatter som du erbjuder dina förmånskunder. Exempelvis kan du erbjuda 5 procents avdrag på alla kläder. | Rabatter måste läggas till i prisgrupper innan de tas med i ett bonusprogram. Prisgrupper tilldelas till bonusprogram och förmånsnivåer. |
| Ställa in prisgrupper (förutsättning)               | Prisgrupper används för att skapa och hantera priser och rabatter för produkter. Ställa in de prisgrupper som inkluderar rabatter som gäller för dina bonusprogram. | Prisgrupper tilldelas till bonusprogram och bonusprogramnivåer. |
| Ställa in kanaler (förutsättning)                   | Handelskanaler är de butiker som ska delta i dina bonusprogram, till exempel fysiska butiker, online-butiker eller kundtjänster. Du måste konfigurera dina handelskanaler innan du kan tilldela bonusprogram till dem. | Du tilldelar kanaler till ett bonusprogram, om kanalen deltar i bonusprogrammet. |
| Ställa in en förmånsbetalningsmetod (förutsättning) | För att se till att förmånspoängen kan lösas in i vilken kanal som helst, till exempel i fysiska butiker, onlinebutiker eller kundtjänst, måste du konfigurera lagerplatsområdet för förmånskorten på sidan **kortnummer**. | Ställa in en förmånstypsbetalningsmetod och sedan tilldela förmånsbetalsättet till de kanalerna som deltar i bonusprogrammet. |
| Ställa in datumintervall                            | Datumintervall är ett flexibelt sätt att ange tidsspann för bonusnivåer. Använd datumintervall för att ange hur länge en kund kan förbli på en nivå eller hur lång tid en kund måste utföra en aktivitet för att kvalificera för en nivå. | Datumintervall är endast tillgängliga om du använder nivåer i dina bonusprogram. Du väljer det datumintervall som gäller för programnivåerna, och även datumintervallen som gäller för programnivåreglerna. |
| Ställa in belöningspoäng                             | Belöningspoäng är olika typer av belöningar som du erbjuder kunderna. Belöningspoäng kan vara inlösbara eller icke-inlösbara. Inlösbara belöningspoäng kan bytas ut mot produkter. Icke-inlösbara belöningspoäng används för att spåra syften eller för att flytta en kund till nästa nivå i ett bonusprogram. | Belöningspoäng refereras i nivåregler och används för att kvalificera en kund för en viss nivå. Belöningspoäng refereras också i förmånsscheman i förtjänst- och befrielseregler. I intäktsregler anger du belöningar som en kund kan tjäna för en viss aktivitet. I befrielseregler anger du den belöning som kunden kan lösa in. |
| Ställa in bonusprogram                          | Bonusprogram är den viktigaste förmånen som du erbjuder. Varje bonusprogram kan även ha tilldelade förmånsnivåer. Rabatter och prisgrupper tilldelas till bonusprogrammen på antingen programnivå eller bonusnivå. | Du skapar förmånsscheman för dina bonusprogram. Du tilldelar förmånskort till dina bonusprogram, förmånskort och kan tilldelas till en kund. Kanaler deltar i bonusprogrammen som har tilldelats till förmånsscheman. Kunder med förmånskort kan delta i de bonusprogram som är tilldelade till kortet. |
| Ställa in förmånsnivåer och nivåregler              | Lojalitetsnivåer är valfria nivåer som du kan definiera för dina bonusprogram. Du kan konfigurera basrabatter och belöningar för alla kunder som deltar i bonusprogrammet, och du kan konfigurera ytterligare rabatter och belöningar för kunder som hanterar andra nivåerna i programmet. För varje lojalitetnivå som du definierar kan du konfigurera reglerna som kvalificerar en kund för varje nivå. Du kan också definiera hur länge en kund kan ligga kvar i nivå, när de har nått den. | Lojalitetsnivåer och lojalitetsnivåregler definieras i bonusprogrammen. Om du inte anger några lojalitetnivåer, kvalificerar alla kunder som deltar i bonusprogrammet sig för de rabatter som du tilldelar i bonusprogramprisgruppen. Om du definierar lojalitetsnivåer, kan du konfigurera förtjänstregler och befrielseregler för lojalitetsnivåerna i bonusprogrammet. |
| Ställa in förmånsscheman                           | Lojalitetsscheman anger de intjänings- och inlösningsregler som gäller för ett valt bonusprogram. Du tilldelar kanaler till ett förmånsschema att identifiera som bonusprogrammet och att tjäna regler och befrielseregler gäller för en butik. | Ett förmånsschema tilldelas till ett bonusprogram och till kanaler. Du kan tilldela många Förmånsscheman till samma bonusprogrammet, och du kan tilldela många Förmånsscheman till många kanaler. |
| Ställa in förmånskort                             | Ett förmånskort ger kortinnehavaren rätt att delta i de bonusprogram som är tilldelade till kortet. Förmånskort går att utfärda anonymt, eller tilldelas till en viss kund. Du kan visa förmånstransaktionerna för ett visst kort, och du kan visa en sammanfattning av förmånspoäng som har ackumulerats på kortet. Du kan utfärda förmånskort från en kanal. Du kan också manuellt justera ett förmånskort för uppgradering kunden till en annan nivå, för att lägga till förmånspoäng eller överföra lojalitetpoängsaldot från ett kort till en annan. | Du tilldelar bonusprogram till ett förmånskort. |

## <a name="loyalty-processes"></a>Bonusprocesser

I tabellen nedan beskrivs de processer som måste köras för att skicka bonuskonfigurationerna och data till dina butiker, och hämta bonuskonfigurationerna från din butik.

| Processnamn                         | Beskrivning | Sidnamn |
|--------------------------------------|-------------|-----------|
| 1050 (information om förmåner)           | Kör den här processen för att skicka förmånskonfigurationsdata till butikerna. Det är en bra idé att tidsplanera den här processen om du vill köra den ofta, så att bonusdata överförs till alla butiker. | Distributionsschema |
| Bearbeta förmånsscheman              | Kör den här processen för att associera förmånsscheman med de kanaler som förmånsschemat är tilldelat till. Den här processen kan schemaläggas för att köras som en batchprocess. Du måste köra den här processen, om du ändrar bonuskonfigurationsdata, till exempel bonusscheman, bonusprogram, eller bonusbelöningspoäng. | Bearbeta förmånsscheman |
| Bokför intjänade förmånspoäng i batchar | Kör den här processen om du vill uppdatera förmånskort för att inkludera transaktioner som har bearbetats offline. Den här processen gäller bara om kryssrutan **Bokför intjänade poäng i batchar** markeras på sidan **Gemensamma delade handelsparametrar** så att belöningar kan tjänas offline. | Bokför intjänade förmånspoäng i batchar |
| Uppdatera skikt för förmånskort            | Kör den här processen för att utvärdera kundens inkomstaktivitet mot nivåreglerna för ett bonusprogram och uppdatera kundens nivåstatus. Den här processen behövs bara om du ändrar nivåreglerna i bonusprogrammen och du vill tillämpa de uppdaterade reglerna retroaktivt för förmånskort som redan har utfärdats. Den här processen kan köras som en batchprocess eller för enskilda kort. | Uppdatera skikt för förmånskort |

## <a name="loyalty-capabilities"></a>Förmånsfunktioner

- Med hjälp av prisgrupperna som är kopplade till bonusprogram och förmånsnivåer kan återförsäljare enkelt skapa särskilda priser och rabatter för förmånsmedlemmar.

- Som en del av ett bonusprogram kan återförsäljare skapa olika regler för inkomst och inlösen genom nivåer för att skilja belöningar för kunder på olika nivåer. Återförsäljare kan även inkludera ”anknytningar” som en del av reglerna för inkomst och inlösen så att viss grupp av kunder kan tillhöra en befintlig nivå, men fortfarande belönas på ett annat sätt. Detta tar bort behovet av att skapa fler nivåer.
    
    > [!NOTE]
    > Inkomstregler inom ett bonusprogram är extra. Till exempel om du skapar en regel som belönar guldmedlem med 10 poäng för varje USD och du även skapar en regel för en kund med ”veteran”-anknytning till en belöning på 5 poäng för varje USD, skulle en veterananvändare som även ingår i guldnivån få 15 poäng för 1 USD eftersom kunden uppfyller kraven för båda raderna. Men om veterankunden inte var guldmedlem skulle kunden få 5 poäng för varje USD. För att reflektera ändringarna i kanalerna, kör **Bearbeta förmånsscheman** och **1050** (information om förmåner) jobb.
    
    ![Anknytningsbaserad inkomst.](./media/Affiliation-based-earning.png "Anknytningsbaserad inkomst")

- Återförsäljare har ofta särskilda priser för en viss grupp av kunder som de inte vill att bonusprogram ska gälla. T.ex. grossister och anställda som får specialpriser och inga förmånspoäng. Vanligtvis används ”anknytningar” för att ge specialpriser till sådana kundgrupper. Om återförsäljaren vill förhindra att vissa kundgrupper tjänar förmånspoäng kan återförsäljaren ange en eller flera anknytningar under avsnittet **Undantagna anknytningar** i bonusprogrammet. På så sätt när kunder som hör till undantagna anknytningar är befintliga lojalitetsmedlemmar har de inte möjlighet att tjäna förmånspoäng för sina inköp. För att reflektera ändringarna i kanalerna, kör **Bearbeta förmånsscheman** och **1050** (information om förmåner) jobb.

    ![Undantagna anknytningar.](./media/Excluded-affiliations.png "Undanta anknytningar från att tjäna förmånspoäng")
    
- POS gör det möjligt för återförsäljare att antingen använda fysiska förmånskort eller generera ett unikt förmånskortsnummer automatiskt. Om du vill aktivera automatisk generering av förmånskort butiker aktiverar du **generera förmånskortnummer** i funktionsprofilen som är kopplad till butiken. För onlinekanaler, kan återförsäljare använda IssueLoyaltyCard-API för att utfärda förmånskort till kunder. Återförsäljare kan antingen tillhandahålla ett förmånskortnummer till denna API, som används för att generera förmånskortet, eller så kommer systemet att använda förmånskortets nummerserie i Commerce. Men om nummerserien inte finns och återförsäljaren inte tillhandahåller ett förmånskortnummer när API anropas visas ett felmeddelande.

    ![Generera förmånskort.](./media/Generate-loyalty-card.png "Generera automatiskt förmånskortnummer")

- Intjänad och inlösta förmånspoäng sparas nu för varje transaktion och försäljningsorder mot försäljningsraden, så att samma belopp kan återbetalas eller tas tillbaka vid hela eller delvisa returer. Dessutom ger synliggörs för punkterna på försäljningsraden nivå möjlighet till call center användarna besvara kundfrågor om hur många poäng som har erhållits eller löses in för varje rad. Före ändringen räknades alltid belöningspoängen om vid returer som resulterade i ett annat belopp än det ursprungligt om reglerna för inkomst eller inlösen ändrades och även användarna av kundtjänst syntes inte på poängfördelningen. Poängen visas under formuläret **korttransaktioner** för varje förmånskort. För att aktivera den här funktionen aktiverar du konfigurationen **Bokför förmånspoäng per försäljningsrad** under **Delade handelsparametrar** \> **Allmänt**.

    > [!NOTE]
    > Du rekommenderas starkt att aktivera den här funktionen så att vid returer kan rätt mängd punkter återbetalas eller hämtas från kunden.

- Återförsäljare kan nu ange överlåtelseperiod för varje belöningspoäng. En överlåtelseperiodkonfiguration definierar varaktighet från tjänstedatum, varefter belöningspoängen skulle bli tillgängliga för kunderna. Ej erhållna poäng kan visas i kolumnen **Ej erhållna poäng** på sidan **förmånskort**. När kunderna returnerar vissa artiklar för vilka förmånspoängen intjänades, kommer systemet som standard att dra av de avsatta punkterna först och sedan dra tillbaka saldot från tillgängliga punkter. Du kan dock endast ställa av tillgängliga punkter i stället för att dra bort från ej intjänade poäng.

Återförsäljare kan dessutom definiera maximal gräns för förmånsbelöningspoäng per förmånskort. Det här fältet kan användas för att minska effekten av förmånskortbedrägeri. När den maximala belöningspoängen har nåtts, kan inte användaren får mer poäng. Återförsäljaren kan välja att blockera sådana kort tills de har undersökts för eventuella bedrägerier. Om återförsäljaren avgör bedrägeri, kan inte återförsäljaren bara spärra förmånskortet för kunden utan även markera kunden som blockerades. För att göra detta, ange egenskapen **spärra kunden för registrering av förmåner** till **Ja** under **alla kunder** på snabbfliken **Commerce**. Spärrade kunder kommer inte att utfärda ett förmånskort i någon av kanalerna.

   ![Överlåtelse och maximala belöningspoäng.](./media/Vesting-and-maximum-reward-points.png "Definiera överlåtelse och maximal belöningspoäng")

- Anknytningar används för att tillhandahålla särskilda priser och rabatter, men det finns vissa anknytningar som återförsäljare inte vill visa kunderna. Exempelvis en anknytning som heter ”kund som spenderar mycket” kanske inte tas emot väl av kunder. Dessutom finns vissa anknytningar som inte kan hanteras i butiken, till exempel anställda, eftersom du inte vill att kassörerna bestämmer vem som är en medarbetare och därmed ge medarbetarbaserade rabatter. Nu kan återförsäljare välja anknytningar som ska döljas i kanalerna. Anknytningar som är markerade som **dölja i kanaler** kan inte visas, läggas till eller tas bort i POS. Men priser och rabatter som är kopplade till anknytningen kan fortfarande tillämpas på produkterna.

    ![Dölj anknytningar.](./media/Hide-affiliations.png "Dölj anknytningar i kanaler")
    
- Användare av kundtjänst kan nu enklare söka efter en kund med deras information om förmånskort och navigera till kundens förmånskort och transaktionssidan för lojalitetskort från sidan **kundtjänst**.

    ![Kundtjänst.](./media/Customer-service.png "Hitta information om förmåner för kunden")
    
- Om ett förmånskort skadas behöver ett nytt kort skapas och befintliga poäng överföras till det nya kortet Ersättningskortet har förenklats i den här versionen. Kunder kan dessutom ge bort några eller alla deras förmånspoäng till familj och vänner. När poängen överförs skapas poängjusteringsposter för varje förmånskort. Ersättningskort och funktionen för överföring av saldo kan nås från sidan **förmånskort**.

    ![Ersätta och överföra poäng.](./media/Replace-and-transfer-points.png "Ersätt förmånskort eller överför saldo")
    
- Återförsäljare kanske vill fånga effektiviteten hos en viss kanal för att registrera kunder i ett bonusprogram. Registreringskällan för förmånskort sparas nu så att återförsäljare kan köra rapporter med dessa data. Registreringskällan inhämtas automatiskt för alla utfärdade förmånskort från MOPS/CPOS eller näthandelsföretagskanaler. För förmånskort som utfärdats av back office-programmet, kan användaren av kundtjänst välja korrekt kanal.
- I tidigare versioner kan återförsäljare använda MOPS/CPOS för att lösa in förmånspoäng för kunder i en butik. Men i dessa versioner, eftersom förmånssaldot visas i förmånspoäng, kan kassören inte visa valutabeloppvärdet som kunde tillämpas mot den aktuella transaktionen. Kassören var tvungen att göra valutakonvertering innan betalning med förmånspoäng. I den aktuella versionen när komponentraderna läggs till transaktionen kan kassören se beloppet som förmånspoängen kan täcka för den aktuella transaktionen vilket gör det enkelt att tillämpa hela eller delar av förmånspoängen till transaktionen. Kassören kan dessutom se poäng som löper ut inom de kommande 30 dagarna så att de kan göra merförsäljning eller korsförsäljning för att motivera kunden att spendera de poäng som snart förfaller på den transaktionen.

    ![Poäng som täcks av bonussaldot.](./media/Points-covered-by-loyalty-balance.png "Visa saldo som täcks av lojalitetspoäng")

    ![Poäng som löper ut.](./media/Expiring-points.png "Visa utgångna punkter")

- Med 8.1.3 frisläppning vi har aktiverat alternativet ”betald av förmånskort” i kundtjänstkanalen. Om du vill aktivera det här alternativet skapar du en typen för förmånsbetalningsmedel och associerar den till en kundtjänst. 

    > [!NOTE]
    > Eftersom lojalitetsbetalningarna är inställda som kortbetalningar du måste välja ett kort från sidan **kortinställningar**. 

    ![Inställning av bonuskort.](./media/LoyaltyCardSetup.png "Inställning av förmånskort")

    När detta har ställts in kunder lösa in sina förmånspoäng i kundtjänst. Dessutom förbättrar vi användargränssnittet för att visa ”Belopp som täcks av förmånspoäng”, så att kundtjänstanvändare inte behöver gå till en annan skärm för att visa förmånskortets saldo.

- Många återförsäljare kan tilldela förmånspoäng endast utifrån försäljningstransaktionerna men mer kundinriktade återförsäljare vill belöna kunderna för deras åtagande med deras varumärke. Till exempel vill de ge belöningar för att fylla en online-undersökning, besöka en butik, gilla återförsäljare på Facebook, twittra om återförsäljaren med mera. För att göra detta kan återförsäljaren definiera en ”andra aktivitetstyp” och definiera inkomstreglerna för aktiviteterna. Det finns också en exponeras Skalningsenhet för handel API ”PostNonTransactionalActivityLoyaltyPoints” som kan anropas när en aktivitet identifieras att belöna kunden med förmånspoäng. Detta API förväntar sig att förmåner kort-ID, kanal-ID och annan aktivitetstyp-ID, så att den kund som ska tilldelas kan finnas inkomstregeln för aktiviteten kan identifieras. 

    Tilldelning av poäng för icke-transaktionsaktiviteter vanligtvis består av två steg:

    - Att uppnå en aktivitet har inträffat som borde belönas.
    - Belöna lämpliga punkter.

    Det första steget är utanför Commerce t.ex. twittra om varumärke eller gilla varumärket på Facebook. När aktiviteten har identifierats kan återförsäljarna anropa ovannämnda skalningsenhet för handel API och tilldela förmånspoäng i realtid. I sådana scenarier behövs det inte några granskningssteg eftersom en aktivitet har inträffat och motsvarande punkter ska tilldelas. Det finns scenarier där återförsäljaren vill granska posterna innan tilldelning av poäng. Återförsäljaren måste till exempel konfigurera en workshop i butiken som kunderna registrerar sig för på webbplatsen för näthandel eller andra program för händelseregistrering. Endast de deltagande kunderna tjänar lojalitetspoäng. För sådana scenarier introducerar vi i version 10.0 en dataentitet med namnet **Butikens förmåner andra aktivitetstyprader**. Denna dataentitet låter återförsäljare använda Data Import/Export Framework (DIXF) eller OData-API för att registrera de aktiviteter för att tilldela kunder förmånspoäng. Dataentiteten lagrar aktiviteterna i en journal med namnet **lojalitetsrader för andra aktiviteter**, som kan användas för granskning och ändring. När data har granskats kan IT-användaren manuellt bokföra aktivitetsraderna eller köra ett jobb som heter **bearbeta annan aktivitetstyp för lojalitetsrader**, som kommer att bokföra alla ej bokförda aktivitetsrader och tilldela poäng till kunder baserat på inkomstreglerna. I fallet ovan skulle händelseregistreringen kräva OData API för att skicka kundinformation till Commerce. Men IT-användaren kan endast bokföra aktivitetsraderna för kunder som har deltagit i verkstaden och ta bort aktivitetsraderna för andra kunder. 

    > [!NOTE]
    > För närvarande tvingar systemet användare att konfigurera en nummerserie för ”andra aktivitetstyper”, men detta blir inte ett obligatoriskt steg i framtida versioner. Om du vill konfigurera en nummerserie gå till **Delade handelsparametrar** \> **Nummerserier** och välj en nummerserie för **Lojalitets-ID för annan aktivitetstyp**.

- För att ge bra kundservice och effektivt lösa kundfrågor är det viktigt för kassörerna att få tillgång till fullständig kundprofil. Med version 10.0 kommer kassörerna kunna se historikinformation tillsammans med den associerade lojalitetsprogrammet och nivåinformation för kassa.
- Gratis eller rabatterad leverans är en mycket motiverande faktor för kunderna att handla online. Om du vill aktivera återförsäljare för att konfigurera leveranserbjudanden introducerar vi med version 10.0 en ny typ av kampanj kallad "Tröskelrabatt för leverans" där återförsäljaren kan definiera de tröskelvärden som, när de uppfylls, berättigar kunderna till gratis eller rabatterad leverans. Spendera till exempel 35 $ för gratis "två dagars leverans" eller "två dagars leverans" för alla förmånskunder. Den här funktionen använder den nya funktionen för avancerade automatiska avgifter. Se [dokumentationen för avancerade automatiska avgifter](/dynamics365/unified-operations/retail/omni-auto-charges). Dessa avancerade automatiska avgifter måste aktiveras för att leveranserbjudandet ska fungera. Dessa kan aktiveras från fliken **kundorder** på sidan **Handelsparametrar** och aktivera konfigurationen ”Använd avancerade automatiska avgifter”. Dessutom, eftersom en återförsäljare kan konfigurera flera typer av avgifter, till exempel hantering eller installation måste den ange vilka avgifter anses vara leveransavgifter. Leveransrabatterna används bara i leveransavgifterna. För att ange avgifter som leveransavgifter, gå till formuläret **avgiftskoder** som finns under **Butik och handel** \> **Butik och handel-IT** \> **Kanalinställning** \> **Avgifter** och markera kryssrutan ”leveransavgifter” för önskade avgifter. Nu kan du gå till formuläret **Tröskelrabatt för leverans** för att konfigurera rabatten.

    Liksom produktrabatter, godkänner den här rabatten alla befintliga standardrabatter, till exempel att återförsäljaren kan begränsa rabatterna med kuponger så att bara kunder med kuponger får rabatterna. Dessutom utnyttjar rabatterna prisgrupper för att avgöra berättigande till sådana rabatter. Exempelvis kan återförsäljaren välja att endast köra dessa erbjudanden i online-kanaler och/eller i kanaler för vissa kundgrupper, exempelvis förmånskunder. När orderrader med angivet leveranssätt uppfyller det definierade tröskelvärdet tillämpas leveransrabatten och minskar leveranskostnaden baserat på den rabatt som anges. 

    > [!NOTE]
    > Till skillnad från andra tidsbegränsade rabatter bl.a kvantitet, enkla, mixa och matcha och tröskelvärde skapar leveransrabatten inte rabattrader, utan snarare redigerar leveransavgifter direkt och lägger till rabattens namn i avgiftsbeskrivningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
