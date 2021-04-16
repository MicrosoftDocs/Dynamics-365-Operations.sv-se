---
title: Kassarabatter
description: Kassarabatter ställs in och delas för Leverantörsreskontra och Kundreskontra.  Den tillgängliga kassarabatten kan definieras på kundfakturan eller leverantörsfakturan och dras av om fakturan betalas innan kassarabattsdatumet har förfallit.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: roschlom
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a9effdbe2aed6175273332654755b0ebc46659
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830493"
---
# <a name="cash-discounts"></a><span data-ttu-id="ed84a-104">Kassarabatter</span><span class="sxs-lookup"><span data-stu-id="ed84a-104">Cash discounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed84a-105">Kassarabatter ställs in och delas för Leverantörsreskontra och Kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="ed84a-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="ed84a-106">Den tillgängliga kassarabatten kan definieras på kundfakturan eller leverantörsfakturan och dras av om fakturan betalas innan kassarabattsdatumet har förfallit.</span><span class="sxs-lookup"><span data-stu-id="ed84a-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

## <a name="cash-discounts"></a><span data-ttu-id="ed84a-107">Kassarabatter</span><span class="sxs-lookup"><span data-stu-id="ed84a-107">Cash discounts</span></span>

<span data-ttu-id="ed84a-108">Kassarabatter för både kunder eller leverantörer kan skapas på sidan Kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="ed84a-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="ed84a-109">Du kan också definiera, genom att använda fältet Nästa rabattkod, en serie kassarabatter som följer efter varandra när tidigare kassarabattdatum förfaller.</span><span class="sxs-lookup"><span data-stu-id="ed84a-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="ed84a-110">Mer information finns i ”Exempel: Serie med kassarabatter” senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ed84a-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="ed84a-111">Om fakturan, kredittransaktionen (antingen en betalning eller en kreditfaktura) eller båda anges i en annan valuta än redovisningsvalutan för den juridiska personen beräknas kassarabatten med hjälp av valutakursen för datumet för betalningen eller kreditfakturan.</span><span class="sxs-lookup"><span data-stu-id="ed84a-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="ed84a-112">Om faktura- och kreditdokumentet anges i olika juridiska personer, och om redovisningsvalutorna förde juridiska personerna skiljer sig, hämtas valutakursen från den juridiska personen på fakturan, från datumet för kreditdokumentet.</span><span class="sxs-lookup"><span data-stu-id="ed84a-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="ed84a-113">Mer information finns i ”Exempel: Valutakurser för kassarabatter” senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="ed84a-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>

## <a name="defaulting-order-of-cash-discount-main-account"></a><span data-ttu-id="ed84a-114">Ange standardordning för kassarabatthuvudkontot</span><span class="sxs-lookup"><span data-stu-id="ed84a-114">Defaulting order of cash discount main account</span></span>

