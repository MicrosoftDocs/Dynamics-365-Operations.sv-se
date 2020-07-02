---
title: Orderinformationsmodul
description: Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2ec629d9fd027be01652351ab1c99001e063e30
ms.sourcegitcommit: 49656661c89c864e8e067259a601c3bbceb8bef4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2020
ms.locfileid: "3464940"
---
# <a name="order-details-module"></a><span data-ttu-id="2ca8d-103">Orderinformationsmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2ca8d-104">Det här avsnittet handlar om orderinformationsmoduler och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2ca8d-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="2ca8d-105">Overview</span></span>

<span data-ttu-id="2ca8d-106">Orderinformationsmodul används för att visa bekräftelseinformationen när en order har placerats.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="2ca8d-107">Det visar order bekräftelse-ID, orderns kontaktinformation och annan orderinformation, till exempel de artiklar som har köpts, betalningsinformation och leveransmetoden.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="2ca8d-108">Egenskaper för orderdetaljmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-108">Order details module properties</span></span>

| <span data-ttu-id="2ca8d-109">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2ca8d-109">Property name</span></span>  | <span data-ttu-id="2ca8d-110">Värden</span><span class="sxs-lookup"><span data-stu-id="2ca8d-110">Values</span></span> | <span data-ttu-id="2ca8d-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2ca8d-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="2ca8d-112">Rubrik</span><span class="sxs-lookup"><span data-stu-id="2ca8d-112">Heading</span></span>        | <span data-ttu-id="2ca8d-113">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="2ca8d-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="2ca8d-114">Orderdetaljmodulen kan ha en rubrik.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-114">The order details module can have a heading.</span></span> <span data-ttu-id="2ca8d-115">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="2ca8d-116">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="2ca8d-117">Kontaktnummer</span><span class="sxs-lookup"><span data-stu-id="2ca8d-117">Contact number</span></span> | <span data-ttu-id="2ca8d-118">Text</span><span class="sxs-lookup"><span data-stu-id="2ca8d-118">Text</span></span> | <span data-ttu-id="2ca8d-119">Ett kontaktnummer kan anges för frågor som är relaterade till order.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="2ca8d-120">Moduler som kan användas på en sida för orderinformation</span><span class="sxs-lookup"><span data-stu-id="2ca8d-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="2ca8d-121">När du skapar en sida för orderinformation kan du lägga till andra relevanta moduler utöver orderinformationsmodulen.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="2ca8d-122">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="2ca8d-122">Here are some examples:</span></span>

- <span data-ttu-id="2ca8d-123">**Rekommendationsmodul** – modulen rekommendationer kan läggs till på sidan för orderinformation för att föreslå andra produkter till kunden.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="2ca8d-124">**Marknadsföringsmoduler** – valfri marknadsföringsmodul kan läggas till på sidan orderinformation om du vill visa marknadsföringsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="2ca8d-125">Lägg till orderdetaljmodul till en sida</span><span class="sxs-lookup"><span data-stu-id="2ca8d-125">Add an order details module to a page</span></span>

<span data-ttu-id="2ca8d-126">Om du vill lägga till en orderdetaljmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="2ca8d-127">Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-127">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="2ca8d-128">I dialogrutan **Ny mall** under **Mallnamn**, ange ett namn **Orderinformationsmall** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-128">In the **New Template** dialog box, under **Template name**, enter the name **Order details template**, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-129">I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-129">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2ca8d-130">I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-131">I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-131">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2ca8d-132">I dialogrutan **Lägg till modul** välj modulen **orderinformation** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-133">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska mallen.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-133">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="2ca8d-134">Orderinformationsmodulen kommer inte återges eftersom den kräver en kontext för orderbekräftelsenumret.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="2ca8d-135">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="2ca8d-136">Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-136">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="2ca8d-137">I dialogrutan **Välj en mall** väljer du en **Orderinnehållsmall**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="2ca8d-138">Under **Sidnamn**, ange **Orderinnehållsida** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-138">Under **Page name**, enter **Order details page**, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-139">I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-139">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2ca8d-140">I dialogrutan **Lägg till modul** välj modulen **orderinformation** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-141">I egenskapsrutan i dragspelsmodulen väljer du **rubrik** bredvid pennsymbolen.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="2ca8d-142">I fältet **Rubriktext** i dialogrutan **Rubrik** ange rubriktext **Orderdetaljer** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details**, and then select **OK**.</span></span>
1. <span data-ttu-id="2ca8d-143">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-143">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="2ca8d-144">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="2ca8d-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ca8d-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2ca8d-145">Additional resources</span></span>

[<span data-ttu-id="2ca8d-146">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="2ca8d-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2ca8d-147">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-147">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2ca8d-148">Köp en boxmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-148">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2ca8d-149">Vagnmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2ca8d-150">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-150">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="2ca8d-151">Rubrikmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-151">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="2ca8d-152">Sidfotmodul</span><span class="sxs-lookup"><span data-stu-id="2ca8d-152">Footer module</span></span>](author-footer-module.md)
