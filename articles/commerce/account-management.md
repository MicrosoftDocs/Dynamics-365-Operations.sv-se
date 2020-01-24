---
title: Sidor och moduler för kontohantering
description: Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885819"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="ba87f-103">Sidor och moduler för kontohantering</span><span class="sxs-lookup"><span data-stu-id="ba87f-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ba87f-104">Det här ämnet omfattar för kontohantering och moduler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ba87f-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ba87f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ba87f-105">Overview</span></span>

<span data-ttu-id="ba87f-106">Kontohantering refererar till en grupp med sidor som används för att hantera information om användarkonton i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ba87f-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ba87f-107">Kontohanteringssidorna omfattar landningssida för kontohantering och sidor för användarprofil, sida för användaradress, sida för orderhistorik, sida för orderinformation, förmånssida och sida för önskelista.</span><span class="sxs-lookup"><span data-stu-id="ba87f-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="ba87f-108">Landningssidan Kontohantering</span><span class="sxs-lookup"><span data-stu-id="ba87f-108">Account management landing page</span></span>

<span data-ttu-id="ba87f-109">Landningssidan för kontohantering använder följande moduler:</span><span class="sxs-lookup"><span data-stu-id="ba87f-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="ba87f-110">**Innehållsplacering** – den här modulen är en behållarmodul som innehåller alla moduler på landningssidan för kontohantering.</span><span class="sxs-lookup"><span data-stu-id="ba87f-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="ba87f-111">**Kontots välkomstobjekt** – modulen används för att tillhandahålla ett välkomstmeddelande på sidan kontohantering.</span><span class="sxs-lookup"><span data-stu-id="ba87f-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="ba87f-112">Det inkluderar egenskaper för rubriken och panelstorleken.</span><span class="sxs-lookup"><span data-stu-id="ba87f-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="ba87f-113">Egenskapen **panelstorlek** definierar modulens bredd i modulen innehållsplacering.</span><span class="sxs-lookup"><span data-stu-id="ba87f-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="ba87f-114">Värdena sträcker sig från **1** till **12**, där **12** representerar den fulla bredden på behållaren för innehållsplacering.</span><span class="sxs-lookup"><span data-stu-id="ba87f-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="ba87f-115">**Artikel för placering av kontoorder** – Den här modulen används för att ge en översikt över antalet order som har placerats av användarkontot.</span><span class="sxs-lookup"><span data-stu-id="ba87f-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="ba87f-116">Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="ba87f-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ba87f-117">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan orderhistorik.</span><span class="sxs-lookup"><span data-stu-id="ba87f-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="ba87f-118">**Artikel för placering av kontoorder** – den här modulen används för att tillhandahålla en sammanfattning av användarprofilen.</span><span class="sxs-lookup"><span data-stu-id="ba87f-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="ba87f-119">Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="ba87f-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ba87f-120">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarprofil.</span><span class="sxs-lookup"><span data-stu-id="ba87f-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="ba87f-121">**Artikel för kontoönskelista** – modulen används för att ge en sammanfattning av artiklarna på kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="ba87f-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="ba87f-122">Det kan till exempel vara "du har tio artiklar i din önskelista."</span><span class="sxs-lookup"><span data-stu-id="ba87f-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="ba87f-123">Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="ba87f-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ba87f-124">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för önskelista.</span><span class="sxs-lookup"><span data-stu-id="ba87f-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="ba87f-125">**Artikel för kontoadress** – den här modulen används för att tillhandahålla en sammanfattning av användarens adress.</span><span class="sxs-lookup"><span data-stu-id="ba87f-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="ba87f-126">Det kan till exempel vara "du har 2 adresser som lagts till i ditt konto".</span><span class="sxs-lookup"><span data-stu-id="ba87f-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="ba87f-127">Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer".</span><span class="sxs-lookup"><span data-stu-id="ba87f-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="ba87f-128">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till sidan för användarens adress.</span><span class="sxs-lookup"><span data-stu-id="ba87f-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="ba87f-129">**Artikeln kontoförmån** – den här modulen används för att visa och länka till information om lojalitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="ba87f-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="ba87f-130">Det inkluderar egenskaper för rubriken, panelstorleken och länken " visa detaljer" och länken "bli en medlem".</span><span class="sxs-lookup"><span data-stu-id="ba87f-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="ba87f-131">Länken "Visa detaljer" ska vara konfigurerad för omdirigering till förmånssidan.</span><span class="sxs-lookup"><span data-stu-id="ba87f-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="ba87f-132">Länken "bli en medlem" bör konfigureras för att omdirigeras till en sida där användarna kan delta i förmånsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="ba87f-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="ba87f-133">Sidan för orderhistorik</span><span class="sxs-lookup"><span data-stu-id="ba87f-133">Order history page</span></span>

