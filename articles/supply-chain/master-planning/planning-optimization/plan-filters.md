---
title: Använda filter på en plan
description: I det här avsnittet beskrivs hur använder filter på en plan när funktionerna för planeringsoptimering används.
author: ChristianRytt
manager: AnnBe
ms.date: 01/08/2020
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
ms.openlocfilehash: 9d1431cc8db6fb28d1f1ec73ee07dd15e78f82e8
ms.sourcegitcommit: 65f4b8a751670a7fe9ef4cb8b218213f792d57a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945429"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="2a989-103">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="2a989-103">Apply filters to a plan</span></span>

<span data-ttu-id="2a989-104">När funktionen för planeringsoptimering används kan du använda ett filter på en plan.</span><span class="sxs-lookup"><span data-stu-id="2a989-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="2a989-105">**Planfiltret** används alltid vid en huvudplaneringskörning.</span><span class="sxs-lookup"><span data-stu-id="2a989-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="2a989-106">Ett **planfilter** är användbart när du vill begränsa en plan till en viss grupp av artiklar och se till att inga andra artiklar ingår i den resulterande huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="2a989-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="2a989-107">Om ett **planfilter** används och ett körningsfilter också används under huvudplaneringskörningen, inkluderas bara skärningen mellan de två filtren i planeringskörningen.</span><span class="sxs-lookup"><span data-stu-id="2a989-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="2a989-108">**Planfiltret** kan nås från **huvudplaner** när planeringsoptimering används.</span><span class="sxs-lookup"><span data-stu-id="2a989-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="2a989-109">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="2a989-109">Example scenario</span></span>

<span data-ttu-id="2a989-110">Ett planfilter är en inställning som omfattar artiklarna A, B och C. Huvudplaneringskörningarna körs sedan för samma plan, men olika körningsfilter tillämpas:</span><span class="sxs-lookup"><span data-stu-id="2a989-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="2a989-111">**Körningsfilter som innehåller artikel D:** inga artiklar planeras eftersom det inte finns någon överlappning mellan planfiltret och körningsfiltret.</span><span class="sxs-lookup"><span data-stu-id="2a989-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="2a989-112">**Körningsfilter som innehåller artikel A och D:** endast artikel A ingår i planeringskörningen, eftersom artikel D inte ingår i planfiltret.</span><span class="sxs-lookup"><span data-stu-id="2a989-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="2a989-113">**Körningsfilter som innehåller artikel B:** endast artikel B ingår i planeringskörningen och det tidigare planeringsresultatet för artikel A behålls.</span><span class="sxs-lookup"><span data-stu-id="2a989-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="2a989-114">**Körningsfilter som innehåller alla poster (tomt filter)** : artiklarna A, B och C inkluderas i planeringskörningen och föregående planeringsresultat för artiklarna A och B skrivs över.</span><span class="sxs-lookup"><span data-stu-id="2a989-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="2a989-115">Du bör inte ange ett planfilter för planen som har valts som **Aktuell dynamisk huvudplan** på sidan för **huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="2a989-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="2a989-116">Annars kommer funktionen för dynamisk huvudplan att begränsas till de filtrerade artiklarna.</span><span class="sxs-lookup"><span data-stu-id="2a989-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="2a989-117">Om till exempel nettobehoven uppdateras för en artikel som inte ingår i planfiltret, genereras inget resultat.</span><span class="sxs-lookup"><span data-stu-id="2a989-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="2a989-118">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="2a989-118">Related resources</span></span>

[<span data-ttu-id="2a989-119">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="2a989-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="2a989-120">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="2a989-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="2a989-121">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="2a989-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="2a989-122">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="2a989-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="2a989-123">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="2a989-123">Cancel a planning job</span></span>](cancel-planning-job.md)
