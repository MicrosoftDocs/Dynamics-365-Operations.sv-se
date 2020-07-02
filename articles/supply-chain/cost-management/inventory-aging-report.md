---
title: Exempel och logik på åldersfördelningsrapport för lager
description: I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från en åldersfördelningsrapport för lager.
author: RichardLuan
manager: AnnBe
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6c165599c11b84e4064a9303d8b1f59558fc6b9d
ms.sourcegitcommit: 6bf8602333191e5161ba3a9ceecf160c85ff7e79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "3484540"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="40ae3-103">Exempel och logik på åldersfördelningsrapport för lager</span><span class="sxs-lookup"><span data-stu-id="40ae3-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40ae3-104">I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från rapporten **åldersfördelning för lager**.</span><span class="sxs-lookup"><span data-stu-id="40ae3-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="40ae3-105">I den här rapporten kategoriseras lagerbehållningskvantitet och lagervärden för en vald artikel eller artikelgrupp till flera periodgrupper.</span><span class="sxs-lookup"><span data-stu-id="40ae3-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="40ae3-106">I det här avsnittet visas också rapportens interna logik.</span><span class="sxs-lookup"><span data-stu-id="40ae3-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="40ae3-107">Exemplen i det här avsnittet visar resultat som visas i en standardrapport för **Lagerföråldring**.</span><span class="sxs-lookup"><span data-stu-id="40ae3-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="40ae3-108">I allmänhet rekommenderar vi dock att du använder versionen [Lagring av Lagerföråldringsrapport](inventory-aging-report-storage.md) för den här rapporten, särskilt när du har många artiklar och lagerställen som måste bearbetas.</span><span class="sxs-lookup"><span data-stu-id="40ae3-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="40ae3-109">Lagring av Lagerföråldringsrapport sparar varje rapport som du skapar, visar resultaten som en interaktiv sida och ett diagram och låter dig exportera alla sparade rapporter.</span><span class="sxs-lookup"><span data-stu-id="40ae3-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="40ae3-110">Exempeldata som används i dessa exempel</span><span class="sxs-lookup"><span data-stu-id="40ae3-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="40ae3-111">Exemplen i det här avsnittet är baserade på transaktionsdata för exempellager som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="40ae3-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="40ae3-112">Inställningar av lagringsdimension</span><span class="sxs-lookup"><span data-stu-id="40ae3-112">Storage dimension setup</span></span>

<span data-ttu-id="40ae3-113">Exempelsystemet innehåller följande inställning av lagringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="40ae3-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="40ae3-114">Namn</span><span class="sxs-lookup"><span data-stu-id="40ae3-114">Name</span></span>      | <span data-ttu-id="40ae3-115">Aktiva</span><span class="sxs-lookup"><span data-stu-id="40ae3-115">Active</span></span> | <span data-ttu-id="40ae3-116">Fysiskt lager</span><span class="sxs-lookup"><span data-stu-id="40ae3-116">Physical inventory</span></span> | <span data-ttu-id="40ae3-117">Ekonomiskt lager</span><span class="sxs-lookup"><span data-stu-id="40ae3-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="40ae3-118">Webbplats</span><span class="sxs-lookup"><span data-stu-id="40ae3-118">Site</span></span>      | <span data-ttu-id="40ae3-119">Ja</span><span class="sxs-lookup"><span data-stu-id="40ae3-119">Yes</span></span>    | <span data-ttu-id="40ae3-120">Ja</span><span class="sxs-lookup"><span data-stu-id="40ae3-120">Yes</span></span>                | <span data-ttu-id="40ae3-121">Ja</span><span class="sxs-lookup"><span data-stu-id="40ae3-121">Yes</span></span>                 |
| <span data-ttu-id="40ae3-122">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="40ae3-122">Warehouse</span></span> | <span data-ttu-id="40ae3-123">Ja</span><span class="sxs-lookup"><span data-stu-id="40ae3-123">Yes</span></span>    | <span data-ttu-id="40ae3-124">Ja</span><span class="sxs-lookup"><span data-stu-id="40ae3-124">Yes</span></span>                | <span data-ttu-id="40ae3-125">Nr</span><span class="sxs-lookup"><span data-stu-id="40ae3-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="40ae3-126">Lagermodell</span><span class="sxs-lookup"><span data-stu-id="40ae3-126">Inventory model</span></span>

