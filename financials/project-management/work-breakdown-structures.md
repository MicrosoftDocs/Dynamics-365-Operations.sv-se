---
title: Uppdelade arbetsstrukturer
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 1666691ec122e65128b74056817a0c40551f49b5
ms.lasthandoff: 03/31/2017


---

# <a name="work-breakdown-structures"></a>Uppdelade arbetsstrukturer



Uppdelade arbetsstrukturer En uppdelad arbetsstruktur (WBS) är en beskrivning av det arbetet utförs för ett projekt. Det är en hierarki med uppgifter som representerar projektteamets kännedom om sammansättningen av arbete och storleken, kostnaden och tidslängden för varje komponent eller uppgift. En WBS har tre viktiga syften:

-   Beskriva uppdelningen eller sammansättningen av arbete i uppgifter.
-   Tidsplanera projektarbetet.
-   Beräkna kostnaden för varje uppgift.

Graden av information i en WBS beror på noggrannhetsnivån som krävs i uppskattningarna och spårningsnivån som krävs för dessa uppskattningar. Projekt som har mycket låg tolerans för förseningar i schema eller kostnad kräver vanligtvis en mer detaljerad WBS och noggrann spårning av arbetsförloppet och kostnader mot WBS. Den här typen av projektet är vanliga för byggnads- och maskinindustrin. 

I motsats till branscher som till exempel media och reklam, programvara och en IT-infrastruktur, tenderar projekt att vara unika och produktivitet är relativt erfarenheten och kompetensen hos individen som utför uppgiften. Därför använder sådana branscher WBS för att få en approximering av storleken på ett projekt, inte för att följa förloppet projektet i detalj. 

Att skapa en WBS är en intensiv process som vanligen utförs över en lång period och som kräver samarbete med och information från många olika personer. Det här avsnittet beskrivs hur du använder struktur förbättringar i Microsoft Dynamics 365 för operationer efter behov för uppskattningar och spårning.

## <a name="prerequisites-for-creating-a-wbs"></a>Förutsättningar för att skapa en WBS
Om du vill skapa en WBS måste du kunna skapa ett arbetsschema och uppskatta arbetskostnaden.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Förutsättningar för att skapa ett arbetsschema

Utför följande inställningar för att använda schemaläggning utökar funktionerna struktur:

1.  Ställ in en standardinställningskalender och en projektkalender:
    1.  Klicka på **projekthantering och redovisning**&gt;**inställningar**&gt;**tidsplanering**. Ange en standardkalender i fältet **Standardarbetskalender**. Den blir standardarbetskalender för alla nya projekt som skapas.
    2.  Det går att ändra standardkalendern för ett visst projekt. Klicka på projektets detaljsida och sedan på snabbfliken **Projektteam och schemaläggning**, uppdatera fältet **Tidsplaneringskalender** genom att välja en annan kalender.

2.  Ställ in arbetsdagarna och arbetstiden. Kalendern som du ställer in som arbetskalender för ditt projekt används i WBS för att bestämma följande information:

-   Arbetsdagar och helgdagar
-   Antal arbetstimmar per dag

Ange arbetsdagar och arbetstimmar för en kalender eller skapa en ny kalender klickar du på **Organisationsadministration**&gt;**gemensamma**&gt;**kalendrar**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Förutsättningar för beräkning av arbetskostnader

Använd fullständig kostnadsredovisning i WBS genom att ställa in kostnaderna och försäljningspriserna för anställda, arbetskategorier, utgifter och avgifter och artiklar.

-   Ställ in självkostnads- och försäljningspris för arbete, utgifts- och avgiftskategorier genom att klicka på **projekthantering och redovisning**&gt;**inställningar**&gt;**priser**.
-   Ställa in kostnad och försäljningspris för artiklar på sidan **Handelsavtal** för varje artikel på listsidan **Frisläppta produkter** i Produktinformationshantering.

## <a name="creating-a-wbs"></a>Skapa en WBS
När du skapar en WBS ingår tre aktiviteter:

1.  **Arbetsuppdelning** – Skapa en uppdelning av arbete i hanterbara bitar eller uppgifter.
2.  **Arbetsschema** – Beräkna tiden som krävs för att utföra en uppgift, ställ in uppgiftsberoenden och välj start - och slutdatum för uppgifter.
3.  **Kostnadsuppskattning** – Uppskatta kostnader för varje uppgift.

