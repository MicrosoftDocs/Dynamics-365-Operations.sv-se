---
title: Modul för leveransalternativ
description: Det här avsnittet modul för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d0e5fa731d4b808cda9863074d17d1917410f399
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213684"
---
# <a name="delivery-options-module"></a><span data-ttu-id="4b466-103">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4b466-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b466-104">Det här avsnittet modul för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b466-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4b466-105">Med hjälp av modul för leveransalternativ kan kunderna välja leveranssätt, t.ex. leverans eller upphämtning för sin onlinebeställning.</span><span class="sxs-lookup"><span data-stu-id="4b466-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="4b466-106">Det krävs en leveransadress för att fastställa leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="4b466-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="4b466-107">Om leveransadressen ändras måste leveransalternativen hämtas igen.</span><span class="sxs-lookup"><span data-stu-id="4b466-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="4b466-108">Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="4b466-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="4b466-109">Mer information om hur du konfigurerar leveranssätt finns i [konfiguration av onlinekanal](channel-setup-online.md) och [Ställ in leveranssätt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="4b466-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="4b466-110">Varje leveranssätt kan ha en associerad avgift.</span><span class="sxs-lookup"><span data-stu-id="4b466-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="4b466-111">Mer information om hur du konfigurerar avgifter för en nätbutik finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="4b466-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="4b466-112">I Commerce version 10.0.13 har modulen leveransalternativ uppdaterats för att stödja funktionerna **huvudavgifter utan proportionell fördelning** och **leverera som radavgift**.</span><span class="sxs-lookup"><span data-stu-id="4b466-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="4b466-113">Om proportionen är inaktiverad är det förväntat att arbetsflödet för näthandel inte tillåter ett blandat leverans sätt för artiklarna i kundvagnen (dvs. vissa artiklar väljs för leverans, men andra väljs för upphämtning).</span><span class="sxs-lookup"><span data-stu-id="4b466-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="4b466-114">Funktionen **huvudavgifter utan proportionell fördelning** kräver att flaggan **Aktivera konsekvent hantering av leveranssätt i kanal** aktiveras i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="4b466-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="4b466-115">När den flaggan är påslagen kommer fraktkostnader att tillämpas antingen på huvudnivå eller radnivå, beroende på konfigurationen i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="4b466-115">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="4b466-116">Temat Fabrikam har stöd för ett blandat leveranssätt, där vissa artiklar har valts för leverans men andra har valts för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="4b466-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="4b466-117">I det här läget beräknas fraktkostnaderna för alla artiklar som väljs för leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="4b466-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="4b466-118">Om ett blandat leveranssätt ska fungera måste du först konfigurera funktionen **huvudavgifter utan proportionell fördelning** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="4b466-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="4b466-119">Mer information om den här konfigurationen finns i [Fördela huvudtillägg proportionellt som matchar försäljningsraderna](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="4b466-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="4b466-120">Om leveransavgifter används på radartiklar kan de visas på kundvagnsraden för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="4b466-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="4b466-121">Den här funktionen kräver att egenskapen **Visa fraktavgifter på radartikel** aktiveras för både kundvagnsmodulen och kassamodulen.</span><span class="sxs-lookup"><span data-stu-id="4b466-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="4b466-122">Mer information finns i [kundvagnsmodulen](add-cart-module.md) och [kassamodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="4b466-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="4b466-123">Följande bild visar ett exempel på en leveransalternativmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="4b466-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Exempel på en modul för leveranssätt på en kassasida](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="4b466-125">Egenskaper för modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="4b466-125">Delivery options module properties</span></span>

| <span data-ttu-id="4b466-126">Egenskap</span><span class="sxs-lookup"><span data-stu-id="4b466-126">Property</span></span> | <span data-ttu-id="4b466-127">Värden</span><span class="sxs-lookup"><span data-stu-id="4b466-127">Values</span></span> | <span data-ttu-id="4b466-128">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4b466-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="4b466-129">Rubrik</span><span class="sxs-lookup"><span data-stu-id="4b466-129">Heading</span></span> | <span data-ttu-id="4b466-130">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="4b466-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="4b466-131">En valfri rubrik för leveransalternativmodul.</span><span class="sxs-lookup"><span data-stu-id="4b466-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="4b466-132">Anpassat CSS-klassnamn</span><span class="sxs-lookup"><span data-stu-id="4b466-132">Custom CSS class name</span></span> | <span data-ttu-id="4b466-133">Text</span><span class="sxs-lookup"><span data-stu-id="4b466-133">Text</span></span> | <span data-ttu-id="4b466-134">Ett klassnamn för Överlappande formatmallar (CSS) som används för att återge modulen, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="4b466-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="4b466-135">Alternativ för att filtrera leveranssätt</span><span class="sxs-lookup"><span data-stu-id="4b466-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="4b466-136">**Filtrera inte** eller **ej leveranssätt**</span><span class="sxs-lookup"><span data-stu-id="4b466-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="4b466-137">Ett värde som anger om modulen för leveransalternativ ska filtrera bort alla leveranssätt som inte kan levereras.</span><span class="sxs-lookup"><span data-stu-id="4b466-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="4b466-138">Lägg till leveransalternativmodul på en kassasida och ställa in de obligatoriska egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="4b466-138">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="4b466-139">En leveransalternativmodul kan bara läggas till i en betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="4b466-139">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="4b466-140">Mer information om hur du konfigurerar leveransalternativmodul och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="4b466-140">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b466-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4b466-141">Additional resources</span></span>

[<span data-ttu-id="4b466-142">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="4b466-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4b466-143">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="4b466-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4b466-144">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="4b466-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="4b466-145">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="4b466-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="4b466-146">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="4b466-146">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="4b466-147">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="4b466-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="4b466-148">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="4b466-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="4b466-149">Konfiguration av onlinekanal</span><span class="sxs-lookup"><span data-stu-id="4b466-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="4b466-150">Avancerade automatiska avgifter för flera kanaler</span><span class="sxs-lookup"><span data-stu-id="4b466-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="4b466-151">Allokera huvudavgifter för att matcha försäljningsrader</span><span class="sxs-lookup"><span data-stu-id="4b466-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="4b466-152">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="4b466-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]