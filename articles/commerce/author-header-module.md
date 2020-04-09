---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025707"
---
# <a name="header-module"></a><span data-ttu-id="1597c-103">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="1597c-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="1597c-104">Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar sidhuvud i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1597c-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1597c-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="1597c-105">Overview</span></span>

<span data-ttu-id="1597c-106">I Dynamics 365 Commerce består ett sidhuvud av flera moduler, t.ex. rubrik, navigeringsmeny, sökning, annonsbanderoll och moduler för godkännande.</span><span class="sxs-lookup"><span data-stu-id="1597c-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="1597c-107">Modulen rubrik innehåller en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen, en vagnsymbol, en önskelista-symbol, inloggningsalternativ och sökfältet.</span><span class="sxs-lookup"><span data-stu-id="1597c-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="1597c-108">En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet).</span><span class="sxs-lookup"><span data-stu-id="1597c-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="1597c-109">Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).</span><span class="sxs-lookup"><span data-stu-id="1597c-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="1597c-110">Egenskaper för sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="1597c-110">Properties of a header module</span></span>

<span data-ttu-id="1597c-111">En sidhuvudmodul stöder egenskaperna **logotypbild**, **logotyplänk** och **länkar till mitt konto**.</span><span class="sxs-lookup"><span data-stu-id="1597c-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="1597c-112">Egenskaperna **logotypbild** och **logotyplänk** används för att definiera en logotyp på sidan.</span><span class="sxs-lookup"><span data-stu-id="1597c-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="1597c-113">Mer information finns i [Lägg till en logotyp](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="1597c-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="1597c-114">Egenskapen **länkar till mitt konto** kan användas för att definiera kontosidor som webbplatsägaren vill visa snabblänkar för i rubriken.</span><span class="sxs-lookup"><span data-stu-id="1597c-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="1597c-115">Moduler som är tillgängliga i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="1597c-115">Modules that are available in a header module</span></span>

<span data-ttu-id="1597c-116">Följande moduler kan användas i en sidhuvudmodul:</span><span class="sxs-lookup"><span data-stu-id="1597c-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="1597c-117">**Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar.</span><span class="sxs-lookup"><span data-stu-id="1597c-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="1597c-118">Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1597c-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="1597c-119">Navigeringsmenyn har egenskapen **navigeringskälla** som används för att ange navigeringsmenyobjekt och statiska menyalternativ i Retail Server som en källa.</span><span class="sxs-lookup"><span data-stu-id="1597c-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="1597c-120">Om statiska menyalternativ anges som källa kan relativa länkar till andra sidor på webbplatsen tillhandahållas.</span><span class="sxs-lookup"><span data-stu-id="1597c-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="1597c-121">Konfigurerade artiklar visas sedan som sidhuvudnavigering.</span><span class="sxs-lookup"><span data-stu-id="1597c-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="1597c-122">**Sökfält** – Sökmodulen låter användarna ange söktermer så att de kan söka efter produkter.</span><span class="sxs-lookup"><span data-stu-id="1597c-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="1597c-123">URL-adressen till standardsöksidan och parametrarna för sökning måste ges i tillägg till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="1597c-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="1597c-124">Sökmodulen har egenskaper som gör att du kan hindra sökknappen eller etiketten efter behov.</span><span class="sxs-lookup"><span data-stu-id="1597c-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="1597c-125">Sökmodulen stöder också automatiska förslag, t.ex. produkt, nyckelord och kategorisökningsresultat.</span><span class="sxs-lookup"><span data-stu-id="1597c-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="1597c-126">Skapa en sidhuvudmodul för en sida</span><span class="sxs-lookup"><span data-stu-id="1597c-126">Create a header module for a page</span></span>

<span data-ttu-id="1597c-127">Gör så här om du vill skapa en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="1597c-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="1597c-128">Skapa ett fragment med namnet **sidhuvudfragment**och lägg till en modul för behållare.</span><span class="sxs-lookup"><span data-stu-id="1597c-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="1597c-129">I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="1597c-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="1597c-130">Lägg till moduler för annonsbanderoll och cookies i behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="1597c-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="1597c-131">Lägg till en annan behållarmodul till fragmentet och ställ in egenskapen **bredd** till **fyll behållare**.</span><span class="sxs-lookup"><span data-stu-id="1597c-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="1597c-132">Lägg till en sidhuvudmodul till den andra behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="1597c-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="1597c-133">I facket **Navigeringsmeny** i sidhuvudmodulen, lägg till en modul för navigeringsmeny.</span><span class="sxs-lookup"><span data-stu-id="1597c-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="1597c-134">Konfigurera egenskaperna för modulen för navigeringmenyn i egenskapsfönstret för modulen navigering.</span><span class="sxs-lookup"><span data-stu-id="1597c-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="1597c-135">Lägg till facket **sök** i sidhuvudmodulens sökmotor.</span><span class="sxs-lookup"><span data-stu-id="1597c-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="1597c-136">Konfigurera egenskaperna för sökmodulen för navigeringmenyn i egenskapsfönstret för sökmodulen.</span><span class="sxs-lookup"><span data-stu-id="1597c-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="1597c-137">Spara sidfragmentet, slutför redigeringen och publicera det.</span><span class="sxs-lookup"><span data-stu-id="1597c-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="1597c-138">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="1597c-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="1597c-139">I facket **Huvud** lägger du till standardsidan, lägg till sidhuvudfragmentet som innehåller sidhuvudmodulen i rubriken.</span><span class="sxs-lookup"><span data-stu-id="1597c-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="1597c-140">Spara mallen, slutför redigeringen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="1597c-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1597c-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1597c-141">Additional resources</span></span>

[<span data-ttu-id="1597c-142">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="1597c-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1597c-143">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="1597c-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="1597c-144">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="1597c-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="1597c-145">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="1597c-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="1597c-146">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="1597c-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="1597c-147">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="1597c-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="1597c-148">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="1597c-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="1597c-149">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="1597c-149">Footer module</span></span>](author-footer-module.md)
