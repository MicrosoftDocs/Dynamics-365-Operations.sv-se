--- 
title: "Skapa flöden (enbart februari 2016)"
description: "Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt."
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1c2801af8201865f5ae9233c9729a4d59ef84bcd
ms.openlocfilehash: 2df913543d89a502aecfe7e2fe61265a8a1a121c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="98615-103">Skapa flöden (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="98615-103">Create routes (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98615-104">Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="98615-104">This task focuses on creating the production routes for a finished product and and a semi-finished product.</span></span> <span data-ttu-id="98615-105">Detta är den femte uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="98615-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="98615-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="98615-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="98615-107">Skapa en rutt för en halvfärdig produkt</span><span class="sxs-lookup"><span data-stu-id="98615-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="98615-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="98615-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="98615-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="98615-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="98615-110">Välj artikelnummer BOM_2.</span><span class="sxs-lookup"><span data-stu-id="98615-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="98615-111">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="98615-112">Klicka på Flöde.</span><span class="sxs-lookup"><span data-stu-id="98615-112">Click Route.</span></span>
5. <span data-ttu-id="98615-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="98615-113">Click New.</span></span>
6. <span data-ttu-id="98615-114">Klicka på Rutt och ruttversion.</span><span class="sxs-lookup"><span data-stu-id="98615-114">Click Route and route version.</span></span>
7. <span data-ttu-id="98615-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="98615-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="98615-116">Ange till exempel ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="98615-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="98615-117">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="98615-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-118">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="98615-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="98615-119">Click OK.</span></span>
10. <span data-ttu-id="98615-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="98615-120">Click New.</span></span>
11. <span data-ttu-id="98615-121">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="98615-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-122">Välj Montage i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="98615-123">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="98615-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="98615-124">Ange till exempel 1.</span><span class="sxs-lookup"><span data-stu-id="98615-124">For example, type 1.</span></span> <span data-ttu-id="98615-125">Körtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="98615-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="98615-126">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="98615-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-127">Välj Std i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="98615-128">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="98615-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="98615-129">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="98615-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-130">Välj Montage i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="98615-131">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="98615-131">Click the Times tab.</span></span>
17. <span data-ttu-id="98615-132">Ange ett värde i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="98615-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="98615-133">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-133">For this example, type 1.</span></span> <span data-ttu-id="98615-134">Ställtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="98615-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="98615-135">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="98615-136">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="98615-136">Click Approve.</span></span>
20. <span data-ttu-id="98615-137">Välj Ja under Vill du även godkänna rutten? .</span><span class="sxs-lookup"><span data-stu-id="98615-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="98615-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="98615-138">Click OK.</span></span>
22. <span data-ttu-id="98615-139">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="98615-140">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="98615-140">Click Activate.</span></span>
24. <span data-ttu-id="98615-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98615-141">Close the page.</span></span>
25. <span data-ttu-id="98615-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98615-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="98615-143">Skapa en rutt för en färdig produkt</span><span class="sxs-lookup"><span data-stu-id="98615-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="98615-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="98615-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="98615-145">Markera artikelnummer BOM_1.</span><span class="sxs-lookup"><span data-stu-id="98615-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="98615-146">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="98615-147">Klicka på Flöde.</span><span class="sxs-lookup"><span data-stu-id="98615-147">Click Route.</span></span>
4. <span data-ttu-id="98615-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="98615-148">Click New.</span></span>
5. <span data-ttu-id="98615-149">Klicka på Rutt och ruttversion.</span><span class="sxs-lookup"><span data-stu-id="98615-149">Click Route and route version.</span></span>
6. <span data-ttu-id="98615-150">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="98615-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="98615-151">Ange ROUTE_1 i detta exempel.</span><span class="sxs-lookup"><span data-stu-id="98615-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="98615-152">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="98615-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-153">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="98615-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="98615-154">Click OK.</span></span>
9. <span data-ttu-id="98615-155">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="98615-155">Click New.</span></span>
10. <span data-ttu-id="98615-156">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="98615-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-157">Välj Förpackning i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="98615-158">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="98615-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="98615-159">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="98615-160">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="98615-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-161">Välj Std i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="98615-162">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="98615-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="98615-163">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="98615-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="98615-164">Välj Förpackning i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="98615-165">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="98615-165">Click the Times tab.</span></span>
16. <span data-ttu-id="98615-166">Ange ett värde i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="98615-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="98615-167">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="98615-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="98615-168">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="98615-169">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="98615-169">Click Approve.</span></span>
19. <span data-ttu-id="98615-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="98615-170">Click OK.</span></span>
20. <span data-ttu-id="98615-171">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="98615-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="98615-172">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="98615-172">Click Activate.</span></span>
22. <span data-ttu-id="98615-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98615-173">Close the page.</span></span>
23. <span data-ttu-id="98615-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98615-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="98615-175">Aktivera automatisk förbrukning av ställtid</span><span class="sxs-lookup"><span data-stu-id="98615-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="98615-176">Gå till Produktionskontroll > Inställningar > Rutter > Ruttgrupper.</span><span class="sxs-lookup"><span data-stu-id="98615-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="98615-177">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="98615-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="98615-178">Ange Std i listan .</span><span class="sxs-lookup"><span data-stu-id="98615-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="98615-179">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="98615-179">Click Edit.</span></span>
4. <span data-ttu-id="98615-180">Välj Ja i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="98615-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="98615-181">Ställtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="98615-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="98615-182">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="98615-182">Click Save.</span></span>
6. <span data-ttu-id="98615-183">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="98615-183">Close the page.</span></span>


