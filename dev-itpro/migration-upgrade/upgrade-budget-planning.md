---
title: Uppgradera budgetplanering
description: "Det finns viktiga skillnader i budgetplanering mellan Microsoft Dynamics AX 2012 och Microsoft Dynamics 365 for Operations. Vissa funktioner har inte uppgraderats och kräver därför omkonfigurering. Det här avsnittet beskriver vad som måste konfigureras om och beskriver även nya funktioner som du bör överväga när uppgraderingen är klar."
author: twheeloc
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fafa323c3949c09707c81ec41edae25ad2677eeb
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="upgrade-budget-planning"></a>Uppgradera budgetplanering

[!include[banner](../includes/banner.md)]


Det finns viktiga skillnader i budgetplanering mellan Microsoft Dynamics AX 2012 och Microsoft Dynamics 365 for Operations. Vissa funktioner har inte uppgraderats och kräver därför omkonfigurering. Det här avsnittet beskriver vad som måste konfigureras om och beskriver även nya funktioner som du bör överväga när uppgraderingen är klar.  

Budgetplanering i Microsoft Dynamics 365 for Operations har många förbättringar som inte var tillgängliga i Microsoft Dynamics AX 2012. Det här avsnittet beskriver de ändringar som kunder som uppgraderar måste göra. Den pekar även ut de nya funktionerna som ska beaktas under uppgraderingsprocessen. På grund av omfattningen av förändringarna kommer eventuella befintliga budgetplaner inte at kunna öppnas förrän du har gjort ändringarna som beskrivs i det här avsnittet. Rapporterna bör emellertid fortsätta att fungera och kräver inte ytterligare ändringar.

## <a name="overview-of-changes"></a>Översikt över ändringar
Många viktiga förändringar har gjorts i budgetering för Dynamics 365 for Operations. Dessa ändringar är avsedda att göra budgetplaneringen enklare att konfigurera och mer återanvändningsbar för att minska årligt underhåll och inställningar. Följande områden i AX 2012 finns inte längre i Dynamics 365 for Operations:

-   Budgetplansmallar (budgetplaneringskonfiguration)
-   Budgetplansmappar (budgetplaneringskonfiguration)
-   Scenariobegränsningar (budgetplaneringskonfiguration)
-   Mallar för Budgetplaneringsfasregler och mallar (budgetplaneringsprocess)
-   Matrisfält för kalkylbladsmallar
-   Mallguide för budgetplan i Microsoft Office

Vissa nya koncept kan inte direkt uppgraderas från den tidigare funktionen. Därför måste du utföra viss omkonfiguration för att hantera dessa nya koncept. I följande avsnitt beskrivs de koncept som har ersatt objekten i föregående lista.

### <a name="columns"></a>Kolumner

Kolumnerna är nya koncept som ersätter delar av Excel-mallen och även matrisfält. Kolumnerna kan representera en period, månad, kvartal, år eller all tid. Tidsreferensen är dynamisk. Den pekar på en relativ eller år med hänvisning till budgetprocessen. Till exempel kolumnen **Föregående år januari** hänvisar till räkenskapsperiod 1 för år -1. En kolumn som är specifik för budgetplanscenariot som till exempel utfall- eller budgetförfrågan.

### <a name="layouts"></a>Layouter

Layouter är ett nytt koncept som ersätter Excel-mallen. Layouterna innehåller kolumner som definierar vilka budget- eller utfallsdata och perioder som ska visas. Layouter delas även mellan klienten och Excel-tillägget. Användargränssnittet när du registrerar eller granskar data i Dynamics 365 for Operations-klienten är därför bättre än användarupplevelsen i AX 2012. Om du vill ange data i Dynamics 365 for Operations-klienten är du inte längre begränsad till att visa och ange ett enda scenario i transaktionsvyn. I stället kan du med en jämförelsevy enkelt visa och ange belopp för flera perioder och konton samtidigt. Layouter kan också definieras så att du kan ange och visa valuta, kommentarer och andra valfria data. Layouter låter dig ange vilka redovisningsdimensioner och dimensionsbeskrivningar som ska visas. Layouter inkludera också scenariobegränsningar som definierar vilka kolumner i en mall som kan redigeras och vilka kolumner som ska vara tillgängliga i Excel. När du har definierat en layout skapas en mall för den. Den här mallen skapar i sin tur motsvarande Excel-mall. Du kan redigera Excel-mallen om du vill lägga in fler formler och formatering och överför sedan bilden igen. Layouter tilldelas sedan varje fasregel på sidan **Budgetplaneringsprocess**. Därför ersätter layouterna mallar, som tilldelats och som används på liknande sätt.

