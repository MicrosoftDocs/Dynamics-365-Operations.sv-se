---
title: Definiera skapande av behållare
description: I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56fc6adc2a0eeb5b824089ff4b1b781f3a99a34c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558066"
---
# <a name="set-up-containerization"></a><span data-ttu-id="e139c-103">Definiera skapande av behållare</span><span class="sxs-lookup"><span data-stu-id="e139c-103">Set up containerization</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e139c-104">I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="e139c-104">This procedure describes how to automate the containerization of loads in Warehouse management.</span></span> <span data-ttu-id="e139c-105">Automatiskt skapande av behållare skapar behållare och plockarbetet för leveranser när en påfyllnad bearbetas och arbetsrader kan delas i kvantiteter som passar behållarna.</span><span class="sxs-lookup"><span data-stu-id="e139c-105">Automated containerization creates containers and the picking work for shipments when a wave is processed and work lines can be split into quantities that fit the containers.</span></span> <span data-ttu-id="e139c-106">Detta hjälper lagerarbetare att plocka artiklarna direkt till den valda behållaren.</span><span class="sxs-lookup"><span data-stu-id="e139c-106">This helps warehouse workers to pick the items directly into the chosen container.</span></span> <span data-ttu-id="e139c-107">Jämfört med den manuella förpackningsprocessen automatiseras uppgifter som till exempel att skapa behållare, tilldela artiklar och stänga behållare av systemet.</span><span class="sxs-lookup"><span data-stu-id="e139c-107">Compared to the manual packing process, tasks such as creating containers, assigning items, and closing containers are automated by the system.</span></span> <span data-ttu-id="e139c-108">I den här proceduren används USMF-demonstrationsföretaget och utförs av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="e139c-108">This procedure uses the USMF demo company and is performed by a Warehouse manager.</span></span>


## <a name="set-up-a-wave-template"></a><span data-ttu-id="e139c-109">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="e139c-109">Set up a wave template</span></span>
1. <span data-ttu-id="e139c-110">Gå till Lagerstyrning > Inställningar > Påfyllnader > Påfyllnadsmallar.</span><span class="sxs-lookup"><span data-stu-id="e139c-110">Go to Warehouse management > Setup > Waves > Wave templates.</span></span>
2. <span data-ttu-id="e139c-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-111">Click New.</span></span>
3. <span data-ttu-id="e139c-112">I fältet Påfyllnadsmallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="e139c-112">In the Wave template name field, type a value.</span></span>
4. <span data-ttu-id="e139c-113">Skriv ett värde i fältet Beskrivning av påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="e139c-113">In the Wave template description field, type a value.</span></span>
5. <span data-ttu-id="e139c-114">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="e139c-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="e139c-115">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="e139c-115">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="e139c-116">Visa avsnittet Metoder.</span><span class="sxs-lookup"><span data-stu-id="e139c-116">Expand the Methods section.</span></span>
    * <span data-ttu-id="e139c-117">Fönstret Valda metoder visar metoderna för den valda påfyllnadsmallstypen.</span><span class="sxs-lookup"><span data-stu-id="e139c-117">The Selected methods pane lists the methods for the selected wave template type.</span></span> <span data-ttu-id="e139c-118">Påfyllnadsmallen måste inkludera metoden för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-118">The wave template must include the containerize method.</span></span>  
8. <span data-ttu-id="e139c-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e139c-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="e139c-120">I fältet Kod för påfyllnadssteg, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="e139c-120">In the Wave step code field, type a value.</span></span>
    * <span data-ttu-id="e139c-121">Ange en Kod för påfyllnadssteg för den tillagda metoden, som kan vara en kod.</span><span class="sxs-lookup"><span data-stu-id="e139c-121">Enter a Wave step code for the added method, which can be any code.</span></span> <span data-ttu-id="e139c-122">Det går att lägga till metod mer än en gång och tilldela olika koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="e139c-122">It’s possible to add the method more than once and assign different wave step codes.</span></span> <span data-ttu-id="e139c-123">Om du vill göra detta väljer du Kan upprepas för den här metoden på sidan Metoder för bearbetning av påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="e139c-123">To do this, select Repeatable for this method in the Wave process methods page.</span></span>  
