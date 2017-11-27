---
title: "Balansräkning"
description: "Den här artikeln beskriver standardrapporter för balansräkningar. Den beskrivs också de byggstenar som associeras med dessa rapporter."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 493c54105b36e561edf6d5db95eaff442a812905
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="balance-sheet-financial-reports"></a>Balansräkning

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver standardrapporter för balansräkningar. Den beskrivs också de byggstenar som associeras med dessa rapporter. 

<a name="default-balance-sheet-reports"></a>Standardbalansräkning
-----------------------------

Det finns två standardrapporter för balansräkning. På en rapport staplas avsnitten. På den andra rapporten visas är avsnitten bredvid varandra.

| Standardrapport                       | Vad den gör                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Balansräkning – standardinställning              | Visar organisationens ekonomiska läge för året.                                                                 |
| Balansräkning sida vid sida – standardinställning | Visar organisationens ekonomiska läge för året. Tillgångar och skulder och aktiekapitalet visas sida vid sida. |

## <a name="building-blocks"></a>Byggstenar
Balansräkningen använder följande byggstenar.

| Standardrapport                       | Raddefinition                       | Kolumndefinition             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Balansräkning – standardinställning              | Balansräkning – standardinställning              | Hittills i år och avvikelse - standardinställning    |
| Balansräkning sida vid sida – standardinställning | Balansräkning sida vid sida – standardinställning | Kolumn för ackumulerat för året - standardinställning |

### <a name="row-definition"></a>Raddefinition

Raddefinitioner för båda balansräkningsrapporterna innehåller avsnitt för varje del i en traditionell balansräkning. I rapporten där elementen visas bredvid varandra finns en kolumnbrytning så att skulder och eget kapital visas bredvid tillgångar. Huvudkontokategoridimensionen används för att bygga upp båda raddefinitionerna. Därför kan alla generera rapporterna, utan att behöva göra några ändringar.

### <a name="column-definition"></a>Kolumndefinition

Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.

-   **Hittills i år och avvikelse – standardkolumntyper:**
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **FD** – ackumulerat för året för innevarande år
    -   **FD** – ackumulerat för året för det senaste året
    -   **CALC** – avvikelsen från subtraktionen av förra året från innevarande år

<!-- -->

-   **Kolumn för ackumulerat för året - standardinställning:**
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **FD** – ackumulerat för året för innevarande år

 

<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-getting-started.md)

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](http://blogs.msdn.com/b/dynamics_financial_reporting/)




