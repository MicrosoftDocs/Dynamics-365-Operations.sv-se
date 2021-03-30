---
title: Skapa manuell förpackning (februari 2016 och maj 2016)
description: Förpackningsprocessen låter dig validera och packa produkter i behållare.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 359d3e6d9b6e2ce5439c36ea52ebad4ce7a3e2c9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211728"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="91ee9-103">Skapa manuell förpackning (februari 2016 och maj 2016)</span><span class="sxs-lookup"><span data-stu-id="91ee9-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="91ee9-104">Förpackningsprocessen låter dig validera och packa produkter i behållare.</span><span class="sxs-lookup"><span data-stu-id="91ee9-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="91ee9-105">I denna process plockar lagerarbetare produkter från lagringsplatserna och flyttar dem till en förpackningsstation där de kontrollerar artikelkvantiteterna och typerna och tilldelar dem en lämplig behållare.</span><span class="sxs-lookup"><span data-stu-id="91ee9-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="91ee9-106">När en behållare är helt ilastad, kan du stänga den och flytta den till utlastningsplatserna och produkterna är redo att skeppas.</span><span class="sxs-lookup"><span data-stu-id="91ee9-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="91ee9-107">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="91ee9-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="91ee9-108">Denna procedur är endast avsedd för versionerna för februari och maj 2016 av Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="91ee9-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="91ee9-109">Konfigurera platsprofiler</span><span class="sxs-lookup"><span data-stu-id="91ee9-109">Set up location profiles</span></span>
1. <span data-ttu-id="91ee9-110">Gå till Lagerstyrning > Inställningar > Lagerställe > Platsprofiler.</span><span class="sxs-lookup"><span data-stu-id="91ee9-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="91ee9-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91ee9-111">Click New.</span></span>
    * <span data-ttu-id="91ee9-112">Platsprofilen används för emballagestationer och innehåller information och regler för en plats.</span><span class="sxs-lookup"><span data-stu-id="91ee9-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="91ee9-113">Skriv ett värde i fältet Platsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="91ee9-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="91ee9-114">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="91ee9-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="91ee9-115">Ange eller välj ett värde i fältet Platsformat.</span><span class="sxs-lookup"><span data-stu-id="91ee9-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="91ee9-116">Ange eller välj ett värde i fältet Platstyp.</span><span class="sxs-lookup"><span data-stu-id="91ee9-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="91ee9-117">Välj Ja i fältet Tillåt blandade artiklar.</span><span class="sxs-lookup"><span data-stu-id="91ee9-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="91ee9-118">Välj Ja i fältet Tillåt blandade lagerstatusar.</span><span class="sxs-lookup"><span data-stu-id="91ee9-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="91ee9-119">Välj Ja i fältet Åsidosättningsregler för batchdagar.</span><span class="sxs-lookup"><span data-stu-id="91ee9-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="91ee9-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91ee9-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="91ee9-121">Ställ in parametrar för lagerstyrning</span><span class="sxs-lookup"><span data-stu-id="91ee9-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="91ee9-122">Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="91ee9-123">Klicka på fliken Förpackning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="91ee9-124">Ange eller välj ett värde i fältet Profil-ID för förpackningsplats.</span><span class="sxs-lookup"><span data-stu-id="91ee9-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="91ee9-125">Välj vilken platsprofil som du vill använda till förpackning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="91ee9-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91ee9-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="91ee9-127">Ställ in behållartyper</span><span class="sxs-lookup"><span data-stu-id="91ee9-127">Set up container types</span></span>
1. <span data-ttu-id="91ee9-128">Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="91ee9-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="91ee9-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91ee9-129">Click New.</span></span>
    * <span data-ttu-id="91ee9-130">Du kan definiera vilka typer av behållare som ska användas.</span><span class="sxs-lookup"><span data-stu-id="91ee9-130">You can define the types of containers to use.</span></span> <span data-ttu-id="91ee9-131">Du kan ange de fysiska dimensionerna på behållaren, inklusive taravikt, högsta vikt, högsta volym, längd, bredd och vikt.</span><span class="sxs-lookup"><span data-stu-id="91ee9-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="91ee9-132">Attribut är anpassade fält som gör att du kan lägga till fler dimensioner på behållaretypen.</span><span class="sxs-lookup"><span data-stu-id="91ee9-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="91ee9-133">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="91ee9-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="91ee9-134">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="91ee9-135">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="91ee9-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="91ee9-136">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="91ee9-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="91ee9-137">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="91ee9-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="91ee9-138">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="91ee9-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="91ee9-139">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="91ee9-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="91ee9-140">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="91ee9-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="91ee9-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91ee9-141">Click Save.</span></span>
