---
title: Skapa manuell förpackning (februari 2016 och maj 2016)
description: Förpackningsprocessen låter dig validera och packa produkter i behållare.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b90b4a71e2447e942dbb4a9645ef93064da630d3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558043"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="18892-103">Skapa manuell förpackning (februari 2016 och maj 2016)</span><span class="sxs-lookup"><span data-stu-id="18892-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="18892-104">Förpackningsprocessen låter dig validera och packa produkter i behållare.</span><span class="sxs-lookup"><span data-stu-id="18892-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="18892-105">I denna process plockar lagerarbetare produkter från lagringsplatserna och flyttar dem till en förpackningsstation där de kontrollerar artikelkvantiteterna och typerna och tilldelar dem en lämplig behållare.</span><span class="sxs-lookup"><span data-stu-id="18892-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="18892-106">När en behållare är helt ilastad, kan du stänga den och flytta den till utlastningsplatserna och produkterna är redo att skeppas.</span><span class="sxs-lookup"><span data-stu-id="18892-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="18892-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="18892-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="18892-108">Denna procedur är endast avsedd för versionerna för februari och maj 2016 av Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="18892-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="18892-109">Konfigurera platsprofiler</span><span class="sxs-lookup"><span data-stu-id="18892-109">Set up location profiles</span></span>
1. <span data-ttu-id="18892-110">Gå till Lagerstyrning > Inställningar > Lagerställe > Platsprofiler.</span><span class="sxs-lookup"><span data-stu-id="18892-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="18892-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18892-111">Click New.</span></span>
    * <span data-ttu-id="18892-112">Platsprofilen används för emballagestationer och innehåller information och regler för en plats.</span><span class="sxs-lookup"><span data-stu-id="18892-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="18892-113">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="18892-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="18892-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="18892-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="18892-115">Ange eller välj ett värde i fältet Platsformat.</span><span class="sxs-lookup"><span data-stu-id="18892-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="18892-116">Ange eller välj ett värde i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="18892-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="18892-117">Välj Ja i fältet Tillåt blandade artiklar.</span><span class="sxs-lookup"><span data-stu-id="18892-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="18892-118">Välj Ja i fältet Tillåt blandade lagerstatusar.</span><span class="sxs-lookup"><span data-stu-id="18892-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="18892-119">Välj Ja i fältet Åsidosättningsregler för batchdagar.</span><span class="sxs-lookup"><span data-stu-id="18892-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="18892-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18892-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="18892-121">Ställ in parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="18892-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="18892-122">Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="18892-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="18892-123">Klicka på fliken Förpackning.</span><span class="sxs-lookup"><span data-stu-id="18892-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="18892-124">Ange eller välj ett värde i fältet Profil-ID för förpackningsplats.</span><span class="sxs-lookup"><span data-stu-id="18892-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="18892-125">Välj vilken platsprofil som du vill använda till förpackning.</span><span class="sxs-lookup"><span data-stu-id="18892-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="18892-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18892-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="18892-127">Ställ in behållartyper</span><span class="sxs-lookup"><span data-stu-id="18892-127">Set up container types</span></span>
1. <span data-ttu-id="18892-128">Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="18892-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="18892-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18892-129">Click New.</span></span>
    * <span data-ttu-id="18892-130">Du kan definiera vilka typer av behållare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="18892-130">You can define the types of containers to use.</span></span> <span data-ttu-id="18892-131">Du kan ange de fysiska dimensionerna på behållaren, inklusive taravikt, högsta vikt, högsta volym, längd, bredd och vikt.</span><span class="sxs-lookup"><span data-stu-id="18892-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="18892-132">Attribut är anpassade fält som gör att du kan lägga till fler dimensioner på behållaretypen.</span><span class="sxs-lookup"><span data-stu-id="18892-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="18892-133">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="18892-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="18892-134">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="18892-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="18892-135">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="18892-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="18892-136">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="18892-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="18892-137">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="18892-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="18892-138">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="18892-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="18892-139">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="18892-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="18892-140">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="18892-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="18892-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="18892-141">Click Save.</span></span>
12. <span data-ttu-id="18892-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18892-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="18892-143">Ställa in förpackningsprofiler</span><span class="sxs-lookup"><span data-stu-id="18892-143">Set up packing profiles</span></span>
1. <span data-ttu-id="18892-144">Gå till Lagerstyrning > Inställningar > Förpackning > Förpackningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="18892-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="18892-145">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18892-145">Click New.</span></span>
3. <span data-ttu-id="18892-146">Ange ett värde i fältet Förpackningsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="18892-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="18892-147">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="18892-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="18892-148">Ange eller välj ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="18892-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="18892-149">Ett profil-ID för stäng behållare är valfri och är standardprofil för stängd behållare för denna förpackningsprofil.</span><span class="sxs-lookup"><span data-stu-id="18892-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="18892-150">Ange ett alternativ i fältet Läge för behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="18892-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="18892-151">Det här alternativet bestämmer om en behållar-ID genereras automatiskt när en behållare skapas, eller om en behållar-ID ska skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="18892-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="18892-152">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="18892-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="18892-153">Behållaretypen ska användas som standard när en ny behållare skapas.</span><span class="sxs-lookup"><span data-stu-id="18892-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="18892-154">Markera kryssrutan Skapa behållare automatiskt när behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="18892-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="18892-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="18892-155">Click Save.</span></span>
10. <span data-ttu-id="18892-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="18892-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="18892-157">Ställa in en profiler för behållarstängning</span><span class="sxs-lookup"><span data-stu-id="18892-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="18892-158">Gå till Lagerstyrning > Inställningar > Behållare > Profiler för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="18892-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="18892-159">Profiler för behållarstängning definierar vad som händer när en behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="18892-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="18892-160">Du kan ställa in flera profiler för slutna behållare.</span><span class="sxs-lookup"><span data-stu-id="18892-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="18892-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="18892-161">Click New.</span></span>
3. <span data-ttu-id="18892-162">Ange ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="18892-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="18892-163">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="18892-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="18892-164">Markera ett alternativ i fältet Manifest.</span><span class="sxs-lookup"><span data-stu-id="18892-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="18892-165">Ange om ett manifest ska utföras när du stänger behållare eller när du bekräftar försändelsen.</span><span class="sxs-lookup"><span data-stu-id="18892-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="18892-166">Observera att manifest kräver Transporthantering.</span><span class="sxs-lookup"><span data-stu-id="18892-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="18892-167">Manifest måste implementeras i transportmotorerna för att den ska fungera.</span><span class="sxs-lookup"><span data-stu-id="18892-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="18892-168">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="18892-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="18892-169">Ange eller välj ett värde i fältet Standardplats för slutgiltig leverans.</span><span class="sxs-lookup"><span data-stu-id="18892-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="18892-170">Detta kommer att vara platsen till vilken produkterna ska flyttas till, efter att behållarna har stängts.</span><span class="sxs-lookup"><span data-stu-id="18892-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="18892-171">Denna plats måste ha en platsprofil definierad i lagerställeparametrar.</span><span class="sxs-lookup"><span data-stu-id="18892-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="18892-172">Ange eller välj ett värde i fältet Viktenhet.</span><span class="sxs-lookup"><span data-stu-id="18892-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="18892-173">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="18892-173">Click Save.</span></span>

