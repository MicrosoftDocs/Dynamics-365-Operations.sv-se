---
title: Konfigurera ditt domännamn
description: I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.
author: psimolin
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
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2ad9ca3aee21301ef6d830d7b29982a45cd53f60
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096830"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="bd8ff-103">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="bd8ff-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bd8ff-104">I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="bd8ff-105">Lägg till domäner vid näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="bd8ff-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="bd8ff-106">Om du vill associera domäner med näthandelsmiljön initierar du e-handel enligt beskrivningen i [distribuera en ny näthandelsplats](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="bd8ff-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="bd8ff-107">Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din e-handelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="bd8ff-108">I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="bd8ff-109">Flera domäner måste skiljas åt med semikolon.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="bd8ff-110">På det här sättet konfigureras domänerna i alla nödvändiga komponenter för e-handel och de är klara att användas när du byter trafik från ditt innehållsleveransnätverk (CDN) eller webbservern och pekar den på näthandelns klientdel.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="bd8ff-111">Lägg till domäner efter näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="bd8ff-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="bd8ff-112">Om du vill koppla nya domäner till din e-handelsmiljö efter initieringen av e-handel måste du skicka en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="bd8ff-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd8ff-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bd8ff-113">Additional resources</span></span>

[<span data-ttu-id="bd8ff-114">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="bd8ff-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="bd8ff-115">Ställ in en kanal för onlinebutik</span><span class="sxs-lookup"><span data-stu-id="bd8ff-115">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="bd8ff-116">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="bd8ff-116">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="bd8ff-117">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="bd8ff-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="bd8ff-118">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="bd8ff-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="bd8ff-119">Överföring av URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="bd8ff-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="bd8ff-120">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="bd8ff-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="bd8ff-121">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="bd8ff-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="bd8ff-122">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="bd8ff-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="bd8ff-123">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="bd8ff-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="bd8ff-124">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="bd8ff-124">Enable location-based store detection</span></span>](enable-store-detection.md)
