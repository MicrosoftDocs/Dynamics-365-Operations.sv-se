---
title: Översikt över standardkategorilandningssida och sida för sökresultat
description: Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3835502c33fbc63f68f2d6350d805badb3891568
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697300"
---
# <a name="overview-of-default-category-landing-page-and-search-results-page"></a><span data-ttu-id="f5472-103">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="f5472-103">Overview of default category landing page and search results page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f5472-104">Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f5472-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="f5472-105">Standardlandningssida för kategori</span><span class="sxs-lookup"><span data-stu-id="f5472-105">Default category landing page</span></span>

<span data-ttu-id="f5472-106">Standardlandningssidan för kategori är den sida som webbplatsanvändarna normalt använder när de väljer en kategori i navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f5472-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="f5472-107">På kategorisidan kan du bläddra och du kan också sortera och justera de kategoriserade produkterna.</span><span class="sxs-lookup"><span data-stu-id="f5472-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Standardlandningssida för kategori](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="f5472-109">Den övre delen av startsidan har en rubrik som visar alla produktkategorier och andra sidor som inköpschefen har kategoriserat.</span><span class="sxs-lookup"><span data-stu-id="f5472-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="f5472-110">Konfigurationen görs som en del av konfigurationen av kanalens navigeringshierarki.</span><span class="sxs-lookup"><span data-stu-id="f5472-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="f5472-111">Startsidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för köpare.</span><span class="sxs-lookup"><span data-stu-id="f5472-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="f5472-112">Följande komponenter är nödvändiga för en kategori:</span><span class="sxs-lookup"><span data-stu-id="f5472-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="f5472-113">**Produkt placeringspaneler** visar de produkter som inköpschefen har definierat i en kategori som en del av konfigurationen av navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f5472-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="f5472-114">**Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar.</span><span class="sxs-lookup"><span data-stu-id="f5472-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="f5472-115">Inköpschefen konfigurerar dem som en del av konfigurationen av metadata som är relaterade till kanalkategorier och produktattribut.</span><span class="sxs-lookup"><span data-stu-id="f5472-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="f5472-116">**Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna.</span><span class="sxs-lookup"><span data-stu-id="f5472-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="f5472-117">Som standard är följande sorteringsalternativ tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f5472-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="f5472-118">Pris – lågt till högt</span><span class="sxs-lookup"><span data-stu-id="f5472-118">Price – low to high</span></span>
    - <span data-ttu-id="f5472-119">Pris – högt till lågt</span><span class="sxs-lookup"><span data-stu-id="f5472-119">Price – high to low</span></span>
    - <span data-ttu-id="f5472-120">Produktnamn – \[A-Ö\]</span><span class="sxs-lookup"><span data-stu-id="f5472-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="f5472-121">Produktnamn – \[Ö-A\]</span><span class="sxs-lookup"><span data-stu-id="f5472-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="f5472-122">Värderingar – låg till hög</span><span class="sxs-lookup"><span data-stu-id="f5472-122">Ratings – low to high</span></span>
    - <span data-ttu-id="f5472-123">Värderingar – hög till låg</span><span class="sxs-lookup"><span data-stu-id="f5472-123">Ratings – high to low</span></span>

- <span data-ttu-id="f5472-124">**Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.</span><span class="sxs-lookup"><span data-stu-id="f5472-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="f5472-125">**Totalt antal** anger det totala antalet produkter som har definierats i en kategori.</span><span class="sxs-lookup"><span data-stu-id="f5472-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="f5472-126">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="f5472-126">Enrich a category landing page</span></span>