I avsnitten nedan beskrivs funktionerna struktur hur med var och en av aktiviteterna.

### <a name="work-decomposition"></a>Arbetsuppdelning

Om du vill skapa en arbetsuppdelning är vanligtvis det första steget i processen i att skapa en WBS. Struktur-funktion stöder följande grundläggande konstruktioner för fördelning av resurser eller nedbrytning. 

**Projektrotuppgift** Projektrotuppgiften är sammanfattningen på högsta nivå för ett projekt. Alla andra projektuppgifter skapas under den. Namnet på rotuppgiften anges alltid i projektets namn. Insatsen, data och tidslängd för rotnoden sammanfattar värdena för uppgifterna under rotuppgiften. Du kan inte ändra egenskaperna för rotnoden eller radera den.

**Sammanfattnings- eller behållaruppgifter** En sammanfattningsuppgift är en uppgift som har under- eller deluppgifter under sig. En sammanfattningsuppgift har inte en egen arbetsinsats eller kostnad. I stället är arbetsinsatsen och kostnaden för en sammanfattningsuppgift summan av arbetsinsatsen och kostnaden för dess deluppgifter. Tidigaste startdatum för deluppgifterna används som startdatum för sammanfattningsuppgiften och senaste slutdatum för deluppgifterna används som slutdatum. Du kan ändra namnet på en sammanfattningsuppgift men du kan inte ändra planeringsegenskaperna för insats, datum och tidslängd. Om du tar bort en sammanfattningsuppgift tar du bort också alla dess deluppgifter. 

**Lövnoduppgifter** En lövnoduppgift representerar det mest grundläggande arbetspaketet för projektet. En lövnod har ett beräknad insats, ett planerat antal resurser, ett planerat startdatum och slutdatum och tidslängd. 

Du kan slutföra följande hierarkioperationer om du vill aktivera generering av en arbetshierarki eller uppdelning för ett projekt. 

**Ny uppgift** Alla nya uppgifter som du skapar läggs till automatiskt under rotnoden och ett WBS-nummer tilldelas automatiskt till uppgiften. WBS-numret representerar uppgiftens nivå i hierarkin. För uppgifter i den första nivån under projektrotuppgiften används numreringen 1, 2, 3 och så vidare. För uppgifter under den första nivån används numreringen 1.1, 1.2, 1.3 och så vidare. För varje nivå som läggs till under en föregående nivå anges i en ny prickig serie med nummer. 

För närvarande kan du inte anpassa numrering för WBS. 

**Dra in uppgift** När du drar in en uppgift blir den underordnad föregående uppgift. WBS-numret för den nya underordnade uppgiften omräknas automatiskt baserat på WBS-numret för dess nya överordnade. Den överordnade uppgiften är nu en sammanfattnings- eller behållaruppgift och blir därför en summering av dess deluppgifter. 

> [!NOTE] 
> När du drar in aktiviteter under en uppgift som har en lövnod innan operationen indrag förlorar nyskapade sammanfattningsaktivitet sin egen datum, kraft och antal resurser. Den använder nu en sammanfattning av värdena för dess nya deluppgifter. 

**Dra ut uppgift** När du drar ut en uppgift är den inte längre det överordnade objektets deluppgift. WBS-numret för den här uppgiften beräknas om automatiskt efter uppgiftens nya nivå i hierarkin. Insats, kostnad och data för uppgiftens tidigare överordnade uppgift beräknas om för att exkludera den uppgiften. 

**Flytta upp och flytta ned** När du klickar på **Flytta upp** och **Flytta ned**ändrar du platsen för en uppgift i det överordnade objektets hierarki. Placeringen av en uppgift påverkar inte uppgiftens insats, kostnad, datum eller varaktighet. WBS-numret för uppgiften beräknas dock om automatiskt enligt uppgiftens nya placering.

### <a name="schedule-estimation"></a>Tidsplanuppskattning

