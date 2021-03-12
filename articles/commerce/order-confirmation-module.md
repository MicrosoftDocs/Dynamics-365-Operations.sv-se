---
title: Orderbekräftelsemodulen
description: Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9d916d2687777403f2b0df7c35171948ad2fb7db
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972763"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="99bb3-103">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="99bb3-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="99bb3-104">Det här avsnittet handlar om orderbekräftelsemoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="99bb3-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="99bb3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="99bb3-105">Overview</span></span>

<span data-ttu-id="99bb3-106">Orderbekräftelsemodulen används för att visa bekräftelseinformationen när en order har lagts.</span><span class="sxs-lookup"><span data-stu-id="99bb3-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="99bb3-107">Denna visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation, upphämtningsalternativ och leveransmetod.</span><span class="sxs-lookup"><span data-stu-id="99bb3-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="99bb3-108">Egenskaper för orderbekräftelsemodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-108">Order confirmation module properties</span></span>

| <span data-ttu-id="99bb3-109">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="99bb3-109">Property name</span></span>  | <span data-ttu-id="99bb3-110">Värden</span><span class="sxs-lookup"><span data-stu-id="99bb3-110">Values</span></span> | <span data-ttu-id="99bb3-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="99bb3-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="99bb3-112">Rubrik</span><span class="sxs-lookup"><span data-stu-id="99bb3-112">Heading</span></span>        | <span data-ttu-id="99bb3-113">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="99bb3-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="99bb3-114">Orderbekräftelsemodulen kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="99bb3-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="99bb3-115">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="99bb3-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="99bb3-116">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="99bb3-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="99bb3-117">Kontaktnummer</span><span class="sxs-lookup"><span data-stu-id="99bb3-117">Contact number</span></span> | <span data-ttu-id="99bb3-118">Text</span><span class="sxs-lookup"><span data-stu-id="99bb3-118">Text</span></span> | <span data-ttu-id="99bb3-119">Ett kontaktnummer kan anges för frågor som är relaterade till order.</span><span class="sxs-lookup"><span data-stu-id="99bb3-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="99bb3-120">Visa information om upphämtningstidpunkt</span><span class="sxs-lookup"><span data-stu-id="99bb3-120">Show pickup timeslot information</span></span> | <span data-ttu-id="99bb3-121">Sant eller falskt</span><span class="sxs-lookup"><span data-stu-id="99bb3-121">True or False</span></span> | <span data-ttu-id="99bb3-122">Denna egenskap är tillgänglig i Dynamics 365 Commerce 10.0.15 och senare.</span><span class="sxs-lookup"><span data-stu-id="99bb3-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="99bb3-123">När värdet är "true" visas information om tidpunkt för upphämtning om en upphämtningsartikel avses</span><span class="sxs-lookup"><span data-stu-id="99bb3-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="99bb3-124">Moduler som kan användas på en sida för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="99bb3-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="99bb3-125">När du skapar en sida för orderbekräfta kan du lägga till andra relevanta moduler utöver orderbekräftelsemodulen.</span><span class="sxs-lookup"><span data-stu-id="99bb3-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="99bb3-126">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="99bb3-126">Here are some examples:</span></span>

- <span data-ttu-id="99bb3-127">**Rekommendationsmodul** – Rekommendationsmodulen kan läggas till på sidan för orderbekräftelse för att föreslå andra produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="99bb3-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="99bb3-128">**Marknadsföringsmoduler** – Valfri marknadsföringsmodul kan läggas till på sidan för orderbekräftelse om du vill visa marknadsföringsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="99bb3-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="99bb3-129">Lägg till en orderbekräftelsemodul på en sida</span><span class="sxs-lookup"><span data-stu-id="99bb3-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="99bb3-130">Om du vill lägga till en orderbekräftelsemodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="99bb3-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="99bb3-131">Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="99bb3-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="99bb3-132">I dialogrutan **Ny mall**, under **Mallnamn**, anger du namnet **Orderbekräftelsemall** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-133">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="99bb3-134">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-135">I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="99bb3-136">I dialogrutan **Lägg till modul** väljer du modulen **Orderbekräftelse** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-137">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska mallen.</span><span class="sxs-lookup"><span data-stu-id="99bb3-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="99bb3-138">Modulen för orderbekräftelse återges inte eftersom den kräver en kontext för orderbekräftelsenumret.</span><span class="sxs-lookup"><span data-stu-id="99bb3-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="99bb3-139">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="99bb3-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="99bb3-140">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="99bb3-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="99bb3-141">I dialogrutan **Välj en mall** väljer du en **Orderbekräftelsemall**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="99bb3-142">Under **Sidnamn** anger du **Orderbekräftelsesida** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-143">I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="99bb3-144">I dialogrutan **Lägg till modul** väljer du modulen **Orderbekräftelse** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-145">I egenskapsrutan för orderbekräftelsemodulen väljer du **Rubrik** bredvid pennsymbolen.</span><span class="sxs-lookup"><span data-stu-id="99bb3-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="99bb3-146">I fältet **Rubriktext** i dialogrutan **Rubrik** anger du rubriktexten **Orderbekräftelse** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="99bb3-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="99bb3-147">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="99bb3-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="99bb3-148">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="99bb3-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99bb3-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="99bb3-149">Additional resources</span></span>

[<span data-ttu-id="99bb3-150">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="99bb3-151">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="99bb3-152">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="99bb3-153">Betalningsmodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="99bb3-154">Modul för leveransadress</span><span class="sxs-lookup"><span data-stu-id="99bb3-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="99bb3-155">Modul för leveransalternativ</span><span class="sxs-lookup"><span data-stu-id="99bb3-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="99bb3-156">Informationsmodul för upphämtning</span><span class="sxs-lookup"><span data-stu-id="99bb3-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="99bb3-157">Presentkortsmodul</span><span class="sxs-lookup"><span data-stu-id="99bb3-157">Gift card module</span></span>](add-giftcard.md)
