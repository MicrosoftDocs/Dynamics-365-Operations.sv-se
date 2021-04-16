---
title: Översikt över standardkategorilandningssida och sida för sökresultat
description: Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Dynamics 365 Commerce.
author: ashishmsft
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f380f3f56727d927d7cd328fef3c9d999afa2873
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794359"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a><span data-ttu-id="f2063-103">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="f2063-103">Default category landing page and search results page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2063-104">Det här ämnet ger en överblick över målsidan för standardkategori och sökresultatsida i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2063-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="f2063-105">Standardlandningssida för kategori</span><span class="sxs-lookup"><span data-stu-id="f2063-105">Default category landing page</span></span>

<span data-ttu-id="f2063-106">Standardlandningssidan för kategori är den sida som webbplatsanvändarna normalt använder när de väljer en kategori i navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f2063-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="f2063-107">På kategorisidan kan du bläddra och du kan också sortera och justera de kategoriserade produkterna.</span><span class="sxs-lookup"><span data-stu-id="f2063-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Standardlandningssida för kategori](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="f2063-109">Den övre delen av startsidan har en rubrik som visar alla produktkategorier och andra sidor som inköpschefen har kategoriserat.</span><span class="sxs-lookup"><span data-stu-id="f2063-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="f2063-110">Konfigurationen görs som en del av konfigurationen av kanalens navigeringshierarki.</span><span class="sxs-lookup"><span data-stu-id="f2063-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="f2063-111">Startsidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för köpare.</span><span class="sxs-lookup"><span data-stu-id="f2063-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="f2063-112">Följande komponenter är nödvändiga för en kategori:</span><span class="sxs-lookup"><span data-stu-id="f2063-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="f2063-113">**Produkt placeringspaneler** visar de produkter som inköpschefen har definierat i en kategori som en del av konfigurationen av navigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="f2063-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="f2063-114">**Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar.</span><span class="sxs-lookup"><span data-stu-id="f2063-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="f2063-115">Inköpschefen konfigurerar dem som en del av konfigurationen av metadata som är relaterade till kanalkategorier och produktattribut.</span><span class="sxs-lookup"><span data-stu-id="f2063-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="f2063-116">**Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna.</span><span class="sxs-lookup"><span data-stu-id="f2063-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="f2063-117">Som standard är följande sorteringsalternativ tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f2063-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="f2063-118">Pris – lågt till högt</span><span class="sxs-lookup"><span data-stu-id="f2063-118">Price – low to high</span></span>
    - <span data-ttu-id="f2063-119">Pris – högt till lågt</span><span class="sxs-lookup"><span data-stu-id="f2063-119">Price – high to low</span></span>
    - <span data-ttu-id="f2063-120">Produktnamn – \[A-Ö\]</span><span class="sxs-lookup"><span data-stu-id="f2063-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="f2063-121">Produktnamn – \[Ö-A\]</span><span class="sxs-lookup"><span data-stu-id="f2063-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="f2063-122">Värderingar – låg till hög</span><span class="sxs-lookup"><span data-stu-id="f2063-122">Ratings – low to high</span></span>
    - <span data-ttu-id="f2063-123">Värderingar – hög till låg</span><span class="sxs-lookup"><span data-stu-id="f2063-123">Ratings – high to low</span></span>

- <span data-ttu-id="f2063-124">**Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.</span><span class="sxs-lookup"><span data-stu-id="f2063-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="f2063-125">**Totalt antal** anger det totala antalet produkter som har definierats i en kategori.</span><span class="sxs-lookup"><span data-stu-id="f2063-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="f2063-126">Utöka en kategorilandningssida</span><span class="sxs-lookup"><span data-stu-id="f2063-126">Enrich a category landing page</span></span>

