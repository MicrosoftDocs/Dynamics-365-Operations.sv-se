---
title: Rapporteringsalternativ
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64a03724d81745373d028d76a8cc64aab66efdbb
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053309"
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
- Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Personal tillhandahåller genom Microsoft Office-integrationen.

**Långsiktig lösning**

Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]