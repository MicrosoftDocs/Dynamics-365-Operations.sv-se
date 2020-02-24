---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 01/17/2020
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
ms.openlocfilehash: 3e0371c6addc0412dc2fc105891b012941e92a06
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971474"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="0d30b-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="0d30b-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="0d30b-104">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0d30b-105">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="0d30b-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="0d30b-106">Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0d30b-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="0d30b-107">Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="0d30b-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="0d30b-108">Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="0d30b-109">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="0d30b-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="0d30b-110">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="0d30b-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="0d30b-111">Licensiering</span><span class="sxs-lookup"><span data-stu-id="0d30b-111">Licensing</span></span>

<span data-ttu-id="0d30b-112">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="0d30b-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="0d30b-113">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="0d30b-113">Install the add-in</span></span>

<span data-ttu-id="0d30b-114">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0d30b-115">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="0d30b-116">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="0d30b-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="0d30b-117">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="0d30b-118">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-118">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="0d30b-119">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="0d30b-120">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="0d30b-121">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="0d30b-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="0d30b-122">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-122">Select **Install**.</span></span>
1. <span data-ttu-id="0d30b-123">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="0d30b-123">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="0d30b-124">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="0d30b-124">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="0d30b-125">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-125">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="0d30b-126">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="0d30b-126">Planning Optimization integration</span></span>

<span data-ttu-id="0d30b-127">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="0d30b-127">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="0d30b-128">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="0d30b-128">Connection status</span></span>

<span data-ttu-id="0d30b-129">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="0d30b-129">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="0d30b-130">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="0d30b-130">The following table shows the possible values.</span></span>

| <span data-ttu-id="0d30b-131">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="0d30b-131">Connection status</span></span> | <span data-ttu-id="0d30b-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0d30b-132">Description</span></span> | <span data-ttu-id="0d30b-133">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="0d30b-133">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="0d30b-134">Ansluten</span><span class="sxs-lookup"><span data-stu-id="0d30b-134">Connected</span></span> | <span data-ttu-id="0d30b-135">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d30b-135">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="0d30b-136">Ja</span><span class="sxs-lookup"><span data-stu-id="0d30b-136">Yes</span></span> |
| <span data-ttu-id="0d30b-137">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="0d30b-137">Enabling connection</span></span> | <span data-ttu-id="0d30b-138">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="0d30b-138">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="0d30b-139">Nej</span><span class="sxs-lookup"><span data-stu-id="0d30b-139">No</span></span> |
| <span data-ttu-id="0d30b-140">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="0d30b-140">Disconnected</span></span> | <span data-ttu-id="0d30b-141">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="0d30b-141">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="0d30b-142">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="0d30b-142">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="0d30b-143">Nej</span><span class="sxs-lookup"><span data-stu-id="0d30b-143">No</span></span> |
| <span data-ttu-id="0d30b-144">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="0d30b-144">Disabling connection</span></span> | <span data-ttu-id="0d30b-145">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="0d30b-145">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="0d30b-146">Nej</span><span class="sxs-lookup"><span data-stu-id="0d30b-146">No</span></span> |
| <span data-ttu-id="0d30b-147">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="0d30b-147">Getting status</span></span> | <span data-ttu-id="0d30b-148">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="0d30b-148">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="0d30b-149">Nej</span><span class="sxs-lookup"><span data-stu-id="0d30b-149">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="0d30b-150">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="0d30b-150">The Use Planning Optimization option</span></span>

<span data-ttu-id="0d30b-151">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="0d30b-151">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="0d30b-152">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="0d30b-152">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="0d30b-153">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="0d30b-153">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="0d30b-154">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="0d30b-154">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="0d30b-155">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="0d30b-155">Integration with the setup</span></span>

<span data-ttu-id="0d30b-156">Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="0d30b-156">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="0d30b-157">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="0d30b-157">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="0d30b-158">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="0d30b-158">Related resources</span></span>

[<span data-ttu-id="0d30b-159">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="0d30b-159">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="0d30b-160">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="0d30b-160">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="0d30b-161">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="0d30b-161">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="0d30b-162">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="0d30b-162">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="0d30b-163">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="0d30b-163">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="0d30b-164">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="0d30b-164">Cancel a planning job</span></span>](cancel-planning-job.md)
