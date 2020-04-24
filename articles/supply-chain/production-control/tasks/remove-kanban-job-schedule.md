---
title: Ta bort ett kanban-jobb från tidsplanen
description: Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0236faa9b534678ed232ac3572c8172c62e5241f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210608"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="56a32-103">Ta bort ett kanban-jobb från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="56a32-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="56a32-104">Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="56a32-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="56a32-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="56a32-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="56a32-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="56a32-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="56a32-107">Sök efter ett planerat kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="56a32-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="56a32-108">Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.</span><span class="sxs-lookup"><span data-stu-id="56a32-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="56a32-109">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="56a32-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="56a32-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="56a32-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="56a32-111">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="56a32-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="56a32-112">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="56a32-112">Click Select.</span></span>
5. <span data-ttu-id="56a32-113">Välj "Tidsplanerad" i fältet Visa jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="56a32-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="56a32-114">Ta bort det planerade kanban-jobbet från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="56a32-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="56a32-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="56a32-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="56a32-116">Välj ett jobb som har statusen Planerad, till exempel ett jobb från 19 december, 2012.</span><span class="sxs-lookup"><span data-stu-id="56a32-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="56a32-117">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="56a32-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="56a32-118">Klicka på Återställ jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="56a32-118">Click Revert job status.</span></span>
4. <span data-ttu-id="56a32-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56a32-119">Click OK.</span></span>
    * <span data-ttu-id="56a32-120">Då återställs den aktuella jobbstatusen från "Planerad" till "Inte planerad" och tas bort från processtavlan.</span><span class="sxs-lookup"><span data-stu-id="56a32-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

