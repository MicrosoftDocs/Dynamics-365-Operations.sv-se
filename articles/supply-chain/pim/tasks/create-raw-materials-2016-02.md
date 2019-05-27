---
title: Skapa råmaterial (februari 2016)
description: Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552680"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="c71e0-103">Skapa råmaterial (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="c71e0-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c71e0-104">Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.</span><span class="sxs-lookup"><span data-stu-id="c71e0-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="c71e0-105">Detta är den tredje uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="c71e0-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="c71e0-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="c71e0-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="c71e0-107">Skapa det första materialet</span><span class="sxs-lookup"><span data-stu-id="c71e0-107">Create the first material</span></span>
1. <span data-ttu-id="c71e0-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="c71e0-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c71e0-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-109">Click New.</span></span>
3. <span data-ttu-id="c71e0-110">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="c71e0-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c71e0-111">Ange ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="c71e0-112">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-113">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="c71e0-113">Select STD.</span></span> <span data-ttu-id="c71e0-114">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="c71e0-115">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-116">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="c71e0-116">For example, select Audio.</span></span> <span data-ttu-id="c71e0-117">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="c71e0-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="c71e0-118">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-119">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c71e0-119">Select SiteWH.</span></span> <span data-ttu-id="c71e0-120">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="c71e0-121">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-122">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c71e0-123">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-123">Select None.</span></span>  
8. <span data-ttu-id="c71e0-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c71e0-124">Click OK.</span></span>
9. <span data-ttu-id="c71e0-125">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="c71e0-126">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-126">Click Default order settings.</span></span>
11. <span data-ttu-id="c71e0-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c71e0-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c71e0-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="c71e0-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-133">Close the page.</span></span>
15. <span data-ttu-id="c71e0-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-134">Close the page.</span></span>
16. <span data-ttu-id="c71e0-135">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c71e0-136">Klicka på ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="c71e0-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="c71e0-137">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="c71e0-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="c71e0-138">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c71e0-139">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="c71e0-140">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="c71e0-141">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-141">Click Item price.</span></span>
21. <span data-ttu-id="c71e0-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-142">Click New.</span></span>
22. <span data-ttu-id="c71e0-143">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="c71e0-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-144">I det här exemplet väljer du 10, som är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="c71e0-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="c71e0-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-146">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="c71e0-147">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c71e0-148">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="c71e0-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71e0-149">Click Save.</span></span>
26. <span data-ttu-id="c71e0-150">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="c71e0-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="c71e0-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-151">Close the page.</span></span>
28. <span data-ttu-id="c71e0-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="c71e0-153">Skapa det andra materialet</span><span class="sxs-lookup"><span data-stu-id="c71e0-153">Create the second material</span></span>
1. <span data-ttu-id="c71e0-154">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-154">Click New.</span></span>
2. <span data-ttu-id="c71e0-155">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="c71e0-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c71e0-156">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="c71e0-157">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-158">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="c71e0-158">Select STD.</span></span> <span data-ttu-id="c71e0-159">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c71e0-160">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-161">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="c71e0-161">For example, select Audio.</span></span> <span data-ttu-id="c71e0-162">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="c71e0-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c71e0-163">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-164">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c71e0-164">Select SiteWH.</span></span> <span data-ttu-id="c71e0-165">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="c71e0-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="c71e0-166">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-167">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c71e0-168">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-168">Select None.</span></span>  
7. <span data-ttu-id="c71e0-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c71e0-169">Click OK.</span></span>
8. <span data-ttu-id="c71e0-170">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c71e0-171">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-171">Click Default order settings.</span></span>
10. <span data-ttu-id="c71e0-172">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-173">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c71e0-174">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-175">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c71e0-176">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-177">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c71e0-178">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-178">Close the page.</span></span>
14. <span data-ttu-id="c71e0-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-179">Close the page.</span></span>
15. <span data-ttu-id="c71e0-180">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c71e0-181">Klicka på ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c71e0-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="c71e0-182">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="c71e0-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c71e0-183">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c71e0-184">Ange M2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="c71e0-185">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c71e0-186">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-186">Click Item price.</span></span>
20. <span data-ttu-id="c71e0-187">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-187">Click New.</span></span>
21. <span data-ttu-id="c71e0-188">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="c71e0-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-189">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-189">For this example, select 10.</span></span> <span data-ttu-id="c71e0-190">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="c71e0-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c71e0-191">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-192">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c71e0-193">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c71e0-194">Ange 10 för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="c71e0-195">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71e0-195">Click Save.</span></span>
25. <span data-ttu-id="c71e0-196">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="c71e0-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c71e0-197">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-197">Close the page.</span></span>
27. <span data-ttu-id="c71e0-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="c71e0-199">Skapa det tredje materialet</span><span class="sxs-lookup"><span data-stu-id="c71e0-199">Create the third material</span></span>
1. <span data-ttu-id="c71e0-200">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-200">Click New.</span></span>
2. <span data-ttu-id="c71e0-201">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="c71e0-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c71e0-202">Ange ITEM_C för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="c71e0-203">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-204">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="c71e0-204">Select STD.</span></span> <span data-ttu-id="c71e0-205">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c71e0-206">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-207">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="c71e0-207">For example, select Audio.</span></span> <span data-ttu-id="c71e0-208">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="c71e0-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c71e0-209">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-210">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c71e0-210">Select SiteWH.</span></span> <span data-ttu-id="c71e0-211">Endast plats och lagerställe används för demonstrationen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="c71e0-212">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-213">Spårningsdimensioner kommer inte att användas i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c71e0-214">Välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="c71e0-214">Select None.</span></span>  
7. <span data-ttu-id="c71e0-215">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c71e0-215">Click OK.</span></span>
8. <span data-ttu-id="c71e0-216">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c71e0-217">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="c71e0-217">Click Default order settings.</span></span>
10. <span data-ttu-id="c71e0-218">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-219">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c71e0-220">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-221">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c71e0-222">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-223">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c71e0-224">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-224">Close the page.</span></span>
14. <span data-ttu-id="c71e0-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-225">Close the page.</span></span>
15. <span data-ttu-id="c71e0-226">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c71e0-227">Klicka på ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="c71e0-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="c71e0-228">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="c71e0-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c71e0-229">Ange ett värde i fältet för kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c71e0-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c71e0-230">Ange M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="c71e0-231">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c71e0-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c71e0-232">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-232">Click Item price.</span></span>
20. <span data-ttu-id="c71e0-233">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c71e0-233">Click New.</span></span>
21. <span data-ttu-id="c71e0-234">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="c71e0-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-235">Välj 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-235">For this example, select 10.</span></span> <span data-ttu-id="c71e0-236">Detta är kostnadsredovisningstypen för standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="c71e0-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c71e0-237">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="c71e0-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c71e0-238">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c71e0-239">Ange ett tal i fältet Pris.</span><span class="sxs-lookup"><span data-stu-id="c71e0-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c71e0-240">Ange 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c71e0-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="c71e0-241">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c71e0-241">Click Save.</span></span>
25. <span data-ttu-id="c71e0-242">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="c71e0-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c71e0-243">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-243">Close the page.</span></span>
27. <span data-ttu-id="c71e0-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c71e0-244">Close the page.</span></span>

