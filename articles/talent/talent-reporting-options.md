---
title: Rapportalternativ i Talent
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 for Talent eller skapa nya rapporter.
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
ms.openlocfilehash: 7e00a6e4fc01f72e1ef2347e08754997135215ed
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/12/2019
ms.locfileid: "950069"
---
# <a name="reporting-options-in-talent"></a>Rapportalternativ i Talent

[!include [banner](includes/banner.md)]

**Miljöinformation**

Det här problemet gäller alla miljöer.

**Symptom**

Kunden vill anpassa rapporter för Microsoft Dynamics 365 for Talent eller skapa nya rapporter.

**Utleverans**

Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.

**Lösning**

- Core HR-data som flödar till Common Data Service kan rapporteras via PowerApps Common Data Service-kopplingen till Power BI Desktop. Observera att Common Data Service innehåller en underuppsättning av Core HR-data. Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Talent. Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.
- Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Talent tillhandahåller genom Microsoft Office-integrationen.

**Långsiktig lösning**

Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service.
