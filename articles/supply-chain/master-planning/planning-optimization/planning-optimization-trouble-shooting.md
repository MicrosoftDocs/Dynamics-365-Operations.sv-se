---
title: Felsöka planeringsoptimering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med planeringsoptimering.
author: ChristianRytt
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2100235fadabe6af87849aab7d9ec55d85ea66fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812893"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="82b21-103">Felsöka planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="82b21-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82b21-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="82b21-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="82b21-105">Installationen av tillägget för planeringsoptimering slutförs inte</span><span class="sxs-lookup"><span data-stu-id="82b21-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="82b21-106">Planeringsoptimering kräver en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="82b21-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="82b21-107">Om du försöker installera tillägget på i en OneBox-miljö slutförs inte installationen.</span><span class="sxs-lookup"><span data-stu-id="82b21-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="82b21-108">**Korrigering**: Avbryt installationen och använd en miljö med hög tillgänglighet, nivå 2 eller högre (inte en Onebox-miljö).</span><span class="sxs-lookup"><span data-stu-id="82b21-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="82b21-109">Planering av batchjobb misslyckas när planeringsoptimeringen aktiveras</span><span class="sxs-lookup"><span data-stu-id="82b21-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="82b21-110">När du aktiverar planeringsoptimering inaktiveras den inbyggda huvudplaneringsmotorn automatiskt.</span><span class="sxs-lookup"><span data-stu-id="82b21-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="82b21-111">Huvudplaneringsjobb i batch som har skapats för den inbyggda Supply Chain Management-motorn kommer att misslyckas om de utlöses medan planeringsoptimeringen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="82b21-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="82b21-112">Ett felmeddelande, till exempel *Denna åtgärd utlöste en huvudplanering som inte stöds när planeringsoptimering har aktiverats*, kan komma att visas.</span><span class="sxs-lookup"><span data-stu-id="82b21-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="82b21-113">**Korrigera**: Avbryt alla batchjobb för huvudplanering som har skapats för den inbyggda planeringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="82b21-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="82b21-114">Resultaten av planeringsoptimeringen skiljer sig från tidigare resultat</span><span class="sxs-lookup"><span data-stu-id="82b21-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="82b21-115">Planeringsoptimeringen skiljer sig från den inbyggda huvudplaneringsdesignen i vissa områden.</span><span class="sxs-lookup"><span data-stu-id="82b21-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="82b21-116">Detta kan också orsakas av väntande funktioner.</span><span class="sxs-lookup"><span data-stu-id="82b21-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="82b21-117">**Korrigera**: Kör anpassningsanalys av planeringsoptimeringen och analysera resultatet när du refererar till den tillhörande dokumentationen i syfte att förstå konsekvenserna.</span><span class="sxs-lookup"><span data-stu-id="82b21-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="82b21-118">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="82b21-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="82b21-119">Kan du inte aktivera planeringsoptimeringen?</span><span class="sxs-lookup"><span data-stu-id="82b21-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="82b21-120">**Anslutningsstatusen** måste vara **Ansluten** innan du kan ange **Använd planeringsoptimering** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="82b21-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="82b21-121">Mer information finns i [komma igång med planeringsoptimering](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="82b21-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="82b21-122">**Korrigera**: Kontrollera att tillägget för planeringsoptimering har installerats.</span><span class="sxs-lookup"><span data-stu-id="82b21-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="82b21-123">Felmeddelande visas under CTP</span><span class="sxs-lookup"><span data-stu-id="82b21-123">Error message is shown during CTP</span></span>

<span data-ttu-id="82b21-124">Om du försöker köra CTP ("capabel to promise") från en försäljningsorder när planeringsoptimering är aktiverad, visas följande felmeddelande: *Denna åtgärd utlöser huvudplanering som inte stöds när planeringsoptimering aktiveras*.</span><span class="sxs-lookup"><span data-stu-id="82b21-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="82b21-125">Detta är relaterat till en väntande funktion som planeras som en del av supporten för tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="82b21-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="82b21-126">**Korrigera;** Undvik CTP-beräkningar när planeringsoptimering är aktiverat tills CTP-stödet är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="82b21-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82b21-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="82b21-127">Additional resources</span></span>

[<span data-ttu-id="82b21-128">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="82b21-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="82b21-129">Bristanalys för planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="82b21-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]