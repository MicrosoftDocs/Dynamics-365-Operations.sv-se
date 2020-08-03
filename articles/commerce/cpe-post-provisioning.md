---
title: Konfigurera en Dynamics 365 Commerce utvärderingsmiljö
description: Detta ämne förklarar hur du konfigurerar utvärderingsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.
author: psimolin
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599734"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="709a2-103">Konfigurera en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="709a2-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="709a2-104">Detta ämne förklarar hur du konfigurerar utvärderingsmiljö för Microsoft Dynamics 365 Commerce efter att den är etablerad.</span><span class="sxs-lookup"><span data-stu-id="709a2-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="709a2-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="709a2-105">Overview</span></span>

<span data-ttu-id="709a2-106">Slutför procedurerna i det här avsnittet först när utvärderingsmiljö för Commerce har etablerats.</span><span class="sxs-lookup"><span data-stu-id="709a2-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="709a2-107">Information om hur du konfigurerar etablerar utvärderingsmiljö för Commerce, se [Etablera en utvärderingsmiljö för Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="709a2-107">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="709a2-108">När din utvärderingsmiljö för Commerce har etablerats måste ytterligare konfigurationssteg för efter etableringen slutföras innan du kan börja utvärdera miljön.</span><span class="sxs-lookup"><span data-stu-id="709a2-108">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="709a2-109">Om du vill utföra dessa steg måste du använda Microsoft Dynamics Lifecycle Services (LCS) och Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="709a2-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="709a2-110">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="709a2-110">Before you start</span></span>

