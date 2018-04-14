--- 
title: "Definiera skapande av behållare"
description: "I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 734034776e1adb42ee5f131e91b6fd7d28f811ab
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-containerization"></a><span data-ttu-id="2de50-103">Definiera skapande av behållare</span><span class="sxs-lookup"><span data-stu-id="2de50-103">Set up containerization</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2de50-104">I den här proceduren beskrivs hur du automatiserar skapandet av behållare för last Lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="2de50-104">This procedure describes how to automate the containerization of loads in Warehouse management.</span></span> <span data-ttu-id="2de50-105">Automatiskt skapande av behållare skapar behållare och plockarbetet för leveranser när en påfyllnad bearbetas och arbetsrader kan delas i kvantiteter som passar behållarna.</span><span class="sxs-lookup"><span data-stu-id="2de50-105">Automated containerization creates containers and the picking work for shipments when a wave is processed and work lines can be split into quantities that fit the containers.</span></span> <span data-ttu-id="2de50-106">Detta hjälper lagerarbetare att plocka artiklarna direkt till den valda behållaren.</span><span class="sxs-lookup"><span data-stu-id="2de50-106">This helps warehouse workers to pick the items directly into the chosen container.</span></span> <span data-ttu-id="2de50-107">Jämfört med den manuella förpackningsprocessen automatiseras uppgifter som till exempel att skapa behållare, tilldela artiklar och stänga behållare av systemet.</span><span class="sxs-lookup"><span data-stu-id="2de50-107">Compared to the manual packing process, tasks such as creating containers, assigning items, and closing containers are automated by the system.</span></span> <span data-ttu-id="2de50-108">I den här proceduren används USMF-demonstrationsföretaget och utförs av en lagerchef.</span><span class="sxs-lookup"><span data-stu-id="2de50-108">This procedure uses the USMF demo company and is performed by a Warehouse manager.</span></span>


## <a name="set-up-a-wave-template"></a><span data-ttu-id="2de50-109">Ställa in en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="2de50-109">Set up a wave template</span></span>
1. <span data-ttu-id="2de50-110">Gå till Lagerstyrning > Inställningar > Påfyllnader > Påfyllnadsmallar.</span><span class="sxs-lookup"><span data-stu-id="2de50-110">Go to Warehouse management > Setup > Waves > Wave templates.</span></span>
2. <span data-ttu-id="2de50-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-111">Click New.</span></span>
3. <span data-ttu-id="2de50-112">I fältet Påfyllnadsmallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="2de50-112">In the Wave template name field, type a value.</span></span>
4. <span data-ttu-id="2de50-113">Skriv ett värde i fältet Beskrivning av påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="2de50-113">In the Wave template description field, type a value.</span></span>
5. <span data-ttu-id="2de50-114">Ange eller välj ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="2de50-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="2de50-115">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="2de50-115">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="2de50-116">Visa avsnittet Metoder.</span><span class="sxs-lookup"><span data-stu-id="2de50-116">Expand the Methods section.</span></span>
    * <span data-ttu-id="2de50-117">Fönstret Valda metoder visar metoderna för den valda påfyllnadsmallstypen.</span><span class="sxs-lookup"><span data-stu-id="2de50-117">The Selected methods pane lists the methods for the selected wave template type.</span></span> <span data-ttu-id="2de50-118">Påfyllnadsmallen måste inkludera metoden för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-118">The wave template must include the containerize method.</span></span>  
8. <span data-ttu-id="2de50-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="2de50-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="2de50-120">I fältet Kod för påfyllnadssteg, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="2de50-120">In the Wave step code field, type a value.</span></span>
    * <span data-ttu-id="2de50-121">Ange en Kod för påfyllnadssteg för den tillagda metoden, som kan vara en kod.</span><span class="sxs-lookup"><span data-stu-id="2de50-121">Enter a Wave step code for the added method, which can be any code.</span></span> <span data-ttu-id="2de50-122">Det går att lägga till metod mer än en gång och tilldela olika koder för påfyllnadssteg.</span><span class="sxs-lookup"><span data-stu-id="2de50-122">It’s possible to add the method more than once and assign different wave step codes.</span></span> <span data-ttu-id="2de50-123">Om du vill göra detta väljer du Kan upprepas för den här metoden på sidan Metoder för bearbetning av påfyllnad.</span><span class="sxs-lookup"><span data-stu-id="2de50-123">To do this, select Repeatable for this method in the Wave process methods page.</span></span>  
