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
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 39e597b88afcca69623b1a23acc95e4da3873082
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818309"
---
# <a name="delivery-options-module"></a><span data-ttu-id="5bfc2-103">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="5bfc2-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5bfc2-104">Det här avsnittet modul för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5bfc2-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="5bfc2-105">Overview</span></span>

<span data-ttu-id="5bfc2-106">Med hjälp av modul för leveransalternativ kan kunderna välja leveranssätt, t.ex. leverans eller upphämtning för sin onlinebeställning.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-106">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="5bfc2-107">Det krävs en leveransadress för att fastställa leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-107">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="5bfc2-108">Om leveransadressen ändras måste leveransalternativen hämtas igen.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-108">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="5bfc2-109">Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-109">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="5bfc2-110">Mer information om hur du konfigurerar leveranssätt finns i [konfiguration av onlinekanal](channel-setup-online.md) och [Ställ in leveranssätt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-110">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="5bfc2-111">Varje leveranssätt kan ha en associerad avgift.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-111">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="5bfc2-112">Mer information om hur du konfigurerar avgifter för en nätbutik finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-112">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="5bfc2-113">I Commerce version 10.0.13 har modulen leveransalternativ uppdaterats för att stödja funktionerna **huvudavgifter utan proportionell fördelning** och **leverera som radavgift**.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-113">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="5bfc2-114">Om proportionen är inaktiverad är det förväntat att arbetsflödet för e-handel inte tillåter ett blandat leverans sätt för artiklarna i kundvagnen (dvs. vissa artiklar väljs för leverans, men andra väljs för upphämtning).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-114">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="5bfc2-115">Funktionen **huvudavgifter utan proportionell fördelning** kräver att flaggan **Aktivera konsekvent hantering av leveranssätt i kanal** aktiveras i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-115">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="5bfc2-116">När den flaggan är påslagen kommer fraktkostnader att tillämpas antingen på huvudnivå eller radnivå, beroende på konfigurationen i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-116">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="5bfc2-117">Temat Fabrikam har stöd för ett blandat leveranssätt, där vissa artiklar har valts för leverans men andra har valts för upphämtning.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-117">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="5bfc2-118">I det här läget beräknas fraktkostnaderna för alla artiklar som väljs för leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-118">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="5bfc2-119">Om ett blandat leveranssätt ska fungera måste du först konfigurera funktionen **huvudavgifter utan proportionell fördelning** i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-119">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="5bfc2-120">Mer information om den här konfigurationen finns i [Fördela huvudtillägg proportionellt som matchar försäljningsraderna](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-120">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="5bfc2-121">Om leveransavgifter används på radartiklar kan de visas på kundvagnsraden för varje artikel.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-121">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="5bfc2-122">Den här funktionen kräver att egenskapen **Visa fraktavgifter på radartikel** aktiveras för både kundvagnsmodulen och kassamodulen.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-122">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="5bfc2-123">Mer information finns i [kundvagnsmodulen](add-cart-module.md) och [kassamodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-123">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="5bfc2-124">Följande bild visar ett exempel på en leveransalternativmodul på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-124">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Exempel på en modul för leveranssätt på en sida i kassan](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="5bfc2-126">Egenskaper för modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="5bfc2-126">Delivery options module properties</span></span>

| <span data-ttu-id="5bfc2-127">Egenskap</span><span class="sxs-lookup"><span data-stu-id="5bfc2-127">Property</span></span> | <span data-ttu-id="5bfc2-128">Värden</span><span class="sxs-lookup"><span data-stu-id="5bfc2-128">Values</span></span> | <span data-ttu-id="5bfc2-129">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5bfc2-129">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="5bfc2-130">Rubrik</span><span class="sxs-lookup"><span data-stu-id="5bfc2-130">Heading</span></span> | <span data-ttu-id="5bfc2-131">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="5bfc2-131">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="5bfc2-132">En valfri rubrik för leveransalternativmodul.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-132">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="5bfc2-133">Anpassat CSS-klassnamn</span><span class="sxs-lookup"><span data-stu-id="5bfc2-133">Custom CSS class name</span></span> | <span data-ttu-id="5bfc2-134">Text</span><span class="sxs-lookup"><span data-stu-id="5bfc2-134">Text</span></span> | <span data-ttu-id="5bfc2-135">Ett klassnamn för Överlappande formatmallar (CSS) som används för att återge modulen, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-135">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="5bfc2-136">Alternativ för att filtrera leveranssätt</span><span class="sxs-lookup"><span data-stu-id="5bfc2-136">Filter Delivery Mode Option</span></span> | <span data-ttu-id="5bfc2-137">**Filtrera inte** eller **ej leveranslägen**</span><span class="sxs-lookup"><span data-stu-id="5bfc2-137">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="5bfc2-138">Ett värde som anger om modulen för leveransalternativ ska filtrera bort alla leveranslägen som inte kan levereras.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-138">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="5bfc2-139">Lägg till leveransalternativmodul på en kassasida och ställa in de obligatoriska egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-139">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="5bfc2-140">En leveransalternativmodul kan bara läggas till i en betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="5bfc2-140">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="5bfc2-141">Mer information om hur du konfigurerar leveransalternativmodul och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5bfc2-141">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5bfc2-142">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5bfc2-142">Additional resources</span></span>

[<span data-ttu-id="5bfc2-143">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="5bfc2-143">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5bfc2-144">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="5bfc2-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5bfc2-145">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="5bfc2-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5bfc2-146">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="5bfc2-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5bfc2-147">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="5bfc2-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5bfc2-148">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="5bfc2-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="5bfc2-149">Konfiguration av onlinekanal</span><span class="sxs-lookup"><span data-stu-id="5bfc2-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="5bfc2-150">Avancerade automatiska avgifter för flera kanaler</span><span class="sxs-lookup"><span data-stu-id="5bfc2-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="5bfc2-151">Allokera huvudavgifter för att matcha försäljningsrader</span><span class="sxs-lookup"><span data-stu-id="5bfc2-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="5bfc2-152">Ställ in leveranssätt</span><span class="sxs-lookup"><span data-stu-id="5bfc2-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
