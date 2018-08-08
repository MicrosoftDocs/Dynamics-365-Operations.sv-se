--- 
title: Flytta tidsplanerade kanban-jobb
description: "Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6461e5638eaddeaeaef82304b7976bad350b331e
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="cfaad-103">Flytta tidsplanerade kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="cfaad-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cfaad-104">Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="cfaad-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="cfaad-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cfaad-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren som arbetar med kanbans.</span><span class="sxs-lookup"><span data-stu-id="cfaad-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="cfaad-107">Välj tidsplanerade kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="cfaad-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="cfaad-108">Gå till Produktionsstyring > Kanban > Tidsplanering av kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="cfaad-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="cfaad-109">!MtCMR!Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="cfaad-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="cfaad-110">áçêìõý!</span><span class="sxs-lookup"><span data-stu-id="cfaad-110">áçêìõý !</span></span>
3. <span data-ttu-id="cfaad-111">På för række för Markér hålavalgte lyssnar.</span><span class="sxs-lookup"><span data-stu-id="cfaad-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="cfaad-112">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="cfaad-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="cfaad-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="cfaad-113">Klik på Select.</span></span>
5. <span data-ttu-id="cfaad-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="cfaad-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="cfaad-115">Jobblistan filtreras så att endast de tidsplanerade kanban-jobben visas.</span><span class="sxs-lookup"><span data-stu-id="cfaad-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="cfaad-116">Flytta kanban-jobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="cfaad-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="cfaad-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="cfaad-118">Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 20 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="cfaad-119">Flytta sedan jobbet till föregående period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="cfaad-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="cfaad-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="cfaad-121">Klik på End.</span></span>
    * <span data-ttu-id="cfaad-122">Jobbet flyttas till slutet av jobblistan som det sista jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="cfaad-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="cfaad-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="cfaad-124">Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 18 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="cfaad-125">Flytta sedan jobbet till nästa period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="cfaad-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-126">Klik på Next period.</span></span>
6. <span data-ttu-id="cfaad-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="cfaad-127">Klik på Start.</span></span>
    * <span data-ttu-id="cfaad-128">Jobbet flyttas till början av jobblistan som det sista första jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="cfaad-129">Uppgift: Flytta ett jobb inom en period</span><span class="sxs-lookup"><span data-stu-id="cfaad-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="cfaad-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="cfaad-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="cfaad-131">Markera ett jobb som har statusen Planerat jobb, till exempel det andra jobbet som har tidsplanerats den 19 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="cfaad-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="cfaad-132">Flytta sedan jobbet inom den planerade perioden.</span><span class="sxs-lookup"><span data-stu-id="cfaad-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="cfaad-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="cfaad-133">Klik på Forward.</span></span>
    * <span data-ttu-id="cfaad-134">Observera att jobbet flyttas en rad ned på listan.</span><span class="sxs-lookup"><span data-stu-id="cfaad-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="cfaad-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="cfaad-135">Klik på Backward.</span></span>
    * <span data-ttu-id="cfaad-136">Observera att jobbet flyttas en rad upp på listan.</span><span class="sxs-lookup"><span data-stu-id="cfaad-136">Notice that the job is moved one line up on the list.</span></span>  


