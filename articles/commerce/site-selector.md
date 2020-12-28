---
title: Modul för webbplatsväljare
description: Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b4e5f715efcac7f883df99508d282db904be0d80
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665233"
---
# <a name="site-selector-module"></a><span data-ttu-id="63227-103">Modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="63227-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="63227-104">Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="63227-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="63227-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="63227-105">Overview</span></span>

<span data-ttu-id="63227-106">Om ett företag har olika webbplatser på olika marknader, regioner och språk, behöver webbplatsanvändarna ett enkelt sätt att växla mellan platserna och välja sin föredragna webbplats att handla på.</span><span class="sxs-lookup"><span data-stu-id="63227-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="63227-107">I det här scenariot kan du använda modulen webbplatsväljare för att söka på flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="63227-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="63227-108">Modulen webbplatsväljare måste vara konfigurerad med en lista över platser (marknader, regioner eller språk) som webbplatsanvändarna kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="63227-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="63227-109">Modulen webbplatsväljare är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.</span><span class="sxs-lookup"><span data-stu-id="63227-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="63227-110">I följande bild visas ett exempel på en modul för webbplatsväljare som finns i rubriken på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="63227-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exempel på en modul för webbplatsväljare i rubriken till en webbplatssida](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="63227-112">Egenskaper för modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="63227-112">Site selector module properties</span></span>

| <span data-ttu-id="63227-113">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="63227-113">Property name</span></span> | <span data-ttu-id="63227-114">Värde</span><span class="sxs-lookup"><span data-stu-id="63227-114">Value</span></span>                 | <span data-ttu-id="63227-115">beskrivning</span><span class="sxs-lookup"><span data-stu-id="63227-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="63227-116">Rubrik</span><span class="sxs-lookup"><span data-stu-id="63227-116">Heading</span></span>       | <span data-ttu-id="63227-117">Text</span><span class="sxs-lookup"><span data-stu-id="63227-117">Text</span></span>                  | <span data-ttu-id="63227-118">Rubriken för modulen.</span><span class="sxs-lookup"><span data-stu-id="63227-118">The heading for the module.</span></span> |
| <span data-ttu-id="63227-119">Webbplatsalternativ</span><span class="sxs-lookup"><span data-stu-id="63227-119">Site options</span></span>  | <span data-ttu-id="63227-120">Namn, bild, URL</span><span class="sxs-lookup"><span data-stu-id="63227-120">Name, Image, URL</span></span>      | <span data-ttu-id="63227-121">Den här egenskapen anger ett namn, en länk till webbplatsens startsida och en valfri bild som ska visas för varje webbplats som ingår i modulen.</span><span class="sxs-lookup"><span data-stu-id="63227-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="63227-122">Bilden kan vara en flagga eller en del representation av en marknad, region eller nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="63227-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="63227-123">Lägg till modulen för webbplatsväljare till en sida</span><span class="sxs-lookup"><span data-stu-id="63227-123">Add a site selector module to a page</span></span>

<span data-ttu-id="63227-124">Modulen webbplatsväljare kan läggas till i [huvudmodul](author-header-module.md) under platsen för webbplatsväljare.</span><span class="sxs-lookup"><span data-stu-id="63227-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="63227-125">När den har lagts till kan du definiera modulens rubrik och webbplatsalternativ.</span><span class="sxs-lookup"><span data-stu-id="63227-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63227-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="63227-126">Additional resources</span></span>

[<span data-ttu-id="63227-127">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="63227-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="63227-128">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="63227-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="63227-129">Modul för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="63227-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="63227-130">Modul för navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="63227-130">Navigation menu module</span></span>](nav-menu-module.md)
