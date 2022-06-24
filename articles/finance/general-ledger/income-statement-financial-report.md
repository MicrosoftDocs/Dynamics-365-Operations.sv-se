---
title: Resultaträkning
description: Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9a1f20ed5e2a84e0d18101ede46ffffef4230c7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868472"
---
# <a name="income-statement-financial-report"></a>Resultaträkning

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver standardrapporten för inkomstredovisning. Här beskrivs också de byggstenar som associeras med den här rapporten. 

## <a name="default-income-statement-report"></a>Standardresultaträkning

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



## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över ekonomisk rapportering](financial-reporting-getting-started.md)

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
