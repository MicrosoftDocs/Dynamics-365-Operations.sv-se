---
title: "Bankutdrag och betalningsavstämning för EU"
description: "Det här avsnittet innehåller en översikt över funktioner med vilka du kan stämma av betalningsinformation från banker i format som används av europeiska länder."
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fcae9bf8068913f8cda61e3fd3063f0a6122ae4d
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a><span data-ttu-id="6667a-103">Bankutdrag och betalningsavstämning för EU</span><span class="sxs-lookup"><span data-stu-id="6667a-103">Bank statement and payment reconciliation for the EU</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="6667a-104">Det här avsnittet innehåller en översikt över funktioner med vilka du kan stämma av betalningsinformation från banker i format som används av europeiska länder.</span><span class="sxs-lookup"><span data-stu-id="6667a-104">This topic provides an overview of the functionality that you can use to reconcile payment information from banks in formats that are used by European countries.</span></span>

<span data-ttu-id="6667a-105">Du kan importera transaktioner från banker och kvitta dessa transaktioner mot befintliga transaktioner i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6667a-105">In Microsoft Dynamics 365 for Finance and Operations, you can import transactions from banks and settle these transactions against existing transactions.</span></span> <span data-ttu-id="6667a-106">I Europa kan du göra detta i följande fall:</span><span class="sxs-lookup"><span data-stu-id="6667a-106">In Europe, you can do this for the following scenarios:</span></span>

-   <span data-ttu-id="6667a-107">Importera bankutdrag</span><span class="sxs-lookup"><span data-stu-id="6667a-107">Importing bank statements</span></span>
-   <span data-ttu-id="6667a-108">Importera betalningar</span><span class="sxs-lookup"><span data-stu-id="6667a-108">Importing payments</span></span>
-   <span data-ttu-id="6667a-109">Importera returfiler</span><span class="sxs-lookup"><span data-stu-id="6667a-109">Importing return files</span></span>

## <a name="bank-statements"></a><span data-ttu-id="6667a-110">Bankutdrag</span><span class="sxs-lookup"><span data-stu-id="6667a-110">Bank statements</span></span>
<span data-ttu-id="6667a-111">Ett *bankutdrag* eller *kontoutdrag* är en sammanfattning av finansiella transaktioner som har inträffat under en viss period på ett bankkonto som innehas av ett företag med ett finansinstitut.</span><span class="sxs-lookup"><span data-stu-id="6667a-111">A *bank statement* or *account statement* is a summary of financial transactions that have occurred over a given period on a bank account held by a company with a financial institution.</span></span> <span data-ttu-id="6667a-112">Du kan importera ett bankutdrag i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6667a-112">In Finance and Operations you can import a bank statement.</span></span> <span data-ttu-id="6667a-113">Det är viktigt att kvitta importerade transaktioner mot befintliga transaktioner, samt att kontrollera inledande och avslutande saldon på bankkontona.</span><span class="sxs-lookup"><span data-stu-id="6667a-113">It is important to settle imported transactions with existing transactions as well as verify the opening and ending balance of the bank accounts.</span></span> <span data-ttu-id="6667a-114">Följande lista innehåller de europeiska format som stöds.</span><span class="sxs-lookup"><span data-stu-id="6667a-114">The following list includes the supported European formats.</span></span>

