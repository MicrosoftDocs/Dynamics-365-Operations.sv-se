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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0087c53d9cdc3bb65e6fa446c193c752d0f9b4fc
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845099"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="446a5-103">Skapa strukturlistor (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="446a5-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="446a5-104">Den här uppgiften fokuserar på att skapa strukturlistestrukturen för en färdig produkt och en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="446a5-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="446a5-105">Detta är den fjärde uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="446a5-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="446a5-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="446a5-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="446a5-107">Skapa en strukturlista för en halvfärdig produkt</span><span class="sxs-lookup"><span data-stu-id="446a5-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="446a5-108">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="446a5-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="446a5-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="446a5-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="446a5-110">Välj artikelnummer BOM_2.</span><span class="sxs-lookup"><span data-stu-id="446a5-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="446a5-111">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="446a5-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="446a5-112">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="446a5-112">Click BOM versions.</span></span>
5. <span data-ttu-id="446a5-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-113">Click New.</span></span>
6. <span data-ttu-id="446a5-114">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="446a5-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="446a5-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="446a5-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="446a5-116">Ange till exempel BOM_2.</span><span class="sxs-lookup"><span data-stu-id="446a5-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="446a5-117">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="446a5-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-118">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="446a5-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-119">Click OK.</span></span>
10. <span data-ttu-id="446a5-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-120">Click New.</span></span>
11. <span data-ttu-id="446a5-121">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="446a5-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="446a5-122">Välj ITEM_C i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="446a5-123">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="446a5-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-124">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="446a5-125">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="446a5-125">Click Header.</span></span>
14. <span data-ttu-id="446a5-126">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="446a5-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="446a5-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-127">Click OK.</span></span>
16. <span data-ttu-id="446a5-128">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="446a5-128">Click Approve.</span></span>
    * <span data-ttu-id="446a5-129">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="446a5-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="446a5-130">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="446a5-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="446a5-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-131">Click OK.</span></span>
18. <span data-ttu-id="446a5-132">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="446a5-132">Click Activate.</span></span>
19. <span data-ttu-id="446a5-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-133">Close the page.</span></span>
20. <span data-ttu-id="446a5-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-134">Close the page.</span></span>
21. <span data-ttu-id="446a5-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="446a5-136">Skapa en strukturlista för en färdig produkt</span><span class="sxs-lookup"><span data-stu-id="446a5-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="446a5-137">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="446a5-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="446a5-138">Markera artikelnummer BOM_1.</span><span class="sxs-lookup"><span data-stu-id="446a5-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="446a5-139">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="446a5-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="446a5-140">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="446a5-140">Click BOM versions.</span></span>
4. <span data-ttu-id="446a5-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-141">Click New.</span></span>
5. <span data-ttu-id="446a5-142">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="446a5-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="446a5-143">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="446a5-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="446a5-144">Ange till exempel BOM_1.</span><span class="sxs-lookup"><span data-stu-id="446a5-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="446a5-145">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="446a5-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-146">Ange eller välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="446a5-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-147">Click OK.</span></span>
9. <span data-ttu-id="446a5-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-148">Click New.</span></span>
10. <span data-ttu-id="446a5-149">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="446a5-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="446a5-150">Välj ITEM_A i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="446a5-151">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="446a5-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-152">Välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="446a5-153">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-153">Click New.</span></span>
13. <span data-ttu-id="446a5-154">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="446a5-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="446a5-155">Välj ITEM_B i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="446a5-156">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="446a5-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-157">Ange eller välj 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="446a5-158">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="446a5-158">Click New.</span></span>
16. <span data-ttu-id="446a5-159">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="446a5-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="446a5-160">Ange BOM_2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="446a5-161">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="446a5-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="446a5-162">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="446a5-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="446a5-163">Ange eller välj plats lagerställe 11 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="446a5-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="446a5-164">Klicka på Rubrik.</span><span class="sxs-lookup"><span data-stu-id="446a5-164">Click Header.</span></span>
20. <span data-ttu-id="446a5-165">Klicka på Godkänn för att godkänna strukturlistor.</span><span class="sxs-lookup"><span data-stu-id="446a5-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="446a5-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-166">Click OK.</span></span>
22. <span data-ttu-id="446a5-167">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="446a5-167">Click Approve.</span></span>
    * <span data-ttu-id="446a5-168">Knappen Godkänn finns i verktygsfältet i avsnittet för strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="446a5-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="446a5-169">Om den inte syns klickar du på rubriken i det övre högra hörnet av sidan för strukturlista för att visa Godkänn.</span><span class="sxs-lookup"><span data-stu-id="446a5-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="446a5-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="446a5-170">Click OK.</span></span>
24. <span data-ttu-id="446a5-171">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="446a5-171">Click Activate.</span></span>
25. <span data-ttu-id="446a5-172">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-172">Close the page.</span></span>
26. <span data-ttu-id="446a5-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-173">Close the page.</span></span>
27. <span data-ttu-id="446a5-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="446a5-174">Close the page.</span></span>

