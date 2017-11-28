---
title: "Gemensamma källor till produktionsavvikelser"
description: "Det här avsnittet beskriver olika typiska källor till varje typ av produktionsavvikelse."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f8eea27edaa97150ceb2c36996177395cba8bdb9
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="common-sources-of-production-variances"></a>Gemensamma källor till produktionsavvikelser

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver olika typiska källor till varje typ av produktionsavvikelse. 

Nedan följer några typiska källor till en avvikelse i **partistorlek**:

-   Den godkända kvantiteten för en tillverkningsorder avviker från den beräknade kvantitet som används i standardkostnadsberäkningen. Kvantiteten ligger till grund för periodiseringen av konstanta kostnader.
-   Värdet av de konstanta kostnaderna på produktionsordern avviker från de konstanta kostnader som används i standardkostnadsberäkningen. De konstanta kostnaderna på produktionsordern kan avvika av flera skäl. Exempelvis kan de konstanta kostnaderna avspegla följande faktorer:
    -   Manuella ändringar av produktionsstrukturlistan (BOM) eller flödet
    -   Valet av en annan strukturlisteversion eller flödesversion när produktionsordern skapas
    -   Planerade teknikändringar till den strukturlisteversion eller flödesversion som har tilldelats till artikeln

Nedan följer några typiska källor till en avvikelse i **produktionspris**:

-   Kostnadskategorin (och dess kostnadskategoripris) för den rapporterade förbrukningen av en flödesåtgärd avviker från den kostnadskategori som används i standardkostnadsberäkningen.
-   Den aktiva kostnaden för kostnadskategoripriset avviker från det kostnadskategoripris som används i standardkostnadsberäkningen.

Nedan följer några typiska källor till en avvikelse i **produktionskvantitet**:

-   Över- eller underuttag av en materialkomponent.
-   Över- eller underrapportering av tid för en flödesåtgärd.
-   Du tar emot mer eller mindre av den godkända kvantiteten av den överordnade artikeln i relation till orderkvantiteten. Du utfärdar dock komponenter och rapporteringsoperationer fullständigt, baserat på orderkvantiteten för produktionsordern.

Nedan följer några typiska källor till en avvikelse i **produktionsersättning**:

-   Uttag av en materialkomponent som inte finns i produktionsstrukturlistan.
-   Manuellt tillägg av en komponent i produktionsstrukturlistan och rapportering av den komponenten som förbrukad.
-   Rapportering av en artikel som förbrukad utan att den läggs till manuellt i produktionsstrukturlistan.
-   Manuellt tillägg av en åtgärd i produktionsflödet och rapportering av den åtgärden som förbrukad.
-   Vid skapandet av en produktionsorder väljer du en strukturlisteversionen som avviker från den som används i standardkostnadsberäkningen.
-   Vid skapandet av produktionsordern väljer du en flödesversionen som avviker från den flödesversion som används i standardkostnadsberäkningen.





