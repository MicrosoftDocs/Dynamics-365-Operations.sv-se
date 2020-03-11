---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: AnnBe
ms.date: 02/10/2020
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
ms.openlocfilehash: 3e64699005387adcc92e2e7c9fefad68a9de85c0
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076142"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="56978-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="56978-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="56978-104">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="56978-105">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="56978-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="56978-106">Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="56978-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="56978-107">Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="56978-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="56978-108">Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="56978-109">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56978-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="56978-110">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="56978-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="56978-111">Licensiering</span><span class="sxs-lookup"><span data-stu-id="56978-111">Licensing</span></span>

<span data-ttu-id="56978-112">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56978-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="56978-113">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="56978-113">Install the add-in</span></span>

<span data-ttu-id="56978-114">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="56978-115">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="56978-116">Kravet på planeringsoptimering är en LCS-aktiverad miljö med hög tillgänglighet (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="56978-116">The requirement for Planning Optimization is an LCS enabled high-availability environment (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span>

1. <span data-ttu-id="56978-117">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="56978-117">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="56978-118">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="56978-118">Go to **Full details**.</span></span>
1. <span data-ttu-id="56978-119">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="56978-119">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="56978-120">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="56978-120">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="56978-121">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="56978-121">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="56978-122">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="56978-122">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="56978-123">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="56978-123">Select **Install**.</span></span>
1. <span data-ttu-id="56978-124">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="56978-124">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="56978-125">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="56978-125">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="56978-126">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-126">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="56978-127">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="56978-127">Planning Optimization integration</span></span>

<span data-ttu-id="56978-128">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="56978-128">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="56978-129">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="56978-129">Connection status</span></span>

<span data-ttu-id="56978-130">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="56978-130">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="56978-131">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="56978-131">The following table shows the possible values.</span></span>

| <span data-ttu-id="56978-132">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="56978-132">Connection status</span></span> | <span data-ttu-id="56978-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="56978-133">Description</span></span> | <span data-ttu-id="56978-134">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="56978-134">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="56978-135">Ansluten</span><span class="sxs-lookup"><span data-stu-id="56978-135">Connected</span></span> | <span data-ttu-id="56978-136">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="56978-136">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="56978-137">Ja</span><span class="sxs-lookup"><span data-stu-id="56978-137">Yes</span></span> |
| <span data-ttu-id="56978-138">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="56978-138">Enabling connection</span></span> | <span data-ttu-id="56978-139">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="56978-139">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="56978-140">Nej</span><span class="sxs-lookup"><span data-stu-id="56978-140">No</span></span> |
| <span data-ttu-id="56978-141">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="56978-141">Disconnected</span></span> | <span data-ttu-id="56978-142">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="56978-142">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="56978-143">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="56978-143">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="56978-144">Nej</span><span class="sxs-lookup"><span data-stu-id="56978-144">No</span></span> |
| <span data-ttu-id="56978-145">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="56978-145">Disabling connection</span></span> | <span data-ttu-id="56978-146">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="56978-146">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="56978-147">Nej</span><span class="sxs-lookup"><span data-stu-id="56978-147">No</span></span> |
| <span data-ttu-id="56978-148">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="56978-148">Getting status</span></span> | <span data-ttu-id="56978-149">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="56978-149">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="56978-150">Nej</span><span class="sxs-lookup"><span data-stu-id="56978-150">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="56978-151">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="56978-151">The Use Planning Optimization option</span></span>

<span data-ttu-id="56978-152">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="56978-152">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="56978-153">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="56978-153">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="56978-154">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="56978-154">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="56978-155">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="56978-155">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="56978-156">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="56978-156">Integration with the setup</span></span>

<span data-ttu-id="56978-157">Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="56978-157">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="56978-158">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="56978-158">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="56978-159">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="56978-159">Related resources</span></span>

[<span data-ttu-id="56978-160">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="56978-160">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="56978-161">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="56978-161">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="56978-162">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="56978-162">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="56978-163">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="56978-163">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="56978-164">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="56978-164">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="56978-165">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="56978-165">Cancel a planning job</span></span>](cancel-planning-job.md)
