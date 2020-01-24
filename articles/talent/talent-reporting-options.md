---
title: Rapportalternativ i Talent
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 Talent eller skapa nya rapporter.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 05d4a2c4314b40042ae45b4f653554bad09be4fa
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897958"
---
# <a name="reporting-options-in-talent"></a>Rapportalternativ i Talent

**Miljöinformation**

Det här problemet gäller alla miljöer.

**Symptom**

Kunden vill anpassa rapporter för Microsoft Dynamics 365 Talent eller skapa nya rapporter.

**Utleverans**

Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.

**Lösning**

- Core HR-data som flödar till Common Data Service kan rapporteras via Power Apps Common Data Service-kopplingen till Power BI Desktop. Observera att Common Data Service innehåller en underuppsättning av Core HR-data. Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Talent. Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.
- Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Talent tillhandahåller genom Microsoft Office-integrationen.

**Långsiktig lösning**

Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service.
