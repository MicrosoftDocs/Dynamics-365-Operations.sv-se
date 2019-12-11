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
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697285"
---
# <a name="header-module"></a><span data-ttu-id="55d77-103">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="55d77-103">Header module</span></span>

<span data-ttu-id="55d77-104">[!inkludera [banderoll](includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="55d77-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="55d77-105">Det här avsnittet handlar om moduler för sidhuvud och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55d77-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="55d77-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="55d77-106">Overview</span></span>

<span data-ttu-id="55d77-107">En sidhuvudmodul är en särskild behållare som används för att vara värd för alla moduler som ska visas i sidans huvud.</span><span class="sxs-lookup"><span data-stu-id="55d77-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="55d77-108">Det kan till exempel vara en webbplats logotyp, länkar till navigeringsnoden, länkar till andra sidor på webbplatsen och sökfältet.</span><span class="sxs-lookup"><span data-stu-id="55d77-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="55d77-109">En sidhuvudmodul optimeras automatiskt för enheten som platsen visas på (dvs. en stationär enhet eller en mobil enhet).</span><span class="sxs-lookup"><span data-stu-id="55d77-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="55d77-110">Om du till exempel använder en mobil enhet döljs navigeringsfältet i **meny**-knapp (som ibland kallas en *hamburgarmeny*).</span><span class="sxs-lookup"><span data-stu-id="55d77-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="55d77-111">Egenskaper för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="55d77-111">Properties of a header</span></span>

<span data-ttu-id="55d77-112">Liksom generiska behållare stöder en sidhuvudmodul egenskaperna **rubrik** och **bredd**.</span><span class="sxs-lookup"><span data-stu-id="55d77-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="55d77-113">En sidhuvudmodul har flera platser.</span><span class="sxs-lookup"><span data-stu-id="55d77-113">A header module has multiple slots.</span></span> <span data-ttu-id="55d77-114">Det finns till exempel kortplatser för informationsmeddelanden, navigeringsmeny, logotyp, sökfält, ikon för vagn, ikon för önskelista och kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="55d77-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="55d77-115">Varje plats stöder en viss uppsättning moduler.</span><span class="sxs-lookup"><span data-stu-id="55d77-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="55d77-116">Moduler som är tillgängliga i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="55d77-116">Modules that are available in a header module</span></span>

<span data-ttu-id="55d77-117">Följande moduler kan användas i en sidhuvudmodul:</span><span class="sxs-lookup"><span data-stu-id="55d77-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="55d77-118">**Navigeringsmeny** – navigeringsmenyn representerar en hierarki för kanaler och andra statiska navigeringslänkar.</span><span class="sxs-lookup"><span data-stu-id="55d77-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="55d77-119">Du kan konfigurera kanalnavigeringshierarkin i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="55d77-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="55d77-120">Konfigurerade artiklar visas sedan som sidhuvudnavigering.</span><span class="sxs-lookup"><span data-stu-id="55d77-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="55d77-121">Dessutom kan statiska navigeringslänkar konfigureras och relativa länkar till andra sidor på näthandelsplatsen kan tillhandahållas.</span><span class="sxs-lookup"><span data-stu-id="55d77-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="55d77-122">Själva sidhuvudet kan justeras åt vänster, höger eller centrerat.</span><span class="sxs-lookup"><span data-stu-id="55d77-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="55d77-123">**Vagnikon** – vagnikonen är en särskild ikon som representerar vagnen.</span><span class="sxs-lookup"><span data-stu-id="55d77-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="55d77-124">Det visas i sidhuvudet och anger antalet artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="55d77-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="55d77-125">En länk till vagnsidan ska medfölja vagnikonen, så att kunder kan dirigeras om till vagnsidan när de interagerar med ikonen.</span><span class="sxs-lookup"><span data-stu-id="55d77-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="55d77-126">**Ikonen önskelista** – Ikonen önskelista visas i sidhuvudet och anger antalet artiklar som har lagts till i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="55d77-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="55d77-127">En länk till sidan för önskelista ska medfölja den här ikonen, så att kunder kan dirigeras om till sidan för önskelista när de interagerar med ikonen.</span><span class="sxs-lookup"><span data-stu-id="55d77-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="55d77-128">**Inloggningsmodul** – inloggningsmodulen visas i sidhuvudet.</span><span class="sxs-lookup"><span data-stu-id="55d77-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="55d77-129">Kunder kan antingen logga in på sitt konto eller registrera sig för ett konto.</span><span class="sxs-lookup"><span data-stu-id="55d77-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="55d77-130">Om kunden redan är inloggad kan modulen konfigureras så att den visar länkar till kontosidan, sidan för orderhistorik eller en annan sida.</span><span class="sxs-lookup"><span data-stu-id="55d77-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="55d77-131">**Logotypmodul** – den här modulen visar logotypen som representerar återförsäljaren och varumärket.</span><span class="sxs-lookup"><span data-stu-id="55d77-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="55d77-132">Det är en bild som har en länk.</span><span class="sxs-lookup"><span data-stu-id="55d77-132">It's an image that has a link.</span></span> <span data-ttu-id="55d77-133">Länken konfigureras vanligtvis så att den har en omdirigering till startsidan, vilket innebär att kunderna snabbt kan gå tillbaka till startsidan från vilken sida som helst på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="55d77-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="55d77-134">**Varning** – en notifiering visas i sidhuvudet och används för att visa ett infogat meddelande som gäller alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="55d77-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="55d77-135">En notifiering kan till exempel visa ett meddelande som "årlig rea slutar om 2 dagar."</span><span class="sxs-lookup"><span data-stu-id="55d77-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="55d77-136">**Sökfält** – Sökfältet låter användarna ange söktermer så att de kan söka efter produkter.</span><span class="sxs-lookup"><span data-stu-id="55d77-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="55d77-137">Modulen måste konfigureras med URL:en för sökresultatsidan.</span><span class="sxs-lookup"><span data-stu-id="55d77-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="55d77-138">Frågesträngparametern (standardvärde) kan konfigureras (standardvärdet är **"q"**).</span><span class="sxs-lookup"><span data-stu-id="55d77-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="55d77-139">Sökfältet har en plats frö automatiska förslag där den automatiska förslagsmodulen ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="55d77-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="55d77-140">**Föreslå automatiskt** – modulen föreslå automatiskt visar automatiskt föreslagna resultat.</span><span class="sxs-lookup"><span data-stu-id="55d77-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="55d77-141">Resultaten kan vara nyckelord, produkter eller kategorier där söktermen finns.</span><span class="sxs-lookup"><span data-stu-id="55d77-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="55d77-142">Skapa en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="55d77-142">Create a header module</span></span>

<span data-ttu-id="55d77-143">Gör så här om du vill skapa en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="55d77-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="55d77-144">Skapa ett sidfragment som innehåller en sidhuvudmodul.</span><span class="sxs-lookup"><span data-stu-id="55d77-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="55d77-145">Lägg till moduler till platserna i sidhuvudmodulen.</span><span class="sxs-lookup"><span data-stu-id="55d77-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="55d77-146">Uppdatera inställningarna för varje modul.</span><span class="sxs-lookup"><span data-stu-id="55d77-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="55d77-147">Spara sidfragmentet.</span><span class="sxs-lookup"><span data-stu-id="55d77-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="55d77-148">Checka in sidan och publicera den.</span><span class="sxs-lookup"><span data-stu-id="55d77-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="55d77-149">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="55d77-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="55d77-150">På standardsidan lägger du till sidfragment som innehåller sidhuvudmodulen till sidhuvudplatsen.</span><span class="sxs-lookup"><span data-stu-id="55d77-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="55d77-151">Spara mallen.</span><span class="sxs-lookup"><span data-stu-id="55d77-151">Save the template.</span></span> 
1. <span data-ttu-id="55d77-152">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="55d77-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55d77-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="55d77-153">Additional resources</span></span>

[<span data-ttu-id="55d77-154">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="55d77-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="55d77-155">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="55d77-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="55d77-156">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="55d77-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="55d77-157">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="55d77-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="55d77-158">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="55d77-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="55d77-159">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="55d77-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="55d77-160">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="55d77-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="55d77-161">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="55d77-161">Footer module</span></span>](author-footer-module.md)
