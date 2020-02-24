---
title: Rapporteringsalternativ
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ee6dba5e37877f1c0b3b9df8306b3194ea2f3e4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010671"
---
# <a name="reporting-options"></a>Rapporteringsalternativ

**Miljöinformation**

Det här problemet gäller alla miljöer.

**Symptom**

Kunden vill anpassa rapporter för Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.

**Utleverans**

Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.

**Lösning**

- Personal-data som flödar till Common Data Service kan rapporteras via Power Apps Common Data Service-kopplingen till Power BI Desktop. Observera att Common Data Service innehåller en underuppsättning av Personal-data. Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Personal. Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.
- Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Personal tillhandahåller genom Microsoft Office-integrationen.

**Långsiktig lösning**

Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service.
