---
title: "Återbetala kunder"
description: "Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 01c9dcebe82544624c6dd0feb3672d1c5bdfe2d1
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="reimburse-customers"></a><span data-ttu-id="784a9-104">Återbetala kunder</span><span class="sxs-lookup"><span data-stu-id="784a9-104">Reimburse customers</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="784a9-105">Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="784a9-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="784a9-106">Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot.</span><span class="sxs-lookup"><span data-stu-id="784a9-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="784a9-107">Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar</span><span class="sxs-lookup"><span data-stu-id="784a9-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="784a9-108">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="784a9-108">Prerequisite</span></span>                                                            | <span data-ttu-id="784a9-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="784a9-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="784a9-110">Ange det minsta återbetalningsbeloppet för den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="784a9-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="784a9-111">Ange minimibeloppet som går att återbetala för kundöverbetalningar på sidan **Parametrar för kundreskontra** i området **Allmänt** i fältet **Minimiåterbetalning**.</span><span class="sxs-lookup"><span data-stu-id="784a9-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="784a9-112">Du kan även: Lägg till ett leverantörskonto i varje kund som kan återbetalas.</span><span class="sxs-lookup"><span data-stu-id="784a9-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="784a9-113">Välj leverantörskontot för kunden på sidan **Kunder** på snabbfliken **Diverse detaljer** i fältet **Leverantörskonto**.</span><span class="sxs-lookup"><span data-stu-id="784a9-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="784a9-114">När du skapar återbetalningstransaktioner, skapas en leverantörsfaktura för beloppet i kreditsaldot.</span><span class="sxs-lookup"><span data-stu-id="784a9-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="784a9-115">Återbetalningsprocessen tar bort kreditsaldot för kundkontot och skapar ett förfallet saldo för det leverantörskonto som motsvarar kundens.</span><span class="sxs-lookup"><span data-stu-id="784a9-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="784a9-116">Kör processen **Återbetalning** i kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="784a9-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="784a9-117">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="784a9-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="784a9-118">Om du vill återbetala vissa kundkonton klickar du på **Välj** och anger kundkontona i frågan.</span><span class="sxs-lookup"><span data-stu-id="784a9-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="784a9-119">Om du vill återbetala alla kundkonton klickar du på **OK**.</span><span class="sxs-lookup"><span data-stu-id="784a9-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="784a9-120">Kreditbeloppen överförs till kundernas leverantörskonton och bearbetas som normala betalningar.</span><span class="sxs-lookup"><span data-stu-id="784a9-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="784a9-121">Om en kund inte har ett leverantörskonto skapas ett engångsleverantörskonto automatiskt för den kunden.</span><span class="sxs-lookup"><span data-stu-id="784a9-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="784a9-122">Om du vill visa de återbetalningstransaktioner som skapades använder du sidan **Återbetalning**.</span><span class="sxs-lookup"><span data-stu-id="784a9-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="784a9-123">Skapa en betalning för leverantörsfakturor som har skapats i återbetalningsprocessen i leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="784a9-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>





