---
title: "Resultaträkning"
description: "Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8ca90b949a1a2b5af4a0fd78ddf80d5add2565b9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="income-statement-financial-report"></a>Resultaträkning

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten. 

<a name="default-income-statement-report"></a>Standardresultaträkning
-------------------------------

| Standardrapport             | Vad den gör                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Resultaträkning – standardinställning | Visar organisationens lönsamhet för den aktuella perioden och även till dags dato. |

## <a name="building-blocks"></a>Byggstenar
Resultatrapporten använder följande byggstenar.

| Standardrapport             | Raddefinition                     | Kolumndefinition          |
|----------------------------|------------------------------------|----------------------------|
| Resultaträkning – standardinställning | Översiktsresultaträkning – standardinställning | Periodisk och hittills i år – standardvärde |

### <a name="row-definition"></a>Raddefinition

Raddefinitionen, översiktsresultaträkningen – standardinställning, innehåller ett avsnitt för varje del av en traditionell resultaträkning. Huvudkontokategoridimensionen används för att bygga upp raddefinitionen. Därför kan alla generera rapporten, utan att behöva göra några ändringar.

### <a name="column-definition"></a>Kolumndefinition

Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.

-   **Periodisk och hittills i år – standardkolumntyper:**
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **FD** – ekonomiska data för den aktuella perioden
    -   **FD** – ekonomiska data hittills i år

 

<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-getting-started.md)

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](http://blogs.msdn.com/b/dynamics_financial_reporting/)




