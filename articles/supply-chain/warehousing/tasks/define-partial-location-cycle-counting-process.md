---
title: 'Definiera rullande inventering av del av platser '
description: När du använder planer för rullande inventering för att skapa inventeringsarbete kan du styra den faktiska inventeringen genom att begära att enbart vissa produkter eller produktvarianter inventeras i stället för all lagerbehållning på platsen.
author: ShylaThompson
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcda301934c6ccc06f17ed8ae13c52754336d2ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830917"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="a6b81-103">Definiera rullande inventering av del av platser </span><span class="sxs-lookup"><span data-stu-id="a6b81-103">Define partial location cycle counting process</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a6b81-104">När du använder planer för rullande inventering för att skapa inventeringsarbete kan du styra den faktiska inventeringen genom att begära att enbart vissa produkter eller produktvarianter inventeras i stället för all lagerbehållning på platsen.</span><span class="sxs-lookup"><span data-stu-id="a6b81-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="a6b81-105">Genom att filtrera efter specifika produkter kan lagerchefen minska granskningsomkostnaderna, undvika konsolideringsmisstag och spara tid.</span><span class="sxs-lookup"><span data-stu-id="a6b81-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="a6b81-106">Vanligtvis utför en lagerchef inställningsuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="a6b81-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="a6b81-107">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.</span><span class="sxs-lookup"><span data-stu-id="a6b81-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="a6b81-108">Skapa en arbetsmall för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="a6b81-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="a6b81-109">Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.</span><span class="sxs-lookup"><span data-stu-id="a6b81-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="a6b81-110">Välj Rullande inventering i fältet Typ av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a6b81-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="a6b81-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6b81-111">Click New.</span></span>
4. <span data-ttu-id="a6b81-112">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="a6b81-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="a6b81-113">Sorteringsordningen är från det lägsta talet till det högsta talet.</span><span class="sxs-lookup"><span data-stu-id="a6b81-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="a6b81-114">Värdet måste vara större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a6b81-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="a6b81-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="a6b81-116">Skriv ett värde i fältet Arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="a6b81-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="a6b81-117">Skriv ett värde i fältet Beskrivning av arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="a6b81-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="a6b81-118">Ange eller välj ett värde i fältet ID för arbetspool.</span><span class="sxs-lookup"><span data-stu-id="a6b81-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="a6b81-119">Välj ett tal i fältet Arbetsprioritet.</span><span class="sxs-lookup"><span data-stu-id="a6b81-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="a6b81-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6b81-120">Click Save.</span></span>
11. <span data-ttu-id="a6b81-121">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6b81-121">Click New.</span></span>
12. <span data-ttu-id="a6b81-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a6b81-123">Välj Inventering i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="a6b81-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="a6b81-124">I fältet Arbetsklass-ID, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="a6b81-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="a6b81-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6b81-125">Click Save.</span></span>
16. <span data-ttu-id="a6b81-126">Klicka på Arbetsradsuppdelningar.</span><span class="sxs-lookup"><span data-stu-id="a6b81-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="a6b81-127">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6b81-127">Click New.</span></span>
18. <span data-ttu-id="a6b81-128">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="a6b81-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="a6b81-129">Sorteringsordningen är från det lägsta talet till det högsta talet.</span><span class="sxs-lookup"><span data-stu-id="a6b81-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="a6b81-130">Värdet måste vara större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a6b81-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="a6b81-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6b81-131">Click Save.</span></span>
20. <span data-ttu-id="a6b81-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-132">Close the page.</span></span>
21. <span data-ttu-id="a6b81-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="a6b81-134">Skapa en plan för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="a6b81-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="a6b81-135">Gå till Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a6b81-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="a6b81-136">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6b81-136">Click New.</span></span>
3. <span data-ttu-id="a6b81-137">Skriv ett värde i fältet Plan-ID för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a6b81-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="a6b81-138">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a6b81-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a6b81-139">Ange ett värde i fältet Högsta antal rullande inventeringar.</span><span class="sxs-lookup"><span data-stu-id="a6b81-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="a6b81-140">Ange eller välj ett värde i fältet Arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="a6b81-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="a6b81-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6b81-141">Click New.</span></span>
8. <span data-ttu-id="a6b81-142">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="a6b81-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="a6b81-143">Sorteringsordningen är från det lägsta talet till det högsta talet.</span><span class="sxs-lookup"><span data-stu-id="a6b81-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="a6b81-144">Värdet måste vara större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a6b81-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="a6b81-145">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a6b81-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="a6b81-146">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a6b81-146">Click Save.</span></span>
11. <span data-ttu-id="a6b81-147">Klicka på Definiera produktfråga.</span><span class="sxs-lookup"><span data-stu-id="a6b81-147">Click Define product query.</span></span>
12. <span data-ttu-id="a6b81-148">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a6b81-149">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a6b81-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="a6b81-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a6b81-150">Click OK.</span></span>
15. <span data-ttu-id="a6b81-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6b81-151">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]