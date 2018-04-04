---
title: "Kreditkortinställning, auktorisering och registrering"
description: "Den här artikeln innehåller en översikt över kreditkortskontroll i Microsoft Dynamics 365 for Finance and Operations. Här finns information om hur du ställer in en betalningstjänst, lägger till ett kreditkort till en försäljningsorder och annullerar en auktorisering."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a6354563fdebff901498f1cd6caed3aedae668b
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="credit-card-setup-authorization-and-capture"></a><span data-ttu-id="672bc-104">Kreditkortinställning, auktorisering och registrering</span><span class="sxs-lookup"><span data-stu-id="672bc-104">Credit card setup, authorization, and capture</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="672bc-105">Den här artikeln innehåller en översikt över kreditkortskontroll i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="672bc-105">This article provides an overview of credit card authorization in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="672bc-106">Här finns information om hur du ställer in en betalningstjänst, lägger till ett kreditkort till en försäljningsorder och annullerar en auktorisering.</span><span class="sxs-lookup"><span data-stu-id="672bc-106">It includes information about how to set up a payment service, add a credit card to a sales order, and void an authorization.</span></span>

<a name="setting-up-the-credit-card-payment-service"></a><span data-ttu-id="672bc-107">Ställa in kreditkortbetalningtjänsten</span><span class="sxs-lookup"><span data-stu-id="672bc-107">Setting up the credit card payment service</span></span>
------------------------------------------

<span data-ttu-id="672bc-108">Om du vill använda kreditkort måste du ställa in och aktivera en betalning på sidan Betalningtjänst.</span><span class="sxs-lookup"><span data-stu-id="672bc-108">To use credit cards, you must set up and activate a payment service on the Payment services page.</span></span> <span data-ttu-id="672bc-109">En betalningstjänst fungerar som en brygga mellan din juridiska person och banken som bearbetar en kunds kreditkortavgifter.</span><span class="sxs-lookup"><span data-stu-id="672bc-109">A payment service acts as a bridge between your legal entity and the bank that processes a customer's credit card charges.</span></span> <span data-ttu-id="672bc-110">Du måste arbeta med en kreditkortleverantör, som anges i fältet Betalningkoppling och ställer in ett konto med den leverantören.</span><span class="sxs-lookup"><span data-stu-id="672bc-110">You must work with a credit card provider that is listed in the Payment connector field and set up an account with that provider.</span></span> <span data-ttu-id="672bc-111">Du måste sedan ställa in andra alternativ på sidan Betalningtjänst, ställa in kreditkorttyper för American Express Discover och MasterCard på sian Kreditkorttyp och aktivera leverantören som standardleverantören.</span><span class="sxs-lookup"><span data-stu-id="672bc-111">You must then set up the other options on the Payment services page, set up credit card types for American Express, Discover, MasterCard, and Discover on the Credit card types page, and activate the provider as the default provider.</span></span> <span data-ttu-id="672bc-112">Du måste även följa stegen för att slutföra inställningarna:</span><span class="sxs-lookup"><span data-stu-id="672bc-112">You must also follow these steps to complete your setup:</span></span>
-   <span data-ttu-id="672bc-113">På sidan Parametrar för kundreskontra anger du parametrar för att använda kreditkortskontroller.</span><span class="sxs-lookup"><span data-stu-id="672bc-113">On the Accounts receivable parameters page, specify parameters for using credit card authorizations.</span></span>
-   <span data-ttu-id="672bc-114">På sidan Betalningsvillkor ställer du in betalningsvillkor för kreditkort.</span><span class="sxs-lookup"><span data-stu-id="672bc-114">On the Terms of payment page, set up payment terms for credit cards.</span></span> <span data-ttu-id="672bc-115">I fältet Betalningstyp väljer du Kreditkort.</span><span class="sxs-lookup"><span data-stu-id="672bc-115">In the Payment type field, select Credit card.</span></span>
-   <span data-ttu-id="672bc-116">På sidan Kundkreditokort anger du kreditkortsinformation för kunder.</span><span class="sxs-lookup"><span data-stu-id="672bc-116">On the Customer credit cards page, enter credit card information for customers.</span></span>

## <a name="adding-a-new-credit-card"></a><span data-ttu-id="672bc-117">Lägg till ett nytt kreditkort</span><span class="sxs-lookup"><span data-stu-id="672bc-117">Adding a new credit card</span></span>
<span data-ttu-id="672bc-118">Du kan skapa nya kreditkortsposter på sidan Kunder, genom att använda Kund, Inställning, Kreditkort.</span><span class="sxs-lookup"><span data-stu-id="672bc-118">You can create new credit card records on the Customers page by using Customer, Set up, Credit card.</span></span> <span data-ttu-id="672bc-119">Du kan också skapa kreditkortsposter när du registrerar försäljningsorder på sidan Försäljningsorder, genom att använda Hantera, Kund, Kreditkort, Register.</span><span class="sxs-lookup"><span data-stu-id="672bc-119">You can also create credit card records when you enter sales orders on the Sales order page, by using Manage, Customer, Credit card, Register.</span></span>
<span data-ttu-id="672bc-120">Lägg till ett kreditkort till en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="672bc-120">Adding a credit card to a sales order</span></span>
-------------------------------------

