---
title: Sidor och moduler för kontohantering
description: Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: df4959a61f1b2948c62a558523a848ff8b2fe0a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796304"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="64756-103">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="64756-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="64756-104">Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="64756-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="64756-105">Kontohantering refererar till en grupp med sidor som används för att hantera information om användarkonton i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="64756-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="64756-106">Kontohanteringssidorna omfattar landningssida för kontohantering och sidor för användarprofil, sida för användaradress, sida för orderhistorik, sida för orderinformation, förmånssida och sida för önskelista.</span><span class="sxs-lookup"><span data-stu-id="64756-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="64756-107">Landningssidan Kontohantering</span><span class="sxs-lookup"><span data-stu-id="64756-107">Account management landing page</span></span>

<span data-ttu-id="64756-108">Landningssidan för kontohantering använder följande moduler:</span><span class="sxs-lookup"><span data-stu-id="64756-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="64756-109">**Behållare** – alla moduler för landningssida för kontohantering ska placeras i en behållare.</span><span class="sxs-lookup"><span data-stu-id="64756-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="64756-110">**Kontots välkomstpanel** – modulen används för att tillhandahålla ett välkomstmeddelande på sidan kontohantering.</span><span class="sxs-lookup"><span data-stu-id="64756-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="64756-111">Den innehåller egenskaper för rubriken.</span><span class="sxs-lookup"><span data-stu-id="64756-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="64756-112">**Allmän panel för konto** – denna modul kan användas för att tillhandahålla rubriker och länkar till kontohanteringssidor, t.ex. "orderhistorik" eller "min profil"-sidorna.</span><span class="sxs-lookup"><span data-stu-id="64756-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="64756-113">Den generiska panelen kan användas för att konfigurera en panel för varje sida.</span><span class="sxs-lookup"><span data-stu-id="64756-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="64756-114">I Fabrikam används den här modulen för länkarna "orderhistorik" och "min profil" på landningssidan för kontohantering.</span><span class="sxs-lookup"><span data-stu-id="64756-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="64756-115">**Panel för kontoönskelista** – modulen används för att ge en sammanfattning av artiklarna på kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="64756-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="64756-116">Det kan till exempel vara "du har tio artiklar i din önskelista."</span><span class="sxs-lookup"><span data-stu-id="64756-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="64756-117">Den inkluderar egenskaper för rubriken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="64756-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="64756-118">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för önskelista.</span><span class="sxs-lookup"><span data-stu-id="64756-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="64756-119">**Panel för kontoadress** – den här modulen används för att tillhandahålla en sammanfattning av användarens adress.</span><span class="sxs-lookup"><span data-stu-id="64756-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="64756-120">Det kan till exempel vara "du har 2 adresser som lagts till i ditt konto".</span><span class="sxs-lookup"><span data-stu-id="64756-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="64756-121">Den inkluderar egenskaper för rubriken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="64756-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="64756-122">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarens adress.</span><span class="sxs-lookup"><span data-stu-id="64756-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="64756-123">**Panel för kontoförmån** – den här modulen används för att visa och länka till information om lojalitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="64756-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="64756-124">Den här panelen har två lägen: ett tillstånd visar länkar för att delta i en förmånsprogam om användaren inte redan är medlem.</span><span class="sxs-lookup"><span data-stu-id="64756-124">This tile has two states: one state shows links to join a loyalty program if the user is not a member already.</span></span> <span data-ttu-id="64756-125">I det andra läget visas länkar som visar sidan med förmånsinformation när användaren redan är medlem.</span><span class="sxs-lookup"><span data-stu-id="64756-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="64756-126">Egenskaper inkluderar rubrik, "registrerings"-länken och "Visa förmån"-länken.</span><span class="sxs-lookup"><span data-stu-id="64756-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="64756-127">Länken "Visa förmån" ska vara konfigurerad för omdirigering till förmånssidan.</span><span class="sxs-lookup"><span data-stu-id="64756-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="64756-128">Länken "Registrera" bör konfigureras för att omdirigeras till en sida där användarna kan delta i förmånsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="64756-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="64756-129">Sidan för orderhistorik</span><span class="sxs-lookup"><span data-stu-id="64756-129">Order history page</span></span>

