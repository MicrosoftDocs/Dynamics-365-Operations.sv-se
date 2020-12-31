---
title: Startsida för mobilapp
description: Det här avsnittet beskriver mobilappen Finance and Operations (Dynamics 365) och ger länkar till resurser som kan hjälpa dig att implementera den i din organisation.
author: ChrisGarty
manager: AnnBe
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: e4a9d6424e2d214624c148c0565c88ea4cf4ccf9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683468"
---
# <a name="mobile-app-home-page"></a><span data-ttu-id="5555c-103">Startsida för mobilapp</span><span class="sxs-lookup"><span data-stu-id="5555c-103">Mobile app home page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5555c-104">Det här avsnittet beskriver mobilappen **Finance and Operations (Dynamics 365)** och ger länkar till resurser som kan hjälpa dig att implementera den i din organisation.</span><span class="sxs-lookup"><span data-stu-id="5555c-104">This topic describes the **Finance and Operations (Dynamics 365)** mobile app and provides links to resources that can help you implement it in your organization.</span></span>

<a name="overview"></a><span data-ttu-id="5555c-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5555c-105">Overview</span></span>
--------

<span data-ttu-id="5555c-106">Mobilappen låter din organisation sina dess affärsprocesser tillgängliga på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="5555c-106">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="5555c-107">När din IT-administratör aktiverar funktionen för mobila arbetsytor för organisationen, kan användare logga in på appen och omedelbart börja köra affärsprocesser från sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="5555c-107">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="5555c-108">Mobilappen innehåller följande funktioner som hjälper dig att öka produktiviteten:</span><span class="sxs-lookup"><span data-stu-id="5555c-108">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="5555c-109">Användare kan visa, redigera och arbeta med affärsdata, även om de har en opålitlig nätverksanslutning eller om deras mobila enheter är helt offline.</span><span class="sxs-lookup"><span data-stu-id="5555c-109">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="5555c-110">När en enhet återupprättar en nätverksanslutning, synkroniseras offline dataågärder automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5555c-110">When a device reestablishes a network connection, offline data operations are automatically synchronized.</span></span>
- <span data-ttu-id="5555c-111">IT-administratörer och utvecklare kan bygga och publicera mobila arbetsytor som har anpassats till organisationen.</span><span class="sxs-lookup"><span data-stu-id="5555c-111">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="5555c-112">Appen använder befintliga kodtillgångar.</span><span class="sxs-lookup"><span data-stu-id="5555c-112">The app uses your existing code assets.</span></span> <span data-ttu-id="5555c-113">Det innebär inte du inte behöver återimplementera dina valideringsförfaranden, affärslogik eller säkerhetskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="5555c-113">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="5555c-114">IT-administratörer och utvecklare kan enkelt utforma mobila arbetsytor genom att använda arbetsytedesignern med peka-och-klicka som ingår i webbklienten.</span><span class="sxs-lookup"><span data-stu-id="5555c-114">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="5555c-115">IT-administratörer och utvecklare kan även optimera arbetsytornas offlinekapacitet med hjälp av ramverket för Business logic utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="5555c-115">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="5555c-116">Eftersom data fortfarande bearbetas när en enhet är offline, förblir dina mobila scenarier omfattande eller flytande, även om enheterna inte har fasta nätverksanslutningar.</span><span class="sxs-lookup"><span data-stu-id="5555c-116">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="5555c-117">Delar av mobilappen</span><span class="sxs-lookup"><span data-stu-id="5555c-117">Elements of the mobile app</span></span>
<span data-ttu-id="5555c-118">Navigering i mobilappen består av fyra grundläggande begrepp: instrumentpanel, arbetsytor, sidor och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5555c-118">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="5555c-119">[![Navigeringsbegrepp i mobilappen](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="5555c-119">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="5555c-120">När du startar programmet kan du gå till **instrumentpanelen**.</span><span class="sxs-lookup"><span data-stu-id="5555c-120">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="5555c-121">På instrumentpanelen visas en lista över **arbetsytor** som har publicerats.</span><span class="sxs-lookup"><span data-stu-id="5555c-121">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="5555c-122">I varje arbetsyta visas en lista över **sidor** som är tillgängliga för arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="5555c-122">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="5555c-123">När du befinner dig på en sida kan du utföra flera åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5555c-123">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="5555c-124">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="5555c-124">Here are some examples:</span></span>

    - <span data-ttu-id="5555c-125">Visa detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="5555c-125">View detailed data.</span></span>
    - <span data-ttu-id="5555c-126">Navigera till andra sidor för relaterade data, till exempel enhetsinformation eller -rader.</span><span class="sxs-lookup"><span data-stu-id="5555c-126">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="5555c-127">Visa en lista över **åtgärder** som är tillgängliga för den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="5555c-127">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="5555c-128">Åtgärder låter dig skapa och redigera befintliga data.</span><span class="sxs-lookup"><span data-stu-id="5555c-128">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="5555c-129">Implementeringsprocess</span><span class="sxs-lookup"><span data-stu-id="5555c-129">Implementation process</span></span>
