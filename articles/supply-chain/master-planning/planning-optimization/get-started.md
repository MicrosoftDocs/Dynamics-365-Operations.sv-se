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
ms.openlocfilehash: 54ad180b7f4691ead3563b077eadadc3b9b20588
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438114"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="fafaf-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="fafaf-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fafaf-104">Som [tidigare presenterade](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios) planeringsoptimeringen till att ersätta den befintliga inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="fafaf-104">As [previously announced](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="fafaf-105">Om du använder den inbyggda huvudplaneringsmotorn för närvarande bör du börja planera migreringen för planeringsoptimering nu.</span><span class="sxs-lookup"><span data-stu-id="fafaf-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="fafaf-106">Det är viktigt att du startar flyttningen direkt eftersom dina åtgärder kan påverkas när utgångsmetoden är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="fafaf-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="fafaf-107">Vi rekommenderar starkt att du slutför migreringen före den 1 december 2020 för att undvika problem med sista minuten när utgången är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="fafaf-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="fafaf-108">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="fafaf-109">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="fafaf-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="fafaf-110">Funktionen för planeringsoptimering är för närvarande inte aktive rad som standard i Dynamics Lifecycle Services (LCS), så du har möjlighet att utföra utvärderingen innan funktionen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="fafaf-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="fafaf-111">Du måste begära ett undantag från migrering till planeringsoptimering om huvudplaneringsprocessen inte innehåller någon produktion (huvudplanering genererade planerade produktionsorder) och du behöver den inbyggda huvudplaneringsmotorn utöver version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="fafaf-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="fafaf-112">Från och med version 10.0.16 visas ett felmeddelande i miljöer vid körning av inbyggd huvudplanering utan att planerade tillverkningsorder genereras.</span><span class="sxs-lookup"><span data-stu-id="fafaf-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="fafaf-113">Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="fafaf-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="fafaf-114">Ägare till befintliga miljöer som kör den inbyggda huvudplaneringsmotorn utan att generera planerade tillverkningsorder får ett e-postmeddelande med information om undantagsprocessen.</span><span class="sxs-lookup"><span data-stu-id="fafaf-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="fafaf-115">Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="fafaf-116">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="fafaf-117">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="fafaf-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="fafaf-118">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="fafaf-118">Availability</span></span>
<span data-ttu-id="fafaf-119">Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien och Australien.</span><span class="sxs-lookup"><span data-stu-id="fafaf-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="fafaf-120">Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds.</span><span class="sxs-lookup"><span data-stu-id="fafaf-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="fafaf-121">Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="fafaf-122">Licensiering</span><span class="sxs-lookup"><span data-stu-id="fafaf-122">Licensing</span></span>

<span data-ttu-id="fafaf-123">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="fafaf-124">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="fafaf-124">Install the add-in</span></span>

<span data-ttu-id="fafaf-125">Om du vill använda planeringsoptimering installerar du tillägget för planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-125">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="fafaf-126">Du kan komma åt tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-126">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="fafaf-127">Kravet på planeringsoptimering är en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="fafaf-127">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="fafaf-128">Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.</span><span class="sxs-lookup"><span data-stu-id="fafaf-128">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="fafaf-129">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="fafaf-129">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="fafaf-130">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="fafaf-131">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-131">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="fafaf-132">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-132">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="fafaf-133">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-133">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="fafaf-134">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="fafaf-134">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="fafaf-135">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-135">Select **Install**.</span></span>
1. <span data-ttu-id="fafaf-136">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="fafaf-136">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="fafaf-137">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="fafaf-137">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="fafaf-138">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-138">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="fafaf-139">Det huvudsakliga syftet med tillägget att installera tilläggsprogrammet för planeringsoptimering är att ansluta tjänsten och miljön.</span><span class="sxs-lookup"><span data-stu-id="fafaf-139">The main purpose of installing the Planning Optimization add-in is to connect the service and the environment.</span></span> <span data-ttu-id="fafaf-140">Därför måste du installera tillägget separat för varje miljö där du vill använda planeringsoptimering, oavsett vilken kod som flyttas mellan miljöerna.</span><span class="sxs-lookup"><span data-stu-id="fafaf-140">Therefore, you must install the add-in separately on each environment where you will use Planning Optimization, regardless of any code moved between the environments.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="fafaf-141">Planera optimeringsintegration</span><span class="sxs-lookup"><span data-stu-id="fafaf-141">Planning Optimization integration</span></span>

<span data-ttu-id="fafaf-142">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="fafaf-142">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="fafaf-143">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="fafaf-143">Connection status</span></span>

<span data-ttu-id="fafaf-144">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="fafaf-144">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="fafaf-145">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="fafaf-145">The following table shows the possible values.</span></span>

| <span data-ttu-id="fafaf-146">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="fafaf-146">Connection status</span></span> | <span data-ttu-id="fafaf-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fafaf-147">Description</span></span> | <span data-ttu-id="fafaf-148">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="fafaf-148">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="fafaf-149">Ansluten</span><span class="sxs-lookup"><span data-stu-id="fafaf-149">Connected</span></span> | <span data-ttu-id="fafaf-150">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fafaf-150">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="fafaf-151">Ja</span><span class="sxs-lookup"><span data-stu-id="fafaf-151">Yes</span></span> |
| <span data-ttu-id="fafaf-152">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="fafaf-152">Enabling connection</span></span> | <span data-ttu-id="fafaf-153">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="fafaf-153">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="fafaf-154">Nej</span><span class="sxs-lookup"><span data-stu-id="fafaf-154">No</span></span> |
| <span data-ttu-id="fafaf-155">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="fafaf-155">Disconnected</span></span> | <span data-ttu-id="fafaf-156">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="fafaf-156">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="fafaf-157">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fafaf-157">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="fafaf-158">Nej</span><span class="sxs-lookup"><span data-stu-id="fafaf-158">No</span></span> |
| <span data-ttu-id="fafaf-159">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="fafaf-159">Disabling connection</span></span> | <span data-ttu-id="fafaf-160">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="fafaf-160">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="fafaf-161">Nej</span><span class="sxs-lookup"><span data-stu-id="fafaf-161">No</span></span> |
| <span data-ttu-id="fafaf-162">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="fafaf-162">Getting status</span></span> | <span data-ttu-id="fafaf-163">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="fafaf-163">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="fafaf-164">Nej</span><span class="sxs-lookup"><span data-stu-id="fafaf-164">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="fafaf-165">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="fafaf-165">The Use Planning Optimization option</span></span>

<span data-ttu-id="fafaf-166">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="fafaf-166">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="fafaf-167">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-167">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="fafaf-168">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-168">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="fafaf-169">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="fafaf-169">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="fafaf-170">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="fafaf-170">Integration with the setup</span></span>

<span data-ttu-id="fafaf-171">Om planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="fafaf-171">If the Planning Optimization is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="fafaf-172">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="fafaf-172">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fafaf-173">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fafaf-173">Additional resources</span></span>

[<span data-ttu-id="fafaf-174">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="fafaf-174">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="fafaf-175">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="fafaf-175">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="fafaf-176">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="fafaf-176">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="fafaf-177">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="fafaf-177">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="fafaf-178">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="fafaf-178">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="fafaf-179">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="fafaf-179">Cancel a planning job</span></span>](cancel-planning-job.md)
