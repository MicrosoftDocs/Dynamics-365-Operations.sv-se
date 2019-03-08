---
title: Skapa en halvfärdig produkt (enbart februari 2016)
description: Den här uppgiften fokuserar på att skapa en halvfärdig produkt.
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
ms.openlocfilehash: 76fcba3732879f85c9bf0faa6d2481b9c5313a17
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "358955"
---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="f911e-103">Skapa en halvfärdig produkt (enbart februari 2016)</span><span class="sxs-lookup"><span data-stu-id="f911e-103">Create a semi-finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f911e-104">Den här uppgiften fokuserar på att skapa en halvfärdig produkt.</span><span class="sxs-lookup"><span data-stu-id="f911e-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="f911e-105">Detta är den andra uppgiften i beräkningsserien för strukturlista.</span><span class="sxs-lookup"><span data-stu-id="f911e-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="f911e-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="f911e-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="f911e-107">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="f911e-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f911e-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f911e-108">Click New.</span></span>
3. <span data-ttu-id="f911e-109">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="f911e-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f911e-110">Ange BOM_2 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="f911e-111">Ange eller välj ett värde i fältet Artikelmodellgrupp.</span><span class="sxs-lookup"><span data-stu-id="f911e-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-112">Välj STD.</span><span class="sxs-lookup"><span data-stu-id="f911e-112">Select STD.</span></span> <span data-ttu-id="f911e-113">STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="f911e-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="f911e-114">Ange eller välj ett värde i fältet Artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="f911e-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-115">Välj till exempel "Ljud".</span><span class="sxs-lookup"><span data-stu-id="f911e-115">For example, select Audio.</span></span> <span data-ttu-id="f911e-116">Detta påverkar inte kostnadsberäkningarna.</span><span class="sxs-lookup"><span data-stu-id="f911e-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="f911e-117">Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f911e-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-118">Välj SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f911e-118">Select SiteWH.</span></span> <span data-ttu-id="f911e-119">Endast plats och lagerställe används för detta exempel.</span><span class="sxs-lookup"><span data-stu-id="f911e-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="f911e-120">Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f911e-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-121">Spårningsdimensioner kommer inte att användas i det här exemplet; välj Ingen.</span><span class="sxs-lookup"><span data-stu-id="f911e-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="f911e-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f911e-122">Click OK.</span></span>
9. <span data-ttu-id="f911e-123">Klicka på Hantera inventering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f911e-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="f911e-124">Visa standardorderinställningar.</span><span class="sxs-lookup"><span data-stu-id="f911e-124">Click Default order settings.</span></span>
11. <span data-ttu-id="f911e-125">Välj "Produktion" i fältet för förvald ordertyp.</span><span class="sxs-lookup"><span data-stu-id="f911e-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="f911e-126">Eftersom detta är en halvfärdig produkt som ska tillverkas, välj Produktion.</span><span class="sxs-lookup"><span data-stu-id="f911e-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="f911e-127">Ange eller välj ett värde i fältet Inköpsplats.</span><span class="sxs-lookup"><span data-stu-id="f911e-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-128">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f911e-129">Ange eller välj ett värde i fältet Lagerplats.</span><span class="sxs-lookup"><span data-stu-id="f911e-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-130">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="f911e-131">Ange eller välj ett värde i fältet Försäljningsplats.</span><span class="sxs-lookup"><span data-stu-id="f911e-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-132">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="f911e-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f911e-133">Close the page.</span></span>
16. <span data-ttu-id="f911e-134">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f911e-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="f911e-135">Klicka på Artikelpris.</span><span class="sxs-lookup"><span data-stu-id="f911e-135">Click Item price.</span></span>
18. <span data-ttu-id="f911e-136">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f911e-136">Click New.</span></span>
19. <span data-ttu-id="f911e-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f911e-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="f911e-138">Ange eller välj ett värde i fältet Version.</span><span class="sxs-lookup"><span data-stu-id="f911e-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-139">Välj Version 10 för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="f911e-140">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="f911e-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-141">Välj Plats 1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="f911e-142">Ange Pris som "10".</span><span class="sxs-lookup"><span data-stu-id="f911e-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="f911e-143">Ange ett självkostnadspris på 10 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="f911e-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f911e-144">Click Save.</span></span>
24. <span data-ttu-id="f911e-145">Klicka på Aktivera väntande pris(er).</span><span class="sxs-lookup"><span data-stu-id="f911e-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="f911e-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f911e-146">Close the page.</span></span>
26. <span data-ttu-id="f911e-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f911e-147">Close the page.</span></span>
27. <span data-ttu-id="f911e-148">Klicka på BOM_2 för att öppna.</span><span class="sxs-lookup"><span data-stu-id="f911e-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="f911e-149">Expandera avsnittet Hantera kostnader.</span><span class="sxs-lookup"><span data-stu-id="f911e-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="f911e-150">Ange eller välj ett värde i fältet Kostnadsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f911e-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="f911e-151">Välj Kostnadsgrupp M1 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="f911e-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="f911e-152">Använd genvägen för att spara en post.</span><span class="sxs-lookup"><span data-stu-id="f911e-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="f911e-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f911e-153">Close the page.</span></span>

