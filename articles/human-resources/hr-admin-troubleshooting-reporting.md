---
title: Rapporteringsalternativ
description: Detta ämne förklarar hur du anpassar Microsoft Dynamics 365 Human Resources-rapporter eller skapar nya rapporter.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 706e901e89fa618540067d68546be1cef1ee7148
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413392"
---
# <a name="reporting-options"></a>Rapporteringsalternativ

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Miljöinformation**

Det här problemet gäller alla miljöer.

**Symptom**

Kunden vill anpassa rapporter för Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.

**Utleverans**

Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.

**Lösning**

- Personal-data som flödar till Dataverse kan rapporteras via Power Apps Dataverse-kopplingen till Power BI Desktop. Observera att Dataverse innehåller en underuppsättning av Personal-data. Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Personal. Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.
- Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Personal tillhandahåller genom Microsoft Office-integreringen.

**Långsiktig lösning**

Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
