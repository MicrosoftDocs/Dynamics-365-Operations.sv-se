---
title: Sidor och moduler för kontohantering
description: Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 29523d03fb687684dae7d0ce08208905cce702df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206641"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="bd751-103">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="bd751-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bd751-104">Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd751-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bd751-105">Kontohantering refererar till en grupp med sidor som används för att hantera information om användarkonton i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd751-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="bd751-106">Kontohanteringssidorna omfattar landningssida för kontohantering och sidor för användarprofil, sida för användaradress, sida för orderhistorik, sida för orderinformation, förmånssida och sida för önskelista.</span><span class="sxs-lookup"><span data-stu-id="bd751-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="bd751-107">Landningssidan Kontohantering</span><span class="sxs-lookup"><span data-stu-id="bd751-107">Account management landing page</span></span>

<span data-ttu-id="bd751-108">Landningssidan för kontohantering använder följande moduler:</span><span class="sxs-lookup"><span data-stu-id="bd751-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="bd751-109">**Behållare** – alla moduler för landningssida för kontohantering ska placeras i en behållare.</span><span class="sxs-lookup"><span data-stu-id="bd751-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="bd751-110">**Kontots välkomstpanel** – modulen används för att tillhandahålla ett välkomstmeddelande på sidan kontohantering.</span><span class="sxs-lookup"><span data-stu-id="bd751-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="bd751-111">Den innehåller egenskaper för rubriken.</span><span class="sxs-lookup"><span data-stu-id="bd751-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="bd751-112">**Allmän panel för konto** – denna modul kan användas för att tillhandahålla rubriker och länkar till kontohanteringssidor, t.ex. "orderhistorik" eller "min profil"-sidorna.</span><span class="sxs-lookup"><span data-stu-id="bd751-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="bd751-113">Den generiska panelen kan användas för att konfigurera en panel för varje sida.</span><span class="sxs-lookup"><span data-stu-id="bd751-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="bd751-114">I Fabrikam används den här modulen för länkarna "orderhistorik" och "min profil" på landningssidan för kontohantering.</span><span class="sxs-lookup"><span data-stu-id="bd751-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="bd751-115">**Panel för kontoönskelista** – modulen används för att ge en sammanfattning av artiklarna på kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="bd751-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="bd751-116">Det kan till exempel vara "du har tio artiklar i din önskelista."</span><span class="sxs-lookup"><span data-stu-id="bd751-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="bd751-117">Den inkluderar egenskaper för rubriken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="bd751-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="bd751-118">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för önskelista.</span><span class="sxs-lookup"><span data-stu-id="bd751-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="bd751-119">**Panel för kontoadress** – den här modulen används för att tillhandahålla en sammanfattning av användarens adress.</span><span class="sxs-lookup"><span data-stu-id="bd751-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="bd751-120">Det kan till exempel vara "du har 2 adresser som lagts till i ditt konto".</span><span class="sxs-lookup"><span data-stu-id="bd751-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="bd751-121">Den inkluderar egenskaper för rubriken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="bd751-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="bd751-122">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarens adress.</span><span class="sxs-lookup"><span data-stu-id="bd751-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="bd751-123">**Panel för kontoförmån** – den här modulen används för att visa och länka till information om lojalitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="bd751-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="bd751-124">Den här panelen har två lägen: ett tillstånd visar länkar för att delta i en förmånsprogam om användaren inte redan är medlem.</span><span class="sxs-lookup"><span data-stu-id="bd751-124">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="bd751-125">I det andra läget visas länkar som visar sidan med förmånsinformation när användaren redan är medlem.</span><span class="sxs-lookup"><span data-stu-id="bd751-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="bd751-126">Egenskaper inkluderar rubrik, "registrerings"-länken och "Visa förmån"-länken.</span><span class="sxs-lookup"><span data-stu-id="bd751-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="bd751-127">Länken "Visa förmån" ska vara konfigurerad för omdirigering till förmånssidan.</span><span class="sxs-lookup"><span data-stu-id="bd751-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="bd751-128">Länken "Registrera" bör konfigureras för att omdirigeras till en sida där användarna kan delta i förmånsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="bd751-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="bd751-129">Sidan för orderhistorik</span><span class="sxs-lookup"><span data-stu-id="bd751-129">Order history page</span></span>

