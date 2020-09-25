---
title: Exempel och logik på åldersfördelningsrapport för lager
description: I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från en åldersfördelningsrapport för lager.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759554"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="d5aeb-103">Exempel och logik på åldersfördelningsrapport för lager</span><span class="sxs-lookup"><span data-stu-id="d5aeb-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5aeb-104">I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från rapporten **åldersfördelning för lager**.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="d5aeb-105">I den här rapporten kategoriseras lagerbehållningskvantitet och lagervärden för en vald artikel eller artikelgrupp till flera periodgrupper.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="d5aeb-106">I det här avsnittet visas också rapportens interna logik.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="d5aeb-107">Exemplen i det här avsnittet visar resultat som visas i en standardrapport för **Lagerföråldring**.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="d5aeb-108">I allmänhet rekommenderar vi dock att du använder versionen [Lagring av Lagerföråldringsrapport](inventory-aging-report-storage.md) för den här rapporten, särskilt när du har många artiklar och lagerställen som måste bearbetas.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="d5aeb-109">Lagring av Lagerföråldringsrapport sparar varje rapport som du skapar, visar resultaten som en interaktiv sida och ett diagram och låter dig exportera alla sparade rapporter.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="d5aeb-110">Exempeldata som används i dessa exempel</span><span class="sxs-lookup"><span data-stu-id="d5aeb-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="d5aeb-111">Exemplen i det här avsnittet är baserade på transaktionsdata för exempellager som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="d5aeb-112">Inställningar av lagringsdimension</span><span class="sxs-lookup"><span data-stu-id="d5aeb-112">Storage dimension setup</span></span>

<span data-ttu-id="d5aeb-113">Exempelsystemet innehåller följande inställning av lagringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="d5aeb-114">Namn</span><span class="sxs-lookup"><span data-stu-id="d5aeb-114">Name</span></span>      | <span data-ttu-id="d5aeb-115">Aktiva</span><span class="sxs-lookup"><span data-stu-id="d5aeb-115">Active</span></span> | <span data-ttu-id="d5aeb-116">Fysiskt lager</span><span class="sxs-lookup"><span data-stu-id="d5aeb-116">Physical inventory</span></span> | <span data-ttu-id="d5aeb-117">Ekonomiskt lager</span><span class="sxs-lookup"><span data-stu-id="d5aeb-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="d5aeb-118">Webbplats</span><span class="sxs-lookup"><span data-stu-id="d5aeb-118">Site</span></span>      | <span data-ttu-id="d5aeb-119">Ja</span><span class="sxs-lookup"><span data-stu-id="d5aeb-119">Yes</span></span>    | <span data-ttu-id="d5aeb-120">Ja</span><span class="sxs-lookup"><span data-stu-id="d5aeb-120">Yes</span></span>                | <span data-ttu-id="d5aeb-121">Ja</span><span class="sxs-lookup"><span data-stu-id="d5aeb-121">Yes</span></span>                 |
| <span data-ttu-id="d5aeb-122">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="d5aeb-122">Warehouse</span></span> | <span data-ttu-id="d5aeb-123">Ja</span><span class="sxs-lookup"><span data-stu-id="d5aeb-123">Yes</span></span>    | <span data-ttu-id="d5aeb-124">Ja</span><span class="sxs-lookup"><span data-stu-id="d5aeb-124">Yes</span></span>                | <span data-ttu-id="d5aeb-125">Nr</span><span class="sxs-lookup"><span data-stu-id="d5aeb-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="d5aeb-126">Lagermodell</span><span class="sxs-lookup"><span data-stu-id="d5aeb-126">Inventory model</span></span>

<span data-ttu-id="d5aeb-127">För systemexemplet är lagermodellen för de frisläppta produkterna *FIFO* och inställningen **självkostnad** för lagermodellen är *inkludera fysiskt värde*.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="d5aeb-128">Lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="d5aeb-128">Inventory transactions</span></span>

