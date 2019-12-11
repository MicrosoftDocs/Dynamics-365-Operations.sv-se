---
title: Distribuera en ny klientorganisation för e-handel
description: I det här avsnittet beskrivs hur du distribuerar en ny näthandelsinnehavare med hjälp av Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2632632b9b21dd3a88e9a4df0e65cfd28e579d2
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697461"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="4b566-103">Distribuera en ny klientorganisation för e-handel</span><span class="sxs-lookup"><span data-stu-id="4b566-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4b566-104">I det här avsnittet beskrivs hur du distribuerar en ny näthandelsplats med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4b566-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="4b566-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4b566-105">Overview</span></span>
    
<span data-ttu-id="4b566-106">Microsoft Dynamics Lifecycle Services (LCS) är en molnbaserad samarbetsyta som partners och kunder kan använda för att hantera sina projekt och miljöer, visa den senaste informationen om Microsoft Dynamics produkter och funktioner samt skapa, spåra och bläddra i supporthändelser.</span><span class="sxs-lookup"><span data-stu-id="4b566-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="4b566-107">Funktionerna för hantering av e-handel integreras i LCS.</span><span class="sxs-lookup"><span data-stu-id="4b566-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="4b566-108">Mer information om LCS finns i [användarhandboken för Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="4b566-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="4b566-109">Kom igång</span><span class="sxs-lookup"><span data-stu-id="4b566-109">Get started</span></span>

<span data-ttu-id="4b566-110">Innan du kan initiera e-handel måste du initiera ett projekt, en miljö och en Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="4b566-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="4b566-111">Om du vill utföra initieringen i LCS måste du ha behörighet till rollen som projektägare eller som en miljöhanterare.</span><span class="sxs-lookup"><span data-stu-id="4b566-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="4b566-112">Topologierna för tillverkning och begränsat läge stöds.</span><span class="sxs-lookup"><span data-stu-id="4b566-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="4b566-113">Mer information om miljöer finns i [miljöplanering](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="4b566-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="4b566-114">Mer information om RCSU finns i [Initiera Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="4b566-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="4b566-115">Initiera e-handelsplattform</span><span class="sxs-lookup"><span data-stu-id="4b566-115">Initialize e-Commerce</span></span>

<span data-ttu-id="4b566-116">Använd den här proceduren för att initiera funktionen för e-handel i en befintlig miljö.</span><span class="sxs-lookup"><span data-stu-id="4b566-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="4b566-117">Innan du börjar måste du se till att du har följande obligatoriska information:</span><span class="sxs-lookup"><span data-stu-id="4b566-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="4b566-118">RCSU som ska användas.</span><span class="sxs-lookup"><span data-stu-id="4b566-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="4b566-119">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för e-handelssystemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="4b566-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="4b566-120">Den Microsoft Azure Active Directory-säkerhetsgrupp som ska användas för moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="4b566-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="4b566-121">Domänerna som ska associeras med miljön.</span><span class="sxs-lookup"><span data-stu-id="4b566-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="4b566-122">Dessutom kan du samla in följande valfria information:</span><span class="sxs-lookup"><span data-stu-id="4b566-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="4b566-123">Azure AD information om B2C (business-to-consumer):</span><span class="sxs-lookup"><span data-stu-id="4b566-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="4b566-124">Innehavarens namn.</span><span class="sxs-lookup"><span data-stu-id="4b566-124">Tenant Name.</span></span>
    - <span data-ttu-id="4b566-125">Klient-ID.</span><span class="sxs-lookup"><span data-stu-id="4b566-125">Client ID.</span></span>
    - <span data-ttu-id="4b566-126">Anpassad domän för inloggning.</span><span class="sxs-lookup"><span data-stu-id="4b566-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="4b566-127">Svars-URL.</span><span class="sxs-lookup"><span data-stu-id="4b566-127">Reply URL.</span></span>
    - <span data-ttu-id="4b566-128">Policy-ID för SignUp SignIn.</span><span class="sxs-lookup"><span data-stu-id="4b566-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="4b566-129">Policy-ID för återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="4b566-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="4b566-130">Redigera ID för profilpolicy.</span><span class="sxs-lookup"><span data-stu-id="4b566-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="4b566-131">Denna information kan läggas till senare, genom en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="4b566-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="4b566-132">När du har samlat in den information som krävs följer du stegen nedan för att initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="4b566-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="4b566-133">Logga in på [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="4b566-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="4b566-134">Öppna det projekt som innehåller den miljö där du vill initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="4b566-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="4b566-135">Välj miljön avsnittet **miljöer**.</span><span class="sxs-lookup"><span data-stu-id="4b566-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="4b566-136">Under **miljöfunktioner**, välj länken **Butik – hantera**.</span><span class="sxs-lookup"><span data-stu-id="4b566-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="4b566-137">På fliken **e-handel** välj **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="4b566-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="4b566-138">En dialogruta visas där du måste ange den information som krävs för etableringen.</span><span class="sxs-lookup"><span data-stu-id="4b566-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="4b566-139">Fyll i den information som krävs och gå sedan till nästa sida.</span><span class="sxs-lookup"><span data-stu-id="4b566-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="4b566-140">Fyll i önskad information på nästa sida och skicka sedan in formuläret.</span><span class="sxs-lookup"><span data-stu-id="4b566-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="4b566-141">Du kommer tillbaka till fliken **e-handel** där du bör se att initieringen har startats.</span><span class="sxs-lookup"><span data-stu-id="4b566-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="4b566-142">Om du vill visa initieringsstatusen **uppdatera** du eller återgår till fliken **e-handel** senare.</span><span class="sxs-lookup"><span data-stu-id="4b566-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="4b566-143">När e-handel initieras från LCS, etablerar systemet flera komponenter som krävs för e-handel och kopplar dem till miljön.</span><span class="sxs-lookup"><span data-stu-id="4b566-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="4b566-144">När etableringen har slutförts, på fliken **e-handel** på sidan **Butikshantering** uppdateras för att avspegla etableringen.</span><span class="sxs-lookup"><span data-stu-id="4b566-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="4b566-145">På sidan visas de senaste anpassningsdistributionerna och status för alla andra pågående distributioner.</span><span class="sxs-lookup"><span data-stu-id="4b566-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="4b566-146">Den innehåller också länkar till webbplatsen för e-handel och platshanteringsverktyg för e-handel (redigeringsverktyget).</span><span class="sxs-lookup"><span data-stu-id="4b566-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="4b566-147">Åtkomst till redigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="4b566-147">Access the authoring environment</span></span>

<span data-ttu-id="4b566-148">Om du vill komma åt redigeringsmiljön går du till fliken **e-handel** på sidan **butikshantering**.</span><span class="sxs-lookup"><span data-stu-id="4b566-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="4b566-149">Där hittar du länkar till din e-handelsplats och verktyget för webbplatshantering.</span><span class="sxs-lookup"><span data-stu-id="4b566-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b566-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4b566-150">Additional resources</span></span>

[<span data-ttu-id="4b566-151">Översikt över onlinebutik</span><span class="sxs-lookup"><span data-stu-id="4b566-151">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="4b566-152">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="4b566-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4b566-153">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="4b566-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4b566-154">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="4b566-154">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="4b566-155">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="4b566-155">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="4b566-156">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="4b566-156">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="4b566-157">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="4b566-157">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
