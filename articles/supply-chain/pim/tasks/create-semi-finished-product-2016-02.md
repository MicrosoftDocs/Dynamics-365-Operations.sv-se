--- 
title: "Skapa en halvfärdig produkt (februari 2016)"
description: "Den här uppgiften fokuserar på att skapa en halvfärdig produkt."
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
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-semi-finished-product-february-2016"></a><span data-ttu-id="056c7-103">Skapa en halvfärdig produkt (februari 2016)</span><span class="sxs-lookup"><span data-stu-id="056c7-103">Create a semi-finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="056c7-104">Den här uppgiften fokuserar på att skapa en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="056c7-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="056c7-105">Detta är den andra uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="056c7-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="056c7-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="056c7-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="056c7-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="056c7-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="056c7-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="056c7-108">Click New.</span></span>
3. <span data-ttu-id="056c7-109">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="056c7-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="056c7-110">Ange BOM_2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="056c7-111">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="056c7-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-112">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="056c7-112">Select STD.</span></span> <span data-ttu-id="056c7-113">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="056c7-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="056c7-114">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="056c7-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-115">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="056c7-115">For example, select Audio.</span></span> <span data-ttu-id="056c7-116">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="056c7-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="056c7-117">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="056c7-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-118">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="056c7-118">Select SiteWH.</span></span> <span data-ttu-id="056c7-119">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="056c7-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="056c7-120">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="056c7-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-121">Spårningsdimensioner kommer inte att användas i det här exemplet; välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="056c7-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="056c7-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="056c7-122">Click OK.</span></span>
9. <span data-ttu-id="056c7-123">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="056c7-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="056c7-124">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="056c7-124">Click Default order settings.</span></span>
11. <span data-ttu-id="056c7-125">Välj "Produktion" i fältet för förvald ordertyp.</span><span class="sxs-lookup"><span data-stu-id="056c7-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="056c7-126">Eftersom detta är en halvfärdig produkt som ska tillverkas, välj Produktion.</span><span class="sxs-lookup"><span data-stu-id="056c7-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="056c7-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="056c7-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="056c7-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="056c7-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="056c7-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="056c7-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="056c7-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="056c7-133">Close the page.</span></span>
16. <span data-ttu-id="056c7-134">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="056c7-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="056c7-135">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="056c7-135">Click Item price.</span></span>
18. <span data-ttu-id="056c7-136">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="056c7-136">Click New.</span></span>
19. <span data-ttu-id="056c7-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="056c7-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="056c7-138">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="056c7-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-139">Välj Version 10 för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="056c7-140">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="056c7-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-141">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="056c7-142">Ange Pris som "10".</span><span class="sxs-lookup"><span data-stu-id="056c7-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="056c7-143">Ange ett självkostnadspris på 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="056c7-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="056c7-144">Click Save.</span></span>
24. <span data-ttu-id="056c7-145">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="056c7-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="056c7-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="056c7-146">Close the page.</span></span>
26. <span data-ttu-id="056c7-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="056c7-147">Close the page.</span></span>
27. <span data-ttu-id="056c7-148">Klicka på BOM_2 för att öppna.</span><span class="sxs-lookup"><span data-stu-id="056c7-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="056c7-149">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="056c7-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="056c7-150">Ange eller välj ett värde i fältet Kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="056c7-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="056c7-151">Välj Kostnadsgrupp M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="056c7-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="056c7-152">Använd genvägen för att spara en post.</span><span class="sxs-lookup"><span data-stu-id="056c7-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="056c7-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="056c7-153">Close the page.</span></span>


