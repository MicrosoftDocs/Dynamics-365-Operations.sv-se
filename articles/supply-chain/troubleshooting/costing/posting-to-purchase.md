---
title: Inköpsperiodisering som har ett nollbelopp bokförs för en nollvärdesproduktinleverans
description: När en produktinleverans som har nollvärde bokförs skapas en bokföring i inköpsperiodisering där beloppet är 0 (noll).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026931"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="884c0-103">Inköpsperiodisering som har ett nollbelopp bokförs för en nollvärdesproduktinleverans</span><span class="sxs-lookup"><span data-stu-id="884c0-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="884c0-104">KB-nummer: 4612588</span><span class="sxs-lookup"><span data-stu-id="884c0-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="884c0-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="884c0-105">Symptoms</span></span>

<span data-ttu-id="884c0-106">När en produktinleverans som har nollvärde bokförs skapas en bokföring i inköpsperiodisering där beloppet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="884c0-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="884c0-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="884c0-107">Resolution</span></span>

<span data-ttu-id="884c0-108">För redovisningsbokföring av typen *Inköp, periodisering* är fältet `IsTransferredIndetail` som standard alltid inställt på *Sammanfattning* i redovisningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="884c0-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="884c0-109">Därför skapar systemet en relaterad verifikationspost även om beloppet är 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="884c0-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="884c0-110">Om du vill hoppa över den här bokföringstypen när beloppet är 0 (noll) utökar du metoden `subledgerJournalizer.markDoNotTransferEntries` så att den inkluderar `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, som visas i exemplet nedan.</span><span class="sxs-lookup"><span data-stu-id="884c0-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
