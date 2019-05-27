---
title: Skapa flöden (enbart februari 2016)
description: Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt.
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
ms.openlocfilehash: 63ad2cc0c41a5931750dffbfc64bc7ce965a1da4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563214"
---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="5487e-103">Skapa flöden (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="5487e-103">Create routes (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5487e-104">Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="5487e-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="5487e-105">Detta är den femte uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="5487e-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="5487e-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="5487e-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="5487e-107">Skapa en rutt för en halvfärdig produkt</span><span class="sxs-lookup"><span data-stu-id="5487e-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="5487e-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="5487e-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="5487e-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5487e-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5487e-110">Välj artikelnummer BOM_2.</span><span class="sxs-lookup"><span data-stu-id="5487e-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="5487e-111">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="5487e-112">Klicka på Flöde.</span><span class="sxs-lookup"><span data-stu-id="5487e-112">Click Route.</span></span>
5. <span data-ttu-id="5487e-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5487e-113">Click New.</span></span>
6. <span data-ttu-id="5487e-114">Klicka på Rutt och ruttversion.</span><span class="sxs-lookup"><span data-stu-id="5487e-114">Click Route and route version.</span></span>
7. <span data-ttu-id="5487e-115">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5487e-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="5487e-116">Ange till exempel ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="5487e-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="5487e-117">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="5487e-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-118">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="5487e-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5487e-119">Click OK.</span></span>
10. <span data-ttu-id="5487e-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5487e-120">Click New.</span></span>
11. <span data-ttu-id="5487e-121">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="5487e-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-122">Välj Montage i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="5487e-123">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="5487e-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="5487e-124">Ange till exempel 1.</span><span class="sxs-lookup"><span data-stu-id="5487e-124">For example, type 1.</span></span> <span data-ttu-id="5487e-125">Körtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="5487e-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="5487e-126">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="5487e-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-127">Välj Std i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="5487e-128">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="5487e-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="5487e-129">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="5487e-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-130">Välj Montage i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="5487e-131">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="5487e-131">Click the Times tab.</span></span>
17. <span data-ttu-id="5487e-132">Ange ett värde i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="5487e-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="5487e-133">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-133">For this example, type 1.</span></span> <span data-ttu-id="5487e-134">Ställtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="5487e-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="5487e-135">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="5487e-136">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="5487e-136">Click Approve.</span></span>
20. <span data-ttu-id="5487e-137">Välj Ja under Vill du även godkänna rutten? .</span><span class="sxs-lookup"><span data-stu-id="5487e-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="5487e-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5487e-138">Click OK.</span></span>
22. <span data-ttu-id="5487e-139">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="5487e-140">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="5487e-140">Click Activate.</span></span>
24. <span data-ttu-id="5487e-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5487e-141">Close the page.</span></span>
25. <span data-ttu-id="5487e-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5487e-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="5487e-143">Skapa en rutt för en färdig produkt</span><span class="sxs-lookup"><span data-stu-id="5487e-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="5487e-144">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5487e-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5487e-145">Markera artikelnummer BOM_1.</span><span class="sxs-lookup"><span data-stu-id="5487e-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="5487e-146">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="5487e-147">Klicka på Flöde.</span><span class="sxs-lookup"><span data-stu-id="5487e-147">Click Route.</span></span>
4. <span data-ttu-id="5487e-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5487e-148">Click New.</span></span>
5. <span data-ttu-id="5487e-149">Klicka på Rutt och ruttversion.</span><span class="sxs-lookup"><span data-stu-id="5487e-149">Click Route and route version.</span></span>
6. <span data-ttu-id="5487e-150">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5487e-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="5487e-151">Ange ROUTE_1 i detta exempel.</span><span class="sxs-lookup"><span data-stu-id="5487e-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="5487e-152">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="5487e-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-153">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="5487e-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5487e-154">Click OK.</span></span>
9. <span data-ttu-id="5487e-155">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5487e-155">Click New.</span></span>
10. <span data-ttu-id="5487e-156">Ange eller välj ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="5487e-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-157">Välj Förpackning i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="5487e-158">Ange ett värde i fältet Körtid.</span><span class="sxs-lookup"><span data-stu-id="5487e-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="5487e-159">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="5487e-160">Ange eller välj ett värde i fältet Flödesgrupp.</span><span class="sxs-lookup"><span data-stu-id="5487e-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-161">Välj Std i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="5487e-162">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="5487e-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="5487e-163">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="5487e-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="5487e-164">Välj Förpackning i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="5487e-165">Klicka på fliken Tider.</span><span class="sxs-lookup"><span data-stu-id="5487e-165">Click the Times tab.</span></span>
16. <span data-ttu-id="5487e-166">Ange ett värde i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="5487e-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="5487e-167">Ange 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="5487e-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="5487e-168">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="5487e-169">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="5487e-169">Click Approve.</span></span>
19. <span data-ttu-id="5487e-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5487e-170">Click OK.</span></span>
20. <span data-ttu-id="5487e-171">Klicka på Ruttversion i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5487e-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="5487e-172">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="5487e-172">Click Activate.</span></span>
22. <span data-ttu-id="5487e-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5487e-173">Close the page.</span></span>
23. <span data-ttu-id="5487e-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5487e-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="5487e-175">Aktivera automatisk förbrukning av ställtid</span><span class="sxs-lookup"><span data-stu-id="5487e-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="5487e-176">Gå till Produktionskontroll > Inställningar > Rutter > Ruttgrupper.</span><span class="sxs-lookup"><span data-stu-id="5487e-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="5487e-177">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5487e-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5487e-178">Ange Std i listan .</span><span class="sxs-lookup"><span data-stu-id="5487e-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="5487e-179">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="5487e-179">Click Edit.</span></span>
4. <span data-ttu-id="5487e-180">Välj Ja i fältet Ställtid.</span><span class="sxs-lookup"><span data-stu-id="5487e-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="5487e-181">Ställtider ingår ofta i det pris som beräknas för en artikel.</span><span class="sxs-lookup"><span data-stu-id="5487e-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="5487e-182">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5487e-182">Click Save.</span></span>
6. <span data-ttu-id="5487e-183">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5487e-183">Close the page.</span></span>

