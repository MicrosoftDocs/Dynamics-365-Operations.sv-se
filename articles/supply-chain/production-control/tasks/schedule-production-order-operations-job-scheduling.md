--- 
title: Tidsplanera en produktionsorder med operationer och jobbplanering
description: "Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 690a0d2db67bc7a13adf186e3e9c3b9238932eb0
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="6e68b-103">Tidsplanera en produktionsorder med operationer och jobbplanering</span><span class="sxs-lookup"><span data-stu-id="6e68b-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e68b-104">Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.</span><span class="sxs-lookup"><span data-stu-id="6e68b-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="6e68b-105">Inga jobb skapas med grovplanering medan jobb skapas med finplanering.</span><span class="sxs-lookup"><span data-stu-id="6e68b-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="6e68b-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="6e68b-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="6e68b-107">Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.</span><span class="sxs-lookup"><span data-stu-id="6e68b-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="6e68b-108">Skapa en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="6e68b-108">Create a production order</span></span>
1. <span data-ttu-id="6e68b-109">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="6e68b-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="6e68b-110">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="6e68b-110">Click New production order.</span></span>
3. <span data-ttu-id="6e68b-111">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="6e68b-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="6e68b-112">Välj artikelnummer D0001.</span><span class="sxs-lookup"><span data-stu-id="6e68b-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="6e68b-113">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="6e68b-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="6e68b-114">Tidsplanera åtgärder för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="6e68b-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="6e68b-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6e68b-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6e68b-116">Välj den tillverkningsorder som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="6e68b-116">Select the production order that you have just created.</span></span> <span data-ttu-id="6e68b-117">Den bör vara överst i listan.</span><span class="sxs-lookup"><span data-stu-id="6e68b-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="6e68b-118">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6e68b-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="6e68b-119">Klicka på Tidsplanera operationer.</span><span class="sxs-lookup"><span data-stu-id="6e68b-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="6e68b-120">Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.</span><span class="sxs-lookup"><span data-stu-id="6e68b-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="6e68b-121">Ange ett datum i fältet Planeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="6e68b-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="6e68b-122">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="6e68b-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="6e68b-123">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="6e68b-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="6e68b-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6e68b-124">Click OK.</span></span>
7. <span data-ttu-id="6e68b-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6e68b-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6e68b-126">Observera att statusen ändras till Tidsplanerad.</span><span class="sxs-lookup"><span data-stu-id="6e68b-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="6e68b-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="6e68b-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6e68b-128">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="6e68b-128">Click All jobs.</span></span>
    * <span data-ttu-id="6e68b-129">Observera att inga jobb skapas med grovplanering.</span><span class="sxs-lookup"><span data-stu-id="6e68b-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="6e68b-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6e68b-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="6e68b-131">Tidsplanera jobben för produktionsordern</span><span class="sxs-lookup"><span data-stu-id="6e68b-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="6e68b-132">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6e68b-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="6e68b-133">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="6e68b-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="6e68b-134">Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.</span><span class="sxs-lookup"><span data-stu-id="6e68b-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="6e68b-135">Ange ett datum i fältet Planeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="6e68b-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="6e68b-136">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="6e68b-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="6e68b-137">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="6e68b-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="6e68b-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6e68b-138">Click OK.</span></span>
6. <span data-ttu-id="6e68b-139">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="6e68b-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="6e68b-140">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="6e68b-140">Click All jobs.</span></span>
    * <span data-ttu-id="6e68b-141">Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.</span><span class="sxs-lookup"><span data-stu-id="6e68b-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  


