---
title: "Gantt-diagram för jobbplanering"
description: "Gantt-diagrammet har utformats för att tillåta produktionsplanerare att kontrollera och optimera produktionsplanen. Gantt-diagrammet gör arbetsflödet transparent och gör det enkelt att justera produktionsplanen med hänsyn tagen till brist på material eller resurser. På så vis kan planerare använda tillgängliga resurser på bästa sätt, minimera pågående arbete och optimera genomflödestiderna för produktionsorder."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: JmgShopSupervisorWorkspace ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: johanhoffmann
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 55631c4d588c699b9e47f73190d5b01d6da3b9ec
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# Gantt-diagram för jobbplanering
<a id="gantt-chart-for-job-scheduling" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Gantt-diagrammet har utformats för att tillåta produktionsplanerare att kontrollera och optimera produktionsplanen. Gantt-diagrammet gör arbetsflödet transparent och gör det enkelt att justera produktionsplanen med hänsyn tagen till brist på material eller resurser. På så vis kan planerare använda tillgängliga resurser på bästa sätt, minimera pågående arbete och optimera genomflödestiderna för produktionsorder.

Gantt-diagrammet har utformats för att tillåta produktionsplanerare att kontrollera och optimera produktionsplanen. Gantt-diagrammet gör arbetsflödet transparent och gör det enkelt att justera produktionsplanen med hänsyn tagen till brist på material eller resurser. På så vis kan planerare använda tillgängliga resurser på bästa sätt, minimera pågående arbete och optimera genomflödestiderna för produktionsorder.

Ett Gantt-diagram är en visuell representation av schemalagda aktiviteter inom ett fastställt tidsintervall. Aktiviteterna schemaläggs på resurser som har en kapacitet enligt en kalender för kapacitet. Följande typer av aktiviteter kan visas i Gantt-diagrammet:

-   Jobb från tillverkningsorder som är schemalagda jobb.
-   Jobb från planerade tillverkningsorder.
-   Finplanerade projektaktiviteter av typen timprognoser.

Gantt-diagrammet kan öppnas i två lägen: **Ordervy** och **Resursvy**[.](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true)I **Ordervy** är aktiviteter grupperade under tillverkningsorder. Detta kan exempelvis vara användbart om du vill behålla en översikt över de jobb som tillhör samma order. I **Resursvy** grupperas alla jobb under enskilda resurser. Den här vyn kan vara användbar när du optimerar planen på resursnivå, till exempel en dator eller en grupp av datorer. Gantt-diagrammet nedan visar **Ordervy** och **Resursvy** med dessa nyckelelement:

1.  Gantt-diagramaktivitet
2.  Symbol för materialbrist
3.  Symbol för materialtillgänglighet
4.  Symbol för orderns leveransdatum
5.  Kapacitetsstapel

## Ordervy
<a id="order-view" class="xliff"></a>

[![ordervy](./media/orderview.png)](./media/orderview.png)

## Resursvy
<a id="resource-view" class="xliff"></a>
[![resursvy](./media/resview.png)](./media/resview.png)

## Aktiviteter
<a id="activities" class="xliff"></a>
Aktiviteterna visas som staplar och ordnas i ett tidsskalerutnät med en schemalagd start- och sluttid, som gör längden på staplarna proportionell mot den tid som krävs för att slutföra aktiviteten. Aktiviteterna visas enligt en tidsskala. Du kan anpassa tidsskalan i menyn där du väljer ett startdatum, slutdatum och en tidsenhet såsom timmar eller dagar. Du kan ange fokus på ett tidsintervall inom vilket du vill hantera aktiviteter genom att justera tidsskalan. 

Om du vill få en bättre översikt finns det olika alternativ som styr färgen på aktiviteterna. Du kan konfigurera en enskild färg för aktiviteter, använda temafärgen som allmänt färgtema som används för programmet eller ställa in färgen som ska styras av färgkoden för produktionsorder. 

Tidsintervallet för aktiviteter har en bakgrundsnyans. Perioder med en nyans av vitt anger ett tidsintervall med en definierad kapacitet för resursen för en aktivitet, medan perioder med en grå nyans visar tidsintervall där ingen kapacitet är definierad. 

Till vänster om diagrammet finns ytterligare information om aktiviteten, till exempel resursen på vilken aktiviteten är schemalagd och produktionsordernummer. Sambandet mellan jobb som tillhör samma order indikeras med en pil. 