<span data-ttu-id="ba87f-134">På sidan för orderhistorik används modulen orderhistorik för att visa alla nya order som användaren har placerat.</span><span class="sxs-lookup"><span data-stu-id="ba87f-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="ba87f-135">Sidan Orderdetaljer</span><span class="sxs-lookup"><span data-stu-id="ba87f-135">Order details page</span></span>

<span data-ttu-id="ba87f-136">Sidan orderdetaljer innehåller detaljerad information för varje order och du öppnar den från sidan orderhistorik.</span><span class="sxs-lookup"><span data-stu-id="ba87f-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="ba87f-137">Den använder modulen orderdetaljer, som kräver försäljnings-ID eller transaktions-ID för att hämta orderdetaljer.</span><span class="sxs-lookup"><span data-stu-id="ba87f-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="ba87f-138">Sidan användarprofil</span><span class="sxs-lookup"><span data-stu-id="ba87f-138">User profile page</span></span>

<span data-ttu-id="ba87f-139">På sidan användarprofil visas information om användarkonton, t.ex. användarens namn och e-postadress.</span><span class="sxs-lookup"><span data-stu-id="ba87f-139">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="ba87f-140">Den använder modulen användarprofil.</span><span class="sxs-lookup"><span data-stu-id="ba87f-140">It uses the user profile module.</span></span> <span data-ttu-id="ba87f-141">Även om e-postadressen inte kan tas bort, kan den redigera.</span><span class="sxs-lookup"><span data-stu-id="ba87f-141">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="ba87f-142">På sidan användarprofil visas även användarinställningar som gör det möjligt för en användare att anmäla sig eller välja bort vissa funktioner, till exempel anpassning av rekommendationslistor.</span><span class="sxs-lookup"><span data-stu-id="ba87f-142">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="ba87f-143">Sidan användaradress</span><span class="sxs-lookup"><span data-stu-id="ba87f-143">User address page</span></span>

<span data-ttu-id="ba87f-144">På sidan användaradress visas listan med adresser som är associerade med användarkontot.</span><span class="sxs-lookup"><span data-stu-id="ba87f-144">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="ba87f-145">Användaren tillhandahöll antingen dessa adresser i kassan eller lade till dem direkt på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ba87f-145">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="ba87f-146">Modulen för användaradresser används för att lägga till och redigera adresser, ange den primära adressen och återge befintliga adresser på sidan.</span><span class="sxs-lookup"><span data-stu-id="ba87f-146">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="ba87f-147">Sidan för önskelista</span><span class="sxs-lookup"><span data-stu-id="ba87f-147">Wish list page</span></span>

<span data-ttu-id="ba87f-148">Sidan önskelista visar en lista över artiklar som har lagts till i kundens önskelista.</span><span class="sxs-lookup"><span data-stu-id="ba87f-148">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="ba87f-149">Den använder modulen önskelista för att återge artiklar i önskelistan.</span><span class="sxs-lookup"><span data-stu-id="ba87f-149">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="ba87f-150">Förmånssida</span><span class="sxs-lookup"><span data-stu-id="ba87f-150">Loyalty page</span></span>

<span data-ttu-id="ba87f-151">Med hjälp av förmånssidan kan kunderna ansluta sig till ett förmånsprogram eller, om de redan har förmånsprogrammedlemmar, visa sina programuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ba87f-151">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="ba87f-152">De kan också visa de poäng de har fått och löst in i de senaste transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="ba87f-152">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba87f-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ba87f-153">Additional resources</span></span>

[<span data-ttu-id="ba87f-154">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="ba87f-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ba87f-155">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="ba87f-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ba87f-156">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="ba87f-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ba87f-157">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="ba87f-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ba87f-158">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="ba87f-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ba87f-159">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ba87f-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ba87f-160">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="ba87f-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ba87f-161">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="ba87f-161">Footer module</span></span>](author-footer-module.md)
