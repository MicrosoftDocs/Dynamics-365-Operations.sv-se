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
ms.search.scope: Core, Operations
ms.custom: 262684
ms.search.region: Sweden
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 90239c3c4dffbc7007c04bf5db9aa7d78abd3447
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="import-payment-formats-for-sweden"></a><span data-ttu-id="3cb48-103">Importformat för betalning för Sverige</span><span class="sxs-lookup"><span data-stu-id="3cb48-103">Import payment formats for Sweden</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3cb48-104">Det här avsnittet innehåller information om BankGirot MAX, importera via BankGirot OCR och BankGirot-returformat för Sverige.</span><span class="sxs-lookup"><span data-stu-id="3cb48-104">This topic provides information about the BankGirot MAX, BankGirot OCR import, and BankGirot return formats for Sweden.</span></span>

<a name="bankgirot-max-bankgirot-ocr"></a><span data-ttu-id="3cb48-105">BankGirot MAX, BankGirot OCR</span><span class="sxs-lookup"><span data-stu-id="3cb48-105">BankGirot MAX, BankGirot OCR</span></span>
----------------------------

<span data-ttu-id="3cb48-106">Filimporter via BankGirot MAX och BankGirot OCR låter dig importera kundbetalningar BankGirot-filformat.</span><span class="sxs-lookup"><span data-stu-id="3cb48-106">BankGirot MAX and BankGirot OCR file import lets you import customer payments in BankGirot file formats.</span></span> <span data-ttu-id="3cb48-107">BG MAX är fillayout som samlar alla betalningar i en fil.</span><span class="sxs-lookup"><span data-stu-id="3cb48-107">BG MAX is a file layout that collects all payments in one file.</span></span> <span data-ttu-id="3cb48-108">OCR är en specifik referenstyp i filformatet BG MAX med en betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="3cb48-108">OCR is a specific kind of reference in the BG MAX file format with a payment reference.</span></span> <span data-ttu-id="3cb48-109">Utför följande steg för att importera betalningar:</span><span class="sxs-lookup"><span data-stu-id="3cb48-109">To import payments, complete the following steps.</span></span>

1.  <span data-ttu-id="3cb48-110">Gå till sidan **Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-110">Go to the **Payment journal** page.</span></span>
2.  <span data-ttu-id="3cb48-111">Klicka på **Rader**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-111">Click **Lines**.</span></span>
3.  <span data-ttu-id="3cb48-112">Klicka på **Funktioner** &gt; **Importera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-112">Click **Functions** &gt; **Import payments**.</span></span>
4.  <span data-ttu-id="3cb48-113">I dialogrutan väljer du betalningsmetoden och bläddrar sedan till platsen för filen som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="3cb48-113">In the dialog box, select the method of payment, and then browse to the location of the file to import.</span></span>

  > [!NOTE]
  >  <span data-ttu-id="3cb48-114">Innan du kan slutföra detta steg måste du redan ha importerat konfigurationerna från Lifecycle Services (LCS) och ställt in betalningsmetoderna.</span><span class="sxs-lookup"><span data-stu-id="3cb48-114">Before you can complete this step, you must have already imported the configurations from Lifecycle Services (LCS) and set up the methods of payment.</span></span> <span data-ttu-id="3cb48-115">Mer information finns i [Filformat för betalningsmetod](emea-select-file-formats-for-the-method-of-payments.md).</span><span class="sxs-lookup"><span data-stu-id="3cb48-115">For more information, see [File formats for method of payments](emea-select-file-formats-for-the-method-of-payments.md).</span></span>

<span data-ttu-id="3cb48-116">När du har importerat betalningsfilen bör journalrader skapas för den valda journalen, och markeras för kvittning mot kundfakturor.</span><span class="sxs-lookup"><span data-stu-id="3cb48-116">After you import the payment file, payment journal lines should be created for the selected journal and marked for settlement with customer invoices.</span></span>

## <a name="bankgirot-autogiro-returns"></a><span data-ttu-id="3cb48-117">Bankgirot Autogiro-returer</span><span class="sxs-lookup"><span data-stu-id="3cb48-117">Bankgirot Autogiro returns</span></span>
<span data-ttu-id="3cb48-118">Bankgirot Autogiro returnerar format för autogiro-betalningsformatet med samma namn.</span><span class="sxs-lookup"><span data-stu-id="3cb48-118">Bankgirot Autogiro returns format for the direct debit payment format of the same name.</span></span> <span data-ttu-id="3cb48-119">Du kan importera dessa meddelanden som ett svar på autogiromeddelanden som tidigare har exporterats.</span><span class="sxs-lookup"><span data-stu-id="3cb48-119">These messages can be imported as a response to direct debit messages that were previously exported.</span></span> <span data-ttu-id="3cb48-120">För närvarande representeras dessa betalningar i Operations som betalningsjournalrader med statusen **Skickad**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-120">Currently, these payments are represented in Operations as payment journal lines with a **Sent** status.</span></span> <span data-ttu-id="3cb48-121">Utför följande steg för att importera en fil:</span><span class="sxs-lookup"><span data-stu-id="3cb48-121">To import a file, complete the following steps.</span></span>

1.  <span data-ttu-id="3cb48-122">Gå till sidan **Betalningsöverföringar**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-122">Go to the **Payment transfers** page.</span></span>
2.  <span data-ttu-id="3cb48-123">Klicka på **Returfil-kund**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-123">Click **Return file-customer**.</span></span>
3.  <span data-ttu-id="3cb48-124">I dialogrutan väljer du relaterad betalningsmetod och bläddrar sedan till platsen för filen som ska importeras.</span><span class="sxs-lookup"><span data-stu-id="3cb48-124">In the dialog box, select corresponding method of payment, and then browse to the location of the file to import.</span></span> 

  > [!NOTE]
  >  <span data-ttu-id="3cb48-125">Innan du kan slutföra detta steg måste du redan ha importerat konfigurationerna från Lifecycle Services (LCS) och ställt in betalningsmetoderna.</span><span class="sxs-lookup"><span data-stu-id="3cb48-125">Before you can complete this step, you must have already imported the configurations from Lifecycle Services (LCS) and set up the methods of payment.</span></span> <span data-ttu-id="3cb48-126">Mer information finns i [Filformat för betalningsmetod](emea-select-file-formats-for-the-method-of-payments.md).</span><span class="sxs-lookup"><span data-stu-id="3cb48-126">For more information, see [File formats for method of payments](emea-select-file-formats-for-the-method-of-payments.md).</span></span>

<span data-ttu-id="3cb48-127">När du har importerat returfilen bör betalningarna uppdateras till statusen **Godkänd**.</span><span class="sxs-lookup"><span data-stu-id="3cb48-127">After you import the return file, the payments should be updated to the status **Approved**.</span></span>




