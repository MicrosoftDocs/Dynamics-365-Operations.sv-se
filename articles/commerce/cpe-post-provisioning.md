---
title: Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce
description: Detta ämne förklarar hur du konfigurerar förhandsversionsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ad05996eaabd3965308370649a27b8bc3080c7ce
ms.sourcegitcommit: f72e90dccc80718e99cab2752eaf8931dcbb915e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "3534077"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="ae3c1-103">Konfigurera en förhandsversionsmiljö för Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae3c1-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ae3c1-104">Detta ämne förklarar hur du konfigurerar förhandsversionsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="ae3c1-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ae3c1-105">Overview</span></span>

<span data-ttu-id="ae3c1-106">Slutför procedurerna i det här avsnittet först när förhandsversionsmiljö för Commerce har etablerats.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="ae3c1-107">Information om hur du konfigurerar etablerar förhandsversionsmiljö för Commerce, se [Etablera en förhandsversionsmiljö för Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="ae3c1-108">När din förhandsversionsmiljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="ae3c1-109">Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="ae3c1-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="ae3c1-110">Before you start</span></span>

1. <span data-ttu-id="ae3c1-111">Logga in på [LCS-portal](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="ae3c1-112">Gå till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-112">Go to your project.</span></span>
1. <span data-ttu-id="ae3c1-113">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="ae3c1-114">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="ae3c1-115">Välj i miljöinformation till höger **Fullständig information**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="ae3c1-116">Välj **Logga in** för att öppna en meny och välj sedan **Logga in på miljön**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="ae3c1-117">Kontrollera att **USRT** juridisk person har valts i övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="ae3c1-118">Konfigurera kassan i LCS</span><span class="sxs-lookup"><span data-stu-id="ae3c1-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="ae3c1-119">Associera arbetare med din identitet</span><span class="sxs-lookup"><span data-stu-id="ae3c1-119">Associate a worker with your identity</span></span>

<span data-ttu-id="ae3c1-120">Om du vill associera en anställd med din identitet i LCS, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="ae3c1-121">Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> arbetare**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="ae3c1-122">Hitta och markera följande post: **000713 - Andrew Collette** i listan.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="ae3c1-123">Klicka på **butik** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="ae3c1-124">Välj **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="ae3c1-125">I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="ae3c1-126">Välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-126">Select **Search**.</span></span>
1. <span data-ttu-id="ae3c1-127">Markera posten med ditt namn.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="ae3c1-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-128">Select **OK**.</span></span>
1. <span data-ttu-id="ae3c1-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="ae3c1-130">Aktivera molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="ae3c1-130">Activate Cloud POS</span></span>

<span data-ttu-id="ae3c1-131">Om du vill aktivera Cloud POS i LCS, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="ae3c1-132">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="ae3c1-133">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="ae3c1-134">Välj i miljöinformation till höger **Fullständig information**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="ae3c1-135">Välj **logga in** för att öppna en meny och välj sedan **Logga in på Cloud Point of Sale** för att öppna kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="ae3c1-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-136">Select **Next**.</span></span>
1. <span data-ttu-id="ae3c1-137">Logga in med ditt Microsoft Azure Active Directory (Azure AD)-konto.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="ae3c1-138">Under **Butiksnamn**, välj **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="ae3c1-139">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-139">Select **Next**.</span></span>
1. <span data-ttu-id="ae3c1-140">Under **Register och enhet**, välj **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="ae3c1-141">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-141">Select **Activate**.</span></span> <span data-ttu-id="ae3c1-142">Du är utloggad och tagen till kassainloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="ae3c1-143">Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="ae3c1-144">Ställ in din webbplats i Commerce</span><span class="sxs-lookup"><span data-stu-id="ae3c1-144">Set up your site in Commerce</span></span>

<span data-ttu-id="ae3c1-145">Följ dessa steg om du vill börja konfigurera din förhandsgranskningswebbplats i Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ae3c1-146">Logga in på platshanteringsverktyget med hjälp av den URL som du antecknade när du initierade e-handel under etableringen (se [initiera e-handel](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="ae3c1-147">Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="ae3c1-148">Välj den domän som du angav när du initierade e-handel.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="ae3c1-149">Som standardkanal väljer du **Fabrikam utökade online-butik**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="ae3c1-150">(Se till att välja den **utökade** onlinebutiken)</span><span class="sxs-lookup"><span data-stu-id="ae3c1-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="ae3c1-151">För standardspråk väljer du **sv-SE**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="ae3c1-152">Lämna värdet i fältet **sökväg** som det är.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="ae3c1-153">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-153">Select **OK**.</span></span> <span data-ttu-id="ae3c1-154">Listan över sidor på webbplatsen visas.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="ae3c1-155">Aktivera jobb</span><span class="sxs-lookup"><span data-stu-id="ae3c1-155">Enable jobs</span></span>

<span data-ttu-id="ae3c1-156">Gör så här om du vill aktivera jobb i Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ae3c1-157">Logga in på miljön (HQ).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="ae3c1-158">Gå till menyn till vänster **Retail och Commerce \> Förfrågningar och rapporter \> Batch-jobb**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="ae3c1-159">De återstående stegen i den här proceduren måste slutföras för vart och ett av följande jobb:</span><span class="sxs-lookup"><span data-stu-id="ae3c1-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="ae3c1-160">Bearbeta butikorders e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="ae3c1-160">Process retail order email notification</span></span>
    * <span data-ttu-id="ae3c1-161">Produkttillgänglighet</span><span class="sxs-lookup"><span data-stu-id="ae3c1-161">Product availability</span></span>
    * <span data-ttu-id="ae3c1-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="ae3c1-162">P-0001</span></span>
    * <span data-ttu-id="ae3c1-163">Synkronisera orderjobb</span><span class="sxs-lookup"><span data-stu-id="ae3c1-163">Synchronize orders job</span></span>

1. <span data-ttu-id="ae3c1-164">Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="ae3c1-165">Utför följande steg om status för jobbet är **Undanhåll**:</span><span class="sxs-lookup"><span data-stu-id="ae3c1-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="ae3c1-166">Välj posten.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-166">Select the record.</span></span>
    1. <span data-ttu-id="ae3c1-167">I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="ae3c1-168">Välj **Väntar**och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="ae3c1-169">Kör fullständig datasynkronisering</span><span class="sxs-lookup"><span data-stu-id="ae3c1-169">Run full data synchronization</span></span>

<span data-ttu-id="ae3c1-170">Om du vill köra fullständig datasynkronisering i Commerce, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-170">To run full data synchronization in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="ae3c1-171">Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-171">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="ae3c1-172">**Standard** kanalen väljs i listan till vänster.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="ae3c1-173">Välj den andra tillgängliga kanalen.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-173">Select the other available channel.</span></span> <span data-ttu-id="ae3c1-174">Den här kanalen heter **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="ae3c1-175">I åtgärdsfönstret, välj **Fullständig datasynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="ae3c1-176">Ange **9999** som distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="ae3c1-177">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-177">Select **OK**.</span></span>
1. <span data-ttu-id="ae3c1-178">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="ae3c1-179">Testa kreditkortsinformation för att utföra testinköp</span><span class="sxs-lookup"><span data-stu-id="ae3c1-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="ae3c1-180">För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:</span><span class="sxs-lookup"><span data-stu-id="ae3c1-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="ae3c1-181">**Kortnummer:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="ae3c1-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="ae3c1-182">**Utgångsdatum:** 10/20</span><span class="sxs-lookup"><span data-stu-id="ae3c1-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="ae3c1-183">**Kortverifieringsnummer (CVV) kod:** 737</span><span class="sxs-lookup"><span data-stu-id="ae3c1-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae3c1-184">Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae3c1-185">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ae3c1-185">Next steps</span></span>

<span data-ttu-id="ae3c1-186">När etablerings- och konfigurationsstegen är slutförda är du redo att utvärdera din förhandsversionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="ae3c1-187">Använd URL:en för hanteringsverktyg för näthandelsplats för att gå till redigeringsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="ae3c1-188">Använd URL:en för hanteringsverktyg för näthandelsplats för att gå till näthandelsplats för butikskunden.</span><span class="sxs-lookup"><span data-stu-id="ae3c1-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="ae3c1-189">För att konfigurera valfria funktioner för Commerce efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för förhandsversionsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="ae3c1-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae3c1-190">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ae3c1-190">Additional resources</span></span>

[<span data-ttu-id="ae3c1-191">Dynamics 365 Commerce förhandsversionsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="ae3c1-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="ae3c1-192">Etablera en Dynamics 365 Commerce förhandsversionsmiljö</span><span class="sxs-lookup"><span data-stu-id="ae3c1-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="ae3c1-193">Konfigurera valfria funktioner för en förhandsversionsmiljö för Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ae3c1-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="ae3c1-194">Vanliga frågor om Dynamics 365 Commerce förhandsversionsmiljö</span><span class="sxs-lookup"><span data-stu-id="ae3c1-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="ae3c1-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="ae3c1-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="ae3c1-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="ae3c1-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="ae3c1-197">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="ae3c1-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="ae3c1-198">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="ae3c1-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
