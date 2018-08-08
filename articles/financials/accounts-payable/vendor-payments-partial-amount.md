---
title: "Leverantörsbetalningar för ett delvist belopp"
description: "Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör. Det här avsnittet innehåller en beskrivning av de olika alternativen för att hantera den här situationen."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2644e0a27eff3e45ddcddb89c9aac9230190788f
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-payments-for-a-partial-amount"></a><span data-ttu-id="0b9f1-104">Leverantörsbetalningar för ett delbelopp</span><span class="sxs-lookup"><span data-stu-id="0b9f1-104">Vendor payments for a partial amount</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b9f1-105">Ibland kan du utföra betalningar som är mindre än beloppet i en faktura till en leverantör.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-105">Sometimes, you might make a payment to a vendor that is less than the amount of an invoice.</span></span> <span data-ttu-id="0b9f1-106">Den här artikeln beskriver de olika alternativen för att hantera den här situationen.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-106">This article describes the various options for handling this situation.</span></span> <span data-ttu-id="0b9f1-107">Vilka alternativ som är tillgängliga för dig beror på dina affärskrav och konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-107">The options that are available to you depend on your business requirements and configuration.</span></span> 

<a name="cash-discount-amounts"></a><span data-ttu-id="0b9f1-108">Kassarabattbelopp</span><span class="sxs-lookup"><span data-stu-id="0b9f1-108">Cash discount amounts</span></span>
---------------------

<span data-ttu-id="0b9f1-109">En leverantör kan erbjuda dig en kassarabatt för att betala en faktura före förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-109">A vendor can offer you a cash discount for paying an invoice before the due date.</span></span> <span data-ttu-id="0b9f1-110">Till exempel anger du en faktura på 100,00 som anger en kassarabatt 2 procent, om fakturan betalas inom 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-110">For example, you enter an invoice for 100.00 that specifies a 2-percent cash discount if the invoice is paid within 10 days.</span></span> <span data-ttu-id="0b9f1-111">Förfallodatumtermerna är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-111">The due date terms are 30 days.</span></span> <span data-ttu-id="0b9f1-112">Om ett betalningsförslag använder kassarabatt som villkor för att välja en faktura om om förslaget körs på eller före kassarabattsdatumet, kommer fakturan att markeras till betalning och betalningen skapas för 98,00.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-112">If a payment proposal uses the cash discount as a criterion for selecting an invoice, and if the proposal is run on or before the cash discount date, the invoice is selected for payment, and the payment is created for 98.00.</span></span> <span data-ttu-id="0b9f1-113">En kassarabatt kan också användas för en enstaka betalning som skapats manuellt.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-113">A cash discount can also be taken for a one-off payment that was created manually.</span></span>

## <a name="partial-payments-with-cash-discounts"></a><span data-ttu-id="0b9f1-114">Delbetalningar med kassarabatter</span><span class="sxs-lookup"><span data-stu-id="0b9f1-114">Partial payments with cash discounts</span></span>
<span data-ttu-id="0b9f1-115">När du gör en delvis betalning, kan du planera att göra en ytterligare delvis betalning för att helt kvitta fakturan.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-115">When you make a partial payment, you might plan to make an additional partial payment to fully settle the invoice.</span></span> <span data-ttu-id="0b9f1-116">För att få kassarabatt för en delvis betalning måste du ange alternativet **Beräkna kassarabatter för delvisa betalningar** till**Ja** på sidan **Obetalda parametrar för konto**.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-116">To take a cash discount for a partial payment, you must set the **Calculate cash discounts for partial payments** option to **Yes** on the **Account payable parameters** page.</span></span> 

<span data-ttu-id="0b9f1-117">Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-117">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="0b9f1-118">En faktura på 100,00 bokförs.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-118">An invoice is posted for 100.00.</span></span> <span data-ttu-id="0b9f1-119">Om du gör en betalning på 49,00 inom 10 dagar, anger du ett debetbelopp på 49,00 i en betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-119">If you make a payment of 49.00 within 10 days, you enter a debit of 49.00 in a payment journal.</span></span> <span data-ttu-id="0b9f1-120">När du kvittar delbetalningen på sidan **Kvitta öppna transaktioner** visas **1,00** i fältet **Kassarabattbelopp att utnyttja**.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-120">When you settle the partial payment on the **Settle open transactions** page, **1.00** appears in the **Cash discount amount to take** field.</span></span> 