12. <span data-ttu-id="91ee9-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91ee9-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="91ee9-143">Ställa in förpackningsprofiler</span><span class="sxs-lookup"><span data-stu-id="91ee9-143">Set up packing profiles</span></span>
1. <span data-ttu-id="91ee9-144">Gå till Lagerstyrning > Inställningar > Förpackning > Förpackningsprofiler.</span><span class="sxs-lookup"><span data-stu-id="91ee9-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="91ee9-145">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91ee9-145">Click New.</span></span>
3. <span data-ttu-id="91ee9-146">Ange ett värde i fältet Förpackningsprofil-ID.</span><span class="sxs-lookup"><span data-stu-id="91ee9-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="91ee9-147">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="91ee9-148">Ange eller välj ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="91ee9-149">Ett profil-ID för stäng behållare är valfri och är standardprofil för stängd behållare för denna förpackningsprofil.</span><span class="sxs-lookup"><span data-stu-id="91ee9-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="91ee9-150">Ange ett alternativ i fältet Läge för behållar-ID.</span><span class="sxs-lookup"><span data-stu-id="91ee9-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="91ee9-151">Det här alternativet bestämmer om en behållar-ID genereras automatiskt när en behållare skapas, eller om en behållar-ID ska skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="91ee9-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="91ee9-152">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="91ee9-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="91ee9-153">Behållaretypen ska användas som standard när en ny behållare skapas.</span><span class="sxs-lookup"><span data-stu-id="91ee9-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="91ee9-154">Markera kryssrutan Skapa behållare automatiskt när behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="91ee9-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="91ee9-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91ee9-155">Click Save.</span></span>
10. <span data-ttu-id="91ee9-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="91ee9-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="91ee9-157">Ställa in en profiler för behållarstängning</span><span class="sxs-lookup"><span data-stu-id="91ee9-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="91ee9-158">Gå till Lagerstyrning > Inställningar > Behållare > Profiler för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="91ee9-159">Profiler för behållarstängning definierar vad som händer när en behållare stängs.</span><span class="sxs-lookup"><span data-stu-id="91ee9-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="91ee9-160">Du kan ställa in flera profiler för slutna behållare.</span><span class="sxs-lookup"><span data-stu-id="91ee9-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="91ee9-161">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="91ee9-161">Click New.</span></span>
3. <span data-ttu-id="91ee9-162">Ange ett värde i fältet Profil-ID för behållarstängning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="91ee9-163">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91ee9-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="91ee9-164">Markera ett alternativ i fältet Manifest.</span><span class="sxs-lookup"><span data-stu-id="91ee9-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="91ee9-165">Ange om ett manifest ska utföras när du stänger behållare eller när du bekräftar försändelsen.</span><span class="sxs-lookup"><span data-stu-id="91ee9-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="91ee9-166">Observera att manifest kräver Transporthantering.</span><span class="sxs-lookup"><span data-stu-id="91ee9-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="91ee9-167">Manifest måste implementeras i transportmotorerna för att den ska fungera.</span><span class="sxs-lookup"><span data-stu-id="91ee9-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="91ee9-168">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="91ee9-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="91ee9-169">Ange eller välj ett värde i fältet Standardplats för slutgiltig leverans.</span><span class="sxs-lookup"><span data-stu-id="91ee9-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="91ee9-170">Detta kommer att vara platsen till vilken produkterna ska flyttas till, efter att behållarna har stängts.</span><span class="sxs-lookup"><span data-stu-id="91ee9-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="91ee9-171">Denna plats måste ha en platsprofil definierad i lagerställeparametrar.</span><span class="sxs-lookup"><span data-stu-id="91ee9-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="91ee9-172">Ange eller välj ett värde i fältet Viktenhet.</span><span class="sxs-lookup"><span data-stu-id="91ee9-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="91ee9-173">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="91ee9-173">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]