<span data-ttu-id="64756-130">På sidan för orderhistorik används modulen orderhistorik för att visa alla nya order som användaren har placerat.</span><span class="sxs-lookup"><span data-stu-id="64756-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="64756-131">Sidan Orderdetaljer</span><span class="sxs-lookup"><span data-stu-id="64756-131">Order details page</span></span>

<span data-ttu-id="64756-132">Sidan orderdetaljer innehåller detaljerad information för varje order och du öppnar den från sidan orderhistorik.</span><span class="sxs-lookup"><span data-stu-id="64756-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="64756-133">Den använder modulen orderdetaljer, som kräver försäljnings-ID eller transaktions-ID för att hämta orderdetaljer.</span><span class="sxs-lookup"><span data-stu-id="64756-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="my-profile-page"></a><span data-ttu-id="64756-134">Min profilsida</span><span class="sxs-lookup"><span data-stu-id="64756-134">My profile page</span></span>

<span data-ttu-id="64756-135">På min profilsida visas användarens kontoprofilinformation med hjälp av kontoprofilmodulen.</span><span class="sxs-lookup"><span data-stu-id="64756-135">The My profile page shows the user's account profile details using the account profile module.</span></span> <span data-ttu-id="64756-136">På sidan visas den e-postadress som är kopplad till användarens konto, samt vilka inställningar som har ställts in för kontot.</span><span class="sxs-lookup"><span data-stu-id="64756-136">The page shows the email address associated with the user's account, as well as preferences set up for the account.</span></span> <span data-ttu-id="64756-137">Om du ställer in anpassade kundattribut visas även dessa attribut i avsnittet "Ytterligare information".</span><span class="sxs-lookup"><span data-stu-id="64756-137">If setting up custom customer attributes, an "Additional Information" section will also display those attributes.</span></span> <span data-ttu-id="64756-138">Användarna kan redigera sina namn, inställningar eller ytterligare information (om sådan finns tillgänglig).</span><span class="sxs-lookup"><span data-stu-id="64756-138">Users can edit their name, preferences, or additional information (if available).</span></span>

### <a name="user-address-page"></a><span data-ttu-id="64756-139">Sidan användaradress</span><span class="sxs-lookup"><span data-stu-id="64756-139">User address page</span></span>

<span data-ttu-id="64756-140">På sidan användaradress visas listan med adresser som är associerade med användarkontot.</span><span class="sxs-lookup"><span data-stu-id="64756-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="64756-141">Användaren tillhandahöll antingen dessa adresser i kassan eller lade till dem direkt på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="64756-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="64756-142">Modulen för användaradresser används för att lägga till och redigera adresser, ange den primära adressen och återge befintliga adresser på sidan.</span><span class="sxs-lookup"><span data-stu-id="64756-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="64756-143">Sidan för önskelista</span><span class="sxs-lookup"><span data-stu-id="64756-143">Wish list page</span></span>

<span data-ttu-id="64756-144">Sidan önskelista visar en lista över artiklar som har lagts till i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="64756-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="64756-145">Den använder modulen önskelista för att återge artiklar i önskelistan.</span><span class="sxs-lookup"><span data-stu-id="64756-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="64756-146">Förmånssida</span><span class="sxs-lookup"><span data-stu-id="64756-146">Loyalty page</span></span>

<span data-ttu-id="64756-147">Med hjälp av förmånssidan kan kunderna visa deras förmånsdetaljer om de redan har förmånsprogrammedlemmar.</span><span class="sxs-lookup"><span data-stu-id="64756-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="64756-148">De kan också visa de poäng de har fått och löst in i de senaste transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="64756-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="64756-149">Sidan använder modulen för förmånsdetaljer för att visa information om förmånerna.</span><span class="sxs-lookup"><span data-stu-id="64756-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="64756-150">Om du vill delta i förmånsprogrammet kan du skapa en marknadsföringssida med modulerna förmånsregistrering och förmånsvillkor.</span><span class="sxs-lookup"><span data-stu-id="64756-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="64756-151">Om användaren inte är medlem i ett förmånsprogram kommer dessa moduler att göra det möjligt för användaren att registrera sig.</span><span class="sxs-lookup"><span data-stu-id="64756-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64756-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="64756-152">Additional resources</span></span>

[<span data-ttu-id="64756-153">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="64756-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="64756-154">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="64756-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="64756-155">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="64756-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="64756-156">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="64756-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="64756-157">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="64756-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="64756-158">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="64756-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="64756-159">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="64756-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="64756-160">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="64756-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]