Tidsplanuppskattning är vanligtvis det andra steget i att skapa en WBS. Som bästa praxis bör du slutföra tidsplanuppskattning efter att du skapar uppgifterna. Den **struktur** sidan i Microsoft Dynamics 365 för operationen har två delar. Det övre fönstret är avsett för tidsplanuppskattning och det nedre fönstret innehåller fliken **Uppskattade kostnader och intäkter** som du kan använda för kostnadsuppskattning. 
**Uppgiftsberoenden** I en WBS kan du skapa en företrädarrelation mellan uppgifter. När du tilldelar företrädaruppgifter till en uppgift, kan den uppgiften endast starta när alla dess företrädaruppgifter har slutförts. Planerat startdatum för uppgiften ställs automatiskt in på det senaste datumet för alla dess företrädare. 

**Aktiviteter för schemaläggning i Microsoft Dynamics 365 för operationer** följande faktorer avgör schemaläggningen av lägsta noden uppgifter:

-   Företrädare
-   Insats
-   Antal resurser
-   Start- och slutdatum

Startdatumet för en lövnoduppgift som inte har företrädare ställs automatiskt in på projektets startdatum. Tidslängden för en lövnoduppgift beräknas alltid som antalet arbetsdagar mellan dess start - och slutdatum. 

Schemaläggning av *** regler när automatisk tidsplanering-stöd är aktiverat gäller följande regler för schemaläggningen för lägsta noden uppgifter:

-   Start- och slutdatum för en uppgift måste vara arbetsdagar enligt projektets planeringskalender.
-   Startdatum för uppgiften ställs automatiskt in på det senaste slutdatumet för dess företrädare.
-   Insatsen för en uppgift beräknas automatiskt enligt följande:

Antal personer × varaktighet × antal timmar under en normal arbetsdag i projektkalendern. 

I vissa fall kanske du vill avvika från dessa regler. Du kan inaktivera automatisk tidsplanering om du vill förhindra Microsoft Dynamics 365 för åtgärder på automatiskt ange eller korrigera någon egenskap för lägsta noden uppgifter. När du anger information om en uppgift som bryter mot planeringsregler, visas en ikon för planeringsfel för uppgiften. Om du inte vill visa planeringsfel, klicka på **Planeringsfel visas** för att stänga av funktionen. 

> [!NOTE] 
> Värdena för en sammanfattning eller containern aktivitet även fortsättningsvis beräknas som summan av värdet av ingående uppgifter, oavsett om automatisk schemaläggning hjälp aktiveras eller inaktiveras. 

**Korrigera planeringsfel** När automatisk hjälp för tidsplanering är aktiverad är det osannolikt att planeringsfel inträffar. Om du vill stänga av automatisk hjälp för tidsplanering och sedan aktivera den på nytt, kan ikoner för tidsplaneringsfel visas i WBS. 

**Korrigera tidsplaneringsfel efter uppgift** När du dubbelklickar på ikonen för tidsplaneringsfel för en viss uppgift, visas en dialogruta med alla tidsplaneringsfel för den uppgiften. Du kan bestämma vilka tidsplaneringsfel som korrigeras för uppgiften. 

**Korrigera alla tidsplaneringsfel** Microsoft Dynamics 365 för operationer som att korrigera alla tidsplaneringsfel i Strukturen, i åtgärdsfönstret, klicka på **löser alla avvikelser schemaläggning**. 

> [!NOTE] 
> Den här funktionen kan orsaka betydande ändringar i Strukturen. Fel korrigeras i följande ordning:

1.  Den beräknade insatsen för alla uppgifter ändras så att den är lika med kapaciteten som definieras i projektkalendern.
2.  Startdatumet för varje uppgift ändras så att uppgiften startar när alla föregående uppgifter har slutförts.
3.  Startdatumet för varje uppgift ändras om du vill ta bort luckor i startdatumen för föregående uppgifter.

### <a name="cost-estimation"></a>Kostnadsuppskattning

Som nämndes tidigare i det här dokumentet, anger du den kostnadsuppskattningen för varje lövnoduppgift genom att använda fliken **Uppskattade kostnader och intäkter** i det nedre fönstret på sidan **Uppdelad arbetsstruktur**. 

> [!NOTE] 
> Du kan inte ändra kostnadsberäkningen för en sammanfattning eller containern aktivitet. Kostnadsuppskattningen för en sammanfattningsuppgift är lika med summan av kostnadsuppskattningen av dess lövnoduppgifter. Den beräknade totala kostnaden för varje uppgift beräknas som summan av uppskattat kostnadsbelopp för följande transaktionstyper:

