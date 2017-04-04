---
title: "Importera betalningsformat för Sverige"
description: "Det här avsnittet innehåller information om BankGirot MAX, importera BankGirot OCR och BankGirot returnerade format för Sverige."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPaymMode, CustVendPaymReconciliation, LedgerJournalTransCustPaym, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262684
ms.assetid: 7632f01a-28b6-408f-8734-b03416c6fb81
ms.search.region: Sweden
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: 89747e2637920a9d333be2b3dd0d589d27b29569
ms.lasthandoff: 03/31/2017


---

# <a name="import-payment-formats-for-sweden"></a>Importera betalningsformat för Sverige

Det här avsnittet innehåller information om BankGirot MAX, importera BankGirot OCR och BankGirot returnerade format för Sverige.

<a name="bankgirot-max-bankgirot-ocr"></a>BankGirot MAX, BankGirot OCR
----------------------------

Importera BankGirot MAX och BankGirot OCR kan du importera kundbetalningar BankGirot filformat. BG MAX är layouten fil som samlar alla betalningar i en fil. OCR är en viss typ av referens i BG MAX-format med en betalningsreferens. Gör följande om du vill importera betalningar.

1.  Gå till den **betalningsjournal** sida.
2.  Klicka på **Rader**.
3.  Klicka på **funktion**&gt;**Importbetalningar**.
4.  I dialogrutan Välj betalningsmetoden och bläddra sedan till platsen för filen som ska importeras. 
  > [!NOTE]
  >  Innan du kan slutföra proceduren måste du har redan importerat konfigurationer från Lifecycle Services (LCS) och ställa in betalningsmetoderna. Mer information finns i [filformat för betalningsmetod betalningar](emea-select-file-formats-for-the-method-of-payments.md).

När du har importerat betalningsfilen journalrader för den valda journalen och markeras för kvittning med kundfakturor.

## <a name="bankgirot-autogiro-returns"></a>Returnerar bankgirot Autogiro
Bankgirot Autogiro returnerar format för direktdebitering betalningsformatet med samma namn. Du kan importera meddelandena som svar på direkt debet meddelanden som tidigare har exporterats. För närvarande kan dessa betalningar representeras i operationer betalningsjournalraderna med en **skickad** status. Gör följande om du vill importera en fil.

1.  Gå till den **betalningsöverföringar** sida.
2.  Klicka på **returnerar filen kunden**.
3.  I dialogrutan Välj motsvarande betalningsmetod och bläddra sedan till platsen för filen som ska importeras. 
  > [!NOTE]
  >  Innan du kan slutföra proceduren måste du har redan importerat konfigurationer från Lifecycle Services (LCS) och ställa in betalningsmetoderna. Mer information finns i [filformat för betalningsmetod betalningar](emea-select-file-formats-for-the-method-of-payments.md).

När du har importerat returfilen betalningarna ska uppdateras till statusen **godkänd**.


