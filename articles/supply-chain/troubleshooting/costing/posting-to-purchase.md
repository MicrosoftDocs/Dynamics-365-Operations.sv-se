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
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>Inköpsperiodisering som har ett nollbelopp bokförs för en nollvärdesproduktinleverans

KB-nummer: 4612588

## <a name="symptoms"></a>Symtom

När en produktinleverans som har nollvärde bokförs skapas en bokföring i inköpsperiodisering där beloppet är 0 (noll).

## <a name="resolution"></a>Upplösning

För redovisningsbokföring av typen *Inköp, periodisering* är fältet `IsTransferredIndetail` som standard alltid inställt på *Sammanfattning* i redovisningstransaktioner. Därför skapar systemet en relaterad verifikationspost även om beloppet är 0 (noll).

Om du vill hoppa över den här bokföringstypen när beloppet är 0 (noll) utökar du metoden `subledgerJournalizer.markDoNotTransferEntries` så att den inkluderar `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, som visas i exemplet nedan.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
