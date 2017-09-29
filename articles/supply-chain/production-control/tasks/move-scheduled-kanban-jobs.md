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
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="f67c6-103">Flytta tidsplanerade kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="f67c6-103">Move scheduled kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f67c6-104">Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="f67c6-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="f67c6-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f67c6-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren som arbetar med kanbans.</span><span class="sxs-lookup"><span data-stu-id="f67c6-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="f67c6-107">Välj tidsplanerade kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="f67c6-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="f67c6-108">Gå till Produktionsstyring > Kanban > Tidsplanering av kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="f67c6-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="f67c6-109">!MtCMR!Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="f67c6-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="f67c6-110">áçêìõý!</span><span class="sxs-lookup"><span data-stu-id="f67c6-110">áçêìõý !</span></span>
3. <span data-ttu-id="f67c6-111">På för række för Markér hålavalgte lyssnar.</span><span class="sxs-lookup"><span data-stu-id="f67c6-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="f67c6-112">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="f67c6-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="f67c6-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="f67c6-113">Klik på Select.</span></span>
5. <span data-ttu-id="f67c6-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="f67c6-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="f67c6-115">Jobblistan filtreras så att endast de tidsplanerade kanban-jobben visas.</span><span class="sxs-lookup"><span data-stu-id="f67c6-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="f67c6-116">Flytta kanban-jobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="f67c6-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="f67c6-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="f67c6-118">Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 20 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="f67c6-119">Flytta sedan jobbet till föregående period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="f67c6-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="f67c6-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="f67c6-121">Klik på End.</span></span>
    * <span data-ttu-id="f67c6-122">Jobbet flyttas till slutet av jobblistan som det sista jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="f67c6-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="f67c6-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="f67c6-124">Markera ett jobb som har statusen Planerat jobb, till exempel ett jobb som har tidsplanerats den 18 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="f67c6-125">Flytta sedan jobbet till nästa period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="f67c6-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-126">Klik på Next period.</span></span>
6. <span data-ttu-id="f67c6-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="f67c6-127">Klik på Start.</span></span>
    * <span data-ttu-id="f67c6-128">Jobbet flyttas till början av jobblistan som det sista första jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="f67c6-129">Uppgift: Flytta ett jobb inom en period</span><span class="sxs-lookup"><span data-stu-id="f67c6-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="f67c6-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="f67c6-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="f67c6-131">Markera ett jobb som har statusen Planerat jobb, till exempel det andra jobbet som har tidsplanerats den 19 december 2012 i fältet Planerad period.</span><span class="sxs-lookup"><span data-stu-id="f67c6-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="f67c6-132">Flytta sedan jobbet inom den planerade perioden.</span><span class="sxs-lookup"><span data-stu-id="f67c6-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="f67c6-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="f67c6-133">Klik på Forward.</span></span>
    * <span data-ttu-id="f67c6-134">Observera att jobbet flyttas en rad ned på listan.</span><span class="sxs-lookup"><span data-stu-id="f67c6-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="f67c6-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="f67c6-135">Klik på Backward.</span></span>
    * <span data-ttu-id="f67c6-136">Observera att jobbet flyttas en rad upp på listan.</span><span class="sxs-lookup"><span data-stu-id="f67c6-136">Notice that the job is moved one line up on the list.</span></span>  


