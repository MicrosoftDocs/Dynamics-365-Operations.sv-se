---
title: Värden för lagerobjekt
description: Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a55b1068835f1e050110c57e6af3340a018ff31
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187780"
---
# <a name="inventory-object-values"></a><span data-ttu-id="03d8a-103">Värden för lagerobjekt</span><span class="sxs-lookup"><span data-stu-id="03d8a-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03d8a-104">Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas.</span><span class="sxs-lookup"><span data-stu-id="03d8a-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="03d8a-105">En ny funktion med namnet, **fysisk kvantitet** visar värdena för ett visst lagerobjekt.</span><span class="sxs-lookup"><span data-stu-id="03d8a-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="03d8a-106">Ett kostnadsobjekt representerar enhetsnivån där lagerredovisning utförs.</span><span class="sxs-lookup"><span data-stu-id="03d8a-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="03d8a-107">Mer information om kostnadsobjekt finns i [Kostnadsobjekt](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="03d8a-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="03d8a-108">För att visa värdena för ett visst lagerobjekt, klicka på **Fysisk kvantitet** på sidan **Kostnadsobjekt**.</span><span class="sxs-lookup"><span data-stu-id="03d8a-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="03d8a-109">Här visas hur värdet för ett lagerobjekt beräknas:</span><span class="sxs-lookup"><span data-stu-id="03d8a-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="03d8a-110">Lagerobjekt på lager. Värde = kostnadsobjekt. Genomsnittlig enhetskostnad × lagerobjekt. Kvantitet</span><span class="sxs-lookup"><span data-stu-id="03d8a-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="03d8a-111">Följande exempel visar hur värdena beräknas för ett objekt i lagret och en kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="03d8a-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="03d8a-112">Två produktinleveranshändelser registreras på artikel A:</span><span class="sxs-lookup"><span data-stu-id="03d8a-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="03d8a-113">Produktinleverans 1: Kvantitet = 100 st., Belopp = 1 000,00 USD, Plats = 1, Lagerställe =11, Buntnr.</span><span class="sxs-lookup"><span data-stu-id="03d8a-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="03d8a-114">= B1</span><span class="sxs-lookup"><span data-stu-id="03d8a-114">= B1</span></span>
-   <span data-ttu-id="03d8a-115">Produktinleverans 2: Kvantitet = 50 st., Belopp = 800,00 USD, Plats = 1, Lagerställe =11, Buntnr.</span><span class="sxs-lookup"><span data-stu-id="03d8a-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="03d8a-116">= B2</span><span class="sxs-lookup"><span data-stu-id="03d8a-116">= B2</span></span>