<span data-ttu-id="672bc-121">Du kan lägga till ett kreditkort till en försäljningsorder, genom att välja ett kreditkort i kreditkortuppslagningen på snabbfliken Pris och rabatter på sidan Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="672bc-121">You can add a credit card to a sales order by selecting a credit card in the credit card lookup on the Price and discounts FastTab on the Sales order page.</span></span> <span data-ttu-id="672bc-122">Om du vill starta behörighetsprocessen, väljer du kreditkort och godkänna i åtgärdsfönstret på fliken Hantera.</span><span class="sxs-lookup"><span data-stu-id="672bc-122">To start the authorization process, on the Action Pane, on the Manage tab, select Credit card and Authorize.</span></span>
<span data-ttu-id="672bc-123">Kreditkortskontroll</span><span class="sxs-lookup"><span data-stu-id="672bc-123">Authorizing a credit card</span></span>
-------------------------

<span data-ttu-id="672bc-124">När ett kreditkort auktoriseras verifieras kortnumret och kortinnehavarens namn, och det tillgängliga kreditsaldot bekräftas.</span><span class="sxs-lookup"><span data-stu-id="672bc-124">When a credit card is authorized, the card number and cardholder's name are verified, and the available credit balance is confirmed.</span></span> <span data-ttu-id="672bc-125">Du kan även verifiera cvv-kod och kortinnehavarens adress verifieras.</span><span class="sxs-lookup"><span data-stu-id="672bc-125">Optionally, the card verification value and the cardholder’s address are verified.</span></span> <span data-ttu-id="672bc-126">Kundens tillgängliga kreditsaldo minskas med beloppet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="672bc-126">The customer's available credit balance is then reduced by the amount of the invoice.</span></span> <span data-ttu-id="672bc-127">Betaltjänsten skickar information om att kreditkortet har godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="672bc-127">The payment service sends information that the credit card has been approved or declined.</span></span> <span data-ttu-id="672bc-128">När en försäljningsorder faktureras, debiteras kreditkortet (samlats in) med fakturabeloppet.</span><span class="sxs-lookup"><span data-stu-id="672bc-128">When the sales order is invoiced, the credit card is charged (captured) for the invoice amount.</span></span>

### <a name="card-verification-value"></a><span data-ttu-id="672bc-129">Kortverifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="672bc-129">Card verification value</span></span>

<span data-ttu-id="672bc-130">Du kan kräva cvv-kod, som ibland refereras till som kortets säkerhetkod.</span><span class="sxs-lookup"><span data-stu-id="672bc-130">You can require the card verification value, which is sometimes referred to as the card's security code.</span></span> <span data-ttu-id="672bc-131">För American Express är detta ett fyrsiffrigt värde.</span><span class="sxs-lookup"><span data-stu-id="672bc-131">For American Express, this is a four-digit value.</span></span> <span data-ttu-id="672bc-132">För Discover, MasterCard och Visa är det ett ensiffrigt värde.</span><span class="sxs-lookup"><span data-stu-id="672bc-132">For Discover, MasterCard, and Visa, it is a three-digit value.</span></span>

### <a name="address-verification"></a><span data-ttu-id="672bc-133">Adressverifiering</span><span class="sxs-lookup"><span data-stu-id="672bc-133">Address verification</span></span>

