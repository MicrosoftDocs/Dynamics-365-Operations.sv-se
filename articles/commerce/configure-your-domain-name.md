---
title: Konfigurera ditt domännamn
description: I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
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
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945546"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="383ad-103">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="383ad-103">Configure your domain name</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="383ad-104">I det här avsnittet beskrivs hur du konfigurerar ett domännamn för Microsoft Dynamics 365 näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="383ad-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="383ad-105">Lägg till domäner vid näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="383ad-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="383ad-106">Om du vill associera domäner med näthandelsmiljön initierar du e-handel enligt beskrivningen i [distribuera en ny näthandelsplats](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="383ad-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="383ad-107">Under initieringen uppmanas du att ange information som ska användas för att tillhandahålla din e-handelsmiljö.</span><span class="sxs-lookup"><span data-stu-id="383ad-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="383ad-108">I fältet **Värdnamn som stöds** lägger du till alla domäner som du planerar att använda i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="383ad-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="383ad-109">Flera domäner måste skiljas åt med semikolon.</span><span class="sxs-lookup"><span data-stu-id="383ad-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="383ad-110">På det här sättet konfigureras domänerna i alla nödvändiga komponenter för e-handel och de är klara att användas när du byter trafik från ditt innehållsleveransnätverk (CDN) eller webbservern och pekar den på näthandelns klientdel.</span><span class="sxs-lookup"><span data-stu-id="383ad-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="383ad-111">Lägg till domäner efter näthandelsinitiering</span><span class="sxs-lookup"><span data-stu-id="383ad-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="383ad-112">Om du vill koppla nya domäner till din e-handelsmiljö efter initieringen av e-handel måste du skicka en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="383ad-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="383ad-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="383ad-113">Additional resources</span></span>

[<span data-ttu-id="383ad-114">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="383ad-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="383ad-115">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="383ad-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="383ad-116">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="383ad-116">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="383ad-117">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="383ad-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="383ad-118">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="383ad-118">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="383ad-119">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="383ad-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="383ad-120">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="383ad-120">Enable location-based store detection</span></span>](enable-store-detection.md)