<span data-ttu-id="03d8a-117">Följande tabell visar beräkningsresultatet för ett kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="03d8a-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="03d8a-118">Du kan visa resultaten på sidan **Kostnadsobjekt**.</span><span class="sxs-lookup"><span data-stu-id="03d8a-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03d8a-119">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="03d8a-119">Object type</span></span></th>
<th><span data-ttu-id="03d8a-120">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="03d8a-120">Item number</span></span></th>
<th><span data-ttu-id="03d8a-121">Plats</span><span class="sxs-lookup"><span data-stu-id="03d8a-121">Site</span></span></th>
<th><span data-ttu-id="03d8a-122">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="03d8a-122">Quantity</span></span></th>
<th><span data-ttu-id="03d8a-123">Lagerenhet</span><span class="sxs-lookup"><span data-stu-id="03d8a-123">Inventory unit</span></span></th>
<th><span data-ttu-id="03d8a-124">Värde</span><span class="sxs-lookup"><span data-stu-id="03d8a-124">Value</span></span></th>
<th><span data-ttu-id="03d8a-125">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="03d8a-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="03d8a-126">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="03d8a-126">Cost object</span></span></td>
<td><span data-ttu-id="03d8a-127">A</span><span class="sxs-lookup"><span data-stu-id="03d8a-127">A</span></span></td>
<td><span data-ttu-id="03d8a-128">1</span><span class="sxs-lookup"><span data-stu-id="03d8a-128">1</span></span></td>
<td><span data-ttu-id="03d8a-129">150</span><span class="sxs-lookup"><span data-stu-id="03d8a-129">150</span></span></td>
<td><span data-ttu-id="03d8a-130">Stk.</span><span class="sxs-lookup"><span data-stu-id="03d8a-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="03d8a-131">1800,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="03d8a-132">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03d8a-133">Följande tabell visar beräkningsresultatet för ett lagerobjekt.</span><span class="sxs-lookup"><span data-stu-id="03d8a-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="03d8a-134">Du kan visa resultaten genom att klicka på **Fysisk kvantitet** på sidan **Kostnadsobjekt**.</span><span class="sxs-lookup"><span data-stu-id="03d8a-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03d8a-135">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="03d8a-135">Object type</span></span></th>
<th><span data-ttu-id="03d8a-136">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="03d8a-136">Item number</span></span></th>
<th><span data-ttu-id="03d8a-137">Plats</span><span class="sxs-lookup"><span data-stu-id="03d8a-137">Site</span></span></th>
<th><span data-ttu-id="03d8a-138">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="03d8a-138">Warehouse</span></span></th>
<th><span data-ttu-id="03d8a-139">Buntnr.</span><span class="sxs-lookup"><span data-stu-id="03d8a-139">Batch No.</span></span></th>
<th><span data-ttu-id="03d8a-140">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="03d8a-140">Quantity</span></span></th>
<th><span data-ttu-id="03d8a-141">Lagerenhet</span><span class="sxs-lookup"><span data-stu-id="03d8a-141">Inventory unit</span></span></th>
<th><span data-ttu-id="03d8a-142">Värde</span><span class="sxs-lookup"><span data-stu-id="03d8a-142">Value</span></span></th>
<th><span data-ttu-id="03d8a-143">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="03d8a-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="03d8a-144">Lagerobjekt</span><span class="sxs-lookup"><span data-stu-id="03d8a-144">Inventory object</span></span></td>
<td><span data-ttu-id="03d8a-145">A</span><span class="sxs-lookup"><span data-stu-id="03d8a-145">A</span></span></td>
<td><span data-ttu-id="03d8a-146">1</span><span class="sxs-lookup"><span data-stu-id="03d8a-146">1</span></span></td>
<td><span data-ttu-id="03d8a-147">11</span><span class="sxs-lookup"><span data-stu-id="03d8a-147">11</span></span></td>
<td><span data-ttu-id="03d8a-148">B1</span><span class="sxs-lookup"><span data-stu-id="03d8a-148">B1</span></span></td>
<td><span data-ttu-id="03d8a-149">100</span><span class="sxs-lookup"><span data-stu-id="03d8a-149">100</span></span></td>
<td><span data-ttu-id="03d8a-150">Stk.</span><span class="sxs-lookup"><span data-stu-id="03d8a-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="03d8a-151">1200,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="03d8a-152">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="03d8a-153">Lagerobjekt</span><span class="sxs-lookup"><span data-stu-id="03d8a-153">Inventory object</span></span></td>
<td><span data-ttu-id="03d8a-154">A</span><span class="sxs-lookup"><span data-stu-id="03d8a-154">A</span></span></td>
<td><span data-ttu-id="03d8a-155">1</span><span class="sxs-lookup"><span data-stu-id="03d8a-155">1</span></span></td>
<td><span data-ttu-id="03d8a-156">11</span><span class="sxs-lookup"><span data-stu-id="03d8a-156">11</span></span></td>
<td><span data-ttu-id="03d8a-157">B2</span><span class="sxs-lookup"><span data-stu-id="03d8a-157">B2</span></span></td>
<td><span data-ttu-id="03d8a-158">50</span><span class="sxs-lookup"><span data-stu-id="03d8a-158">50</span></span></td>
<td><span data-ttu-id="03d8a-159">Stk.</span><span class="sxs-lookup"><span data-stu-id="03d8a-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="03d8a-160">600,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="03d8a-161">12,00 USD</span><span class="sxs-lookup"><span data-stu-id="03d8a-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



## <a name="additional-resources"></a><span data-ttu-id="03d8a-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="03d8a-162">Additional resources</span></span>

[<span data-ttu-id="03d8a-163">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="03d8a-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="03d8a-164">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="03d8a-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="03d8a-165">Nyheter och ändringar</span><span class="sxs-lookup"><span data-stu-id="03d8a-165">What's new and changed</span></span>](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]