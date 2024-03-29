---
title: Övervaka en huvudplaneringskörning
description: Denna artikel förklarar hur produktionsplanerare kan se om en huvudplaneringskörning pågår.
author: t-benebo
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da04ef95f2f7e411ecea3fadf7ff31b3502d3d99
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860766"
---
# <a name="monitor-a-master-planning-run"></a>Övervaka en huvudplaneringskörning

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Visualisera huvudplaneringsförlopp med hjälp av ett Gantt-diagram

På sidan **Visa huvudplaneringsförlopp** kan du visa detaljer om historisk huvudplanering som körs som ett Gantt-diagram. Med hjälp av den här funktionen kan du förstå hur lång tid som ägnas åt olika faser i huvudplaneringen. För ett aktuellt aktivt planeringsjobb kan du använda sidan **Visa huvudplaneringsförlopp** för att spåra status och visa den uppskattade återstående tiden.

### <a name="turn-the-master-plan-progress-visualization-feature-on-or-off"></a>Aktivera och inaktivera funktionen för visualisering av huvudplanstatus

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Visualisering av huvudplaneringsförlopp* i arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="use-the-master-plan-progress-visualization-feature"></a>Använda funktionen för visualisering av huvudplanstatus

Sidan **Visa huvudplaneringsförlopp** kan visa både historiska planeringsjobb och aktiva planeringsjobb. 

Det finns två alternativ för att visa historiska planeringsjobb. 

1. Gå till **huvudplanering \> inställningar \> planer \> huvudplaner** och välj sedan **historik** i åtgärdsfönstret. Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**
1. Gå till **huvudplanering \> arbetsytor \> huvudplanering** och klicka på **historik** på panelen Huvudplanering. Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**

Det finns två alternativ för att visa aktiva planeringsjobb. 
1. Gå till **Huvudplanering \> Arbetsytor \> Huvudplanering** i åtgärdsfönstret välj **Oavslutade planeringsprocesser**. Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**.
1. Gå till **huvudplanering \> arbetsytor \> huvudplanering** och klicka på **Visa förlopp** på panelen Huvudplanering. Med det valda jobbet markerat väljer du **Förfrågningar** och väljer **Visa förlopp**

Observera att du kan bara visa aktiva jobb när ett planeringsjobb bearbetas.

### <a name="analyze-a-master-planning-job"></a>Analysera ett huvudplaneringsjobb

I Gantt-diagrammet kan du expandera var och en av följande planeringsprocesser för att visa mer information om tiden som förbrukas:

- Initierar
- Tar bort och infogar data
- Disponeringsplanering
- Fördröjningar
- Åtgärdsmeddelanden
- Slutförande
- Automatisk bekräftelse

Gantt-diagrammet är ett användbart verktyg om du vill visa effekten av att använda åtgärdsmeddelanden.

#### <a name="navigation-in-the-gantt-chart"></a>Navigering i Gantt-diagrammet

- Om du vill expandera den markerade gruppen och visa information markerar du plustecknet (**+**) i trädvyn.
- Om du vill komprimera den markerade gruppen väljer du minustecknet (**–**) i trädvyn.
- Du kan använda tangentbordet för att navigera. Använd **uppilen** och **nedpilen** om du vill flytta mellan raderna. Använd **högerpilen** och **vänsterpilen** för att visa eller dölja grupper.
- Om du vill öppna eller stänga alla nivåer i Gantt-diagrammet väljer du **Visa alla** eller **Dölj alla**.
- Om du vill visa den relaterade bearbetningstiden hovrar du över en aktivitet. (Uppgifter är de lägsta nivåerna i Gantt-diagrammet.)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Visa en ytterligare huvudplaneringskörning för att jämföra jobb

Genom att välja ett huvudplaneringsjobb på fältet **Visa ytterligare huvudplaneringskörning**, men du kan visa ytterligare en huvudplaneringskörning i Gantt-diagrammet och jämföra de två jobben.

#### <a name="bom-level-display"></a>Visning på strukturnivå

Strukturlistenivåer visas på olika sätt vid disponeringsplanering, förseningar, åtgärder och bekräftelse.

- **Disponeringsplanering** – strukturnivåerna visas som förväntat. De beräknas uppifrån och ned.

    **Exempel:** Strukturlistenivå 0, 1, 2

- **Fördröjningar** – strukturlistenivåer visas som disponeringsplanering för strukturlistenivåer multiplicerat med –1. (Med andra ord har de ett negativt tecken.)

    **Exempel:** Strukturlistenivå –2, –1, 0

- **Åtgärdsmeddelande** – strukturnivåerna visas som förväntat. De beräknas uppifrån och ned.

    **Exempel:** Strukturlistenivå 0, 1, 2

- **Automatisk bekräftelse** – strukturlistenivåerna visas som 999 minus nivån för disponeringsplanering.

    **Exempel:** Strukturlistenivå 999, 998, 997

I följande tabell sammanfattas beteendet.

| Strukturlistenivå som visas | Slutartikel | Delkomponent | Råmaterial |
|---|---|---|---|
| Disponeringsplanering | 0 | 1 | 2 |
| Fördröjningar | 0 | –1 | –2 |
| Åtgärdsmeddelande | 0 | 1 | 2 |
| Automatisk bekräftelse | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Visualisera förlopp

Om du visar ett huvudplaneringsjobb som körs visas förlopp via färger i Gantt-diagrammet. Följande färger gäller för det blåa temat. För andra färgteman skiljer sig färgerna åt.

- **Mörkblå** – slutförda planeringsuppgifter.
- **Orange** – den uppgift som pågår just nu.
- **Ljusblå** – uppskattningen för återstående uppgifter.

Färgen visas endast på den lägsta nivån i Gantt-diagrammet. Välj **expandera alla** om du vill visa alla uppgifter i huvudplaneringsjobbet. Uppskattningen av återstående uppgifter baseras på historiska huvudplaneringsjobb.

## <a name="run-master-planning-and-track-processing-time"></a>Kör huvudplanering och spårning av bearbetningstid

1. Välj **Huvudplanering** på standardinstrumentpanelen.
1. I fältet **Plan**, ange eller välj ett värde.
1. Välj **kör**.
1. Ange alternativet **Spåra bearbetningstid** till **Ja**.
1. Ange ett nummer i fältet **Antal trådar.**
1. På snabbfliken **Poster att inkludera**, välj **Filter**.
1. I rutnätet väljer du den rad där fältet **fält** är inställt på **artikelnummer**.
1. I fältet **Kriterier** anger du ett värde.
1. Välj **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]