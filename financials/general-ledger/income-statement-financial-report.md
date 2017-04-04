---
title: "Resultaträkning"
description: "Den här artikeln beskrivs standardrapporten för resultaträkningar. Här beskrivs också byggstenar som associeras med den här rapporten."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 8dd289c1943afb55373ba682afcc3cd107cb67a7
ms.lasthandoff: 03/31/2017


---

# <a name="income-statement-financial-report"></a>Resultaträkning

Den här artikeln beskrivs standardrapporten för resultaträkningar. Här beskrivs också byggstenar som associeras med den här rapporten. 

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

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[Blogg för Dynamics ekonomisk rapportering](http://blogs.msdn.com/b/dynamics_financial_reporting/)


