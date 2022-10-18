---
title: Balansräkning
description: Den här artikeln beskriver standardrapporter för balansräkningar. Den beskrivs också de byggstenar som associeras med dessa rapporter.
author: jinniew
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad297f401143388d682da175a6b14727a8f2f0
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643834"
---
# <a name="balance-sheet-financial-reports"></a>Balansräkning

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver standardrapporter för balansräkningar. Den beskrivs också de byggstenar som associeras med dessa rapporter. 

## <a name="default-balance-sheet-reports"></a>Standardbalansräkning

Det finns två standardrapporter för balansräkning. På en rapport staplas avsnitten. På den andra rapporten visas är avsnitten bredvid varandra.

| Standardrapport                       | Vad den gör                                                                                                                           |
|--------------------------------------|--------------------------------------------------------------------------------------|
| Balansräkning – standardinställning              | Visar organisationens ekonomiska läge för året.                    |
| Balansräkning och resultaträkning sida vid sida – standardinställning | Visar organisationens ekonomiska läge för året. |

## <a name="building-blocks"></a>Byggblock
Balansräkningen använder följande byggstenar.

| Standardrapport                       | Raddefinition                       | Kolumndefinition             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Balansräkning – standardinställning              | Balansräkning – standardinställning              | Hittills i år och avvikelse – standardinställning    |
| Balansräkning och resultaträkning sida vid sida – standardinställning | Balansräkning och resultaträkning sida vid sida – standardinställning | Kolumn för ackumulerat för året – standardinställning |

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

-   **Kolumn för ackumulerat för året – standardinställning:**
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **FD** – ackumulerat för året för innevarande år



## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över ekonomisk rapportering](financial-reporting-getting-started.md)

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