<span data-ttu-id="672bc-134">Information om adressverifieringen skickas alltid till betalningsleverantören.</span><span class="sxs-lookup"><span data-stu-id="672bc-134">Address verification information is always sent to the payment provider.</span></span> <span data-ttu-id="672bc-135">Du kan bestämma hur mycket information som krävs för att en transaktion ska godkännas.</span><span class="sxs-lookup"><span data-stu-id="672bc-135">You can decide how much information is required for a transaction to be accepted.</span></span> <span data-ttu-id="672bc-136">Se till att kontrollera med din leverantör för att avgöra om denne godkänner denna information.</span><span class="sxs-lookup"><span data-stu-id="672bc-136">Be sure to check with your provider to determine whether it accepts this information.</span></span> <span data-ttu-id="672bc-137">Här följer alternativen för adressverifiering:</span><span class="sxs-lookup"><span data-stu-id="672bc-137">Here are the options for address verification:</span></span>
-   <span data-ttu-id="672bc-138">**Acceptera alltid transaktionen** - Acceptera transaktionen oavsett adressverifieringresultat.</span><span class="sxs-lookup"><span data-stu-id="672bc-138">**Always accept transaction** – Accept the transaction, regardless of address verification results.</span></span>
-   <span data-ttu-id="672bc-139">**Kontohållare** – Jämför kortinnehavarens namn från transaktionen med kreditkortsföretagets information.</span><span class="sxs-lookup"><span data-stu-id="672bc-139">**Account holder** – Compare the cardholder's name from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="672bc-140">**Faktureringsadress** – Jämför kortinnehavarens namn och faktureringsadress från transaktionen med kreditkortsföretagets information.</span><span class="sxs-lookup"><span data-stu-id="672bc-140">**Billing address** – Compare the cardholder's name and billing address from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="672bc-141">**Postnummer för fakturering** – Jämför kortinnehavarens namn och faktureringsadress och postnummer från transaktionen med kreditkortsföretagets information.</span><span class="sxs-lookup"><span data-stu-id="672bc-141">**Billing postal code** – Compare the cardholder's name, billing address, and postal code from the transaction with the credit card company’s information.</span></span>

## <a name="data-support"></a><span data-ttu-id="672bc-142">Datasupport</span><span class="sxs-lookup"><span data-stu-id="672bc-142">Data support</span></span>
<span data-ttu-id="672bc-143">För respektive kreditkortstyp som stöds kan du ange datasupportnivån.</span><span class="sxs-lookup"><span data-stu-id="672bc-143">For each credit card type that is supported, you can specify the level of data support.</span></span> <span data-ttu-id="672bc-144">Denna nivå kontrollerar hur mycket information om en transaktion överförs till betalningtjänsten.</span><span class="sxs-lookup"><span data-stu-id="672bc-144">The level controls how much information about a transaction is transferred to the payment service.</span></span> <span data-ttu-id="672bc-145">Se till att kontrollera med leverantören för att avgöra om den kan ange den här informationen.</span><span class="sxs-lookup"><span data-stu-id="672bc-145">Be sure to check with your provider to determine whether it can provide this information.</span></span> <span data-ttu-id="672bc-146">Här följer alternativen för datasupportnivån:</span><span class="sxs-lookup"><span data-stu-id="672bc-146">Here are the options for the level of data support:</span></span>
-   <span data-ttu-id="672bc-147">**Nivå 1** – Överför transaktionsdatum, transaktionsbelopp och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="672bc-147">**Level 1** – Transfer the transaction date, transaction amount, and description.</span></span>
-   <span data-ttu-id="672bc-148">**Nivå 2** – Överför all nivå 1-information, plus leverans- och handelsadresser och momsinformation.</span><span class="sxs-lookup"><span data-stu-id="672bc-148">**Level 2** – Transfer all Level 1 information, plus the shipping and merchant addresses, and tax information.</span></span>
-   <span data-ttu-id="672bc-149">**Nivå 3** – Överför nivå 2-information, plus information om orderrad.</span><span class="sxs-lookup"><span data-stu-id="672bc-149">**Level 3** – Transfer all Level 2 information, plus order line information.</span></span>

## <a name="partial-payments"></a><span data-ttu-id="672bc-150">Delbetalningar</span><span class="sxs-lookup"><span data-stu-id="672bc-150">Partial payments</span></span>
<span data-ttu-id="672bc-151">Om du levererar en delorder kommer beloppet för denna del av ordern att regitreras; tillståndet, som gällde beloppet för hela ordern, stängs.</span><span class="sxs-lookup"><span data-stu-id="672bc-151">If you ship part of an order, the amount of the partial order is captured, and the authorization, which was for the amount of the whole order, is closed.</span></span> <span data-ttu-id="672bc-152">Ett nytt tillstånd skickas sedan för det återstående beloppet för den order som inte har levererats.</span><span class="sxs-lookup"><span data-stu-id="672bc-152">A new authorization is then submitted for the remaining amount of the order that hasn't been shipped.</span></span>

## <a name="voiding-an-authorization"></a><span data-ttu-id="672bc-153">Annullera en auktorisering </span><span class="sxs-lookup"><span data-stu-id="672bc-153">Voiding an authorization</span></span>
<span data-ttu-id="672bc-154">Om du vill annullera en kreditkortskontroll kan du ändra betalningsmetoden till en annan metod som inte har någon typ av kreditkort.</span><span class="sxs-lookup"><span data-stu-id="672bc-154">To void a credit card authorization, you can change the method of payment to another method that doesn't have a type of Credit card.</span></span>