<span data-ttu-id="d5aeb-129">Exempelsystemet innehåller följande lagertransaktioner för en frisläppt produkt som har artikel numret *1000*.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="d5aeb-130">Referens</span><span class="sxs-lookup"><span data-stu-id="d5aeb-130">Reference</span></span>      | <span data-ttu-id="d5aeb-131">Webbplats</span><span class="sxs-lookup"><span data-stu-id="d5aeb-131">Site</span></span> | <span data-ttu-id="d5aeb-132">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="d5aeb-132">Warehouse</span></span> | <span data-ttu-id="d5aeb-133">Inleverans</span><span class="sxs-lookup"><span data-stu-id="d5aeb-133">Receipt</span></span>   | <span data-ttu-id="d5aeb-134">Utfärda</span><span class="sxs-lookup"><span data-stu-id="d5aeb-134">Issue</span></span> | <span data-ttu-id="d5aeb-135">Fysiskt datum</span><span class="sxs-lookup"><span data-stu-id="d5aeb-135">Physical date</span></span> | <span data-ttu-id="d5aeb-136">Ekonomiskt datum</span><span class="sxs-lookup"><span data-stu-id="d5aeb-136">Financial date</span></span> | <span data-ttu-id="d5aeb-137">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-137">Quantity</span></span> | <span data-ttu-id="d5aeb-138">Kostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-138">Cost amount</span></span> | <span data-ttu-id="d5aeb-139">Fysiskt kostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="d5aeb-140">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-140">Purchase order</span></span> | <span data-ttu-id="d5aeb-141">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-141">1</span></span>    | <span data-ttu-id="d5aeb-142">11</span><span class="sxs-lookup"><span data-stu-id="d5aeb-142">11</span></span>        | <span data-ttu-id="d5aeb-143">Inköpt</span><span class="sxs-lookup"><span data-stu-id="d5aeb-143">Purchased</span></span> |       | <span data-ttu-id="d5aeb-144">15 mars</span><span class="sxs-lookup"><span data-stu-id="d5aeb-144">March 15</span></span>      | <span data-ttu-id="d5aeb-145">15 mars</span><span class="sxs-lookup"><span data-stu-id="d5aeb-145">March 15</span></span>       | <span data-ttu-id="d5aeb-146">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-146">10</span></span>       | <span data-ttu-id="d5aeb-147">1 000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-147">1,000</span></span>       | <span data-ttu-id="d5aeb-148">1 000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-148">1,000</span></span>                |
| <span data-ttu-id="d5aeb-149">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-149">Purchase order</span></span> | <span data-ttu-id="d5aeb-150">2</span><span class="sxs-lookup"><span data-stu-id="d5aeb-150">2</span></span>    | <span data-ttu-id="d5aeb-151">21</span><span class="sxs-lookup"><span data-stu-id="d5aeb-151">21</span></span>        | <span data-ttu-id="d5aeb-152">Inköpt</span><span class="sxs-lookup"><span data-stu-id="d5aeb-152">Purchased</span></span> |       | <span data-ttu-id="d5aeb-153">15 mars</span><span class="sxs-lookup"><span data-stu-id="d5aeb-153">March 15</span></span>      | <span data-ttu-id="d5aeb-154">15 mars</span><span class="sxs-lookup"><span data-stu-id="d5aeb-154">March 15</span></span>       | <span data-ttu-id="d5aeb-155">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-155">10</span></span>       | <span data-ttu-id="d5aeb-156">2,000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-156">2,000</span></span>       | <span data-ttu-id="d5aeb-157">2,000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-157">2,000</span></span>                |
| <span data-ttu-id="d5aeb-158">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-158">Purchase order</span></span> | <span data-ttu-id="d5aeb-159">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-159">1</span></span>    | <span data-ttu-id="d5aeb-160">11</span><span class="sxs-lookup"><span data-stu-id="d5aeb-160">11</span></span>        | <span data-ttu-id="d5aeb-161">Inlevererat</span><span class="sxs-lookup"><span data-stu-id="d5aeb-161">Received</span></span>  |       | <span data-ttu-id="d5aeb-162">15 april</span><span class="sxs-lookup"><span data-stu-id="d5aeb-162">April 15</span></span>      |                | <span data-ttu-id="d5aeb-163">5</span><span class="sxs-lookup"><span data-stu-id="d5aeb-163">5</span></span>        |             | <span data-ttu-id="d5aeb-164">375</span><span class="sxs-lookup"><span data-stu-id="d5aeb-164">375</span></span>                  |
| <span data-ttu-id="d5aeb-165">Överföringsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-165">Transfer order</span></span> | <span data-ttu-id="d5aeb-166">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-166">1</span></span>    | <span data-ttu-id="d5aeb-167">11</span><span class="sxs-lookup"><span data-stu-id="d5aeb-167">11</span></span>        |           | <span data-ttu-id="d5aeb-168">Sålt</span><span class="sxs-lookup"><span data-stu-id="d5aeb-168">Sold</span></span>  | <span data-ttu-id="d5aeb-169">2 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-169">May 2</span></span>         | <span data-ttu-id="d5aeb-170">2 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-170">May 2</span></span>          | <span data-ttu-id="d5aeb-171">-5</span><span class="sxs-lookup"><span data-stu-id="d5aeb-171">-5</span></span>       | <span data-ttu-id="d5aeb-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-172">-458.33</span></span>     | <span data-ttu-id="d5aeb-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-173">-458.33</span></span>              |
| <span data-ttu-id="d5aeb-174">Överföringsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-174">Transfer order</span></span> | <span data-ttu-id="d5aeb-175">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-175">1</span></span>    | <span data-ttu-id="d5aeb-176">12</span><span class="sxs-lookup"><span data-stu-id="d5aeb-176">12</span></span>        | <span data-ttu-id="d5aeb-177">Inköpt</span><span class="sxs-lookup"><span data-stu-id="d5aeb-177">Purchased</span></span> |       | <span data-ttu-id="d5aeb-178">2 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-178">May 2</span></span>         | <span data-ttu-id="d5aeb-179">2 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-179">May 2</span></span>          | <span data-ttu-id="d5aeb-180">5</span><span class="sxs-lookup"><span data-stu-id="d5aeb-180">5</span></span>        | <span data-ttu-id="d5aeb-181">458.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-181">458.33</span></span>      | <span data-ttu-id="d5aeb-182">458.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-182">458.33</span></span>               |
| <span data-ttu-id="d5aeb-183">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="d5aeb-183">Sales order</span></span>    | <span data-ttu-id="d5aeb-184">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-184">1</span></span>    | <span data-ttu-id="d5aeb-185">12</span><span class="sxs-lookup"><span data-stu-id="d5aeb-185">12</span></span>        |           | <span data-ttu-id="d5aeb-186">Sålt</span><span class="sxs-lookup"><span data-stu-id="d5aeb-186">Sold</span></span>  | <span data-ttu-id="d5aeb-187">3 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-187">May 3</span></span>         | <span data-ttu-id="d5aeb-188">3 maj</span><span class="sxs-lookup"><span data-stu-id="d5aeb-188">May 3</span></span>          | <span data-ttu-id="d5aeb-189">-1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-189">-1</span></span>       | <span data-ttu-id="d5aeb-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-190">-91.67</span></span>      | <span data-ttu-id="d5aeb-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="d5aeb-192">Hur kvantiteter och belopp i varje periodgrupp beräknas</span><span class="sxs-lookup"><span data-stu-id="d5aeb-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="d5aeb-193">Genom att använda de exempeldata som beskrivs i föregående avsnitt kan du köra en rapport **Lagerföråldring** med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d5aeb-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="d5aeb-194">**Från och med:** *9 maj 2020*</span><span class="sxs-lookup"><span data-stu-id="d5aeb-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="d5aeb-195">**plats:** *Vy*</span><span class="sxs-lookup"><span data-stu-id="d5aeb-195">**Site:** *View*</span></span>
- <span data-ttu-id="d5aeb-196">**Lagerställe:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="d5aeb-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="d5aeb-197">**Artikelnummer:** *Total*</span><span class="sxs-lookup"><span data-stu-id="d5aeb-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="d5aeb-198">**Åldersfördelningsperiod:** Ange det här fältet om du vill generera månatliga grupper.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="d5aeb-199">I det här fallet kommer innehållet i den rapport som genereras att likna följande exempel.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="d5aeb-200">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="d5aeb-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-201">Webbplats</span><span class="sxs-lookup"><span data-stu-id="d5aeb-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-202">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="d5aeb-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-203">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-204">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-205">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-206">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="d5aeb-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-207">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-208">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-209">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="d5aeb-210">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-211">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-212">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-213">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-214">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-215">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="d5aeb-216">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-216">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-217">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-217">1</span></span></td>
    <td><span data-ttu-id="d5aeb-218">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-218">14</span></span></td>
    <td><span data-ttu-id="d5aeb-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-219">1,283.33</span></span></td>
    <td><span data-ttu-id="d5aeb-220">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-220">14</span></span></td>
    <td><span data-ttu-id="d5aeb-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-221">1,283.33</span></span></td>
    <td><span data-ttu-id="d5aeb-222">91.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-223">5.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-223">5.00</span></span></td>
    <td><span data-ttu-id="d5aeb-224">458.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-224">458.33</span></span></td>
    <td><span data-ttu-id="d5aeb-225">9.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-225">9.00</span></span></td>
    <td><span data-ttu-id="d5aeb-226">825.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="d5aeb-227">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-227">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-228">2</span><span class="sxs-lookup"><span data-stu-id="d5aeb-228">2</span></span></td>
    <td><span data-ttu-id="d5aeb-229">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-229">10</span></span></td>
    <td><span data-ttu-id="d5aeb-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-230">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-231">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-231">10</span></span></td>
    <td><span data-ttu-id="d5aeb-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-232">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-233">200.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-234">10,00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-234">10.00</span></span></td>
    <td><span data-ttu-id="d5aeb-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="d5aeb-236"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="d5aeb-243">Lägg märke till följande information i exempelrapporten:</span><span class="sxs-lookup"><span data-stu-id="d5aeb-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="d5aeb-244">Värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som visas i rapporten är värden för den finansiella inventeringsdimensionen (**plats**, i detta fall).</span><span class="sxs-lookup"><span data-stu-id="d5aeb-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="d5aeb-245">För t.ex. plats 1 visar rapporten följande information:</span><span class="sxs-lookup"><span data-stu-id="d5aeb-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="d5aeb-246">Värdet för **Lagervärdets kvantitet** är *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="d5aeb-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="d5aeb-247">Värdet för **Lagervärde** är *1,283.33* (= 1,000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="d5aeb-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="d5aeb-248">Värdet för **Genomsnittlig enhetskostnad**är *91,67*.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="d5aeb-249">Värdet **Behållningsvärde** och **Belopp** i varje period grupp beräknas med hjälp av värdet **Genomsnittlig enhetskostnad**.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="d5aeb-250">Rapporten bestämmer lagerbehållningen för varje periodgrupp genom att summera den totala inlevererade lagerkvantiteten för varje periodgrupp.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="d5aeb-251">Därefter tillämpas principen först in, först ut (FIFO) för att dra av den totala utfärdade kvantiteten, oavsett vilken lagermodell som används för artiklarna.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="d5aeb-252">Om du kör samma rapport igen, men den här gången du anger båda fälten **plats** och **Lagerställe** till *Vy*, kommer den nya rapporten att likna följande exempel.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="d5aeb-253">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="d5aeb-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-254">Webbplats</span><span class="sxs-lookup"><span data-stu-id="d5aeb-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-255">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="d5aeb-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-256">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="d5aeb-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-257">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-258">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-259">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-260">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="d5aeb-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-261">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-262">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-263">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="d5aeb-264">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-265">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-266">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-267">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-268">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-269">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="d5aeb-270">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-270">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-271">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-271">1</span></span></td>
    <td><span data-ttu-id="d5aeb-272">11</span><span class="sxs-lookup"><span data-stu-id="d5aeb-272">11</span></span></td>
    <td><span data-ttu-id="d5aeb-273">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-273">10</span></span></td>
    <td><span data-ttu-id="d5aeb-274">916.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-274">916.67</span></span></td>
    <td><span data-ttu-id="d5aeb-275">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-275">14</span></span></td>
    <td><span data-ttu-id="d5aeb-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-276">1,283.33</span></span></td>
    <td><span data-ttu-id="d5aeb-277">91.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-278">5.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-278">5.00</span></span></td>
    <td><span data-ttu-id="d5aeb-279">458.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-279">458.33</span></span></td>
    <td><span data-ttu-id="d5aeb-280">5.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-280">5.00</span></span></td>
    <td><span data-ttu-id="d5aeb-281">458.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="d5aeb-282">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-282">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-283">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-283">1</span></span></td>
    <td><span data-ttu-id="d5aeb-284">12</span><span class="sxs-lookup"><span data-stu-id="d5aeb-284">12</span></span></td>
    <td><span data-ttu-id="d5aeb-285">4</span><span class="sxs-lookup"><span data-stu-id="d5aeb-285">4</span></span></td>
    <td><span data-ttu-id="d5aeb-286">366.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-286">366.67</span></span></td>
    <td><span data-ttu-id="d5aeb-287">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-287">14</span></span></td>
    <td><span data-ttu-id="d5aeb-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="d5aeb-288">1,283.33</span></span></td>
    <td><span data-ttu-id="d5aeb-289">91.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-289">91.67</span></span></td>
    <td><span data-ttu-id="d5aeb-290">4.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-290">4.00</span></span></td>
    <td><span data-ttu-id="d5aeb-291">366.67</span><span class="sxs-lookup"><span data-stu-id="d5aeb-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="d5aeb-292">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-292">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-293">2</span><span class="sxs-lookup"><span data-stu-id="d5aeb-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-294">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-294">10</span></span></td>
    <td><span data-ttu-id="d5aeb-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-295">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-296">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-296">10</span></span></td>
    <td><span data-ttu-id="d5aeb-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-297">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-298">200.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-299">10,00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-299">10.00</span></span></td>
    <td><span data-ttu-id="d5aeb-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="d5aeb-301"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="d5aeb-310">Den här gången är plats 1 uppdelad i två rader, en för lagerställe 11 och ett för lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="d5aeb-311">Men värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som är samma eftersom **Lagerställe** inte är en ekonomisk lagerdimension.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="d5aeb-312">Observera dessutom att kvantitetsfördelningen för plats 1 är annorlunda.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="d5aeb-313">I den första rapporten som du körde ignorerade systemet överföringsordern som inträffade på samma plats och dragit av kvantiteten av försäljningsfakturan från **3/31/2020-3/1/2020** periodgrupp 1 på plats 1.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="d5aeb-314">I den nya rapporten drar systemet emellertid av kvantiteten på försäljningsfakturan från **5/8/2020 - 5/1/2020** periodgrupp i lagerstället 12.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="d5aeb-315">Effekter av stängning av lager</span><span class="sxs-lookup"><span data-stu-id="d5aeb-315">Effects of inventory closing</span></span>

