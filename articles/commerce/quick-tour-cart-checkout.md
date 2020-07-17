---
title: Översikt över sidor för kundvagn och kassa
description: Det här ämnet innehåller en översikt över sidor för kundvagn och kassa i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c879b90cf49dcab9cf069e4f3613602bd6673aa9
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527581"
---
# <a name="cart-and-checkout-pages-overview"></a><span data-ttu-id="0a5d3-103">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="0a5d3-103">Cart and checkout pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0a5d3-104">Det här ämnet innehåller en översikt över sidor för kundvagn och kassa i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-104">This topic provides an overview of the cart and checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0a5d3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0a5d3-105">Overview</span></span>

<span data-ttu-id="0a5d3-106">På sidan kundvagn på en näthandelsplats visas alla artiklar som kunden har lagt till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-106">The cart page of an e-Commerce website shows all items that a customer has added to the cart.</span></span> <span data-ttu-id="0a5d3-107">Sidan kundvagn skapas med hjälp av modulen kundvagn.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-107">The cart page is built by using the cart module.</span></span> <span data-ttu-id="0a5d3-108">En kundvagnsmodul är en behållare som används för att vara värd för alla moduler som krävs för att visa upp artiklar i vagnen.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-108">The cart module is a container that hosts all the modules that are required to showcase items in the cart.</span></span> <span data-ttu-id="0a5d3-109">I kundvagnsmodulen kan även använda andra moduler för att visa ordersammanfattningen och eventuella kampanjkoder som har tillämpats på kundordern.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-109">The cart module can also use other modules to show the order summary and any promotional codes that have been applied to the customer order.</span></span>

<span data-ttu-id="0a5d3-110">På kassasida in en näthandelsplats visas ett steg-för-steg-flöde som kunderna följer för att ange all information som krävs för att göra en beställning.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-110">The checkout page of an e-Commerce website presents a step-by-step flow that customers follow to enter all the information that is required to place an order.</span></span> <span data-ttu-id="0a5d3-111">En kassamodul kan innehålla moduler som hanterar leveransadress, leveransmetoder, faktureringsinformation, ordersammanfattning och annan information som hör till en kundorder.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-111">A checkout module can include modules that handle the shipping address, shipping methods, billing information, order summary, and other information that is related to customer orders.</span></span>

## <a name="cart-page"></a><span data-ttu-id="0a5d3-112">Kundvagnssida</span><span class="sxs-lookup"><span data-stu-id="0a5d3-112">Cart page</span></span>

<span data-ttu-id="0a5d3-113">Kundvagnssidan fungerar som shoppingväskor och innehåller alla artiklar som har lagts till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-113">The cart page serves as the shopping bag and includes all the items that have been added to the cart.</span></span>

<span data-ttu-id="0a5d3-114">Följande illustration visar ett exempel på en kundvagnssida som har skapats med hjälp av online-startpaketet och temat "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="0a5d3-114">The following illustration show an example of a cart page that was built by using the online starter kit and the "Fabrikam" theme.</span></span>

![Exempel på en kundvagnssida](./media/cart2.PNG)

<span data-ttu-id="0a5d3-116">Huvudsakliga materialet på kundvagnssidan visar alla artiklar som kunden har lagt till i vagnen.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-116">The main body of the cart page shows all the items that the customer has added to the cart.</span></span> <span data-ttu-id="0a5d3-117">Alla tillämpliga rabatter visas.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-117">All applicable discounts are showcased.</span></span> <span data-ttu-id="0a5d3-118">Rabatterna inkluderar komplexa rabatter.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-118">These discounts include complex discounts.</span></span> <span data-ttu-id="0a5d3-119">Exempel på detta är "Köp 3 artiklar och få 10 % rabatt" eller "Köp en flaska och en ryggsäck för att få 10 % rabatt".</span><span class="sxs-lookup"><span data-stu-id="0a5d3-119">Examples include "Buy 3 items and get 10% off" or "Buy a bottle and a backpack to get 10% off."</span></span> <span data-ttu-id="0a5d3-120">Modulen ordersammanfattning visar det belopp som förfaller efter rabatt, leverans, moms och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-120">The order summary module shows the amount that is due after discounts, shipping, taxes, and so on, have been applied.</span></span> <span data-ttu-id="0a5d3-121">Det finns också en modul för kampanjkod som gör att kunden kan använda eller ta bort kampanjkoder.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-121">There is also a promo code module that lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="0a5d3-122">En kund kan handla anonymt eller som en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-122">A customer can shop anonymously or as a signed-in user.</span></span> <span data-ttu-id="0a5d3-123">Om en kund är inloggad behålls artiklar i kundvagnen mellan sessionerna.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-123">If a customer is signed in, items in the cart are preserved between sessions.</span></span> <span data-ttu-id="0a5d3-124">På så sätt kan kunden fortsätta att handla från flera enheter.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-124">In this way, the customer can continue to shop from multiple devices.</span></span>