### <a name="budget-planning-processes"></a>Budgetplaneringsprocesser

Budgetplaneringsprocesser är oftast detsamma som i AX 2012. Den största ändringen är ersättningen av mallar med layouter. Om alla processer har slutförts i AX 2012 uppdateras tidigare processer till statusen Pågående så att ändringar kan göras. Du måste tilldela layouter för varje fasregel för att bestämma vilka tidsperioder och scenarier som visas när planen har öppnats i klienten. Layouterna bestämmer också vilken Excel-mall som öppnas utanför Dynamic 365 for Operations så att du kan visa budgeten. **Standardkontostruktur** är ett nytt obligatoriskt fält för budgetplaneringsprocessen. För varje budgetplaneringsprocess, tilldela den primära kontostrukturen som ska användas för budgetering.

### <a name="attachments"></a>Bilagor

Handlingar har sparats till en bilagemapp i AX 2012. Inga tidigare handlingar uppgraderas. Motiveringsdokument lagras nu i databasen. Om denna information ska sparas i den uppgraderade versionen kan du överföra motiveringsdokument för varje plan som en bifogad fil med hjälp av knappen **justering** i åtgärdsfönstret. I AX 2012 skapades Excel-kalkylblad för varje budgetplan utifrån mallen. I Dynamics 365 for Operations öppnar alla planer en kopia av layouten. Inga ändringar i Excel-filen sparas dock. Eventuella formler eller stöd information som användes per plan måste läggas till via kommentarer, ett motiveringsdokumentet eller någon annan kompletterande process.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Konfigurera en uppgraderad miljö från AX 2012
För att hjälpa dig att avgöra hur du konfigurerar det uppgraderade systemet, har följande exempel en uppgraderad budgetprocess från AX 2012 demodata. Standardkonfigurationsdata för kolumner har skapats för att hjälpa uppgraderingsprocessen. Du kan uppdatera eller ta bort den här standarddatan om den inte uppfyller dina behov av konfigurering. **Obs!** Det finns nya obligatoriska fält som inte anges i systemet. Om du fastnar på en sida som t.ex. sidan **Budgetplaneringskonfiguration** och kan inte navigera iväg. Du kan stänga webbläsaren och öppna den på nytt till en annan sida för att ange information i rätt ordning. Det finns obligatoriska fält som inte ännu är angivna. Därför kan problem uppstå tills allt är konfigurerat och alla obligatoriska fält har angetts. Det här avsnittet beskriver hur du ställer in dessa fält efter behov. Här följer några exempel på krävda fält:

-   Sidan **Budgetplaneringsprocess**: fältet **standardkontostruktur**
-   Sida **Budgetplaneringsprocessen**: fältet **Layout** på snabbfliken **Regler och layouter för budgetplaneringsfaser**

### <a name="define-columns-and-layouts"></a>Definiera kolumner och layout

