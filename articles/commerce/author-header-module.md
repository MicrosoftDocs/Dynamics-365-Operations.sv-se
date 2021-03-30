---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 569fb5ac3d30be30044ef9b928ecf1f6dde20aab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211434"
---
# <a name="header-module"></a><span data-ttu-id="d363d-103">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="d363d-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d363d-104">Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d363d-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d363d-105">I Dynamics 365 Commerce konfigureras ett sidrubrik som ett fragment som innehåller modulerna rubrik, annonsbanderoll och cookie-samtycke.</span><span class="sxs-lookup"><span data-stu-id="d363d-105">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="d363d-106">Modulen rubrik innehåller en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen, en vagnmodul, en önskelista-symbol, inloggningsalternativ och sökfältet.</span><span class="sxs-lookup"><span data-stu-id="d363d-106">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="d363d-107">En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet).</span><span class="sxs-lookup"><span data-stu-id="d363d-107">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="d363d-108">Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).</span><span class="sxs-lookup"><span data-stu-id="d363d-108">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="d363d-109">Följande bild visar ett exempel på en rubrikmodul på en startsida.</span><span class="sxs-lookup"><span data-stu-id="d363d-109">The following image shows an example of a header module on a home page.</span></span>

![Exempel på en rubrikmodul](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="d363d-111">Egenskaper för sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="d363d-111">Properties of a header module</span></span>

<span data-ttu-id="d363d-112">En sidhuvudmodul stöder egenskaperna **logotypbild**, **logotyplänk** och **länkar till mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="d363d-112">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="d363d-113">Egenskaperna **logotypbild** och **logotyplänk** används för att definiera en logotyp på sidan.</span><span class="sxs-lookup"><span data-stu-id="d363d-113">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="d363d-114">Mer information finns i [Lägg till en logotyp](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="d363d-114">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="d363d-115">Egenskapen **länkar till mitt konto** kan användas för att definiera kontosidor som webbplatsägaren vill visa snabblänkar för i rubriken.</span><span class="sxs-lookup"><span data-stu-id="d363d-115">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="d363d-116">Moduler som är tillgängliga i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="d363d-116">Modules that are available within a header module</span></span>

<span data-ttu-id="d363d-117">Följande moduler kan användas i en sidhuvudmodul:</span><span class="sxs-lookup"><span data-stu-id="d363d-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="d363d-118">**Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar.</span><span class="sxs-lookup"><span data-stu-id="d363d-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="d363d-119">Mer information finns i [Modulen navigeringsmeny](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="d363d-119">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="d363d-120">**Sökfält** – Sökmodulen låter användarna ange söktermer så att de kan söka efter produkter.</span><span class="sxs-lookup"><span data-stu-id="d363d-120">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="d363d-121">URL-adressen till standardsöksidan och parametrarna för sökning måste ges i tillägg till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="d363d-121">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="d363d-122">Sökmodulen har egenskaper som gör att du kan hindra sökknappen eller etiketten efter behov.</span><span class="sxs-lookup"><span data-stu-id="d363d-122">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="d363d-123">Sökmodulen stöder också automatiska förslag, t.ex. produkt, nyckelord och kategorisökningsresultat.</span><span class="sxs-lookup"><span data-stu-id="d363d-123">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="d363d-124">**Vagnikon** – modulen kundvagn representerar vagnikonen, som visar antalet artiklar i vagnen vid en given tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="d363d-124">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="d363d-125">Mer information finns i avsnittet [modulen vagnikonen](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="d363d-125">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="d363d-126">**Webbplatsväljare** – modulen webbplatsväljare gör det möjligt för användarna att bläddra mellan olika fördefinierade webbplatser, baserat på marknad, regioner och nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="d363d-126">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="d363d-127">Mer information finns i avsnittet [modulen webbplatsväljare](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="d363d-127">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="d363d-128">**Butiksväljare** – modulen butiksväljare kan inkluderas i huvudmodulens plats för butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="d363d-128">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="d363d-129">Användarna kan då bläddra bland och söka efter butiker i närheten.</span><span class="sxs-lookup"><span data-stu-id="d363d-129">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="d363d-130">Användare kan också ange en prioriterad butik.</span><span class="sxs-lookup"><span data-stu-id="d363d-130">Users can also specify a preferred store.</span></span> <span data-ttu-id="d363d-131">Denna butik visas sedan i rubriken.</span><span class="sxs-lookup"><span data-stu-id="d363d-131">That store will then be shown in the header.</span></span> <span data-ttu-id="d363d-132">Om modulen för butiksväljaren är inkluderad i huvudmodulen, måste egenskapen **Läge** ställas in för att **Hitta butiker**.</span><span class="sxs-lookup"><span data-stu-id="d363d-132">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="d363d-133">Mer information finns i avsnittet [modulen butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="d363d-133">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="d363d-134">Stöd för användning av modulen kundvagnikon i huvudmoduler finns i Dynamics 365 Commerce 10.0.11-versionen.</span><span class="sxs-lookup"><span data-stu-id="d363d-134">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="d363d-135">Stöd för användning av modulen webbplatsväljare i huvudmoduler finns i Dynamics 365 Commerce 10.0.14-versionen.</span><span class="sxs-lookup"><span data-stu-id="d363d-135">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="d363d-136">Stöd för användning av modulen butiksväljare i huvudmoduler finns i Dynamics 365 Commerce 10.0.15-versionen.</span><span class="sxs-lookup"><span data-stu-id="d363d-136">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="d363d-137">Skapa ett huvudfragment för en sida</span><span class="sxs-lookup"><span data-stu-id="d363d-137">Create a header fragment for a page</span></span>

<span data-ttu-id="d363d-138">Gör så här om du vill skapa ett huvudfragment.</span><span class="sxs-lookup"><span data-stu-id="d363d-138">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="d363d-139">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="d363d-139">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="d363d-140">I dialogrutan **Nytt fragment** väljer du modul för **Behållare**, anger ett namn på fragmentet och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-140">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-141">Välj platsen **standardenhet** och sedan i egenskapsfönstret till höger, ange egenskapen **Bredd** till **Fyll skärm**.</span><span class="sxs-lookup"><span data-stu-id="d363d-141">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="d363d-142">I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="d363d-142">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d363d-143">I dialogrutan **Lägg till modul** välj **Cookie-samtycke**, **Huvud** och **Kampanjbanderoll** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-143">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-144">I egenskapsfönstret i modulen **Kampanjbanderoll** välj **Lägg till meddelande** och välj sedan **Meddelande**.</span><span class="sxs-lookup"><span data-stu-id="d363d-144">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="d363d-145">I dialogrutan **Meddelande** lägg till text och länkar för säljinnehåll och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-145">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-146">I egenskapsfönstret för modulen **Cookie-samtycke** lägg till och konfigurera text och en länk till webbplatsens sekretesspolicy.</span><span class="sxs-lookup"><span data-stu-id="d363d-146">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="d363d-147">I platsen för rubrikmodul väljer du **Navigeringsmeny**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="d363d-147">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d363d-148">I dialogrutan **Lägg till modul** välj modulen **Navigeringsmeny** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-148">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-149">I egenskapsrutan för modulen navigeringsmeny under **källa för navigeringsmeny**, väljer du **butiksserver**.</span><span class="sxs-lookup"><span data-stu-id="d363d-149">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="d363d-150">I egenskapspanelen för navigeringsmenymodulen under **Statiska menyobjekt**, välj **Lägg till menyobjekt** och välj sedan **Menyobjekt**.</span><span class="sxs-lookup"><span data-stu-id="d363d-150">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="d363d-151">I dialogrutan **Menyobjekt** under **Menyobjekttext** ange "kontakt."</span><span class="sxs-lookup"><span data-stu-id="d363d-151">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="d363d-152">I dialogrutan **Menyobjekt** under **Länkmål för menyobjekt** välj **Lägg till en länk**.</span><span class="sxs-lookup"><span data-stu-id="d363d-152">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="d363d-153">I dialogrutan **Lägg till en länk** väljer du URL för webbplatsens sida "Kontakter" och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-153">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="d363d-154">I dialogrutan **Menyobjekt** väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-154">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="d363d-155">I platsen för rubrikmodul väljer du **Sök**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="d363d-155">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d363d-156">I dialogrutan **Lägg till modul**, välj modulen **Sök** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-156">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-157">Konfigurera egenskaperna efter behov i egenskapsfönstret för sökmodulen.</span><span class="sxs-lookup"><span data-stu-id="d363d-157">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="d363d-158">I platsen för rubrikmodul väljer du **Kundvagnsikon**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="d363d-158">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="d363d-159">I dialogrutan **Lägg till modul**, välj modulen **Kundvagnsikon** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d363d-159">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="d363d-160">Konfigurera egenskaperna efter behov i egenskapsfönstret för modulen för kundvagnsikon.</span><span class="sxs-lookup"><span data-stu-id="d363d-160">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="d363d-161">Om du vill att kundvagnsikonen ska visa en kundvagnssammanfattning (även kallad en minikundvagn) när användarna hovrar över den väljer du **Visa minikundvagnen**.</span><span class="sxs-lookup"><span data-stu-id="d363d-161">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="d363d-162">Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="d363d-162">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="d363d-163">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d363d-163">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="d363d-164">På platsen **Rubrik** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.</span><span class="sxs-lookup"><span data-stu-id="d363d-164">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="d363d-165">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="d363d-165">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d363d-166">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d363d-166">Additional resources</span></span>

[<span data-ttu-id="d363d-167">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="d363d-167">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d363d-168">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="d363d-168">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d363d-169">Ikon för kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="d363d-169">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="d363d-170">Modul med kampanjbanderoll</span><span class="sxs-lookup"><span data-stu-id="d363d-170">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="d363d-171">Modulen navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="d363d-171">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="d363d-172">Cookie-medgivande</span><span class="sxs-lookup"><span data-stu-id="d363d-172">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="d363d-173">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="d363d-173">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="d363d-174">Modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="d363d-174">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="d363d-175">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="d363d-175">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]