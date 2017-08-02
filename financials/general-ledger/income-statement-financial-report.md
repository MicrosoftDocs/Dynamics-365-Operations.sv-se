---
title: "Resultaträkning"
description: "Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f07aea0b87bc3e09982f9ba248d3c28540fd2dc5
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


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




