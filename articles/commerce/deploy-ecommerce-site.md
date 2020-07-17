---
title: Distribuera en ny klientorganisation för e-handel
description: I det här avsnittet beskrivs hur du distribuerar en ny näthandelsinnehavare med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
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
ms.openlocfilehash: 00f35b516dbf6ab4d4d9171c84a16b89f6afe832
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533285"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="ce1ba-103">Distribuera en ny klientorganisation för e-handel</span><span class="sxs-lookup"><span data-stu-id="ce1ba-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ce1ba-104">I det här avsnittet beskrivs hur du distribuerar en ny näthandelsplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="ce1ba-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ce1ba-105">Overview</span></span>

<span data-ttu-id="ce1ba-106">Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="ce1ba-107">Funktionerna för hantering av e-handel integreras i LCS.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="ce1ba-108">Mer information om LCS finns i [användarhandboken för Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="ce1ba-109">Kom igång</span><span class="sxs-lookup"><span data-stu-id="ce1ba-109">Get started</span></span>

<span data-ttu-id="ce1ba-110">Innan du kan initiera e-handel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="ce1ba-111">Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="ce1ba-112">Topologierna för tillverkning och begränsat läge stöds.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="ce1ba-113">Mer information om miljöer finns i [miljöplanering](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="ce1ba-114">Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="ce1ba-115">Initiera e-handelsplattform</span><span class="sxs-lookup"><span data-stu-id="ce1ba-115">Initialize e-Commerce</span></span>

<span data-ttu-id="ce1ba-116">Använd den här proceduren för att initiera funktionen för e-handel i en befintlig miljö.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="ce1ba-117">Innan du börjar måste du se till att du har följande obligatoriska information:</span><span class="sxs-lookup"><span data-stu-id="ce1ba-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="ce1ba-118">RCSU som ska användas.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="ce1ba-119">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för e-handelssystemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="ce1ba-120">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="ce1ba-121">Domänerna som ska associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="ce1ba-122">Dessutom kan du samla in följande valfria information:</span><span class="sxs-lookup"><span data-stu-id="ce1ba-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="ce1ba-123">Azure AD information om B2C (business-to-consumer):</span><span class="sxs-lookup"><span data-stu-id="ce1ba-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="ce1ba-124">Innehavarens namn.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-124">Tenant Name.</span></span>
    - <span data-ttu-id="ce1ba-125">Klient-ID.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-125">Client ID.</span></span>
    - <span data-ttu-id="ce1ba-126">Anpassad domän för inloggning.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="ce1ba-127">Svars-URL.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-127">Reply URL.</span></span>
    - <span data-ttu-id="ce1ba-128">Policy-ID för SignUp SignIn.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="ce1ba-129">Policy-ID för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="ce1ba-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="ce1ba-130">Redigera ID för profilpolicy.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="ce1ba-131">Denna information kan läggas till senare, genom en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="ce1ba-132">När du har samlat in den information som krävs följer du stegen nedan för att initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="ce1ba-133">Logga in på [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="ce1ba-134">Öppna det projekt som innehåller den miljö där du vill initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="ce1ba-135">Välj miljön avsnittet **miljöer**.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="ce1ba-136">Under **miljöfunktioner**, välj länken **Butik – hantera**.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="ce1ba-137">På fliken **e-handel** välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="ce1ba-138">En dialogruta visas där du måste ange den information som krävs för etableringen.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="ce1ba-139">Fyll i den information som krävs och gå sedan till nästa sida.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="ce1ba-140">Fyll i önskad information på nästa sida och skicka sedan in formuläret.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="ce1ba-141">Du kommer tillbaka till fliken **e-handel** där du bör se att initieringen har startats.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="ce1ba-142">Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **e-handel** senare.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="ce1ba-143">När e-handel initieras från LCS, etablerar systemet flera komponenter som krävs för e-handel och kopplar dem till miljön.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="ce1ba-144">När etableringen har slutförts, på fliken **e-handel** på sidan **Butikshantering** uppdateras för att avspegla etableringen.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="ce1ba-145">På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="ce1ba-146">Den innehåller också länkar till webbplatsen för e-handel och webbplatsskaparen för e-handel där webbplatser har redigerats.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="ce1ba-147">Få åtkomst till webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="ce1ba-147">Access site builder</span></span>

<span data-ttu-id="ce1ba-148">Du öppnar webbplatsskaparen genom att gå till fliken **e-handel** på sidan **butikshantering** i LCS och väljer länken **Hanteringsverktyg för näthandelsplats**.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="ce1ba-149">Landningssidan för webbplatsskaparen visar en vy på klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="ce1ba-150">Från den här sidan kan du:</span><span class="sxs-lookup"><span data-stu-id="ce1ba-150">From this page, you can:</span></span>

- <span data-ttu-id="ce1ba-151">Ändra inställningarna för klientorganisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="ce1ba-152">Navigera till en webbplats som du har skapat och ha behörighet att visa den.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="ce1ba-153">Åtkomst till granskningsfunktioner, t.ex. av redigering och rapportering.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="ce1ba-154">Skapa en ny anläggning.</span><span class="sxs-lookup"><span data-stu-id="ce1ba-154">Create a new site.</span></span> <span data-ttu-id="ce1ba-155">Mer information om hur du skapar en ny webbplats finns i [Skapa en e-handelsplats](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="ce1ba-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="ce1ba-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ce1ba-156">Additional resources</span></span>

[<span data-ttu-id="ce1ba-157">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="ce1ba-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="ce1ba-158">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="ce1ba-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="ce1ba-159">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="ce1ba-159">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="ce1ba-160">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="ce1ba-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="ce1ba-161">Överföring av URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="ce1ba-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="ce1ba-162">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="ce1ba-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="ce1ba-163">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="ce1ba-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="ce1ba-164">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="ce1ba-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="ce1ba-165">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="ce1ba-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="ce1ba-166">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="ce1ba-166">Enable location-based store detection</span></span>](enable-store-detection.md)
