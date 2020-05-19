---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
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
ms.openlocfilehash: ce1bbb18e9a448e84d001a4195421d2b0e4af5be
ms.sourcegitcommit: c0d37fdd70f3dec4605fdee6f981f84a49be9b9e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "3339888"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="d6ae8-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="d6ae8-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6ae8-104">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d6ae8-105">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="d6ae8-106">Som standard är funktionen planeringsoptimering inte aktiverad i Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="d6ae8-107">Därför har du möjlighet att utföra utvärderingen innan den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="d6ae8-108">Planeringsoptimering kommer till slut att ersätta befintliga inbyggda planeringsmotorn för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="d6ae8-109">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="d6ae8-110">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="d6ae8-111">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="d6ae8-111">Availability</span></span>
<span data-ttu-id="d6ae8-112">Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien och Australien.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="d6ae8-113">Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="d6ae8-114">Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="d6ae8-115">Licensiering</span><span class="sxs-lookup"><span data-stu-id="d6ae8-115">Licensing</span></span>

<span data-ttu-id="d6ae8-116">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="d6ae8-117">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="d6ae8-117">Install the add-in</span></span>

<span data-ttu-id="d6ae8-118">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d6ae8-119">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="d6ae8-120">Kravet på planeringsoptimering är en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="d6ae8-121">Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="d6ae8-122">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="d6ae8-123">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="d6ae8-124">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="d6ae8-125">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="d6ae8-126">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="d6ae8-127">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="d6ae8-128">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-128">Select **Install**.</span></span>
1. <span data-ttu-id="d6ae8-129">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="d6ae8-130">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="d6ae8-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="d6ae8-131">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="d6ae8-132">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="d6ae8-132">Planning Optimization integration</span></span>

<span data-ttu-id="d6ae8-133">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="d6ae8-134">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="d6ae8-134">Connection status</span></span>

<span data-ttu-id="d6ae8-135">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="d6ae8-136">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="d6ae8-137">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="d6ae8-137">Connection status</span></span> | <span data-ttu-id="d6ae8-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d6ae8-138">Description</span></span> | <span data-ttu-id="d6ae8-139">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="d6ae8-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="d6ae8-140">Ansluten</span><span class="sxs-lookup"><span data-stu-id="d6ae8-140">Connected</span></span> | <span data-ttu-id="d6ae8-141">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="d6ae8-142">Ja</span><span class="sxs-lookup"><span data-stu-id="d6ae8-142">Yes</span></span> |
| <span data-ttu-id="d6ae8-143">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="d6ae8-143">Enabling connection</span></span> | <span data-ttu-id="d6ae8-144">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d6ae8-145">Nej</span><span class="sxs-lookup"><span data-stu-id="d6ae8-145">No</span></span> |
| <span data-ttu-id="d6ae8-146">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="d6ae8-146">Disconnected</span></span> | <span data-ttu-id="d6ae8-147">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="d6ae8-148">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="d6ae8-149">Nej</span><span class="sxs-lookup"><span data-stu-id="d6ae8-149">No</span></span> |
| <span data-ttu-id="d6ae8-150">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="d6ae8-150">Disabling connection</span></span> | <span data-ttu-id="d6ae8-151">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d6ae8-152">Nej</span><span class="sxs-lookup"><span data-stu-id="d6ae8-152">No</span></span> |
| <span data-ttu-id="d6ae8-153">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="d6ae8-153">Getting status</span></span> | <span data-ttu-id="d6ae8-154">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="d6ae8-155">Nej</span><span class="sxs-lookup"><span data-stu-id="d6ae8-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="d6ae8-156">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="d6ae8-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="d6ae8-157">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="d6ae8-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="d6ae8-158">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="d6ae8-159">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="d6ae8-160">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="d6ae8-161">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="d6ae8-161">Integration with the setup</span></span>

<span data-ttu-id="d6ae8-162">Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="d6ae8-163">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="d6ae8-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6ae8-164">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d6ae8-164">Additional resources</span></span>

[<span data-ttu-id="d6ae8-165">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="d6ae8-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="d6ae8-166">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="d6ae8-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="d6ae8-167">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="d6ae8-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="d6ae8-168">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="d6ae8-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="d6ae8-169">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="d6ae8-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="d6ae8-170">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="d6ae8-170">Cancel a planning job</span></span>](cancel-planning-job.md)