10. <span data-ttu-id="2de50-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-124">Click Save.</span></span>
11. <span data-ttu-id="2de50-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2de50-125">Close the page.</span></span>

## <a name="set-up-a-container-type"></a><span data-ttu-id="2de50-126">Ställ in en behållartyp</span><span class="sxs-lookup"><span data-stu-id="2de50-126">Set up a container type</span></span>
1. <span data-ttu-id="2de50-127">Gå till Lagerstyrning > Inställningar > Behållare > Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="2de50-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
    * <span data-ttu-id="2de50-128">Du kan definiera dina behållare på sidan Behållartyper.</span><span class="sxs-lookup"><span data-stu-id="2de50-128">You can define your containers in the Container types page.</span></span> <span data-ttu-id="2de50-129">Du kan konfigurera de fysiska dimensionerna på behållare, inklusive taravikt, högsta vikt, högsta volym, längd, bredd, vikt och höjd.</span><span class="sxs-lookup"><span data-stu-id="2de50-129">You can configure the physical dimensions of containers including tare weight, maximum weight, maximum volume, length, width, and height.</span></span> <span data-ttu-id="2de50-130">I det här exemplet har vi tre olika storlek på boxar.</span><span class="sxs-lookup"><span data-stu-id="2de50-130">In this example, we have three different sizes of boxes.</span></span>  
2. <span data-ttu-id="2de50-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-131">Click New.</span></span>
3. <span data-ttu-id="2de50-132">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="2de50-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="2de50-133">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-133">In the Tare weight field, enter a number.</span></span>
5. <span data-ttu-id="2de50-134">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-134">In the Maximum weight field, enter a number.</span></span>
6. <span data-ttu-id="2de50-135">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="2de50-135">In the Volume field, enter a number.</span></span>
7. <span data-ttu-id="2de50-136">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="2de50-136">In the Length field, enter a number.</span></span>
8. <span data-ttu-id="2de50-137">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="2de50-137">In the Width field, enter a number.</span></span>
9. <span data-ttu-id="2de50-138">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="2de50-138">In the Height field, enter a number.</span></span>
10. <span data-ttu-id="2de50-139">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2de50-139">In the Description field, type a value.</span></span>
11. <span data-ttu-id="2de50-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-140">Click Save.</span></span>
12. <span data-ttu-id="2de50-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-141">Click New.</span></span>
13. <span data-ttu-id="2de50-142">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="2de50-142">In the Container type code field, type a value.</span></span>
14. <span data-ttu-id="2de50-143">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2de50-143">In the Description field, type a value.</span></span>
15. <span data-ttu-id="2de50-144">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-144">In the Tare weight field, enter a number.</span></span>
16. <span data-ttu-id="2de50-145">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-145">In the Maximum weight field, enter a number.</span></span>
17. <span data-ttu-id="2de50-146">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="2de50-146">In the Volume field, enter a number.</span></span>
18. <span data-ttu-id="2de50-147">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="2de50-147">In the Length field, enter a number.</span></span>
19. <span data-ttu-id="2de50-148">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="2de50-148">In the Width field, enter a number.</span></span>
20. <span data-ttu-id="2de50-149">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="2de50-149">In the Height field, enter a number.</span></span>
21. <span data-ttu-id="2de50-150">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-150">Click Save.</span></span>
22. <span data-ttu-id="2de50-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-151">Click New.</span></span>
23. <span data-ttu-id="2de50-152">Ange ett värde i fältet Behållartypkod.</span><span class="sxs-lookup"><span data-stu-id="2de50-152">In the Container type code field, type a value.</span></span>
24. <span data-ttu-id="2de50-153">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2de50-153">In the Description field, type a value.</span></span>
25. <span data-ttu-id="2de50-154">Ange ett nummer i fältet Taravikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-154">In the Tare weight field, enter a number.</span></span>
26. <span data-ttu-id="2de50-155">Ange ett värde i fältet Högsta vikt.</span><span class="sxs-lookup"><span data-stu-id="2de50-155">In the Maximum weight field, enter a number.</span></span>
27. <span data-ttu-id="2de50-156">Välj ett nummer i fältet Volym.</span><span class="sxs-lookup"><span data-stu-id="2de50-156">In the Volume field, enter a number.</span></span>
28. <span data-ttu-id="2de50-157">I fältet Längd, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="2de50-157">In the Length field, enter a number.</span></span>
29. <span data-ttu-id="2de50-158">Ange ett värde i fältet Bredd.</span><span class="sxs-lookup"><span data-stu-id="2de50-158">In the Width field, enter a number.</span></span>
30. <span data-ttu-id="2de50-159">Ange ett värde i fältet Höjd.</span><span class="sxs-lookup"><span data-stu-id="2de50-159">In the Height field, enter a number.</span></span>
31. <span data-ttu-id="2de50-160">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-160">Click Save.</span></span>
32. <span data-ttu-id="2de50-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2de50-161">Close the page.</span></span>