<span data-ttu-id="0a5d3-125">Från kundvagnen kan kunden fortsätta till kassan.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-125">From the cart, the customer can proceed to checkout.</span></span> <span data-ttu-id="0a5d3-126">En kund kan initiera kassan som en gästanvändare eller som en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-126">A customer can initiate checkout as a guest user or as a signed-in user.</span></span>

<span data-ttu-id="0a5d3-127">Information om hur du redigerar en kundvagnssida finns i [lägga till en kundvagnsmodul på en sida](add-cart-module.md).</span><span class="sxs-lookup"><span data-stu-id="0a5d3-127">For information about how to author a cart page, see [Add a cart module to a page](add-cart-module.md).</span></span>

## <a name="checkout-page"></a><span data-ttu-id="0a5d3-128">Kassasida</span><span class="sxs-lookup"><span data-stu-id="0a5d3-128">Checkout page</span></span>

<span data-ttu-id="0a5d3-129">Kassasidan anger var kunden anger den information som behövs för att göra en beställning.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-129">The checkout page is where customers enter the information that is required to place an order.</span></span>

<span data-ttu-id="0a5d3-130">Följande illustration visar ett exempel på kassasidan som har skapats med hjälp av online startpaketet.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-130">The following illustration show an example of a checkout page that was built by using the online starter kit.</span></span>

![Exempel på en kassasida](./media/Checkout.PNG)

<span data-ttu-id="0a5d3-132">Huvuddelen av kassasidan är där all orderinformation samlas in.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-132">The main body of the checkout page is where all the order information is collected.</span></span> <span data-ttu-id="0a5d3-133">Informationen omfattar leveransadress, leveransalternativ och betalningsinformation.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-133">This information includes the shipping address, delivery options, and payment information.</span></span> <span data-ttu-id="0a5d3-134">Kassan har ett steg-för-steg-flöde, eftersom informationen måste anges i en specifik order för att kunna bearbetas.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-134">Checkout has a step-by-step flow, because the information must be entered in a specific order to be processed.</span></span> <span data-ttu-id="0a5d3-135">Leveransadressen måste t.ex. anges innan leveranskostnaderna kan beräknas och betalningen kan godkännas.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-135">For example, the shipping address must be entered before the shipping costs can be calculated and the payment can be authorized.</span></span>

### <a name="shipping-address"></a><span data-ttu-id="0a5d3-136">Leveransadress</span><span class="sxs-lookup"><span data-stu-id="0a5d3-136">Shipping address</span></span>

<span data-ttu-id="0a5d3-137">En leveransadress måste anges om artiklar måste levereras.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-137">A shipping address is required if items must be shipped.</span></span> <span data-ttu-id="0a5d3-138">Formatet på leveransadresser för varje språkversion kan konfigureras i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-138">The format of shipping addresses for each locale can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="0a5d3-139">Om till exempel artiklarna ska levereras till USA måste leveransadressen innehålla gatuadress, region och postnummer.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-139">For example, if the items will be shipped to the United States, the shipping address must include a street address, state, and ZIP Code.</span></span> <span data-ttu-id="0a5d3-140">En del grundläggande verifiering sker för leverans adressfält, t.ex. validering av alfanumeriska tecken, maximal längd och siffror.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-140">Some basic input validation is done for shipping address fields, such as validation for alphanumeric characters, maximum length, and numbers.</span></span> <span data-ttu-id="0a5d3-141">Även om giltigheten för själva adressen inte har verifierats kan den här verifieringen utföras med hjälp av anpassade tjänster från tredje part.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-141">Although the validity of the address itself isn't verified, this verification can be done by using customized third-party services.</span></span>