<span data-ttu-id="bd751-130">På sidan för orderhistorik används modulen orderhistorik för att visa alla nya order som användaren har placerat.</span><span class="sxs-lookup"><span data-stu-id="bd751-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="bd751-131">Sidan Orderdetaljer</span><span class="sxs-lookup"><span data-stu-id="bd751-131">Order details page</span></span>

<span data-ttu-id="bd751-132">Sidan orderdetaljer innehåller detaljerad information för varje order och du öppnar den från sidan orderhistorik.</span><span class="sxs-lookup"><span data-stu-id="bd751-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="bd751-133">Den använder modulen orderdetaljer, som kräver försäljnings-ID eller transaktions-ID för att hämta orderdetaljer.</span><span class="sxs-lookup"><span data-stu-id="bd751-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="bd751-134">Sidan användarprofil</span><span class="sxs-lookup"><span data-stu-id="bd751-134">User profile page</span></span>

<span data-ttu-id="bd751-135">På sidan användarprofil visas information om användarkonton, t.ex. användarens namn och e-postadress.</span><span class="sxs-lookup"><span data-stu-id="bd751-135">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="bd751-136">Den använder informationen från användarprofilen och redigeringsmodulerna för användarprofiler.</span><span class="sxs-lookup"><span data-stu-id="bd751-136">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="bd751-137">Även om e-postadressen inte kan tas bort, kan den redigera.</span><span class="sxs-lookup"><span data-stu-id="bd751-137">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="bd751-138">På sidan användarprofil visas även användarinställningar som gör det möjligt för en användare att anmäla sig eller välja bort vissa funktioner, till exempel anpassning av rekommendationslistor.</span><span class="sxs-lookup"><span data-stu-id="bd751-138">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="bd751-139">Sidan användaradress</span><span class="sxs-lookup"><span data-stu-id="bd751-139">User address page</span></span>

<span data-ttu-id="bd751-140">På sidan användaradress visas listan med adresser som är associerade med användarkontot.</span><span class="sxs-lookup"><span data-stu-id="bd751-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="bd751-141">Användaren tillhandahöll antingen dessa adresser i kassan eller lade till dem direkt på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="bd751-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="bd751-142">Modulen för användaradresser används för att lägga till och redigera adresser, ange den primära adressen och återge befintliga adresser på sidan.</span><span class="sxs-lookup"><span data-stu-id="bd751-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="bd751-143">Sidan för önskelista</span><span class="sxs-lookup"><span data-stu-id="bd751-143">Wish list page</span></span>

<span data-ttu-id="bd751-144">Sidan önskelista visar en lista över artiklar som har lagts till i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="bd751-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="bd751-145">Den använder modulen önskelista för att återge artiklar i önskelistan.</span><span class="sxs-lookup"><span data-stu-id="bd751-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="bd751-146">Förmånssida</span><span class="sxs-lookup"><span data-stu-id="bd751-146">Loyalty page</span></span>

<span data-ttu-id="bd751-147">Med hjälp av förmånssidan kan kunderna visa deras förmånsdetaljer om de redan har förmånsprogrammedlemmar.</span><span class="sxs-lookup"><span data-stu-id="bd751-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="bd751-148">De kan också visa de poäng de har fått och löst in i de senaste transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="bd751-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="bd751-149">Sidan använder modulen för förmånsdetaljer för att visa information om förmånerna.</span><span class="sxs-lookup"><span data-stu-id="bd751-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="bd751-150">Om du vill delta i förmånsprogrammet kan du skapa en marknadsföringssida med modulerna förmånsregistrering och förmånsvillkor.</span><span class="sxs-lookup"><span data-stu-id="bd751-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="bd751-151">Om användaren inte är medlem i ett förmånsprogram kommer dessa moduler att göra det möjligt för användaren att registrera sig.</span><span class="sxs-lookup"><span data-stu-id="bd751-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd751-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="bd751-152">Additional resources</span></span>

[<span data-ttu-id="bd751-153">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="bd751-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bd751-154">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="bd751-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="bd751-155">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="bd751-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="bd751-156">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="bd751-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="bd751-157">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="bd751-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="bd751-158">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="bd751-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="bd751-159">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="bd751-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="bd751-160">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="bd751-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]