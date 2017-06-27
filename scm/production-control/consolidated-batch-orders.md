---
title: Konsoliderade batchorder
description: "Det här avsnittet beskriver begreppet konsoliderade batchorder."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 45c83752b4dc50a615e3bb64320cb22b7fc6dec0
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="consolidated-batch-orders"></a>Konsoliderade batchorder

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver begreppet konsoliderade batchorder.

En bulkartikel som produceras anses vara en överordnad artikel, och en packad artikel anses vara en underordnad artikel. Relationen mellan bulkartikeln och den bokförda artikeln uttrycks i en bulkartikelkonvertering. Den här bulkartikelkonverteringen definieras på själva bulkartikeln.  

Packade artiklar kan förpackas i behållare med en eller flera storlekar som anses vara en enhet. Genom att konsolidera order för en bulkartikel kan du se alla relaterade batchordrar i en enda vy, vilket hjälper dig att fastställa återstående arbete som måste slutföras.  

En konsoliderad batchorder kan innehålla en kombination av följande order:

-   En enskild bulkorder och flera packade order
-   Flera bulkorder och flera packade order
-   Flera bulkorder och en enskild packad order
-   Enbart packade order





