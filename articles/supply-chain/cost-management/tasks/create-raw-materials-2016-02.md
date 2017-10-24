--- 
title: "Skapa råmaterial (enbart februari 2016)"
description: "Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="f7195-103">Skapa råmaterial (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="f7195-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f7195-104">Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.</span><span class="sxs-lookup"><span data-stu-id="f7195-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="f7195-105">Detta är den tredje uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="f7195-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="f7195-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="f7195-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="f7195-107">Skapa det första materialet</span><span class="sxs-lookup"><span data-stu-id="f7195-107">Create the first material</span></span>
1. <span data-ttu-id="f7195-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="f7195-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f7195-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-109">Click New.</span></span>
3. <span data-ttu-id="f7195-110">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="f7195-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f7195-111">Ange ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="f7195-112">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-113">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="f7195-113">Select STD.</span></span> <span data-ttu-id="f7195-114">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="f7195-115">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-116">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="f7195-116">For example, select Audio.</span></span> <span data-ttu-id="f7195-117">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="f7195-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="f7195-118">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-119">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f7195-119">Select SiteWH.</span></span> <span data-ttu-id="f7195-120">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="f7195-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="f7195-121">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-122">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f7195-123">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="f7195-123">Select None.</span></span>  
8. <span data-ttu-id="f7195-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7195-124">Click OK.</span></span>
9. <span data-ttu-id="f7195-125">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="f7195-126">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-126">Click Default order settings.</span></span>
11. <span data-ttu-id="f7195-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f7195-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f7195-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="f7195-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-133">Close the page.</span></span>
15. <span data-ttu-id="f7195-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-134">Close the page.</span></span>
16. <span data-ttu-id="f7195-135">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f7195-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f7195-136">Klicka på ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f7195-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="f7195-137">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="f7195-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="f7195-138">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f7195-139">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="f7195-140">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="f7195-141">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="f7195-141">Click Item price.</span></span>
21. <span data-ttu-id="f7195-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-142">Click New.</span></span>
22. <span data-ttu-id="f7195-143">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="f7195-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-144">I det här exemplet väljer du 10, som är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="f7195-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="f7195-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f7195-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-146">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="f7195-147">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="f7195-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f7195-148">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="f7195-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7195-149">Click Save.</span></span>
26. <span data-ttu-id="f7195-150">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="f7195-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="f7195-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-151">Close the page.</span></span>
28. <span data-ttu-id="f7195-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="f7195-153">Skapa det andra materialet</span><span class="sxs-lookup"><span data-stu-id="f7195-153">Create the second material</span></span>
1. <span data-ttu-id="f7195-154">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-154">Click New.</span></span>
2. <span data-ttu-id="f7195-155">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="f7195-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f7195-156">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="f7195-157">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-158">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="f7195-158">Select STD.</span></span> <span data-ttu-id="f7195-159">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f7195-160">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-161">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="f7195-161">For example, select Audio.</span></span> <span data-ttu-id="f7195-162">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="f7195-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f7195-163">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-164">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f7195-164">Select SiteWH.</span></span> <span data-ttu-id="f7195-165">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="f7195-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="f7195-166">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-167">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f7195-168">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="f7195-168">Select None.</span></span>  
7. <span data-ttu-id="f7195-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7195-169">Click OK.</span></span>
8. <span data-ttu-id="f7195-170">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f7195-171">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-171">Click Default order settings.</span></span>
10. <span data-ttu-id="f7195-172">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-173">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f7195-174">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-175">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f7195-176">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-177">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f7195-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-178">Close the page.</span></span>
14. <span data-ttu-id="f7195-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-179">Close the page.</span></span>
15. <span data-ttu-id="f7195-180">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f7195-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f7195-181">Klicka på ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="f7195-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="f7195-182">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="f7195-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f7195-183">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f7195-184">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="f7195-185">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f7195-186">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="f7195-186">Click Item price.</span></span>
20. <span data-ttu-id="f7195-187">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-187">Click New.</span></span>
21. <span data-ttu-id="f7195-188">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="f7195-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-189">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-189">For this example, select 10.</span></span> <span data-ttu-id="f7195-190">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="f7195-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f7195-191">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f7195-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-192">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f7195-193">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="f7195-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f7195-194">Ange 10 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="f7195-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="f7195-195">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7195-195">Click Save.</span></span>
25. <span data-ttu-id="f7195-196">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="f7195-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f7195-197">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-197">Close the page.</span></span>
27. <span data-ttu-id="f7195-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="f7195-199">Skapa det tredje materialet</span><span class="sxs-lookup"><span data-stu-id="f7195-199">Create the third material</span></span>
1. <span data-ttu-id="f7195-200">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-200">Click New.</span></span>
2. <span data-ttu-id="f7195-201">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="f7195-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f7195-202">Ange ITEM_C för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="f7195-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="f7195-203">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-204">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="f7195-204">Select STD.</span></span> <span data-ttu-id="f7195-205">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f7195-206">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-207">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="f7195-207">For example, select Audio.</span></span> <span data-ttu-id="f7195-208">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="f7195-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f7195-209">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-210">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f7195-210">Select SiteWH.</span></span> <span data-ttu-id="f7195-211">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="f7195-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="f7195-212">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-213">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f7195-214">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="f7195-214">Select None.</span></span>  
7. <span data-ttu-id="f7195-215">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7195-215">Click OK.</span></span>
8. <span data-ttu-id="f7195-216">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f7195-217">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="f7195-217">Click Default order settings.</span></span>
10. <span data-ttu-id="f7195-218">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-219">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f7195-220">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-221">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f7195-222">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="f7195-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-223">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f7195-224">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-224">Close the page.</span></span>
14. <span data-ttu-id="f7195-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-225">Close the page.</span></span>
15. <span data-ttu-id="f7195-226">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f7195-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f7195-227">Klicka på ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="f7195-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="f7195-228">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="f7195-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f7195-229">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f7195-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f7195-230">Ange M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="f7195-231">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f7195-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f7195-232">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="f7195-232">Click Item price.</span></span>
20. <span data-ttu-id="f7195-233">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f7195-233">Click New.</span></span>
21. <span data-ttu-id="f7195-234">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="f7195-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-235">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-235">For this example, select 10.</span></span> <span data-ttu-id="f7195-236">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="f7195-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f7195-237">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f7195-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7195-238">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f7195-239">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="f7195-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f7195-240">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f7195-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="f7195-241">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7195-241">Click Save.</span></span>
25. <span data-ttu-id="f7195-242">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="f7195-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f7195-243">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-243">Close the page.</span></span>
27. <span data-ttu-id="f7195-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7195-244">Close the page.</span></span>


