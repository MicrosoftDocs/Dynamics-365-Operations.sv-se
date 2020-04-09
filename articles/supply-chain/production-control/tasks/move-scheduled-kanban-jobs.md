---
title: Flytta tidsplanerade kanban-jobb
description: Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cad61ad292f80d6092ecea679645f729469b8a8f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149008"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="1fd4b-103">Flytta tidsplanerade kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="1fd4b-103">Move scheduled kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1fd4b-104">Proceduren fokuserar på att flytta planerade kanban-processjobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="1fd4b-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1fd4b-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren som arbetar med kanbans.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="1fd4b-107">Välj tidsplanerade kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="1fd4b-108">Gå till **Produktionskontroll > Kanban > Kanban-jobbplanering**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="1fd4b-109">I fältet **Arbetsgrupp**, klicka på den nedrullningsbara knappen för att öppna uppslaget.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="1fd4b-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="1fd4b-111">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="1fd4b-112">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-112">Click **Select**.</span></span> 

5. <span data-ttu-id="1fd4b-113">I fältet **Visa jobbstatus**, välj **Tidsplanerad**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="1fd4b-114">Jobblistan filtreras så att endast de tidsplanerade kanban-jobben visas.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="1fd4b-115">Flytta kanban-jobb till en annan period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="1fd4b-116">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="1fd4b-117">Markera ett jobb som har statusen **Planerat jobb** till exempel ett jobb som har tidsplanerats den 20 december 2012 i fältet **Planerad period**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="1fd4b-118">Flytta sedan jobbet till föregående period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="1fd4b-119">Klicka på **Föregående period**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="1fd4b-120">Klicka på **Slut** för att flytta jobbet till slutet av jobblistan som det sista jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="1fd4b-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="1fd4b-122">Markera ett jobb som har statusen **Planerat jobb** till exempel ett jobb som har tidsplanerats den 18 december 2012 i fältet **Planerad period**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="1fd4b-123">Flytta sedan jobbet till nästa period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="1fd4b-124">Klicka på **Nästa period**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="1fd4b-125">Klicka på **Start** för att flytta jobbet till start av jobblistan som det första jobbet i föregående period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="1fd4b-126">Flytta ett jobb inom en period.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="1fd4b-127">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="1fd4b-128">Markera ett jobb som har statusen Planerat jobb, till exempel det andra jobbet som har tidsplanerats den 19 december 2012 i fältet **Planerad period**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="1fd4b-129">Flytta sedan jobbet inom den planerade perioden.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="1fd4b-130">Klicka på **Framåt.**</span><span class="sxs-lookup"><span data-stu-id="1fd4b-130">Click **Forward**.</span></span> <span data-ttu-id="1fd4b-131">Observera att jobbet flyttas en rad ned på listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="1fd4b-132">Klicka på **Bakåt**.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-132">Click **Backward**.</span></span> <span data-ttu-id="1fd4b-133">Observera att jobbet flyttas en rad upp på listan.</span><span class="sxs-lookup"><span data-stu-id="1fd4b-133">Notice that the job is moved one line up on the list.</span></span>
