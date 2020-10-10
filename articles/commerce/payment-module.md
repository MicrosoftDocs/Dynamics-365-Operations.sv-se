---
title: Betalningsmodul
description: Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 4267391edaf70ec645933b2c5c08a72735f52894
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818336"
---
# <a name="payment-module"></a><span data-ttu-id="cfcd2-103">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-103">Payment module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cfcd2-104">Det här avsnittet handlar om betalningsmodul för leveransadressmodulen förklarar hur du konfigurera i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-104">This topic covers the payment module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cfcd2-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="cfcd2-105">Overview</span></span>

<span data-ttu-id="cfcd2-106">Betalningsmodulen låter kunder betala för beställningar med kredit- eller betalkort.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-106">The payment module lets customers pay for orders by using credit or debit cards.</span></span> <span data-ttu-id="cfcd2-107">Betalningsintegration för den här modulen tillhandahålls av Dynamics 365-betalningskoppling för Adyen.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-107">Payment integration for this module is provided by the Dynamics 365 Payment Connector for Adyen.</span></span> <span data-ttu-id="cfcd2-108">För mer information om hur du konfigurerar och konfigurerar betalningskontakten, se [Dynamics 365 betalningsanslutning för Adyen](dev-itpro/adyen-connector.md)</span><span class="sxs-lookup"><span data-stu-id="cfcd2-108">For more information about how to set up and configure the payment connector, see [Dynamics 365 Payment Connector for Adyen](dev-itpro/adyen-connector.md).</span></span>

<span data-ttu-id="cfcd2-109">Modulen för betalning innehåller betalningsinformationen som betjänas via Adyen i en HTML-infogad ram (iframe).</span><span class="sxs-lookup"><span data-stu-id="cfcd2-109">The payment module hosts the payment information that is served via Adyen in an HTML inline frame (iframe).</span></span> <span data-ttu-id="cfcd2-110">Modulen för betalning interagerar med Commerce Scale Unit för att hämta Adyen betalningsinformation.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-110">The payment module interacts with the Commerce Scale Unit to retrieve the Adyen payment information.</span></span> <span data-ttu-id="cfcd2-111">Som en del av Commerce Scale Unit interaktionen kan betalningsmodulen tillåta att faktureringsadressinformation betjänas antingen i iframe eller som en separat modul.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-111">As part of the Commerce Scale Unit interaction, the payment module can allow billing address information to be served either in the iframe or as a separate module.</span></span> <span data-ttu-id="cfcd2-112">I temat Fabrikam visas faktureringsadressen i en separat modul.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-112">In the Fabrikam theme, the billing address is shown in a separate module.</span></span> <span data-ttu-id="cfcd2-113">Detta ger större flexibilitet eftersom adress raderna kan återges så att de liknar raderna i leveransadressen.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-113">This approach allows for more formatting flexibility, because the address lines can be rendered so that they resemble the lines of the shipping address.</span></span>

<span data-ttu-id="cfcd2-114">I betalningsmodulen kan också kunder som är inloggade spara sina betalningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-114">The payment module also lets signed-in customers save their payment information.</span></span> <span data-ttu-id="cfcd2-115">Betalningsinformationen och fakturerings adressen sparas och hanteras via Adyen betalningskoppling.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-115">The payment information and billing address are saved and managed via the Adyen payment connector.</span></span>

<span data-ttu-id="cfcd2-116">Betalningsmodulen täcker alla orderavgifter som inte redan omfattas av förmånspoäng eller presentkort.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-116">The payment module covers any order charges that aren't already covered by loyalty points or a gift card.</span></span> <span data-ttu-id="cfcd2-117">Om summan för en order helt täcks av förmånspoäng eller presentkortskrediter, döljs betalningsmodulen och kunden kan placera ordern utan den.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-117">If the total for an order is fully covered by loyalty points or gift card credits, the payment module will be hidden, and the customer will be able to place the order without it.</span></span>

