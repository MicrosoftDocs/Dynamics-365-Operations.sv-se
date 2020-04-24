---
title: Planera med negativ lagerbehållning
description: Det här ämnet förklarar hur negativ behållning hanteras när du använder planeringsoptimering.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8803b0b90f22711b844442d16f717ab87dabf041
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209868"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="e1062-103">Planera med negativ lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="e1062-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1062-104">Om systemet visar en negativ total lagerbehållning behandlas kvantiteten som 0 (noll) i planeringsmotorn för att undvika överleverans.</span><span class="sxs-lookup"><span data-stu-id="e1062-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="e1062-105">Så här fungerar funktionen:</span><span class="sxs-lookup"><span data-stu-id="e1062-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="e1062-106">Funktionen för planeringsoptimering aggregerar lagerbehållningen till den lägsta nivån av disponeringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="e1062-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="e1062-107">(Till exempel om *plats* är inte en disponeringsdimensionen, planerar optimeringsaggregat för närvarande kvantiteter vid nivå *lagerställe*.)</span><span class="sxs-lookup"><span data-stu-id="e1062-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="e1062-108">Om den sammanlagda lagerbehållningen på den lägsta nivån för disponering är negativ, förutsätter systemet att lagerbehållningen verkligen är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="e1062-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1062-109">Planeringssystemet kan bara vara precis så exakt som indata.</span><span class="sxs-lookup"><span data-stu-id="e1062-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="e1062-110">Om inmatningsdata är felaktiga kommer negativa poster för lagerbehållning att visa att lagerinformationen i Microsoft Dynamics 365 Supply Chain Management inte är synkroniserad med den verkliga världen.</span><span class="sxs-lookup"><span data-stu-id="e1062-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="e1062-111">Därför är det fel på planeringsresultatet.</span><span class="sxs-lookup"><span data-stu-id="e1062-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="e1062-112">Om du vill få ett exakt planeringsresultat bör du minimera antalet poster som visar en negativ lagerbehållning.</span><span class="sxs-lookup"><span data-stu-id="e1062-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="e1062-113">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e1062-113">Example 1</span></span>

<span data-ttu-id="e1062-114">Lagerställe 13 konfigureras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e1062-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="e1062-115">**Disponeringskod:** Min./Max.</span><span class="sxs-lookup"><span data-stu-id="e1062-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="e1062-116">**Minimum:** 15 stycken</span><span class="sxs-lookup"><span data-stu-id="e1062-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="e1062-117">**Maximum:** 25 stycken</span><span class="sxs-lookup"><span data-stu-id="e1062-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="e1062-118">Disponeringsdimensionernas sista nivå är *lagerställe* och följande kvantiteter på lagerbehållning registreras på nivån *plats*:</span><span class="sxs-lookup"><span data-stu-id="e1062-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="e1062-119">**Plats 1, lagerställe 13, plats 1:** 20 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="e1062-120">**Plats 1 lagerställe 13, plats 2:** &minus;8 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="e1062-121">Därför är den aggregerade lagerbehållningen för lagerställe 13 är 12 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="e1062-122">(= 20 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-122">(= 20 pcs.</span></span> <span data-ttu-id="e1062-123">&minus; 8 stycken).</span><span class="sxs-lookup"><span data-stu-id="e1062-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="e1062-124">I det här fallet använder planeringsmotorn en samlad lagerbehållning på 12 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="e1062-125">för lagerställe 13.</span><span class="sxs-lookup"><span data-stu-id="e1062-125">for warehouse 13.</span></span>

<span data-ttu-id="e1062-126">Resultatet blir en planerad order på 13 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="e1062-127">(= 25 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-127">(= 25 pcs.</span></span> <span data-ttu-id="e1062-128">&minus; 12 stycken) för att fylla på lagerställe 13 från 12 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="e1062-129">till 25 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="e1062-130">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e1062-130">Example 2</span></span>

<span data-ttu-id="e1062-131">Lagerställe 13 konfigureras på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="e1062-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="e1062-132">**Disponeringskod:** Min./Max.</span><span class="sxs-lookup"><span data-stu-id="e1062-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="e1062-133">**Minimum:** 15 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="e1062-134">**Maximum:** 25 stycken</span><span class="sxs-lookup"><span data-stu-id="e1062-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="e1062-135">Disponeringsdimensionernas sista nivå är *lagerställe* och följande kvantiteter på lagerbehållning registreras på nivån *plats*:</span><span class="sxs-lookup"><span data-stu-id="e1062-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="e1062-136">**Plats 1, lagerställe 13, plats 1:** 4 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="e1062-137">**Plats 1 lagerställe 13, plats 2:** &minus;8 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="e1062-138">Därför är den aggregerade lagerbehållningen 13 är &minus;4 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="e1062-139">(= 4 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-139">(= 4 pcs.</span></span> <span data-ttu-id="e1062-140">&minus; 8 stycken).</span><span class="sxs-lookup"><span data-stu-id="e1062-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="e1062-141">Med andra ord är det mindre än 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="e1062-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="e1062-142">I det här fallet förutsätter planeringsmotorn att lagerbehållningen för lagerställe 13 är 0 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="e1062-143">i stället för &minus; 4 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="e1062-144">Resultatet blir en planerad order på 25 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="e1062-145">(= 25 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-145">(= 25 pcs.</span></span> <span data-ttu-id="e1062-146">&minus; 0 stycken) för att fylla på lagerställe 13 från 0 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="e1062-147">till 25 stycken.</span><span class="sxs-lookup"><span data-stu-id="e1062-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e1062-148">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="e1062-148">Related resources</span></span>

[<span data-ttu-id="e1062-149">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="e1062-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="e1062-150">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="e1062-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="e1062-151">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="e1062-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="e1062-152">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="e1062-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="e1062-153">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="e1062-153">Cancel a planning job</span></span>](cancel-planning-job.md)