Du kan få mer information om en aktivitet i dialogrutan Aktivitet. Dubbelklicka på aktiviteten så att den öppnas eller välj menyn **Information**. I dialogrutan Aktivitet ser du planerade start- och slutdatum och tidsinformation om vilka material aktiviteten är planerad att förbruka. 

Aktiviteter kan grupperas i grupperingsnivåer. Grupperingsnivåerna är hierarkiska och kan användas för att göra en logisk gruppering av aktiviteter. Om du exempelvis har en layout där tillverkningsaktiviteter grupperas efter plats, produktionsenheter, resursgrupper och resurser kan du använda grupperingsnivåerna för att gruppera aktiviteter efter layouten. Grupperingsnivåerna kan visas och döljas på den enskilda grupperingsnivån eller för alla nivåer i diagrammet med hjälp av knapparna **Visa alla** och **Dölj alla** på menyn. Du kan också konfigurera vilka grupperingsnivåer du vill visa eller dölja när diagrammet öppnas.

### Tillgång till material
<a id="material-availability" class="xliff"></a>

Gantt-diagrammet kan ställas in för att ge planeraren detaljerad information om materialstatus för enskilda aktiviteter. Exempelvis kan det vara användbart om materialet är försenat och påverkar produktionsplanen. I det här fallet markeras materialproblem i Gantt-diagrammet för att hjälpa planeraren att förstå konsekvenser och göra nödvändiga justeringar. 

Ett jobb visas med en symbol för materialbrist om det schemalagda startdatumet för jobbet infaller efter datumet för tillgång på material som förbrukas av jobbet. Datumet för materialtillgängligheten beräknas baserat på pegging-informationen i den dynamiska huvudplanen. Symbolen för materialbrist visas till exempel på ett jobb som förbrukar material som peggas mot en inköpsorder med en inleverans som infaller efter det planerade startdatumet för jobbet.

### Indikator för datum för materialtillgänglighet
<a id="indicator-of-material-availability-date" class="xliff"></a>

När du ställer in diagrammet för att visa jobb med materialbrist kan en symbol som visar datumet för materialtillgängligheten för jobbet också visas. Symbolen visas endast om datumet för materialtillgängligheten infaller inom det definierade tidsintervallet i diagrammet. Om datumet för materialtillgängligheten ligger utanför det definierade tidsintervallet kan mer detaljerad information om materialtillgänglighet hämtas från materiallistan i jobbdialogrutan. I listan finns även en symbol som visar försenade material för jobbet. Du kan tidsplanera om ett jobb med hjälp av materialtillgänglighetsdatumet som startdatum.

### Indikator för leveransdatum för order
<a id="indicator-of-order-delivery-date" class="xliff"></a>

Symbolen visar leveransdatum för en tillverkningsorder. Symbolen visas endast i Ordervyn.

### Kapacitetsstapel
<a id="capacity-bar" class="xliff"></a>

Du kan konfigurera diagrammet om du vill visa en stapel med resurskapacitet. Den här stapeln innehåller en översikt över resurskapacitet för en aktivitet i det definierade tidsintervallet i diagrammet. Kapacitetsstapeln visas inte under tidsperioder då resursen inte är bokad. Under perioder då resursen är kapacitetsbokad visas fältet kapacitetstapeln som en solid stapel. Under perioder där resursen är överbokad är stapeln tjockare och röd. Om exempelvis två jobb överlappar varandra kommer kapacitetsstapeln att indikera ett överbokning i tidsintervallet där det är en överlappning. Kapacitetsstapeln uppdateras dynamiskt när du schemalägger ett jobb. Du aktiverar kapacitetsstapeln i menyn **Visa kapacitetsstapel**. Det kan bara visas i **Resursvy**. Om du vill ha en mer detaljerad vy över kapacitetsbeläggningen för en resurs kan du använda diagrammet **Kapacitetsbeläggning**, som du öppnar från menyn eller innehållsmenyn för en vald aktivitet.

## Gantt-diagram för jobbplanering
<a id="job-scheduling-in-the-gantt-chart" class="xliff"></a>
I Gantt-diagrammet finns olika alternativ för att göra justeringar i produktionsplanen. I Gantt-diagrammet kan du planera om aktiviteter som en dra och släpp-interaktion eller från tidsplansmenyn. Under planeringsprocessen bör du beakta resurskapacitet, resurskunskaper och materialbegränsningar.

### Tidsplanera ett jobb som en dra och släpp-interaktion
<a id="schedule-a-job-as-a-drag-and-drop-interaction" class="xliff"></a>

