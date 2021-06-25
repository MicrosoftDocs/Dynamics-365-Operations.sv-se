---
title: Visa planhistorik och planeringsloggar
description: I det här avsnittet beskrivs hur du visar historiken för planeringsjobb som löses av funktionen för planeringsoptimering.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187257"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="7ff9e-103">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="7ff9e-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ff9e-104">I det här avsnittet beskrivs hur du visar historiken för planeringsjobb som löses av funktionen för planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="7ff9e-105">Om du vill visa historiken för en plan öppnar du planen genom att gå till **huvudplanering** \> **inställningar** \> **planer** \> **huvudplaner** och väljer **historik**.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="7ff9e-106">I historiken visas alla jobb för den valda planen.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="7ff9e-107">Listan innehåller slutförda och aktiva jobb.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="7ff9e-108">Jobbhistoriken i huvudplaneringskörningarna för planeringsoptimeraren innehåller bara upp till 60 poster per huvudplan.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="7ff9e-109">När du kör en ny huvudplaneringsberäkning tas den planens tidigaste historikpost bort.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="7ff9e-110">Förutom att visa starttid och status för jobb kan du visa loggen för ett specifikt jobb.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="7ff9e-111">Loggen innehåller ytterligare information och varningar.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="7ff9e-112">Alla jobb har inte en logg.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-112">Not all jobs have a log.</span></span> <span data-ttu-id="7ff9e-113">Om du vill visa loggen för ett jobb väljer du **logg**.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="7ff9e-114">Loggposter lagras bara i 30 dagar efter det datum då jobbet avslutades, efter det att de raderas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7ff9e-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="7ff9e-115">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="7ff9e-115">Related resources</span></span>

- [<span data-ttu-id="7ff9e-116">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="7ff9e-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="7ff9e-117">Kom i gång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="7ff9e-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="7ff9e-118">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="7ff9e-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="7ff9e-119">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="7ff9e-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="7ff9e-120">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="7ff9e-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]