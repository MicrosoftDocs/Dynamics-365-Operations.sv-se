--- 
title: Tidsplanera kanban-jobb
description: "Den här proceduren fokuserar på att tidsplanera kanban-processjobb för en specifik arbetsgrupp."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fd6349c0da71a7fcf4429e7f6a2ef366afda6678
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="b5000-103">Tidsplanera kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="b5000-103">Schedule kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5000-104">Den här proceduren fokuserar på att tidsplanera kanban-processjobb för en specifik arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b5000-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="b5000-105">Proceduren "Förbered ett kanban-processjobb när material inte är tillgängliga" är en förutsättning när du skapar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="b5000-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="b5000-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="b5000-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b5000-107">Denna uppgift är avsedd för produktionslagerarbetsledaren och produktionsplaneraren som arbetar med kanbans.</span><span class="sxs-lookup"><span data-stu-id="b5000-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="b5000-108">Välj kanban-jobb för en arbetsgrupp</span><span class="sxs-lookup"><span data-stu-id="b5000-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="b5000-109">Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.</span><span class="sxs-lookup"><span data-stu-id="b5000-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="b5000-110">Expandera faktarutan Periodkapacitet</span><span class="sxs-lookup"><span data-stu-id="b5000-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="b5000-111">Expandera Kanban-faktaboxen.</span><span class="sxs-lookup"><span data-stu-id="b5000-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="b5000-112">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b5000-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b5000-113">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b5000-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b5000-114">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="b5000-114">Select work cell 1250.</span></span> <span data-ttu-id="b5000-115">Då filtreras vyn så att endast jobben för arbetsgrupp 1250 visas.</span><span class="sxs-lookup"><span data-stu-id="b5000-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="b5000-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="b5000-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b5000-117">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="b5000-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="b5000-118">Tidsplanera ett kanban-jobb i den första tillgängliga perioden</span><span class="sxs-lookup"><span data-stu-id="b5000-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="b5000-119">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b5000-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b5000-120">Välj den första raden i listan som statusen Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="b5000-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="b5000-121">Den prickiga ikonen i fältet Jobbstatus anger inte planerad.</span><span class="sxs-lookup"><span data-stu-id="b5000-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="b5000-122">Klicka på Tidsplanera.</span><span class="sxs-lookup"><span data-stu-id="b5000-122">Click Schedule.</span></span>
    * <span data-ttu-id="b5000-123">Kanban-jobbet tidsplaneras i den första tillgängliga perioden.</span><span class="sxs-lookup"><span data-stu-id="b5000-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="b5000-124">Observera att kanban-jobb flyttas till slutet av listan, eftersom de har lagts till den period som startar från idag.</span><span class="sxs-lookup"><span data-stu-id="b5000-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="b5000-125">Om den period som startar från dagens datum är fullbokad, kommer jobbet flyttas till den första tillgängliga perioden.</span><span class="sxs-lookup"><span data-stu-id="b5000-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="b5000-126">Tidsplanera två kanban-jobb för en specifik dag</span><span class="sxs-lookup"><span data-stu-id="b5000-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="b5000-127">Väl rad 1 i listan.</span><span class="sxs-lookup"><span data-stu-id="b5000-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="b5000-128">Du bör se att den första raden har statusen Inte planerad i fältet Jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="b5000-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="b5000-129">Väl rad 2 i listan.</span><span class="sxs-lookup"><span data-stu-id="b5000-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="b5000-130">Du bör se att den andra raden har statusen Inte planerad i fältet Jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="b5000-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="b5000-131">Nu har de två första jobben valts.</span><span class="sxs-lookup"><span data-stu-id="b5000-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="b5000-132">Klicka på Tidsplan från den om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="b5000-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="b5000-133">Markera eller avmarkera rutan Åsidosätt reaktion på standardkapacitetsbrist.</span><span class="sxs-lookup"><span data-stu-id="b5000-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="b5000-134">Med det här alternativet kan du åsidosätta reaktionen på standardkapacitetsbristen.</span><span class="sxs-lookup"><span data-stu-id="b5000-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="b5000-135">Välj "Lägg till i den begärda perioden" i fältet Reaktion på kapacitetsbrist.</span><span class="sxs-lookup"><span data-stu-id="b5000-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="b5000-136">Med det här alternativet läggs jobbet till i den begärda perioden oavsett om arbetsgruppen kanske är överbelagd.</span><span class="sxs-lookup"><span data-stu-id="b5000-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="b5000-137">Klicka på Tidsplanera.</span><span class="sxs-lookup"><span data-stu-id="b5000-137">Click Schedule.</span></span>
    * <span data-ttu-id="b5000-138">Observera att båda jobben anges till den önskade perioden.</span><span class="sxs-lookup"><span data-stu-id="b5000-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="b5000-139">I avsnittet Periodkapacitet kan du visa beläggningen för varje period.</span><span class="sxs-lookup"><span data-stu-id="b5000-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="b5000-140">I fältet Förbrukning visas den tidsplanerade förbrukningen i denna period.</span><span class="sxs-lookup"><span data-stu-id="b5000-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="b5000-141">Om den tidsplanerade förbrukningen är högre än den tillgängliga kapaciteten i denna period, kommer den överbelagda förbrukningen att markeras.</span><span class="sxs-lookup"><span data-stu-id="b5000-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  


