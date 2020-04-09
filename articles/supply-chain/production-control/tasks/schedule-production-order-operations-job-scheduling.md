---
title: Tidsplanera en produktionsorder med operationer och jobbplanering
description: Det här avsnittet fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.
author: ChristianRytt
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 2181a84aea08aac0ddb202f7211dbda6330a3d49
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148847"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="d7f19-103">Tidsplanera en produktionsorder med operationer och jobbplanering</span><span class="sxs-lookup"><span data-stu-id="d7f19-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7f19-104">Det här avsnittet fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.</span><span class="sxs-lookup"><span data-stu-id="d7f19-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="d7f19-105">Inga jobb skapas med grovplanering medan jobb skapas med finplanering.</span><span class="sxs-lookup"><span data-stu-id="d7f19-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="d7f19-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="d7f19-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="d7f19-107">Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.</span><span class="sxs-lookup"><span data-stu-id="d7f19-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="d7f19-108">Skapa en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="d7f19-108">Create a production order</span></span>
1. <span data-ttu-id="d7f19-109">I Navigeringsfönster, gå till **Moduler > Produktionskontroll > Produktionsorder > Alla produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="d7f19-110">Välj **Ny produktionsorder**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-110">Select **New production order**.</span></span>
3. <span data-ttu-id="d7f19-111">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="d7f19-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="d7f19-112">Välj artikelnummer **D0001**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="d7f19-113">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="d7f19-114">Tidsplanera åtgärder för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="d7f19-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="d7f19-115">Markera den nyss skapade raden.</span><span class="sxs-lookup"><span data-stu-id="d7f19-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="d7f19-116">I åtgärdsfönstret, välj **Tidsplan**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="d7f19-117">Välj **Tidsplanera operationer**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="d7f19-118">Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="d7f19-119">Ange ett datum i fältet **Planeringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="d7f19-120">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="d7f19-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="d7f19-121">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="d7f19-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="d7f19-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-122">Select **OK**.</span></span>
7. <span data-ttu-id="d7f19-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d7f19-123">In the list, mark the selected row.</span></span> <span data-ttu-id="d7f19-124">Observera att statusen ändras till **Tidsplanerad**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="d7f19-125">Välj **Alla jobb**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-125">Select **All jobs**.</span></span> <span data-ttu-id="d7f19-126">Observera att inga jobb skapas med grovplanering.</span><span class="sxs-lookup"><span data-stu-id="d7f19-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="d7f19-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d7f19-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="d7f19-128">Tidsplanera jobben för produktionsordern</span><span class="sxs-lookup"><span data-stu-id="d7f19-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="d7f19-129">I åtgärdsfönstret, välj **Tidsplan**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="d7f19-130">Välj **Tidsplanera jobb**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="d7f19-131">Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="d7f19-132">Ange ett datum i fältet **Planeringsdatum**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="d7f19-133">Välj ett framtida datum, till exempel idag plus en vecka.</span><span class="sxs-lookup"><span data-stu-id="d7f19-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="d7f19-134">Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.</span><span class="sxs-lookup"><span data-stu-id="d7f19-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="d7f19-135">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-135">Select **OK**.</span></span>
6. <span data-ttu-id="d7f19-136">Välj **Produktionsorder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d7f19-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="d7f19-137">Välj **Alla jobb**.</span><span class="sxs-lookup"><span data-stu-id="d7f19-137">Select **All jobs**.</span></span> <span data-ttu-id="d7f19-138">Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.</span><span class="sxs-lookup"><span data-stu-id="d7f19-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

