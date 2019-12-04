---
title: Annullera ett planeringsjobb
description: I det här avsnittet beskrivs hur du avbryter ett aktivt planeringsjobb där funktionerna för planeringsoptimering används.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774056"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="45f7b-103">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="45f7b-103">Cancel a planning job</span></span>

<span data-ttu-id="45f7b-104">I Microsoft Dynamics 365 Supply Chain Management kan du avbryta ett aktivt planeringsjobb där funktionerna för planeringsoptimering används.</span><span class="sxs-lookup"><span data-stu-id="45f7b-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="45f7b-105">Om du vill avbryta ett aktivt planeringsjobb följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="45f7b-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="45f7b-106">Endast aktiva jobb kan annulleras.</span><span class="sxs-lookup"><span data-stu-id="45f7b-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="45f7b-107">Gå till **huvudplanering \> inställning \> planer**.</span><span class="sxs-lookup"><span data-stu-id="45f7b-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="45f7b-108">Välj en lämplig plan för planeringskörningen.</span><span class="sxs-lookup"><span data-stu-id="45f7b-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="45f7b-109">Välj **historik**.</span><span class="sxs-lookup"><span data-stu-id="45f7b-109">Select **History**.</span></span>
4. <span data-ttu-id="45f7b-110">Markera planeringsjobbet som ska annulleras.</span><span class="sxs-lookup"><span data-stu-id="45f7b-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="45f7b-111">Välj **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="45f7b-111">Select **Cancel**.</span></span>

<span data-ttu-id="45f7b-112">Jobbstatus kommer att vara **annullerar** tills planeringsoptimeringstjänsten bekräftar att jobbet har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="45f7b-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="45f7b-113">Status kommer sedan att ändras till **annullerad**.</span><span class="sxs-lookup"><span data-stu-id="45f7b-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="45f7b-114">Om du vill se statusändringar måste du uppdatera sidan genom att välja **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="45f7b-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="45f7b-115">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="45f7b-115">Related resources</span></span>

[<span data-ttu-id="45f7b-116">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="45f7b-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="45f7b-117">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="45f7b-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="45f7b-118">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="45f7b-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="45f7b-119">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="45f7b-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="45f7b-120">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="45f7b-120">Apply filters to a plan</span></span>](plan-filters.md)