-   Arbete
-   Artikel eller material
-   Utgifter

Transaktionstypen **Avgift** används för uppskattning avgiftsbaserade intäkter. Den här transaktionstypen har ingen kostnadskomponent och inkluderas därför inte när kostnader uppskattas. 

Transaktionstypen **A conto** används för att registrera det avtalade försäljningsvärdet i ett projekt av fast värdetyp. Den här transaktionstypen inkluderas inte heller när kostnader uppskattas. 

När du beräknar kostnader för material, arbete och utgifter för varje uppgift måste du tilldela en projektkategori till den uppskattade kostnaden. 

**Beräkning av arbetskostnader** För varje lövnoduppgift tilldelar du en arbetsinsats i timmar och en standardkategori. När du ställer in en tidsplan för en uppgift läggs därför arbetskostnadsuppskattningen för den uppgiften automatiskt till i standardkategorin för arbete. Den här kostnadsuppskattningen visas på fliken **Uppskattade kostnader och intäkter** i rutnätet **Radinformation** för den uppgiften. Om du behöver fler arbetskostnadsuppskattningar kan du lägga till dem på den här fliken. Om du ökar eller minskar timmarna i arbetskostnadsuppskattningen beräknas tidsplanen för uppgiften automatiskt om. 

**Uppskattning av kostnader och materialkostnader** På fliken **Uppskattade kostnader och intäkter** kan du också beräkna utgifter och materialkostnader för en uppgift om du kräver uppskattningar. 

Självkostnads- och försäljningspris för varje arbete eller kostnad uppskatta raden baseras på inställningarna som har definierats för varje kategori i tabellerna prissättning vid **projekthantering och redovisning**&gt;**inställningar**&gt;**prissättning**. Kostnad och försäljningspris för artiklar läggs till som standard från artikel- eller handelsavtal på listsidan **Frisläppta produkter** i Produktinformationshantering.

## <a name="tracking-progress-on-the-wbs"></a>Spårning av förlopp på WBS
Vissa branscher följer förloppet för ett projekt mot en WBS på en mycket grundläggande nivå, medan andra följer förloppet på en högre nivå i WBS. Det här avsnittet beskriver hur du kan använda WBS-spårning för dina projektkrav. 

Microsoft Dynamics 365 för operationer har tre vyer för Strukturen för ett projekt: den planering vyerna, insats spårning och visa Kostnadsuppföljning.

### <a name="planning-view"></a>Planeringsvy

Planeringsvy visar planerad eller baslinjeuppskattningen för tidsplan och kostnadsinformation. Även om det inte finns funktioner för spårning av version och baslinje för ett projekt-WBS, representerar värdena i den här vyn baslinjeversionen. Avsnitten Tidsplanuppskattningen och Kostnadsuppskattning i det här avsnittet beskriver den här vyn och hur den används för att skapa en WBS.

### <a name="effort-tracking-view"></a>Insatsspårningsvy

Insatsspårningsvy visar spårning av uppgiftsförloppet i WBS. Den jämför ackumulerade verkliga insatstimmar för en uppgift med planerade insatstimmar. Följande formler tillhandahåller värdena i insatsspårningsvyn:

-   Förlopp i procent = verklig insats till datum ÷ planerad insats för uppgiften
-   Återstående arbete (så kallade uppskattning-till-komplett \[ETC\]) = planerat arbete-Verkligt arbete hittills
-   Uppskattning vid slutförande (EAC) = återstående insats + faktisk insats till datum
-   Planerad insatsavvikelse = planerad insats – EAC

Insatsspårningsvyn visar en beräkning av insatsavvikelsen för uppgiften, baserad på om EAC är större eller mindre än den planerade insatsen:

-   Om EAC är större än den planerade insatsen, beräknas uppgiften att ta mer tid än planerat och ligger efter tidsplanen.
-   Om EAC är mindre än den planerade insatsen, beräknas uppgiften att ta mindre tid än planerat och ligger före tidsplanen.

