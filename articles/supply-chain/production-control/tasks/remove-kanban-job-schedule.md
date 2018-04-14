--- 
title: "Ta bort ett kanban-jobb från tidsplanen"
description: "Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad."
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7304c6cac1f31c179231f72d05ee4d02502d4ca3
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="d370c-103">Ta bort ett kanban-jobb från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="d370c-103">Remove a kanban job from the schedule</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d370c-104">Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="d370c-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="d370c-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d370c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d370c-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="d370c-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="d370c-107">Sök efter ett planerat kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="d370c-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="d370c-108">Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.</span><span class="sxs-lookup"><span data-stu-id="d370c-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="d370c-109">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d370c-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d370c-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d370c-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d370c-111">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="d370c-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="d370c-112">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="d370c-112">Click Select.</span></span>
5. <span data-ttu-id="d370c-113">Välj "Tidsplanerad" i fältet Visa jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="d370c-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="d370c-114">Ta bort det planerade kanban-jobbet från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="d370c-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="d370c-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d370c-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d370c-116">Välj ett jobb som har statusen Planerad, till exempel ett jobb från 19 december, 2012.</span><span class="sxs-lookup"><span data-stu-id="d370c-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="d370c-117">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d370c-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="d370c-118">Klicka på Återställ jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="d370c-118">Click Revert job status.</span></span>
4. <span data-ttu-id="d370c-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d370c-119">Click OK.</span></span>
    * <span data-ttu-id="d370c-120">Då återställs den aktuella jobbstatusen från "Planerad" till "Inte planerad" och tas bort från processtavlan.</span><span class="sxs-lookup"><span data-stu-id="d370c-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   


