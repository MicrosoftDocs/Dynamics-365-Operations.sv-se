---
title: Skapa en näthandelssajt
description: I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny näthandelssajt i webbplatsskaparen för Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf084f90d203d84c91ddf7c0d963780b895ef23d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963045"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="74bb6-103">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="74bb6-103">Create an e-commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="74bb6-104">I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny näthandelssajt i webbplatsskaparen för Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="74bb6-104">This topic describes the steps and information required to create a new e-commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="74bb6-105">När du licensierar Dynamics 365 Commerce-funktionerna etableras webbplatsskaparen med en startwebbplats som du kan använda som grund för din egen webbplats.</span><span class="sxs-lookup"><span data-stu-id="74bb6-105">When you license the Dynamics 365 Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="74bb6-106">Om du däremot vill börja från början eller om du vill skapa en andra plats måste du skapa en ny webbplats i redigeringsmiljön för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="74bb6-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="74bb6-107">Ställ in din webbplats</span><span class="sxs-lookup"><span data-stu-id="74bb6-107">Set up your site</span></span>

<span data-ttu-id="74bb6-108">Gör följande om du vill ställa in din webbplats.</span><span class="sxs-lookup"><span data-stu-id="74bb6-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="74bb6-109">Öppna miljön för webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="74bb6-109">Open the site builder environment.</span></span> <span data-ttu-id="74bb6-110">Du hittar en länk till webbplatsskaparen i Microsoft Lifecycle Services (LCS) på sidan miljöfunktioner för Commerce.</span><span class="sxs-lookup"><span data-stu-id="74bb6-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="74bb6-111">På startsidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="74bb6-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="74bb6-112">Ange följande information i dialogrutan **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="74bb6-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="74bb6-113">Fält</span><span class="sxs-lookup"><span data-stu-id="74bb6-113">Field</span></span>                               | <span data-ttu-id="74bb6-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="74bb6-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="74bb6-115">Webbplatsens namn</span><span class="sxs-lookup"><span data-stu-id="74bb6-115">Site name</span></span>                           | <span data-ttu-id="74bb6-116">Ange visningsnamnet som ska användas för webbplatsen i webbplatsredigeringsmiljön.</span><span class="sxs-lookup"><span data-stu-id="74bb6-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="74bb6-117">Det här namnet visas bara i redigeringsmiljön och kommer inte att visas för kunderna.</span><span class="sxs-lookup"><span data-stu-id="74bb6-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="74bb6-118">Webbplatsadministratörens säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="74bb6-118">Site administrator's security group</span></span> | <span data-ttu-id="74bb6-119">Ange den säkerhetsgrupp för Microsoft Azure Active Directory (Azure AD) som hanterar användare med rollen webbplatsadministratör på den här webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="74bb6-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="74bb6-120">Standardkanal (driftenhetsnummer)</span><span class="sxs-lookup"><span data-stu-id="74bb6-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="74bb6-121">Välj den onlinebutik som den här webbplatsen ska fungera som webbskyltfönster för.</span><span class="sxs-lookup"><span data-stu-id="74bb6-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="74bb6-122">Om du vill att din näthandelssajt ska stödja flera olika onlinebutiker måste du associera butikerna med din webbplats under **Webbplatsinställningar** efter det att webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="74bb6-122">If you want your e-commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="74bb6-123">Standardspråk</span><span class="sxs-lookup"><span data-stu-id="74bb6-123">Default language</span></span>                            | <span data-ttu-id="74bb6-124">Ange standardspråket för den här onlinebutiken och marknaden.</span><span class="sxs-lookup"><span data-stu-id="74bb6-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="74bb6-125">En onlinebutik har stöd för flera språk.</span><span class="sxs-lookup"><span data-stu-id="74bb6-125">An online store can support multiple languages.</span></span> <span data-ttu-id="74bb6-126">Om du vill stödja flera språk för den här onlinebutiken eller en annan onlinebutik kan du konfigurera stödet i **platsinställningar** efter att webbplatsen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="74bb6-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="74bb6-127">Domän</span><span class="sxs-lookup"><span data-stu-id="74bb6-127">Domain</span></span>                              | <span data-ttu-id="74bb6-128">Välj ett domännamn som ska fungera som domän för denna onlinebutik.</span><span class="sxs-lookup"><span data-stu-id="74bb6-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="74bb6-129">Om du inte har konfigurerat några domäner i LCS kan du lämna det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="74bb6-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="74bb6-130">När din domän har konfigurerats i LCS måste du lägga till den i din onlinebutik i **webbplatsinställningarna**.</span><span class="sxs-lookup"><span data-stu-id="74bb6-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="74bb6-131">Sökväg</span><span class="sxs-lookup"><span data-stu-id="74bb6-131">Path</span></span>                              | <span data-ttu-id="74bb6-132">När din webbplats har stöd för mer än ett språk för ett givet domännamn, använder du sökvägsfältet för att skapa en unik webbplats-URL för den domänen och språkkombinationen.</span><span class="sxs-lookup"><span data-stu-id="74bb6-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="74bb6-133">Om det språk som du har angett i fältet **Standardspråk** är det enda språk som du kommer att stödja för den här domänen, eller om det är standardspråket när du har lokaliserat platsen till ytterligare språk, rekommenderar vi att du lämnar det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="74bb6-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="74bb6-134">När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="74bb6-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="74bb6-135">Du kan också använda det nedrullningsbara menyn längst upp till vänster på sidan för att komma åt de tilldelade produkterna efter kategori.</span><span class="sxs-lookup"><span data-stu-id="74bb6-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74bb6-136">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="74bb6-136">Additional resources</span></span>

[<span data-ttu-id="74bb6-137">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="74bb6-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="74bb6-138">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="74bb6-138">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="74bb6-139">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="74bb6-139">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="74bb6-140">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="74bb6-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="74bb6-141">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="74bb6-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="74bb6-142">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="74bb6-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="74bb6-143">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="74bb6-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="74bb6-144">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="74bb6-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="74bb6-145">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="74bb6-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="74bb6-146">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="74bb6-146">Enable location-based store detection</span></span>](enable-store-detection.md)
