---
title: Skapa en näthandelsplats
description: I det här avsnittet beskrivs de uppgifter som är kopplade till skapandet av en ny e-handelswebbplats i Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697139"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="49631-103">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="49631-103">Create an e-Commerce site</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="49631-104">I det här avsnittet beskrivs de uppgifter som är kopplade till skapandet av en ny e-handelswebbplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49631-104">This topic describes the tasks that are associated with the creation of a new e-Commerce site in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="49631-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="49631-105">Overview</span></span>

<span data-ttu-id="49631-106">Innan du börjar utveckla din näthandelsplats måste du först skapa en ny webbplats i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="49631-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="49631-107">Innan du kan skapa en ny plats måste minst en onlinebutik skapas i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="49631-107">Before you can create a new site, at least one online store must be created in Dynamics 365 Retail.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="49631-108">Ställ in din webbplats</span><span class="sxs-lookup"><span data-stu-id="49631-108">Set up your site</span></span>

<span data-ttu-id="49631-109">Gör följande om du vill ställa in din webbplats.</span><span class="sxs-lookup"><span data-stu-id="49631-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="49631-110">Välj länken för webbplatsredigeringsmiljön i LCS (Microsoft Lifecycle Services).</span><span class="sxs-lookup"><span data-stu-id="49631-110">In Microsoft Lifecycle Services (LCS), select the link for the site authoring environment.</span></span> 
1. <span data-ttu-id="49631-111">På startsidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="49631-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="49631-112">Ange följande information i dialogrutan **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="49631-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="49631-113">Fält</span><span class="sxs-lookup"><span data-stu-id="49631-113">Field</span></span>                               | <span data-ttu-id="49631-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="49631-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="49631-115">Webbplatsens namn</span><span class="sxs-lookup"><span data-stu-id="49631-115">Site name</span></span>                           | <span data-ttu-id="49631-116">Ange visningsnamnet som ska användas för webbplatsen i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="49631-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="49631-117">Det här namnet visas bara i redigeringsmiljön och kommer inte att visas för kunderna.</span><span class="sxs-lookup"><span data-stu-id="49631-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="49631-118">Webbplatsadministratörens säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="49631-118">Site administrator's security group</span></span> | <span data-ttu-id="49631-119">Ange den säkerhetsgrupp för Microsoft Azure Active Directory (Azure AD) som hanterar användare med rollen webbplatsadministratör på den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="49631-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="49631-120">Standardkanal (driftenhetsnummer)</span><span class="sxs-lookup"><span data-stu-id="49631-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="49631-121">Välj den onlinebutik som den här webbplatsen ska fungera som webbskyltfönster för.</span><span class="sxs-lookup"><span data-stu-id="49631-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="49631-122">Om du vill att din näthandelsplats ska stödja flera onlinebutiker måste du associera butikerna med din webbplats i **webbplatsinställningar** när webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="49631-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="49631-123">Standardspråk</span><span class="sxs-lookup"><span data-stu-id="49631-123">Default language</span></span>                            | <span data-ttu-id="49631-124">Ange standardspråket för den här onlinebutiken och marknaden.</span><span class="sxs-lookup"><span data-stu-id="49631-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="49631-125">En onlinebutik har stöd för flera språk.</span><span class="sxs-lookup"><span data-stu-id="49631-125">An online store can support multiple languages.</span></span> <span data-ttu-id="49631-126">Om du vill stödja flera språk för den här onlinebutiken eller en annan onlinebutik kan du konfigurera stödet i **platsinställningar** efter att webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="49631-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="49631-127">Domän</span><span class="sxs-lookup"><span data-stu-id="49631-127">Domain</span></span>                              | <span data-ttu-id="49631-128">Välj ett domännamn som ska fungera som domän för denna onlinebutik.</span><span class="sxs-lookup"><span data-stu-id="49631-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="49631-129">Om du inte har konfigurerat några domäner i LCS kan du lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="49631-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="49631-130">När din domän har konfigurerats i LCS måste du lägga till den i din onlinebutik i **webbplatsinställningarna**.</span><span class="sxs-lookup"><span data-stu-id="49631-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="49631-131">Sökväg</span><span class="sxs-lookup"><span data-stu-id="49631-131">Path</span></span>                              | <span data-ttu-id="49631-132">När din webbplats har stöd för mer än ett språk för ett givet domännamn, använder du sökvägsfältet för att skapa en unik webbplats-URL för den domänen och språkkombinationen.</span><span class="sxs-lookup"><span data-stu-id="49631-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="49631-133">Om det språk som du har angett i fältet **Standardspråk** är det enda språk som du kommer att stödja för den här domänen, eller om det är standardspråket när du har lokaliserat platsen till ytterligare språk, rekommenderar vi att du lämnar det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="49631-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="49631-134">När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="49631-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="49631-135">Du kan också använda det nedrullningsbara menyn längst upp till vänster på sidan för att komma åt de tilldelade produkterna efter kategori.</span><span class="sxs-lookup"><span data-stu-id="49631-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49631-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="49631-136">Additional resources</span></span>

[<span data-ttu-id="49631-137">Översikt över onlinebutik</span><span class="sxs-lookup"><span data-stu-id="49631-137">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="49631-138">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="49631-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="49631-139">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="49631-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="49631-140">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="49631-140">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="49631-141">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="49631-141">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="49631-142">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="49631-142">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="49631-143">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="49631-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="49631-144">Översikt över startsidan för redigering</span><span class="sxs-lookup"><span data-stu-id="49631-144">Authoring home page overview</span></span>](authoring-home-overview.md)

[<span data-ttu-id="49631-145">Lägga till en ny webbplatssida</span><span class="sxs-lookup"><span data-stu-id="49631-145">Add a new site page</span></span>](add-new-page.md)