-   <span data-ttu-id="6667a-115">Avancerade europeiska format för bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="6667a-115">Advanced bank reconciliation European file formats.</span></span> <span data-ttu-id="6667a-116">Mer information finns i [Översikt för avancerad bankavstämning](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6667a-116">For more information, see [Advanced bank reconciliation overview](../cash-bank-management/advanced-bank-reconciliation-overview.md).</span></span>
-   <span data-ttu-id="6667a-117">Filformatet ISO 20022 camt.053 för bankutdragsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6667a-117">ISO 20022 camt.053 bank statement message file format.</span></span>
-   <span data-ttu-id="6667a-118">CODA-filformat för bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="6667a-118">CODA bank statement file format.</span></span> <span data-ttu-id="6667a-119">Mer information finns i [CODA-bankutdrag](emea-bel-coda-bank-statement-import.md).</span><span class="sxs-lookup"><span data-stu-id="6667a-119">For more information, see [CODA bank statement](emea-bel-coda-bank-statement-import.md).</span></span>

## <a name="customer-and-vendor-payments-import-and-return-messages"></a><span data-ttu-id="6667a-120">Import- och returmeddelanden för kund- och leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="6667a-120">Customer and vendor payments import and return messages</span></span>
<span data-ttu-id="6667a-121">Förutom ett bankutdrag kan banker även tillhandahålla specifika meddelanden som innehåller information om kund- och leverantörsbetalningar, och som kan importeras till Finance and Operations och synkroniseras med kund-och leverantörstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6667a-121">In addition to a bank statement, banks can provide specific messages, containing information about customer and vendor payments, which can be imported into Finance and Operations and reconciled with customer and vendor transactions.</span></span> <span data-ttu-id="6667a-122">När ett företag måste ta emot information om inkommande kundbetalningstransaktioner från banken, kan importformaten användas.</span><span class="sxs-lookup"><span data-stu-id="6667a-122">When a company needs to receive information about incoming customer payments transactions from the bank, the import formats can be used.</span></span> <span data-ttu-id="6667a-123">För företag som använder direktdebitering och kreditöverföring kan returmeddelanden tas emot för att uppdatera statusen för betalningar som tidigare har exporterats.</span><span class="sxs-lookup"><span data-stu-id="6667a-123">For companies that use direct debit and credit transfer, the return messages can be received to update the status of payments that were previously exported.</span></span> <span data-ttu-id="6667a-124">Skillnaden mellan importformat och returformat är att returer oftast riktas mot att uppdatera redan skapade journalrader (dessa kan skapas när överföringar via autogiro eller kredit startas) istället för att skapa nya rader.</span><span class="sxs-lookup"><span data-stu-id="6667a-124">The difference between import formats and return formats is that returns are targeted mostly to update already created payment journal lines (they can be created when direct debit or credit transfer were initiated) instead of creating new lines.</span></span> <span data-ttu-id="6667a-125">Vissa komplexa importformat kan även innehålla returer.</span><span class="sxs-lookup"><span data-stu-id="6667a-125">Some complex import formats can also include return scenarios.</span></span> <span data-ttu-id="6667a-126">I följande exempel visas hur denna fördelning bör genomföras.</span><span class="sxs-lookup"><span data-stu-id="6667a-126">The following example shows how this division should be implemented.</span></span>

### <a name="import-formats"></a><span data-ttu-id="6667a-127">Importformat</span><span class="sxs-lookup"><span data-stu-id="6667a-127">Import formats</span></span>

-   <span data-ttu-id="6667a-128">ISO 20022 [camt.054](emea-ISO20022-file-formats.md)-bankmeddelande</span><span class="sxs-lookup"><span data-stu-id="6667a-128">ISO 20022 [camt.054](emea-ISO20022-file-formats.md) bank notification message</span></span>
-   <span data-ttu-id="6667a-129">[Nettoimportformat](emea-nor-nets-import-format.md) - Komplexa funktioner för norska betalningsformat</span><span class="sxs-lookup"><span data-stu-id="6667a-129">[Nets import format](emea-nor-nets-import-format.md) - Complex feature for Norwegian payment formats</span></span>
-   <span data-ttu-id="6667a-130">Import av [ESR-kundbetalningar](emea-che-esr-customer-payments-import.md)</span><span class="sxs-lookup"><span data-stu-id="6667a-130">[ESR](emea-che-esr-customer-payments-import.md) customer payments import</span></span>
-   <span data-ttu-id="6667a-131">Importera betalningsformat för Sverige - BankGirot Max och BankGirot OCR-format</span><span class="sxs-lookup"><span data-stu-id="6667a-131">Import payment formats for Sweden - BankGirot Max and BankGirot OCR formats</span></span>

### <a name="return-formats"></a><span data-ttu-id="6667a-132">Returformat</span><span class="sxs-lookup"><span data-stu-id="6667a-132">Return formats</span></span>

-   <span data-ttu-id="6667a-133">ISO 20022 [pain.002](emea-ISO20022-file-formats.md)-rapport för betalningsstatus</span><span class="sxs-lookup"><span data-stu-id="6667a-133">ISO 20022 [pain.002](emea-ISO20022-file-formats.md) payment status report</span></span>
-   <span data-ttu-id="6667a-134">(DNK) BetalingsserviceBasis-returformat – Returformat för kundexportformatet Betalingsservice</span><span class="sxs-lookup"><span data-stu-id="6667a-134">(DNK) BetalingsserviceBasis-returformat – Return format for customer Betalingsservice export format</span></span>
-   <span data-ttu-id="6667a-135">[Importera betalningsformat för Sverige](emea-swe-payment-formats-import.md) - Bankgirot Autogiro returnerar</span><span class="sxs-lookup"><span data-stu-id="6667a-135">[Import payment formats for Sweden](emea-swe-payment-formats-import.md) - Bankgirot Autogiro returns</span></span>
-   <span data-ttu-id="6667a-136">(SVERIGE) BankGirot retur – Returformat för leverantörsbetalningar som motsvarar exportformatet Bankgirot</span><span class="sxs-lookup"><span data-stu-id="6667a-136">(SWE) BankGirot return – Vendor payments return format, which corresponds to Bankgirot export format</span></span>