<span data-ttu-id="d5aeb-316">Om du kör lagerstängningen för maj och sedan kör föregående rapport igen, men ställer in fältet **Från och med** till *31 maj 2020*, kommer du att märka följande resultat:</span><span class="sxs-lookup"><span data-stu-id="d5aeb-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="d5aeb-317">**Lagervärdet** och **Genomsnittlig enhetskostnad** uppdateras.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="d5aeb-318">Värdet **Behållningsvärde** och värdena **Belopp** i varje periodgrupp uppdateras därefter.</span><span class="sxs-lookup"><span data-stu-id="d5aeb-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="d5aeb-319">Den nya rapporten liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="d5aeb-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="d5aeb-320">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="d5aeb-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-321">Webbplats</span><span class="sxs-lookup"><span data-stu-id="d5aeb-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-322">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="d5aeb-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-323">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="d5aeb-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-324">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-325">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-326">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="d5aeb-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="d5aeb-327">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="d5aeb-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-328">5/31/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-329">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="d5aeb-330">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="d5aeb-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="d5aeb-331">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-332">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-333">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-334">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="d5aeb-335">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="d5aeb-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="d5aeb-336">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="d5aeb-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="d5aeb-337">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-337">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-338">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-338">1</span></span></td>
    <td><span data-ttu-id="d5aeb-339">11</span><span class="sxs-lookup"><span data-stu-id="d5aeb-339">11</span></span></td>
    <td><span data-ttu-id="d5aeb-340">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-340">10</span></span></td>
    <td><span data-ttu-id="d5aeb-341">910.70</span><span class="sxs-lookup"><span data-stu-id="d5aeb-341">910.70</span></span></td>
    <td><span data-ttu-id="d5aeb-342">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-342">14</span></span></td>
    <td><span data-ttu-id="d5aeb-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-343">1,275.00</span></span></td>
    <td><span data-ttu-id="d5aeb-344">91.07</span><span class="sxs-lookup"><span data-stu-id="d5aeb-344">91.07</span></span></td>
    <td><span data-ttu-id="d5aeb-345">0,00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-346">5.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-346">5.00</span></span></td>
    <td><span data-ttu-id="d5aeb-347">455.36</span><span class="sxs-lookup"><span data-stu-id="d5aeb-347">455.36</span></span></td>
    <td><span data-ttu-id="d5aeb-348">5.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-348">5.00</span></span></td>
    <td><span data-ttu-id="d5aeb-349">455.36</span><span class="sxs-lookup"><span data-stu-id="d5aeb-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="d5aeb-350">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-350">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-351">1</span><span class="sxs-lookup"><span data-stu-id="d5aeb-351">1</span></span></td>
    <td><span data-ttu-id="d5aeb-352">12</span><span class="sxs-lookup"><span data-stu-id="d5aeb-352">12</span></span></td>
    <td><span data-ttu-id="d5aeb-353">4</span><span class="sxs-lookup"><span data-stu-id="d5aeb-353">4</span></span></td>
    <td><span data-ttu-id="d5aeb-354">364.29</span><span class="sxs-lookup"><span data-stu-id="d5aeb-354">364.29</span></span></td>
    <td><span data-ttu-id="d5aeb-355">14</span><span class="sxs-lookup"><span data-stu-id="d5aeb-355">14</span></span></td>
    <td><span data-ttu-id="d5aeb-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-356">1,275.00</span></span></td>
    <td><span data-ttu-id="d5aeb-357">91.07</span><span class="sxs-lookup"><span data-stu-id="d5aeb-357">91.07</span></span></td>
    <td><span data-ttu-id="d5aeb-358">4.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-358">4.00</span></span></td>
    <td><span data-ttu-id="d5aeb-359">364.29</span><span class="sxs-lookup"><span data-stu-id="d5aeb-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="d5aeb-360">1000</span><span class="sxs-lookup"><span data-stu-id="d5aeb-360">1000</span></span></td>
    <td><span data-ttu-id="d5aeb-361">2</span><span class="sxs-lookup"><span data-stu-id="d5aeb-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-362">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-362">10</span></span></td>
    <td><span data-ttu-id="d5aeb-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-363">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-364">10</span><span class="sxs-lookup"><span data-stu-id="d5aeb-364">10</span></span></td>
    <td><span data-ttu-id="d5aeb-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-365">2,000.00</span></span></td>
    <td><span data-ttu-id="d5aeb-366">200.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-367">10,00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-367">10.00</span></span></td>
    <td><span data-ttu-id="d5aeb-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="d5aeb-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="d5aeb-369"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="d5aeb-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="d5aeb-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="d5aeb-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
