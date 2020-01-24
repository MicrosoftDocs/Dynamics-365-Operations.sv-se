---
title: Planera analys av optimeringsanpassning
description: I det här avsnittet beskrivs hur du kontrollerar dina aktuella inställningar och data mot funktionerna i funktionen för planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
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
ms.openlocfilehash: a61529da63bc20fdd591afc94db960b05c284bb9
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935885"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="003e4-103">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="003e4-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="003e4-104">Om du vill se hur kompatibla aktuella inställningar och data är med funktionen för planeringsoptimering går du till **Huvudplanering** \> **Inställningar** \> **Planera analys av optimeringsanpassning** och väljer sedan **Kör analys**.</span><span class="sxs-lookup"><span data-stu-id="003e4-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="003e4-105">Om analysen hittar eventuella inkonsekvenser visas de på samma sida.</span><span class="sxs-lookup"><span data-stu-id="003e4-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="003e4-106">(Det kan ta några minuter att köra analysen.)</span><span class="sxs-lookup"><span data-stu-id="003e4-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="003e4-107">Om inkonsekvenser hittas kan du fortfarande använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="003e4-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="003e4-108">Resultaten av anpassningsanalysen visar bara platser där planeringstjänsten inte ska svara på den aktuella inställningen.</span><span class="sxs-lookup"><span data-stu-id="003e4-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="003e4-109">Med andra ord visar de platser där vissa processer kan ignoreras eller kanske inte stöds.</span><span class="sxs-lookup"><span data-stu-id="003e4-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="003e4-110">Analysresultat: exempel 1</span><span class="sxs-lookup"><span data-stu-id="003e4-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="003e4-111">**Funktion:** produktion</span><span class="sxs-lookup"><span data-stu-id="003e4-111">**Feature:** Production</span></span>
- <span data-ttu-id="003e4-112">**Problem:** artiklar med strukturlistenivåer större än noll: 56</span><span class="sxs-lookup"><span data-stu-id="003e4-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="003e4-113">**Förklaring:** anpassningsanalysen hittade 56 artiklar som har en inställning för strukturlista (BOM) för produktion.</span><span class="sxs-lookup"><span data-stu-id="003e4-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="003e4-114">Eftersom den aktuella versionen av planeringsoptimering inte stöder produktionen genererar planeringsoptimering planerade inköpsorder istället för planerade tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="003e4-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="003e4-115">Dessutom visas en varning med en lista över de objekt som påverkas.</span><span class="sxs-lookup"><span data-stu-id="003e4-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="003e4-116">Analysresultat: exempel 2</span><span class="sxs-lookup"><span data-stu-id="003e4-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="003e4-117">**Funktion:** åtgärder</span><span class="sxs-lookup"><span data-stu-id="003e4-117">**Feature:** Actions</span></span>
- <span data-ttu-id="003e4-118">**Problem:** Disponeringsgrupper med aktiverad åtgärdsberäkning: 6</span><span class="sxs-lookup"><span data-stu-id="003e4-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="003e4-119">**Förklaring:** anpassningsanalysen hittade sex disponeringsgrupper där åtgärdsberäkning är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="003e4-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="003e4-120">Eftersom den aktuella versionen av planeringsoptimering inte stöder åtgärder kommer inga åtgärder att genereras under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="003e4-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="003e4-121">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="003e4-121">Related resources</span></span>

[<span data-ttu-id="003e4-122">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="003e4-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="003e4-123">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="003e4-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="003e4-124">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="003e4-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="003e4-125">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="003e4-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="003e4-126">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="003e4-126">Cancel a planning job</span></span>](cancel-planning-job.md)