<span data-ttu-id="ed84a-115">Om en faktura betalas i tid för en kassarabatt bokförs rabatten automatiskt på ett huvudkonto för kassarabatter enligt följande standardprioritet:</span><span class="sxs-lookup"><span data-stu-id="ed84a-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="ed84a-116">Huvudkontot som angetts i fältet Alternativt kassarabattskonto på sidan Kvitta öppna transaktioner för kunden eller på sidan Kvitta öppna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="ed84a-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="ed84a-117">Huvudkontot som angetts i fältet Kundkassarabatt eller fältet Leverantörskassarabatt i redovisningsbokföringsgruppen som är tilldelad till momskoden på fakturan.</span><span class="sxs-lookup"><span data-stu-id="ed84a-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="ed84a-118">Ställ in redovisningsbokföringsgrupper på sidan för redovisningsbokföringsgrupper och tilldela dem till momskoder på sidan Momskoder.</span><span class="sxs-lookup"><span data-stu-id="ed84a-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="ed84a-119">Huvudredovisningskontot på sidan Kassarabatter i fältet Huvudkonto för kundrabatter eller fältet Huvudkonto för leverantörsrabatter för kassarabattkoden på den kvittade fakturan.</span><span class="sxs-lookup"><span data-stu-id="ed84a-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="ed84a-120">Huvudkontot för kassarabatter så som detta definierats på sidan Konton för automatiska transaktioner.</span><span class="sxs-lookup"><span data-stu-id="ed84a-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="ed84a-121"> Exempel: Serie med kassarabatter</span><span class="sxs-lookup"><span data-stu-id="ed84a-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="ed84a-122">Ställ in tre kassarabattkoder enligt följande:</span><span class="sxs-lookup"><span data-stu-id="ed84a-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="ed84a-123">Kod 5D10% – En kassarabatt på 10 % om beloppet betalas inom 5 dagar.</span><span class="sxs-lookup"><span data-stu-id="ed84a-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="ed84a-124">Kod 10D5% – En kassarabatt på 5 % om beloppet betalas inom 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="ed84a-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="ed84a-125">Kod 14D2% – En kassarabatt på 2 % om beloppet betalas inom 14 dagar.</span><span class="sxs-lookup"><span data-stu-id="ed84a-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="ed84a-126">I fältet Nästa rabattkod:</span><span class="sxs-lookup"><span data-stu-id="ed84a-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="ed84a-127">Välj 10D5% för koden 5D10%.</span><span class="sxs-lookup"><span data-stu-id="ed84a-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="ed84a-128">Välj 14D2% för koden 10D5%.</span><span class="sxs-lookup"><span data-stu-id="ed84a-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="ed84a-129">För koden 14D2% låter du fältet Nästa rabattkod vara tomt.</span><span class="sxs-lookup"><span data-stu-id="ed84a-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="ed84a-130">De tre kassarabatterna följer efter varandra allteftersom betalningsdatumet passerar det föregående kassarabattdatumet på fakturan.</span><span class="sxs-lookup"><span data-stu-id="ed84a-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="ed84a-131">Endast en kassarabatt beviljas när fakturan betalats, baserat på vilket kassarabattdatum som följer i serien med kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="ed84a-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="ed84a-132"> Exempel: Valutakurser för kassarabatter</span><span class="sxs-lookup"><span data-stu-id="ed84a-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="ed84a-133">Din juridisk persons redovisningsvaluta är EUR och följande valutakurser anges för USD:</span><span class="sxs-lookup"><span data-stu-id="ed84a-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="ed84a-134">1 februari = 110</span><span class="sxs-lookup"><span data-stu-id="ed84a-134">February 1 = 110</span></span>
-   <span data-ttu-id="ed84a-135">1 mars = 80</span><span class="sxs-lookup"><span data-stu-id="ed84a-135">March 1 = 80</span></span>

<span data-ttu-id="ed84a-136">En faktura på 1000 USD med villkor för kassarabatt på 20D2% bokförs den 15 februari.</span><span class="sxs-lookup"><span data-stu-id="ed84a-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="ed84a-137">Fakturans belopp i redovisningsvalutan är 1 100 EUR.</span><span class="sxs-lookup"><span data-stu-id="ed84a-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="ed84a-138">En betalning på 980 USD kvittas mot fakturan den 1 mars.</span><span class="sxs-lookup"><span data-stu-id="ed84a-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="ed84a-139">Kassarabattbeloppet är 20 USD.</span><span class="sxs-lookup"><span data-stu-id="ed84a-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="ed84a-140">Redovisningsvalutabeloppet för betalningen är 784 EUR.</span><span class="sxs-lookup"><span data-stu-id="ed84a-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="ed84a-141">Redovisningsvalutabeloppet för kassarabatten beräknas med hjälp av valutakursen för den 1 mars 1: 20 \* 80 / 100 = 16 EUR.</span><span class="sxs-lookup"><span data-stu-id="ed84a-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>

> [!NOTE]
> <span data-ttu-id="ed84a-142">Om alternativet Beräkna kassarabatter för delbetalningar har valts på sidan Parametrar för kundreskontra eller sidan Parametrar för leverantörsreskontra används valutakursen som gäller på datumet för respektive delbetalning.</span><span class="sxs-lookup"><span data-stu-id="ed84a-142">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]