Du kan tidsplanera om jobbet igen inom det definierade tidsintervallet som en dra och släpp-interaktion. Du kan endast tidsplanera om jobbet på samma resurs och du kan endast tidsplanera ett jobb i taget.

### Tidsplanera ett jobb från menyn
<a id="schedule-a-job-from-the-menu" class="xliff"></a>

I menyn **Tidplanera jobb** kan du tidsplanera ett eller flera jobb i diagrammet baserat på tidsplaneringsriktningen och ett tidsplaneringsdatum. Det finns tre olika tidsplaneringsriktningar.

-   Framåt från tidsplaneringsdatum
-   Bakåt från tidsplaneringsdatum
-   Framåt från datumet för materialtillgänglighet

Det går inte att schemalägga ett jobb utanför det definierade tidsintervallet i Gantt-diagrammet. Om du gör det kommer jobbet att förbli icke-tidsplanerat och du får felmeddelandet ”Kunde inte tidsplanera jobbet inom den inlästa tidsperioden”.

### Tidsplanera föregående jobb
<a id="schedule-previous-jobs" class="xliff"></a>

I ett nätverk med aktiviteter såsom jobb som tillhör samma produktionsorder kan du använda funktionen **Tidsplanera tidigare jobb** för att tidsplanera tidigare jobb i relation till ett valt jobb i nätverket. I exemplet nedan är den markerade aktiviteten det valda jobbet.

<table>
<tr>
<td>
Före
</td>
<td rowspan=2>
<img src='./media/schprevjob3.png'/>
</td>
</tr>
<tr>
<td>
Efter
</td>
</tr>
</table>

### Tidsplanera nästa jobb
<a id="schedule-next-jobs" class="xliff"></a>

Du kan använda funktionen **Tidsplanera nästa jobb** för att tidsplanera nästa jobb i relation till ett valt jobb i ett nätverk med aktiviteter. I exemplet nedan är den markerade aktiviteten det valda jobbet.

<table>
<tr>
<td>
Före
</td>
<td rowspan=2>
<img src='./media/schnxtjob.png'/>
</td>
</tr>
<tr>
<td>
Efter
</td>
</tr>
</table>

### Tidsplanera runt jobb
<a id="schedule-around-job" class="xliff"></a>

Du kan använda funktionen **Tidsplanera runt jobb** för att tidsplanera nästa jobb och tidigare jobb i relation till ett valt jobb i ett nätverk med aktiviteter. I exemplet nedan är den markerade aktiviteten det valda jobbet.

<table>
<tr>
<td>
Före
</td>
<td rowspan=2>
<img src='./media/scharoundjob1.png'/>
</td>
</tr>
<tr>
<td>
Efter
</td>
</tr>
</table>

### Ordna jobb
<a id="arrange-jobs" class="xliff"></a>

Du kan använda funktionen **Ordna** för att ordna valda aktiviteter på samma resurs. Aktiviteterna kan finnas i samma nätverk med aktiviteter, men kan även ingå i olika nätverk. När du använder funktionen Ordna ska tidsgapet mellan de valda aktiviteterna elimineras. Du kan använda funktionen för att optimera kapacitetsutnyttjande resurser.

<table>
<tr>
<td>
Före
</td>
<td rowspan=2>
<img src='./media/arrangejobs1.png'/>
</td>
</tr>
<tr>
<td>
Efter
</td>
</tr>
</table>

### Tilldela om aktiviteter från en resurs till en annan
<a id="reassign-activities-from-one-resource-to-another" class="xliff"></a>

Du kan tilldela om ett jobb från en resurs till en annan. Detta kan vara användbart i situationer där en dator är obrukbar eller överbokad och du vill söka efter en annan tillgänglig resurs som kan utföra jobbet.

### Tilldela om en aktivitet som en dra och släpp-interaktion
<a id="reassigning-an-activity-as-a-drag-and-drop-interaction" class="xliff"></a>

I vyn **Resurs** kan du tilldela om en aktivitet till en annan resurs i Gantt-diagrammet som en dra och släpp-interaktion. Det gör du genom att markera raden där aktiviteten är planerad. Du kan dra raden till resursen i diagrammet grupperad under en annan resursgrupperingsnivå när du har valt raden.

### Tilldela om en aktivitet från menyn Schemalägg jobb
<a id="reassigning-an-activity-from-the-schedule-jobs-menu" class="xliff"></a>

