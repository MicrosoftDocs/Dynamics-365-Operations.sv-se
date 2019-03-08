---
title: Skapa processaktiviteter för lean manufacturing
description: Skapa en processaktivitet för lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fa4d7fe2345d54faf405086a1e1bef599265470b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "345224"
---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="45603-103">Skapa processaktiviteter för lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="45603-103">Create process activities for lean manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="45603-104">Skapa en processaktivitet för lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="45603-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="45603-105">Förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="45603-105">Prerequisites:</span></span> 

1. <span data-ttu-id="45603-106">Ett produktionsflöde och en version som inte är aktiv måste skapas.</span><span class="sxs-lookup"><span data-stu-id="45603-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="45603-107">En arbetsgrupp måste skapas.</span><span class="sxs-lookup"><span data-stu-id="45603-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="45603-108">Hitta produktionsflödesversionen</span><span class="sxs-lookup"><span data-stu-id="45603-108">Find the production flow version</span></span>
1. <span data-ttu-id="45603-109">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="45603-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="45603-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="45603-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="45603-112">Skapa en ny aktivitet</span><span class="sxs-lookup"><span data-stu-id="45603-112">Create a new activity</span></span>
1. <span data-ttu-id="45603-113">Klicka på Aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="45603-113">Click Activities.</span></span>
    * <span data-ttu-id="45603-114">Kontrollera att det valda produktionsflödet har en version i utkast och välj den version.</span><span class="sxs-lookup"><span data-stu-id="45603-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="45603-115">Klicka på Skapa en ny planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="45603-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="45603-116">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="45603-116">Click Next.</span></span>
4. <span data-ttu-id="45603-117">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="45603-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="45603-118">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="45603-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="45603-119">Observera att namnet måste vara unikt för ett visst produktionsflöde för alla versioner.</span><span class="sxs-lookup"><span data-stu-id="45603-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="45603-120">Ange ett nummer i fältet Processkvantitet.</span><span class="sxs-lookup"><span data-stu-id="45603-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="45603-121">Observera att oavsett vilken jobbkvantitet som ska bearbetas så är detta den minsta kvantiteten per jobb för att beräkna arbetskostnaden.</span><span class="sxs-lookup"><span data-stu-id="45603-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="45603-122">Om jobbkvantiteter avviker från denna kvantitet skapas arbetskostnadsavvikelser.</span><span class="sxs-lookup"><span data-stu-id="45603-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="45603-123">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="45603-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="45603-124">Välj arbetsgruppen</span><span class="sxs-lookup"><span data-stu-id="45603-124">Select the work cell</span></span>
1. <span data-ttu-id="45603-125">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="45603-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="45603-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="45603-127">Definiera lageruppdateringarna</span><span class="sxs-lookup"><span data-stu-id="45603-127">Define the inventory updates</span></span>
1. <span data-ttu-id="45603-128">Markera eller avmarkera kryssrutan Uppdatera inleverans för behållning.</span><span class="sxs-lookup"><span data-stu-id="45603-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="45603-129">Om Uppdatera behållning = Nej kan du definiera aktiviteten för att ta emot en halvfärdig produkt (aktiviteten når inte nästa strukturlistenivån).</span><span class="sxs-lookup"><span data-stu-id="45603-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="45603-130">Du kan också välja att förbruka halvfärdiga produkter.</span><span class="sxs-lookup"><span data-stu-id="45603-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="45603-131">Definiera plockningsaktiviteterna</span><span class="sxs-lookup"><span data-stu-id="45603-131">Define the picking activities</span></span>
1. <span data-ttu-id="45603-132">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="45603-132">Click Next.</span></span>
2. <span data-ttu-id="45603-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="45603-134">En standardplockningsaktivitet skapas för inleveransplatsen för den valda arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="45603-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="45603-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="45603-135">Click Add.</span></span>
    * <span data-ttu-id="45603-136">Du kan skapa ytterligare plockningsaktiviteter för specifika produkter, som inte mellanlagras i inleveransaktiviteten för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="45603-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="45603-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="45603-138">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="45603-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="45603-139">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="45603-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="45603-140">Med denna definition plockas allt material som förbrukats i aktiviteten från standardinleveranslagret och standardinleveransplatsen förutom artikeln som definieras i den andra plockningsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="45603-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="45603-141">Den här artikeln plockas från ett annat lagerställe och en annan plats.</span><span class="sxs-lookup"><span data-stu-id="45603-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="45603-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="45603-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="45603-144">Markera eller avmarkera kryssrutan Registerkassation.</span><span class="sxs-lookup"><span data-stu-id="45603-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="45603-145">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="45603-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="45603-146">Definiera aktivitetstiderna</span><span class="sxs-lookup"><span data-stu-id="45603-146">Define the activity times</span></span>
1. <span data-ttu-id="45603-147">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="45603-148">Definitionen av en körning krävs.</span><span class="sxs-lookup"><span data-stu-id="45603-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="45603-149">Körningen används för att beräkna kostnader och genomflödetiderna för kanban-jobben.</span><span class="sxs-lookup"><span data-stu-id="45603-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="45603-150">Körningar används inte för att beräkna kapacitetsbeläggning och förbrukning; detta beräknas med cykeltider, som hämtas från uppgiften för produktionsflödesversion.</span><span class="sxs-lookup"><span data-stu-id="45603-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="45603-151">Ange ett värde i fältet Tid.</span><span class="sxs-lookup"><span data-stu-id="45603-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="45603-152">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="45603-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="45603-153">Välj tidsenhet.</span><span class="sxs-lookup"><span data-stu-id="45603-153">Select the Time unit.</span></span>
5. <span data-ttu-id="45603-154">Ange ett värde i fältet Per kvantitet.</span><span class="sxs-lookup"><span data-stu-id="45603-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="45603-155">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45603-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="45603-156">Kötider är valfria.</span><span class="sxs-lookup"><span data-stu-id="45603-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="45603-157">Ange ett värde i fältet Tid.</span><span class="sxs-lookup"><span data-stu-id="45603-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="45603-158">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="45603-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="45603-159">Välj tidsenhet.</span><span class="sxs-lookup"><span data-stu-id="45603-159">Select the Time unit.</span></span>
10. <span data-ttu-id="45603-160">Ange ett värde i fältet Per kvantitet.</span><span class="sxs-lookup"><span data-stu-id="45603-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="45603-161">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="45603-161">Click Next.</span></span>
12. <span data-ttu-id="45603-162">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="45603-162">Click Finish.</span></span>
13. <span data-ttu-id="45603-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45603-163">Close the page.</span></span>

