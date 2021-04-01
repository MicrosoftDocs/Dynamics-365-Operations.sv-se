---
title: Modul för leveransadress
description: Det här avsnittet handlar om modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e590c966ca6bd8111df5f91cbac0485afaa45c78
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234423"
---
# <a name="shipping-address-module"></a><span data-ttu-id="93e18-103">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="93e18-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="93e18-104">Det här avsnittet beskriver modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93e18-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="93e18-105">Leveransadressmodulen låter kunderna lägga till eller välja leveransadressen för en order under kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="93e18-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="93e18-106">Om kunden är inloggad visas alla adresser som har sparats för den kunden och kunden kan välja bland dem.</span><span class="sxs-lookup"><span data-stu-id="93e18-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="93e18-107">Kunden kan också lägga till en ny adress.</span><span class="sxs-lookup"><span data-stu-id="93e18-107">The customer can also add a new address.</span></span> <span data-ttu-id="93e18-108">Leveransadressmodulen används för alla artiklar i den order som kräver leverans.</span><span class="sxs-lookup"><span data-stu-id="93e18-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="93e18-109">Adressformat för leverans kan definieras i Commerce-administration för varje land eller region och i modulen för leverans används lands-/regionspecifika regler.</span><span class="sxs-lookup"><span data-stu-id="93e18-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="93e18-110">När kunderna anger en leveransadress under kassaflödet kan de välja att spara adressen som en primär adress.</span><span class="sxs-lookup"><span data-stu-id="93e18-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="93e18-111">Det här alternativet visas bara om kunden är inloggad.</span><span class="sxs-lookup"><span data-stu-id="93e18-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="93e18-112">Även om modulen leveransadress inte ger adressvalidering kan denna funktion implementeras genom anpassning.</span><span class="sxs-lookup"><span data-stu-id="93e18-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="93e18-113">Följande bild visar ett exempel på en ny leveransadressmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="93e18-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exempel på en modul för leveransadresser på en sida i POS](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="93e18-115">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="93e18-115">Module properties</span></span>

| <span data-ttu-id="93e18-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="93e18-116">Property name</span></span> | <span data-ttu-id="93e18-117">Värden</span><span class="sxs-lookup"><span data-stu-id="93e18-117">Values</span></span> | <span data-ttu-id="93e18-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="93e18-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="93e18-119">Rubrik</span><span class="sxs-lookup"><span data-stu-id="93e18-119">Heading</span></span> | <span data-ttu-id="93e18-120">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="93e18-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="93e18-121">En valfri rubrik för leveransadressmodulen.</span><span class="sxs-lookup"><span data-stu-id="93e18-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="93e18-122">Visa adresstyp</span><span class="sxs-lookup"><span data-stu-id="93e18-122">Show address type</span></span> | <span data-ttu-id="93e18-123">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="93e18-123">**True** or **False**</span></span> | <span data-ttu-id="93e18-124">Om den här valfria egenskapen har värdet **True** visas en adresstyp, t.ex. **Start** eller **företag**.</span><span class="sxs-lookup"><span data-stu-id="93e18-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="93e18-125">Om ingen adresstyp har angetts kommer adressen automatiskt att sparas som **Typ**=**Övriga**.</span><span class="sxs-lookup"><span data-stu-id="93e18-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="93e18-126">Aktivera automatiskt förslag</span><span class="sxs-lookup"><span data-stu-id="93e18-126">Enable auto suggestion</span></span>| <span data-ttu-id="93e18-127">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="93e18-127">**True** or **False**</span></span> | <span data-ttu-id="93e18-128">Om den här valfria egenskapen ställs in på **True**, ges automatiska adressförslag.</span><span class="sxs-lookup"><span data-stu-id="93e18-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="93e18-129">De här förslagen används av Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="93e18-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="93e18-130">Information om hur du ställer in Bing Maps-integration för din webbplats finns i [modulen Butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="93e18-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="93e18-131">Den här funktionen är tillgänglig i Commerce version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="93e18-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="93e18-132">Alternativ för automatiskt förslag</span><span class="sxs-lookup"><span data-stu-id="93e18-132">Auto suggest options</span></span>| <span data-ttu-id="93e18-133">Ett nummer</span><span class="sxs-lookup"><span data-stu-id="93e18-133">A number</span></span>| <span data-ttu-id="93e18-134">Om automatiska adressförslag har aktiverats kan du ange ytterligare alternativ, till exempel det högsta antalet förslag som ska ges.</span><span class="sxs-lookup"><span data-stu-id="93e18-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="93e18-135">Lägg till leveransadressmodul på en kassasida och ställa in de obligatoriska egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="93e18-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="93e18-136">En modul för leveransadress kan bara läggas till i en betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="93e18-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="93e18-137">Mer information om hur du konfigurerar modulen för leveransadress och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="93e18-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93e18-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="93e18-138">Additional resources</span></span>

[<span data-ttu-id="93e18-139">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="93e18-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="93e18-140">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="93e18-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="93e18-141">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="93e18-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="93e18-142">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="93e18-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="93e18-143">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="93e18-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="93e18-144">Modul för upphämtningsinformation</span><span class="sxs-lookup"><span data-stu-id="93e18-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="93e18-145">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="93e18-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="93e18-146">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="93e18-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="93e18-147">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="93e18-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]