---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686632"
---
# <a name="header-module"></a><span data-ttu-id="346c2-103">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="346c2-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="346c2-104">Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="346c2-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="346c2-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="346c2-105">Overview</span></span>

<span data-ttu-id="346c2-106">I Dynamics 365 Commerce består ett sidhuvud av flera moduler, t.ex. rubrik, navigeringsmeny, sökning, annonsbanderoll och moduler för godkännande.</span><span class="sxs-lookup"><span data-stu-id="346c2-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="346c2-107">Modulen rubrik innehåller en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen, en vagnsymbol, en önskelista-symbol, inloggningsalternativ och sökfältet.</span><span class="sxs-lookup"><span data-stu-id="346c2-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="346c2-108">En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet).</span><span class="sxs-lookup"><span data-stu-id="346c2-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="346c2-109">Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).</span><span class="sxs-lookup"><span data-stu-id="346c2-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="346c2-110">Följande bild visar ett exempel på en rubrikmodul på en startsida.</span><span class="sxs-lookup"><span data-stu-id="346c2-110">The following image shows an example of a header module on a home page.</span></span>

![Exempel på en rubrikmodul](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="346c2-112">Egenskaper för sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="346c2-112">Properties of a header module</span></span>

<span data-ttu-id="346c2-113">En sidhuvudmodul stöder egenskaperna **logotypbild**, **logotyplänk** och **länkar till mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="346c2-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="346c2-114">Egenskaperna **logotypbild** och **logotyplänk** används för att definiera en logotyp på sidan.</span><span class="sxs-lookup"><span data-stu-id="346c2-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="346c2-115">Mer information finns i [Lägg till en logotyp](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="346c2-116">Egenskapen **länkar till mitt konto** kan användas för att definiera kontosidor som webbplatsägaren vill visa snabblänkar för i rubriken.</span><span class="sxs-lookup"><span data-stu-id="346c2-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="346c2-117">Moduler som är tillgängliga i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="346c2-117">Modules that are available in a header module</span></span>

<span data-ttu-id="346c2-118">Följande moduler kan användas i en sidhuvudmodul:</span><span class="sxs-lookup"><span data-stu-id="346c2-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="346c2-119">**Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar.</span><span class="sxs-lookup"><span data-stu-id="346c2-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="346c2-120">Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="346c2-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="346c2-121">Navigeringsmenyn har egenskapen **navigeringskälla** som används för att ange navigeringsmenyobjekt och statiska menyalternativ i Retail Server som en källa.</span><span class="sxs-lookup"><span data-stu-id="346c2-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="346c2-122">Om statiska menyalternativ anges som källa kan relativa länkar till andra sidor på webbplatsen tillhandahållas.</span><span class="sxs-lookup"><span data-stu-id="346c2-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="346c2-123">Konfigurerade artiklar visas sedan som sidhuvudnavigering.</span><span class="sxs-lookup"><span data-stu-id="346c2-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="346c2-124">**Sökfält** – Sökmodulen låter användarna ange söktermer så att de kan söka efter produkter.</span><span class="sxs-lookup"><span data-stu-id="346c2-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="346c2-125">URL-adressen till standardsöksidan och parametrarna för sökning måste ges i tillägg till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="346c2-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="346c2-126">Sökmodulen har egenskaper som gör att du kan hindra sökknappen eller etiketten efter behov.</span><span class="sxs-lookup"><span data-stu-id="346c2-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="346c2-127">Sökmodulen stöder också automatiska förslag, t.ex. produkt, nyckelord och kategorisökningsresultat.</span><span class="sxs-lookup"><span data-stu-id="346c2-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="346c2-128">**Vagnikon** – modulen kundvagn representerar vagnikonen, som visar antalet artiklar i vagnen vid en given tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="346c2-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="346c2-129">Mer information finns i avsnittet [modulen vagnikonen](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="346c2-130">Skapa en sidhuvudmodul för en sida</span><span class="sxs-lookup"><span data-stu-id="346c2-130">Create a header module for a page</span></span>

<span data-ttu-id="346c2-131">Gör så här om du vill skapa en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="346c2-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="346c2-132">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="346c2-132">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="346c2-133">I dialogrutan **Nytt sidfragment** väljer du modul för **Behållare**, anger ett namn på sidan och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-133">In the **New page fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-134">Välj platse **standardenhet** och sedan i egenskapsfönstret till höger, ange egenskapen **Bredd** till **Fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="346c2-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="346c2-135">I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="346c2-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-136">I dialogrutan **Lägg till modul** välj modulerna **Kampanjbanderoll** och **Cookie-samtycke** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-137">I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="346c2-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-138">I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-139">Välj platsen **behållare** och sedan i egenskapsfönstret till höger, ange egenskapen **Bredd** till **Fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="346c2-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="346c2-140">I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="346c2-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-141">I dialogrutan **Lägg till modul**, välj modulen **Rubrik** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-142">I platsen för rubrikmodul väljer du **Navigeringsmeny**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="346c2-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-143">I dialogrutan **Lägg till modul** välj modulen **Navigeringsmeny** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-144">Konfigurera egenskaperna efter behov i egenskapsfönstret för modulen för navigeringmenyn.</span><span class="sxs-lookup"><span data-stu-id="346c2-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="346c2-145">I platsen för rubrikmodul väljer du **Sök**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="346c2-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-146">I dialogrutan **Lägg till modul**, välj modulen **Sök** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-147">Konfigurera egenskaperna efter behov i egenskapsfönstret för sökmodulen.</span><span class="sxs-lookup"><span data-stu-id="346c2-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="346c2-148">I platsen för rubrikmodul väljer du **Kundvagnsikon**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="346c2-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="346c2-149">I dialogrutan **Lägg till modul**, välj modulen **Kundvagnsikon** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="346c2-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="346c2-150">Konfigurera egenskaperna efter behov i egenskapsfönstret för modulen för kundvagnsikon.</span><span class="sxs-lookup"><span data-stu-id="346c2-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="346c2-151">Om du vill att kundvagnsikonen ska visa en kundvagnssammanfattning (även kallad en minikundvagn) när användarna hovrar över den väljer du **Visa minikundvagnen**.</span><span class="sxs-lookup"><span data-stu-id="346c2-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="346c2-152">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="346c2-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="346c2-153">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="346c2-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="346c2-154">På platsen **Rubrik** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.</span><span class="sxs-lookup"><span data-stu-id="346c2-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="346c2-155">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="346c2-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="346c2-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="346c2-156">Additional resources</span></span>

[<span data-ttu-id="346c2-157">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="346c2-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="346c2-158">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="346c2-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="346c2-159">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="346c2-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="346c2-160">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="346c2-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="346c2-161">Vagnikonmodul</span><span class="sxs-lookup"><span data-stu-id="346c2-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="346c2-162">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="346c2-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="346c2-163">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="346c2-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="346c2-164">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="346c2-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="346c2-165">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="346c2-165">Footer module</span></span>](author-footer-module.md)