1. <span data-ttu-id="709a2-111">Logga in på [LCS-portal](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="709a2-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="709a2-112">Gå till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="709a2-112">Go to your project.</span></span>
1. <span data-ttu-id="709a2-113">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="709a2-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="709a2-114">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="709a2-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="709a2-115">Välj i miljöinformation till höger **Logga in i miljön**.</span><span class="sxs-lookup"><span data-stu-id="709a2-115">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="709a2-116">Du kommer att skickas till Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="709a2-116">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="709a2-117">Kontrollera att **USRT** juridisk person har valts i övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="709a2-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="709a2-118">Under åtgärderna efter etablering i Commerce-administration, se till att den juridiska personen **USRT** alltid är vald.</span><span class="sxs-lookup"><span data-stu-id="709a2-118">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="709a2-119">Konfigurera kassan</span><span class="sxs-lookup"><span data-stu-id="709a2-119">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="709a2-120">Associera arbetare med din identitet</span><span class="sxs-lookup"><span data-stu-id="709a2-120">Associate a worker with your identity</span></span>

<span data-ttu-id="709a2-121">Om du vill associera en anställd med din identitet, följ dessa steg i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="709a2-121">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="709a2-122">Använd menyn till vänster för att gå till **moduler \> Retail och Commerce \> anställda \> arbetare**.</span><span class="sxs-lookup"><span data-stu-id="709a2-122">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="709a2-123">Hitta och markera följande post: **000713 - Andrew Collette** i listan.</span><span class="sxs-lookup"><span data-stu-id="709a2-123">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="709a2-124">I åtgärdsfönstret, välj **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="709a2-124">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="709a2-125">Välj **Associera befintlig identitet**.</span><span class="sxs-lookup"><span data-stu-id="709a2-125">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="709a2-126">I fältet **E-post** (till höger om **Sök via e-post**), skriv din e-postadress.</span><span class="sxs-lookup"><span data-stu-id="709a2-126">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="709a2-127">Välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="709a2-127">Select **Search**.</span></span>
1. <span data-ttu-id="709a2-128">Markera posten med ditt namn.</span><span class="sxs-lookup"><span data-stu-id="709a2-128">Select the record that has your name.</span></span>
1. <span data-ttu-id="709a2-129">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="709a2-129">Select **OK**.</span></span>
1. <span data-ttu-id="709a2-130">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="709a2-130">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="709a2-131">Aktivera molnbaserad kassa</span><span class="sxs-lookup"><span data-stu-id="709a2-131">Activate Cloud POS</span></span>

<span data-ttu-id="709a2-132">Om du vill aktivera Cloud POS i LCS, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="709a2-132">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="709a2-133">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="709a2-133">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="709a2-134">Välj din miljö i listan.</span><span class="sxs-lookup"><span data-stu-id="709a2-134">Select your environment in the list.</span></span>
1. <span data-ttu-id="709a2-135">Välj i miljöinformation till höger **Logga in i molnbaserad kassa**.</span><span class="sxs-lookup"><span data-stu-id="709a2-135">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="709a2-136">Välj **Nästa** om du vill öppna dialogrutan **innan du startar**.</span><span class="sxs-lookup"><span data-stu-id="709a2-136">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="709a2-137">Lämna fältet **Server URL** tomt.</span><span class="sxs-lookup"><span data-stu-id="709a2-137">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="709a2-138">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="709a2-138">Select **Next**.</span></span>
1. <span data-ttu-id="709a2-139">Logga in med ditt Microsoft Azure Active Directory (Azure AD)-konto.</span><span class="sxs-lookup"><span data-stu-id="709a2-139">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="709a2-140">Under **Butiksnamn**, välj **San Francisco** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="709a2-140">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="709a2-141">Under **Register och enhet**, välj **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="709a2-141">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="709a2-142">Välj **aktivera**.</span><span class="sxs-lookup"><span data-stu-id="709a2-142">Select **Activate**.</span></span> <span data-ttu-id="709a2-143">Du är utloggad och tagen till kassainloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="709a2-143">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="709a2-144">Du kan nu logga in på molnbaserad kassaupplevelsen med operatörs-ID **000713** och lösenord **123**.</span><span class="sxs-lookup"><span data-stu-id="709a2-144">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="709a2-145">Ställ in din webbplats i Commerce</span><span class="sxs-lookup"><span data-stu-id="709a2-145">Set up your site in Commerce</span></span>

<span data-ttu-id="709a2-146">Följ dessa steg om du vill börja konfigurera din utvärderingswebbplats i Commerce.</span><span class="sxs-lookup"><span data-stu-id="709a2-146">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="709a2-147">Logga in på webbplatsskaparen med hjälp av den URL som du antecknade när du initierade e-handel under etableringen (se [initiera e-handel](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="709a2-147">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="709a2-148">Klicka på på webbplatsen **Fabrikam** för att öppna dialogrutan webbplatsinställningar.</span><span class="sxs-lookup"><span data-stu-id="709a2-148">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="709a2-149">Välj den domän som du angav när du initierade e-handel.</span><span class="sxs-lookup"><span data-stu-id="709a2-149">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="709a2-150">Som standardkanal väljer du **Fabrikam utökade online-butik**.</span><span class="sxs-lookup"><span data-stu-id="709a2-150">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="709a2-151">(Se till att välja den **utökade** onlinebutiken)</span><span class="sxs-lookup"><span data-stu-id="709a2-151">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="709a2-152">För standardspråk väljer du **sv-SE**.</span><span class="sxs-lookup"><span data-stu-id="709a2-152">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="709a2-153">Lämna värdet i fältet **sökväg** som det är.</span><span class="sxs-lookup"><span data-stu-id="709a2-153">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="709a2-154">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="709a2-154">Select **OK**.</span></span> <span data-ttu-id="709a2-155">Listan över sidor på webbplatsen visas.</span><span class="sxs-lookup"><span data-stu-id="709a2-155">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="709a2-156">Aktivera jobb</span><span class="sxs-lookup"><span data-stu-id="709a2-156">Enable jobs</span></span>

<span data-ttu-id="709a2-157">Gör så här om du vill aktivera jobb i Commerce.</span><span class="sxs-lookup"><span data-stu-id="709a2-157">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="709a2-158">Logga in på miljön (HQ).</span><span class="sxs-lookup"><span data-stu-id="709a2-158">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="709a2-159">Gå till menyn till vänster **Retail och Commerce \> Förfrågningar och rapporter \> Batch-jobb**.</span><span class="sxs-lookup"><span data-stu-id="709a2-159">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="709a2-160">De återstående stegen i den här proceduren måste slutföras för vart och ett av följande jobb:</span><span class="sxs-lookup"><span data-stu-id="709a2-160">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="709a2-161">Bearbeta butikorders e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="709a2-161">Process retail order email notification</span></span>
    * <span data-ttu-id="709a2-162">Produkttillgänglighet</span><span class="sxs-lookup"><span data-stu-id="709a2-162">Product availability</span></span>
    * <span data-ttu-id="709a2-163">P-0001</span><span class="sxs-lookup"><span data-stu-id="709a2-163">P-0001</span></span>
    * <span data-ttu-id="709a2-164">Synkronisera orderjobb</span><span class="sxs-lookup"><span data-stu-id="709a2-164">Synchronize orders job</span></span>

1. <span data-ttu-id="709a2-165">Använd snabbfiltret för att söka efter jobbet med hjälp av dess namn.</span><span class="sxs-lookup"><span data-stu-id="709a2-165">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="709a2-166">Utför följande steg om status för jobbet är **Kör**:</span><span class="sxs-lookup"><span data-stu-id="709a2-166">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="709a2-167">Välj posten.</span><span class="sxs-lookup"><span data-stu-id="709a2-167">Select the record.</span></span>
    1. <span data-ttu-id="709a2-168">I Åtgärdsfönstret på fliken **Batchjobb** välj **Ändra status**.</span><span class="sxs-lookup"><span data-stu-id="709a2-168">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="709a2-169">Välj **Avbryt** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="709a2-169">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="709a2-170">Om du vill kan du också ställa in upprepningsintervallet till en (1) minut för följande jobb:</span><span class="sxs-lookup"><span data-stu-id="709a2-170">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="709a2-171">Bearbeta butikorders e-postmeddelandejobb</span><span class="sxs-lookup"><span data-stu-id="709a2-171">Process retail order email notification job</span></span>
* <span data-ttu-id="709a2-172">P-0001 jobb</span><span class="sxs-lookup"><span data-stu-id="709a2-172">P-0001 job</span></span>
* <span data-ttu-id="709a2-173">Synkronisera orderjobb</span><span class="sxs-lookup"><span data-stu-id="709a2-173">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="709a2-174">Kör fullständig datasynkronisering</span><span class="sxs-lookup"><span data-stu-id="709a2-174">Run full data synchronization</span></span>

<span data-ttu-id="709a2-175">Om du vill köra fullständig datasynkronisering i Commerce-administration följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="709a2-175">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="709a2-176">Med hjälp av menyn till vänster, gå till **Moduler \> Retail och Commerce \> Administrationsinställning \> Handelsschemaläggare \> Kanaldatabas**.</span><span class="sxs-lookup"><span data-stu-id="709a2-176">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="709a2-177">Välj kanalen med namnet **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="709a2-177">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="709a2-178">I åtgärdsfönstret, välj **Fullständig datasynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="709a2-178">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="709a2-179">Ange **9999** som distributionsschema.</span><span class="sxs-lookup"><span data-stu-id="709a2-179">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="709a2-180">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="709a2-180">Select **OK**.</span></span>
1. <span data-ttu-id="709a2-181">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="709a2-181">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="709a2-182">Testa kreditkortsinformation för att utföra testinköp</span><span class="sxs-lookup"><span data-stu-id="709a2-182">Test credit card information to do test purchases</span></span>

<span data-ttu-id="709a2-183">För att kunna utföra testtransaktioner på webbplatsen kan du använda den här kreditkortsinformationen för testet:</span><span class="sxs-lookup"><span data-stu-id="709a2-183">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="709a2-184">**Kortnummer:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="709a2-184">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="709a2-185">**Utgångsdatum:** 10/20</span><span class="sxs-lookup"><span data-stu-id="709a2-185">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="709a2-186">**Kortverifieringsnummer (CVV) kod:** 737</span><span class="sxs-lookup"><span data-stu-id="709a2-186">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="709a2-187">Du bör aldrig försöka använda äkta kreditkortsinformation på testwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="709a2-187">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="709a2-188">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="709a2-188">Next steps</span></span>

<span data-ttu-id="709a2-189">När etablerings- och konfigurationsstegen är slutförda kan du börja använda din utvärderingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="709a2-189">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="709a2-190">Använd Commerce URL:en för webbplatsskaparen för att gå till redigeringsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="709a2-190">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="709a2-191">Använd URL:en för Commerce webbplats för att gå till näthandelsplats för butikskunden.</span><span class="sxs-lookup"><span data-stu-id="709a2-191">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="709a2-192">För att konfigurera valfria funktioner för Commerce utvärderingsmiljö efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för utvärderingsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="709a2-192">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="709a2-193">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="709a2-193">Additional resources</span></span>

[<span data-ttu-id="709a2-194">Dynamics 365 Commerce utvärderingsmiljö – översikt</span><span class="sxs-lookup"><span data-stu-id="709a2-194">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="709a2-195">Etablera en Dynamics 365 Commerce utvärderingsmiljön</span><span class="sxs-lookup"><span data-stu-id="709a2-195">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="709a2-196">Konfigurera valfria funktioner för en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="709a2-196">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="709a2-197">Konfigurera BOPIS i en Dynamics 365 Commerce utvärderingsmiljö</span><span class="sxs-lookup"><span data-stu-id="709a2-197">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="709a2-198">Dynamics 365 Commerce utvärderingsmiljö – vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="709a2-198">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="709a2-199">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="709a2-199">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="709a2-200">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="709a2-200">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="709a2-201">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="709a2-201">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="709a2-202">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="709a2-202">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