<span data-ttu-id="cfcd2-118">Adyen betalningskontakt stöder också stark kundautentisering (SCA).</span><span class="sxs-lookup"><span data-stu-id="cfcd2-118">The Adyen payment connector also supports strong customer authentication (SCA).</span></span> <span data-ttu-id="cfcd2-119">En del av Europeiska unionen (EU) direktiv om betalningstjänster 2.0 (PSD 2.0) kräver att online-shoppare autentiseras utanför deras online-erfarenhet när de använder en elektronisk betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-119">Part of the European Union (EU) Payment Services Directive 2.0 (PSD2.0) requires that online shoppers be authenticated outside their online shopping experience when they use an electronic payment method.</span></span> <span data-ttu-id="cfcd2-120">Under kassaflödet omdirigeras kunderna till sin banks webbplats.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-120">During the checkout flow,  customers are redirected to their banking site.</span></span> <span data-ttu-id="cfcd2-121">Efter autentiseringen omdirigeras de tillbaka till Commerce-kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-121">Then, after authentication, they are redirected back to the Commerce checkout flow.</span></span> <span data-ttu-id="cfcd2-122">Under denna omdirigering behålls den information som en kunden registrerats i kassaflödet (t.ex. leveransadress, leveransalternativ, presentkortsinformation och lojalitetsinformation).</span><span class="sxs-lookup"><span data-stu-id="cfcd2-122">During this redirection, the information that a customer entered in the checkout flow (for example, the shipping address, delivery options, gift card information, and loyalty information) will persist.</span></span> <span data-ttu-id="cfcd2-123">Innan du kan aktivera den här funktionen måste betalningskopplingen konfigureras för SCA i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-123">Before you can turn on this feature, the payment connector must be configured for SCA in Commerce headquarters.</span></span> <span data-ttu-id="cfcd2-124">Mer information finns i [grundlig kundautentisering med hjälp av Adyen](adyen_redirect.md).</span><span class="sxs-lookup"><span data-stu-id="cfcd2-124">For more information, see [Strong Customer Authentication using Adyen](adyen_redirect.md).</span></span>

<span data-ttu-id="cfcd2-125">Följande bild visar ett exempel på moduler för presentkorts-, förmåns- och betalningsmoduler på en kassasida.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-125">The following illustration shows an example of gift card, loyalty, and payment modules on a checkout page.</span></span>