**Projektledarens omberäkning av insats** Ibland ändrar projektledaren eller någon annan person som följer förloppet för ett projekt de ursprungliga uppskattningar för en uppgift. Uppgiften går av olika orsaker kanske snabbare eller långsammare än som ursprungligen förutsågs. Till exempel har omfånget minskats eller anställda har mindre erfarenhet än ursprungligen planerat. Beräkningar är projektledarens uppfattningar om uppskattningar baserade på aktuell status för ett projekt. Vanligtvis bör du inte ändra baslinjenumren, eftersom en projektbaslinje är ett välpublicerat dokument för uppskattning av projekts tidsplan och kostnad som alla projekts intressenter har godkänt. 

Det finns två sätt att projektledare kan ändra arbetsinsatsen för uppgifter:

-   Ändra den återstående insatsen som är inställd på automatiskt uppdatering av verkliga återstående insats för uppgiften.
-   Ändra förloppet i procent som är inställd på automatisk uppdatering av uppgiftens verkliga förlopp.

Båda sätten medför omberäkning av uppgiften ETC, EAC och förloppsprocentsatsen och den planerade insatsavvikelsen för uppgiften. EAC, ETC och förloppsprocentsatsen på sammanfattningsaktiviteter beräknas också om och deras planerade insatsavvikelse uppdateras. 

**Ändrad insats i sammanfattningsuppgifter** Du kan ändra insatsen i sammanfattnings- eller behållaruppgifter. Oavsett om du ändrar dessa värden genom att använda den återstående insatsen eller förloppsprocentsatsen på sammanfattningsuppgifterna, äger beräkningarna rum i följande ordning:

1.  EAC, ETC och förloppsprocentsatsen för uppgiften beräknas.
2.  Den nya EAC fördelas till de underordnade uppgifterna i samma proportion som det ursprungliga EAC-beloppet.
3.  Den nya EAC på varje lövnoduppgift beräknas.
4.  Återstående insats och framstegprocentsats beräknas om för alla berörda underordnade uppgifter, baserat på det nya EAC-värdet. Insatsavvikelsen av uppgifterna räknas också om.
5.  EAC av sammanfattningsuppgifterna beräknas också om från lövnoderna.

Klicka på **Utöka till nivå** i insatsspårningsvyn för att ange nivån för spårning och underhåll av din WBS. WBS utvidgas automatiskt till den nivån i insatsspårningsvyn när du öppnar den.

### <a name="cost-tracking-view"></a>Kostnadsspårningsvy

Kostnadsspårningsvyn visar spårning av kostnadsförbrukning för en uppgift. I den här vyn jämförs den faktiska utbetalade kostnaden för en uppgift till dagens datum mot planerad kostnad för uppgiften. Följande formler tillhandahåller värdena i kostnadsspårningsvyn:

-   Procentandel av förbrukad kostnad = faktiskt kostnad till datum ÷ planerad kostnad för uppgiften
-   Kostnad för slutförande (CTC) = planerad kostnad – faktisk kostnad till datum
-   Uppskattning vid slutförande (EAC) = CTC + faktisk kostnad till datum
-   Planerad kostnadsavvikelse = planerad kostnad – EAC

Kostnadsspårningsvyn visar en beräkning av kostnadsavvikelsen för uppgiften, baserad på om EAC är större eller mindre än den planerade kostnaden:

-   Om EAC är större än den planerade kostnaden, beräknas uppgiften kosta mer pengar än planerat och ligger över budget.
-   Om EAC är mindre än den planerade kostnaden, beräknas uppgiften kosta mindre pengar än planerat och ligger under budget.

**Projektledarens omberäkning av insats** Projektledare måste använda CTC för att ändra ursprunglig kostnadsuppskattning för en uppgift. Projektledaren kan ändra CTC-värdet till kostnaden som krävs för att slutföra uppgiften. Om du ändrar CTC-värdet beräknas uppgiftens CTC, EAC och procentandel av förbrukad kostnad och planerad kostnadsavvikelse för en uppgift om. EAC, ETC och procentandel av förbrukad kostnad på sammanfattningsuppgifterna beräknas också om och deras planerade kostnadsavvikelse uppdateras. 

> [!NOTE] 
> När du ändrar arbete för en aktivitet struktur i kraft spårning visas aktivitetens CTC, UK, förbrukas av procent av kostnaden och planerade kostnadsavvikelsen beräknas i Kostnadsuppföljning vy. Kostnadsändringar påverkar emellertid inte värdena i insatsspårningsvyn, eftersom kostnaden per transaktionstyp (arbete, material eller utgift) eller projektkategori inte ändras. 