<span data-ttu-id="40ae3-127">För systemexemplet är lagermodellen för de frisläppta produkterna *FIFO* och inställningen **självkostnad** för lagermodellen är *inkludera fysiskt värde*.</span><span class="sxs-lookup"><span data-stu-id="40ae3-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="40ae3-128">Lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="40ae3-128">Inventory transactions</span></span>

<span data-ttu-id="40ae3-129">Exempelsystemet innehåller följande lagertransaktioner för en frisläppt produkt som har artikel numret *1000*.</span><span class="sxs-lookup"><span data-stu-id="40ae3-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="40ae3-130">Referens</span><span class="sxs-lookup"><span data-stu-id="40ae3-130">Reference</span></span>      | <span data-ttu-id="40ae3-131">Webbplats</span><span class="sxs-lookup"><span data-stu-id="40ae3-131">Site</span></span> | <span data-ttu-id="40ae3-132">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="40ae3-132">Warehouse</span></span> | <span data-ttu-id="40ae3-133">Inleverans</span><span class="sxs-lookup"><span data-stu-id="40ae3-133">Receipt</span></span>   | <span data-ttu-id="40ae3-134">Utfärda</span><span class="sxs-lookup"><span data-stu-id="40ae3-134">Issue</span></span> | <span data-ttu-id="40ae3-135">Fysiskt datum</span><span class="sxs-lookup"><span data-stu-id="40ae3-135">Physical date</span></span> | <span data-ttu-id="40ae3-136">Ekonomiskt datum</span><span class="sxs-lookup"><span data-stu-id="40ae3-136">Financial date</span></span> | <span data-ttu-id="40ae3-137">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-137">Quantity</span></span> | <span data-ttu-id="40ae3-138">Kostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-138">Cost amount</span></span> | <span data-ttu-id="40ae3-139">Fysiskt kostnadsbelopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="40ae3-140">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-140">Purchase order</span></span> | <span data-ttu-id="40ae3-141">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-141">1</span></span>    | <span data-ttu-id="40ae3-142">11</span><span class="sxs-lookup"><span data-stu-id="40ae3-142">11</span></span>        | <span data-ttu-id="40ae3-143">Inköpt</span><span class="sxs-lookup"><span data-stu-id="40ae3-143">Purchased</span></span> |       | <span data-ttu-id="40ae3-144">15 mars</span><span class="sxs-lookup"><span data-stu-id="40ae3-144">March 15</span></span>      | <span data-ttu-id="40ae3-145">15 mars</span><span class="sxs-lookup"><span data-stu-id="40ae3-145">March 15</span></span>       | <span data-ttu-id="40ae3-146">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-146">10</span></span>       | <span data-ttu-id="40ae3-147">1 000</span><span class="sxs-lookup"><span data-stu-id="40ae3-147">1,000</span></span>       | <span data-ttu-id="40ae3-148">1 000</span><span class="sxs-lookup"><span data-stu-id="40ae3-148">1,000</span></span>                |
| <span data-ttu-id="40ae3-149">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-149">Purchase order</span></span> | <span data-ttu-id="40ae3-150">2</span><span class="sxs-lookup"><span data-stu-id="40ae3-150">2</span></span>    | <span data-ttu-id="40ae3-151">21</span><span class="sxs-lookup"><span data-stu-id="40ae3-151">21</span></span>        | <span data-ttu-id="40ae3-152">Inköpt</span><span class="sxs-lookup"><span data-stu-id="40ae3-152">Purchased</span></span> |       | <span data-ttu-id="40ae3-153">15 mars</span><span class="sxs-lookup"><span data-stu-id="40ae3-153">March 15</span></span>      | <span data-ttu-id="40ae3-154">15 mars</span><span class="sxs-lookup"><span data-stu-id="40ae3-154">March 15</span></span>       | <span data-ttu-id="40ae3-155">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-155">10</span></span>       | <span data-ttu-id="40ae3-156">2,000</span><span class="sxs-lookup"><span data-stu-id="40ae3-156">2,000</span></span>       | <span data-ttu-id="40ae3-157">2,000</span><span class="sxs-lookup"><span data-stu-id="40ae3-157">2,000</span></span>                |
| <span data-ttu-id="40ae3-158">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-158">Purchase order</span></span> | <span data-ttu-id="40ae3-159">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-159">1</span></span>    | <span data-ttu-id="40ae3-160">11</span><span class="sxs-lookup"><span data-stu-id="40ae3-160">11</span></span>        | <span data-ttu-id="40ae3-161">Inlevererat</span><span class="sxs-lookup"><span data-stu-id="40ae3-161">Received</span></span>  |       | <span data-ttu-id="40ae3-162">15 april</span><span class="sxs-lookup"><span data-stu-id="40ae3-162">April 15</span></span>      |                | <span data-ttu-id="40ae3-163">5</span><span class="sxs-lookup"><span data-stu-id="40ae3-163">5</span></span>        |             | <span data-ttu-id="40ae3-164">375</span><span class="sxs-lookup"><span data-stu-id="40ae3-164">375</span></span>                  |
| <span data-ttu-id="40ae3-165">Överföringsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-165">Transfer order</span></span> | <span data-ttu-id="40ae3-166">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-166">1</span></span>    | <span data-ttu-id="40ae3-167">11</span><span class="sxs-lookup"><span data-stu-id="40ae3-167">11</span></span>        |           | <span data-ttu-id="40ae3-168">Sålt</span><span class="sxs-lookup"><span data-stu-id="40ae3-168">Sold</span></span>  | <span data-ttu-id="40ae3-169">2 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-169">May 2</span></span>         | <span data-ttu-id="40ae3-170">2 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-170">May 2</span></span>          | <span data-ttu-id="40ae3-171">-5</span><span class="sxs-lookup"><span data-stu-id="40ae3-171">-5</span></span>       | <span data-ttu-id="40ae3-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="40ae3-172">-458.33</span></span>     | <span data-ttu-id="40ae3-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="40ae3-173">-458.33</span></span>              |
| <span data-ttu-id="40ae3-174">Överföringsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-174">Transfer order</span></span> | <span data-ttu-id="40ae3-175">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-175">1</span></span>    | <span data-ttu-id="40ae3-176">12</span><span class="sxs-lookup"><span data-stu-id="40ae3-176">12</span></span>        | <span data-ttu-id="40ae3-177">Inköpt</span><span class="sxs-lookup"><span data-stu-id="40ae3-177">Purchased</span></span> |       | <span data-ttu-id="40ae3-178">2 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-178">May 2</span></span>         | <span data-ttu-id="40ae3-179">2 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-179">May 2</span></span>          | <span data-ttu-id="40ae3-180">5</span><span class="sxs-lookup"><span data-stu-id="40ae3-180">5</span></span>        | <span data-ttu-id="40ae3-181">458.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-181">458.33</span></span>      | <span data-ttu-id="40ae3-182">458.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-182">458.33</span></span>               |
| <span data-ttu-id="40ae3-183">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="40ae3-183">Sales order</span></span>    | <span data-ttu-id="40ae3-184">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-184">1</span></span>    | <span data-ttu-id="40ae3-185">12</span><span class="sxs-lookup"><span data-stu-id="40ae3-185">12</span></span>        |           | <span data-ttu-id="40ae3-186">Sålt</span><span class="sxs-lookup"><span data-stu-id="40ae3-186">Sold</span></span>  | <span data-ttu-id="40ae3-187">3 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-187">May 3</span></span>         | <span data-ttu-id="40ae3-188">3 maj</span><span class="sxs-lookup"><span data-stu-id="40ae3-188">May 3</span></span>          | <span data-ttu-id="40ae3-189">-1</span><span class="sxs-lookup"><span data-stu-id="40ae3-189">-1</span></span>       | <span data-ttu-id="40ae3-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="40ae3-190">-91.67</span></span>      | <span data-ttu-id="40ae3-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="40ae3-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="40ae3-192">Hur kvantiteter och belopp i varje periodgrupp beräknas</span><span class="sxs-lookup"><span data-stu-id="40ae3-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="40ae3-193">Genom att använda de exempeldata som beskrivs i föregående avsnitt kan du köra en rapport **Lagerföråldring** med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="40ae3-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="40ae3-194">**Från och med:** *9 maj 2020*</span><span class="sxs-lookup"><span data-stu-id="40ae3-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="40ae3-195">**plats:** *Vy*</span><span class="sxs-lookup"><span data-stu-id="40ae3-195">**Site:** *View*</span></span>
- <span data-ttu-id="40ae3-196">**Lagerställe:** *Nej*</span><span class="sxs-lookup"><span data-stu-id="40ae3-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="40ae3-197">**Artikelnummer:** *Total*</span><span class="sxs-lookup"><span data-stu-id="40ae3-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="40ae3-198">**Åldersfördelningsperiod:** Ange det här fältet om du vill generera månatliga grupper.</span><span class="sxs-lookup"><span data-stu-id="40ae3-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="40ae3-199">I det här fallet kommer innehållet i den rapport som genereras att likna följande exempel.</span><span class="sxs-lookup"><span data-stu-id="40ae3-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="40ae3-200">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="40ae3-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-201">Webbplats</span><span class="sxs-lookup"><span data-stu-id="40ae3-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-202">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="40ae3-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-203">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-204">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-205">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-206">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="40ae3-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-207">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-208">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-209">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="40ae3-210">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-211">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-212">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-213">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-214">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-215">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="40ae3-216">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-216">1000</span></span></td>
    <td><span data-ttu-id="40ae3-217">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-217">1</span></span></td>
    <td><span data-ttu-id="40ae3-218">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-218">14</span></span></td>
    <td><span data-ttu-id="40ae3-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-219">1,283.33</span></span></td>
    <td><span data-ttu-id="40ae3-220">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-220">14</span></span></td>
    <td><span data-ttu-id="40ae3-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-221">1,283.33</span></span></td>
    <td><span data-ttu-id="40ae3-222">91.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-223">5.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-223">5.00</span></span></td>
    <td><span data-ttu-id="40ae3-224">458.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-224">458.33</span></span></td>
    <td><span data-ttu-id="40ae3-225">9.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-225">9.00</span></span></td>
    <td><span data-ttu-id="40ae3-226">825.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="40ae3-227">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-227">1000</span></span></td>
    <td><span data-ttu-id="40ae3-228">2</span><span class="sxs-lookup"><span data-stu-id="40ae3-228">2</span></span></td>
    <td><span data-ttu-id="40ae3-229">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-229">10</span></span></td>
    <td><span data-ttu-id="40ae3-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-230">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-231">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-231">10</span></span></td>
    <td><span data-ttu-id="40ae3-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-232">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-233">200.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-234">10,00</span><span class="sxs-lookup"><span data-stu-id="40ae3-234">10.00</span></span></td>
    <td><span data-ttu-id="40ae3-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="40ae3-236"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="40ae3-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="40ae3-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="40ae3-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="40ae3-243">Lägg märke till följande information i exempelrapporten:</span><span class="sxs-lookup"><span data-stu-id="40ae3-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="40ae3-244">Värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som visas i rapporten är värden för den finansiella inventeringsdimensionen (**plats**, i detta fall).</span><span class="sxs-lookup"><span data-stu-id="40ae3-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="40ae3-245">För t.ex. plats 1 visar rapporten följande information:</span><span class="sxs-lookup"><span data-stu-id="40ae3-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="40ae3-246">Värdet för **Lagervärdets kvantitet** är *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="40ae3-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="40ae3-247">Värdet för **Lagervärde** är *1,283.33* (= 1,000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="40ae3-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="40ae3-248">Värdet för **Genomsnittlig enhetskostnad**är *91,67*.</span><span class="sxs-lookup"><span data-stu-id="40ae3-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="40ae3-249">Värdet **Behållningsvärde** och **Belopp** i varje period grupp beräknas med hjälp av värdet **Genomsnittlig enhetskostnad**.</span><span class="sxs-lookup"><span data-stu-id="40ae3-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="40ae3-250">Rapporten bestämmer lagerbehållningen för varje periodgrupp genom att summera den totala inlevererade lagerkvantiteten för varje periodgrupp.</span><span class="sxs-lookup"><span data-stu-id="40ae3-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="40ae3-251">Därefter tillämpas principen först in, först ut (FIFO) för att dra av den totala utfärdade kvantiteten, oavsett vilken lagermodell som används för artiklarna.</span><span class="sxs-lookup"><span data-stu-id="40ae3-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="40ae3-252">Om du kör samma rapport igen, men den här gången du anger båda fälten **plats** och **Lagerställe** till *Vy*, kommer den nya rapporten att likna följande exempel.</span><span class="sxs-lookup"><span data-stu-id="40ae3-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="40ae3-253">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="40ae3-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-254">Webbplats</span><span class="sxs-lookup"><span data-stu-id="40ae3-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-255">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="40ae3-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-256">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="40ae3-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-257">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-258">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-259">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-260">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="40ae3-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-261">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-262">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-263">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="40ae3-264">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-265">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-266">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-267">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-268">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-269">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="40ae3-270">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-270">1000</span></span></td>
    <td><span data-ttu-id="40ae3-271">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-271">1</span></span></td>
    <td><span data-ttu-id="40ae3-272">11</span><span class="sxs-lookup"><span data-stu-id="40ae3-272">11</span></span></td>
    <td><span data-ttu-id="40ae3-273">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-273">10</span></span></td>
    <td><span data-ttu-id="40ae3-274">916.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-274">916.67</span></span></td>
    <td><span data-ttu-id="40ae3-275">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-275">14</span></span></td>
    <td><span data-ttu-id="40ae3-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-276">1,283.33</span></span></td>
    <td><span data-ttu-id="40ae3-277">91.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-278">5.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-278">5.00</span></span></td>
    <td><span data-ttu-id="40ae3-279">458.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-279">458.33</span></span></td>
    <td><span data-ttu-id="40ae3-280">5.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-280">5.00</span></span></td>
    <td><span data-ttu-id="40ae3-281">458.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="40ae3-282">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-282">1000</span></span></td>
    <td><span data-ttu-id="40ae3-283">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-283">1</span></span></td>
    <td><span data-ttu-id="40ae3-284">12</span><span class="sxs-lookup"><span data-stu-id="40ae3-284">12</span></span></td>
    <td><span data-ttu-id="40ae3-285">4</span><span class="sxs-lookup"><span data-stu-id="40ae3-285">4</span></span></td>
    <td><span data-ttu-id="40ae3-286">366.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-286">366.67</span></span></td>
    <td><span data-ttu-id="40ae3-287">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-287">14</span></span></td>
    <td><span data-ttu-id="40ae3-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="40ae3-288">1,283.33</span></span></td>
    <td><span data-ttu-id="40ae3-289">91.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-289">91.67</span></span></td>
    <td><span data-ttu-id="40ae3-290">4.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-290">4.00</span></span></td>
    <td><span data-ttu-id="40ae3-291">366.67</span><span class="sxs-lookup"><span data-stu-id="40ae3-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="40ae3-292">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-292">1000</span></span></td>
    <td><span data-ttu-id="40ae3-293">2</span><span class="sxs-lookup"><span data-stu-id="40ae3-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="40ae3-294">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-294">10</span></span></td>
    <td><span data-ttu-id="40ae3-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-295">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-296">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-296">10</span></span></td>
    <td><span data-ttu-id="40ae3-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-297">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-298">200.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-299">10,00</span><span class="sxs-lookup"><span data-stu-id="40ae3-299">10.00</span></span></td>
    <td><span data-ttu-id="40ae3-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="40ae3-301"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="40ae3-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="40ae3-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="40ae3-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="40ae3-310">Den här gången är plats 1 uppdelad i två rader, en för lagerställe 11 och ett för lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="40ae3-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="40ae3-311">Men värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som är samma eftersom **Lagerställe** inte är en ekonomisk lagerdimension.</span><span class="sxs-lookup"><span data-stu-id="40ae3-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="40ae3-312">Observera dessutom att kvantitetsfördelningen för plats 1 är annorlunda.</span><span class="sxs-lookup"><span data-stu-id="40ae3-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="40ae3-313">I den första rapporten som du körde ignorerade systemet överföringsordern som inträffade på samma plats och dragit av kvantiteten av försäljningsfakturan från **3/31/2020-3/1/2020** periodgrupp 1 på plats 1.</span><span class="sxs-lookup"><span data-stu-id="40ae3-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="40ae3-314">I den nya rapporten drar systemet emellertid av kvantiteten på försäljningsfakturan från **5/8/2020 - 5/1/2020** periodgrupp i lagerstället 12.</span><span class="sxs-lookup"><span data-stu-id="40ae3-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="40ae3-315">Effekter av stängning av lager</span><span class="sxs-lookup"><span data-stu-id="40ae3-315">Effects of inventory closing</span></span>

<span data-ttu-id="40ae3-316">Om du kör lagerstängningen för maj och sedan kör föregående rapport igen, men ställer in fältet **Från och med** till *31 maj 2020*, kommer du att märka följande resultat:</span><span class="sxs-lookup"><span data-stu-id="40ae3-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="40ae3-317">**Lagervärdet** och **Genomsnittlig enhetskostnad** uppdateras.</span><span class="sxs-lookup"><span data-stu-id="40ae3-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="40ae3-318">Värdet **Behållningsvärde** och värdena **Belopp** i varje periodgrupp uppdateras därefter.</span><span class="sxs-lookup"><span data-stu-id="40ae3-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="40ae3-319">Den nya rapporten liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="40ae3-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="40ae3-320">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="40ae3-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-321">Webbplats</span><span class="sxs-lookup"><span data-stu-id="40ae3-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-322">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="40ae3-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-323">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="40ae3-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-324">Behållningsvärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-325">Lagervärdekvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-326">Lagervärde</span><span class="sxs-lookup"><span data-stu-id="40ae3-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="40ae3-327">Genomsnittlig enhetskostnad</span><span class="sxs-lookup"><span data-stu-id="40ae3-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-328">5/31/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-329">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="40ae3-330">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="40ae3-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="40ae3-331">P1:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-332">P1:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-333">P2:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-334">P2:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="40ae3-335">P3:Kvantitet</span><span class="sxs-lookup"><span data-stu-id="40ae3-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="40ae3-336">P3:Belopp</span><span class="sxs-lookup"><span data-stu-id="40ae3-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="40ae3-337">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-337">1000</span></span></td>
    <td><span data-ttu-id="40ae3-338">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-338">1</span></span></td>
    <td><span data-ttu-id="40ae3-339">11</span><span class="sxs-lookup"><span data-stu-id="40ae3-339">11</span></span></td>
    <td><span data-ttu-id="40ae3-340">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-340">10</span></span></td>
    <td><span data-ttu-id="40ae3-341">910.70</span><span class="sxs-lookup"><span data-stu-id="40ae3-341">910.70</span></span></td>
    <td><span data-ttu-id="40ae3-342">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-342">14</span></span></td>
    <td><span data-ttu-id="40ae3-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-343">1,275.00</span></span></td>
    <td><span data-ttu-id="40ae3-344">91.07</span><span class="sxs-lookup"><span data-stu-id="40ae3-344">91.07</span></span></td>
    <td><span data-ttu-id="40ae3-345">0,00</span><span class="sxs-lookup"><span data-stu-id="40ae3-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="40ae3-346">5.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-346">5.00</span></span></td>
    <td><span data-ttu-id="40ae3-347">455.36</span><span class="sxs-lookup"><span data-stu-id="40ae3-347">455.36</span></span></td>
    <td><span data-ttu-id="40ae3-348">5.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-348">5.00</span></span></td>
    <td><span data-ttu-id="40ae3-349">455.36</span><span class="sxs-lookup"><span data-stu-id="40ae3-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="40ae3-350">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-350">1000</span></span></td>
    <td><span data-ttu-id="40ae3-351">1</span><span class="sxs-lookup"><span data-stu-id="40ae3-351">1</span></span></td>
    <td><span data-ttu-id="40ae3-352">12</span><span class="sxs-lookup"><span data-stu-id="40ae3-352">12</span></span></td>
    <td><span data-ttu-id="40ae3-353">4</span><span class="sxs-lookup"><span data-stu-id="40ae3-353">4</span></span></td>
    <td><span data-ttu-id="40ae3-354">364.29</span><span class="sxs-lookup"><span data-stu-id="40ae3-354">364.29</span></span></td>
    <td><span data-ttu-id="40ae3-355">14</span><span class="sxs-lookup"><span data-stu-id="40ae3-355">14</span></span></td>
    <td><span data-ttu-id="40ae3-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-356">1,275.00</span></span></td>
    <td><span data-ttu-id="40ae3-357">91.07</span><span class="sxs-lookup"><span data-stu-id="40ae3-357">91.07</span></span></td>
    <td><span data-ttu-id="40ae3-358">4.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-358">4.00</span></span></td>
    <td><span data-ttu-id="40ae3-359">364.29</span><span class="sxs-lookup"><span data-stu-id="40ae3-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="40ae3-360">1000</span><span class="sxs-lookup"><span data-stu-id="40ae3-360">1000</span></span></td>
    <td><span data-ttu-id="40ae3-361">2</span><span class="sxs-lookup"><span data-stu-id="40ae3-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="40ae3-362">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-362">10</span></span></td>
    <td><span data-ttu-id="40ae3-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-363">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-364">10</span><span class="sxs-lookup"><span data-stu-id="40ae3-364">10</span></span></td>
    <td><span data-ttu-id="40ae3-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-365">2,000.00</span></span></td>
    <td><span data-ttu-id="40ae3-366">200.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-367">10,00</span><span class="sxs-lookup"><span data-stu-id="40ae3-367">10.00</span></span></td>
    <td><span data-ttu-id="40ae3-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="40ae3-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="40ae3-369"><strong>1 000 summor</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="40ae3-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="40ae3-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="40ae3-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="40ae3-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="40ae3-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="40ae3-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
