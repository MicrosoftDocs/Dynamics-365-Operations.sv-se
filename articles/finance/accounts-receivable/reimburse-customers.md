---
title: Återbetala kunder
description: Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae6a3078743fc9cd43c71bc1d4531c0553ee53bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012149"
---
# <a name="reimburse-customers"></a><span data-ttu-id="002ab-104">Återbetala kunder</span><span class="sxs-lookup"><span data-stu-id="002ab-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="002ab-105">Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="002ab-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="002ab-106">Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot.</span><span class="sxs-lookup"><span data-stu-id="002ab-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="002ab-107">Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar</span><span class="sxs-lookup"><span data-stu-id="002ab-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="002ab-108">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="002ab-108">Prerequisite</span></span>                                                            | <span data-ttu-id="002ab-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="002ab-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="002ab-110">Ange det minsta återbetalningsbeloppet för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="002ab-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="002ab-111">Ange minimibeloppet som går att återbetala för kundöverbetalningar på sidan **Parametrar för kundreskontra** i området **Allmänt** i fältet **Minimiåterbetalning**.</span><span class="sxs-lookup"><span data-stu-id="002ab-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="002ab-112">Du kan även: Lägg till ett leverantörskonto i varje kund som kan återbetalas.</span><span class="sxs-lookup"><span data-stu-id="002ab-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="002ab-113">Välj leverantörskontot för kunden på sidan **Kunder** på snabbfliken **Diverse detaljer** i fältet **Leverantörskonto**.</span><span class="sxs-lookup"><span data-stu-id="002ab-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="002ab-114">När du skapar återbetalningstransaktioner, skapas en leverantörsfaktura för beloppet i kreditsaldot.</span><span class="sxs-lookup"><span data-stu-id="002ab-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="002ab-115">Återbetalningsprocessen tar bort kreditsaldot för kundkontot och skapar ett förfallet saldo för det leverantörskonto som motsvarar kundens.</span><span class="sxs-lookup"><span data-stu-id="002ab-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="002ab-116">I Kundreskontra, kör processen **Återbetalning** (**Kundreskontra \> Periodiska uppgifter \> Återbetalning**).</span><span class="sxs-lookup"><span data-stu-id="002ab-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="002ab-117">Om du vill gruppera alla transaktioner, oavsett redovisningsdimensioner, anger du **Ja** för alternativet **Sammanfatta kund**.</span><span class="sxs-lookup"><span data-stu-id="002ab-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="002ab-118">Om du bara vill gruppera transaktioner som har liknande redovisningsdimensioner anger du alternativet till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="002ab-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="002ab-119">Välj **Inkludera kunder med utestående debettransaktioner** om du vill välja kunder som har oreglerade debiteringsbelopp.</span><span class="sxs-lookup"><span data-stu-id="002ab-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="002ab-120">Om du vill återbetala specifika kundkonton välj **Filter** på snabbfliken **Poster som ska ingå** och ange sedan kundkontona i frågan.</span><span class="sxs-lookup"><span data-stu-id="002ab-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="002ab-121">Kreditbeloppen överförs till kundernas leverantörskonton och bearbetas som normala betalningar.</span><span class="sxs-lookup"><span data-stu-id="002ab-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="002ab-122">Om en kund inte har ett leverantörskonto skapas ett engångsleverantörskonto automatiskt för den kunden.</span><span class="sxs-lookup"><span data-stu-id="002ab-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="002ab-123">Om du vill visa de återbetalningstransaktioner som har skapades använder du rapporten **Återbetalning** (**Kundreskontra \> Förfrågningar och rapporter \> Återbetalning (rapport)**).</span><span class="sxs-lookup"><span data-stu-id="002ab-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="002ab-124">Skapa en betalning för leverantörsfakturor som har skapats i återbetalningsprocessen i leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="002ab-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="002ab-125">Information om hur du betalar leverantörer finns i [Översikt över leverantörsbetalning](../accounts-payable/Vendor-payments-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="002ab-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>