10. <span data-ttu-id="e139c-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-124">Click Save.</span></span>
11. <span data-ttu-id="e139c-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e139c-125">Close the page.</span></span>

## <a name="set-up-a-container-type"></a><span data-ttu-id="e139c-126">Ställ in en behållartyp</span><span class="sxs-lookup"><span data-stu-id="e139c-126">Set up a container type</span></span>
1. <span data-ttu-id="e139c-127">Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="e139c-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
    * <span data-ttu-id="e139c-128">Du kan definiera dina behållare på sidan Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="e139c-128">You can define your containers in the Container types page.</span></span> <span data-ttu-id="e139c-129">Du kan konfigurera de fysiska dimensionerna på behållare, inklusive taravikt, högsta vikt, högsta volym, längd, bredd, vikt och höjd.</span><span class="sxs-lookup"><span data-stu-id="e139c-129">You can configure the physical dimensions of containers including tare weight, maximum weight, maximum volume, length, width, and height.</span></span> <span data-ttu-id="e139c-130">I det här exemplet har vi tre olika storlek på boxar.</span><span class="sxs-lookup"><span data-stu-id="e139c-130">In this example, we have three different sizes of boxes.</span></span>  
2. <span data-ttu-id="e139c-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-131">Click New.</span></span>
3. <span data-ttu-id="e139c-132">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="e139c-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="e139c-133">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-133">In the Tare weight field, enter a number.</span></span>
5. <span data-ttu-id="e139c-134">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-134">In the Maximum weight field, enter a number.</span></span>
6. <span data-ttu-id="e139c-135">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="e139c-135">In the Volume field, enter a number.</span></span>
7. <span data-ttu-id="e139c-136">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="e139c-136">In the Length field, enter a number.</span></span>
8. <span data-ttu-id="e139c-137">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="e139c-137">In the Width field, enter a number.</span></span>
9. <span data-ttu-id="e139c-138">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="e139c-138">In the Height field, enter a number.</span></span>
10. <span data-ttu-id="e139c-139">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e139c-139">In the Description field, type a value.</span></span>
11. <span data-ttu-id="e139c-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-140">Click Save.</span></span>
12. <span data-ttu-id="e139c-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-141">Click New.</span></span>
13. <span data-ttu-id="e139c-142">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="e139c-142">In the Container type code field, type a value.</span></span>
14. <span data-ttu-id="e139c-143">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e139c-143">In the Description field, type a value.</span></span>
15. <span data-ttu-id="e139c-144">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-144">In the Tare weight field, enter a number.</span></span>
16. <span data-ttu-id="e139c-145">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-145">In the Maximum weight field, enter a number.</span></span>
17. <span data-ttu-id="e139c-146">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="e139c-146">In the Volume field, enter a number.</span></span>
18. <span data-ttu-id="e139c-147">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="e139c-147">In the Length field, enter a number.</span></span>
19. <span data-ttu-id="e139c-148">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="e139c-148">In the Width field, enter a number.</span></span>
20. <span data-ttu-id="e139c-149">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="e139c-149">In the Height field, enter a number.</span></span>
21. <span data-ttu-id="e139c-150">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-150">Click Save.</span></span>
22. <span data-ttu-id="e139c-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-151">Click New.</span></span>
23. <span data-ttu-id="e139c-152">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="e139c-152">In the Container type code field, type a value.</span></span>
24. <span data-ttu-id="e139c-153">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e139c-153">In the Description field, type a value.</span></span>
25. <span data-ttu-id="e139c-154">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-154">In the Tare weight field, enter a number.</span></span>
26. <span data-ttu-id="e139c-155">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="e139c-155">In the Maximum weight field, enter a number.</span></span>
27. <span data-ttu-id="e139c-156">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="e139c-156">In the Volume field, enter a number.</span></span>
28. <span data-ttu-id="e139c-157">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="e139c-157">In the Length field, enter a number.</span></span>
29. <span data-ttu-id="e139c-158">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="e139c-158">In the Width field, enter a number.</span></span>
30. <span data-ttu-id="e139c-159">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="e139c-159">In the Height field, enter a number.</span></span>
31. <span data-ttu-id="e139c-160">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-160">Click Save.</span></span>
32. <span data-ttu-id="e139c-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e139c-161">Close the page.</span></span>