## <a name="set-up-a-container-group"></a><span data-ttu-id="2de50-162">Ställ in en behållargrupp</span><span class="sxs-lookup"><span data-stu-id="2de50-162">Set up a container group</span></span>
1. <span data-ttu-id="2de50-163">Gå till Lagerstyrning > Inställningar > Behållare > Behållargrupper.</span><span class="sxs-lookup"><span data-stu-id="2de50-163">Go to Warehouse management > Setup > Containers > Container groups.</span></span>
2. <span data-ttu-id="2de50-164">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-164">Click New.</span></span>
    * <span data-ttu-id="2de50-165">Du kan ställa in logiska grupper av behållartyper.</span><span class="sxs-lookup"><span data-stu-id="2de50-165">You can set up logical groups of container types.</span></span> <span data-ttu-id="2de50-166">För varje grupp kan du ange i vilken ordning som behållarna packas och procentsatsen för behållarna som ska fyllas.</span><span class="sxs-lookup"><span data-stu-id="2de50-166">For each group, you can specify the sequence in which to pack the containers and the percentage of the containers to fill.</span></span> <span data-ttu-id="2de50-167">Artikelns storleksdimensioner används för att avgöra om den kommer att passa i en behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-167">The size dimensions of the item is used to determine whether it will fit in a container.</span></span> <span data-ttu-id="2de50-168">Den behållare som är närmast artikelns storlek används.</span><span class="sxs-lookup"><span data-stu-id="2de50-168">The container that is closest to the size dimensions of the item is used.</span></span> <span data-ttu-id="2de50-169">Om du har flera behållartyper i en grupp, rekommenderar vi att sekvensen ordnas efter storlek, så att den största, är den första nummer 1 i sekvensen, och den mest minsta behållaren är den sista.</span><span class="sxs-lookup"><span data-stu-id="2de50-169">If you have multiple container types in a group, we recommend that you arrange the sequence by size, so that the largest container is first, number 1 in the sequence, and the smallest container is last.</span></span>    
3. <span data-ttu-id="2de50-170">Skriv ett värde i fältet Behållargrupp-ID.</span><span class="sxs-lookup"><span data-stu-id="2de50-170">In the Container group ID field, type a value.</span></span>
4. <span data-ttu-id="2de50-171">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2de50-171">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2de50-172">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-172">Click New.</span></span>
6. <span data-ttu-id="2de50-173">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2de50-173">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="2de50-174">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="2de50-174">In the Container type field, enter or select a value.</span></span>
8. <span data-ttu-id="2de50-175">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-175">Click New.</span></span>
9. <span data-ttu-id="2de50-176">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2de50-176">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="2de50-177">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="2de50-177">In the Container type field, enter or select a value.</span></span>
11. <span data-ttu-id="2de50-178">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-178">Click New.</span></span>
12. <span data-ttu-id="2de50-179">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2de50-179">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="2de50-180">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="2de50-180">In the Container type field, enter or select a value.</span></span>
14. <span data-ttu-id="2de50-181">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-181">Click Save.</span></span>
15. <span data-ttu-id="2de50-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2de50-182">Close the page.</span></span>