**Projektionsrevidering för kostnader i sammanfattningsuppgifter** Du kan ändra kostnader för sammanfattningsuppgifter och beräkningarna sker automatiskt i följande ordning:

1.  EAC, CTC och procentsatsen av förbrukad kostnad för uppgiften beräknas på nytt.
2.  Den nya EAC fördelas till de underordnade uppgifterna i samma proportion som uppgifternas ursprungliga EAC-belopp.
3.  Den nya EAC för varje uppgift beräknas.
4.  CTS och procentsatsen för förbrukad kostnad beräknas på nytt för berörda underordnade uppgifter, baserat på EAC-värdet. Kostnadsavvikelsen för uppgifterna beräknas också på nytt.
5.  EAC för alla sammanfattningsuppgifter räknas om enligt denna ändring.

Klicka på **Utöka till nivå** i kostnadsspårningsvyn för att ange nivån för spårning och underhåll av din WBS. WBS utvidgas automatiskt till den nivån i kostnadsspårningsvyn när du öppnar den.

### <a name="earned-value-management"></a>Hantering av intjänat värde

Du kan använda metod för upparbetat värde (EVM) för att spåra förloppet för ett projekt. Du kan visa värden för upparbetat värde i projektledarens rollcenter. Diagramkomponenten för upparbetat värde visar tidfasade värdena för planerat värde och faktisk kostnad. Upparbetat värde för aktuellt datum visas som en punkt. Tidfasade data för upparbetat värde är för närvarande är inte tillgängliga. 

Tidfasen på diagrammet för upparbetat värde visas per vecka eller per månad. Det här avsnittet beskriver de tre pelarna i EVM: planerat värde, tjänat värde och faktisk kostnad. 

**Planerat värde** EVM-teorin anger att det planerade värdets rityta representerar takten med vilken projektteamet planerade att upparbeta värde i projektet. 

Microsoft Dynamics 365 för operationer används 0:100 med regeln när som ritar planerade värdet. Med den här regeln bokförs artiklarnas värde i uppgiften till uppgiften vid slutdatumet. Inget värde bokförs förrän uppgiften är avslutad till 100 procent. 

I Projekthantering och redovisning anger du lövnodernas slutdatum och den planerade kostnaden för det. När diagrammet för planerat värde visas per vecka, sammanfattas planerat värde per vecka för alla lövnoduppgifter för projektets varaktighet. 

**Upparbetat värde** EVM-teorin anger att det upparbetade värdets rityta representerar takten med vilken projektteamet verkligen upparbetar värde i projektet. 

Microsoft Dynamics 365 för operationer används 0:100 med regeln när dess områden upparbetat värde. Med den här regeln bokförs artiklarnas värde i uppgiften till uppgiften vid slutdatumet. Inget värde bokförs förrän uppgiften är avslutad till 100 procent. 

När upparbetat värde beräknas inkluderas förloppets procentsatsen för varje uppgift. Med 0:100-regeln inkluderas endast uppgifter som utförs under en given period för beräkning av upparbetat värde vid slutet av perioden. Upparbetat värde i projektet beräknas för alla uppgifter som är klara när diagrammet skapas. 

> [!NOTE] 
> Ett system för spårning av struktur inte för närvarande datastrukturer för att lagra historiska utvecklingen procentsatser för varje aktivitet. Därför kan upparbetat värde endast rapporteras vid tidpunkten när kuben bearbetas. Bearbeta kuben regelbundet för att uppdatera data för upparbetat värde som visas i rollcenter. 

**Faktisk kostnad** EVM-teorin anger att den faktiska kostnaden representerar takten med vilken pengar spenderas i projektet. 

Transaktioner som bokförs till ett projekt används för att rita den faktiska kostnadsraden. Kostnaderna summeras efter datum. Dessa data används sedan för att visa de faktiska kostnaderna per vecka eller månad på diagrammet upparbetat värde.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Använda begreppen i planerat värde, upparbetat värde och faktisk kostnad

**Tidsplansavvikelse** Vid planering skapar du en prognos för arbete på en tidslinje. Därför är planerat värde takten med vilken projektplanerarna ansåg att arbetet i projektet slutförs. När ett projekt pågår, slutförs arbete och projektet upparbetar värde. Genom att jämföra planerat värde med upparbetat värde kan du visa hur arbetet på ett projekt fortskrider. Resultatet av jämförelsen kallas den här tidsplansavvikelse. 

