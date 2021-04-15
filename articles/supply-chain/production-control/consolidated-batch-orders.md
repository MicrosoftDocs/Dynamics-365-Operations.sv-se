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
ms.openlocfilehash: e8d7656889b69cfd1dcffb45b52eb649bce59629
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809240"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="d5008-103">Konsoliderade batchorder</span><span class="sxs-lookup"><span data-stu-id="d5008-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5008-104">Det här avsnittet beskriver begreppet konsoliderade batchorder.</span><span class="sxs-lookup"><span data-stu-id="d5008-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="d5008-105">En bulkartikel som produceras anses vara en överordnad artikel, och en packad artikel anses vara en underordnad artikel.</span><span class="sxs-lookup"><span data-stu-id="d5008-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="d5008-106">Relationen mellan bulkartikeln och den bokförda artikeln uttrycks i en bulkartikelkonvertering.</span><span class="sxs-lookup"><span data-stu-id="d5008-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="d5008-107">Den här bulkartikelkonverteringen definieras på själva bulkartikeln.</span><span class="sxs-lookup"><span data-stu-id="d5008-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="d5008-108">Packade artiklar kan förpackas i behållare med en eller flera storlekar som anses vara en enhet.</span><span class="sxs-lookup"><span data-stu-id="d5008-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="d5008-109">Genom att konsolidera order för en bulkartikel kan du se alla relaterade batchordrar i en enda vy, vilket hjälper dig att fastställa återstående arbete som måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="d5008-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="d5008-110">En konsoliderad batchorder kan innehålla en kombination av följande order:</span><span class="sxs-lookup"><span data-stu-id="d5008-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="d5008-111">En enskild bulkorder och flera packade order</span><span class="sxs-lookup"><span data-stu-id="d5008-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="d5008-112">Flera bulkorder och flera packade order</span><span class="sxs-lookup"><span data-stu-id="d5008-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="d5008-113">Flera bulkorder och en enskild packad order</span><span class="sxs-lookup"><span data-stu-id="d5008-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="d5008-114">Enbart packade order</span><span class="sxs-lookup"><span data-stu-id="d5008-114">Only packed orders</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]