---
title: 'Definiera rullande inventering '
description: Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8b7f39fc9a91d9fe219445e409d000266e24775
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438027"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="bd4e8-103">Definiera rullande inventering </span><span class="sxs-lookup"><span data-stu-id="bd4e8-103">Define cycle counting</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd4e8-104">Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="bd4e8-105">Den här uppgiftsinspelningen visar hur du kan ställa in standardarbetsprioriteten för inventering; aktivera ett menykommando för mobila enheter för att bearbeta både plocknings- och inventeringsåtgärder; aktivera en utlösare för inventeringströskeln när en plats blir tom; aktivera en plan för rullande inventering för en viss artikel i ett bestämt lagerställe.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="bd4e8-106">Dessa inställningsuppgifter utförs normalt av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="bd4e8-107">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="bd4e8-108">Ange prioriteten för inventeringsarbete</span><span class="sxs-lookup"><span data-stu-id="bd4e8-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="bd4e8-109">I **Navigeringsfönster** gå till **Moduler > Lagerstyrning > Inställningar > Parametrar för lagerstyrning**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-109">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="bd4e8-110">Klicka på fliken **Rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-110">Click the **Cycle counting** tab.</span></span>
3. <span data-ttu-id="bd4e8-111">Ange ett värde i fältet **Standardarbetsprioritet för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-111">In the **Default cycle count work priority** field, enter a number.</span></span> <span data-ttu-id="bd4e8-112">Det här steget ändrar prioriteten för arbetet med rullande inventering jämfört med andra typer av arbete i lagerstället.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="bd4e8-113">Genom att ange ett lägre nummer än numret för andra typer av arbete, ger du arbetet med rullande inventering en högre prioritet.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="bd4e8-114">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-114">Click **Save**.</span></span>
5. <span data-ttu-id="bd4e8-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="bd4e8-116">Aktivera den mobila enheten</span><span class="sxs-lookup"><span data-stu-id="bd4e8-116">Enable the mobile device</span></span>
1. <span data-ttu-id="bd4e8-117">I **Navigeringsfönster**, gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-117">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="bd4e8-118">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-118">Click **New**.</span></span>
3. <span data-ttu-id="bd4e8-119">Ange ett värde i fältet **Menyalternativnamn**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-119">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="bd4e8-120">Ange ett värde i fältet **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-120">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="bd4e8-121">Välj Arbete i fältet **Läge**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-121">In the **Mode** field, select 'Work'.</span></span>
6. <span data-ttu-id="bd4e8-122">Ange alternativet **Använd befintligt arbete** till Ja.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-122">Set the **Use existing work** option to Yes.</span></span> <span data-ttu-id="bd4e8-123">Om du anger det här alternativet till Ja kommer systemet att leta efter befintligt arbete när menykommandot för mobila enheter används.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="bd4e8-124">Välj Systemstyrd i fältet **Dirigerad av**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-124">In the **Directed by** field, select 'System directed'.</span></span> <span data-ttu-id="bd4e8-125">När Systemstyrd har valts styrs lagerarbetaren till öppet arbete som definieras i arbetsklasser.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="bd4e8-126">(Vi ska skapa dessa arbetsklasser härnäst.)</span><span class="sxs-lookup"><span data-stu-id="bd4e8-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="bd4e8-127">Expandera snabbfliken **Arbetsklasser**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-127">Expand the **Work classes** fastTab.</span></span> <span data-ttu-id="bd4e8-128">Härnäst ska vi skapa två arbetsklasser som ska användas med menykommandot för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="bd4e8-129">När menykommandot används skickas frågor till dessa arbetsklasser, och arbetet med den högsta prioriteten visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="bd4e8-130">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-130">Click **New**.</span></span>
10. <span data-ttu-id="bd4e8-131">Välj ett värde i fältet **Arbetsklass-ID**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-131">In the **Work class ID** field, select a value.</span></span>
11. <span data-ttu-id="bd4e8-132">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-132">Click **New**.</span></span>
12. <span data-ttu-id="bd4e8-133">Välj ett värde i fältet **Arbetsklass-ID**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-133">In the **Work class ID** field, select a value.</span></span>
13. <span data-ttu-id="bd4e8-134">I **åtgärdsfönstret**, klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-134">In the **Action Pane**, click **Save**.</span></span>
14. <span data-ttu-id="bd4e8-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-135">Close the page.</span></span>
15. <span data-ttu-id="bd4e8-136">I **Navigeringsfönster**, gå till **Moduler > Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-136">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
16. <span data-ttu-id="bd4e8-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="bd4e8-138">Välj menykommandot som du nyss skapat i trädet.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="bd4e8-139">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-139">Click **Edit**.</span></span>
19. <span data-ttu-id="bd4e8-140">Klicka på pilen för att lägga till menykommandot på menyn.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="bd4e8-141">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-141">Click **Save**.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="bd4e8-142">Skapa en tröskel för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="bd4e8-142">Create a counting threshold</span></span>
1. <span data-ttu-id="bd4e8-143">I **navigeringsfönster**, gå till **Moduler > Lagerstyrning > Inställningar > Rullande inventering > Trösklar för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-143">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count thresholds**.</span></span>
2. <span data-ttu-id="bd4e8-144">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-144">Click **New**.</span></span>
3. <span data-ttu-id="bd4e8-145">Skriv ett värde i fältet **Tröskel-ID för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-145">In the **Cycle counting threshold ID** field, type a value.</span></span>
4. <span data-ttu-id="bd4e8-146">Ange alternativet **Bearbeta rullande inventering direkt** till Ja.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-146">Set the **Process cycle counting immediately** option to Yes.</span></span>
5. <span data-ttu-id="bd4e8-147">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-147">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="bd4e8-148">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-148">Click **Save**.</span></span>
7. <span data-ttu-id="bd4e8-149">Klicka på **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-149">Click **Select locations**.</span></span>
8. <span data-ttu-id="bd4e8-150">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="bd4e8-151">Välj ett värde i fältet **Kriterier**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-151">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="bd4e8-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-152">Click **OK**.</span></span>
11. <span data-ttu-id="bd4e8-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="bd4e8-154">Skapa en plan för rullande inventering</span><span class="sxs-lookup"><span data-stu-id="bd4e8-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="bd4e8-155">I **navigeringsfönster**, gå till **Moduler > Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-155">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count plans**.</span></span>
2. <span data-ttu-id="bd4e8-156">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-156">Click **New**.</span></span>
3. <span data-ttu-id="bd4e8-157">Skriv ett värde i fältet **Plan-ID för rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-157">In the **Cycle counting plan ID** field, type a value.</span></span>
4. <span data-ttu-id="bd4e8-158">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-158">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="bd4e8-159">Ange ett värde i fältet **Högsta antal rullande inventeringar**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-159">In the **Maximum number of cycle counts** field, enter a number.</span></span>
6. <span data-ttu-id="bd4e8-160">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-160">Click **Save**.</span></span>
7. <span data-ttu-id="bd4e8-161">Klicka på **Välj platser**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-161">Click **Select locations**.</span></span>
8. <span data-ttu-id="bd4e8-162">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="bd4e8-163">Välj ett värde i fältet **Kriterier**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-163">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="bd4e8-164">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-164">Click **OK**.</span></span>
11. <span data-ttu-id="bd4e8-165">Ange ett värde i fältet **Dagar mellan rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-165">In the **Days between cycle counting** field, enter a number.</span></span> <span data-ttu-id="bd4e8-166">Om till exempel fältet **Dagar mellan rullande inventering** anges till 5 kommer ett arbete för rullande inventering att skapas var femte dag.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-166">For example, if the **Days between cycle counting** field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="bd4e8-167">Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="bd4e8-168">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-168">Click **Save**.</span></span>
13. <span data-ttu-id="bd4e8-169">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-169">Click **New**.</span></span>
14. <span data-ttu-id="bd4e8-170">Ange ett nummer i fältet **Sekvensnummer**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-170">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="bd4e8-171">Sorteringsordningen är från det lägsta talet till det högsta talet.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="bd4e8-172">Värdet måste vara större än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="bd4e8-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="bd4e8-173">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="bd4e8-174">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-174">In the **Description** field, type a value.</span></span>
17. <span data-ttu-id="bd4e8-175">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-175">Click **Save**.</span></span>
18. <span data-ttu-id="bd4e8-176">Klicka på frågan **Definiera produkt**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-176">Click **Define product** query.</span></span>
19. <span data-ttu-id="bd4e8-177">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="bd4e8-178">I fältet **Kriterier** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-178">In the **Criteria** field, enter or select a value.</span></span>
21. <span data-ttu-id="bd4e8-179">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-179">Click **OK**.</span></span>
22. <span data-ttu-id="bd4e8-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bd4e8-180">Close the page.</span></span>