<span data-ttu-id="0a5d3-142">Leveransadressen används för alla artiklar i vagnen som alternativet "leverera" har valts för.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-142">The shipping address is applied to all items in the cart that the "ship" option is selected for.</span></span> <span data-ttu-id="0a5d3-143">Om du använder det kassaflöde som finns i online startpaketet kan enskilda kundvagnsartiklar inte levereras till olika adresser.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-143">If you use the checkout flow that is provided in the online starter kit, individual cart items can't be shipped to different addresses.</span></span> <span data-ttu-id="0a5d3-144">Om du behöver den här funktionen kan den implementeras genom anpassningar av modulerna för utcheckning.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-144">If you require this capability, it can be implemented through customization of the checkout modules.</span></span>

<span data-ttu-id="0a5d3-145">När leveransadressen har angetts visas de leveransmetoder som är tillgängliga från Dynamics 365 Commerce onlinebutiken.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-145">After the shipping address is provided, the shipping methods that are available from the Dynamics 365 Commerce online store are shown.</span></span> <span data-ttu-id="0a5d3-146">Leveransmetoderna och adresserna som stöds kan konfigureras i handel.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-146">The shipping methods and the addresses that they support can be configured in Commerce.</span></span>

### <a name="payment"></a><span data-ttu-id="0a5d3-147">Betalning</span><span class="sxs-lookup"><span data-stu-id="0a5d3-147">Payment</span></span>

<span data-ttu-id="0a5d3-148">Nästa steg i kassaflödet är betalning.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-148">The next step in the checkout flow is payment.</span></span> <span data-ttu-id="0a5d3-149">I e-handel kan flera betalningsmetoder användas för att placera order, t.ex. kreditkort, presentkort och förmånspoäng.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-149">In e-Commerce, multiple methods of payment can be used to place orders, such as credit cards, gift cards, and loyalty points.</span></span> <span data-ttu-id="0a5d3-150">En kombination av dessa betalningsmetoder kan också användas.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-150">A combination of these payment methods can also be used.</span></span> <span data-ttu-id="0a5d3-151">Beroende på vilka betalningsmetoder som används kan ytterligare information krävas.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-151">Depending on the payment methods that are used, additional information might be required.</span></span> <span data-ttu-id="0a5d3-152">En kreditkortsbetalning kräver t.ex. en faktureringsadress.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-152">For example, a credit card payment requires a billing address.</span></span> <span data-ttu-id="0a5d3-153">Kreditkortsbetalningar bearbetas med hjälp av Adyen betalningskoppling.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-153">Credit card payments are processed by using the Adyen Payment Connector.</span></span>

#### <a name="loyalty-points"></a><span data-ttu-id="0a5d3-154">Bonuspoäng</span><span class="sxs-lookup"><span data-stu-id="0a5d3-154">Loyalty points</span></span>

<span data-ttu-id="0a5d3-155">Under kassaflödet kan en kund som är medlem i ett förmånsprogram och som har periodiserade förmånspoäng lösa in förmånspoäng för en order.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-155">During the checkout flow, a customer who is a member of a loyalty program and who has accrued loyalty points can redeem those loyalty points for an order.</span></span> <span data-ttu-id="0a5d3-156">Modulen förmånspoäng visas bara om kunden har ett befintligt förmånsmedlemsskap.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-156">The loyalty points module is shown only if the customer has an existing loyalty membership.</span></span> <span data-ttu-id="0a5d3-157">För icke-medlemmar och gästanvändare är modulen dold.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-157">For non-members and guest users, this module is hidden.</span></span>

#### <a name="gift-cards"></a><span data-ttu-id="0a5d3-158">Presentkort</span><span class="sxs-lookup"><span data-stu-id="0a5d3-158">Gift cards</span></span>

