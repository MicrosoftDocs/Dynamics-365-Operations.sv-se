---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
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
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774051"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="a15e8-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="a15e8-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="a15e8-104">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a15e8-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a15e8-105">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="a15e8-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="a15e8-106">Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a15e8-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="a15e8-107">Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a15e8-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="a15e8-108">Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a15e8-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="a15e8-109">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="a15e8-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="a15e8-110">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a15e8-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="a15e8-111">Licensiering</span><span class="sxs-lookup"><span data-stu-id="a15e8-111">Licensing</span></span>

<span data-ttu-id="a15e8-112">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="a15e8-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="a15e8-113">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="a15e8-113">Install the add-in</span></span>

<span data-ttu-id="a15e8-114">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a15e8-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="a15e8-115">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a15e8-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="a15e8-116">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="a15e8-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="a15e8-117">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="a15e8-118">Välj **underhåll** eller rulla ned till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-118">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="a15e8-119">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="a15e8-120">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="a15e8-121">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="a15e8-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="a15e8-122">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-122">Select **Install**.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="a15e8-123">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="a15e8-123">Planning Optimization integration</span></span>

<span data-ttu-id="a15e8-124">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Integrering av planeringsoptimering** \> **Integreringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="a15e8-124">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization integration** \> **Integration parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="a15e8-125">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="a15e8-125">Connection status</span></span>

<span data-ttu-id="a15e8-126">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="a15e8-126">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="a15e8-127">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="a15e8-127">The following table shows the possible values.</span></span>

| <span data-ttu-id="a15e8-128">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="a15e8-128">Connection status</span></span> | <span data-ttu-id="a15e8-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a15e8-129">Description</span></span> | <span data-ttu-id="a15e8-130">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="a15e8-130">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="a15e8-131">Ansluten</span><span class="sxs-lookup"><span data-stu-id="a15e8-131">Connected</span></span> | <span data-ttu-id="a15e8-132">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a15e8-132">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="a15e8-133">Ja</span><span class="sxs-lookup"><span data-stu-id="a15e8-133">Yes</span></span> |
| <span data-ttu-id="a15e8-134">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="a15e8-134">Enabling connection</span></span> | <span data-ttu-id="a15e8-135">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="a15e8-135">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="a15e8-136">Nej</span><span class="sxs-lookup"><span data-stu-id="a15e8-136">No</span></span> |
| <span data-ttu-id="a15e8-137">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="a15e8-137">Disconnected</span></span> | <span data-ttu-id="a15e8-138">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="a15e8-138">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="a15e8-139">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a15e8-139">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="a15e8-140">Nej</span><span class="sxs-lookup"><span data-stu-id="a15e8-140">No</span></span> |
| <span data-ttu-id="a15e8-141">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="a15e8-141">Disabling connection</span></span> | <span data-ttu-id="a15e8-142">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="a15e8-142">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="a15e8-143">Nej</span><span class="sxs-lookup"><span data-stu-id="a15e8-143">No</span></span> |
| <span data-ttu-id="a15e8-144">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="a15e8-144">Getting status</span></span> | <span data-ttu-id="a15e8-145">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="a15e8-145">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="a15e8-146">Nej</span><span class="sxs-lookup"><span data-stu-id="a15e8-146">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="a15e8-147">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="a15e8-147">The Use Planning Optimization option</span></span>

<span data-ttu-id="a15e8-148">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="a15e8-148">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="a15e8-149">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="a15e8-149">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="a15e8-150">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="a15e8-150">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="a15e8-151">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="a15e8-151">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="a15e8-152">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="a15e8-152">Integration with the setup</span></span>

<span data-ttu-id="a15e8-153">Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="a15e8-153">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="a15e8-154">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="a15e8-154">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="a15e8-155">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="a15e8-155">Related resources</span></span>

[<span data-ttu-id="a15e8-156">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="a15e8-156">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="a15e8-157">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="a15e8-157">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="a15e8-158">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="a15e8-158">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="a15e8-159">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="a15e8-159">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="a15e8-160">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="a15e8-160">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="a15e8-161">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="a15e8-161">Cancel a planning job</span></span>](cancel-planning-job.md)
