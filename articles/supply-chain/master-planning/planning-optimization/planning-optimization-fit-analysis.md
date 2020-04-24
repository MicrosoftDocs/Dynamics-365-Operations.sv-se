---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 10/30/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 17114d4c0ef2c74ab1bb56d41e4a008150c21f36
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208764"
---
# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="e0c93-103">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="e0c93-103">Planning Optimization fit analysis</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0c93-104">Om du vill se hur kompatibla aktuella inställningar och data är med funktionen för planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Planera analys av optimeringsanpassning** och väljer sedan **Kör analys**.</span><span class="sxs-lookup"><span data-stu-id="e0c93-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="e0c93-105">Om analysen hittar eventuella inkonsekvenser visas de på samma sida.</span><span class="sxs-lookup"><span data-stu-id="e0c93-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="e0c93-106">(Det kan ta några minuter att köra analysen.)</span><span class="sxs-lookup"><span data-stu-id="e0c93-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="e0c93-107">Om inkonsekvenser hittas kan du fortfarande använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="e0c93-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="e0c93-108">Resultaten av anpassningsanalysen visar bara platser där planeringstjänsten inte ska svara på den aktuella inställningen.</span><span class="sxs-lookup"><span data-stu-id="e0c93-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="e0c93-109">Med andra ord visar de platser där vissa processer kan ignoreras eller kanske inte stöds.</span><span class="sxs-lookup"><span data-stu-id="e0c93-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="e0c93-110">Analysresultat: exempel 1</span><span class="sxs-lookup"><span data-stu-id="e0c93-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="e0c93-111">**Funktion:** produktion</span><span class="sxs-lookup"><span data-stu-id="e0c93-111">**Feature:** Production</span></span>
- <span data-ttu-id="e0c93-112">**Problem:** artiklar med strukturlistenivåer större än noll: 56</span><span class="sxs-lookup"><span data-stu-id="e0c93-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="e0c93-113">**Förklaring:** anpassningsanalysen hittade 56 artiklar som har en inställning för strukturlista (BOM) för produktion.</span><span class="sxs-lookup"><span data-stu-id="e0c93-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="e0c93-114">Eftersom den aktuella versionen av planeringsoptimering inte stöder produktionen genererar planeringsoptimering planerade inköpsorder istället för planerade tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="e0c93-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="e0c93-115">Dessutom visas en varning med en lista över de objekt som påverkas.</span><span class="sxs-lookup"><span data-stu-id="e0c93-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="e0c93-116">Analysresultat: exempel 2</span><span class="sxs-lookup"><span data-stu-id="e0c93-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="e0c93-117">**Funktion:** åtgärder</span><span class="sxs-lookup"><span data-stu-id="e0c93-117">**Feature:** Actions</span></span>
- <span data-ttu-id="e0c93-118">**Problem:** Disponeringsgrupper med aktiverad åtgärdsberäkning: 6</span><span class="sxs-lookup"><span data-stu-id="e0c93-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="e0c93-119">**Förklaring:** anpassningsanalysen hittade sex disponeringsgrupper där åtgärdsberäkning är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="e0c93-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="e0c93-120">Eftersom den aktuella versionen av planeringsoptimering inte stöder åtgärder kommer inga åtgärder att genereras under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="e0c93-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e0c93-121">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="e0c93-121">Related resources</span></span>

[<span data-ttu-id="e0c93-122">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="e0c93-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="e0c93-123">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="e0c93-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="e0c93-124">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="e0c93-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="e0c93-125">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="e0c93-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="e0c93-126">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="e0c93-126">Cancel a planning job</span></span>](cancel-planning-job.md)