<span data-ttu-id="f5472-127">Om du vill att en kategorilandningssida ska ha en mer skräddarsydd upplevelse för en viss kategori, kan du "utöka" kategorilandningssidan för den kategorin.</span><span class="sxs-lookup"><span data-stu-id="f5472-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="f5472-128">Du kan till exempel lägga till en marknadsföringsvideo och vissa kategoriberättande för att få köparens uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="f5472-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="f5472-129">Mer information finns i [utöka en kategorilandningssida](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="f5472-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="f5472-131">Automatiskt föreslå och sökresultatsidor</span><span class="sxs-lookup"><span data-stu-id="f5472-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="f5472-132">Webbplatsanvändare kan utforska en webbplats antingen genom att gå till en kategori från navigeringshierarkin eller genom att ange en sökterm i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="f5472-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="f5472-133">Så snart användarna börjar skriva i sökfältet, kommer de att uppleva de fördjupade automatiska förslag som föreslår söktermer.</span><span class="sxs-lookup"><span data-stu-id="f5472-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="f5472-134">Här följer några av de typer av förslag som kan visas:</span><span class="sxs-lookup"><span data-stu-id="f5472-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="f5472-135">**Nyckelord** används för att hitta artiklar i alla produkter som är utvalda för kanalen.</span><span class="sxs-lookup"><span data-stu-id="f5472-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="f5472-136">**Produkter** tillhandahåller direktlänkar till sidan med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="f5472-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="f5472-137">**Omfattningsförslag för kategorisökning** anger olika kategorier och låter användare söka efter nyckelordet i en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="f5472-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![Integrerade automatiska förslag](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="f5472-139">När användarna väljer ett av nyckelorden eller omfattande förslagen på kategorisökning, eller när det inte finns några förslag på sökvillkoren som de anger, omdirigeras de till en sökresultatsida.</span><span class="sxs-lookup"><span data-stu-id="f5472-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="f5472-140">Användarna kan sedan bläddra, sortera och finjustera listan med sökresultat för att hitta önskad artikel.</span><span class="sxs-lookup"><span data-stu-id="f5472-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Landningssida för sökning](./media/SearchLanding.png)

<span data-ttu-id="f5472-142">Följande komponenter är nödvändiga för en sökresultatsida:</span><span class="sxs-lookup"><span data-stu-id="f5472-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="f5472-143">**Produktplaceringspaneler** visar produkterna för användarens sökning.</span><span class="sxs-lookup"><span data-stu-id="f5472-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="f5472-144">Som standard sorteras dessa paneler efter den molndrivna sökrelevans som används för användarsökningen.</span><span class="sxs-lookup"><span data-stu-id="f5472-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="f5472-145">**Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar.</span><span class="sxs-lookup"><span data-stu-id="f5472-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="f5472-146">Inköpschefen konfigurerar dem som en del av konfigurationen av metadata för "kanalkategorier och produktattribut".</span><span class="sxs-lookup"><span data-stu-id="f5472-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="f5472-147">**Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna.</span><span class="sxs-lookup"><span data-stu-id="f5472-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="f5472-148">Som standard är följande sorteringsalternativ tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f5472-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="f5472-149">Pris – lågt till högt</span><span class="sxs-lookup"><span data-stu-id="f5472-149">Price – low to high</span></span>
    - <span data-ttu-id="f5472-150">Pris – högt till lågt</span><span class="sxs-lookup"><span data-stu-id="f5472-150">Price – high to low</span></span>
    - <span data-ttu-id="f5472-151">Produktnamn – \[A-Ö\]</span><span class="sxs-lookup"><span data-stu-id="f5472-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="f5472-152">Produktnamn – \[Ö-A\]</span><span class="sxs-lookup"><span data-stu-id="f5472-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="f5472-153">Värderingar – låg till hög</span><span class="sxs-lookup"><span data-stu-id="f5472-153">Ratings – low to high</span></span>
    - <span data-ttu-id="f5472-154">Värderingar – hög till låg</span><span class="sxs-lookup"><span data-stu-id="f5472-154">Ratings – high to low</span></span>
    - <span data-ttu-id="f5472-155">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="f5472-155">Default</span></span>

- <span data-ttu-id="f5472-156">**Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.</span><span class="sxs-lookup"><span data-stu-id="f5472-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="f5472-157">**Totalt antal** anger det totala antalet produkter som har definierats i en kategori som matchar sökkriterierna.</span><span class="sxs-lookup"><span data-stu-id="f5472-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5472-158">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f5472-158">Additional resources</span></span>

[<span data-ttu-id="f5472-159">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="f5472-159">Overview of the home page</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="f5472-160">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="f5472-160">Overview of product details pages</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="f5472-161">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="f5472-161">Overview of cart and checkout pages</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="f5472-162">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="f5472-162">Overview of account management pages</span></span>](quick-tour-account-management.md)

