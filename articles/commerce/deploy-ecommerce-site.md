---
title: Distribuera en ny klientorganisation för näthandel
description: I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelsplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 157dc8225e5bbf9338a1b5a79a2880e8a8c4bf10
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517292"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="0789a-103">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="0789a-103">Deploy a new e-commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0789a-104">I det här avsnittet beskrivs hur du distribuerar en ny Dynamics 365 Commerce-näthandelsplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0789a-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="0789a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0789a-105">Overview</span></span>

<span data-ttu-id="0789a-106">Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser.</span><span class="sxs-lookup"><span data-stu-id="0789a-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="0789a-107">Administreringsfunktionerna för näthandel integreras i LCS.</span><span class="sxs-lookup"><span data-stu-id="0789a-107">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="0789a-108">Mer information om LCS finns i [användarhandboken för Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="0789a-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="0789a-109">Kom i gång</span><span class="sxs-lookup"><span data-stu-id="0789a-109">Get started</span></span>

<span data-ttu-id="0789a-110">Innan du kan initiera näthandel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="0789a-110">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="0789a-111">Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare.</span><span class="sxs-lookup"><span data-stu-id="0789a-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="0789a-112">Topologierna för tillverkning och begränsat läge stöds.</span><span class="sxs-lookup"><span data-stu-id="0789a-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="0789a-113">Mer information om miljöer finns i [miljöplanering](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="0789a-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="0789a-114">Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="0789a-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="0789a-115">Initiera näthandel</span><span class="sxs-lookup"><span data-stu-id="0789a-115">Initialize e-commerce</span></span>

<span data-ttu-id="0789a-116">Använd den här proceduren för att initiera funktionen för näthandel i en befintlig miljö.</span><span class="sxs-lookup"><span data-stu-id="0789a-116">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="0789a-117">Innan du börjar måste du se till att du har följande obligatoriska information:</span><span class="sxs-lookup"><span data-stu-id="0789a-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="0789a-118">RCSU som ska användas.</span><span class="sxs-lookup"><span data-stu-id="0789a-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="0789a-119">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för systemadministratörer för näthandel.</span><span class="sxs-lookup"><span data-stu-id="0789a-119">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="0789a-120">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="0789a-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="0789a-121">Domänerna som ska associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="0789a-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="0789a-122">Dessutom kan du samla in följande valfria information:</span><span class="sxs-lookup"><span data-stu-id="0789a-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="0789a-123">Azure AD information om B2C (business-to-consumer):</span><span class="sxs-lookup"><span data-stu-id="0789a-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="0789a-124">Innehavarens namn.</span><span class="sxs-lookup"><span data-stu-id="0789a-124">Tenant Name.</span></span>
    - <span data-ttu-id="0789a-125">Klient-ID.</span><span class="sxs-lookup"><span data-stu-id="0789a-125">Client ID.</span></span>
    - <span data-ttu-id="0789a-126">Anpassad domän för inloggning.</span><span class="sxs-lookup"><span data-stu-id="0789a-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="0789a-127">Svars-URL.</span><span class="sxs-lookup"><span data-stu-id="0789a-127">Reply URL.</span></span>
    - <span data-ttu-id="0789a-128">Policy-ID för SignUp SignIn.</span><span class="sxs-lookup"><span data-stu-id="0789a-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="0789a-129">Policy-ID för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="0789a-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="0789a-130">Redigera ID för profilpolicy.</span><span class="sxs-lookup"><span data-stu-id="0789a-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="0789a-131">Denna information kan läggas till senare, genom en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="0789a-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="0789a-132">När du har samlat in den information som krävs följer du stegen nedan för att initiera näthandel.</span><span class="sxs-lookup"><span data-stu-id="0789a-132">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="0789a-133">Logga in på [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0789a-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="0789a-134">Öppna det projekt som innehåller den miljö där du vill initiera näthandel.</span><span class="sxs-lookup"><span data-stu-id="0789a-134">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="0789a-135">Välj miljön avsnittet **miljöer**.</span><span class="sxs-lookup"><span data-stu-id="0789a-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="0789a-136">Under **miljöfunktioner**, välj länken **Butik – hantera**.</span><span class="sxs-lookup"><span data-stu-id="0789a-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="0789a-137">På fliken **näthandel** välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="0789a-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="0789a-138">En dialogruta visas där du måste ange den information som krävs för etableringen.</span><span class="sxs-lookup"><span data-stu-id="0789a-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="0789a-139">Fyll i den information som krävs och gå sedan till nästa sida.</span><span class="sxs-lookup"><span data-stu-id="0789a-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="0789a-140">Fyll i önskad information på nästa sida och skicka sedan in formuläret.</span><span class="sxs-lookup"><span data-stu-id="0789a-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="0789a-141">Du kommer tillbaka till fliken **näthandel** där du bör se att initieringen har startats.</span><span class="sxs-lookup"><span data-stu-id="0789a-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="0789a-142">Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **näthandel** senare.</span><span class="sxs-lookup"><span data-stu-id="0789a-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="0789a-143">När näthandel initieras från LCS etablerar systemet flera komponenter som krävs för näthandel och kopplar dem till miljön.</span><span class="sxs-lookup"><span data-stu-id="0789a-143">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="0789a-144">När etableringen har slutförts, på fliken **näthandel** på sidan **Butikshantering** uppdateras för att avspegla etableringen.</span><span class="sxs-lookup"><span data-stu-id="0789a-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="0789a-145">På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner.</span><span class="sxs-lookup"><span data-stu-id="0789a-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="0789a-146">Den innehåller också länkar till webbplatsen för näthandel och Commerce-webbplatsskaparen där webbplatser har skapats.</span><span class="sxs-lookup"><span data-stu-id="0789a-146">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="0789a-147">Få åtkomst till Commerce-webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="0789a-147">Access Commerce site builder</span></span>

<span data-ttu-id="0789a-148">För att få åtkomst till Commerce-webbplatsskaparen går du till fliken **näthandel** på sidan **Butikshantering** i LCS och väljer länken **Hanteringsverktyg för näthandelsplats**.</span><span class="sxs-lookup"><span data-stu-id="0789a-148">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="0789a-149">Landningssidan för webbplatsskaparen visar en vy på klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="0789a-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="0789a-150">Från den här sidan kan du:</span><span class="sxs-lookup"><span data-stu-id="0789a-150">From this page, you can:</span></span>

- <span data-ttu-id="0789a-151">Ändra inställningarna för klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="0789a-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="0789a-152">Navigera till en webbplats som du har skapat och ha behörighet att visa den.</span><span class="sxs-lookup"><span data-stu-id="0789a-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="0789a-153">Åtkomst till granskningsfunktioner, t.ex. av redigering och rapportering.</span><span class="sxs-lookup"><span data-stu-id="0789a-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="0789a-154">Skapa en ny anläggning.</span><span class="sxs-lookup"><span data-stu-id="0789a-154">Create a new site.</span></span> <span data-ttu-id="0789a-155">Mer information om hur du skapar en ny webbplats finns i [Skapa en näthandelsplats](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="0789a-155">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="0789a-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0789a-156">Additional resources</span></span>

[<span data-ttu-id="0789a-157">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="0789a-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="0789a-158">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="0789a-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="0789a-159">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="0789a-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="0789a-160">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="0789a-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="0789a-161">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="0789a-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="0789a-162">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="0789a-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="0789a-163">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="0789a-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="0789a-164">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="0789a-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="0789a-165">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="0789a-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="0789a-166">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="0789a-166">Enable location-based store detection</span></span>](enable-store-detection.md)
