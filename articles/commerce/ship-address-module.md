---
title: Modul för leveransadress
description: Det här avsnittet handlar om modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.openlocfilehash: 6a5eb69c7746be419779b1a844ee35ec375a324c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985646"
---
# <a name="shipping-address-module"></a><span data-ttu-id="33973-103">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="33973-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="33973-104">Det här avsnittet beskriver om modul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="33973-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="33973-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="33973-105">Overview</span></span>

<span data-ttu-id="33973-106">Leveransadressmodulen låter kunderna lägga till eller välja leveransadressen för en order under kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="33973-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="33973-107">Om kunden är inloggad visas alla adresser som har sparats för den kunden och kunden kan välja bland dem.</span><span class="sxs-lookup"><span data-stu-id="33973-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="33973-108">Kunden kan också lägga till en ny adress.</span><span class="sxs-lookup"><span data-stu-id="33973-108">The customer can also add a new address.</span></span> <span data-ttu-id="33973-109">Leveransadressmodulen används för alla artiklar i den order som kräver leverans.</span><span class="sxs-lookup"><span data-stu-id="33973-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="33973-110">Adressformat för leverans kan definieras i Commerce-administration för varje land eller region och i modulen för leverans används lands-/regionspecifika regler.</span><span class="sxs-lookup"><span data-stu-id="33973-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="33973-111">När kunderna anger en leveransadress under kassaflödet kan de välja att spara adressen som en primär adress.</span><span class="sxs-lookup"><span data-stu-id="33973-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="33973-112">Det här alternativet visas bara om kunden är inloggad.</span><span class="sxs-lookup"><span data-stu-id="33973-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="33973-113">Även om modulen leveransadress inte ger adressvalidering kan denna funktion implementeras genom anpassning.</span><span class="sxs-lookup"><span data-stu-id="33973-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="33973-114">Följande bild visar ett exempel på en ny leveransadressmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="33973-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exempel på en modul för leveransadresser på en sida i POS](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="33973-116">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="33973-116">Module properties</span></span>

| <span data-ttu-id="33973-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="33973-117">Property name</span></span> | <span data-ttu-id="33973-118">Värden</span><span class="sxs-lookup"><span data-stu-id="33973-118">Values</span></span> | <span data-ttu-id="33973-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="33973-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="33973-120">Rubrik</span><span class="sxs-lookup"><span data-stu-id="33973-120">Heading</span></span> | <span data-ttu-id="33973-121">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="33973-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="33973-122">En valfri rubrik för leveransadressmodulen.</span><span class="sxs-lookup"><span data-stu-id="33973-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="33973-123">Visa adresstyp</span><span class="sxs-lookup"><span data-stu-id="33973-123">Show address type</span></span> | <span data-ttu-id="33973-124">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="33973-124">**True** or **False**</span></span> | <span data-ttu-id="33973-125">Om den här valfria egenskapen har värdet **True** visas en adresstyp, t.ex. **Start** eller **företag**.</span><span class="sxs-lookup"><span data-stu-id="33973-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="33973-126">Om ingen adresstyp har angetts kommer adressen automatiskt att sparas som **Typ**=**Övriga**.</span><span class="sxs-lookup"><span data-stu-id="33973-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="33973-127">Lägg till leveransadressmodul på en kassasida och ställa in de obligatoriska egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="33973-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="33973-128">En modul för leveransadress kan bara läggas till i en betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="33973-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="33973-129">Mer information om hur du konfigurerar modulen för leveransadress och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="33973-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33973-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="33973-130">Additional resources</span></span>

[<span data-ttu-id="33973-131">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="33973-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="33973-132">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="33973-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="33973-133">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="33973-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="33973-134">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="33973-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="33973-135">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="33973-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="33973-136">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="33973-136">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="33973-137">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="33973-137">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="33973-138">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="33973-138">Gift card module</span></span>](add-giftcard.md)
