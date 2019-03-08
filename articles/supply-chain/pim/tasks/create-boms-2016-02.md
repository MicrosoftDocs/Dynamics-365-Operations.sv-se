---
title: Skapa strukturlistor (februari 2016)
description: Den här uppgiften fokuserar på att skapa strukturlistestrukturen för en färdig produkt och en halvfärdig produkt.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "333218"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="38e08-103">Skapa strukturlistor (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="38e08-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38e08-104">Den här uppgiften fokuserar på att skapa strukturlistestrukturen för en färdig produkt och en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="38e08-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="38e08-105">Detta är den fjärde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="38e08-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="38e08-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="38e08-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="38e08-107">Skapa en strukturlista för en halvfärdig produkt</span><span class="sxs-lookup"><span data-stu-id="38e08-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="38e08-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="38e08-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="38e08-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="38e08-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="38e08-110">Välj artikelnummer BOM_2.</span><span class="sxs-lookup"><span data-stu-id="38e08-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="38e08-111">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="38e08-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="38e08-112">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="38e08-112">Click BOM versions.</span></span>
5. <span data-ttu-id="38e08-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-113">Click New.</span></span>
6. <span data-ttu-id="38e08-114">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="38e08-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="38e08-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="38e08-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="38e08-116">Ange till exempel BOM_2.</span><span class="sxs-lookup"><span data-stu-id="38e08-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="38e08-117">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="38e08-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-118">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="38e08-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-119">Click OK.</span></span>
10. <span data-ttu-id="38e08-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-120">Click New.</span></span>
11. <span data-ttu-id="38e08-121">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="38e08-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="38e08-122">Välj ITEM_C i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="38e08-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="38e08-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-124">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="38e08-125">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="38e08-125">Click Header.</span></span>
14. <span data-ttu-id="38e08-126">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="38e08-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="38e08-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-127">Click OK.</span></span>
16. <span data-ttu-id="38e08-128">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="38e08-128">Click Approve.</span></span>
    * <span data-ttu-id="38e08-129">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="38e08-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="38e08-130">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="38e08-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="38e08-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-131">Click OK.</span></span>
18. <span data-ttu-id="38e08-132">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="38e08-132">Click Activate.</span></span>
19. <span data-ttu-id="38e08-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-133">Close the page.</span></span>
20. <span data-ttu-id="38e08-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-134">Close the page.</span></span>
21. <span data-ttu-id="38e08-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="38e08-136">Skapa en strukturlista för en färdig produkt</span><span class="sxs-lookup"><span data-stu-id="38e08-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="38e08-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="38e08-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="38e08-138">Markera artikelnummer BOM_1.</span><span class="sxs-lookup"><span data-stu-id="38e08-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="38e08-139">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="38e08-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="38e08-140">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="38e08-140">Click BOM versions.</span></span>
4. <span data-ttu-id="38e08-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-141">Click New.</span></span>
5. <span data-ttu-id="38e08-142">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="38e08-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="38e08-143">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="38e08-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="38e08-144">Ange till exempel BOM_1.</span><span class="sxs-lookup"><span data-stu-id="38e08-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="38e08-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="38e08-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-146">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="38e08-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-147">Click OK.</span></span>
9. <span data-ttu-id="38e08-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-148">Click New.</span></span>
10. <span data-ttu-id="38e08-149">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="38e08-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="38e08-150">Välj ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="38e08-151">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="38e08-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-152">Välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="38e08-153">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-153">Click New.</span></span>
13. <span data-ttu-id="38e08-154">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="38e08-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="38e08-155">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="38e08-156">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="38e08-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-157">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="38e08-158">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38e08-158">Click New.</span></span>
16. <span data-ttu-id="38e08-159">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="38e08-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="38e08-160">Ange BOM_2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="38e08-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="38e08-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="38e08-162">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="38e08-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38e08-163">Ange eller välj plats lagerställe 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="38e08-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="38e08-164">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="38e08-164">Click Header.</span></span>
20. <span data-ttu-id="38e08-165">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="38e08-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="38e08-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-166">Click OK.</span></span>
22. <span data-ttu-id="38e08-167">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="38e08-167">Click Approve.</span></span>
    * <span data-ttu-id="38e08-168">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="38e08-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="38e08-169">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="38e08-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="38e08-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38e08-170">Click OK.</span></span>
24. <span data-ttu-id="38e08-171">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="38e08-171">Click Activate.</span></span>
25. <span data-ttu-id="38e08-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-172">Close the page.</span></span>
26. <span data-ttu-id="38e08-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-173">Close the page.</span></span>
27. <span data-ttu-id="38e08-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38e08-174">Close the page.</span></span>

