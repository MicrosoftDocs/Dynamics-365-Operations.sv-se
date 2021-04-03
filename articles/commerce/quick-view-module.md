---
title: Snabbvisningsmodul
description: Detta ämne handlar om snabbvisningsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 07fbf8d4115561808b7c61489b343e1c72dd1b6d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243803"
---
# <a name="quick-view-module"></a><span data-ttu-id="6fb45-103">Snabbvymodul</span><span class="sxs-lookup"><span data-stu-id="6fb45-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6fb45-104">Detta ämne handlar om snabbvisningsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6fb45-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6fb45-105">I snabbvisningsmodulen kan användarna snabbt visa produktinformation när de bläddrar bland produkter på en listsida och lägger till en eller flera produkter i kundvagnen från listsidan, detta utan att behöva gå till produktinformationssidan (PDP).</span><span class="sxs-lookup"><span data-stu-id="6fb45-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="6fb45-106">Snabbvisningsmodulen ger en översikt över produktinformationen som användarna behöver för att fatta ett beslut om att "lägga till i kundvagnen".</span><span class="sxs-lookup"><span data-stu-id="6fb45-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="6fb45-107">Den ger också en länk till PDP, så att användare kan visa ytterligare produktinformation och inköpsalternativ.</span><span class="sxs-lookup"><span data-stu-id="6fb45-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="6fb45-108">Snabbvisningsmodulen stöds av modulerna för [produktsamling](product-collection-module-overview.md) och [sökresultat](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="6fb45-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fb45-109">Snabbvisningsmodulen är tillgänglig i från och med Commerce-version 10.0.17.</span><span class="sxs-lookup"><span data-stu-id="6fb45-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="6fb45-110">Följande bild visar ett exempel på en snabbvisningsmodul på en produktlistsida.</span><span class="sxs-lookup"><span data-stu-id="6fb45-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Exempel på en snabbvisningsmodul på en produktlistsida](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="6fb45-112">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="6fb45-112">Module properties</span></span>

<span data-ttu-id="6fb45-113">Snabbvisningsmodulen stöder delvis samma funktioner som modulen för inköpsruta.</span><span class="sxs-lookup"><span data-stu-id="6fb45-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="6fb45-114">Därför liknar egenskaperna för en snabbvisningsmodul egenskaperna hos en modul för inköpsruta.</span><span class="sxs-lookup"><span data-stu-id="6fb45-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="6fb45-115">Egenskap</span><span class="sxs-lookup"><span data-stu-id="6fb45-115">Property</span></span> | <span data-ttu-id="6fb45-116">Värden</span><span class="sxs-lookup"><span data-stu-id="6fb45-116">Values</span></span> | <span data-ttu-id="6fb45-117">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6fb45-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="6fb45-118">Rubriktagg</span><span class="sxs-lookup"><span data-stu-id="6fb45-118">Heading tag</span></span> | <span data-ttu-id="6fb45-119">**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**</span><span class="sxs-lookup"><span data-stu-id="6fb45-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="6fb45-120">Denna egenskap definierar rubriketiketten för produktrubriken.</span><span class="sxs-lookup"><span data-stu-id="6fb45-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="6fb45-121">Om snabbvisningsmodulen finns högst upp på sidan ska den här egenskapen ställas in på **H1** för att uppfylla tillgänglighetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="6fb45-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="6fb45-122">Tillåt anpassat pris</span><span class="sxs-lookup"><span data-stu-id="6fb45-122">Allow custom price</span></span> | <span data-ttu-id="6fb45-123">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="6fb45-123">**True** or **False**</span></span> | <span data-ttu-id="6fb45-124">Om egenskapen har angetts som **True** kan användaren ange ett eget pris.</span><span class="sxs-lookup"><span data-stu-id="6fb45-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="6fb45-125">Lägsta pris</span><span class="sxs-lookup"><span data-stu-id="6fb45-125">Minimum price</span></span> | <span data-ttu-id="6fb45-126">Heltal</span><span class="sxs-lookup"><span data-stu-id="6fb45-126">Integer</span></span> | <span data-ttu-id="6fb45-127">Denna egenskap kan bara användas om egenskapen **Tillåt anpassat pris** angetts som **True**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="6fb45-128">De definierar det lägsta pris som användaren kan ange (till exempel 1 USD).</span><span class="sxs-lookup"><span data-stu-id="6fb45-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="6fb45-129">Maxpris</span><span class="sxs-lookup"><span data-stu-id="6fb45-129">Maximum price</span></span> | <span data-ttu-id="6fb45-130">Heltal</span><span class="sxs-lookup"><span data-stu-id="6fb45-130">Integer</span></span> | <span data-ttu-id="6fb45-131">Denna egenskap kan bara användas om egenskapen **Tillåt anpassat pris** angetts som **True**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="6fb45-132">Den definierar det högsta pris som användaren kan ange (till exempel 1 000 USD).</span><span class="sxs-lookup"><span data-stu-id="6fb45-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="6fb45-133">Inställningar för Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="6fb45-133">Commerce site builder settings</span></span>

<span data-ttu-id="6fb45-134">I precis som modulen för inköpsruta beaktar snabbvisningsmodulen inställningarna på **Webbplatsinställningar \> Tillägg \> Lägg till produkt i kundvagnen**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="6fb45-135">Inställningen **Navigera till kundvagnssidan** ignoreras emellertid eftersom detta är inkonsekvent med syftet med snabbvisningsmodulen, nämligen att låta användarna bläddra bland flera produkter på en listsida och lägga till dem i kundvagnen utan att lämna listsidan.</span><span class="sxs-lookup"><span data-stu-id="6fb45-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="6fb45-136">Lägg till en modul för snabbvisning i en produktsamlingsmodul</span><span class="sxs-lookup"><span data-stu-id="6fb45-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="6fb45-137">En snabbvisningsmodul kan läggas till i modulerna för produktsamling och sökresultat.</span><span class="sxs-lookup"><span data-stu-id="6fb45-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="6fb45-138">Om du vill lägga till en snabbvisningsmodul i en produktsamlingsmodul i Commerce-webbplatsbyggaren följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="6fb45-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6fb45-139">Gå till **Sidor** och välj sedan startsidan för Fabrikam-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6fb45-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="6fb45-140">Gå till valfri modul för **Produktsamlingmodul** på startsidan, välj ellipsen (**...**) och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6fb45-141">I dialogrutan **Lägg till modul** väljer du modulen **Snabbvisning** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6fb45-142">I egenskapsfönstret i modulen **Snabbvisning** väljer du **Rubrik**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="6fb45-143">I dialogrutan **Rubrik** anger du fältet **Rubriknivå** som **H2** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fb45-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="6fb45-144">Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="6fb45-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6fb45-145">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6fb45-145">Additional resources</span></span>

[<span data-ttu-id="6fb45-146">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="6fb45-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6fb45-147">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="6fb45-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6fb45-148">Produktsamlingsmodul</span><span class="sxs-lookup"><span data-stu-id="6fb45-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="6fb45-149">Sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="6fb45-149">Search results module</span></span>](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]