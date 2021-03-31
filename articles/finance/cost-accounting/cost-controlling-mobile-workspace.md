---
title: Mobil arbetsyta för kostnadskontroll
description: Det här avsnittet innehåller information om Mobil arbetsyta för kostnadskontroll. Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f75a868acd8ae7e77c7080e2afe81788490bcccb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226423"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="81c81-104">Mobil arbetsyta för kostnadskontroll</span><span class="sxs-lookup"><span data-stu-id="81c81-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81c81-105">Det här avsnittet innehåller information om den mobila arbetsytan **kostnadskontroll**.</span><span class="sxs-lookup"><span data-stu-id="81c81-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="81c81-106">Den här arbetsytan låter chefer för kostnadsställen visa information om kostnadsställets effektivitet när som helst och var som helst.</span><span class="sxs-lookup"><span data-stu-id="81c81-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="81c81-107">Denna mobila arbetsyta är avsedd att användas med mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="81c81-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="81c81-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="81c81-108">Overview</span></span>
<span data-ttu-id="81c81-109">Mobil arbetsyta för **Kostnadskontroll** ger en omedelbar översikt över aktuell prestanda för kostnadsställen genom att jämföra faktiska kostnader mot budgeterade kostnader.</span><span class="sxs-lookup"><span data-stu-id="81c81-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="81c81-110">Du kan gå ända ner till statusen för enskilda kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="81c81-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="81c81-111">Till exempel en medarbetare får en inbjudan till en internationell konferens, men organisationen måste stå för alla resekostnader.</span><span class="sxs-lookup"><span data-stu-id="81c81-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="81c81-112">Medarbetaren frågar sin chef om hon kan delta i konferensen.</span><span class="sxs-lookup"><span data-stu-id="81c81-112">The employee asks their manager whether they can attend the conference.</span></span> <span data-ttu-id="81c81-113">Chefen öppnar den mobila arbetsytan för **Kostnadskontroll** i sin mobila enhet för att se om budgeten tillåter att medarbetaren deltar i konferensen.</span><span class="sxs-lookup"><span data-stu-id="81c81-113">The manager opens the **Cost controlling** mobile workspace on their mobile device to see whether there is budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="81c81-114">Datasäkerhet</span><span class="sxs-lookup"><span data-stu-id="81c81-114">Data security</span></span>
<span data-ttu-id="81c81-115">Datan i den mobila arbetsytan för **kostnadskontroll** skyddas av användarens autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81c81-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="81c81-116">Chefer för ett kostnadsställe får endast se data för eget kostnadsställe.</span><span class="sxs-lookup"><span data-stu-id="81c81-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="81c81-117">Säkerheten för åtkomstnivå hanteras inom modulen **kostnadsredovisning**.</span><span class="sxs-lookup"><span data-stu-id="81c81-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="81c81-118">Kostnadsrevisorerna definierar konfigurationen för den mobila arbetsytan för **kostnadskontroll** i modulen **kostnadsredovisning**.</span><span class="sxs-lookup"><span data-stu-id="81c81-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="81c81-119">När arbetsytan publiceras i mobilappen, blir den tillgänglig i appen.</span><span class="sxs-lookup"><span data-stu-id="81c81-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="81c81-120">Detta säkerställer att alla chefer för kostnadsställen i organisationen ser data i samma format.</span><span class="sxs-lookup"><span data-stu-id="81c81-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="81c81-121">Åtgärder, vyer och länkar</span><span class="sxs-lookup"><span data-stu-id="81c81-121">Actions, views, and links</span></span>
<span data-ttu-id="81c81-122">Den mobila arbetsytan **kostnadskontroll** innehåller följande åtgärder, vyer och länkar:</span><span class="sxs-lookup"><span data-stu-id="81c81-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="81c81-123">**Åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="81c81-123">**Actions:**</span></span>

    -   <span data-ttu-id="81c81-124">Använd **Välj konfiguration** för att välja en layout.</span><span class="sxs-lookup"><span data-stu-id="81c81-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="81c81-125">Använd **Välj kostnadsobjekt** för att välja kostnadsobjekt att filtrera data på.</span><span class="sxs-lookup"><span data-stu-id="81c81-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="81c81-126">Kostnadsställen som finns med i listan beror på den åtkomst som beviljas i modulen **kostnadsredovisning**.</span><span class="sxs-lookup"><span data-stu-id="81c81-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="81c81-127">**Vyer:** Baserat på de åtgärder som väljs och konfigurationen i modulen **Kostnadsredovisning** kan du visa följande information på korten.</span><span class="sxs-lookup"><span data-stu-id="81c81-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="81c81-128">Utfall kontra budget (aktuell period)</span><span class="sxs-lookup"><span data-stu-id="81c81-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="81c81-129">Utfall kontra reviderad budget (aktuell period)</span><span class="sxs-lookup"><span data-stu-id="81c81-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="81c81-130">Utfall kontra Budget (föregående period)</span><span class="sxs-lookup"><span data-stu-id="81c81-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="81c81-131">Utfall kontra reviderad budget (föregående period)</span><span class="sxs-lookup"><span data-stu-id="81c81-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="81c81-132">Utfall kontra budget (hittills i år)</span><span class="sxs-lookup"><span data-stu-id="81c81-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="81c81-133">Utfall kontra reviderad budget (hittills i år)</span><span class="sxs-lookup"><span data-stu-id="81c81-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="81c81-134">Följande belopp på varje kort: Utfall, Budget, Avvikelse och Avvikelse i %.</span><span class="sxs-lookup"><span data-stu-id="81c81-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="81c81-135">**Länkar:**</span><span class="sxs-lookup"><span data-stu-id="81c81-135">**Links:**</span></span>

    -   <span data-ttu-id="81c81-136">Information om aktuell period.</span><span class="sxs-lookup"><span data-stu-id="81c81-136">Details for current period</span></span>
    -   <span data-ttu-id="81c81-137">Information om föregående period.</span><span class="sxs-lookup"><span data-stu-id="81c81-137">Details for previous period</span></span>
    -   <span data-ttu-id="81c81-138">Information om hittillsvarande år.</span><span class="sxs-lookup"><span data-stu-id="81c81-138">Details for year to date</span></span>

    <span data-ttu-id="81c81-139">När du väljer en länk visas ett kort för varje kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="81c81-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="81c81-140">Följande belopp visas på varje kort: Utfall, Budget, Budgetavvikelse, Budgetavvikelseprocent, Reviderad budget, Reviderad budgetavvikelse samt Reviderad budgetavvikelseprocent.</span><span class="sxs-lookup"><span data-stu-id="81c81-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="81c81-141">[![Kort för ett kostnadselement ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="81c81-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81c81-142">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="81c81-142">Prerequisites</span></span>
<span data-ttu-id="81c81-143">Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81c81-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a><span data-ttu-id="81c81-144">Förutsättningar om du använder Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="81c81-144">Prerequisites if you use Microsoft Dynamics 365 Finance</span></span>
<span data-ttu-id="81c81-145">Om Finance används inom din organisation måste systemadministratören publicera den mobila arbetsytan **Kostnadskontroll**.</span><span class="sxs-lookup"><span data-stu-id="81c81-145">If Finance has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="81c81-146">Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="81c81-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="81c81-147">Förutsättningar om du använder version 1611 med plattformsuppdateringen 3 eller senare</span><span class="sxs-lookup"><span data-stu-id="81c81-147">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="81c81-148">Om version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav.</span><span class="sxs-lookup"><span data-stu-id="81c81-148">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="81c81-149">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="81c81-149">Prerequisite</span></span></th>
<th><span data-ttu-id="81c81-150">Roll</span><span class="sxs-lookup"><span data-stu-id="81c81-150">Role</span></span></th>
<th><span data-ttu-id="81c81-151">beskrivning</span><span class="sxs-lookup"><span data-stu-id="81c81-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="81c81-152">Implementera KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="81c81-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="81c81-153">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="81c81-153">System administrator</span></span></td>

<td><span data-ttu-id="81c81-154">KB 4013633 är en X++ -uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>kostnadskontroll</strong>.</span><span class="sxs-lookup"><span data-stu-id="81c81-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="81c81-155">Om du vill implementera KB 4013633 måste systemadministratören göra följande.</span><span class="sxs-lookup"><span data-stu-id="81c81-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="81c81-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigeringar för metadata från Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="81c81-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="81c81-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</span><span class="sxs-lookup"><span data-stu-id="81c81-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="81c81-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </span><span class="sxs-lookup"><span data-stu-id="81c81-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="81c81-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></span><span class="sxs-lookup"><span data-stu-id="81c81-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="81c81-160">Publicera den mobila arbetsytan <strong>kostnaskontroll</strong>.</span><span class="sxs-lookup"><span data-stu-id="81c81-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="81c81-161">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="81c81-161">System administrator</span></span></td>
<td><span data-ttu-id="81c81-162">Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="81c81-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="81c81-163">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="81c81-163">Download and install the mobile app</span></span>
<span data-ttu-id="81c81-164">Hämta och installera mobilappen Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="81c81-164">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="81c81-165">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="81c81-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="81c81-166">För iPhones</span><span class="sxs-lookup"><span data-stu-id="81c81-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="81c81-167">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="81c81-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="81c81-168">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="81c81-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="81c81-169">Ange din webbadress för Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="81c81-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="81c81-170">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="81c81-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="81c81-171">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81c81-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="81c81-172">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="81c81-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="81c81-173">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="81c81-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="81c81-174">[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="81c81-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="81c81-175">Visa prestanda för ditt kostnadsställe med hjälp av den mobila arbetsytan för kostnadskontroll</span><span class="sxs-lookup"><span data-stu-id="81c81-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="81c81-176">På din mobila enhet väljer du arbetsytan **Kostnadsstyrning**.</span><span class="sxs-lookup"><span data-stu-id="81c81-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="81c81-177">Välj **Styrning av kostnadsobjekt**.</span><span class="sxs-lookup"><span data-stu-id="81c81-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="81c81-178">Välj **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="81c81-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="81c81-179">Välj **Välj konfiguration** för att välja en layout för kostnadsstyrning.</span><span class="sxs-lookup"><span data-stu-id="81c81-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="81c81-180">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="81c81-180">Select **Done**.</span></span>
6.  <span data-ttu-id="81c81-181">Välj **Åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="81c81-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="81c81-182">Välj **Välj kostnadsobjekt** för att välja de kostnadsställen för vilka du har beviljats åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="81c81-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="81c81-183">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="81c81-183">Select **Done**.</span></span>
9.  <span data-ttu-id="81c81-184">Visa total prestanda för ditt kostnadsställe.</span><span class="sxs-lookup"><span data-stu-id="81c81-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="81c81-185">Välj länken **detaljer för aktuell period**.</span><span class="sxs-lookup"><span data-stu-id="81c81-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="81c81-186">Visa prestandan för enskilda kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="81c81-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="81c81-187">Du kan också söka efter specifika kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="81c81-187">You can also search for specific cost elements.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]