Om det planerade värdet för en period är högre än upparbetat värde är mängden arbete som har utförts på ett projekt mindre än det planerade. Därför ligger projektet efter tidsplanen. Eftersom planerat värde och upparbetat värde uttrycks i monetära termer ges förseningen i projektet också ett penningvärde. 

Om det planerade värdet för en period är minde än upparbetat värde är mängden arbete som har utförts på ett projekt mer än det planerade. Därför ligger projektet före tidsplanen. Den här ledtiden ges också ett penningvärde.

**Kostnadsavvikelse** Eftersom upparbetat värde använder självkostnad som multiplikator anger upparbetat värde kostnaden för arbete som utförs i ett projekt. När ett projekt fortskrider innehåller transaktionsloggen en förteckning över pengar som verkligen har använts för projektet. Genom att jämföra upparbetat värde med faktisk kostnad kan du visa beloppet som har använts kontra värdet som har upparbetats. Resultatet av jämförelsen kallas kostnadsavvikelse. 

Om den faktiska kostnaden som använts för en period är större än det upparbetade värdet, har mer pengar spenderats än tjänats. Därför ligger projektet över budget. 

Om den faktiska kostnaden som används för en period är mindre än det upparbetade värdet, har mer pengar tjänats än spenderats. Därför ligger projektet under budget.

## <a name="wbs-templates"></a>WBS-mallar
Du kan använda funktionen struktur mallar för att skapa standardmallar för projekt. Om projekt som ditt företag erbjuder gäller mycket upprepat arbete bör du överväga att skapa en WBS-mall. 

Du kan skapa en WBS-mall från WBS för ett befintligt projekt så att kunskaper och bästa praxis som samlades under planeringen av projektet kan återanvändas på liknande projekt i framtiden. Ibland är det ingen mening att spara hela WBS som en mall. Därför kan du även skapa mallar från delar av en WBS för ett projekt.

### <a name="saving-a-projects-wbs-as-a-template"></a>Spara ett projekt-WBS som en mall

När du skapar en mall kan du importera den till ett nytt projekt-WBS under rotnoden eller under valfri uppgift i projektets WBS.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importera en WBS-mall till ett projekt-WBS

När du importerar uppgifter är uppgifterna i mallen ordnade baserat på startdatum för uppgiften som de importeras under. Vid import används företrädarrelationer på malluppgifterna för att beräkna startdatum för de importerade uppgifterna. Målprojektets standardarbetskalender används för att beräkna slutdatumen för de importerade uppgifterna, så att arbetsdagar och standardarbetstid som definieras i det aktuella projektets arbetskalendern behålls. 

Kostnadsbelopp och försäljningspriser på uppskattningsraderna används för att garantera att priser som är specifika för projektet eller projektkontraktet har giltighetsdatum.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Skillnader mellan ett projekt-WBS och en WBS-mall

-   Uppgifter i WBS-mallar har inte start- och slutdatum.

Arbetsdagar och helgdagar anges inte för WBS-mallar.

-   WBS-mallar använder alltid planeringskalendern som har ställts in som standardkalender för alla projekt.

Standardplaneringskalendern används bara för att få timmarna i en standardarbetsdag.

-   Företrädarrelationer kopieras inte till en WBS-mall.

Eftersom WBS-mallar inte har datum krävs inte logiken för startdatum som baseras på en företrädarrelations slutdatum.

-   En rad för arbetskostnadsuppskattning skapas automatiskt när en uppgift skapas i en WBS-mall. Försäljningspriset och kostnadsbeloppet kopieras från den valda arbetaren.

Utgifter och artikelkostnader kan skapas manuellt på samma sätt som på ett projekt-WBS.

-   Tidsplaneringsfel visas om det förekommer avvikelser från följande formel:

Insats = Antal resurser * Varaktighet * Antalet timmar under en vanlig arbetsdag 

Du kan korrigera alla tidsplanerings samtidigt genom att klicka på **Fix all scheduling errors**. 

Du kan också korrigera tidsplaneringsfel enskilt genom att klicka på varningsikonen för varje uppgift.