## <a name="set-up-a-container-group"></a><span data-ttu-id="e139c-162">Ställ in en behållargrupp</span><span class="sxs-lookup"><span data-stu-id="e139c-162">Set up a container group</span></span>
1. <span data-ttu-id="e139c-163">Gå till Lagerstyrning > Inställningar > Behållare > Behållargrupper.</span><span class="sxs-lookup"><span data-stu-id="e139c-163">Go to Warehouse management > Setup > Containers > Container groups.</span></span>
2. <span data-ttu-id="e139c-164">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-164">Click New.</span></span>
    * <span data-ttu-id="e139c-165">Du kan ställa in logiska grupper av behållartyper.</span><span class="sxs-lookup"><span data-stu-id="e139c-165">You can set up logical groups of container types.</span></span> <span data-ttu-id="e139c-166">För varje grupp kan du ange sekvens för packning av containrar och procentsatsen av containrarna som ska fyllas. I används storleksdimensioner för artikeln för att avgöra om den passar i en behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-166">For each group, you can specify the sequence in which to pack the containers and the percentage of the containers to fill.The size dimensions of the item is used to determine whether it will fit in a container.</span></span> <span data-ttu-id="e139c-167">Den behållare som är närmast artikelns storlek används.</span><span class="sxs-lookup"><span data-stu-id="e139c-167">The container that is closest to the size dimensions of the item is used.</span></span> <span data-ttu-id="e139c-168">Om du har flera behållartyper i en grupp, rekommenderar vi att sekvensen ordnas efter storlek, så att den största, är den första nummer 1 i sekvensen, och den mest minsta behållaren är den sista.</span><span class="sxs-lookup"><span data-stu-id="e139c-168">If you have multiple container types in a group, we recommend that you arrange the sequence by size, so that the largest container is first, number 1 in the sequence, and the smallest container is last.</span></span>    
3. <span data-ttu-id="e139c-169">Skriv ett värde i fältet Behållargrupp-ID.</span><span class="sxs-lookup"><span data-stu-id="e139c-169">In the Container group ID field, type a value.</span></span>
4. <span data-ttu-id="e139c-170">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e139c-170">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e139c-171">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-171">Click New.</span></span>
6. <span data-ttu-id="e139c-172">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e139c-172">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="e139c-173">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="e139c-173">In the Container type field, enter or select a value.</span></span>
8. <span data-ttu-id="e139c-174">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-174">Click New.</span></span>
9. <span data-ttu-id="e139c-175">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e139c-175">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="e139c-176">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="e139c-176">In the Container type field, enter or select a value.</span></span>
11. <span data-ttu-id="e139c-177">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-177">Click New.</span></span>
12. <span data-ttu-id="e139c-178">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e139c-178">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="e139c-179">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="e139c-179">In the Container type field, enter or select a value.</span></span>
14. <span data-ttu-id="e139c-180">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-180">Click Save.</span></span>
15. <span data-ttu-id="e139c-181">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e139c-181">Close the page.</span></span>

