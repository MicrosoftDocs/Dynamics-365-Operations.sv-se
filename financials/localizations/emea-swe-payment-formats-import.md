---
title: "Importformat för betalning för Sverige"
description: "Det här avsnittet innehåller information om BankGirot MAX, importera via BankGirot OCR och BankGirot-returformat för Sverige."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, CustVendPaymReconciliation, LedgerJournalTransCustPaym, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 262684
ms.search.region: Sweden
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: aaf6aab4deb4cd676ecb56d89fbc8f4ef610ae8d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="import-payment-formats-for-sweden"></a>Importformat för betalning för Sverige

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om BankGirot MAX, importera via BankGirot OCR och BankGirot-returformat för Sverige.

<a name="bankgirot-max-bankgirot-ocr"></a>BankGirot MAX, BankGirot OCR
----------------------------

Filimporter via BankGirot MAX och BankGirot OCR låter dig importera kundbetalningar BankGirot-filformat. BG MAX är fillayout som samlar alla betalningar i en fil. OCR är en specifik referenstyp i filformatet BG MAX med en betalningsreferens. Utför följande steg för att importera betalningar:

1.  Gå till sidan **Betalningsjournal**.
2.  Klicka på **Rader**.
3.  Klicka på **Funktioner** &gt; **Importera betalningar**.
4.  I dialogrutan väljer du betalningsmetoden och bläddrar sedan till platsen för filen som ska importeras. 
  > [!NOTE]
  >  Innan du kan slutföra detta steg måste du redan ha importerat konfigurationerna från Lifecycle Services (LCS) och ställt in betalningsmetoderna. Mer information finns i [Filformat för betalningsmetod](emea-select-file-formats-for-the-method-of-payments.md).

När du har importerat betalningsfilen bör journalrader skapas för den valda journalen, och markeras för kvittning mot kundfakturor.

## <a name="bankgirot-autogiro-returns"></a>Bankgirot Autogiro-returer
Bankgirot Autogiro returnerar format för autogiro-betalningsformatet med samma namn. Du kan importera dessa meddelanden som ett svar på autogiromeddelanden som tidigare har exporterats. För närvarande representeras dessa betalningar i Operations som betalningsjournalrader med statusen **Skickad**. Utför följande steg för att importera en fil:

1.  Gå till sidan **Betalningsöverföringar**.
2.  Klicka på **Returfil-kund**.
3.  I dialogrutan väljer du relaterad betalningsmetod och bläddrar sedan till platsen för filen som ska importeras. 
  > [!NOTE]
  >  Innan du kan slutföra detta steg måste du redan ha importerat konfigurationerna från Lifecycle Services (LCS) och ställt in betalningsmetoderna. Mer information finns i [Filformat för betalningsmetod](emea-select-file-formats-for-the-method-of-payments.md).

När du har importerat returfilen bör betalningarna uppdateras till statusen **Godkänd**.




