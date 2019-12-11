---
title: Översikt över sidor med produktinformation
description: Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3b02d50adbfcda27d590bcb87fd9669d67d4a01c
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697875"
---
# <a name="overview-of-product-details-pages"></a><span data-ttu-id="4839d-103">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="4839d-103">Overview of product details pages</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4839d-104">Det här ämnet innehåller en översikt över sidor för produktdetaljer (PDP) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4839d-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4839d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4839d-105">Overview</span></span>

<span data-ttu-id="4839d-106">En PDP innehåller detaljerad information om en produkt och kunder kan välja produktalternativ som storlek, stil och färg.</span><span class="sxs-lookup"><span data-stu-id="4839d-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="4839d-107">En PDP ska visa all produktinformation som en kund behöver för att fatta ett köpbeslut.</span><span class="sxs-lookup"><span data-stu-id="4839d-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="4839d-108">Illustrationen nedan visar ett exempel på en PDP.</span><span class="sxs-lookup"><span data-stu-id="4839d-108">The following illustration shows an example of a PDP.</span></span>

![Exempel på en sida med produktinformation](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="4839d-110">Moduler för sidhuvud och sidfot</span><span class="sxs-lookup"><span data-stu-id="4839d-110">Header and footer modules</span></span>

<span data-ttu-id="4839d-111">Den övre delen av PDP har en rubrik som visar alla produktkategorier och andra sidor som återförsäljaren vill att kunderna ska bläddra i.</span><span class="sxs-lookup"><span data-stu-id="4839d-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="4839d-112">Sidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för kunderna.</span><span class="sxs-lookup"><span data-stu-id="4839d-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="4839d-113">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="4839d-113">Buy box module</span></span>

<span data-ttu-id="4839d-114">Den viktigaste modulen på ett PDP är modulen inköpsruta.</span><span class="sxs-lookup"><span data-stu-id="4839d-114">The most important module on a PDP is the buy box module.</span></span> <span data-ttu-id="4839d-115">Därför är det den första artikeln i huvudavsnittet på sidan.</span><span class="sxs-lookup"><span data-stu-id="4839d-115">Therefore, it's the first item in the main section of the page.</span></span> <span data-ttu-id="4839d-116">Modulen inköpsruta är en behållarmodul och innehåller flera moduler som innehåller den viktigaste informationen om produkten.</span><span class="sxs-lookup"><span data-stu-id="4839d-116">A buy box module is a container module and hosts several modules that contain the most important information about the product.</span></span> <span data-ttu-id="4839d-117">Denna information omfattar produktnamn, produktbilder, beskrivning, pris och produktvärderingar.</span><span class="sxs-lookup"><span data-stu-id="4839d-117">This information includes the product name, product images, the description, the price, and product ratings.</span></span>

<span data-ttu-id="4839d-118">Med modulen inköpsruta kan kunden välja produktalternativ (t.ex. storlek, stil och färg) och lägga till produkten i vagnen.</span><span class="sxs-lookup"><span data-stu-id="4839d-118">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="4839d-119">Kunden kan också köpa produkten online och välja den i en butik.</span><span class="sxs-lookup"><span data-stu-id="4839d-119">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="4839d-120">Modulerna köpa online och hämta i butik använder integration med Bing Maps API:er (Application Programming Interfaces) för att hitta närliggande butiker eller butiker på en annan plats som kunden anger.</span><span class="sxs-lookup"><span data-stu-id="4839d-120">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="4839d-121">En modul för inköpsruta kräver ett produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="4839d-121">A buy box module requires a product ID.</span></span> <span data-ttu-id="4839d-122">Detta ID hämtas från sidans kontext.</span><span class="sxs-lookup"><span data-stu-id="4839d-122">This ID is derived from the page context.</span></span> <span data-ttu-id="4839d-123">Om en modul för inköpsruta läggs till på en sida där sidkontexten inte innehåller något produkt-ID, återges informationen inte på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="4839d-123">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="4839d-124">Modul för produktspecifikationer</span><span class="sxs-lookup"><span data-stu-id="4839d-124">Product specifications module</span></span>

<span data-ttu-id="4839d-125">Modulen för produktspecifikationer kan användas för att visa mer information om produkten.</span><span class="sxs-lookup"><span data-stu-id="4839d-125">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="4839d-126">Dessa detaljer hämtas från produktattribut i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="4839d-126">These details are taken from product attributes in Dynamics 365 Retail.</span></span> <span data-ttu-id="4839d-127">Modulen produktspecifikationer visar alla attribut där egenskapen **synlig** är inställd på **sant**.</span><span class="sxs-lookup"><span data-stu-id="4839d-127">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="4839d-128">Det kräver ett produkt-ID för att hämta produktattribut.</span><span class="sxs-lookup"><span data-stu-id="4839d-128">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="4839d-129">Rekommendationsmodul</span><span class="sxs-lookup"><span data-stu-id="4839d-129">Recommendations module</span></span>

<span data-ttu-id="4839d-130">Rekommendationsmodulen är en viktig modul på en PDP.</span><span class="sxs-lookup"><span data-stu-id="4839d-130">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="4839d-131">Medan kunder bläddrar efter produkter, bör fler produktalternativ presenteras för dem, så att de kan hitta rätt produkter och göra inköp.</span><span class="sxs-lookup"><span data-stu-id="4839d-131">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="4839d-132">Rekommendationer hjälper kunder att enkelt hitta relaterat innehåll och fortsätta att handla.</span><span class="sxs-lookup"><span data-stu-id="4839d-132">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="4839d-133">Det finns olika typer av rekommendationslistor:</span><span class="sxs-lookup"><span data-stu-id="4839d-133">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="4839d-134">Listan **personer gillar också** baseras på maskinutbildning.</span><span class="sxs-lookup"><span data-stu-id="4839d-134">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="4839d-135">Den använder transaktionshistorik för andra kunder för att ge rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="4839d-135">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="4839d-136">Den här listan genereras av rekommendationstjänsten och liknar listan "kunder som köpt detta har också köpt...".</span><span class="sxs-lookup"><span data-stu-id="4839d-136">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="4839d-137">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="4839d-137">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="4839d-138">En **relaterad** lista kan konfigureras för en produkt i Retail.</span><span class="sxs-lookup"><span data-stu-id="4839d-138">A **Related** list can be configured for a product in Retail.</span></span> <span data-ttu-id="4839d-139">För till exempel en handväska i brunt läder kan flera handväskor som är läderbaserade eller utformade för resor konfigureras för den relaterade listan.</span><span class="sxs-lookup"><span data-stu-id="4839d-139">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="4839d-140">Andra typer av relaterade listor, till exempel **tillbehör** och **Fler som den här**, kan också konfigureras i Retail.</span><span class="sxs-lookup"><span data-stu-id="4839d-140">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Retail.</span></span> <span data-ttu-id="4839d-141">Ett produkt-ID krävs för att listan ska kunna skapas.</span><span class="sxs-lookup"><span data-stu-id="4839d-141">A product ID is required to generate this list.</span></span> <span data-ttu-id="4839d-142">Om den läggs till på en startsida, där sidkontexten inte innehåller något produkt-ID, kommer listan att vara tom.</span><span class="sxs-lookup"><span data-stu-id="4839d-142">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="4839d-143">Algoritmskapade rekommendationslistor, t.ex. **Trend**, **Bästsäljande** och **Ny** kan användas på PDP.</span><span class="sxs-lookup"><span data-stu-id="4839d-143">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="4839d-144">Även om dessa listor kanske inte är direkt relaterade till produkten i PDP är de ett annat sätt att hjälpa kunderna att hitta produkter som kan vara intressanta för dem.</span><span class="sxs-lookup"><span data-stu-id="4839d-144">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="4839d-145">Dessa typer av listor kräver inget produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="4839d-145">These types of lists don't require a product ID.</span></span> <span data-ttu-id="4839d-146">De är generiska listor som skapas baserat på köpmönster på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="4839d-146">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="4839d-147">Redaktionella listor är manuellt granskade listor.</span><span class="sxs-lookup"><span data-stu-id="4839d-147">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="4839d-148">En återförsäljare kan till exempel välja att manuellt granska listor över produkter som den vill visa.</span><span class="sxs-lookup"><span data-stu-id="4839d-148">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-module"></a><span data-ttu-id="4839d-149">Moduler för omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4839d-149">Ratings and reviews module</span></span>

<span data-ttu-id="4839d-150">I modulen omdömen och recensioner visas omdömen och recensioner som andra kunder har gett.</span><span class="sxs-lookup"><span data-stu-id="4839d-150">The ratings and reviews module shows ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="4839d-151">Det gör också att kunden kan skriva sin egen granskning av produkten.</span><span class="sxs-lookup"><span data-stu-id="4839d-151">It also lets a customer write his or her own review of the product.</span></span> <span data-ttu-id="4839d-152">Dessutom innehåller den ett histogram som visar klassificeringstrenden för produkten.</span><span class="sxs-lookup"><span data-stu-id="4839d-152">Additionally, it includes a histogram that shows the ratings trend for the product.</span></span> <span data-ttu-id="4839d-153">Mer information finns i [Översikt över omdömen och recensioner](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4839d-153">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="4839d-154">Marknadsföringsmoduler</span><span class="sxs-lookup"><span data-stu-id="4839d-154">Marketing modules</span></span>

<span data-ttu-id="4839d-155">Om marknadsföringsinnehållet är unikt för en viss produkt kan en marknadsföringsmodul läggas till i PDP.</span><span class="sxs-lookup"><span data-stu-id="4839d-155">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="4839d-156">Du kan lägga till marknadsföringsmaterial i ett PDP genom att "berika" sidan.</span><span class="sxs-lookup"><span data-stu-id="4839d-156">You can add marketing modules to a PDP by "enriching" the page.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="4839d-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4839d-157">Additional resources</span></span>

[<span data-ttu-id="4839d-158">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="4839d-158">Overview of the home page</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="4839d-159">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="4839d-159">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="4839d-160">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="4839d-160">Overview of cart and checkout pages</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="4839d-161">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="4839d-161">Overview of account management pages</span></span>](quick-tour-account-management.md)