## <a name="set-up-a-container-build-template"></a><span data-ttu-id="2de50-183">Ställa in en behållarversionsmall</span><span class="sxs-lookup"><span data-stu-id="2de50-183">Set up a container build template</span></span>
1. <span data-ttu-id="2de50-184">Gå till Lagerstyrning > Inställningar > Behållare > Mall för skapande av behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-184">Go to Warehouse management > Setup > Containers > Container build templates.</span></span>
2. <span data-ttu-id="2de50-185">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-185">Click New.</span></span>
    * <span data-ttu-id="2de50-186">Behållareversionmallen baseras på vilket process för skapande av fraktbehållare som utförs.</span><span class="sxs-lookup"><span data-stu-id="2de50-186">The container build template is based on which of the containerization processes are performed.</span></span> <span data-ttu-id="2de50-187">Varje behållareversionmall definierar en process för skapande av fraktbehållare som ska användas i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="2de50-187">Each container build template defines one containerization process that will be used by a wave template.</span></span> <span data-ttu-id="2de50-188">Alternativet Redigera fråga låter dig definiera de villkor som den valda mallen ska bearbeta.</span><span class="sxs-lookup"><span data-stu-id="2de50-188">The Edit query option allows you to define the conditions on which the selected template will be processed.</span></span> <span data-ttu-id="2de50-189">Till exempel vill du kanske bara att köra skapande av fraktbehållare för specifika kunder, produkter, eller lagerställen och du kan lägga till motsvarande frågeintervall i mallen.</span><span class="sxs-lookup"><span data-stu-id="2de50-189">For example, you may want to only run containerization for specific customers, products, or warehouses or you can add the corresponding query ranges to the template.</span></span> <span data-ttu-id="2de50-190">Fältet Kod för påfyllnadssteg är hur en behållarversionsmall länkas till steg i en påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="2de50-190">The Wave step code field is how a container build template is linked to steps in a wave template.</span></span> <span data-ttu-id="2de50-191">När en påfyllnad körs, bestämmer den vilka/vilken behållarversionsmall(ar) som används för att initiera skapande av fraktbehållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-191">When a wave is executed, it determines which container build template(s) are used to initiate containerization.</span></span> <span data-ttu-id="2de50-192">Fältet Basfrågetyper bestämmer vad som ska packas och vad filterfrågan ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="2de50-192">The Base query type field determines what to pack and what to base the filter query on.</span></span>  
3. <span data-ttu-id="2de50-193">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2de50-193">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2de50-194">Skriv ett värde i fältet Behållarmall-ID.</span><span class="sxs-lookup"><span data-stu-id="2de50-194">In the Container template ID field, type a value.</span></span>
5. <span data-ttu-id="2de50-195">I fältet Behållargrupp kan du ange eller välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="2de50-195">In the Container group ID field, enter or select a value.</span></span>
6. <span data-ttu-id="2de50-196">I fältet Kod för påfyllnadssteg, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="2de50-196">In the Wave step code field, type a value.</span></span>
7. <span data-ttu-id="2de50-197">Markera kryssrutan Tillåt delade plockningar.</span><span class="sxs-lookup"><span data-stu-id="2de50-197">Select the Allow split picks check box.</span></span>
8. <span data-ttu-id="2de50-198">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2de50-198">Click Save.</span></span>
9. <span data-ttu-id="2de50-199">Klicka på Blandade begränsningar för behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-199">Click Container mixing constraints.</span></span>
    * <span data-ttu-id="2de50-200">Avbrott för blandningslogik låter dig ställa in regler för att packa allokeringsrader i behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-200">Mixing logic breaks allows you to set up rules for packing allocation lines in containers.</span></span> <span data-ttu-id="2de50-201">Om du t.ex. lägger till fältet Artikelnummer, när artiklar tilldelas till behållare, kommer en ny behållare att skapas om det finns ett nytt artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2de50-201">For example, if you add the Item number field, when items are assigned to containers, a new container will be created when there is a new item number.</span></span> <span data-ttu-id="2de50-202">Detta kommer att förebygga att arbetare packar allokeringsrader för två olika kunder i samma behållare.</span><span class="sxs-lookup"><span data-stu-id="2de50-202">This is will prevent workers from packing allocations lines for two different customers in the same container.</span></span>  
10. <span data-ttu-id="2de50-203">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2de50-203">Click New.</span></span>
11. <span data-ttu-id="2de50-204">Markera ett alternativ i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="2de50-204">In the Table field, select an option.</span></span>
12. <span data-ttu-id="2de50-205">Ange eller välj ett värde i fältet Välj.</span><span class="sxs-lookup"><span data-stu-id="2de50-205">In the Field Select field, enter or select a value.</span></span>
13. <span data-ttu-id="2de50-206">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2de50-206">Click OK.</span></span>