![Exempel på moduler för presentkorts-, förmåns- och betalningsmoduler på en kassasida](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a><span data-ttu-id="cfcd2-127">Egenskaper för betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-127">Payment module properties</span></span>

| <span data-ttu-id="cfcd2-128">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="cfcd2-128">Property name</span></span> | <span data-ttu-id="cfcd2-129">Värden</span><span class="sxs-lookup"><span data-stu-id="cfcd2-129">Values</span></span> | <span data-ttu-id="cfcd2-130">beskrivning</span><span class="sxs-lookup"><span data-stu-id="cfcd2-130">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="cfcd2-131">Rubrik</span><span class="sxs-lookup"><span data-stu-id="cfcd2-131">Heading</span></span> | <span data-ttu-id="cfcd2-132">Rubriktext</span><span class="sxs-lookup"><span data-stu-id="cfcd2-132">Heading text</span></span> | <span data-ttu-id="cfcd2-133">En valfri rubrik för betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-133">An optional heading for the payment module.</span></span> |
| <span data-ttu-id="cfcd2-134">Höjd på iframe.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-134">Height of the iframe</span></span> | <span data-ttu-id="cfcd2-135">Pixlar</span><span class="sxs-lookup"><span data-stu-id="cfcd2-135">Pixels</span></span> | <span data-ttu-id="cfcd2-136">Höjdpunkter iframe i bildpunkter.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-136">The iframe height, in pixels.</span></span> <span data-ttu-id="cfcd2-137">Höjden kan dock justeras efter behov.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-137">The height can be adjusted as required.</span></span> |
| <span data-ttu-id="cfcd2-138">Visa faktureringsadress</span><span class="sxs-lookup"><span data-stu-id="cfcd2-138">Show billing address</span></span> | <span data-ttu-id="cfcd2-139">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="cfcd2-139">**True** or **False**</span></span> | <span data-ttu-id="cfcd2-140">Om den här egenskapen har värdet **True** kommer faktureringsadressen att betjänas av Adyen inuti den inbäddade modulen för iframe.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-140">If this property is set to **True**, the billing address will be served by Adyen inside the payment module iframe.</span></span> <span data-ttu-id="cfcd2-141">Om den har värdet **False** faktureringsadressen inte att betjänas av Adyen och en Commerce-användare måste konfigurera en modul för att visa faktureringsadressen på kassasidan.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-141">If it's set to **False**, the billing address won't be served by Adyen, and a Commerce user will have to configure a module to show the billing address on the checkout page.</span></span> |
| <span data-ttu-id="cfcd2-142">Åsidosättning av betalningsformat</span><span class="sxs-lookup"><span data-stu-id="cfcd2-142">Payment style override</span></span> | <span data-ttu-id="cfcd2-143">Kod för överlappande formatmallar (CSS)</span><span class="sxs-lookup"><span data-stu-id="cfcd2-143">Cascading Style Sheets (CSS) code</span></span> | <span data-ttu-id="cfcd2-144">Eftersom betalningsmodulen finns i en iframe finns det en begränsad format kapacitet.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-144">Because the payment module is hosted in an iframe, there is limited styling capability.</span></span> <span data-ttu-id="cfcd2-145">Du kan formatera formateringen genom att använda den här egenskapen.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-145">You can achieve some styling by using this property.</span></span> <span data-ttu-id="cfcd2-146">Om du vill åsidosätta webbplatsformat måste du klistra in CSS-koden som egenskapensvärde.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-146">To override site styles, you must paste the CSS code as the value of this property.</span></span> <span data-ttu-id="cfcd2-147">Webbplatsskaparen CSS åsidosätter och stilar gäller inte för den här modulen.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-147">Site builder CSS overrides and styles don't apply to this module.</span></span> |

## <a name="billing-address"></a><span data-ttu-id="cfcd2-148">Faktureringsadress</span><span class="sxs-lookup"><span data-stu-id="cfcd2-148">Billing address</span></span>

<span data-ttu-id="cfcd2-149">Betalningsmodulen erbjuder kunder en faktureringsadress för sina betalningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-149">The payment module lets customers provide a billing address for their payment information.</span></span> <span data-ttu-id="cfcd2-150">De kan också använda sina leveransadresser som faktureringsadress, för att göra kassaflödet enklare och snabbare.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-150">It also lets them  use their shipping address as the billing address, to make the checkout flow easier and faster.</span></span> <span data-ttu-id="cfcd2-151">Om egenskapen **Visa faktureringsadress** är inställd på **False** ska betalningsmodulen konfigureras på betalningssidan.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-151">If the **Show billing address** property is set to **False**, the payment module should be configured on the checkout page.</span></span>

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="cfcd2-152">Lägg till en betalningsmodul på en kassasida och ställa in de obligatoriska egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-152">Add a payment module to a checkout page and set the required properties</span></span>

<span data-ttu-id="cfcd2-153">En betalningsmodul kan bara läggas till i en betalningsmodul.</span><span class="sxs-lookup"><span data-stu-id="cfcd2-153">A payment module can be added only to a checkout module.</span></span> <span data-ttu-id="cfcd2-154">Mer information om hur du konfigurera en betalningsmodul för en kassasida, se [kassamodul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="cfcd2-154">For more information about how to configure a payment module for a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cfcd2-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cfcd2-155">Additional resources</span></span>

[<span data-ttu-id="cfcd2-156">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="cfcd2-157">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="cfcd2-158">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="cfcd2-159">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="cfcd2-159">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="cfcd2-160">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="cfcd2-160">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="cfcd2-161">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-161">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="cfcd2-162">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="cfcd2-162">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="cfcd2-163">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="cfcd2-163">Dynamics 365 Payment Connector for Adyen</span></span>](dev-itpro/adyen-connector.md)

[<span data-ttu-id="cfcd2-164">Stark kundautentisering med Adyen</span><span class="sxs-lookup"><span data-stu-id="cfcd2-164">Strong Customer Authentication using Adyen</span></span>](adyen_redirect.md)
