---
title: "Konfiguration av lagerställe"
description: "Det här avsnittet innehåller information om hur du konfigurerar ett lagerställe. Det inkluderar information om att aktivera ett lagerställes layout och lagerställeprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-10-30 12 - 52 - 43
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 437f2348603db432df6d7589e4043d8145c52a1e
ms.lasthandoff: 03/30/2017


---

# <a name="warehouse-configuration"></a>Konfiguration av lagerställe

Det här avsnittet innehåller information om hur du konfigurerar ett lagerställe. Det inkluderar information om att aktivera ett lagerställes layout och lagerställeprocesser.

**Anm.:** Den här artikeln gäller funktioner i modulen** Lagerstyrning** (avancerad lagerstyrning). Den gäller inte lagerställefunktioner i modulen** Lagerhantering**.

## <a name="warehouse-layout"></a>Layout för lagerställe
Lagerhanteringssystemet i Microsoft Dynamics 365 for Operations ger flexibla sätt att definiera lagerställets layout för att uppfylla föränderliga behov, så att du kan uppnå en optimal lagereffektivitet.

-   Du kan fastställa högprioriterade och lågprioriterade lagerområden för optimal placering av varor.
-   Du kan dela upp till lagerstället i zoner som tar hänsyn till olika lagringsbehov, till exempel temperaturkrav eller olika omsättningshastigheter för artiklar.
-   Du kan ange lagerplatser på valfri nivå (till exempel positionerna plats, lagerställe, gång, ställningen, hylla och binge).
-   Du kan gruppera platser genom att använda inställningar för begränsning för fysisk lagring.
-   Du kan kontrollera hur artiklar lagras och plockas, baserat på frågedefinierade regler.

Om du vill använda lagerstyrning i Microsoft Dynamics 365 for Operations måste du skapa ett lagerställe och aktivera funktionen för mer avancerade eller specialiserade lagerhanteringsaktiviteter. Välj alternativet **Använd lagerstyrningsprocesser** på sidan **Lagerställen**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Zongrupper, zoner, platstyper och platser

Som en del av processen för att aktivera en lagerställelayout måste du definiera lagerställezongrupper och zoner, platsprofiler, platstyper och platser.

-   **Zongrupper** – En logisk eller fysisk gruppering av zoner i ett lagerställe.
-   **Zoner** – En logisk eller fysisk gruppering av platser i ett lagerställe.
-   **Zongrupper** – En logisk eller fysisk gruppering av platser som har samma principer för lagerplatsprocessen (exempelvis en blandning av olika artikelnummer kan lagras där och samma begränsningar för fysisk lagring gäller).
-   **Platstyper** – En logisk eller fysisk gruppering av lagerplatser. Du kan till exempel skapa en platstyp för alla byggnadsställningsplatser. Obligatoriska inställningar på sidan **Parametrar för lagerstyrning** kör processen att definiera mellanlagringsplatstyper och den slutgiltiga leveransplatstypen.
-   **Platser** – Den lägsta nivån i platsinformationen. Platser används för att spåra var lagerbehållningen lagras och plockas på ett lagerställe.

Enheterna som du skapar för att definiera din lagerställelayout som används i frågorna som du angav i arbetsmallar för att köra arbetsordrar på lagerstället. När du definierar zonerna, platstyperna och så vidare, beakta därför hur andra områden på lagerstället används för olika processer. Beakta även faktorer såsom de fysiska egenskaperna för ett visst område. Det kan exempelvis vara områden där du kan använda endast en viss typ av gaffeltrucken. Eller, om företaget har produktions- och färdiga varor inom samma anläggning, kanske du vill skapa ett enda lagerställe i Dynamics 365 för operationer men sedan lämna de här två uppgifterna genom att skapa två grupper av zonen. Ge entiteter beskrivande namn så att det är lätt att känna igen när du använder dem i mallen frågor.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Lagringsbegränsningsplatser, platsprofiler och fasta plockplatser

Du måste ta hänsyn till den fysiska utformningen av lagerstället, både för att bestämma lagringskapaciteter (lagringsbegränsningsplatser och platsprofiler) och som en del av företagets försök att uppnå optimala lagerställeprocesser. 

Platsen lagring gränser att garantera att arbetet inte skapas för att begära att lager placeras på en plats som inte har den fysiska kapaciteten för lagret. Till exempel om vissa platser inom ett lagerställe kan innehålla endast en lastpall per plats, kan plats lagring gränser aktiveras. Den ** kvantitet ** värdet kan anges till **1**, och ** enhet ** värdet kan anges till **PL** inom en viss plats profil grupperingen. 

Om mer avancerade beräkningar krävs för att kontrollera platskapacitetsbegränsningarna kan platsprofilinställningarna användas. I det här fallet beaktas vikt och volym när kapacitetsberäkningarna utförs. 