<span data-ttu-id="f2063-127">Om du vill att en kategorilandningssida ska ha en mer skräddarsydd upplevelse för en viss kategori, kan du "utöka" kategorilandningssidan för den kategorin.</span><span class="sxs-lookup"><span data-stu-id="f2063-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="f2063-128">Du kan till exempel lägga till en marknadsföringsvideo och vissa kategoriberättande för att få köparens uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="f2063-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="f2063-129">Mer information finns i [utöka en kategorilandningssida](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="f2063-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Utöka en kategorilandningssida](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="f2063-131">Automatiskt föreslå och sökresultatsidor</span><span class="sxs-lookup"><span data-stu-id="f2063-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="f2063-132">Webbplatsanvändare kan utforska en webbplats antingen genom att gå till en kategori från navigeringshierarkin eller genom att ange en sökterm i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="f2063-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="f2063-133">Så snart användarna börjar skriva i sökfältet, kommer de att uppleva de fördjupade automatiska förslag som föreslår söktermer.</span><span class="sxs-lookup"><span data-stu-id="f2063-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="f2063-134">Här följer några av de typer av förslag som kan visas:</span><span class="sxs-lookup"><span data-stu-id="f2063-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="f2063-135">**Nyckelord** används för att hitta artiklar i alla produkter som är utvalda för kanalen.</span><span class="sxs-lookup"><span data-stu-id="f2063-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="f2063-136">**Produkter** tillhandahåller direktlänkar till sidan med produktinformation.</span><span class="sxs-lookup"><span data-stu-id="f2063-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="f2063-137">**Omfattningsförslag för kategorisökning** anger olika kategorier och låter användare söka efter nyckelordet i en viss kategori.</span><span class="sxs-lookup"><span data-stu-id="f2063-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![Integrerade automatiska förslag](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="f2063-139">När användarna väljer ett av nyckelorden eller omfattande förslagen på kategorisökning, eller när det inte finns några förslag på sökvillkoren som de anger, omdirigeras de till en sökresultatsida.</span><span class="sxs-lookup"><span data-stu-id="f2063-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="f2063-140">Användarna kan sedan bläddra, sortera och finjustera listan med sökresultat för att hitta önskad artikel.</span><span class="sxs-lookup"><span data-stu-id="f2063-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Landningssida för sökning](./media/SearchLanding.png)

<span data-ttu-id="f2063-142">Följande komponenter är nödvändiga för en sökresultatsida:</span><span class="sxs-lookup"><span data-stu-id="f2063-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="f2063-143">**Produktplaceringspaneler** visar produkterna för användarens sökning.</span><span class="sxs-lookup"><span data-stu-id="f2063-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="f2063-144">Som standard sorteras dessa paneler efter den molndrivna sökrelevans som används för användarsökningen.</span><span class="sxs-lookup"><span data-stu-id="f2063-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="f2063-145">**Förfiningar och alternativsammanfattning** är filter som anger antal och som kan användas för att förfina artiklar.</span><span class="sxs-lookup"><span data-stu-id="f2063-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="f2063-146">Inköpschefen konfigurerar dem som en del av konfigurationen av metadata för "kanalkategorier och produktattribut".</span><span class="sxs-lookup"><span data-stu-id="f2063-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="f2063-147">**Sorteringsalternativen** används av besökare på webbplatsen för att sortera produkterna.</span><span class="sxs-lookup"><span data-stu-id="f2063-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="f2063-148">Som standard är följande sorteringsalternativ tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="f2063-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="f2063-149">Pris – lågt till högt</span><span class="sxs-lookup"><span data-stu-id="f2063-149">Price – low to high</span></span>
    - <span data-ttu-id="f2063-150">Pris – högt till lågt</span><span class="sxs-lookup"><span data-stu-id="f2063-150">Price – high to low</span></span>
    - <span data-ttu-id="f2063-151">Produktnamn – \[A-Ö\]</span><span class="sxs-lookup"><span data-stu-id="f2063-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="f2063-152">Produktnamn – \[Ö-A\]</span><span class="sxs-lookup"><span data-stu-id="f2063-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="f2063-153">Värderingar – låg till hög</span><span class="sxs-lookup"><span data-stu-id="f2063-153">Ratings – low to high</span></span>
    - <span data-ttu-id="f2063-154">Värderingar – hög till låg</span><span class="sxs-lookup"><span data-stu-id="f2063-154">Ratings – high to low</span></span>
    - <span data-ttu-id="f2063-155">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="f2063-155">Default</span></span>

- <span data-ttu-id="f2063-156">**Sidnumrering** gör att webbplatsbesökarna kan flytta från en sida med kategoriserade produktresultat till en annan sida.</span><span class="sxs-lookup"><span data-stu-id="f2063-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="f2063-157">**Totalt antal** anger det totala antalet produkter som har definierats i en kategori som matchar sökkriterierna.</span><span class="sxs-lookup"><span data-stu-id="f2063-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

>[!NOTE]
><span data-ttu-id="f2063-158">De här molndrivna sökfunktionerna är tillgängliga från och med version 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="f2063-158">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="f2063-159">Se till att under **Handelsparametrar > Konfigurationsparametrar** finns en post för "ProductSearch.UseAzureSearch inställd på true".</span><span class="sxs-lookup"><span data-stu-id="f2063-159">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="f2063-160">![Konfigurationsparametrar för med molndriven sökning](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="f2063-160">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2063-161">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f2063-161">Additional resources</span></span>

[<span data-ttu-id="f2063-162">Översikt över molnbaserade sökningar</span><span class="sxs-lookup"><span data-stu-id="f2063-162">Cloud-powered search overview</span></span>](cloud-powered-search-overview.md)

[<span data-ttu-id="f2063-163">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="f2063-163">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="f2063-164">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="f2063-164">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="f2063-165">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="f2063-165">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="f2063-166">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="f2063-166">Account management pages overview</span></span>](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]