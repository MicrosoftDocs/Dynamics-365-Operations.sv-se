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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e24590d4a8f172809704aab0d761f6db0fb0e11b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234351"
---
# <a name="site-selector-module"></a><span data-ttu-id="b081a-103">Modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="b081a-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b081a-104">Det här avsnittet handlar om modulen för webbplatsväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b081a-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b081a-105">Om ett företag har olika webbplatser på olika marknader, regioner och språk, behöver webbplatsanvändarna ett enkelt sätt att växla mellan platserna och välja sin föredragna webbplats att handla på.</span><span class="sxs-lookup"><span data-stu-id="b081a-105">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="b081a-106">I det här scenariot kan du använda modulen webbplatsväljare för att söka på flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="b081a-106">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="b081a-107">Modulen webbplatsväljare måste vara konfigurerad med en lista över platser (marknader, regioner eller språk) som webbplatsanvändarna kan bläddra i.</span><span class="sxs-lookup"><span data-stu-id="b081a-107">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="b081a-108">Modulen webbplatsväljare är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.</span><span class="sxs-lookup"><span data-stu-id="b081a-108">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="b081a-109">I följande bild visas ett exempel på en modul för webbplatsväljare som finns i rubriken på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="b081a-109">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exempel på en modul för webbplatsväljare i rubriken till en webbplatssida](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="b081a-111">Egenskaper för modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="b081a-111">Site selector module properties</span></span>

| <span data-ttu-id="b081a-112">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="b081a-112">Property name</span></span> | <span data-ttu-id="b081a-113">Värde</span><span class="sxs-lookup"><span data-stu-id="b081a-113">Value</span></span>                 | <span data-ttu-id="b081a-114">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b081a-114">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="b081a-115">Rubrik</span><span class="sxs-lookup"><span data-stu-id="b081a-115">Heading</span></span>       | <span data-ttu-id="b081a-116">Text</span><span class="sxs-lookup"><span data-stu-id="b081a-116">Text</span></span>                  | <span data-ttu-id="b081a-117">Rubriken för modulen.</span><span class="sxs-lookup"><span data-stu-id="b081a-117">The heading for the module.</span></span> |
| <span data-ttu-id="b081a-118">Webbplatsalternativ</span><span class="sxs-lookup"><span data-stu-id="b081a-118">Site options</span></span>  | <span data-ttu-id="b081a-119">Namn, bild, URL</span><span class="sxs-lookup"><span data-stu-id="b081a-119">Name, Image, URL</span></span>      | <span data-ttu-id="b081a-120">Den här egenskapen anger ett namn, en länk till webbplatsens startsida och en valfri bild som ska visas för varje webbplats som ingår i modulen.</span><span class="sxs-lookup"><span data-stu-id="b081a-120">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="b081a-121">Bilden kan vara en flagga eller en del representation av en marknad, region eller nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="b081a-121">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="b081a-122">Lägg till modulen för webbplatsväljare till en sida</span><span class="sxs-lookup"><span data-stu-id="b081a-122">Add a site selector module to a page</span></span>

<span data-ttu-id="b081a-123">Modulen webbplatsväljare kan läggas till i [huvudmodul](author-header-module.md) under platsen för webbplatsväljare.</span><span class="sxs-lookup"><span data-stu-id="b081a-123">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="b081a-124">När den har lagts till kan du definiera modulens rubrik och webbplatsalternativ.</span><span class="sxs-lookup"><span data-stu-id="b081a-124">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b081a-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b081a-125">Additional resources</span></span>

[<span data-ttu-id="b081a-126">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="b081a-126">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b081a-127">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="b081a-127">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="b081a-128">Modul för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="b081a-128">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="b081a-129">Modul för navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="b081a-129">Navigation menu module</span></span>](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]