Du kan tilldela om ett jobb från dialogrutan **Schemalägg jobb** öppnad från menyn **Schemalägg jobb**. Från den här menyn kan du endast tilldela ett jobb till en resurs som redan har lästs in i Gantt-schemat. Om du bara väljer ett jobb sorteras i listrutan för resursen efter tillämpliga resurser. Om du väljer flera jobb kommer det inte att finnas någon information om tillämpliga resurser från resurslistan.

## Läsa in ytterligare resurser i Gantt-schemat
<a id="load-additional-resources-to-the-gantt-chart" class="xliff"></a>
I **Resursvy** har du möjlighet att läsa in ytterligare resurser i Gantt-schemat. Detta kan vara användbart om du vill söka efter en alternativ resurs för ett jobb som schemaläggs på en dator som är överbokad eller ur funktion. På sidan **Läs in ytterligare resurser** visas en lista över resurser som är datumeffektiva från och med det datum som listan öppnas. Tillämpliga resurser i relation till ett valt jobb i Gantt-diagrammet visas först. Om du har markerat flera jobb innan du öppnar listan visas inte tillämpliga resurser. På sidan **Läs in ytterligare resurser** kan du välja en eller flera resurser som ska läsas in i Gantt-schemat när du bekräftar ditt val. Om det inte finns några jobb som är tidsplanerade för den valda resursen i Gantt-diagrammet kommer resursen att placeras under en resursgrupperingsnivå längst ned i listan över aktiviteter i Gantt-diagrammet.

### Komma åt Gantt-diagrammet.
<a id="access-the-gantt-chart" class="xliff"></a>

Gantt-schemat kan öppnas från följande sidor:

| **Sida**                                                                                     | **Beskrivning**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Produktionsorderlista och detaljer**                                                         | På sidan **Produktionsorderlista och detaljer** kan du öppna Gantt-diagrammet från en eller flera valda order. Om du öppnar diagrammet via menyalternativet **Gantt-diagram** inläses alla jobb som är relaterade till den valda produktionsordern, och även jobb från andra tillverkningsorder som är tidsplanerade på samma resurser. Om du öppnar diagrammet från menyn **Gantt-diagram – snabbvisning** inläses endast jobb som är relaterade till valda produktionsorder. I den här vyn går det inte att tidsplanera jobb. |
| **Resurs**                                                                                 | På sidan **Resurs** kan du öppna Gantt-diagrammet från menyalternativet **Gantt-diagram**. När du har markerat alternativet kommer alla jobb som är tidsplanerade för en resurs i det valda tidsintervallet att läsas in i diagrammet.                                                                                                                                                                                                                                                                                                   |
| **Resursgrupp**                                                                           | På sidan **Resursgrupp** kan du öppna Gantt-diagrammet från menyalternativet **Gantt-diagram**. När du har markerat alternativet kommer alla jobb som är tidsplanerade för resurser i resursgruppen att läsas in i diagrammet.                                                                                                                                                                                                                                                                                    |
| **Gantt-diagram**                                                                             | På sidan **Gantt-diagram** kan du konfigurera Gantt-diagram efter resurser och resursgrupper. Till exempel om du vill styra produktionsaktiviteter för specifika uppsättningar resurser eller resursgrupper kan du skapa enskilda konfigurationer av dem på sidan **Gantt-diagram**. Du kan sedan öppna Gantt-diagrammet från varje konfiguration.                                                                                                                                                    |
| **Timprognoser** (projekt)                                                                 | Projektaktiviteter av typen **Timprognos** kan tidsplaneras som jobb på resurser. På sidan **Timprognos** i menyn **Tidsplanering** kan du öppna ett Gantt-diagram i en order för att se tidsplanerade jobbs projektaktiviteter av typen timprognos.                                                                                                                                                                                                                                                             |
| **Jobb att slutföra** (lista i arbetsytan **Produktionsgolvsledning**)                      | Listan **Jobb att slutföra i arbetsytan Produktionsgolvsledning** visar jobb från produktions- och batchorder som pågår på de markerade resurserna på arbetsytan. Via menyalternativet **Gantt-diagram** kan du öppna ett Gantt-diagram där alla markerade jobb i listan läses in i diagrammet.                                                                                                                                                                                |
| **Produktionsorder som ska frisläppas** (öppnas från arbetsytan **Produktionsgolvsledning**) | Sidan Produktionsorder som ska frisläppas öppnas från arbetsytan **Produktionsgolvsledning**. Den här sidan visar tidsplanerade produktions- och batchorder som väntar på att frisläppas. På den här sidan kan du öppna Gantt-diagrammet för valda produktionsorder.                                                                                                                                                                                                                                                        |




