---
title: Översikt över sidor med produktinformation
description: Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e4a61383c790b63aa1c07f7004f264495171441a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792229"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="d5dbd-103">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="d5dbd-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d5dbd-104">Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d5dbd-105">En PDP innehåller detaljerad information om en produkt och kunder kan välja produktalternativ som storlek, stil och färg.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-105">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="d5dbd-106">En PDP ska visa all produktinformation som en kund behöver för att fatta ett köpbeslut.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-106">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="d5dbd-107">Illustrationen nedan visar ett exempel på en PDP.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-107">The following illustration shows an example of a PDP.</span></span>

![Exempel på en sida med produktinformation](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="d5dbd-109">Moduler för sidhuvud och sidfot</span><span class="sxs-lookup"><span data-stu-id="d5dbd-109">Header and footer modules</span></span>

<span data-ttu-id="d5dbd-110">Den övre delen av PDP har en rubrik som visar alla produktkategorier och andra sidor som återförsäljaren vill att kunderna ska bläddra i.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-110">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="d5dbd-111">Sidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för kunderna.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-111">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="d5dbd-112">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="d5dbd-112">Buy box module</span></span>

<span data-ttu-id="d5dbd-113">Den viktigaste modulen på ett PDP är modulen för inköpsruta som visas som det första objektet i huvudavsnittet på sidan.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-113">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="d5dbd-114">En modul för inköpsruta innehåller viktig produktinformation, till exempel produktnamn, produktbeskrivning, produktpris, produktbilder och produktklassificeringar.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-114">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="d5dbd-115">Med modulen inköpsruta kan kunden välja produktalternativ (t.ex. storlek, stil och färg) och lägga till produkten i vagnen.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-115">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="d5dbd-116">Kunden kan också köpa produkten online och välja den i en butik.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-116">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="d5dbd-117">Modulerna köpa online och hämta i butik använder integration med Bing Maps API:er (Application Programming Interfaces) för att hitta närliggande butiker eller butiker på en annan plats som kunden anger.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-117">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="d5dbd-118">En modul för inköpsruta kräver ett produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-118">A buy box module requires a product ID.</span></span> <span data-ttu-id="d5dbd-119">Detta ID hämtas från sidans kontext.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-119">This ID is derived from the page context.</span></span> <span data-ttu-id="d5dbd-120">Om en modul för inköpsruta läggs till på en sida där sidkontexten inte innehåller något produkt-ID, återges informationen inte på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-120">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="d5dbd-121">Modul för produktspecifikationer</span><span class="sxs-lookup"><span data-stu-id="d5dbd-121">Product specifications module</span></span>

<span data-ttu-id="d5dbd-122">Modulen för produktspecifikationer kan användas för att visa mer information om produkten.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-122">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="d5dbd-123">Dessa detaljer hämtas från produktattribut i handel.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-123">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="d5dbd-124">Modulen produktspecifikationer visar alla attribut där egenskapen **synlig** är inställd på **sant**.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-124">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="d5dbd-125">Det kräver ett produkt-ID för att hämta produktattribut.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-125">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="d5dbd-126">Rekommendationsmodul</span><span class="sxs-lookup"><span data-stu-id="d5dbd-126">Recommendations module</span></span>

<span data-ttu-id="d5dbd-127">Rekommendationsmodulen är en viktig modul på en PDP.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-127">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="d5dbd-128">Medan kunder bläddrar efter produkter, bör fler produktalternativ presenteras för dem, så att de kan hitta rätt produkter och göra inköp.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-128">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="d5dbd-129">Rekommendationer hjälper kunder att enkelt hitta relaterat innehåll och fortsätta att handla.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-129">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="d5dbd-130">Det finns olika typer av rekommendationslistor:</span><span class="sxs-lookup"><span data-stu-id="d5dbd-130">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="d5dbd-131">Listan **personer gillar också** baseras på maskinutbildning.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-131">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="d5dbd-132">Den använder transaktionshistorik för andra kunder för att ge rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-132">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="d5dbd-133">Den här listan genereras av rekommendationstjänsten och liknar listan "kunder som köpt detta har också köpt...".</span><span class="sxs-lookup"><span data-stu-id="d5dbd-133">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="d5dbd-134">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-134">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="d5dbd-135">En **relaterad** lista kan konfigureras för en produkt i Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-135">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="d5dbd-136">För till exempel en handväska i brunt läder kan flera handväskor som är läderbaserade eller utformade för resor konfigureras för den relaterade listan.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-136">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="d5dbd-137">Andra typer av relaterade listor, till exempel **tillbehör** och **Fler som den här**, kan också konfigureras i Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-137">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="d5dbd-138">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-138">A product ID is required to generate this list.</span></span> <span data-ttu-id="d5dbd-139">Om den läggs till på en startsida, där sidkontexten inte innehåller något produkt-ID, kommer listan att vara tom.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-139">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="d5dbd-140">Algoritmskapade rekommendationslistor, t.ex. **Trend**, **Bästsäljande** och **Ny** kan användas på PDP.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-140">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="d5dbd-141">Även om dessa listor kanske inte är direkt relaterade till produkten i PDP är de ett annat sätt att hjälpa kunderna att hitta produkter som kan vara intressanta för dem.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-141">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="d5dbd-142">Dessa typer av listor kräver inget produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-142">These types of lists don't require a product ID.</span></span> <span data-ttu-id="d5dbd-143">De är generiska listor som skapas baserat på köpmönster på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-143">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="d5dbd-144">Redaktionella listor är manuellt granskade listor.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-144">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="d5dbd-145">En återförsäljare kan till exempel välja att manuellt granska listor över produkter som den vill visa.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-145">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="d5dbd-146">Moduler för omdömen och moduler</span><span class="sxs-lookup"><span data-stu-id="d5dbd-146">Ratings and reviews modules</span></span>

<span data-ttu-id="d5dbd-147">Tre moduler kan användas för att visa och lägga till recensioner:</span><span class="sxs-lookup"><span data-stu-id="d5dbd-147">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="d5dbd-148">**Recensioner** – Den här modulen anger omdömen och recensioner visas omdömen och recensioner som andra kunder har gett.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-148">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="d5dbd-149">Kunder kan sortera och filtrera recensionerna.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-149">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="d5dbd-150">Den här modulen gör det också möjligt för kunder som eller som vill granska recensioner och rapportera problem.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-150">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="d5dbd-151">**Skriv recension** – i den här modulen kan kunderna skriva sina egna recensioner av en produkt.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-151">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="d5dbd-152">**Omdömeshistogram** – i den här modulen finns ett histogram över trender för omdömen för en produkt.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-152">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="d5dbd-153">Mer information finns i [Översikt över omdömen och recensioner](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5dbd-153">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="d5dbd-154">Marknadsföringsmoduler</span><span class="sxs-lookup"><span data-stu-id="d5dbd-154">Marketing modules</span></span>

<span data-ttu-id="d5dbd-155">Om marknadsföringsinnehållet är unikt för en viss produkt kan en marknadsföringsmodul läggas till i PDP.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-155">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="d5dbd-156">Du kan lägga till marknadsföringsmaterial i ett PDP genom att "berika" sidan.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-156">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="d5dbd-157">Mer information finns i [utöka en produktsida](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="d5dbd-157">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5dbd-158">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d5dbd-158">Additional resources</span></span>

[<span data-ttu-id="d5dbd-159">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="d5dbd-159">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="d5dbd-160">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="d5dbd-160">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="d5dbd-161">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="d5dbd-161">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="d5dbd-162">Utöka en produktdetaljsida</span><span class="sxs-lookup"><span data-stu-id="d5dbd-162">Enrich a product details page</span></span>](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
