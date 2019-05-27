---
title: Översikt över kundbetalning
description: Den här guiden går igenom olika metoder som används för att ange kundbetalningar.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e82be0d68165f62bbdc72a70b0675c7418b14ae
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566143"
---
# <a name="customer-payment-overview"></a><span data-ttu-id="e5d87-103">Översikt över kundbetalning</span><span class="sxs-lookup"><span data-stu-id="e5d87-103">Customer payment overview</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e5d87-104">Den här guiden går igenom olika metoder som används för att ange kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e5d87-104">This task guide walks through various methods used to enter customer payments.</span></span> <span data-ttu-id="e5d87-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e5d87-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="e5d87-106">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="e5d87-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="e5d87-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e5d87-107">Click New.</span></span>
3. <span data-ttu-id="e5d87-108">Välj den betalningsjournal där kundbetalningarna sparas.</span><span class="sxs-lookup"><span data-stu-id="e5d87-108">Select the payment journal which the customer payments will be saved.</span></span>
4. <span data-ttu-id="e5d87-109">Välj journalen eller ange den manuellt.</span><span class="sxs-lookup"><span data-stu-id="e5d87-109">Select or manually enter the journal.</span></span>
5. <span data-ttu-id="e5d87-110">Klicka på Ange kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e5d87-110">Click Enter customer payments.</span></span>
    * <span data-ttu-id="e5d87-111">Ange kundbetalningar används för att registrera en kundbetalning åt gången.</span><span class="sxs-lookup"><span data-stu-id="e5d87-111">Enter customer payments is used to record one customer payment at a time.</span></span> <span data-ttu-id="e5d87-112">Du anger betalningsinformationen överst och sedan kan du markera fakturorna som har betalats med betalningen, alla från samma sida.</span><span class="sxs-lookup"><span data-stu-id="e5d87-112">You enter the payment information at the top, and then you can mark the invoices that were paid by the payment, all from the same page.</span></span>  
6. <span data-ttu-id="e5d87-113">Ange den kund från vilken du har tagit emot betalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-113">Enter the customer from whom you received the payment.</span></span>
    * <span data-ttu-id="e5d87-114">Om du inte känner till kunden, men känner till en transaktion som har betalats, kan du använda fältet Transaktion för att ange betalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-114">If you don't know the customer but do know a transaction that was paid, you can use the Transaction field to enter the payment.</span></span> <span data-ttu-id="e5d87-115">Ange eller välj fakturan i fältet Transaktion.</span><span class="sxs-lookup"><span data-stu-id="e5d87-115">Enter or select the invoice in the Transaction field.</span></span> <span data-ttu-id="e5d87-116">Kunden hämtas som standard automatiskt när du har valt transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-116">The customer will automatically default after you select the transaction.</span></span>  
7. <span data-ttu-id="e5d87-117">Ange en betalningsreferens i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="e5d87-117">In the Payment reference field, enter a payment reference.</span></span>
    * <span data-ttu-id="e5d87-118">Betalningsreferensen kan vara kundens checknummer eller en referens eller från kundens elektroniska betalning.</span><span class="sxs-lookup"><span data-stu-id="e5d87-118">The payment reference could be the customer's check number or a reference from the customer's electronic payment.</span></span> <span data-ttu-id="e5d87-119">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="e5d87-119">The payment reference is only required if you mark to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="e5d87-120">Välj om betalningen ska inkluderas på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="e5d87-120">Select whether the payment will be included on a deposit slip.</span></span> 
9. <span data-ttu-id="e5d87-121">Ange beloppet för kundbetalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-121">Enter the amount of the customer payment.</span></span>
    * <span data-ttu-id="e5d87-122">Betalningsbeloppet hämtas inte som standard.</span><span class="sxs-lookup"><span data-stu-id="e5d87-122">The payment amount will not default.</span></span> <span data-ttu-id="e5d87-123">Det måste anges manuellt.</span><span class="sxs-lookup"><span data-stu-id="e5d87-123">It must be manually entered.</span></span>  
10. <span data-ttu-id="e5d87-124">Markera fakturorna som betalades av kunden.</span><span class="sxs-lookup"><span data-stu-id="e5d87-124">Mark the invoices that were paid by the customer.</span></span>
    * <span data-ttu-id="e5d87-125">Om betalningen är en förskottsbetalning behöver du inte välja några fakturor för kvittning.</span><span class="sxs-lookup"><span data-stu-id="e5d87-125">If the payment is a prepayment, you are not required to mark any invoices for settlement.</span></span> <span data-ttu-id="e5d87-126">Betalningen kan fortfarande sparas och bokföras.</span><span class="sxs-lookup"><span data-stu-id="e5d87-126">The payment can still be saved and posted.</span></span> <span data-ttu-id="e5d87-127">Kvittningen till en faktura kan utföras vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="e5d87-127">Settlement to an invoice can happen at a later time.</span></span>  