> [!NOTE] 
> <span data-ttu-id="0b9f1-121">Om du anger en delbetalning och anger hela fakturabeloppet i fältet **Belopp att kvitta**, kommer fältet **Kassarabattbelopp att utnyttja** att beräknas om automatiskt när du bokför transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-121">If you enter a partial payment and leave the full invoice amount in the **Amount to settle** field, the **Cash discount amount to take** field is automatically recalculated when you post the transactions.</span></span>

## <a name="credit-notes-with-cash-discounts"></a><span data-ttu-id="0b9f1-122">Kreditfakturor med kassarabatter</span><span class="sxs-lookup"><span data-stu-id="0b9f1-122">Credit notes with cash discounts</span></span>
<span data-ttu-id="0b9f1-123">Du kanske returnerar vissa av artiklarna i en faktura och tar emot en kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-123">You might return some of the items on an invoice and receive a credit note.</span></span> <span data-ttu-id="0b9f1-124">Om en kassarabatt utfördes på den ursprungliga fakturan, kan du dra av värdet för rabatter och ta emot en återbetalning för rätt beloppet.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-124">If a cash discount was taken on the original invoice, you can subtract the value of the discount and receive a refund for the correct amount.</span></span> <span data-ttu-id="0b9f1-125">Om alternativet **Beräkna kassarabatter för kreditfakturor** anges på sidan **Ja** på sidan **Parametrar för leverantörsreskontra** beräknas rabatten automatiskt för kreditfakturan.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-125">If the **Calculate cash discounts for credit notes** option is set to **Yes** on the **Accounts payable parameters** page, the discount is automatically calculated for the credit note.</span></span> 

<span data-ttu-id="0b9f1-126">Om du till exempel får 2 procent kassarabatt om fakturan betalas inom 10 dagar, efter att den har utfärdats.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-126">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="0b9f1-127">En faktura på 100,00 bokförs.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-127">An invoice for 100.00 is posted.</span></span> <span data-ttu-id="0b9f1-128">Om du återlämnar varorna och få en kreditfaktura kan du ange kreditfakturan för hela beloppet för den ursprungliga fakturan, 100,00 tillsammans med 2 procents kassarabatten som också definieras på kreditnotan.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-128">If you return the goods and receive a credit note, you can enter the credit note for the full amount of the original invoice, 100.00, together with the 2-percent cash discount that is also defined on the credit memo.</span></span>  <span data-ttu-id="0b9f1-129">När du visar kreditfakturan på sidan **Kvitta transaktioner**, visas **98,00** i fältet **Belopp att kvitta** och **-2,00** visas i fältet **Kassarabattbelopp**.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-129">When you view the credit note on the **Settle transactions** page, **98.00** appears in the **Amount to settle** field, and **-2.00** appears in the **Cash discount amount** field.</span></span> <span data-ttu-id="0b9f1-130">Rabattbeloppet bokförs på ett kassarabattkonto.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-130">The discount amount is posted to a cash discount account.</span></span>

## <a name="overpaymentunderpayment-amounts"></a><span data-ttu-id="0b9f1-131">Över- och underbetalningsbelopp</span><span class="sxs-lookup"><span data-stu-id="0b9f1-131">Overpayment/underpayment amounts</span></span>
<span data-ttu-id="0b9f1-132">Du kanske vill göra en delvis betalning, där beloppet som fortfarande måste kvittas är mycket litet.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-132">You might make a partial payment where the amount that must still be settled is very small.</span></span> <span data-ttu-id="0b9f1-133">Exempelvis är leverantörsfakturan för 1 000,00 och du betalar 999,90.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-133">For example, the vendor invoice is for 1,000.00, and you pay 999.90.</span></span> <span data-ttu-id="0b9f1-134">Om det resterande beloppet är mindre än det belopp som angetts för över- eller underbetalningar på sidan **Parametrar för leverantörsreskontra** bokförs skillnaden automatiskt till ett överbetalning-/underbetalningredovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="0b9f1-134">If the remaining amount is less than the amount that is specified for overpayments or underpayments on the **Accounts payable parameters** page, the difference is automatically posted to an overpayment/underpayment ledger account.</span></span>


<span data-ttu-id="0b9f1-135">Mer information finns i [Översikt över leverantörsbetalning](../cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0b9f1-135">For more information, see [Vendor payment overview](../cash-bank-management/tasks/vendor-payment-overview.md).</span></span>