<span data-ttu-id="5555c-130">Följande illustration visar processen för implementering av såväl mobila arbetsytor som tillhandahålls av Microsoft, som anpassade mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="5555c-130">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

<span data-ttu-id="5555c-131">[![Implementeringsprocess för mobila program](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span><span class="sxs-lookup"><span data-stu-id="5555c-131">[![Mobile apps implementation process](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)</span></span>

<span data-ttu-id="5555c-132">Följande tabell innehåller länkar till resurser som hjälper dig att implementera såväl mobila arbetsytor som tillhandahålls av Microsoft, som anpassade mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="5555c-132">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="5555c-133">Siffrorna i den första kolumnen visar de numrerade stegen i illustrationen.</span><span class="sxs-lookup"><span data-stu-id="5555c-133">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5555c-134">Steg</span><span class="sxs-lookup"><span data-stu-id="5555c-134">Step</span></span></th>
<th><span data-ttu-id="5555c-135">Roll</span><span class="sxs-lookup"><span data-stu-id="5555c-135">Role</span></span></th>
<th><span data-ttu-id="5555c-136">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="5555c-136">Action</span></span></th>
<th><span data-ttu-id="5555c-137">Resurser som hjälper dig att slutföra åtgärden</span><span class="sxs-lookup"><span data-stu-id="5555c-137">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5555c-138">1</span><span class="sxs-lookup"><span data-stu-id="5555c-138">1</span></span></td>
<td><span data-ttu-id="5555c-139">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5555c-139">System administrator</span></span></td>
<td><span data-ttu-id="5555c-140">Implementera Finance and Operations-appen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="5555c-140">Implement the Finance and Operations app in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="5555c-141">Om du ännu inte har installerat en version av Microsoft Dynamics 365, se <a href="../deployment/deploy-demo-environment.md">Distribuera en demomiljö</a>.</span><span class="sxs-lookup"><span data-stu-id="5555c-141">If you haven&#39;t yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="5555c-142">En lista över de mobila arbetsytor som kan användas finns i <a href="mobile-workspaces-released.md">Mobila arbetsytor som nyligen lanserats</a>.</span><span class="sxs-lookup"><span data-stu-id="5555c-142">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5555c-143">2</span><span class="sxs-lookup"><span data-stu-id="5555c-143">2</span></span></td>
<td><span data-ttu-id="5555c-144">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5555c-144">System administrator</span></span></td>
<td><span data-ttu-id="5555c-145"><strong>Om du använder Microsoft Dynamics 365 for Operations version 1611:</strong>  Hämta och installera KBs som gör det möjligt för mobila arbetsytor som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5555c-145"><strong>If you&#39;re using Microsoft Dynamics 365 for Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="5555c-146">Se följande avsnitt för mer information:</span><span class="sxs-lookup"><span data-stu-id="5555c-146">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="5555c-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Mobil arbetsyta för kostnadskontroll</a></span><span class="sxs-lookup"><span data-stu-id="5555c-147"><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="5555c-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Mobil arbetsyta för inventering av lagerbehållning</a></span><span class="sxs-lookup"><span data-stu-id="5555c-148"><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="5555c-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Mobil arbetsyta för arbetsplatser</a></span><span class="sxs-lookup"><span data-stu-id="5555c-149"><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="5555c-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Mobil arbetsyta för leverantörssamarbete</a></span><span class="sxs-lookup"><span data-stu-id="5555c-150"><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="5555c-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Mobil arbetsyta för projekttidangivelse</a></span><span class="sxs-lookup"><span data-stu-id="5555c-151"><a href="../../../finance/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="5555c-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Mobil arbetsyta för utläggshantering</a></span><span class="sxs-lookup"><span data-stu-id="5555c-152"><a href="../../../finance/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5555c-153">3</span><span class="sxs-lookup"><span data-stu-id="5555c-153">3</span></span></td>
<td><span data-ttu-id="5555c-154">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5555c-154">System administrator</span></span></td>
<td><span data-ttu-id="5555c-155">Publicera mobila arbetsytor som tillhandahålls av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5555c-155">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="5555c-156"><a href="publish-mobile-workspace.md">Publicera mobil arbetsyta</a>
</span><span class="sxs-lookup"><span data-stu-id="5555c-156"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5555c-157">4</span><span class="sxs-lookup"><span data-stu-id="5555c-157">4</span></span></td>
<td><span data-ttu-id="5555c-158">Utvecklare eller oberoende programvaruleverantör (ISV)</span><span class="sxs-lookup"><span data-stu-id="5555c-158">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="5555c-159">Använd mobila plattformen om du vill skapa anpassade mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="5555c-159">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="5555c-160"><a href="platform/mobile-platform-home-page.md">Mobilplattform</a></span><span class="sxs-lookup"><span data-stu-id="5555c-160"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5555c-161">5</span><span class="sxs-lookup"><span data-stu-id="5555c-161">5</span></span></td>
<td><span data-ttu-id="5555c-162">ISV</span><span class="sxs-lookup"><span data-stu-id="5555c-162">ISV</span></span></td>
<td><span data-ttu-id="5555c-163">Skapa driftfärdiga paket som innehåller anpassade mobila arbetsytor och överför paketet till Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5555c-163">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="5555c-164"><a href="../deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket</a></span><span class="sxs-lookup"><span data-stu-id="5555c-164"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5555c-165">6</span><span class="sxs-lookup"><span data-stu-id="5555c-165">6</span></span></td>
<td><span data-ttu-id="5555c-166">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5555c-166">System administrator</span></span></td>
<td><span data-ttu-id="5555c-167">Tillämpa det driftfärdiga paketet som innehåller de anpassade arbetsytor som tillhandahålls av den oberoende programvaruleverantören (ISV).</span><span class="sxs-lookup"><span data-stu-id="5555c-167">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="5555c-168"><a href="../deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></span><span class="sxs-lookup"><span data-stu-id="5555c-168"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5555c-169">7</span><span class="sxs-lookup"><span data-stu-id="5555c-169">7</span></span></td>
<td><span data-ttu-id="5555c-170">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="5555c-170">System administrator</span></span></td>
<td><span data-ttu-id="5555c-171">Publicera anpassade mobila arbetsytor som tillhandahålls av ISV.</span><span class="sxs-lookup"><span data-stu-id="5555c-171">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="5555c-172"><a href="publish-mobile-workspace.md">Publicera en mobil arbetsyta</a></span><span class="sxs-lookup"><span data-stu-id="5555c-172"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5555c-173">8</span><span class="sxs-lookup"><span data-stu-id="5555c-173">8</span></span></td>
<td><span data-ttu-id="5555c-174">Användare</span><span class="sxs-lookup"><span data-stu-id="5555c-174">User</span></span></td>
<td><span data-ttu-id="5555c-175">Hämta och installera mobilappen.</span><span class="sxs-lookup"><span data-stu-id="5555c-175">Download and install the mobile app.</span></span></td>
<td><span data-ttu-id="5555c-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations-app för Android</a></span><span class="sxs-lookup"><span data-stu-id="5555c-176">
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Finance and Operations app for Android</a></span></span><BR/><span data-ttu-id="5555c-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations-app för iOS</a></span><span class="sxs-lookup"><span data-stu-id="5555c-177">
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Finance and Operations app for iOS</a></span></span><BR/>
<span data-ttu-id="5555c-178">(Windows Phone stöds inte)</span><span class="sxs-lookup"><span data-stu-id="5555c-178">(Windows Phone unsupported)</span></span>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5555c-179">9</span><span class="sxs-lookup"><span data-stu-id="5555c-179">9</span></span></td>
<td><span data-ttu-id="5555c-180">Användare</span><span class="sxs-lookup"><span data-stu-id="5555c-180">User</span></span></td>
<td><span data-ttu-id="5555c-181">Logga in och använd mobilappen.</span><span class="sxs-lookup"><span data-stu-id="5555c-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="5555c-182">Appen inkluderar de mobila arbetsytor som har publicerats av systemadministratören.</span><span class="sxs-lookup"><span data-stu-id="5555c-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="5555c-183">En lista över de mobila arbetsytor som tillhandahålls av Microsoft finns i <a href="mobile-workspaces-released.md">Mobila arbetsytor som nyligen lanserats</a>.</span><span class="sxs-lookup"><span data-stu-id="5555c-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a><span data-ttu-id="5555c-184">Felsökning</span><span class="sxs-lookup"><span data-stu-id="5555c-184">Troubleshooting</span></span>
[<span data-ttu-id="5555c-185">Mobila plattformsresurser</span><span class="sxs-lookup"><span data-stu-id="5555c-185">Mobile platform resources</span></span>](platform/mobile-platform-home-page.md#troubleshooting-the-app)
