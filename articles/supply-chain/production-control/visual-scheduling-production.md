---
title: Gantt-diagram för jobbplanering
description: Produktionsplanerare kan styra och optimera produktionsplanerna genom att använda Gantt-scheman.
author: johanhoffmann
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage, GanttColorTable, GanttReqExplosionColor, GanttReqExplosionSetup, GanttTable, GanttTimescaleSetup, GanttWrkCtr, GanttWrkCtrColor, GanttWrkCtrJobInfo, GanttWrkCtrLoadResources, GanttWrkCtrMoveJob, GanttWrkCtrSetup, GanttWrkCtrView
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99a7955178ae97e5b696fce04c665d9a251c4a0e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215875"
---
# <a name="gantt-chart-for-job-scheduling"></a>Gantt-diagram för jobbplanering

[!include [banner](../includes/banner.md)]

Gantt-diagrammet har utformats för att tillåta produktionsplanerare att kontrollera och optimera produktionsplanen. Gantt-diagrammet gör arbetsflödet transparent och gör det enkelt att justera produktionsplanen med hänsyn tagen till brist på material eller resurser. På så vis kan planerare använda tillgängliga resurser på bästa sätt, minimera pågående arbete och optimera genomflödestiderna för produktionsorder.

Ett Gantt-diagram är en visuell representation av schemalagda aktiviteter inom ett fastställt tidsintervall. Aktiviteterna schemaläggs på resurser som har en kapacitet enligt en kalender för kapacitet. Följande typer av aktiviteter kan visas i Gantt-diagrammet:

-   Jobb från tillverkningsorder som är schemalagda jobb.
-   Jobb från planerade tillverkningsorder.
-   Finplanerade projektaktiviteter av typen timprognoser.

Gantt-schemat kan öppnas i två olika vyer **Ordervy** och **Resursvy**. I **Ordervy**, grupperas aktiviteter under tillverkningsorder. Detta kan exempelvis vara användbart om du vill behålla en översikt över de jobb som tillhör samma order. I **Resursvy** grupperas alla jobb under enskilda resurser. Den här vyn kan vara användbar när du optimerar planen på resursnivå, till exempel en dator eller en grupp av datorer. Gantt-diagrammet nedan visar **Ordervy** och **Resursvy** med dessa nyckelelement:

1.  Gantt-diagramaktivitet
2.  Symbol för materialbrist
3.  Symbol för materialtillgänglighet
4.  Symbol för orderns leveransdatum
5.  Kapacitetsstapel

## <a name="order-view"></a>Ordervy

