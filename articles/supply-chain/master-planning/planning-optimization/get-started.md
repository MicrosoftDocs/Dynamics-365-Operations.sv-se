---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
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
ms.openlocfilehash: 49025d0aa0f6a627b816a43dd4260449942b400c
ms.sourcegitcommit: ae04c7cb48f7ecafe71bbe77a0f97715e6290991
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973486"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="970b0-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="970b0-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="970b0-104">Som [tidigare presenterade](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios) planeringsoptimeringen till att ersätta den befintliga inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="970b0-104">As [previously announced](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="970b0-105">Om du använder den inbyggda huvudplaneringsmotorn för närvarande bör du börja planera migreringen för planeringsoptimering nu.</span><span class="sxs-lookup"><span data-stu-id="970b0-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="970b0-106">Det är viktigt att du startar flyttningen direkt eftersom dina åtgärder kan påverkas när utgångsmetoden är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="970b0-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="970b0-107">Vi rekommenderar starkt att du slutför migreringen före den 1 december 2020 för att undvika problem med sista minuten när utgången är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="970b0-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="970b0-108">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="970b0-109">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="970b0-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="970b0-110">Funktionen för planeringsoptimering är för närvarande inte aktive rad som standard i Dynamics Lifecycle Services (LCS), så du har möjlighet att utföra utvärderingen innan funktionen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="970b0-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="970b0-111">Du måste begära ett undantag från migrering till planeringsoptimering om huvudplaneringsprocessen inte innehåller någon produktion (huvudplanering genererade planerade produktionsorder) och du behöver den inbyggda huvudplaneringsmotorn utöver version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="970b0-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="970b0-112">Från och med version 10.0.16 visas ett felmeddelande i miljöer vid körning av inbyggd huvudplanering utan att planerade tillverkningsorder genereras.</span><span class="sxs-lookup"><span data-stu-id="970b0-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="970b0-113">Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="970b0-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="970b0-114">Ägare till befintliga miljöer som kör den inbyggda huvudplaneringsmotorn utan att generera planerade tillverkningsorder får ett e-postmeddelande med information om undantagsprocessen.</span><span class="sxs-lookup"><span data-stu-id="970b0-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="970b0-115">Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="970b0-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="970b0-116">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="970b0-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="970b0-117">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="970b0-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="970b0-118">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="970b0-118">Availability</span></span>
<span data-ttu-id="970b0-119">Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien och Australien.</span><span class="sxs-lookup"><span data-stu-id="970b0-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="970b0-120">Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds.</span><span class="sxs-lookup"><span data-stu-id="970b0-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="970b0-121">Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="970b0-122">Licensiering</span><span class="sxs-lookup"><span data-stu-id="970b0-122">Licensing</span></span>

<span data-ttu-id="970b0-123">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="970b0-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="970b0-124">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="970b0-124">Install the add-in</span></span>

<span data-ttu-id="970b0-125">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-125">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="970b0-126">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-126">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="970b0-127">Kravet på planeringsoptimering är en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="970b0-127">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="970b0-128">Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.</span><span class="sxs-lookup"><span data-stu-id="970b0-128">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="970b0-129">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="970b0-129">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="970b0-130">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="970b0-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="970b0-131">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="970b0-131">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="970b0-132">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="970b0-132">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="970b0-133">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="970b0-133">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="970b0-134">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="970b0-134">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="970b0-135">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="970b0-135">Select **Install**.</span></span>
1. <span data-ttu-id="970b0-136">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="970b0-136">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="970b0-137">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="970b0-137">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="970b0-138">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-138">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="970b0-139">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="970b0-139">Planning Optimization integration</span></span>

<span data-ttu-id="970b0-140">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="970b0-140">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="970b0-141">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="970b0-141">Connection status</span></span>

<span data-ttu-id="970b0-142">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="970b0-142">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="970b0-143">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="970b0-143">The following table shows the possible values.</span></span>

| <span data-ttu-id="970b0-144">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="970b0-144">Connection status</span></span> | <span data-ttu-id="970b0-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="970b0-145">Description</span></span> | <span data-ttu-id="970b0-146">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="970b0-146">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="970b0-147">Ansluten</span><span class="sxs-lookup"><span data-stu-id="970b0-147">Connected</span></span> | <span data-ttu-id="970b0-148">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="970b0-148">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="970b0-149">Ja</span><span class="sxs-lookup"><span data-stu-id="970b0-149">Yes</span></span> |
| <span data-ttu-id="970b0-150">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="970b0-150">Enabling connection</span></span> | <span data-ttu-id="970b0-151">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="970b0-151">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="970b0-152">Nej</span><span class="sxs-lookup"><span data-stu-id="970b0-152">No</span></span> |
| <span data-ttu-id="970b0-153">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="970b0-153">Disconnected</span></span> | <span data-ttu-id="970b0-154">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="970b0-154">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="970b0-155">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="970b0-155">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="970b0-156">Nej</span><span class="sxs-lookup"><span data-stu-id="970b0-156">No</span></span> |
| <span data-ttu-id="970b0-157">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="970b0-157">Disabling connection</span></span> | <span data-ttu-id="970b0-158">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="970b0-158">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="970b0-159">Nej</span><span class="sxs-lookup"><span data-stu-id="970b0-159">No</span></span> |
| <span data-ttu-id="970b0-160">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="970b0-160">Getting status</span></span> | <span data-ttu-id="970b0-161">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="970b0-161">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="970b0-162">Nej</span><span class="sxs-lookup"><span data-stu-id="970b0-162">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="970b0-163">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="970b0-163">The Use Planning Optimization option</span></span>

<span data-ttu-id="970b0-164">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="970b0-164">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="970b0-165">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="970b0-165">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="970b0-166">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="970b0-166">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="970b0-167">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="970b0-167">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="970b0-168">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="970b0-168">Integration with the setup</span></span>

<span data-ttu-id="970b0-169">Om förhandsgranskningen av planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="970b0-169">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="970b0-170">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="970b0-170">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="970b0-171">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="970b0-171">Additional resources</span></span>

[<span data-ttu-id="970b0-172">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="970b0-172">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="970b0-173">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="970b0-173">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="970b0-174">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="970b0-174">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="970b0-175">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="970b0-175">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="970b0-176">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="970b0-176">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="970b0-177">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="970b0-177">Cancel a planning job</span></span>](cancel-planning-job.md)
