--- 
title: "Skapa råmaterial (februari 2016)"
description: "Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="817d5-103">Skapa råmaterial (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="817d5-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="817d5-104">Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.</span><span class="sxs-lookup"><span data-stu-id="817d5-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="817d5-105">Detta är den tredje uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="817d5-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="817d5-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="817d5-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="817d5-107">Skapa det första materialet</span><span class="sxs-lookup"><span data-stu-id="817d5-107">Create the first material</span></span>
1. <span data-ttu-id="817d5-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="817d5-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="817d5-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-109">Click New.</span></span>
3. <span data-ttu-id="817d5-110">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="817d5-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="817d5-111">Ange ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="817d5-112">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-113">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="817d5-113">Select STD.</span></span> <span data-ttu-id="817d5-114">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="817d5-115">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-116">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="817d5-116">For example, select Audio.</span></span> <span data-ttu-id="817d5-117">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="817d5-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="817d5-118">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-119">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="817d5-119">Select SiteWH.</span></span> <span data-ttu-id="817d5-120">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="817d5-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="817d5-121">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-122">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="817d5-123">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="817d5-123">Select None.</span></span>  
8. <span data-ttu-id="817d5-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="817d5-124">Click OK.</span></span>
9. <span data-ttu-id="817d5-125">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="817d5-126">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-126">Click Default order settings.</span></span>
11. <span data-ttu-id="817d5-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="817d5-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="817d5-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="817d5-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-133">Close the page.</span></span>
15. <span data-ttu-id="817d5-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-134">Close the page.</span></span>
16. <span data-ttu-id="817d5-135">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="817d5-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="817d5-136">Klicka på ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="817d5-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="817d5-137">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="817d5-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="817d5-138">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="817d5-139">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="817d5-140">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="817d5-141">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="817d5-141">Click Item price.</span></span>
21. <span data-ttu-id="817d5-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-142">Click New.</span></span>
22. <span data-ttu-id="817d5-143">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="817d5-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-144">I det här exemplet väljer du 10, som är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="817d5-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="817d5-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="817d5-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-146">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="817d5-147">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="817d5-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="817d5-148">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="817d5-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="817d5-149">Click Save.</span></span>
26. <span data-ttu-id="817d5-150">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="817d5-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="817d5-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-151">Close the page.</span></span>
28. <span data-ttu-id="817d5-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="817d5-153">Skapa det andra materialet</span><span class="sxs-lookup"><span data-stu-id="817d5-153">Create the second material</span></span>
1. <span data-ttu-id="817d5-154">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-154">Click New.</span></span>
2. <span data-ttu-id="817d5-155">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="817d5-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="817d5-156">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="817d5-157">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-158">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="817d5-158">Select STD.</span></span> <span data-ttu-id="817d5-159">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="817d5-160">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-161">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="817d5-161">For example, select Audio.</span></span> <span data-ttu-id="817d5-162">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="817d5-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="817d5-163">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-164">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="817d5-164">Select SiteWH.</span></span> <span data-ttu-id="817d5-165">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="817d5-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="817d5-166">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-167">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="817d5-168">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="817d5-168">Select None.</span></span>  
7. <span data-ttu-id="817d5-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="817d5-169">Click OK.</span></span>
8. <span data-ttu-id="817d5-170">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="817d5-171">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-171">Click Default order settings.</span></span>
10. <span data-ttu-id="817d5-172">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-173">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="817d5-174">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-175">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="817d5-176">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-177">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="817d5-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-178">Close the page.</span></span>
14. <span data-ttu-id="817d5-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-179">Close the page.</span></span>
15. <span data-ttu-id="817d5-180">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="817d5-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="817d5-181">Klicka på ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="817d5-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="817d5-182">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="817d5-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="817d5-183">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="817d5-184">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="817d5-185">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="817d5-186">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="817d5-186">Click Item price.</span></span>
20. <span data-ttu-id="817d5-187">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-187">Click New.</span></span>
21. <span data-ttu-id="817d5-188">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="817d5-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-189">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-189">For this example, select 10.</span></span> <span data-ttu-id="817d5-190">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="817d5-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="817d5-191">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="817d5-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-192">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="817d5-193">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="817d5-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="817d5-194">Ange 10 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="817d5-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="817d5-195">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="817d5-195">Click Save.</span></span>
25. <span data-ttu-id="817d5-196">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="817d5-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="817d5-197">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-197">Close the page.</span></span>
27. <span data-ttu-id="817d5-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="817d5-199">Skapa det tredje materialet</span><span class="sxs-lookup"><span data-stu-id="817d5-199">Create the third material</span></span>
1. <span data-ttu-id="817d5-200">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-200">Click New.</span></span>
2. <span data-ttu-id="817d5-201">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="817d5-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="817d5-202">Ange ITEM_C för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="817d5-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="817d5-203">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-204">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="817d5-204">Select STD.</span></span> <span data-ttu-id="817d5-205">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="817d5-206">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-207">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="817d5-207">For example, select Audio.</span></span> <span data-ttu-id="817d5-208">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="817d5-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="817d5-209">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-210">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="817d5-210">Select SiteWH.</span></span> <span data-ttu-id="817d5-211">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="817d5-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="817d5-212">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-213">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="817d5-214">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="817d5-214">Select None.</span></span>  
7. <span data-ttu-id="817d5-215">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="817d5-215">Click OK.</span></span>
8. <span data-ttu-id="817d5-216">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="817d5-217">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="817d5-217">Click Default order settings.</span></span>
10. <span data-ttu-id="817d5-218">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-219">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="817d5-220">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-221">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="817d5-222">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="817d5-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-223">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="817d5-224">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-224">Close the page.</span></span>
14. <span data-ttu-id="817d5-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-225">Close the page.</span></span>
15. <span data-ttu-id="817d5-226">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="817d5-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="817d5-227">Klicka på ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="817d5-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="817d5-228">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="817d5-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="817d5-229">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="817d5-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="817d5-230">Ange M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="817d5-231">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="817d5-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="817d5-232">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="817d5-232">Click Item price.</span></span>
20. <span data-ttu-id="817d5-233">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="817d5-233">Click New.</span></span>
21. <span data-ttu-id="817d5-234">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="817d5-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-235">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-235">For this example, select 10.</span></span> <span data-ttu-id="817d5-236">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="817d5-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="817d5-237">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="817d5-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="817d5-238">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="817d5-239">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="817d5-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="817d5-240">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="817d5-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="817d5-241">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="817d5-241">Click Save.</span></span>
25. <span data-ttu-id="817d5-242">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="817d5-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="817d5-243">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-243">Close the page.</span></span>
27. <span data-ttu-id="817d5-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="817d5-244">Close the page.</span></span>


