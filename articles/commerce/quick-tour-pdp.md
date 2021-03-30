---
title: Översikt över sidor med produktinformation
description: Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 020c2a72515eb112adb33c6b58e3a5084339d040
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243850"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="cb277-103">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="cb277-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cb277-104">Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb277-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cb277-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="cb277-105">Overview</span></span>

<span data-ttu-id="cb277-106">En PDP innehåller detaljerad information om en produkt och kunder kan välja produktalternativ som storlek, stil och färg.</span><span class="sxs-lookup"><span data-stu-id="cb277-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="cb277-107">En PDP ska visa all produktinformation som en kund behöver för att fatta ett köpbeslut.</span><span class="sxs-lookup"><span data-stu-id="cb277-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="cb277-108">Illustrationen nedan visar ett exempel på en PDP.</span><span class="sxs-lookup"><span data-stu-id="cb277-108">The following illustration shows an example of a PDP.</span></span>

![Exempel på en sida med produktinformation](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="cb277-110">Moduler för sidhuvud och sidfot</span><span class="sxs-lookup"><span data-stu-id="cb277-110">Header and footer modules</span></span>

<span data-ttu-id="cb277-111">Den övre delen av PDP har en rubrik som visar alla produktkategorier och andra sidor som återförsäljaren vill att kunderna ska bläddra i.</span><span class="sxs-lookup"><span data-stu-id="cb277-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="cb277-112">Sidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för kunderna.</span><span class="sxs-lookup"><span data-stu-id="cb277-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="cb277-113">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="cb277-113">Buy box module</span></span>

<span data-ttu-id="cb277-114">Den viktigaste modulen på ett PDP är modulen för inköpsruta som visas som det första objektet i huvudavsnittet på sidan.</span><span class="sxs-lookup"><span data-stu-id="cb277-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="cb277-115">En modul för inköpsruta innehåller viktig produktinformation, till exempel produktnamn, produktbeskrivning, produktpris, produktbilder och produktklassificeringar.</span><span class="sxs-lookup"><span data-stu-id="cb277-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="cb277-116">Med modulen inköpsruta kan kunden välja produktalternativ (t.ex. storlek, stil och färg) och lägga till produkten i vagnen.</span><span class="sxs-lookup"><span data-stu-id="cb277-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="cb277-117">Kunden kan också köpa produkten online och välja den i en butik.</span><span class="sxs-lookup"><span data-stu-id="cb277-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="cb277-118">Modulerna köpa online och hämta i butik använder integration med Bing Maps API:er (Application Programming Interfaces) för att hitta närliggande butiker eller butiker på en annan plats som kunden anger.</span><span class="sxs-lookup"><span data-stu-id="cb277-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="cb277-119">En modul för inköpsruta kräver ett produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="cb277-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="cb277-120">Detta ID hämtas från sidans kontext.</span><span class="sxs-lookup"><span data-stu-id="cb277-120">This ID is derived from the page context.</span></span> <span data-ttu-id="cb277-121">Om en modul för inköpsruta läggs till på en sida där sidkontexten inte innehåller något produkt-ID, återges informationen inte på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="cb277-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="cb277-122">Modul för produktspecifikationer</span><span class="sxs-lookup"><span data-stu-id="cb277-122">Product specifications module</span></span>

<span data-ttu-id="cb277-123">Modulen för produktspecifikationer kan användas för att visa mer information om produkten.</span><span class="sxs-lookup"><span data-stu-id="cb277-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="cb277-124">Dessa detaljer hämtas från produktattribut i handel.</span><span class="sxs-lookup"><span data-stu-id="cb277-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="cb277-125">Modulen produktspecifikationer visar alla attribut där egenskapen **synlig** är inställd på **sant**.</span><span class="sxs-lookup"><span data-stu-id="cb277-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="cb277-126">Det kräver ett produkt-ID för att hämta produktattribut.</span><span class="sxs-lookup"><span data-stu-id="cb277-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="cb277-127">Rekommendationsmodul</span><span class="sxs-lookup"><span data-stu-id="cb277-127">Recommendations module</span></span>

<span data-ttu-id="cb277-128">Rekommendationsmodulen är en viktig modul på en PDP.</span><span class="sxs-lookup"><span data-stu-id="cb277-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="cb277-129">Medan kunder bläddrar efter produkter, bör fler produktalternativ presenteras för dem, så att de kan hitta rätt produkter och göra inköp.</span><span class="sxs-lookup"><span data-stu-id="cb277-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="cb277-130">Rekommendationer hjälper kunder att enkelt hitta relaterat innehåll och fortsätta att handla.</span><span class="sxs-lookup"><span data-stu-id="cb277-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="cb277-131">Det finns olika typer av rekommendationslistor:</span><span class="sxs-lookup"><span data-stu-id="cb277-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="cb277-132">Listan **personer gillar också** baseras på maskinutbildning.</span><span class="sxs-lookup"><span data-stu-id="cb277-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="cb277-133">Den använder transaktionshistorik för andra kunder för att ge rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="cb277-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="cb277-134">Den här listan genereras av rekommendationstjänsten och liknar listan "kunder som köpt detta har också köpt...".</span><span class="sxs-lookup"><span data-stu-id="cb277-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="cb277-135">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="cb277-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="cb277-136">En **relaterad** lista kan konfigureras för en produkt i Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb277-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="cb277-137">För till exempel en handväska i brunt läder kan flera handväskor som är läderbaserade eller utformade för resor konfigureras för den relaterade listan.</span><span class="sxs-lookup"><span data-stu-id="cb277-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="cb277-138">Andra typer av relaterade listor, till exempel **tillbehör** och **Fler som den här**, kan också konfigureras i Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb277-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="cb277-139">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="cb277-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="cb277-140">Om den läggs till på en startsida, där sidkontexten inte innehåller något produkt-ID, kommer listan att vara tom.</span><span class="sxs-lookup"><span data-stu-id="cb277-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="cb277-141">Algoritmskapade rekommendationslistor, t.ex. **Trend**, **Bästsäljande** och **Ny** kan användas på PDP.</span><span class="sxs-lookup"><span data-stu-id="cb277-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="cb277-142">Även om dessa listor kanske inte är direkt relaterade till produkten i PDP är de ett annat sätt att hjälpa kunderna att hitta produkter som kan vara intressanta för dem.</span><span class="sxs-lookup"><span data-stu-id="cb277-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="cb277-143">Dessa typer av listor kräver inget produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="cb277-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="cb277-144">De är generiska listor som skapas baserat på köpmönster på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="cb277-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="cb277-145">Redaktionella listor är manuellt granskade listor.</span><span class="sxs-lookup"><span data-stu-id="cb277-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="cb277-146">En återförsäljare kan till exempel välja att manuellt granska listor över produkter som den vill visa.</span><span class="sxs-lookup"><span data-stu-id="cb277-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="cb277-147">Moduler för omdömen och moduler</span><span class="sxs-lookup"><span data-stu-id="cb277-147">Ratings and reviews modules</span></span>

<span data-ttu-id="cb277-148">Tre moduler kan användas för att visa och lägga till recensioner:</span><span class="sxs-lookup"><span data-stu-id="cb277-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="cb277-149">**Recensioner** – Den här modulen anger omdömen och recensioner visas omdömen och recensioner som andra kunder har gett.</span><span class="sxs-lookup"><span data-stu-id="cb277-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="cb277-150">Kunder kan sortera och filtrera recensionerna.</span><span class="sxs-lookup"><span data-stu-id="cb277-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="cb277-151">Den här modulen gör det också möjligt för kunder som eller som vill granska recensioner och rapportera problem.</span><span class="sxs-lookup"><span data-stu-id="cb277-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="cb277-152">**Skriv recension** – i den här modulen kan kunderna skriva sina egna recensioner av en produkt.</span><span class="sxs-lookup"><span data-stu-id="cb277-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="cb277-153">**Omdömeshistogram** – i den här modulen finns ett histogram över trender för omdömen för en produkt.</span><span class="sxs-lookup"><span data-stu-id="cb277-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="cb277-154">Mer information finns i [Översikt över omdömen och recensioner](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cb277-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="cb277-155">Marknadsföringsmoduler</span><span class="sxs-lookup"><span data-stu-id="cb277-155">Marketing modules</span></span>

<span data-ttu-id="cb277-156">Om marknadsföringsinnehållet är unikt för en viss produkt kan en marknadsföringsmodul läggas till i PDP.</span><span class="sxs-lookup"><span data-stu-id="cb277-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="cb277-157">Du kan lägga till marknadsföringsmaterial i ett PDP genom att "berika" sidan.</span><span class="sxs-lookup"><span data-stu-id="cb277-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="cb277-158">Mer information finns i [utöka en produktsida](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="cb277-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb277-159">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cb277-159">Additional resources</span></span>

[<span data-ttu-id="cb277-160">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="cb277-160">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="cb277-161">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="cb277-161">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="cb277-162">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="cb277-162">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="cb277-163">Utöka en produktdetaljsida</span><span class="sxs-lookup"><span data-stu-id="cb277-163">Enrich a product details page</span></span>](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]