<span data-ttu-id="0a5d3-159">Online startpaketet ska lösa in sina interna presentkort för en beställning.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-159">The online starter kit lets internal gift cards be redeemed for an order.</span></span> <span data-ttu-id="0a5d3-160">Om du vill använda ett internt presentkort måste kunden vara inloggad.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-160">To apply an internal gift card, the customer must be signed in.</span></span> <span data-ttu-id="0a5d3-161">Om du vill ha ytterligare säkerhet rekommenderar vi att du anpassar flödet med hjälp av en PIN-kod (personal Identification Number) för interna presentkort.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-161">For additional security, we recommend that you customize the flow by using a personal identification number (PIN) for internal gift cards.</span></span>

### <a name="signed-in-and-guest-users"></a><span data-ttu-id="0a5d3-162">Inloggade och gästanvändare</span><span class="sxs-lookup"><span data-stu-id="0a5d3-162">Signed-in and guest users</span></span>

<span data-ttu-id="0a5d3-163">En kund kan slutföra utcheckningsprocessen som en gästanvändare eller som en inloggad användare.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-163">The customer can complete the checkout process as a guest user or a signed-in user.</span></span> <span data-ttu-id="0a5d3-164">Om kunden loggar in hämtas automatiskt kontoinformation som t.ex. sparade leveransadresser och sparade kreditkortsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-164">If the customer signs in, account information such as saved shipping addresses and saved credit card details is automatically retrieved.</span></span>

### <a name="order-summary"></a><span data-ttu-id="0a5d3-165">Orderöversikt</span><span class="sxs-lookup"><span data-stu-id="0a5d3-165">Order summary</span></span>

<span data-ttu-id="0a5d3-166">Kassan visar en sammanfattning av radartiklarna i kundvagnen, så att kunden kan verifiera ordern innan han eller hon placerar den.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-166">Checkout shows a summary of the line items in the cart, so that the customer can verify the order before he or she places it.</span></span> <span data-ttu-id="0a5d3-167">Radartiklarna kan inte redigeras under kassaflödet.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-167">The line items can't be edited during the checkout flow.</span></span> <span data-ttu-id="0a5d3-168">En länk till kundvagnen tillhandahålls dock om användaren vill gå tillbaka och redigerar radartiklarna.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-168">However, a link to the cart is provided in case the user wants to go back and edit line items.</span></span>

<span data-ttu-id="0a5d3-169">När kunden har angett leverans- och faktureringsinformation, visar ordersammanfattningen beloppet som förfaller efter förmånspoäng, presentkort och andra betalningar som har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-169">After the customer provides shipping and billing information, the order summary reflects the amount that is due after loyalty points, gift cards, and other payments have been applied.</span></span>

### <a name="order-confirmation-and-email"></a><span data-ttu-id="0a5d3-170">E-postmeddelande och orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="0a5d3-170">Order confirmation and email</span></span>

<span data-ttu-id="0a5d3-171">När kunden beställer en order lämnas ett bekräftelsenummer.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-171">When the customer places an order, a confirmation number is provided.</span></span> <span data-ttu-id="0a5d3-172">Vid denna tidpunkt har betalningen auktoriserats men inte debiterats.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-172">At this point, the payment has been authorized but not charged.</span></span> <span data-ttu-id="0a5d3-173">Betalningen debiteras först när ordern är uppfylld (dvs. när den antingen har levererats eller hämtats).</span><span class="sxs-lookup"><span data-stu-id="0a5d3-173">The payment will be charged only when the order is fulfilled (that is, when it's either shipped or picked up).</span></span>

<span data-ttu-id="0a5d3-174">När en order har skapats skickas en orderbekräftelse via e-post till kunden.</span><span class="sxs-lookup"><span data-stu-id="0a5d3-174">After an order is created, an order confirmation email is sent to the customer.</span></span>

<span data-ttu-id="0a5d3-175">Mer information om hur du redigerar en kassasida finns i [lägga till en kassamodul på en sida](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="0a5d3-175">For more information about how to author a checkout page, see [Add a checkout module to a page](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a5d3-176">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0a5d3-176">Additional resources</span></span>

[<span data-ttu-id="0a5d3-177">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="0a5d3-177">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="0a5d3-178">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="0a5d3-178">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="0a5d3-179">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="0a5d3-179">Account management pages overview</span></span>](quick-tour-account-management.md)