1.  På sidan **budgetplaneringskonfiguration** klickar du på fliken **kolumner**. Under uppgraderingen skapas automatiskt nya kolumner utifrån dina budgetplansrader. Kolumner använder nu dynamiska datum där tiden och året förskjuts från räkenskapsåret som definieras i budgetplaneringsprocessen. **Obs:** Av prestandaskäl under uppgraderingen förutsätts att alla budgetcykler representerar kalenderår, inte räkenskapsår. Om du använder räkenskapsår måste du utföra ändringar för att mappa kolumnerna till deras räkenskapsår. Exempelvis följande element fanns i AX 2012:
    -   Budgetplanscenarier: verkliga, baslinje, Budgetförfrågan, budget godkänd
    -   Budgetplansrader för alla scenarier i 2017 och utfall för både 2017 och 2016

    Följande kolumner skapas Dynamics 365 for Operations:
    | Kolumnnamn    | Budgetplanscenario | Kolumntidsperiod | Förskjutning för år |
    |----------------|----------------------|--------------------|-------------|
    | Jan Scenario 1 | Utfall              | 1                  | 0           |
    | Jan Scenario 2 | Baslinje             | 1                  | 0           |
    | Jan Scenario 3 | Budgetförfrågan       | 1                  | 0           |
    | Jan Scenario 4 | budget godkänd      | 1                  | 0           |
    | Jan Scenario 5 | Utfall              | 1                  | -1          |
    | Feb Scenario 1 | Utfall              | 1                  | 0           |
    | ...            | ...                  | ...                | ...         |

    I det här exemplet skapas en kolumn som heter **Jan Scenario 1** för den senaste transaktionsdatan för budgetplan som finns där det finns transaktioner i januari. En liknande kolumn skapas för varje scenario som innehåller data. Kolumnerna skapas för alla perioder det året, kolumner skapas för tidigare år.
2.  Ändra kolumnnamn och beskrivningar och övriga detaljer, antingen manuellt på klienten eller genom att göra bulkuppdateringar via Excel-tillägget som refererar till budgetplankolumnernas dataentitet. Alla filter som har tidigare angetts för matrisfält anges nu inne i kolumnerna.
3.  Skapa en ny budgetplanlayout. En layout pekar på flera kolumner för att definiera vyn som visas i Excel och klienten. Layouten kräver först att du anger en redovisningsdimension som är konfigurerad för att avgöra vilka ekonomiska dimensioner som kan anges. När du har nagett dimensionsuppsättningen klickar du på **beskrivningar** för att välja vilka dimensionsbeskrivningar som ska ingå i layouten.
4.  På snabbfliken **layoutelement** klickar du på **Lägg till** för att lägga till metadata för varje rad som en valuta, en kommentar eller en budgetklass som bestämmer intäktsrader jämfört med utgiftsrader. Lägg sedan till kolumner för tidsperioden och scenarier som gäller för den här budgetcykeln och fasen. Du kan göra dessa ändringar manuellt i klienten eller via Excel-tillägget som refererar till dataentiteten för layoutelement för budgetplan.
5.  För varje layoutelement anger du om kolumnen ska kunna redigeras och om kolumnen även visas i Excel-arbetsboken för den här layouten. **Obs!** För våra historiska planer kanske du vill ha en layout som visar 12 månatliga kolumner för alla budgetplanscenarier för den processen.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Uppdatera budgetplaneringsprocesser för att använda passande layout för varje budgetfas

1.  På sidan **Budgetplaneringsprocess** väljer du hur du vill konfigurera.
2.  Klicka på **Redigera** i åtgärdsfönstret.
3.  Ange standardkontostrukturen för denna budgetprocess. **Standardkontostruktur** är ett nytt obligatoriskt fält som måste anges.
4.  På snabbfliken **Regler och layouter för budgetplaneringsfaser** på fältet **Layout** väljer du en layout som tidigare har konfigurerats och som är avsett för den här fasen.
5.  Fortsätt att välja samma eller olika layouter för olika budgetplaneringsfaser och spara ändringarna.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>Ytterligare egenskaper att tänka på i din budgeteringsprocess
### <a name="budget-planning-workspace"></a>Budgetplaneringsarbetsflöde

Den här arbetsytan har utformats för både budgetägaren och enskilda bidragare till budget. Det finns länkar till de budgetdokument som kräver din uppmärksamhet. Det finns också rapporter och prestationsindikatorer (KPI:er) för budgetprocessen. Budgetadministratör kan definiera den aktuella budgetplaneringsprocessen för alla användare på sidan **budgeteringsparametrar**. På fliken **Inställningar för arbetsyta** innehåller snabbfliken **budgetplanering** ett fält där du kan välja budgetplaneringsprocessen.

### <a name="alternate-layouts"></a>Alternativa layouter

