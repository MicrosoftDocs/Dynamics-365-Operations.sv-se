---
title: Modul för butiksväljare
description: Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378218"
---
# <a name="store-selector-module"></a><span data-ttu-id="9875a-103">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="9875a-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9875a-104">Det här avsnittet handlar om modulen för butiksväljare och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9875a-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9875a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="9875a-105">Overview</span></span>

<span data-ttu-id="9875a-106">En modul för butiksväljare används för kundscenariot "Köp online, hämta i butik" "(BOPIS).</span><span class="sxs-lookup"><span data-stu-id="9875a-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="9875a-107">En lista visas med butiker där en produkt är tillgänglig för upphämtning, samt butikstimmar och produktlager för varje butik.</span><span class="sxs-lookup"><span data-stu-id="9875a-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="9875a-108">Modulen butiksväljare kräver en produkts kontext och en sökplats för att hitta butiker.</span><span class="sxs-lookup"><span data-stu-id="9875a-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="9875a-109">I avsaknad av en sökplats är det standardadressen till kundens webbläsare, förutsatt att kunden godkänner det.</span><span class="sxs-lookup"><span data-stu-id="9875a-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="9875a-110">Modulen har en inmatningsruta där kunden kan ange en plats (postnummer, ort och delstat) för att hitta butiker som finns i närheten.</span><span class="sxs-lookup"><span data-stu-id="9875a-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="9875a-111">Butiksväljarmodulen är integrerad med geokodnings-API för Bing Maps för att konvertera platsen till en latitud och longitud.</span><span class="sxs-lookup"><span data-stu-id="9875a-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="9875a-112">En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-parametrar i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9875a-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9875a-113">Modulen butiksväljare kan läggas till i en modul för inköpsruta på sidan produktinformation (PDP) för att visa butiker där en produkt är tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="9875a-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="9875a-114">Den kan också läggas till i en vagnmodul.</span><span class="sxs-lookup"><span data-stu-id="9875a-114">It can also be added to a cart module.</span></span> <span data-ttu-id="9875a-115">När du lägger till i en kundvagn visar modulen butiksväljare visas upphämtningsalternativ för varje vagnradartikel.</span><span class="sxs-lookup"><span data-stu-id="9875a-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="9875a-116">Med anpassad kodning kan du dessutom lägga till modulen i andra sidor eller moduler via tillägg och anpassningar.</span><span class="sxs-lookup"><span data-stu-id="9875a-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="9875a-117">För att BOPIS-scenariot ska fungera bör produkter konfigureras med leveransläget "kundupphämtning".</span><span class="sxs-lookup"><span data-stu-id="9875a-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="9875a-118">Annars visas modulen inte på respektive sida.</span><span class="sxs-lookup"><span data-stu-id="9875a-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="9875a-119">Mer information om hur du konfigurerar leveransläget finns i [ställa in leveransmetod](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="9875a-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="9875a-120">Följande bild visar ett exempel på en modul för butiksväljare som används på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="9875a-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Exempel på en modul för butiksväljare](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="9875a-122">Användning av modul för butiksväljare i e-handel</span><span class="sxs-lookup"><span data-stu-id="9875a-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="9875a-123">En modul för butiksväljare kan användas för sidan produktinformation (PDP) för att hitta butiker i närheten där en produkt är tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="9875a-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="9875a-124">En modul för butiksväljare kan användas på en kundvagnssida för att hitta butiker i närheten där en produkt i kundvagnen är tillgänglig för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="9875a-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="9875a-125">Egenskaper för modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="9875a-125">Store selector module properties</span></span>

| <span data-ttu-id="9875a-126">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="9875a-126">Property name</span></span>             | <span data-ttu-id="9875a-127">Värde</span><span class="sxs-lookup"><span data-stu-id="9875a-127">Value</span></span>                 | <span data-ttu-id="9875a-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="9875a-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="9875a-129">Sök radie</span><span class="sxs-lookup"><span data-stu-id="9875a-129">Search radius</span></span> | <span data-ttu-id="9875a-130">Antal</span><span class="sxs-lookup"><span data-stu-id="9875a-130">Number</span></span> | <span data-ttu-id="9875a-131">Definierar sökradien för butiker, i mil.</span><span class="sxs-lookup"><span data-stu-id="9875a-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="9875a-132">Om inget värde anges används standardsökradien 50 mil.</span><span class="sxs-lookup"><span data-stu-id="9875a-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="9875a-133">Användarvillkor</span><span class="sxs-lookup"><span data-stu-id="9875a-133">Terms of Service</span></span> | <span data-ttu-id="9875a-134">URL</span><span class="sxs-lookup"><span data-stu-id="9875a-134">URL</span></span>    |  <span data-ttu-id="9875a-135">Det krävs en URL för tjänstvillkors för Bing Maps-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9875a-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="9875a-136">Lägg till modulen för butiksväljare till en sida</span><span class="sxs-lookup"><span data-stu-id="9875a-136">Add a store selector module to a page</span></span>

<span data-ttu-id="9875a-137">En modulen för butiksväljare behöver kontexten för en produkt, så den kan bara användas i köp- och vagnmoduler.</span><span class="sxs-lookup"><span data-stu-id="9875a-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="9875a-138">Modulen för butiksväljare fungerar inte utanför dessa moduler.</span><span class="sxs-lookup"><span data-stu-id="9875a-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="9875a-139">Mer information om hur du lägger till en modulen för butiksväljare i en modul för inköpsruta finns i [modul för inköpsruta](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="9875a-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="9875a-140">Mer information om hur du lägger till en modulen för butiksväljare i en vagnmodul i [vagnmodul](add-cart-module.md)</span><span class="sxs-lookup"><span data-stu-id="9875a-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9875a-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9875a-141">Additional resources</span></span>

[<span data-ttu-id="9875a-142">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="9875a-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9875a-143">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="9875a-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9875a-144">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="9875a-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="9875a-145">Guidad visning av PDP</span><span class="sxs-lookup"><span data-stu-id="9875a-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="9875a-146">Guidad visning av kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="9875a-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="9875a-147">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="9875a-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[<span data-ttu-id="9875a-148">Hantera Bing Maps för din organisation</span><span class="sxs-lookup"><span data-stu-id="9875a-148">Manage Bing Maps for your organization</span></span>](dev-itpro/manage-bing-maps.md)
