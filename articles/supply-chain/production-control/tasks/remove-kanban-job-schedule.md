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
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 566a174c631391577441e0f890bd9553dac0891c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204530"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="7ca23-103">Ta bort ett kanban-jobb från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="7ca23-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ca23-104">Den här proceduren fokuserar på att ta bort ett planerat kanban-processjobb från tidsplaneringen genom att återställa jobbstatusen till Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="7ca23-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="7ca23-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="7ca23-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7ca23-106">Proceduren är avsedd för produktionslagerarbetsledaren eller produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="7ca23-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="7ca23-107">Sök efter ett planerat kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="7ca23-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="7ca23-108">Gå till Produktionskontroll > Kanban > Kanban-jobbplanering.</span><span class="sxs-lookup"><span data-stu-id="7ca23-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="7ca23-109">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7ca23-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7ca23-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7ca23-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7ca23-111">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="7ca23-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="7ca23-112">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="7ca23-112">Click Select.</span></span>
5. <span data-ttu-id="7ca23-113">Välj "Tidsplanerad" i fältet Visa jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="7ca23-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="7ca23-114">Ta bort det planerade kanban-jobbet från tidsplanen</span><span class="sxs-lookup"><span data-stu-id="7ca23-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="7ca23-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7ca23-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7ca23-116">Välj ett jobb som har statusen Planerad, till exempel ett jobb från 19 december, 2012.</span><span class="sxs-lookup"><span data-stu-id="7ca23-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="7ca23-117">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7ca23-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="7ca23-118">Klicka på Återställ jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="7ca23-118">Click Revert job status.</span></span>
4. <span data-ttu-id="7ca23-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7ca23-119">Click OK.</span></span>
    * <span data-ttu-id="7ca23-120">Då återställs den aktuella jobbstatusen från "Planerad" till "Inte planerad" och tas bort från processtavlan.</span><span class="sxs-lookup"><span data-stu-id="7ca23-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]