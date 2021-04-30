---
title: Kom igång med planeringsoptimering
description: Det här avsnittet beskriver hur du använder funktionen planeringsoptimering.
author: ChristianRytt
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d346251e82737624edfce88dc7b2ee10280f6877
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907677"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="167e1-103">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="167e1-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="167e1-104">Som [tidigare presenterade](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios) planeringsoptimeringen till att ersätta den befintliga inbyggda huvudplaneringsmotorn.</span><span class="sxs-lookup"><span data-stu-id="167e1-104">As [previously announced](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="167e1-105">Om du använder den inbyggda huvudplaneringsmotorn för närvarande bör du börja planera migreringen för planeringsoptimering nu.</span><span class="sxs-lookup"><span data-stu-id="167e1-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="167e1-106">Det är viktigt att du startar flyttningen direkt eftersom dina åtgärder kan påverkas när utgångsmetoden är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="167e1-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="167e1-107">Vi rekommenderar starkt att du slutför migreringen före den 1 december 2020 för att undvika problem med sista minuten när utgången är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="167e1-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="167e1-108">Funktionen planeringsoptimering stöder för närvarande inte alla funktioner som är tillgängliga i den planeringsmotor som är inbyggd i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="167e1-109">Därför är det viktigt att du utvärderar om den tillgängliga funktionsuppsättningen i planeringsoptimering ska uppfylla dina krav.</span><span class="sxs-lookup"><span data-stu-id="167e1-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="167e1-110">Funktionen för planeringsoptimering är för närvarande inte aktive rad som standard i Dynamics Lifecycle Services (LCS), så du har möjlighet att utföra utvärderingen innan funktionen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="167e1-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="167e1-111">Du måste begära ett undantag från migrering till planeringsoptimering om huvudplaneringsprocessen inte innehåller någon produktion (huvudplanering genererade planerade produktionsorder) och du behöver den inbyggda huvudplaneringsmotorn utöver version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="167e1-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="167e1-112">Från och med version 10.0.16 visas ett felmeddelande i miljöer vid körning av inbyggd huvudplanering utan att planerade tillverkningsorder genereras.</span><span class="sxs-lookup"><span data-stu-id="167e1-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="167e1-113">Planeringsoptimering ska användas för alla nya distributioner som inte genererar planerade tillverkningsorder under huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="167e1-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="167e1-114">Ägare till befintliga miljöer som kör den inbyggda huvudplaneringsmotorn utan att generera planerade tillverkningsorder får ett e-postmeddelande med information om undantagsprocessen.</span><span class="sxs-lookup"><span data-stu-id="167e1-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="167e1-115">Vi rekommenderar att du arbetar med en partner för att utvärdera och planera migreringen till planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="167e1-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="167e1-116">Innan du aktiverar planeringsoptimeringen rekommenderar vi att du utvärderar resultatet av anpassningsanalysen för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="167e1-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="167e1-117">Mer information finns i [anpassningsanalys för planeringsoptimering](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="167e1-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="availability"></a><span data-ttu-id="167e1-118">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="167e1-118">Availability</span></span>

<span data-ttu-id="167e1-119">Planeringsoptimering är för närvarande tillgänglig i följande Azure-områden: USA, Kanada, Europa, Storbritannien, Australien och Asien och stillahavsområdet.</span><span class="sxs-lookup"><span data-stu-id="167e1-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, Australia, and Asia Pacific.</span></span> <span data-ttu-id="167e1-120">Om du försöker installera tillägget från ett annat geografiskt område visas ett meddelande om att detta geografiska område inte stöds.</span><span class="sxs-lookup"><span data-stu-id="167e1-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="167e1-121">Observera att planeringsoptimering inte har stöd för lokala distributioner av Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

## <a name="licensing"></a><span data-ttu-id="167e1-122">Licensiering</span><span class="sxs-lookup"><span data-stu-id="167e1-122">Licensing</span></span>

<span data-ttu-id="167e1-123">Om du kan köra huvudplanering med din nuvarande licens behöver du inte köpa ytterligare en licens för att börja använda planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="167e1-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

## <a name="install-and-enable-planning-optimization"></a><span data-ttu-id="167e1-124">Installera och aktivera planeringsoptimeringen</span><span class="sxs-lookup"><span data-stu-id="167e1-124">Install and enable Planning Optimization</span></span>

<span data-ttu-id="167e1-125">Om du vill använda Planeringsoptimering måste du kontrollera att alla förutsättningar finns i systemet och sedan aktivera licensnyckeln och installera tillägget Planeringsoptimering för Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-125">To use Planning Optimization, you must make sure your system has all of the prerequisites in place and then enable its license key and install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="167e1-126">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="167e1-126">Prerequisites</span></span>

<span data-ttu-id="167e1-127">Innan du installerar tillägget Planeringsoptimering måste följande förutsättningar finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="167e1-127">Before you install the Planning Optimization Add-in, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="167e1-128">Du måste köra Supply Chain Management på en LCS-aktiverad miljö med hög tillgänglighet, lägst nivå 2, (inte en OneBox-miljö) med Dynamics 365 Supply Chain Management version 10.0.7 eller senare.</span><span class="sxs-lookup"><span data-stu-id="167e1-128">You must be running Supply Chain Management on an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="167e1-129">Om du försöker installera tillägget i en OneBox-miljö kommer installationen inte att slutföras och du måste avbryta installationen.</span><span class="sxs-lookup"><span data-stu-id="167e1-129">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

- <span data-ttu-id="167e1-130">Ditt system måste ha ställts in för Power Platform-integration.</span><span class="sxs-lookup"><span data-stu-id="167e1-130">Your system must be set up for Power Platform integration.</span></span> <span data-ttu-id="167e1-131">Mer information finns i [Förutsättningar för att ställa in tillägg](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#prerequisites-for-setting-up-add-ins) och [Ställa in tillägg](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#set-up-add-ins).</span><span class="sxs-lookup"><span data-stu-id="167e1-131">For more information, see [Prerequisites for setting up add-ins](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#prerequisites-for-setting-up-add-ins) and [Set up add-ins](../../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md#set-up-add-ins).</span></span>

### <a name="enable-the-planning-optimization-license"></a><span data-ttu-id="167e1-132">Aktivera licensen för planeringsoptimeringen</span><span class="sxs-lookup"><span data-stu-id="167e1-132">Enable the Planning Optimization license</span></span>

<span data-ttu-id="167e1-133">Om du vill använda Planeringsoptimering måste du aktivera dess konfigurationsnyckel.</span><span class="sxs-lookup"><span data-stu-id="167e1-133">To use Planning Optimization, you must enable its configuration key.</span></span> <span data-ttu-id="167e1-134">Så här går det till:</span><span class="sxs-lookup"><span data-stu-id="167e1-134">To do so:</span></span>

1. <span data-ttu-id="167e1-135">Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="167e1-135">Put your system into maintenance mode, as described in [Maintenance mode](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="167e1-136">Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="167e1-136">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="167e1-137">På fliken **Konfigurationsnycklar** markera kryssrutan för **Planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="167e1-137">On the **Configuration keys** tab, select the check box for **Planning Optimization**.</span></span>
1. <span data-ttu-id="167e1-138">Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="167e1-138">Turn off maintenance mode, as described in [Maintenance mode](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

### <a name="install-the-planning-optimization-add-in"></a><span data-ttu-id="167e1-139">Installera tillägget Planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="167e1-139">Install the Planning Optimization Add-in</span></span>

<span data-ttu-id="167e1-140">Du måste installera tillägget från LCS-projektet och aktivera funktionen för planeringsoptimering från användargränssnittet för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-140">You must install the add-in from your LCS project and then turn on the Planning Optimization functionality from the Supply Chain Management user interface.</span></span>

<span data-ttu-id="167e1-141">För att installera tillägget Planeringsoptimering:</span><span class="sxs-lookup"><span data-stu-id="167e1-141">To install the Planning Optimization Add-in:</span></span>

1. <span data-ttu-id="167e1-142">Logga in på LCS och öppna den önskade miljön.</span><span class="sxs-lookup"><span data-stu-id="167e1-142">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="167e1-143">Gå till **Fullständiga detaljer**.</span><span class="sxs-lookup"><span data-stu-id="167e1-143">Go to **Full details**.</span></span>
1. <span data-ttu-id="167e1-144">Bläddra till snabbfliken **miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="167e1-144">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="167e1-145">Välj **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="167e1-145">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="167e1-146">Välj **Rådgivning om optimering**.</span><span class="sxs-lookup"><span data-stu-id="167e1-146">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="167e1-147">Följ installationsguiden och godkänn villkoren.</span><span class="sxs-lookup"><span data-stu-id="167e1-147">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="167e1-148">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="167e1-148">Select **Install**.</span></span>
1. <span data-ttu-id="167e1-149">På snabbfliken **miljötillägg** ser du till att planeringsoptimeringen installeras.</span><span class="sxs-lookup"><span data-stu-id="167e1-149">On the **Environment add-ins** FastTab, you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="167e1-150">När ett par minuter **installeras** bör du byta till **installerat** (du kan behöva uppdatera sidan).</span><span class="sxs-lookup"><span data-stu-id="167e1-150">After a few minutes, **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="167e1-151">När installationen är klar kan du aktivera planeringsoptimering i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-151">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="167e1-152">Det huvudsakliga syftet med tillägget att installera tilläggsprogrammet för planeringsoptimering är att ansluta tjänsten och miljön.</span><span class="sxs-lookup"><span data-stu-id="167e1-152">The main purpose of installing the Planning Optimization Add-in is to connect the service and the environment.</span></span> <span data-ttu-id="167e1-153">Därför måste du installera tillägget separat för varje miljö där du vill använda planeringsoptimering, oavsett vilken kod som flyttas mellan miljöerna.</span><span class="sxs-lookup"><span data-stu-id="167e1-153">Therefore, you must install the add-in separately on each environment where you will use Planning Optimization, regardless of any code moved between the environments.</span></span>

## <a name="integrate-planning-optimization-with-your-system"></a><span data-ttu-id="167e1-154">Integrera Planeringsoptimering med systemet</span><span class="sxs-lookup"><span data-stu-id="167e1-154">Integrate Planning Optimization with your system</span></span>

<span data-ttu-id="167e1-155">Om du vill konfigurera om tillägget för planeringsoptimering ska användas för huvudplanering går du till **Huvudplanering** \> **Inställningar** \> **Parametrar för planeringsoptimering**.</span><span class="sxs-lookup"><span data-stu-id="167e1-155">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

### <a name="connection-status"></a><span data-ttu-id="167e1-156">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="167e1-156">Connection status</span></span>

<span data-ttu-id="167e1-157">Anslutningsstatus anger aktuell status för anslutningen mellan hantering av Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="167e1-157">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="167e1-158">Följande tabell visar de möjliga värdena.</span><span class="sxs-lookup"><span data-stu-id="167e1-158">The following table shows the possible values.</span></span>

| <span data-ttu-id="167e1-159">Anslutningsstatus</span><span class="sxs-lookup"><span data-stu-id="167e1-159">Connection status</span></span> | <span data-ttu-id="167e1-160">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="167e1-160">Description</span></span> | <span data-ttu-id="167e1-161">Kan planeringsoptimering användas?</span><span class="sxs-lookup"><span data-stu-id="167e1-161">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="167e1-162">Ansluten</span><span class="sxs-lookup"><span data-stu-id="167e1-162">Connected</span></span> | <span data-ttu-id="167e1-163">En anslutning har upprättats mellan planeringsoptimeringstjänsten och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="167e1-163">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="167e1-164">Ja</span><span class="sxs-lookup"><span data-stu-id="167e1-164">Yes</span></span> |
| <span data-ttu-id="167e1-165">Aktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="167e1-165">Enabling connection</span></span> | <span data-ttu-id="167e1-166">En begäran om att aktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="167e1-166">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="167e1-167">Nej</span><span class="sxs-lookup"><span data-stu-id="167e1-167">No</span></span> |
| <span data-ttu-id="167e1-168">Frånkopplad</span><span class="sxs-lookup"><span data-stu-id="167e1-168">Disconnected</span></span> | <span data-ttu-id="167e1-169">Det finns ingen anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="167e1-169">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="167e1-170">Anslutningen kan aktiveras från LCS, vilket beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="167e1-170">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="167e1-171">Nej</span><span class="sxs-lookup"><span data-stu-id="167e1-171">No</span></span> |
| <span data-ttu-id="167e1-172">Inaktiverar anslutning</span><span class="sxs-lookup"><span data-stu-id="167e1-172">Disabling connection</span></span> | <span data-ttu-id="167e1-173">En begäran om att inaktivera anslutningen till planeringsoptimeringstjänsten pågår just nu.</span><span class="sxs-lookup"><span data-stu-id="167e1-173">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="167e1-174">Nej</span><span class="sxs-lookup"><span data-stu-id="167e1-174">No</span></span> |
| <span data-ttu-id="167e1-175">Hämtar status</span><span class="sxs-lookup"><span data-stu-id="167e1-175">Getting status</span></span> | <span data-ttu-id="167e1-176">Systemet väntar på statusinformation från planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="167e1-176">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="167e1-177">Nej</span><span class="sxs-lookup"><span data-stu-id="167e1-177">No</span></span> |

### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="167e1-178">Alternativet Använd planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="167e1-178">The Use Planning Optimization option</span></span>

<span data-ttu-id="167e1-179">Inställningen av alternativet **Använd planeringsoptimering** avgör vilken planeringsmotor som används för huvudplanering:</span><span class="sxs-lookup"><span data-stu-id="167e1-179">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="167e1-180">**Ja** – planeringsoptimering används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="167e1-180">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="167e1-181">**Nej** – den inbyggda planeringsmotorn för Supply Chain Management används för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="167e1-181">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="167e1-182">Om befintliga planeringsbatchjobb som har skapats för den inbyggda planeringsmotorn för Supply Chain Management utlöses medan alternativet **Använd planeringsoptimering** anges till **ja**, kommer dessa jobb att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="167e1-182">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="167e1-183">Integration med inställningen</span><span class="sxs-lookup"><span data-stu-id="167e1-183">Integration with the setup</span></span>

<span data-ttu-id="167e1-184">Om planeringsoptimeringen är aktiverad görs huvudplanering med tillägget planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="167e1-184">If the Planning Optimization is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="167e1-185">I det här fallet påverkas huvudplaneringens resultat och funktioner.</span><span class="sxs-lookup"><span data-stu-id="167e1-185">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="167e1-186">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="167e1-186">Additional resources</span></span>

[<span data-ttu-id="167e1-187">Villkor för förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="167e1-187">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="167e1-188">Planeringsoptimering – översikt</span><span class="sxs-lookup"><span data-stu-id="167e1-188">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="167e1-189">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="167e1-189">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="167e1-190">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="167e1-190">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="167e1-191">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="167e1-191">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="167e1-192">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="167e1-192">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]