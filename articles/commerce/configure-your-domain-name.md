---
title: Konfigurera ditt domännamn
description: I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelssajt.
author: psimolin
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
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8b7bc322b1a42190d5eec99f89a34025c34ba09f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220496"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="5222d-103">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="5222d-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5222d-104">I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="5222d-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="5222d-105">Lägg till domäner vid näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="5222d-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="5222d-106">Om du vill associera domäner med din Dynamics 365 Commerce-näthandelsmiljö initierar du näthandeln enligt beskrivningen i [distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="5222d-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="5222d-107">Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din näthandelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="5222d-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="5222d-108">I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="5222d-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="5222d-109">Flera domäner måste skiljas åt med semikolon.</span><span class="sxs-lookup"><span data-stu-id="5222d-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="5222d-110">På det här sättet konfigureras domänerna i alla nödvändiga komponenter för näthandel och de är klara att användas när du byter trafik från ditt nätverk för innehållsleverans (CDN) eller webbservern och riktar den mot näthandelsklienterna.</span><span class="sxs-lookup"><span data-stu-id="5222d-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="5222d-111">Lägg till domäner efter näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="5222d-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="5222d-112">Om du vill koppla nya domäner till din näthandelsmiljö efter näthandelsinitieringen måste du skicka in en tjänstebegäran.</span><span class="sxs-lookup"><span data-stu-id="5222d-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5222d-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5222d-113">Additional resources</span></span>

[<span data-ttu-id="5222d-114">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="5222d-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="5222d-115">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="5222d-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5222d-116">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="5222d-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5222d-117">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="5222d-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5222d-118">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="5222d-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="5222d-119">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="5222d-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="5222d-120">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="5222d-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5222d-121">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="5222d-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="5222d-122">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="5222d-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="5222d-123">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="5222d-123">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]