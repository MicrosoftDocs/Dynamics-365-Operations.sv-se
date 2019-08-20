---
title: Tidsplanera en produktionsorder med operationer och jobbplanering
description: Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4932cfa472c34a16249b226aa4a07b8e5f528053
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838497"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="f8eef-103">Tidsplanera en produktionsorder med operationer och jobbplanering</span><span class="sxs-lookup"><span data-stu-id="f8eef-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8eef-104">Den här proceduren fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.</span><span class="sxs-lookup"><span data-stu-id="f8eef-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="f8eef-105">Inga jobb skapas med grovplanering medan jobb skapas med finplanering.</span><span class="sxs-lookup"><span data-stu-id="f8eef-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="f8eef-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="f8eef-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="f8eef-107">Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.</span><span class="sxs-lookup"><span data-stu-id="f8eef-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="f8eef-108">Skapa en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="f8eef-108">Create a production order</span></span>
1. <span data-ttu-id="f8eef-109">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="f8eef-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="f8eef-110">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="f8eef-110">Click New production order.</span></span>
3. <span data-ttu-id="f8eef-111">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="f8eef-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="f8eef-112">Välj artikelnummer D0001.</span><span class="sxs-lookup"><span data-stu-id="f8eef-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="f8eef-113">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="f8eef-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="f8eef-114">Tidsplanera åtgärder för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="f8eef-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="f8eef-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f8eef-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f8eef-116">Välj den tillverkningsorder som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="f8eef-116">Select the production order that you have just created.</span></span> <span data-ttu-id="f8eef-117">Den bör vara överst i listan.</span><span class="sxs-lookup"><span data-stu-id="f8eef-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="f8eef-118">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f8eef-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="f8eef-119">Klicka på Tidsplanera operationer.</span><span class="sxs-lookup"><span data-stu-id="f8eef-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="f8eef-120">Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.</span><span class="sxs-lookup"><span data-stu-id="f8eef-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="f8eef-121">Ange ett datum i fältet Planeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="f8eef-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="f8eef-122">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="f8eef-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="f8eef-123">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="f8eef-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="f8eef-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f8eef-124">Click OK.</span></span>
7. <span data-ttu-id="f8eef-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f8eef-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f8eef-126">Observera att statusen ändras till Tidsplanerad.</span><span class="sxs-lookup"><span data-stu-id="f8eef-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="f8eef-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f8eef-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f8eef-128">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="f8eef-128">Click All jobs.</span></span>
    * <span data-ttu-id="f8eef-129">Observera att inga jobb skapas med grovplanering.</span><span class="sxs-lookup"><span data-stu-id="f8eef-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="f8eef-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f8eef-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="f8eef-131">Tidsplanera jobben för produktionsordern</span><span class="sxs-lookup"><span data-stu-id="f8eef-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="f8eef-132">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f8eef-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="f8eef-133">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="f8eef-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="f8eef-134">Välj "Framåt från tidsplaneringsdatum" i fältet Planeringsriktning.</span><span class="sxs-lookup"><span data-stu-id="f8eef-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="f8eef-135">Ange ett datum i fältet Planeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="f8eef-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="f8eef-136">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="f8eef-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="f8eef-137">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="f8eef-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="f8eef-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f8eef-138">Click OK.</span></span>
6. <span data-ttu-id="f8eef-139">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f8eef-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="f8eef-140">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="f8eef-140">Click All jobs.</span></span>
    * <span data-ttu-id="f8eef-141">Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.</span><span class="sxs-lookup"><span data-stu-id="f8eef-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

