--- 
title: "Ställ in en arbetsmall för inköpsorder"
description: "I den här proceduren fokuseras på inställningarna av en enkel arbetsmall som ska användas när mottagna artiklar inlagras."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1e2dcd25fc50c4fd9568175246004899fc3e7360
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="a88a4-103">Ställ in en arbetsmall för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="a88a4-103">Set up a work template for purchase orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a88a4-104">I den här proceduren fokuseras på inställningarna av en enkel arbetsmall som ska användas när mottagna artiklar inlagras.</span><span class="sxs-lookup"><span data-stu-id="a88a4-104">This procedure focuses on the set up of a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="a88a4-105">Arbetsmallar bestämmer instruktionsuppsättning som visas för lagerställearbetaren på en mobil enhet när artiklar flyttas från inleveransområdet.</span><span class="sxs-lookup"><span data-stu-id="a88a4-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="a88a4-106">Du kan använda den här proceduren med uppgifterna i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a88a4-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="a88a4-107">Innan du startar guiden skapar du ett arbetspool-id.</span><span class="sxs-lookup"><span data-stu-id="a88a4-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="a88a4-108">I det här exemplet används arbetspool-id:t Inkommande.</span><span class="sxs-lookup"><span data-stu-id="a88a4-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="a88a4-109">Den här proceduren är avsedd för lagerchefen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="a88a4-110">Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.</span><span class="sxs-lookup"><span data-stu-id="a88a4-110">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="a88a4-111">Välj Inköpsorder i fältet Typ av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a88a4-111">In the Work order type field, select 'Purchase orders'.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="a88a4-112">Skapa ett arbetsmallshuvud</span><span class="sxs-lookup"><span data-stu-id="a88a4-112">Create a work template header</span></span>
1. <span data-ttu-id="a88a4-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a88a4-113">Click New.</span></span>
2. <span data-ttu-id="a88a4-114">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="a88a4-114">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="a88a4-115">I den här sekvensen utvärderas arbetsmallen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="a88a4-116">Du kan ändra sekvensen vid behov.</span><span class="sxs-lookup"><span data-stu-id="a88a4-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="a88a4-117">Skriv ett värde i fältet Arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="a88a4-117">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="a88a4-118">Detta är den unika identifieraren för mallen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="a88a4-119">Skriv ett värde i fältet Beskrivning av arbetsmall.</span><span class="sxs-lookup"><span data-stu-id="a88a4-119">In the Work template description field, type a value.</span></span>
    * <span data-ttu-id="a88a4-120">Alternativet Giltig markeras inte förrän du har fyllt i all information som krävs av mallen och klickat på Spara.</span><span class="sxs-lookup"><span data-stu-id="a88a4-120">The Valid option will not be checked until you’ve completed all the information that's needed by the template and have then clicked Save.</span></span>  
    * <span data-ttu-id="a88a4-121">En arbetsorder av typen Inköpsorder kan inte bearbetas automatiskt, så lämna alternativet Bearbeta automatiskt med värdet Nej.</span><span class="sxs-lookup"><span data-stu-id="a88a4-121">A work order of type Purchase order cannot be automatically processed, so leave the  Automatically process option set to No.</span></span>  
5. <span data-ttu-id="a88a4-122">Skriv ett värde i fältet ID för arbetspool.</span><span class="sxs-lookup"><span data-stu-id="a88a4-122">In the Work pool ID field, type a value.</span></span>
    * <span data-ttu-id="a88a4-123">Id:n för arbetspooler gör att du kan strukturera arbetsuppgifter i grupper.</span><span class="sxs-lookup"><span data-stu-id="a88a4-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="a88a4-124">Det värde som du som anges här är det förvalda värdet för alla arbetsuppgifter som skapas med den här mallen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-124">The value that you set here will be the default value for any work that’s created using this template.</span></span>  
6. <span data-ttu-id="a88a4-125">Ange 1 i fältet Arbetsprioritet.</span><span class="sxs-lookup"><span data-stu-id="a88a4-125">In the Work priority field, enter '1'.</span></span>
    * <span data-ttu-id="a88a4-126">Detta indikerar värdet för arbetsuppgiften och värdet du anger här är standardinställningen för alla arbetsuppgifter som skapas med hjälp av den här mallen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="a88a4-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a88a4-127">Click Save.</span></span>
    * <span data-ttu-id="a88a4-128">Du måste spara arbetsmallhuvudet för att knappen Redigera fråga ska bli tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a88a4-128">You must save the work template header before the Edit Query button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="a88a4-129">Ställa in frågan för arbetsmallen</span><span class="sxs-lookup"><span data-stu-id="a88a4-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="a88a4-130">Klicka på Redigera fråga.</span><span class="sxs-lookup"><span data-stu-id="a88a4-130">Click Edit query.</span></span>
    * <span data-ttu-id="a88a4-131">Vi anger en begränsning som innebär att mallen bara kan användas på ett specifikt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a88a4-131">We’ll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="a88a4-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a88a4-132">Click Add.</span></span>
3. <span data-ttu-id="a88a4-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a88a4-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="a88a4-134">Skriv lagerställe i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="a88a4-134">In the Field field, type 'warehouse'.</span></span>
5. <span data-ttu-id="a88a4-135">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a88a4-135">In the Criteria field, type a value.</span></span>
6. <span data-ttu-id="a88a4-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a88a4-136">Click OK.</span></span>
7. <span data-ttu-id="a88a4-137">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="a88a4-137">Click Yes.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="a88a4-138">Ställa in arbetsmallinformation</span><span class="sxs-lookup"><span data-stu-id="a88a4-138">Set work template details</span></span>
1. <span data-ttu-id="a88a4-139">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a88a4-139">Click New.</span></span>
2. <span data-ttu-id="a88a4-140">Välj Välj i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="a88a4-140">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="a88a4-141">Skriv inköp i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="a88a4-141">In the Work class ID field, type 'purchase'.</span></span>
    * <span data-ttu-id="a88a4-142">Arbetsklassen att du som anges här är standardinställningen i alla arbetsrader av typen Välj som skapas med den här mallen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-142">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="a88a4-143">Arbetsklassen kan inte ersättas av arbetsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="a88a4-143">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="a88a4-144">Arbetsklasser används för att begränsa och/eller styra typen arbetsorderrader som en lagerställemedarbetare kan behandla på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="a88a4-144">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="a88a4-145">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a88a4-145">Click New.</span></span>
5. <span data-ttu-id="a88a4-146">Välj Placera i fältet Arbetstyp.</span><span class="sxs-lookup"><span data-stu-id="a88a4-146">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="a88a4-147">Skriv ett värde i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="a88a4-147">In the Work class ID field, type a value.</span></span>
    * <span data-ttu-id="a88a4-148">Instruktionerna för plock och plats är en uppsättning.</span><span class="sxs-lookup"><span data-stu-id="a88a4-148">The pick and put instructions are a set.</span></span> <span data-ttu-id="a88a4-149">Varje plock/platsuppsättning måste ha samma arbetsklass.</span><span class="sxs-lookup"><span data-stu-id="a88a4-149">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="a88a4-150">Använda samma arbetsklass som du gjorde i plockinstruktionen.</span><span class="sxs-lookup"><span data-stu-id="a88a4-150">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="a88a4-151">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a88a4-151">Click Save.</span></span>
    * <span data-ttu-id="a88a4-152">Observera att kryssrutan Giltig nu är markerad.</span><span class="sxs-lookup"><span data-stu-id="a88a4-152">Note that the Valid checkbox is now checked.</span></span>  


