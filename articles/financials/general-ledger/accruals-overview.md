---
title: "Översikt över periodiseringar"
description: "Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 00ecc493e6dcf59ab61e7082297c95516a248b58
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="accruals-overview"></a><span data-ttu-id="cf475-103">Översikt över periodiseringar</span><span class="sxs-lookup"><span data-stu-id="cf475-103">Accruals overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cf475-104">Det här avsnittet innehåller en beskrivning av periodiseringar och information om hur du ställer in dem och skapar transaktioner.</span><span class="sxs-lookup"><span data-stu-id="cf475-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="cf475-105">Periodiseringar används i periodiserad redovisning för att följa intäkt som redovisas i den period då den har tjänats in, inte när betalningen mottas, och följa utgifter (kostnader) som redovisas när de uppträder, inte när betalning görs.</span><span class="sxs-lookup"><span data-stu-id="cf475-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="cf475-106">Periodiseringsscheman</span><span class="sxs-lookup"><span data-stu-id="cf475-106">Accrual schemes</span></span>
<span data-ttu-id="cf475-107">Periodiseringsscheman används för att ställa in den uppskjutna intäkter och kostnader, och samma periodiseringsschema kan användas för både intäkter och kostnader.</span><span class="sxs-lookup"><span data-stu-id="cf475-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="cf475-108">Periodiseringen av redovisningen omfördelar de kostnader eller intäkterna för en journalrad så att kostnaderna och intäkterna redovisas i rätt period.</span><span class="sxs-lookup"><span data-stu-id="cf475-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="cf475-109">På sidan **Periodiseringsschema** anger du debetkonton och kreditkonton som ska användas när schemat används.</span><span class="sxs-lookup"><span data-stu-id="cf475-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="cf475-110">**Debet** – Huvudkontot som du definierar ska ersätta debethuvudkontot på journalverifikationsraden.</span><span class="sxs-lookup"><span data-stu-id="cf475-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="cf475-111">Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="cf475-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="cf475-112">**Kredit** – Huvudkontot som du definierar ska ersätta kredithuvudkontot på journalverifikationsraden.</span><span class="sxs-lookup"><span data-stu-id="cf475-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="cf475-113">Detta konto används också för återföringen av uppskjutandet baserat på redovisningsperiodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="cf475-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="cf475-114">När du har definierat vilka konton som ska användas, kan du ange hur verifikationsnummer skapas när periodiseringstransaktioner skapas.</span><span class="sxs-lookup"><span data-stu-id="cf475-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="cf475-115">Du kan även ange hur ofta transaktionerna ska göras, hur många gånger transaktionerna skapas och när transaktionerna bokförs.</span><span class="sxs-lookup"><span data-stu-id="cf475-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="cf475-116">När det periodiseringsschemat har skapats, kan du använda det i någon av journalerna genom att använda redovisningsperiodiseringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cf475-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="cf475-117">Periodiseringar</span><span class="sxs-lookup"><span data-stu-id="cf475-117">Ledger accruals</span></span>
<span data-ttu-id="cf475-118">När du anger en journal, kan du klicka på **Periodiseringar** på menyn **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="cf475-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="cf475-119">Därefter, när du väljer periodiseringsschema, kan du se basbeloppet från journalen som ska fördelas på perioden, vilket bestäms av periodiseringsschemat.</span><span class="sxs-lookup"><span data-stu-id="cf475-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="cf475-120">Om du till exempel betalar en medarbetares försäkring för hela året i januari och beloppet är 12 000, måste du redovisa utgiften varje månad.</span><span class="sxs-lookup"><span data-stu-id="cf475-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="cf475-121">Du kan välja startdatum.</span><span class="sxs-lookup"><span data-stu-id="cf475-121">You can select the start date.</span></span> <span data-ttu-id="cf475-122">Du kan även ange om beloppet som periodiseras baseras på kontot eller motkontot.</span><span class="sxs-lookup"><span data-stu-id="cf475-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="cf475-123">När du har gjort dina val klickar du på **Transaktioner** att visa alla transaktioner som har skapats baserat på periodiseringsschemat.</span><span class="sxs-lookup"><span data-stu-id="cf475-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="cf475-124">Om du till exempel sprider ut de 12 000 i försäkringsutgifter över året, visas 1 000 för varje månad.</span><span class="sxs-lookup"><span data-stu-id="cf475-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="cf475-125">När du bokför journalen kan du visa transaktionerna via förfrågningssidan **Verifikationstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="cf475-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="cf475-126">Om ett periodiseringsschema inte kan användas (t.ex. när en försäljningsorderfaktura eller en inköpsorderfaktura är inblandad), kan du kreditera det förskottsbetalda beloppet och debitera utgiftsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="cf475-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="cf475-127">Du kan sedan välja **Motboka** när du använder periodiseringsschemat.</span><span class="sxs-lookup"><span data-stu-id="cf475-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="cf475-128">Mer information finns i [Skapa periodiseringsscheman](tasks/create-accrual-schemes.md) och [Skapa periodiseringstransaktioner](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="cf475-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>

