---
title: Skapa strukturlistor (enbart februari 2016)
description: Den här uppgiften fokuserar på att skapa strukturlistestrukturen för en färdig produkt och en halvfärdig produkt.
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
ms.openlocfilehash: f132a3865b180a74d328ebc76ca29b2fc8aee85f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "332551"
---
# <a name="create-boms-february-2016-only"></a><span data-ttu-id="ecbba-103">Skapa strukturlistor (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="ecbba-103">Create BOMs (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ecbba-104">Den här uppgiften fokuserar på att skapa strukturlistestrukturen för en färdig produkt och en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="ecbba-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="ecbba-105">Detta är den fjärde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="ecbba-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="ecbba-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="ecbba-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="ecbba-107">Skapa en strukturlista för en halvfärdig produkt</span><span class="sxs-lookup"><span data-stu-id="ecbba-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="ecbba-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="ecbba-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="ecbba-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecbba-110">Välj artikelnummer BOM_2.</span><span class="sxs-lookup"><span data-stu-id="ecbba-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="ecbba-111">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ecbba-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="ecbba-112">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="ecbba-112">Click BOM versions.</span></span>
5. <span data-ttu-id="ecbba-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-113">Click New.</span></span>
6. <span data-ttu-id="ecbba-114">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="ecbba-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="ecbba-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="ecbba-116">Ange till exempel BOM_2.</span><span class="sxs-lookup"><span data-stu-id="ecbba-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="ecbba-117">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="ecbba-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-118">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="ecbba-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-119">Click OK.</span></span>
10. <span data-ttu-id="ecbba-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-120">Click New.</span></span>
11. <span data-ttu-id="ecbba-121">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="ecbba-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ecbba-122">Välj ITEM_C i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="ecbba-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="ecbba-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-124">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="ecbba-125">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="ecbba-125">Click Header.</span></span>
14. <span data-ttu-id="ecbba-126">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="ecbba-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="ecbba-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-127">Click OK.</span></span>
16. <span data-ttu-id="ecbba-128">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-128">Click Approve.</span></span>
    * <span data-ttu-id="ecbba-129">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="ecbba-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="ecbba-130">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="ecbba-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-131">Click OK.</span></span>
18. <span data-ttu-id="ecbba-132">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ecbba-132">Click Activate.</span></span>
19. <span data-ttu-id="ecbba-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-133">Close the page.</span></span>
20. <span data-ttu-id="ecbba-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-134">Close the page.</span></span>
21. <span data-ttu-id="ecbba-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="ecbba-136">Skapa en strukturlista för en färdig produkt</span><span class="sxs-lookup"><span data-stu-id="ecbba-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="ecbba-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecbba-138">Markera artikelnummer BOM_1.</span><span class="sxs-lookup"><span data-stu-id="ecbba-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="ecbba-139">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ecbba-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="ecbba-140">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="ecbba-140">Click BOM versions.</span></span>
4. <span data-ttu-id="ecbba-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-141">Click New.</span></span>
5. <span data-ttu-id="ecbba-142">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="ecbba-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="ecbba-143">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="ecbba-144">Ange till exempel BOM_1.</span><span class="sxs-lookup"><span data-stu-id="ecbba-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="ecbba-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="ecbba-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-146">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="ecbba-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-147">Click OK.</span></span>
9. <span data-ttu-id="ecbba-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-148">Click New.</span></span>
10. <span data-ttu-id="ecbba-149">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="ecbba-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ecbba-150">Välj ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="ecbba-151">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="ecbba-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-152">Välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="ecbba-153">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-153">Click New.</span></span>
13. <span data-ttu-id="ecbba-154">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="ecbba-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ecbba-155">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="ecbba-156">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="ecbba-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-157">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="ecbba-158">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ecbba-158">Click New.</span></span>
16. <span data-ttu-id="ecbba-159">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="ecbba-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ecbba-160">Ange BOM_2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="ecbba-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="ecbba-162">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="ecbba-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="ecbba-163">Ange eller välj plats lagerställe 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="ecbba-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="ecbba-164">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="ecbba-164">Click Header.</span></span>
20. <span data-ttu-id="ecbba-165">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="ecbba-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="ecbba-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-166">Click OK.</span></span>
22. <span data-ttu-id="ecbba-167">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-167">Click Approve.</span></span>
    * <span data-ttu-id="ecbba-168">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="ecbba-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="ecbba-169">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="ecbba-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="ecbba-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ecbba-170">Click OK.</span></span>
24. <span data-ttu-id="ecbba-171">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="ecbba-171">Click Activate.</span></span>
25. <span data-ttu-id="ecbba-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-172">Close the page.</span></span>
26. <span data-ttu-id="ecbba-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-173">Close the page.</span></span>
27. <span data-ttu-id="ecbba-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ecbba-174">Close the page.</span></span>

