---
title: Skapa råmaterial (enbart februari 2016)
description: Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 869acddf6f7e9754bb4952176ded4b22c74eaffd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563306"
---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="00918-103">Skapa råmaterial (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="00918-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="00918-104">Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.</span><span class="sxs-lookup"><span data-stu-id="00918-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="00918-105">Detta är den tredje uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="00918-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="00918-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="00918-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="00918-107">Skapa det första materialet</span><span class="sxs-lookup"><span data-stu-id="00918-107">Create the first material</span></span>
1. <span data-ttu-id="00918-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="00918-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="00918-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-109">Click New.</span></span>
3. <span data-ttu-id="00918-110">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="00918-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="00918-111">Ange ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="00918-112">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-113">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="00918-113">Select STD.</span></span> <span data-ttu-id="00918-114">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="00918-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="00918-115">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-116">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="00918-116">For example, select Audio.</span></span> <span data-ttu-id="00918-117">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="00918-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="00918-118">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-119">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="00918-119">Select SiteWH.</span></span> <span data-ttu-id="00918-120">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="00918-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="00918-121">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-122">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="00918-123">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="00918-123">Select None.</span></span>  
8. <span data-ttu-id="00918-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="00918-124">Click OK.</span></span>
9. <span data-ttu-id="00918-125">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="00918-126">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="00918-126">Click Default order settings.</span></span>
11. <span data-ttu-id="00918-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="00918-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="00918-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="00918-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="00918-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-133">Close the page.</span></span>
15. <span data-ttu-id="00918-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-134">Close the page.</span></span>
16. <span data-ttu-id="00918-135">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="00918-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="00918-136">Klicka på ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="00918-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="00918-137">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="00918-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="00918-138">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="00918-139">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="00918-140">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="00918-141">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="00918-141">Click Item price.</span></span>
21. <span data-ttu-id="00918-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-142">Click New.</span></span>
22. <span data-ttu-id="00918-143">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="00918-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-144">I det här exemplet väljer du 10, som är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="00918-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="00918-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="00918-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-146">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="00918-147">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="00918-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="00918-148">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="00918-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="00918-149">Click Save.</span></span>
26. <span data-ttu-id="00918-150">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="00918-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="00918-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-151">Close the page.</span></span>
28. <span data-ttu-id="00918-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="00918-153">Skapa det andra materialet</span><span class="sxs-lookup"><span data-stu-id="00918-153">Create the second material</span></span>
1. <span data-ttu-id="00918-154">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-154">Click New.</span></span>
2. <span data-ttu-id="00918-155">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="00918-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="00918-156">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="00918-157">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-158">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="00918-158">Select STD.</span></span> <span data-ttu-id="00918-159">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="00918-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="00918-160">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-161">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="00918-161">For example, select Audio.</span></span> <span data-ttu-id="00918-162">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="00918-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="00918-163">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-164">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="00918-164">Select SiteWH.</span></span> <span data-ttu-id="00918-165">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="00918-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="00918-166">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-167">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="00918-168">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="00918-168">Select None.</span></span>  
7. <span data-ttu-id="00918-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="00918-169">Click OK.</span></span>
8. <span data-ttu-id="00918-170">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="00918-171">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="00918-171">Click Default order settings.</span></span>
10. <span data-ttu-id="00918-172">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-173">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="00918-174">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="00918-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-175">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="00918-176">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-177">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="00918-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-178">Close the page.</span></span>
14. <span data-ttu-id="00918-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-179">Close the page.</span></span>
15. <span data-ttu-id="00918-180">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="00918-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="00918-181">Klicka på ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="00918-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="00918-182">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="00918-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="00918-183">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="00918-184">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="00918-185">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="00918-186">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="00918-186">Click Item price.</span></span>
20. <span data-ttu-id="00918-187">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-187">Click New.</span></span>
21. <span data-ttu-id="00918-188">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="00918-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-189">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-189">For this example, select 10.</span></span> <span data-ttu-id="00918-190">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="00918-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="00918-191">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="00918-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-192">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="00918-193">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="00918-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="00918-194">Ange 10 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="00918-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="00918-195">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="00918-195">Click Save.</span></span>
25. <span data-ttu-id="00918-196">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="00918-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="00918-197">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-197">Close the page.</span></span>
27. <span data-ttu-id="00918-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="00918-199">Skapa det tredje materialet</span><span class="sxs-lookup"><span data-stu-id="00918-199">Create the third material</span></span>
1. <span data-ttu-id="00918-200">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-200">Click New.</span></span>
2. <span data-ttu-id="00918-201">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="00918-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="00918-202">Ange ITEM_C för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="00918-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="00918-203">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-204">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="00918-204">Select STD.</span></span> <span data-ttu-id="00918-205">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="00918-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="00918-206">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-207">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="00918-207">For example, select Audio.</span></span> <span data-ttu-id="00918-208">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="00918-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="00918-209">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-210">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="00918-210">Select SiteWH.</span></span> <span data-ttu-id="00918-211">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="00918-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="00918-212">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-213">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="00918-214">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="00918-214">Select None.</span></span>  
7. <span data-ttu-id="00918-215">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="00918-215">Click OK.</span></span>
8. <span data-ttu-id="00918-216">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="00918-217">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="00918-217">Click Default order settings.</span></span>
10. <span data-ttu-id="00918-218">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-219">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="00918-220">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="00918-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-221">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="00918-222">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="00918-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-223">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="00918-224">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-224">Close the page.</span></span>
14. <span data-ttu-id="00918-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-225">Close the page.</span></span>
15. <span data-ttu-id="00918-226">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="00918-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="00918-227">Klicka på ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="00918-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="00918-228">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="00918-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="00918-229">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="00918-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="00918-230">Ange M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="00918-231">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="00918-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="00918-232">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="00918-232">Click Item price.</span></span>
20. <span data-ttu-id="00918-233">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="00918-233">Click New.</span></span>
21. <span data-ttu-id="00918-234">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="00918-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-235">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-235">For this example, select 10.</span></span> <span data-ttu-id="00918-236">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="00918-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="00918-237">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="00918-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="00918-238">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="00918-239">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="00918-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="00918-240">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="00918-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="00918-241">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="00918-241">Click Save.</span></span>
25. <span data-ttu-id="00918-242">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="00918-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="00918-243">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-243">Close the page.</span></span>
27. <span data-ttu-id="00918-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="00918-244">Close the page.</span></span>

