---
title: Konsoliderade batchorder
description: Det här avsnittet beskriver begreppet konsoliderade batchorder.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 090536b31856d3ba848d864ec193a33ae1e502508961a2d2853aa97f98b025e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744736"
---
# <a name="consolidated-batch-orders"></a>Konsoliderade batchorder

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver begreppet konsoliderade batchorder.

En bulkartikel som produceras anses vara en överordnad artikel, och en packad artikel anses vara en underordnad artikel. Relationen mellan bulkartikeln och den bokförda artikeln uttrycks i en bulkartikelkonvertering. Den här bulkartikelkonverteringen definieras på själva bulkartikeln.  

Packade artiklar kan förpackas i behållare med en eller flera storlekar som anses vara en enhet. Genom att konsolidera order för en bulkartikel kan du se alla relaterade batchordrar i en enda vy, vilket hjälper dig att fastställa återstående arbete som måste slutföras.  

En konsoliderad batchorder kan innehålla en kombination av följande order:

-   En enskild bulkorder och flera packade order
-   Flera bulkorder och flera packade order
-   Flera bulkorder och en enskild packad order
-   Enbart packade order






[!INCLUDE[footer-include](../../includes/footer-banner.md)]