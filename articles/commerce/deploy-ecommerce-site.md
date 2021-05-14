---
title: Distribuera en ny klientorganisation för näthandel
description: I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelssajt med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b228babfd32a4191eeed2a6d924a8b99f1a5311
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936716"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="654b8-103">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="654b8-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="654b8-104">I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelssajt med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="654b8-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="654b8-105">Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser.</span><span class="sxs-lookup"><span data-stu-id="654b8-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="654b8-106">Administreringsfunktionerna för näthandel integreras i LCS.</span><span class="sxs-lookup"><span data-stu-id="654b8-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="654b8-107">Mer information om LCS finns i [användarhandboken för Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="654b8-107">To learn more about LCS, see the [Lifecycle Services User Guide](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="654b8-108">Kom i gång</span><span class="sxs-lookup"><span data-stu-id="654b8-108">Get started</span></span>

<span data-ttu-id="654b8-109">Innan du kan initiera näthandel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="654b8-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="654b8-110">Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare.</span><span class="sxs-lookup"><span data-stu-id="654b8-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="654b8-111">Topologierna för tillverkning och begränsat läge stöds.</span><span class="sxs-lookup"><span data-stu-id="654b8-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="654b8-112">Mer information om miljöer finns i [miljöplanering](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="654b8-112">For more information about environments, see [Environment planning](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="654b8-113">Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="654b8-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="654b8-114">Initiera näthandel</span><span class="sxs-lookup"><span data-stu-id="654b8-114">Initialize e-commerce</span></span>

<span data-ttu-id="654b8-115">Använd den här proceduren för att initiera funktionen för näthandel i en befintlig miljö.</span><span class="sxs-lookup"><span data-stu-id="654b8-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="654b8-116">Innan du börjar måste du se till att du har följande obligatoriska information:</span><span class="sxs-lookup"><span data-stu-id="654b8-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="654b8-117">RCSU som ska användas.</span><span class="sxs-lookup"><span data-stu-id="654b8-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="654b8-118">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för systemadministratörer för näthandel.</span><span class="sxs-lookup"><span data-stu-id="654b8-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="654b8-119">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="654b8-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="654b8-120">Domänerna som ska associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="654b8-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="654b8-121">Dessutom kan du samla in följande valfria information:</span><span class="sxs-lookup"><span data-stu-id="654b8-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="654b8-122">Azure AD information om B2C (business-to-consumer):</span><span class="sxs-lookup"><span data-stu-id="654b8-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="654b8-123">Innehavarens namn.</span><span class="sxs-lookup"><span data-stu-id="654b8-123">Tenant Name.</span></span>
    - <span data-ttu-id="654b8-124">Klient-ID.</span><span class="sxs-lookup"><span data-stu-id="654b8-124">Client ID.</span></span>
    - <span data-ttu-id="654b8-125">Anpassad domän för inloggning.</span><span class="sxs-lookup"><span data-stu-id="654b8-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="654b8-126">Svars-URL.</span><span class="sxs-lookup"><span data-stu-id="654b8-126">Reply URL.</span></span>
    - <span data-ttu-id="654b8-127">Policy-ID för SignUp SignIn.</span><span class="sxs-lookup"><span data-stu-id="654b8-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="654b8-128">Policy-ID för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="654b8-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="654b8-129">Redigera ID för profilpolicy.</span><span class="sxs-lookup"><span data-stu-id="654b8-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="654b8-130">Denna information kan läggas till senare, genom en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="654b8-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="654b8-131">När du har samlat in den information som krävs följer du stegen nedan för att initiera näthandel.</span><span class="sxs-lookup"><span data-stu-id="654b8-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="654b8-132">Logga in på [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="654b8-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="654b8-133">Öppna det projekt som innehåller den miljö där du vill initiera näthandel.</span><span class="sxs-lookup"><span data-stu-id="654b8-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="654b8-134">Välj miljön avsnittet **miljöer**.</span><span class="sxs-lookup"><span data-stu-id="654b8-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="654b8-135">Under **miljöfunktioner**, välj länken **Butik – hantera**.</span><span class="sxs-lookup"><span data-stu-id="654b8-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="654b8-136">På fliken **näthandel** välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="654b8-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="654b8-137">En dialogruta visas där du måste ange den information som krävs för etableringen.</span><span class="sxs-lookup"><span data-stu-id="654b8-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="654b8-138">Fyll i den information som krävs och gå sedan till nästa sida.</span><span class="sxs-lookup"><span data-stu-id="654b8-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="654b8-139">Fyll i önskad information på nästa sida och skicka sedan in formuläret.</span><span class="sxs-lookup"><span data-stu-id="654b8-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="654b8-140">Du kommer tillbaka till fliken **näthandel** där du bör se att initieringen har startats.</span><span class="sxs-lookup"><span data-stu-id="654b8-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="654b8-141">Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **näthandel** senare.</span><span class="sxs-lookup"><span data-stu-id="654b8-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="654b8-142">När näthandel initieras från LCS etablerar systemet flera komponenter som krävs för näthandel och kopplar dem till miljön.</span><span class="sxs-lookup"><span data-stu-id="654b8-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="654b8-143">När etableringen har slutförts, på fliken **näthandel** på sidan **Butikshantering** uppdateras för att avspegla etableringen.</span><span class="sxs-lookup"><span data-stu-id="654b8-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="654b8-144">På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner.</span><span class="sxs-lookup"><span data-stu-id="654b8-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="654b8-145">Den innehåller också länkar till webbplatsen för näthandel och Commerce-webbplatsbyggaren där webbplatser har skapats.</span><span class="sxs-lookup"><span data-stu-id="654b8-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="654b8-146">Få åtkomst till Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="654b8-146">Access Commerce site builder</span></span>

<span data-ttu-id="654b8-147">För att få åtkomst till Commerce-webbplatsbyggaren går du till fliken **näthandel** på sidan **Butikshantering** i LCS och väljer länken **Hanteringsverktyg för näthandelssajt**.</span><span class="sxs-lookup"><span data-stu-id="654b8-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="654b8-148">Landningssidan för webbplatsskaparen visar en vy på klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="654b8-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="654b8-149">Från den här sidan kan du:</span><span class="sxs-lookup"><span data-stu-id="654b8-149">From this page, you can:</span></span>

- <span data-ttu-id="654b8-150">Ändra inställningarna för klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="654b8-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="654b8-151">Navigera till en webbplats som du har skapat och ha behörighet att visa den.</span><span class="sxs-lookup"><span data-stu-id="654b8-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="654b8-152">Åtkomst till granskningsfunktioner, t.ex. av redigering och rapportering.</span><span class="sxs-lookup"><span data-stu-id="654b8-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="654b8-153">Skapa en ny anläggning.</span><span class="sxs-lookup"><span data-stu-id="654b8-153">Create a new site.</span></span> <span data-ttu-id="654b8-154">Mer information om hur du skapar en ny webbplats finns i [Skapa en näthandelssajt](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="654b8-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="654b8-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="654b8-155">Additional resources</span></span>

[<span data-ttu-id="654b8-156">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="654b8-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="654b8-157">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="654b8-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="654b8-158">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="654b8-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="654b8-159">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="654b8-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="654b8-160">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="654b8-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="654b8-161">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="654b8-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="654b8-162">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="654b8-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="654b8-163">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="654b8-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="654b8-164">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="654b8-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="654b8-165">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="654b8-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]