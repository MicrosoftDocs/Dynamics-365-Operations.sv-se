--- 
title: 'Definiera rullande inventering '
description: "Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f9cdb0a7de0199363279c53e817c98085b31fe6b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-cycle-counting"></a><span data-ttu-id="a3fe1-103">Definiera rullande inventering </span><span class="sxs-lookup"><span data-stu-id="a3fe1-103">Define cycle counting</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a3fe1-104">Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="a3fe1-105">Den här uppgiftsinspelningen visar hur du kan ställa in standardarbetsprioriteten för inventering; aktivera ett menykommando för mobila enheter för att bearbeta både plocknings- och inventeringsåtgärder; aktivera en utlösare för inventeringströskeln när en plats blir tom; aktivera en plan för rullande inventering för en viss artikel i ett bestämt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="a3fe1-106">Dessa inställningsuppgifter utförs normalt av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="a3fe1-107">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="a3fe1-108">Ange prioriteten för inventeringsarbete</span><span class="sxs-lookup"><span data-stu-id="a3fe1-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="a3fe1-109">Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="a3fe1-110">Klicka på fliken Rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="a3fe1-111">Ange ett värde i fältet Standardarbetsprioritet för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="a3fe1-112">Det här steget ändrar prioriteten för arbetet med rullande inventering jämfört med andra typer av arbete i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="a3fe1-113">Genom att ange ett lägre nummer än numret för andra typer av arbete, ger du arbetet med rullande inventering en högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="a3fe1-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-114">Click Save.</span></span>
5. <span data-ttu-id="a3fe1-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="a3fe1-116">Aktivera den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="a3fe1-116">Enable the mobile device</span></span>
1. <span data-ttu-id="a3fe1-117">Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="a3fe1-118">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-118">Click New.</span></span>
3. <span data-ttu-id="a3fe1-119">Skriv ett värde i fältet Menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="a3fe1-120">Ange ett värde i fältet Titel.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="a3fe1-121">Välj Arbete i fältet Läge.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="a3fe1-122">Ange alternativet Använd befintligt arbete till Ja.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="a3fe1-123">Om du anger det här alternativet till Ja kommer systemet att leta efter befintligt arbete när menykommandot för mobila enheter används.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="a3fe1-124">Välj Systemstyrd i fältet Dirigerad av.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="a3fe1-125">När Systemstyrd har valts styrs lagerarbetaren till öppet arbete som definieras i arbetsklasser.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="a3fe1-126">(Vi ska skapa dessa arbetsklasser härnäst.)</span><span class="sxs-lookup"><span data-stu-id="a3fe1-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="a3fe1-127">Dölj eller Visa avsnittet Arbetsklasser.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="a3fe1-128">Härnäst ska vi skapa två arbetsklasser som ska användas med menykommandot för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="a3fe1-129">När menykommandot används skickas frågor till dessa arbetsklasser, och arbetet med den högsta prioriteten visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="a3fe1-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-130">Click New.</span></span>
10. <span data-ttu-id="a3fe1-131">Välj ett värde i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="a3fe1-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-132">Click New.</span></span>
12. <span data-ttu-id="a3fe1-133">Välj ett värde i fältet Arbetsklass-ID.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="a3fe1-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-134">Click Save.</span></span>
14. <span data-ttu-id="a3fe1-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-135">Close the page.</span></span>
15. <span data-ttu-id="a3fe1-136">Gå till Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="a3fe1-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="a3fe1-138">Välj menykommandot som du nyss skapat i trädet.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="a3fe1-139">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-139">Click Edit.</span></span>
19. <span data-ttu-id="a3fe1-140">Klicka på pilen för att lägga till menykommandot på menyn.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="a3fe1-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="a3fe1-142">Skapa en tröskel för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="a3fe1-142">Create a counting threshold</span></span>
1. <span data-ttu-id="a3fe1-143">Gå till Lagerstyrning > Inställningar > Rullande inventering > Trösklar för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="a3fe1-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-144">Click New.</span></span>
3. <span data-ttu-id="a3fe1-145">Skriv ett värde i fältet Tröskel-ID för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="a3fe1-146">Ange alternativet Bearbeta rullande inventering direkt till Ja.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="a3fe1-147">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="a3fe1-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-148">Click Save.</span></span>
7. <span data-ttu-id="a3fe1-149">Klicka på Välj platser.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-149">Click Select locations.</span></span>
8. <span data-ttu-id="a3fe1-150">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a3fe1-151">Välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="a3fe1-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-152">Click OK.</span></span>
11. <span data-ttu-id="a3fe1-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="a3fe1-154">Skapa en plan för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="a3fe1-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="a3fe1-155">Gå till Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="a3fe1-156">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-156">Click New.</span></span>
3. <span data-ttu-id="a3fe1-157">Skriv ett värde i fältet Plan-ID för rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="a3fe1-158">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a3fe1-159">Ange ett värde i fältet Högsta antal rullande inventeringar.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="a3fe1-160">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-160">Click Save.</span></span>
7. <span data-ttu-id="a3fe1-161">Klicka på Välj platser.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-161">Click Select locations.</span></span>
8. <span data-ttu-id="a3fe1-162">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a3fe1-163">Välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="a3fe1-164">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-164">Click OK.</span></span>
11. <span data-ttu-id="a3fe1-165">Ange ett värde i fältet Dagar mellan rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="a3fe1-166">Om till exempel fältet Dagar mellan rullande inventering anges till 5 kommer ett arbete för rullande inventering att skapas var femte dag.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="a3fe1-167">Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="a3fe1-168">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-168">Click Save.</span></span>
13. <span data-ttu-id="a3fe1-169">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-169">Click New.</span></span>
14. <span data-ttu-id="a3fe1-170">Ange ett nummer i fältet Sekvensnummer.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="a3fe1-171">Sorteringsordningen är från det lägsta talet till det högsta talet.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="a3fe1-172">Värdet måste vara större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a3fe1-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="a3fe1-173">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="a3fe1-174">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="a3fe1-175">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-175">Click Save.</span></span>
18. <span data-ttu-id="a3fe1-176">Klicka på Definiera produktfråga.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-176">Click Define product query.</span></span>
19. <span data-ttu-id="a3fe1-177">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="a3fe1-178">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="a3fe1-179">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-179">Click OK.</span></span>
22. <span data-ttu-id="a3fe1-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a3fe1-180">Close the page.</span></span>