## <a name="set-up-a-container-build-template"></a><span data-ttu-id="e139c-182">Ställa in en behållarversionsmall</span><span class="sxs-lookup"><span data-stu-id="e139c-182">Set up a container build template</span></span>
1. <span data-ttu-id="e139c-183">Gå till Lagerstyrning > Inställningar > Behållare > Mall för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-183">Go to Warehouse management > Setup > Containers > Container build templates.</span></span>
2. <span data-ttu-id="e139c-184">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-184">Click New.</span></span>
    * <span data-ttu-id="e139c-185">Behållareversionmallen baseras på vilket process för skapande av fraktbehållare som utförs.</span><span class="sxs-lookup"><span data-stu-id="e139c-185">The container build template is based on which of the containerization processes are performed.</span></span> <span data-ttu-id="e139c-186">Varje behållareversionmall definierar en process för skapande av fraktbehållare som ska användas i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="e139c-186">Each container build template defines one containerization process that will be used by a wave template.</span></span> <span data-ttu-id="e139c-187">Alternativet Redigera fråga låter dig definiera de villkor som den valda mallen ska bearbeta.</span><span class="sxs-lookup"><span data-stu-id="e139c-187">The Edit query option allows you to define the conditions on which the selected template will be processed.</span></span> <span data-ttu-id="e139c-188">Till exempel vill du kanske bara att köra skapande av fraktbehållare för specifika kunder, produkter, eller lagerställen och du kan lägga till motsvarande frågeintervall i mallen.</span><span class="sxs-lookup"><span data-stu-id="e139c-188">For example, you may want to only run containerization for specific customers, products, or warehouses or you can add the corresponding query ranges to the template.</span></span> <span data-ttu-id="e139c-189">Fältet Kod för påfyllnadssteg är hur en behållarversionsmall länkas till steg i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="e139c-189">The Wave step code field is how a container build template is linked to steps in a wave template.</span></span> <span data-ttu-id="e139c-190">När en påfyllnad körs, bestämmer den vilka/vilken behållarversionsmall(ar) som används för att initiera skapande av fraktbehållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-190">When a wave is executed, it determines which container build template(s) are used to initiate containerization.</span></span> <span data-ttu-id="e139c-191">Fältet Basfrågetyper bestämmer vad som ska packas och vad filterfrågan ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="e139c-191">The Base query type field determines what to pack and what to base the filter query on.</span></span>  
3. <span data-ttu-id="e139c-192">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e139c-192">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e139c-193">Skriv ett värde i fältet Behållarmall-ID.</span><span class="sxs-lookup"><span data-stu-id="e139c-193">In the Container template ID field, type a value.</span></span>
5. <span data-ttu-id="e139c-194">I fältet Behållargrupp kan du ange eller välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="e139c-194">In the Container group ID field, enter or select a value.</span></span>
6. <span data-ttu-id="e139c-195">I fältet Kod för påfyllnadssteg, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="e139c-195">In the Wave step code field, type a value.</span></span>
7. <span data-ttu-id="e139c-196">Markera kryssrutan Tillåt delade plockningar.</span><span class="sxs-lookup"><span data-stu-id="e139c-196">Select the Allow split picks check box.</span></span>
8. <span data-ttu-id="e139c-197">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e139c-197">Click Save.</span></span>
9. <span data-ttu-id="e139c-198">Klicka på Blandade begränsningar för behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-198">Click Containier mixing constraints.</span></span>
    * <span data-ttu-id="e139c-199">Avbrott för blandningslogik låter dig ställa in regler för att packa allokeringsrader i behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-199">Mixing logic breaks allows you to set up rules for packing allocation lines in containers.</span></span> <span data-ttu-id="e139c-200">Om du t.ex. lägger till fältet Artikelnummer, när artiklar tilldelas till behållare, kommer en ny behållare att skapas om det finns ett nytt artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="e139c-200">For example, if you add the Item number field, when items are assigned to containers, a new container will be created when there is a new item number.</span></span> <span data-ttu-id="e139c-201">Detta kommer att förebygga att arbetare packar allokeringsrader för två olika kunder i samma behållare.</span><span class="sxs-lookup"><span data-stu-id="e139c-201">This is will prevent workers from packing allocations lines for two different customers in the same container.</span></span>  
10. <span data-ttu-id="e139c-202">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e139c-202">Click New.</span></span>
11. <span data-ttu-id="e139c-203">Markera ett alternativ i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="e139c-203">In the Table field, select an option.</span></span>
12. <span data-ttu-id="e139c-204">Ange eller välj ett värde i fältet Välj.</span><span class="sxs-lookup"><span data-stu-id="e139c-204">In the Field Select field, enter or select a value.</span></span>
13. <span data-ttu-id="e139c-205">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e139c-205">Click OK.</span></span>

