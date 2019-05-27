---
title: Ställ in kompensationsrutnät
description: Kompensationsrutnät används för att definiera och underhålla lönstrukturerna för fasta kompensationsplaner.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0caebb2dfbff12545610aa6438dccbec84db3f9
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509744"
---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="427dc-103">Ställ in kompensationsrutnät</span><span class="sxs-lookup"><span data-stu-id="427dc-103">Set up compensation grids</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="427dc-104">Kompensationsrutnät används för att definiera och underhålla lönstrukturerna för fasta kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="427dc-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="427dc-105">Kompensationsrutnät kan delas mellan flera planer och kopieras när du skapar en ny kompensationsplan.</span><span class="sxs-lookup"><span data-stu-id="427dc-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="427dc-106">Innan du skapar ett kompensationsrutnät måste nivåer och referenspunkter ställas in.</span><span class="sxs-lookup"><span data-stu-id="427dc-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="427dc-107">I det här exemplet skapas en ny typ av kompensationsrutnät med hjälp av demodata för nivåer och referenspunkter.</span><span class="sxs-lookup"><span data-stu-id="427dc-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="427dc-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="427dc-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="427dc-109">Ställ in information om kompensationsrutnätet</span><span class="sxs-lookup"><span data-stu-id="427dc-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="427dc-110">Gå till Personal > Kompensation > Fast kompensation > Kompensationsrutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="427dc-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="427dc-111">Click New.</span></span>
3. <span data-ttu-id="427dc-112">Ange ett värde i fältet Rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="427dc-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="427dc-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="427dc-114">Välj ett alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="427dc-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="427dc-115">Ange eller välj ett värde i fältet Referensinställningar.</span><span class="sxs-lookup"><span data-stu-id="427dc-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="427dc-116">Ange eller välj ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="427dc-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="427dc-117">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="427dc-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="427dc-118">Ange ett datum i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="427dc-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="427dc-119">Lägg till nivåer i kompensationsstrukturen</span><span class="sxs-lookup"><span data-stu-id="427dc-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="427dc-120">Klicka på Kompensationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="427dc-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="427dc-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="427dc-122">Ange eller välj ett värde i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="427dc-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="427dc-123">Click New.</span></span>
5. <span data-ttu-id="427dc-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="427dc-125">Ange eller välj ett värde i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="427dc-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="427dc-126">Click New.</span></span>
8. <span data-ttu-id="427dc-127">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="427dc-128">Ange eller välj ett värde i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="427dc-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="427dc-129">Click New.</span></span>
11. <span data-ttu-id="427dc-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="427dc-131">Ange eller välj ett värde i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="427dc-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="427dc-132">Click New.</span></span>
14. <span data-ttu-id="427dc-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="427dc-134">Ange eller välj ett värde i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="427dc-135">Fyll i kompensationsstrukturen med värden</span><span class="sxs-lookup"><span data-stu-id="427dc-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="427dc-136">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="427dc-137">Nu kan kompensationsvärden anges manuellt i varje fält i registret, eller också kan massändringsfunktionen användas för att fylla i flera fält och utför grundläggande beräkningar.</span><span class="sxs-lookup"><span data-stu-id="427dc-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="427dc-138">Klicka på Massändra.</span><span class="sxs-lookup"><span data-stu-id="427dc-138">Click Mass change.</span></span>
    * <span data-ttu-id="427dc-139">I det här rutnätet använder vi först värdet på mittpunkten på den första nivån till alla fält i registret.</span><span class="sxs-lookup"><span data-stu-id="427dc-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="427dc-140">Detta blir basen för kompensationsmatrisen.</span><span class="sxs-lookup"><span data-stu-id="427dc-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="427dc-141">Välj ett alternativ i fältet Modifieringstyp.</span><span class="sxs-lookup"><span data-stu-id="427dc-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="427dc-142">Ange ett tal i fältet Justeringsbelopp.</span><span class="sxs-lookup"><span data-stu-id="427dc-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="427dc-143">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="427dc-144">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="427dc-145">Nu använder massändringsfunktionen för att öka beloppen på varje efterföljande nivå med en viss procentandel eller ett visst belopp.</span><span class="sxs-lookup"><span data-stu-id="427dc-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="427dc-146">I det här exemplet ska varje grad ha en spridning på 12,5 % mellan mittpunkterna.</span><span class="sxs-lookup"><span data-stu-id="427dc-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="427dc-147">Välj ett alternativ i fältet Modifieringstyp.</span><span class="sxs-lookup"><span data-stu-id="427dc-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="427dc-148">Ange ett tal i fältet Justeringsbelopp.</span><span class="sxs-lookup"><span data-stu-id="427dc-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="427dc-149">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="427dc-150">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="427dc-151">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="427dc-152">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="427dc-153">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="427dc-154">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="427dc-155">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="427dc-156">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="427dc-157">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="427dc-158">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="427dc-159">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="427dc-160">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="427dc-161">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="427dc-162">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="427dc-163">Nu använder vi massändringsfunktionen för att de lägsta och högsta referenspunkterna för varje nivå.</span><span class="sxs-lookup"><span data-stu-id="427dc-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="427dc-164">I det här exemplet använder vi en spridning på 50 %, så den lägsta referenspunkten justeras med -20 %, och den högsta med +20 %.</span><span class="sxs-lookup"><span data-stu-id="427dc-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="427dc-165">Ange ett tal i fältet Justeringsbelopp.</span><span class="sxs-lookup"><span data-stu-id="427dc-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="427dc-166">Ange eller välj ett värde i fältet Referenspunkt.</span><span class="sxs-lookup"><span data-stu-id="427dc-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="427dc-167">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="427dc-168">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="427dc-169">Ange ett tal i fältet Justeringsbelopp.</span><span class="sxs-lookup"><span data-stu-id="427dc-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="427dc-170">Ange eller välj ett värde i fältet Referenspunkt.</span><span class="sxs-lookup"><span data-stu-id="427dc-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="427dc-171">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="427dc-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="427dc-172">Klicka på Använd i rutnät.</span><span class="sxs-lookup"><span data-stu-id="427dc-172">Click Apply to grid.</span></span>

