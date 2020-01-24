---
title: Modul för sidhuvud
description: Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885488"
---
# <a name="header-module"></a><span data-ttu-id="69592-103">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="69592-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="69592-104">Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69592-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="69592-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="69592-105">Overview</span></span>

<span data-ttu-id="69592-106">En sidhuvudmodul är en särskild behållare som används för att vara värd för alla moduler som ska visas i sidans huvud.</span><span class="sxs-lookup"><span data-stu-id="69592-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="69592-107">Det kan till exempel vara en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen och sökfältet.</span><span class="sxs-lookup"><span data-stu-id="69592-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="69592-108">En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet).</span><span class="sxs-lookup"><span data-stu-id="69592-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="69592-109">Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).</span><span class="sxs-lookup"><span data-stu-id="69592-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="69592-110">Egenskaper för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="69592-110">Properties of a header</span></span>

<span data-ttu-id="69592-111">Liksom generiska behållare stöder en sidhuvudmodul egenskaperna **rubrik** och **bredd**.</span><span class="sxs-lookup"><span data-stu-id="69592-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="69592-112">En sidhuvudmodul har flera platser.</span><span class="sxs-lookup"><span data-stu-id="69592-112">A header module has multiple slots.</span></span> <span data-ttu-id="69592-113">Det finns till exempel kortplatser för informationsmeddelanden, navigeringsmeny, logotyp, sökfält, ikon för vagn, ikon för önskelista och kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="69592-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="69592-114">Varje plats stöder en viss uppsättning moduler.</span><span class="sxs-lookup"><span data-stu-id="69592-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="69592-115">Moduler som är tillgängliga i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="69592-115">Modules that are available in a header module</span></span>

<span data-ttu-id="69592-116">Följande moduler kan användas i en sidhuvudmodul:</span><span class="sxs-lookup"><span data-stu-id="69592-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="69592-117">**Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar.</span><span class="sxs-lookup"><span data-stu-id="69592-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="69592-118">Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="69592-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="69592-119">Konfigurerade artiklar visas sedan som sidhuvudnavigering.</span><span class="sxs-lookup"><span data-stu-id="69592-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="69592-120">Dessutom kan statiska navigeringslänkar konfigureras och relativa länkar till andra sidor på näthandelsplatsen kan tillhandahållas.</span><span class="sxs-lookup"><span data-stu-id="69592-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="69592-121">Själva sidhuvudet kan justeras åt vänster, höger eller centrerat.</span><span class="sxs-lookup"><span data-stu-id="69592-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="69592-122">**Vagnikon** – vagnikonen är en särskild ikon som representerar vagnen.</span><span class="sxs-lookup"><span data-stu-id="69592-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="69592-123">Det visas i sidhuvudet och anger antalet artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="69592-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="69592-124">En länk till vagnsidan ska medfölja vagnikonen, så att kunder kan dirigeras om till vagnsidan när de interagerar med ikonen.</span><span class="sxs-lookup"><span data-stu-id="69592-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="69592-125">**Ikonen önskelista** – Ikonen önskelista visas i sidhuvudet och anger antalet artiklar som har lagts till i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="69592-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="69592-126">En länk till sidan för önskelista ska medfölja den här ikonen, så att kunder kan dirigeras om till sidan för önskelista när de interagerar med ikonen.</span><span class="sxs-lookup"><span data-stu-id="69592-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="69592-127">**Inloggningsmodul** – inloggningsmodulen visas i sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="69592-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="69592-128">Kunder kan antingen logga in på sitt konto eller registrera sig för ett konto.</span><span class="sxs-lookup"><span data-stu-id="69592-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="69592-129">Om kunden redan är inloggad kan modulen konfigureras så att den visar länkar till kontosidan, sidan för orderhistorik eller en annan sida.</span><span class="sxs-lookup"><span data-stu-id="69592-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="69592-130">**Logotypmodul** – den här modulen visar logotypen som representerar återförsäljaren och varumärket.</span><span class="sxs-lookup"><span data-stu-id="69592-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="69592-131">Det är en bild som har en länk.</span><span class="sxs-lookup"><span data-stu-id="69592-131">It's an image that has a link.</span></span> <span data-ttu-id="69592-132">Länken konfigureras vanligtvis så att den har en omdirigering till startsidan, vilket innebär att kunderna snabbt kan gå tillbaka till startsidan från vilken sida som helst på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="69592-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="69592-133">**Varning** – en notifiering visas i sidhuvudet och används för att visa ett infogat meddelande som gäller alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="69592-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="69592-134">En notifiering kan till exempel visa ett meddelande som "årlig rea slutar om 2 dagar."</span><span class="sxs-lookup"><span data-stu-id="69592-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="69592-135">**Sökfält** – Sökfältet låter användarna ange söktermer så att de kan söka efter produkter.</span><span class="sxs-lookup"><span data-stu-id="69592-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="69592-136">Modulen måste konfigureras med URL:en för sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="69592-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="69592-137">Frågesträngparametern (standardvärde) kan konfigureras (standardvärdet är **"q"**).</span><span class="sxs-lookup"><span data-stu-id="69592-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="69592-138">Sökfältet har en plats frö automatiska förslag där den automatiska förslagsmodulen ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="69592-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="69592-139">**Föreslå automatiskt** – modulen föreslå automatiskt visar automatiskt föreslagna resultat.</span><span class="sxs-lookup"><span data-stu-id="69592-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="69592-140">Resultaten kan vara nyckelord, produkter eller kategorier där söktermen finns.</span><span class="sxs-lookup"><span data-stu-id="69592-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="69592-141">Skapa en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="69592-141">Create a header module</span></span>

<span data-ttu-id="69592-142">Gör så här om du vill skapa en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="69592-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="69592-143">Skapa ett sidfragment som innehåller en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="69592-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="69592-144">Lägg till moduler till platserna i sidhuvudmodulen.</span><span class="sxs-lookup"><span data-stu-id="69592-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="69592-145">Uppdatera inställningarna för varje modul.</span><span class="sxs-lookup"><span data-stu-id="69592-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="69592-146">Spara sidfragmentet.</span><span class="sxs-lookup"><span data-stu-id="69592-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="69592-147">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="69592-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="69592-148">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="69592-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="69592-149">På standardsidan lägger du till sidfragment som innehåller sidhuvudmodulen till sidhuvudplatsen.</span><span class="sxs-lookup"><span data-stu-id="69592-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="69592-150">Spara mallen.</span><span class="sxs-lookup"><span data-stu-id="69592-150">Save the template.</span></span> 
1. <span data-ttu-id="69592-151">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="69592-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69592-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="69592-152">Additional resources</span></span>

[<span data-ttu-id="69592-153">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="69592-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="69592-154">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="69592-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="69592-155">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="69592-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="69592-156">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="69592-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="69592-157">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="69592-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="69592-158">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="69592-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="69592-159">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="69592-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="69592-160">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="69592-160">Footer module</span></span>](author-footer-module.md)
