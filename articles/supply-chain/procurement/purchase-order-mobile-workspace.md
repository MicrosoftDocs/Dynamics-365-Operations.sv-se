---
title: "Mobil arbetsyta för inköpsordergodkännande"
description: "Det här avsnittet innehåller information om den mobila arbetsytan Godkännande av inköpsorder där du kan visa inköpsorder och reagera på dem genom att utföra åtgärder. Du kan exempelvis godkänna eller avvisa en inköpsorder."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 60744c2b90e64ac77155ba28cdc4fcf65fee1bb6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="d0f22-104">Mobil arbetsyta för inköpsordergodkännande</span><span class="sxs-lookup"><span data-stu-id="d0f22-104">Purchase order approval mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

<span data-ttu-id="d0f22-105">Detta avsnitt innehåller information om den mobila arbetsytan **Godkännande av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="d0f22-106">På den här arbetsytan kan du visa inköpsorder och reagera på dem genom att utföra åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="d0f22-107">Du kan exempelvis godkänna eller avvisa en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="d0f22-108">Översikt</span><span class="sxs-lookup"><span data-stu-id="d0f22-108">Overview</span></span> 
<span data-ttu-id="d0f22-109">Inköpsorder som kräver godkännande genomgår en arbetsflöde för godkännande.</span><span class="sxs-lookup"><span data-stu-id="d0f22-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="d0f22-110">Arbetsflödet kan innehålla olika steg som kräver att en eller fler personer utför åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="d0f22-111">Exempelvis kanske en person behöva slutföra en aktivitet eller godkänna inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="d0f22-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="d0f22-112">Med hjälp av den mobila arbetsytan **Godkännande av inköpsorder** kan du lätt visa och svara på inköpsorder från din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="d0f22-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="d0f22-113">På den här arbetsytan kan du utföra samma arbetsflödesåtgärder som du kan utföra från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, web client.</span><span class="sxs-lookup"><span data-stu-id="d0f22-113">This workspace also lets you take the same workflow actions that you can take from the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0f22-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d0f22-114">Prerequisites</span></span>
<span data-ttu-id="d0f22-115">Förutsättningarna varierar beroende på vilken version av Finance and Operations som har distribuerats inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="d0f22-115">The prerequisites vary, depending on the version of Finance and Operations that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="d0f22-116">Förutsättningar om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017)</span><span class="sxs-lookup"><span data-stu-id="d0f22-116">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span> 
<span data-ttu-id="d0f22-117">Om Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) har implementerats för din organisation, måste systemadministratören publicera den mobila arbetsytan **Godkännande av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-117">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="d0f22-118">Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="d0f22-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="d0f22-119">Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare</span><span class="sxs-lookup"><span data-stu-id="d0f22-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="d0f22-120">Om Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav.</span><span class="sxs-lookup"><span data-stu-id="d0f22-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d0f22-121">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="d0f22-121">Prerequisite</span></span></th>
<th><span data-ttu-id="d0f22-122">Roll</span><span class="sxs-lookup"><span data-stu-id="d0f22-122">Role</span></span></th>
<th><span data-ttu-id="d0f22-123">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0f22-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d0f22-124">Implementera KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="d0f22-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="d0f22-125">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="d0f22-125">System administrator</span></span></td>
<td><span data-ttu-id="d0f22-126">KB 4017918 är en X++-uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>.</span><span class="sxs-lookup"><span data-stu-id="d0f22-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="d0f22-127">Om du vill implementera KB 4017918 måste systemadministratören göra följande.</span><span class="sxs-lookup"><span data-stu-id="d0f22-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="d0f22-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="d0f22-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="d0f22-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</span><span class="sxs-lookup"><span data-stu-id="d0f22-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="d0f22-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket </a> som innehåller modellerna <strong>SCMMobile</strong> och modellen och överför sedan det driftfärdiga paketet till LCS. </span><span class="sxs-lookup"><span data-stu-id="d0f22-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="d0f22-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></span><span class="sxs-lookup"><span data-stu-id="d0f22-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d0f22-132">Publicera den mobila arbetsytan <strong>Godkännande av inköpsorder</strong>.</span><span class="sxs-lookup"><span data-stu-id="d0f22-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="d0f22-133">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="d0f22-133">System administrator</span></span></td>
<td><span data-ttu-id="d0f22-134">Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</span><span class="sxs-lookup"><span data-stu-id="d0f22-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d0f22-135">Hämta och installera mobilappen</span><span class="sxs-lookup"><span data-stu-id="d0f22-135">Download and install the mobile app</span></span>
<span data-ttu-id="d0f22-136">Hämta och installera mobilappen Microsoft Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="d0f22-136">Download and install the Microsoft Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="d0f22-137">För Android-telefoner</span><span class="sxs-lookup"><span data-stu-id="d0f22-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="d0f22-138">För iPhones</span><span class="sxs-lookup"><span data-stu-id="d0f22-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d0f22-139">Logga in på mobilappen</span><span class="sxs-lookup"><span data-stu-id="d0f22-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="d0f22-140">Starta appen i din mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="d0f22-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="d0f22-141">Ange din webbadress för Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d0f22-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="d0f22-142">Första gången du loggar in uppmanas du ange användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="d0f22-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d0f22-143">Ange dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d0f22-143">Enter your credentials.</span></span>
4. <span data-ttu-id="d0f22-144">När du loggar in visas tillgängliga arbetsytor för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="d0f22-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d0f22-145">Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.</span><span class="sxs-lookup"><span data-stu-id="d0f22-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Arbetsytan Godkännande av inköpsorder i listan över tillgängliga arbetsytor](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="d0f22-147">Visa order som har tilldelats dig</span><span class="sxs-lookup"><span data-stu-id="d0f22-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="d0f22-148">På din mobila enhet väljer du arbetsytan **Godkännande av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="d0f22-149">Välj **Order tilldelad till mig** om du vill visa alla inköpsorder som du har blivit ombedd att vidta åtgärder för i arbetsflödet Godkännande av inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="d0f22-150">Välj en order.</span><span class="sxs-lookup"><span data-stu-id="d0f22-150">Select an order.</span></span> <span data-ttu-id="d0f22-151">På sidan **Orderinformation** visas informationen i orderrubriken och raderna.</span><span class="sxs-lookup"><span data-stu-id="d0f22-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="d0f22-152">Du kan också finna riktlinjer för arbetsflödesuppgiften.</span><span class="sxs-lookup"><span data-stu-id="d0f22-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="d0f22-153">Välj **Redovisningsfördelningar** för att öppna sidan **Redovisningsfördelning, huvud**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="d0f22-154">Gå tillbaka till sidan **Orderinformation** och markera en rad.</span><span class="sxs-lookup"><span data-stu-id="d0f22-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="d0f22-155">Du kan även utforska radspecifika redovisningsfördelningar från raden Orderinformation.</span><span class="sxs-lookup"><span data-stu-id="d0f22-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="d0f22-156">Utföra en åtgärd på inköpsordern</span><span class="sxs-lookup"><span data-stu-id="d0f22-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="d0f22-157">När du har visat den inköpsorder som har tilldelats dig och läst instruktionerna om arbetsflödet bör du vara redo att vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="d0f22-158">På din mobila enhet väljer du arbetsytan **Godkännande av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="d0f22-159">Välj **Order tilldelad till mig** om du vill visa alla inköpsorder som du har blivit ombedd att vidta åtgärder för i arbetsflödet Godkännande av inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="d0f22-160">Markera en order och visa informationssidan.</span><span class="sxs-lookup"><span data-stu-id="d0f22-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="d0f22-161">Välj **Åtgärder** om du vill visa tillgängliga åtgärder.</span><span class="sxs-lookup"><span data-stu-id="d0f22-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="d0f22-162">Vilka åtgärder som är tillgängliga beror på vilken uppgift som har tilldelats dig.</span><span class="sxs-lookup"><span data-stu-id="d0f22-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="d0f22-163">Aktivitetsåtgärd</span><span class="sxs-lookup"><span data-stu-id="d0f22-163">Task action</span></span>    | <span data-ttu-id="d0f22-164">Godkännandeåtgärd</span><span class="sxs-lookup"><span data-stu-id="d0f22-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="d0f22-165">Komplett</span><span class="sxs-lookup"><span data-stu-id="d0f22-165">Complete</span></span>       | <span data-ttu-id="d0f22-166">Godkänn</span><span class="sxs-lookup"><span data-stu-id="d0f22-166">Approve</span></span>          |
    | <span data-ttu-id="d0f22-167">Retur</span><span class="sxs-lookup"><span data-stu-id="d0f22-167">Return</span></span>         | <span data-ttu-id="d0f22-168">Avvisa</span><span class="sxs-lookup"><span data-stu-id="d0f22-168">Reject</span></span>           |
    | <span data-ttu-id="d0f22-169">Begär ändring</span><span class="sxs-lookup"><span data-stu-id="d0f22-169">Request change</span></span> | <span data-ttu-id="d0f22-170">Begär ändring</span><span class="sxs-lookup"><span data-stu-id="d0f22-170">Request change</span></span>   |
    | <span data-ttu-id="d0f22-171">Delegera</span><span class="sxs-lookup"><span data-stu-id="d0f22-171">Delegate</span></span>       | <span data-ttu-id="d0f22-172">Delegera</span><span class="sxs-lookup"><span data-stu-id="d0f22-172">Delegate</span></span>         |

5. <span data-ttu-id="d0f22-173">Välj lämplig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="d0f22-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="d0f22-174">Skriv en kommentar på sidan **Slutför uppgift**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="d0f22-175">Observera att om du väljer åtgärden **Delegera** måste du välja den användare du vill delegera uppgiften till.</span><span class="sxs-lookup"><span data-stu-id="d0f22-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="d0f22-176">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="d0f22-176">Select **Done**.</span></span> <span data-ttu-id="d0f22-177">När du uppdaterar din arbetsyta kommer inköpsordern inte längre att finnas i listan.</span><span class="sxs-lookup"><span data-stu-id="d0f22-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 

