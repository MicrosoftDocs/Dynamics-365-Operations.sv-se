---
title: Skapa en e-handelsplats
description: I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny e-handelswebbplats i Dynamics 365 Commerce webbplatsskaparen.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
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
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096784"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="33e5d-103">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="33e5d-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="33e5d-104">I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny e-handelswebbplats i Dynamics 365 Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="33e5d-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="33e5d-105">Innan du börjar utveckla din näthandelsplats måste du först skapa en ny webbplats i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="33e5d-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="33e5d-106">Innan du börjar utveckla din näthandelsplats måste du först skapa en ny webbplats i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="33e5d-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="33e5d-107">Innan du kan skapa en ny plats måste minst en onlinebutik skapas i Handel.</span><span class="sxs-lookup"><span data-stu-id="33e5d-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="33e5d-108">Ställ in din webbplats</span><span class="sxs-lookup"><span data-stu-id="33e5d-108">Set up your site</span></span>

<span data-ttu-id="33e5d-109">Gör följande om du vill ställa in din webbplats.</span><span class="sxs-lookup"><span data-stu-id="33e5d-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="33e5d-110">Öppna miljön för webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="33e5d-110">Open the site builder environment.</span></span> <span data-ttu-id="33e5d-111">Du hittar en länk till webbplatsskaparen i Microsoft Lifecycle Services (LCS) på sidan miljöfunktioner för Handel.</span><span class="sxs-lookup"><span data-stu-id="33e5d-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="33e5d-112">På startsidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="33e5d-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="33e5d-113">Ange följande information i dialogrutan **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="33e5d-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="33e5d-114">Fält</span><span class="sxs-lookup"><span data-stu-id="33e5d-114">Field</span></span>                               | <span data-ttu-id="33e5d-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="33e5d-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="33e5d-116">Webbplatsens namn</span><span class="sxs-lookup"><span data-stu-id="33e5d-116">Site name</span></span>                           | <span data-ttu-id="33e5d-117">Ange visningsnamnet som ska användas för webbplatsen i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="33e5d-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="33e5d-118">Det här namnet visas bara i redigeringsmiljön och kommer inte att visas för kunderna.</span><span class="sxs-lookup"><span data-stu-id="33e5d-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="33e5d-119">Webbplatsadministratörens säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="33e5d-119">Site administrator's security group</span></span> | <span data-ttu-id="33e5d-120">Ange den säkerhetsgrupp för Microsoft Azure Active Directory (Azure AD) som hanterar användare med rollen webbplatsadministratör på den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="33e5d-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="33e5d-121">Standardkanal (driftenhetsnummer)</span><span class="sxs-lookup"><span data-stu-id="33e5d-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="33e5d-122">Välj den onlinebutik som den här webbplatsen ska fungera som webbskyltfönster för.</span><span class="sxs-lookup"><span data-stu-id="33e5d-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="33e5d-123">Om du vill att din näthandelsplats ska stödja flera onlinebutiker måste du associera butikerna med din webbplats i **webbplatsinställningar** när webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="33e5d-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="33e5d-124">Standardspråk</span><span class="sxs-lookup"><span data-stu-id="33e5d-124">Default language</span></span>                            | <span data-ttu-id="33e5d-125">Ange standardspråket för den här onlinebutiken och marknaden.</span><span class="sxs-lookup"><span data-stu-id="33e5d-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="33e5d-126">En onlinebutik har stöd för flera språk.</span><span class="sxs-lookup"><span data-stu-id="33e5d-126">An online store can support multiple languages.</span></span> <span data-ttu-id="33e5d-127">Om du vill stödja flera språk för den här onlinebutiken eller en annan onlinebutik kan du konfigurera stödet i **platsinställningar** efter att webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="33e5d-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="33e5d-128">Domän</span><span class="sxs-lookup"><span data-stu-id="33e5d-128">Domain</span></span>                              | <span data-ttu-id="33e5d-129">Välj ett domännamn som ska fungera som domän för denna onlinebutik.</span><span class="sxs-lookup"><span data-stu-id="33e5d-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="33e5d-130">Om du inte har konfigurerat några domäner i LCS kan du lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="33e5d-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="33e5d-131">När din domän har konfigurerats i LCS måste du lägga till den i din onlinebutik i **webbplatsinställningarna**.</span><span class="sxs-lookup"><span data-stu-id="33e5d-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="33e5d-132">Sökväg</span><span class="sxs-lookup"><span data-stu-id="33e5d-132">Path</span></span>                              | <span data-ttu-id="33e5d-133">När din webbplats har stöd för mer än ett språk för ett givet domännamn, använder du sökvägsfältet för att skapa en unik webbplats-URL för den domänen och språkkombinationen.</span><span class="sxs-lookup"><span data-stu-id="33e5d-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="33e5d-134">Om det språk som du har angett i fältet **Standardspråk** är det enda språk som du kommer att stödja för den här domänen, eller om det är standardspråket när du har lokaliserat platsen till ytterligare språk, rekommenderar vi att du lämnar det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="33e5d-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="33e5d-135">När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="33e5d-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="33e5d-136">Du kan också använda det nedrullningsbara menyn längst upp till vänster på sidan för att komma åt de tilldelade produkterna efter kategori.</span><span class="sxs-lookup"><span data-stu-id="33e5d-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33e5d-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="33e5d-137">Additional resources</span></span>

[<span data-ttu-id="33e5d-138">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="33e5d-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="33e5d-139">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="33e5d-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="33e5d-140">Ställ in en kanal för onlinebutik</span><span class="sxs-lookup"><span data-stu-id="33e5d-140">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="33e5d-141">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="33e5d-141">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="33e5d-142">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="33e5d-142">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="33e5d-143">Överföring av URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="33e5d-143">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="33e5d-144">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="33e5d-144">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="33e5d-145">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="33e5d-145">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="33e5d-146">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="33e5d-146">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="33e5d-147">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="33e5d-147">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="33e5d-148">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="33e5d-148">Enable location-based store detection</span></span>](enable-store-detection.md)
