---
title: Konsoliderade batchorder
description: Det här avsnittet beskriver begreppet konsoliderade batchorder.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49c2df19168855e6e6ab9ff061bcdce698947b20
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "358817"
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