Alternativa layouter är en ny funktion som gör att du kan visa planer i olika layouter. En eller flera layouter kan anges som alternativ. Du kan visa en budgetplan i en månatlig layout eller kvartalsvis layout. Du definierar alternativa layouter på snabbfliken **Regler och layouter för budgetplaneringsfaser** på sidan **Budgetplaneringsprocess**.

### <a name="budget-milestones"></a>Budgetmilstolpar

Som ett led i budgetprocessen är det viktigt att du förstår viktiga datum och deadlines. Du kan nu konfigurera datum så att de har beskrivningar. Budgeterande användare kommer att se dessa beskrivningar när de öppnar budgetar för att redigera eller visa allt som har tilldelats.

### <a name="copy-from-budget-plan-allocation"></a>Kopia från allokering av budgetplan

En ny allokeringsmetod låter dig distribuera från en överordnad plan till en underordnad plan utan att gå via en mellanliggande nivå i hierarkin. Denna metod är särskilt användbar för kunder som tidigare skapade ekonomisk dimension för budgetfördelning och godkännanden.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Generera budgetplaner från nya budgetkällor

Följande alternativ har lagts till som en periodisk bearbetning. Dessa alternativ låter dig skapa en budgetplan med befintliga data från en annan modul som startpunkt:

-   Generera budgetplan från efterfrågeprognos
-   Generera budgetplan från leveransprognos
-   Generera budgetplan från projekt
-   Generera budgetplan från budgetregister

### <a name="more-complete-tracking-of-amounts"></a>Fullständig spårning av belopp

Budgetplanering hade ett enstaka planeringsbelopp, eller lagrades för varje värde i AX 2012. I Dynamics 365 for Operations, har datamodellen expanderats. Det finns nu redovisningsvaluta, transaktionsvaluta och rapporteringsvalutabelopp för varje värde. Under uppgraderingen fylls dessa nya kolumner i automatiskt för befintliga data.

### <a name="do-not-convert-currency-in-aggregation"></a>Konvertera inte valuta i sammansättning

Vanligtvis när en underordnad plan läggs till en överordnad nivå konverteras beloppen automatiskt från transaktionsvalutan till redovisningsvalutan för organisationen. När du anger alternativet **konvertera inte valutan i sammansättning** till **Nej** förblir de sammanlagda beloppen i transaktionens ursprungliga valuta. Detta alternativ tillåter därför mer exakta justeringar som påverkas av valutakursen.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Få en återblick från en budgetplan till andra moduler som bidrar till budgeten

Budgetplaner kan genereras från efterfrågan eller ange prognoser, projekt och andra områden. Budgetplaner genom dimension innehåller flera alternativ som gör att du kan köra en fråga som hjälper dig att identifiera den data som var källan till budgetplanen.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Skriva över eller bifoga till planen för allokeringsscheman

Om det finns flera källor till belopp som måste fördelas, kan du ange beloppen ska vara additiva. I det här fallet skriver inte beloppen över eventuella befintliga belopp. I stället läggs de till befintliga belopp.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Ekonomiska standarddimensionsuppsättning för budgetplaneringskonfiguration

Sidan **budgetplaneringskonfiguration** innehåller nu ett fält där du kan ange standard för ekonomiska dimensionsuppsättningen. Även om det här fältet är ett valfritt fält, kanske det krävs för vissa förfrågningar. Det kan också krävas om du vill gruppera eller filtrera rapportgruppering genom dimensionsuppsättning.

### <a name="data-entities"></a>Datatabeller

Flera datatabeller har lagts till för att aktivera snabb implementering av budgetplanering. Enheterna låter dig även göra många ändringar via Excel. Därför måste du inte skapa ett objekt i taget till klienten. Här följer en lista över nya datatabeller:

-   Enhetsnamn
-   Budgetparametrar
-   Budgetplanparametrar
-   Budgetplanscenarier
-   Faser för budgetplan
-   Arbetsflödesfas för budgetplan
-   Allokeringsscheman för budgetplan
-   Allokeringar för budgetplanfas
-   Budgetplansprioriteter
-   Budgetplanskolumner
-   Layoutelement för budgetplan