11. <span data-ttu-id="e5d87-128">Ange beloppet för den betalning som ska kvittas mot den markerade fakturan.</span><span class="sxs-lookup"><span data-stu-id="e5d87-128">Enter the amount of the payment that should be settled to the marked invoice.</span></span> 
    * <span data-ttu-id="e5d87-129">Det här fältet kan användas när betalningen gäller en delbetalning.</span><span class="sxs-lookup"><span data-stu-id="e5d87-129">This field can be used when the payment is for a partial payment.</span></span> <span data-ttu-id="e5d87-130">Om du inte anger något belopp kommer kvittningsbeloppet bestämmas automatiskt för dig.</span><span class="sxs-lookup"><span data-stu-id="e5d87-130">If you don't enter an amount, the amount to settle will automatically be determined for you.</span></span>  
12. <span data-ttu-id="e5d87-131">Klicka på Spara i journal.</span><span class="sxs-lookup"><span data-stu-id="e5d87-131">Click Save in journal.</span></span>
    * <span data-ttu-id="e5d87-132">Kontrollera att motkontot har definierats innan du sparar betalningen till journalen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-132">Before you save the payment to the journal, make sure that the offset account is defined.</span></span> <span data-ttu-id="e5d87-133">Om du använder Spara i journalen sparas betalningen och flyttas till journalen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-133">Using Save in journal will save the payment and move it to the journal.</span></span> <span data-ttu-id="e5d87-134">Du kan sedan fortsätta och ange nästa betalning.</span><span class="sxs-lookup"><span data-stu-id="e5d87-134">You can then continue entering the next payment.</span></span>  
13. <span data-ttu-id="e5d87-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e5d87-135">Close the page.</span></span>
14. <span data-ttu-id="e5d87-136">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="e5d87-136">Click Lines.</span></span>
    * <span data-ttu-id="e5d87-137">När du öppnar rader visas alla betalningar som du har registrerat på sidan Ange kundbetalningar och sparat i journalen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-137">When opening Lines, you will see any payments you recorded on the Enter customer payments page and saved into the journal.</span></span> <span data-ttu-id="e5d87-138">Du kan också använda den här sidan för att ange nya kundbetalningar eller redigera en befintlig kundbetalning innan den bokförs.</span><span class="sxs-lookup"><span data-stu-id="e5d87-138">You can also use this page to enter new customer payments, or edit existing customer payment before they are posted.</span></span>  
15. <span data-ttu-id="e5d87-139">Klicka på Ny för att skapa en annan betalning.</span><span class="sxs-lookup"><span data-stu-id="e5d87-139">Click New to create another payment.</span></span> 
16. <span data-ttu-id="e5d87-140">Välj den kund från vilken du har tagit emot betalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-140">Select the customer from whom you received the payment.</span></span>
    * <span data-ttu-id="e5d87-141">Om du inte känner till kunden, men känner till en faktura som betalas med betalningen, använder du fältet Faktura för att ange eller välja fakturan manuellt.</span><span class="sxs-lookup"><span data-stu-id="e5d87-141">If you don't know the customer but know an invoice paid by the payment, use the Invoice field to manually enter or select the invoice.</span></span> <span data-ttu-id="e5d87-142">Kunden hämtas som standard efter att fakturan har valts.</span><span class="sxs-lookup"><span data-stu-id="e5d87-142">The customer will default after the invoice is selected.</span></span>  
17. <span data-ttu-id="e5d87-143">Klicka på Kvitta transaktioner för att markera fakturor som har betalats.</span><span class="sxs-lookup"><span data-stu-id="e5d87-143">Click Settle transctions to mark invoices that were paid.</span></span>
    * <span data-ttu-id="e5d87-144">Du måste inte att kvitta betalningen mot några fakturor.</span><span class="sxs-lookup"><span data-stu-id="e5d87-144">You are not required to settle the payment to any invoices.</span></span> <span data-ttu-id="e5d87-145">Om det är en förskottsbetalning eller om du inte vet vilken faktura som har betalats kan du ange och bokföra betalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-145">If this is a prepayment or if you don't know what invoice was paid, you can enter and post the payment.</span></span> <span data-ttu-id="e5d87-146">Betalningen kan kvittas mot en faktura vid en senare tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="e5d87-146">The payment can be settled to an invoice at a later point.</span></span>  
18. <span data-ttu-id="e5d87-147">Markera fakturorna som har betalats med betalningen.</span><span class="sxs-lookup"><span data-stu-id="e5d87-147">Mark the invoices paid by the payment.</span></span> 
19. <span data-ttu-id="e5d87-148">Ange beloppet för den betalning som ska kvittas mot fakturan.</span><span class="sxs-lookup"><span data-stu-id="e5d87-148">Enter the amount of the payment that will be settled to the invoice.</span></span>
20. <span data-ttu-id="e5d87-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e5d87-149">Click OK.</span></span>
21. <span data-ttu-id="e5d87-150">Ange en betalningsreferens i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="e5d87-150">In the Payment reference field, Enter a payment reference.</span></span> <span data-ttu-id="e5d87-151">.</span><span class="sxs-lookup"><span data-stu-id="e5d87-151">.</span></span>
    * <span data-ttu-id="e5d87-152">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="e5d87-152">The payment reference is only required if you mark to include the payment on a deposit slip.</span></span>  
22. <span data-ttu-id="e5d87-153">Bokför kundbetalningarna.</span><span class="sxs-lookup"><span data-stu-id="e5d87-153">Post the customer payments.</span></span> 

