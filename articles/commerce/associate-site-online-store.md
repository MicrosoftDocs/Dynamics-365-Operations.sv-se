---
title: Associera en Dynamics 365 Commerce-webbplats med en onlinekanal
description: I det här avsnittet beskrivs hur du binder Microsoft Dynamics 365 Commerce-webbplats till en eller flera onlinebutiker.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb39b54e45e387067720dcbc5d9ccffbf8bf08b4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211532"
---
# <a name="associate-a-dynamics-365-commerce-site-with-an-online-channel"></a><span data-ttu-id="67f85-103">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="67f85-103">Associate a Dynamics 365 Commerce site with an online channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="67f85-104">I det här avsnittet beskrivs hur du binder Microsoft Dynamics 365 Commerce-webbplats till en eller flera onlinebutiker.</span><span class="sxs-lookup"><span data-stu-id="67f85-104">This topic explains how to bind your Microsoft Dynamics 365 Commerce site to one or more online stores.</span></span> 

<span data-ttu-id="67f85-105">När du har etablerat din Dynamics 365 Commerce-näthandelsmiljö med hjälp av Microsoft Dynamics Lifecycle Services-portalen (LCS) är du redo att upprätta din första näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="67f85-105">After you've provisioned your Dynamics 365 Commerce e-commerce environment by using the Microsoft Dynamics Lifecycle Services (LCS) portal, you're ready to establish your first e-commerce website.</span></span> <span data-ttu-id="67f85-106">Som en del av den första webbplatsen som skapas associerar du webbplatsen till en onlinebutik som skapats tidigare.</span><span class="sxs-lookup"><span data-stu-id="67f85-106">As part of the initial site creation, you associate the site with an online store that was previously created.</span></span> <span data-ttu-id="67f85-107">Detta steg binder webbplatsen till en onlinekanal och låter webbplatsen visa navigeringshierarki, produkter, kategorier, priser, leveransalternativ och allt annat som du har definierat i onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="67f85-107">This step binds the site to an online channel and lets the site show the navigation hierarchy, products, categories, prices, shipping options, and everything else that you defined in the online store.</span></span>

<span data-ttu-id="67f85-108">Om du vill skapa en ny webbplats och koppla en onlinebutik till den väljer du länken för webbplatsredigeringsmiljön i LCS.</span><span class="sxs-lookup"><span data-stu-id="67f85-108">To establish a new site and associate an online store with it, in LCS, select the link for the site authoring environment.</span></span> <span data-ttu-id="67f85-109">Sedan på sidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.</span><span class="sxs-lookup"><span data-stu-id="67f85-109">Then, on the page for the site authoring environment, select **New site**.</span></span> <span data-ttu-id="67f85-110">I dialogrutan **Ny webbplats** måste du ange en grundläggande information om webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="67f85-110">In the **New site** dialog box, you must provide some basic information about your site.</span></span> <span data-ttu-id="67f85-111">En fullständig förklaring av den information som du måste tillhandahålla finns i [Skapa en ny näthandelssajt](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="67f85-111">For a complete explanation of the information that you must provide, see [Create a new e-commerce site](create-ecommerce-site.md).</span></span>

<span data-ttu-id="67f85-112">När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="67f85-112">After your site is created, you can verify that it's associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="67f85-113">Du kan också använda det nedrullningsbara fältet längst upp till vänster på sidan för att komma åt produkterna efter kategori.</span><span class="sxs-lookup"><span data-stu-id="67f85-113">You can also use the drop-down field in the upper left of the page to access the products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67f85-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="67f85-114">Additional resources</span></span>

[<span data-ttu-id="67f85-115">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="67f85-115">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="67f85-116">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="67f85-116">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="67f85-117">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="67f85-117">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="67f85-118">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="67f85-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="67f85-119">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="67f85-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="67f85-120">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="67f85-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="67f85-121">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="67f85-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="67f85-122">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="67f85-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="67f85-123">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="67f85-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="67f85-124">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="67f85-124">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]