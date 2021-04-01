---
title: Annullera ett planeringsjobb
description: I det här avsnittet beskrivs hur du avbryter ett aktivt planeringsjobb där funktionerna för planeringsoptimering används.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 5aadf7fb94bb2d836892064837f9cb1c5790d657
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238024"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="1cf73-103">Avbryta ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="1cf73-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1cf73-104">I Microsoft Dynamics 365 Supply Chain Management kan du avbryta ett aktivt planeringsjobb där funktionerna för planeringsoptimering används.</span><span class="sxs-lookup"><span data-stu-id="1cf73-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="1cf73-105">När du väljer **Avbryt** i dialogrutan när ett planeringsoptimeringsjobb utlöses direkt från användargränssnittet (inte i bakgrunden) avbryts inte jobbet planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="1cf73-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="1cf73-106">Även om du får en varning om att "åtgärden har avbrutits", måste du ändå använda följande steg för att avbryta ett planeringsjobb med planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="1cf73-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="1cf73-107">Om du vill avbryta ett aktivt planeringsjobb följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="1cf73-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="1cf73-108">Endast aktiva jobb kan annulleras.</span><span class="sxs-lookup"><span data-stu-id="1cf73-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="1cf73-109">Gå till **huvudplanering \> inställning \> planer**.</span><span class="sxs-lookup"><span data-stu-id="1cf73-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="1cf73-110">Välj en lämplig plan för planeringskörningen.</span><span class="sxs-lookup"><span data-stu-id="1cf73-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="1cf73-111">Välj **historik**.</span><span class="sxs-lookup"><span data-stu-id="1cf73-111">Select **History**.</span></span>
4. <span data-ttu-id="1cf73-112">Markera planeringsjobbet som ska annulleras.</span><span class="sxs-lookup"><span data-stu-id="1cf73-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="1cf73-113">Välj **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="1cf73-113">Select **Cancel**.</span></span>

<span data-ttu-id="1cf73-114">Jobbstatus kommer att vara **annullerar** tills planeringsoptimeringstjänsten bekräftar att jobbet har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="1cf73-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="1cf73-115">Status kommer sedan att ändras till **annullerad**.</span><span class="sxs-lookup"><span data-stu-id="1cf73-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="1cf73-116">Om du vill se statusändringar måste du uppdatera sidan genom att välja **uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="1cf73-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1cf73-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1cf73-117">Additional resources</span></span>

[<span data-ttu-id="1cf73-118">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="1cf73-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="1cf73-119">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="1cf73-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="1cf73-120">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="1cf73-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="1cf73-121">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="1cf73-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="1cf73-122">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="1cf73-122">Apply filters to a plan</span></span>](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]