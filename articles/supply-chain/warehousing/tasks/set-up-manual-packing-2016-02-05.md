--- 
title: "Ställ in manuell förpackning (enbart februari och maj 2016)"
description: "Förpackningsprocessen låter dig validera och packa produkter i behållare."
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="83cf2-103">Ställ in manuell förpackning (enbart februari och maj 2016)</span><span class="sxs-lookup"><span data-stu-id="83cf2-103">Set up manual packing (February & May 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="83cf2-104">Förpackningsprocessen låter dig validera och packa produkter i behållare.</span><span class="sxs-lookup"><span data-stu-id="83cf2-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="83cf2-105">I denna process plockar lagerarbetare produkter från lagringsplatserna och flyttar dem till en förpackningsstation där de kontrollerar artikelkvantiteterna och typerna och tilldelar dem en lämplig behållare.</span><span class="sxs-lookup"><span data-stu-id="83cf2-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="83cf2-106">När en behållare är helt ilastad, kan du stänga den och flytta den till utlastningsplatserna och produkterna är redo att skeppas.</span><span class="sxs-lookup"><span data-stu-id="83cf2-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="83cf2-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="83cf2-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="83cf2-108">Konfigurera platsprofiler</span><span class="sxs-lookup"><span data-stu-id="83cf2-108">Set up location profiles</span></span>
1. <span data-ttu-id="83cf2-109">Gå till Lagerstyrning > Inställningar > Lagerställe > Platsprofiler.</span><span class="sxs-lookup"><span data-stu-id="83cf2-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="83cf2-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="83cf2-110">Click New.</span></span>
    * <span data-ttu-id="83cf2-111">Platsprofilen används för emballagestationer och innehåller information och regler för en plats.</span><span class="sxs-lookup"><span data-stu-id="83cf2-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="83cf2-112">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="83cf2-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cf2-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="83cf2-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="83cf2-114">Ange eller välj ett värde i fältet Platsformat.</span><span class="sxs-lookup"><span data-stu-id="83cf2-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="83cf2-115">Ange eller välj ett värde i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="83cf2-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="83cf2-116">Välj Ja i fältet Tillåt blandade artiklar.</span><span class="sxs-lookup"><span data-stu-id="83cf2-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="83cf2-117">Välj Ja i fältet Tillåt blandade lagerstatusar.</span><span class="sxs-lookup"><span data-stu-id="83cf2-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="83cf2-118">Välj Ja i fältet Åsidosättningsregler för batchdagar.</span><span class="sxs-lookup"><span data-stu-id="83cf2-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="83cf2-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83cf2-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="83cf2-120">Ställ in parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="83cf2-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="83cf2-121">Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="83cf2-122">Klicka på fliken Förpackning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="83cf2-123">Ange eller välj ett värde i fältet Profil-ID för förpackningsplats.</span><span class="sxs-lookup"><span data-stu-id="83cf2-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="83cf2-124">Välj vilken platsprofil som du vill använda till förpackning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="83cf2-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83cf2-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="83cf2-126">Ställ in behållartyper</span><span class="sxs-lookup"><span data-stu-id="83cf2-126">Set up container types</span></span>
1. <span data-ttu-id="83cf2-127">Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="83cf2-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="83cf2-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="83cf2-128">Click New.</span></span>
    * <span data-ttu-id="83cf2-129">Du kan definiera vilka typer av behållare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="83cf2-129">You can define the types of containers to use.</span></span> <span data-ttu-id="83cf2-130">Du kan ange de fysiska dimensionerna på behållaren, inklusive taravikt, högsta vikt, högsta volym, längd, bredd och vikt.</span><span class="sxs-lookup"><span data-stu-id="83cf2-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="83cf2-131">Attribut är anpassade fält som gör att du kan lägga till fler dimensioner på behållaretypen.</span><span class="sxs-lookup"><span data-stu-id="83cf2-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="83cf2-132">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="83cf2-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="83cf2-133">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cf2-134">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="83cf2-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="83cf2-135">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="83cf2-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="83cf2-136">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="83cf2-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="83cf2-137">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="83cf2-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="83cf2-138">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="83cf2-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="83cf2-139">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="83cf2-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="83cf2-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="83cf2-140">Click Save.</span></span>
12. <span data-ttu-id="83cf2-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83cf2-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="83cf2-142">Ställa in förpackningsprofiler</span><span class="sxs-lookup"><span data-stu-id="83cf2-142">Set up packing profiles</span></span>
1. <span data-ttu-id="83cf2-143">Gå till Lagerstyrning > Inställningar > Förpackning > Förpackningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="83cf2-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="83cf2-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="83cf2-144">Click New.</span></span>
3. <span data-ttu-id="83cf2-145">Ange ett värde i fältet Förpackningsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="83cf2-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cf2-146">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cf2-147">Ange eller välj ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="83cf2-148">Ett profil-ID för stäng behållare är valfri och är standardprofil för stängd behållare för denna förpackningsprofil.</span><span class="sxs-lookup"><span data-stu-id="83cf2-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="83cf2-149">Ange ett alternativ i fältet Läge för behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="83cf2-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="83cf2-150">Det här alternativet bestämmer om en behållar-ID genereras automatiskt när en behållare skapas, eller om en behållar-ID ska skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="83cf2-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="83cf2-151">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="83cf2-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="83cf2-152">Behållaretypen ska användas som standard när en ny behållare skapas.</span><span class="sxs-lookup"><span data-stu-id="83cf2-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="83cf2-153">Markera kryssrutan Skapa behållare automatiskt när behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="83cf2-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="83cf2-154">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="83cf2-154">Click Save.</span></span>
10. <span data-ttu-id="83cf2-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="83cf2-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="83cf2-156">Ställa in en profiler för behållarstängning</span><span class="sxs-lookup"><span data-stu-id="83cf2-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="83cf2-157">Gå till Lagerstyrning > Inställningar > Behållare > Profiler för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="83cf2-158">Profiler för behållarstängning definierar vad som händer när en behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="83cf2-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="83cf2-159">Du kan ställa in flera profiler för slutna behållare.</span><span class="sxs-lookup"><span data-stu-id="83cf2-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="83cf2-160">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="83cf2-160">Click New.</span></span>
3. <span data-ttu-id="83cf2-161">Ange ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="83cf2-162">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="83cf2-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83cf2-163">Markera ett alternativ i fältet Manifest.</span><span class="sxs-lookup"><span data-stu-id="83cf2-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="83cf2-164">Ange om ett manifest ska utföras när du stänger behållare eller när du bekräftar försändelsen.</span><span class="sxs-lookup"><span data-stu-id="83cf2-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="83cf2-165">Observera att manifest kräver Transporthantering.</span><span class="sxs-lookup"><span data-stu-id="83cf2-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="83cf2-166">Manifest måste implementeras i transportmotorerna för att den ska fungera.</span><span class="sxs-lookup"><span data-stu-id="83cf2-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="83cf2-167">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="83cf2-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="83cf2-168">Ange eller välj ett värde i fältet Standardplats för slutgiltig leverans.</span><span class="sxs-lookup"><span data-stu-id="83cf2-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="83cf2-169">Detta kommer att vara platsen till vilken produkterna ska flyttas till, efter att behållarna har stängts.</span><span class="sxs-lookup"><span data-stu-id="83cf2-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="83cf2-170">Denna plats måste ha en platsprofil definierad i lagerställeparametrar.</span><span class="sxs-lookup"><span data-stu-id="83cf2-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="83cf2-171">Ange eller välj ett värde i fältet Viktenhet.</span><span class="sxs-lookup"><span data-stu-id="83cf2-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="83cf2-172">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="83cf2-172">Click Save.</span></span>


