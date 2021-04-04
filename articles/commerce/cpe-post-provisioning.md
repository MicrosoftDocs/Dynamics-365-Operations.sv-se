---
title: Konfigurera en Dynamics 365 Commerce utvärderingsmiljö
description: Detta ämne förklarar hur du konfigurerar bedömningsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9b11ab600bb2aa17cf330947304f5b22dd522081
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477983"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="b000d-103">Konfigurera en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="b000d-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b000d-104">Detta ämne förklarar hur du konfigurerar bedömningsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.</span><span class="sxs-lookup"><span data-stu-id="b000d-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="b000d-105">Slutför procedurerna i det här avsnittet först när bedömningsmiljö för Commerce har etablerats.</span><span class="sxs-lookup"><span data-stu-id="b000d-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="b000d-106">Information om hur du konfigurerar etablerar bedömningsmiljö för Commerce, se [Etablera en bedömningsmiljö för Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="b000d-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="b000d-107">När din bedömningsmiljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön.</span><span class="sxs-lookup"><span data-stu-id="b000d-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="b000d-108">Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b000d-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b000d-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b000d-109">Before you start</span></span>

1. <span data-ttu-id="b000d-110">Logga in på [LCS-portal](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="b000d-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="b000d-111">Gå till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="b000d-111">Go to your project.</span></span>
1. <span data-ttu-id="b000d-112">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="b000d-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="b000d-113">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="b000d-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="b000d-114">Välj i miljöinformation till höger **Logga in i miljön**.</span><span class="sxs-lookup"><span data-stu-id="b000d-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="b000d-115">Du kommer att skickas till Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="b000d-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="b000d-116">Kontrollera att **USRT** juridisk person har valts i övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="b000d-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="b000d-117">Under åtgärderna efter etablering i Commerce-administration, se till att den juridiska personen **USRT** alltid är vald.</span><span class="sxs-lookup"><span data-stu-id="b000d-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="b000d-118">Konfigurera POS</span><span class="sxs-lookup"><span data-stu-id="b000d-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="b000d-119">Associera arbetare med din identitet</span><span class="sxs-lookup"><span data-stu-id="b000d-119">Associate a worker with your identity</span></span>

<span data-ttu-id="b000d-120">Om du vill associera en anställd med din identitet, följ dessa steg i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="b000d-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="b000d-121">Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> arbetare**.</span><span class="sxs-lookup"><span data-stu-id="b000d-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="b000d-122">Hitta och markera följande post: **000713 – Andrew Collette** i listan.</span><span class="sxs-lookup"><span data-stu-id="b000d-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="b000d-123">I åtgärdsfönstret, välj **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="b000d-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="b000d-124">Välj **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="b000d-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="b000d-125">I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="b000d-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="b000d-126">Välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="b000d-126">Select **Search**.</span></span>
1. <span data-ttu-id="b000d-127">Markera posten med ditt namn.</span><span class="sxs-lookup"><span data-stu-id="b000d-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="b000d-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000d-128">Select **OK**.</span></span>
1. <span data-ttu-id="b000d-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b000d-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="b000d-130">Aktivera molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="b000d-130">Activate Cloud POS</span></span>

<span data-ttu-id="b000d-131">Om du vill aktivera Cloud POS i LCS, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b000d-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="b000d-132">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="b000d-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="b000d-133">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="b000d-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="b000d-134">Välj i miljöinformation till höger **Logga in i molnbaserad kassa**.</span><span class="sxs-lookup"><span data-stu-id="b000d-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="b000d-135">Välj **Nästa** om du vill öppna dialogrutan **innan du startar**.</span><span class="sxs-lookup"><span data-stu-id="b000d-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="b000d-136">Lämna fältet **Server URL** tomt.</span><span class="sxs-lookup"><span data-stu-id="b000d-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="b000d-137">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b000d-137">Select **Next**.</span></span>
1. <span data-ttu-id="b000d-138">Logga in med ditt Microsoft Azure Active Directory (Azure AD)-konto.</span><span class="sxs-lookup"><span data-stu-id="b000d-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="b000d-139">Under **Butiksnamn**, välj **San Francisco** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b000d-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="b000d-140">Under **Register och enhet**, välj **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="b000d-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="b000d-141">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="b000d-141">Select **Activate**.</span></span> <span data-ttu-id="b000d-142">Du är utloggad och tagen till kassainloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="b000d-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="b000d-143">Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.</span><span class="sxs-lookup"><span data-stu-id="b000d-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="b000d-144">Ställ in din webbplats i Commerce</span><span class="sxs-lookup"><span data-stu-id="b000d-144">Set up your site in Commerce</span></span>

<span data-ttu-id="b000d-145">Följ dessa steg om du vill börja konfigurera din bedömningswebbplats i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b000d-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b000d-146">Logga in på webbplatsskaparen med hjälp av den URL som du antecknade när du initierade näthandel under etableringen (se [initiera näthandel](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="b000d-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="b000d-147">Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.</span><span class="sxs-lookup"><span data-stu-id="b000d-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="b000d-148">Välj den domän som du angav när du initierade näthandel.</span><span class="sxs-lookup"><span data-stu-id="b000d-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="b000d-149">Som standardkanal väljer du **Fabrikam utökade online-butik**.</span><span class="sxs-lookup"><span data-stu-id="b000d-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="b000d-150">(Se till att välja den **utökade** onlinebutiken)</span><span class="sxs-lookup"><span data-stu-id="b000d-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="b000d-151">För standardspråk väljer du **sv-SE**.</span><span class="sxs-lookup"><span data-stu-id="b000d-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="b000d-152">Lämna värdet i fältet **sökväg** som det är.</span><span class="sxs-lookup"><span data-stu-id="b000d-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="b000d-153">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000d-153">Select **OK**.</span></span> <span data-ttu-id="b000d-154">Listan över sidor på webbplatsen visas.</span><span class="sxs-lookup"><span data-stu-id="b000d-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="b000d-155">Aktivera jobb</span><span class="sxs-lookup"><span data-stu-id="b000d-155">Enable jobs</span></span>

<span data-ttu-id="b000d-156">Gör så här om du vill aktivera jobb i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b000d-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="b000d-157">Logga in på miljön (HQ).</span><span class="sxs-lookup"><span data-stu-id="b000d-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="b000d-158">Gå till menyn till vänster **Retail och Commerce \> Förfrågningar och rapporter \> Batch-jobb**.</span><span class="sxs-lookup"><span data-stu-id="b000d-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="b000d-159">De återstående stegen i den här proceduren måste slutföras för vart och ett av följande jobb:</span><span class="sxs-lookup"><span data-stu-id="b000d-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="b000d-160">Bearbeta butikorders e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="b000d-160">Process retail order email notification</span></span>
    * <span data-ttu-id="b000d-161">Produkttillgänglighet</span><span class="sxs-lookup"><span data-stu-id="b000d-161">Product availability</span></span>
    * <span data-ttu-id="b000d-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="b000d-162">P-0001</span></span>
    * <span data-ttu-id="b000d-163">Synkronisera orderjobb</span><span class="sxs-lookup"><span data-stu-id="b000d-163">Synchronize orders job</span></span>

1. <span data-ttu-id="b000d-164">Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn.</span><span class="sxs-lookup"><span data-stu-id="b000d-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="b000d-165">Utför följande steg om status för jobbet är **Kör**:</span><span class="sxs-lookup"><span data-stu-id="b000d-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="b000d-166">Välj posten.</span><span class="sxs-lookup"><span data-stu-id="b000d-166">Select the record.</span></span>
    1. <span data-ttu-id="b000d-167">I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="b000d-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="b000d-168">Välj **Avbryt** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000d-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="b000d-169">Om du vill kan du också ställa in upprepningsintervallet till en (1) minut för följande jobb:</span><span class="sxs-lookup"><span data-stu-id="b000d-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="b000d-170">Bearbeta butikorders e-postmeddelandejobb</span><span class="sxs-lookup"><span data-stu-id="b000d-170">Process retail order email notification job</span></span>
* <span data-ttu-id="b000d-171">P-0001 jobb</span><span class="sxs-lookup"><span data-stu-id="b000d-171">P-0001 job</span></span>
* <span data-ttu-id="b000d-172">Synkronisera orderjobb</span><span class="sxs-lookup"><span data-stu-id="b000d-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="b000d-173">Kör fullständig datasynkronisering</span><span class="sxs-lookup"><span data-stu-id="b000d-173">Run full data synchronization</span></span>

<span data-ttu-id="b000d-174">Om du vill köra fullständig datasynkronisering i Commerce-administration följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b000d-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="b000d-175">Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Commercesschemaläggare \> Kanaldatabas**.</span><span class="sxs-lookup"><span data-stu-id="b000d-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="b000d-176">Välj kanalen med namnet **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="b000d-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="b000d-177">I åtgärdsfönstret, välj **Fullständig datasynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="b000d-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="b000d-178">Ange **9999** som distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="b000d-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="b000d-179">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000d-179">Select **OK**.</span></span>
1. <span data-ttu-id="b000d-180">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b000d-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="b000d-181">Testa kreditkortsinformation för att utföra testinköp</span><span class="sxs-lookup"><span data-stu-id="b000d-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="b000d-182">För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:</span><span class="sxs-lookup"><span data-stu-id="b000d-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="b000d-183">**Kortnummer:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="b000d-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="b000d-184">**Utgångsdatum:** 10/20</span><span class="sxs-lookup"><span data-stu-id="b000d-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="b000d-185">**Kortverifieringsnummer (CVV) kod:** 737</span><span class="sxs-lookup"><span data-stu-id="b000d-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b000d-186">Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="b000d-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b000d-187">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b000d-187">Next steps</span></span>

<span data-ttu-id="b000d-188">När etablerings- och konfigurationsstegen är slutförda kan du börja använda din bedömningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="b000d-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="b000d-189">Använd Commerce URL:en för webbplatsskaparen för att gå till redigeringsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="b000d-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="b000d-190">Använd URL:en för Commerce webbplats för att gå till näthandelssajt för butikskunden.</span><span class="sxs-lookup"><span data-stu-id="b000d-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="b000d-191">För att konfigurera valfria funktioner för Commerce bedömningsmiljö efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för bedömningsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="b000d-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b000d-192">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b000d-192">Additional resources</span></span>

[<span data-ttu-id="b000d-193">Dynamics 365 Commerce bedömningsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="b000d-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="b000d-194">Etablera en Dynamics 365 Commerce bedömningsmiljön</span><span class="sxs-lookup"><span data-stu-id="b000d-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="b000d-195">Konfigurera valfria funktioner för en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="b000d-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="b000d-196">Konfigurera BOPIS i en Dynamics 365 Commerce bedömningsmiljö</span><span class="sxs-lookup"><span data-stu-id="b000d-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="b000d-197">Dynamics 365 Commerce bedömningsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="b000d-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="b000d-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="b000d-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="b000d-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="b000d-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="b000d-200">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="b000d-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="b000d-201">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="b000d-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