Om du vill uppnå optimala utgående processer ska du utvärdera om du vill använda fasta plockplatser och/eller packplatser. Ofta används minimal/maximal lagerpåfyllnad för lagerpåfyllnadsprocesser från ett bulkområde till de fasta plockplatserna och flera fasta plockplatser kan aktiveras inom samma lagerställe och för produktvarianter. Beakta flexibiliteten som du kan uppnå genom att aktivera dedikerade spillplatser för lagerpåfyllnadsefterfrågan, som endast används för våg-/lastlagerpåfyllnadsprocesser.

### <a name="location-setup-wizard"></a>Guide för platsinställning

Du kan använda för att snabbt skapa platser i lagret, den ** platsinställningar ** guiden. Som en del av den här processen kan du enkelt hantera formatet för platsnamnen.

## <a name="warehouse-processes"></a>Lagerställeprocesser
Som en del av konfigurationen för lagerstället är det viktigt att du aktiverar lagerställeprocesser enligt affärskraven. De viktigaste komponenterna som du måste konfigurera är vågmallar, arbetsmallar, arbetspooler och platsdirektiv.

### <a name="wave-templates"></a>Påfyllnadsmallar

Vågmallar gör det enklare att aktivera den utgående processen Släpp till lagerställe. Så snart orderrader släpps (antingen direkt från källdokument, med buntjobbprocesser eller med laster som redan har skapats) används vågmallfunktionen. 

Du kan skapa tre typer av wave-mallar: **leverans**, **tillverkningsordern**, och **Kanban**. Parametrarna används för att definiera hur långt systemet automatiskt ska börja vid arbete för utgående bearbetning. En vågmall är väljs utifrån vågmallsekvensen och kriterier som anges i mallen. Om en mall anges överst i sekvensen kontrolleras villkoren i mallen först. Om villkoren uppfylls bearbetas vågmallen. Annars kontrolleras villkoren i nästa mall osv. Därför är det en bra idé att placera mallen med det mest specifika villkoret längst upp i listan med vågmallsekvensen så att den bearbetas först. Du vill kanske bearbeta allt arbete för ett specifikt transportföretag idag och tillfälligt försena bearbetning av arbetet för andra transportföretag. I det här fallet ska vågmallen som väljer arbete för transportföretaget anges högre i sekvensen än annan mallar. Annars kan arbetet för andra transportföretag bearbetas innan arbetet för det transportföretaget har slutförts. 

Du måste ange vågprocessmetoderna i varje vågmall. Metoderna som är tillgängliga varierar beroende på vågmalltypen.

### <a name="work-templates"></a>Arbetsmallar

Arbetsmalldefinitioner spelar en viktig roll i definitionen av arbetsprocesser för lagerhantering. De definierar vilket arbete som utförs och hur det utförs. Mallar kan också innehålla en vägledande kod som länkar till ett platsdirektiv för att definiera var arbete utförs. Arbetsmallar innehåller en fråga som anger villkoren för arbetet. Varje mall måste innefatta minst en plockoperation och en placeringsoperation för att köra den grundläggande arbetsoperationen för överföring av lagerbehållning från en plats till en annan. 

Om flera anställda måste kunna utföra arbete för vissa av dina lageroperationer, vill du kanske använda begreppet *mellanlagring* för lagerstället och dela utförande av arbetet till olika arbetsklasser.

### <a name="work-pools"></a>Arbetspooler

Arbetspooler används för att ordna arbete i grupper. Du kan till exempel skapa en arbetspool för att klassificera arbete som uppstår på ett visst lagerställe. För alla arbetstyper utom inventering kan du tilldela en arbetspool till en arbetsmall. För rullande inventering kan du tilldela en arbetspool på följande sidor:

-   Planer för rullande inventering
-   Trösklar för rullande inventering
-   Rullande inventeringsarbete efter plats
-   Rullande inventeringsarbete efter artikel

När du använder arbetsmallar för att skapa arbete kommer arbetspoolen tilldelas automatiskt till arbetet. 

ID för arbetspool kan också användas för att begränsa vilken typ av arbete som skickas till en viss lagerarbetare, förutsatt den här funktionen konfigureras på den relevanta mobilenhetens menyobjekt.

### <a name="location-directives"></a>Platsdirektiv

Som namnet antyder används platsdirektiv för att vidarebefordra arbetstransaktionerna till lämpliga platser på lagerstället. Med andra ord definierar de platserna plocka och lägga. 

Gör det enklare och snabbare att definiera åtgärder som är knutna till varje platsdirektivrad genom att använda en av de fördefinierade strategierna. Du kan till exempel använda strategin **Tom plats utan inkommande arbetsuppgifter** om du vill söka efter lediga platser på ett lagerställe eller använda strategin **FEFO-batchreservation** för plockning av utgående försäljning.

<a name="see-also"></a>Se även
--------

[Konfigurera platser i WMS-aktiverade lagerställe (aktivitet guide)](https://ax.help.dynamics.com/en/wiki/configure-locations-in-a-wms-enabled-warehousing/)