[![Ordervy](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Resursvy
[![Resursvy](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Aktiviteter
Aktiviteterna visas som staplar och ordnas i ett tidsskalerutnät med en schemalagd start- och sluttid, som gör längden på staplarna proportionell mot den tid som krävs för att slutföra aktiviteten. Aktiviteterna visas enligt en tidsskala. Du kan anpassa tidsskalan i menyn där du väljer ett startdatum, slutdatum och en tidsenhet såsom timmar eller dagar. Du kan ange fokus på ett tidsintervall inom vilket du vill hantera aktiviteter genom att justera tidsskalan. 

Om du vill få en bättre översikt finns det olika alternativ som styr färgen på aktiviteterna. Du kan konfigurera en enskild färg för aktiviteter, använda temafärgen som allmänt färgtema som används för programmet eller ställa in färgen som ska styras av färgkoden för produktionsorder. 

Tidsintervallet för aktiviteter har en bakgrundsnyans. Perioder med en nyans av vitt anger ett tidsintervall med en definierad kapacitet för resursen för en aktivitet, medan perioder med en grå nyans visar tidsintervall där ingen kapacitet är definierad. 

Till vänster om diagrammet finns ytterligare information om aktiviteten, till exempel resursen på vilken aktiviteten är schemalagd och produktionsordernummer. Sambandet mellan jobb som tillhör samma order indikeras med en pil. 

Du kan få mer information om en aktivitet i dialogrutan Aktivitet. Dubbelklicka på aktiviteten så att den öppnas eller välj menyn **Information**. I dialogrutan Aktivitet ser du planerade start- och slutdatum och tidsinformation om vilka material aktiviteten är planerad att förbruka. 

Aktiviteter kan grupperas i grupperingsnivåer. Grupperingsnivåerna är hierarkiska och kan användas för att göra en logisk gruppering av aktiviteter. Om du exempelvis har en layout där tillverkningsaktiviteter grupperas efter plats, produktionsenheter, resursgrupper och resurser kan du använda grupperingsnivåerna för att gruppera aktiviteter efter layouten. Grupperingsnivåerna kan visas och döljas på den enskilda grupperingsnivån eller för alla nivåer i diagrammet med hjälp av knapparna **Visa alla** och **Dölj alla** på menyn. Du kan också konfigurera vilka grupperingsnivåer du vill visa eller dölja när diagrammet öppnas.

### <a name="material-availability"></a>Tillgång till material

Gantt-diagrammet kan ställas in för att ge planeraren detaljerad information om materialstatus för enskilda aktiviteter. Exempelvis kan det vara användbart om materialet är försenat och påverkar produktionsplanen. I det här fallet markeras materialproblem i Gantt-diagrammet för att hjälpa planeraren att förstå konsekvenser och göra nödvändiga justeringar. 

Ett jobb visas med en symbol för materialbrist om det schemalagda startdatumet för jobbet infaller efter datumet för tillgång på material som förbrukas av jobbet. Datumet för materialtillgängligheten beräknas baserat på pegging-informationen i den dynamiska huvudplanen. Symbolen för materialbrist visas till exempel på ett jobb som förbrukar material som peggas mot en inköpsorder med en inleverans som infaller efter det planerade startdatumet för jobbet.

### <a name="indicator-of-material-availability-date"></a>Indikator för datum för materialtillgänglighet

När du ställer in diagrammet för att visa jobb med materialbrist kan en symbol som visar datumet för materialtillgängligheten för jobbet också visas. Symbolen visas endast om datumet för materialtillgängligheten infaller inom det definierade tidsintervallet i diagrammet. Om datumet för materialtillgängligheten ligger utanför det definierade tidsintervallet kan mer detaljerad information om materialtillgänglighet hämtas från materiallistan i jobbdialogrutan. I listan finns även en symbol som visar försenade material för jobbet. Du kan tidsplanera om ett jobb med hjälp av materialtillgänglighetsdatumet som startdatum.

### <a name="indicator-of-order-delivery-date"></a>Indikator för leveransdatum för order

Symbolen visar leveransdatum för en tillverkningsorder. Symbolen visas endast i Ordervyn.

### <a name="capacity-bar"></a>Kapacitetsstapel

Du kan konfigurera diagrammet om du vill visa en stapel med resurskapacitet. Den här stapeln innehåller en översikt över resurskapacitet för en aktivitet i det definierade tidsintervallet i diagrammet. Kapacitetsstapeln visas inte under tidsperioder då resursen inte är bokad. Under perioder då resursen är kapacitetsbokad visas fältet kapacitetstapeln som en solid stapel. Under perioder där resursen är överbokad är stapeln tjockare och röd. Om exempelvis två jobb överlappar varandra kommer kapacitetsstapeln att indikera ett överbokning i tidsintervallet där det är en överlappning. Kapacitetsstapeln uppdateras dynamiskt när du schemalägger ett jobb. Du aktiverar kapacitetsstapeln i menyn **Visa kapacitetsstapel**. Det kan bara visas i **Resursvy**. Om du vill ha en mer detaljerad vy över kapacitetsbeläggningen för en resurs kan du använda diagrammet **Kapacitetsbeläggning**, som du öppnar från menyn eller innehållsmenyn för en vald aktivitet.

## <a name="job-scheduling-in-the-gantt-chart"></a>Gantt-diagram för jobbplanering
I Gantt-diagrammet finns olika alternativ för att göra justeringar i produktionsplanen. I Gantt-diagrammet kan du planera om aktiviteter som en dra och släpp-interaktion eller från tidsplansmenyn. Under planeringsprocessen bör du beakta resurskapacitet, resurskunskaper och materialbegränsningar.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Tidsplanera ett jobb som en dra och släpp-interaktion

Du kan tidsplanera om jobbet igen inom det definierade tidsintervallet som en dra och släpp-interaktion. Du kan endast tidsplanera om jobbet på samma resurs och du kan endast tidsplanera ett jobb i taget.

### <a name="schedule-a-job-from-the-menu"></a>Tidsplanera ett jobb från menyn

I menyn **Tidplanera jobb** kan du tidsplanera ett eller flera jobb i diagrammet baserat på tidsplaneringsriktningen och ett tidsplaneringsdatum. Det finns tre olika tidsplaneringsriktningar.

-   Framåt från tidsplaneringsdatum
-   Bakåt från tidsplaneringsdatum
-   Framåt från datumet för materialtillgänglighet

Det går inte att schemalägga ett jobb utanför det definierade tidsintervallet i Gantt-diagrammet. Om du gör det kommer jobbet att förbli icke-tidsplanerat och du får felmeddelandet ”Kunde inte tidsplanera jobbet inom den inlästa tidsperioden”.

### <a name="schedule-previous-jobs"></a>Tidsplanera föregående jobb

I ett nätverk med aktiviteter såsom jobb som tillhör samma produktionsorder kan du använda funktionen **Tidsplanera tidigare jobb** för att tidsplanera tidigare jobb i relation till ett valt jobb i nätverket. I exemplet nedan är den markerade aktiviteten det valda jobbet. Diagrammet visar situationer innan ett tidigare jobb har schemalagts, samt efter det att det har schemalagts. 

[![Schemalägg tidigare jobb](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Tidsplanera nästa jobb

Du kan använda funktionen **Tidsplanera nästa jobb** för att tidsplanera nästa jobb i relation till ett valt jobb i ett nätverk med aktiviteter. I exemplet nedan är den markerade aktiviteten det valda jobbet. Diagrammet visar situationer innan nästa jobb har schemalagts, samt efter det att det har schemalagts. 

[![Schemalägg nästa jobb](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Tidsplanera runt jobb

Du kan använda funktionen **Tidsplanera runt jobb** för att tidsplanera nästa jobb och tidigare jobb i relation till ett valt jobb i ett nätverk med aktiviteter. I exemplet nedan är den markerade aktiviteten det valda jobbet. Diagrammet visar situationer innan ett jobb har schemalagts, samt efter det att det har schemalagts. 

[![Tidsplanera runt jobb](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Ordna jobb

Du kan använda funktionen **Ordna** för att ordna valda aktiviteter på samma resurs. Aktiviteterna kan finnas i samma nätverk med aktiviteter, men kan även ingå i olika nätverk. När du använder funktionen Ordna ska tidsgapet mellan de valda aktiviteterna elimineras. Du kan använda funktionen för att optimera kapacitetsutnyttjande resurser. Diagrammet visar situationer innan ett jobb har schemalagts, samt efter det att det har schemalagts. 

[![Ordna jobb](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Tilldela om aktiviteter från en resurs till en annan

Du kan tilldela om ett jobb från en resurs till en annan. Detta kan vara användbart i situationer där en dator är obrukbar eller överbokad och du vill söka efter en annan tillgänglig resurs som kan utföra jobbet.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Tilldela om en aktivitet som en dra och släpp-interaktion

I vyn **Resurs** kan du tilldela om en aktivitet till en annan resurs i Gantt-diagrammet som en dra och släpp-interaktion. Det gör du genom att markera raden där aktiviteten är planerad. Du kan dra raden till resursen i diagrammet grupperad under en annan resursgrupperingsnivå när du har valt raden.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Tilldela om en aktivitet från menyn Schemalägg jobb

Du kan tilldela om ett jobb från dialogrutan **Schemalägg jobb** öppnad från menyn **Schemalägg jobb**. Från den här menyn kan du endast tilldela ett jobb till en resurs som redan har lästs in i Gantt-schemat. Om du bara väljer ett jobb sorteras i listrutan för resursen efter tillämpliga resurser. Om du väljer flera jobb kommer det inte att finnas någon information om tillämpliga resurser från resurslistan.

## <a name="load-additional-resources-to-the-gantt-chart"></a>Läsa in ytterligare resurser i Gantt-schemat
I **Resursvy** har du möjlighet att läsa in ytterligare resurser i Gantt-schemat. Detta kan vara användbart om du vill söka efter en alternativ resurs för ett jobb som schemaläggs på en dator som är överbokad eller ur funktion. På sidan **Läs in ytterligare resurser** visas en lista över resurser som är datumeffektiva från och med det datum som listan öppnas. Tillämpliga resurser i relation till ett valt jobb i Gantt-diagrammet visas först. Om du har markerat flera jobb innan du öppnar listan visas inte tillämpliga resurser. På sidan **Läs in ytterligare resurser** kan du välja en eller flera resurser som ska läsas in i Gantt-schemat när du bekräftar ditt val. Om det inte finns några jobb som är tidsplanerade för den valda resursen i Gantt-diagrammet kommer resursen att placeras under en resursgrupperingsnivå längst ned i listan över aktiviteter i Gantt-diagrammet.

### <a name="access-the-gantt-chart"></a>Komma åt Gantt-diagrammet.

Gantt-schemat kan öppnas från följande sidor:


|                                                 <strong>Sida</strong>                                                  |                                                                                                                                                                                                                                                            <strong>Beskrivning</strong>                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   <strong>Produktionsorderlista och detaljer</strong>                                    | På sidan <strong>Produktionsorderlista och detaljer</strong> kan du öppna Gantt-diagrammet från en eller flera valda order. Om du öppnar diagrammet via menyalternativet <strong>Gantt-diagram</strong> inläses alla jobb som är relaterade till den valda produktionsordern, och även jobb från andra tillverkningsorder som är tidsplanerade på samma resurser. Om du öppnar diagrammet från menyn <strong>Gantt-diagram – snabbvisning</strong> inläses endast jobb som är relaterade till valda produktionsorder. I den här vyn går det inte att tidsplanera jobb. |
|                                               <strong>Resurs</strong>                                                |                                                                                                                                                        På sidan <strong>Resurs</strong> kan du öppna Gantt-diagrammet från menyalternativet <strong>Gantt-diagram</strong>. När du har markerat alternativet kommer alla jobb som är tidsplanerade för en resurs i det valda tidsintervallet att läsas in i diagrammet.                                                                                                                                                         |
|                                            <strong>Resursgrupp</strong>                                             |                                                                                                                                                 På sidan <strong>Resursgrupp</strong> kan du öppna Gantt-diagrammet från menyalternativet <strong>Gantt-diagram</strong>. När du har markerat alternativet kommer alla jobb som är tidsplanerade för resurser i resursgruppen att läsas in i diagrammet.                                                                                                                                                 |
|                                             <strong>Gantt-diagram</strong>                                              |                                                                                 På sidan <strong>Gantt-diagram</strong> kan du konfigurera Gantt-diagram efter resurser och resursgrupper. Till exempel om du vill styra produktionsaktiviteter för specifika uppsättningar resurser eller resursgrupper kan du skapa enskilda konfigurationer av dem på sidan <strong>Gantt-diagram</strong>. Du kan sedan öppna Gantt-diagrammet från varje konfiguration.                                                                                 |
|                                       <strong>Timprognoser</strong> (projekt)                                        |                                                                                                                              Projektaktiviteter av typen <strong>Timprognos</strong> kan tidsplaneras som jobb på resurser. På sidan <strong>Timprognos</strong> i menyn <strong>Tidsplanering</strong> kan du öppna ett Gantt-diagram i en order för att se tidsplanerade jobbs projektaktiviteter av typen timprognos.                                                                                                                               |
|           <strong>Jobb att slutföra</strong> (lista i arbetsytan <strong>Produktionsgolvsledning</strong>)            |                                                                                               Listan <strong>Jobb att slutföra i arbetsytan Produktionsgolvsledning</strong> visar jobb från produktions- och batchorder som pågår på de markerade resurserna på arbetsytan. Via menyalternativet <strong>Gantt-diagram</strong> kan du öppna ett Gantt-diagram där alla markerade jobb i listan läses in i diagrammet.                                                                                               |
| <strong>Produktionsorder som ska frisläppas</strong> (öppnas från arbetsytan <strong>Produktionsgolvsledning</strong>) |                                                                                                                                         Sidan Produktionsorder som ska frisläppas öppnas från arbetsytan <strong>Produktionsgolvsledning</strong>. Den här sidan visar tidsplanerade produktions- och batchorder som väntar på att frisläppas. På den här sidan kan du öppna Gantt-diagrammet för valda produktionsorder.                                                                                                                                          |

## <a name="additional-resources"></a>Ytterligare resurser  
[Visuell schemaläggning med Gantt-schema för produktion och batch-order (Video)](https://youtu.be/BtbuShkGj4I)

[Visuell planering för produktion (demo-skrift)](https://docs.microsoft.com/dynamics/s-e/)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]