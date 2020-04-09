---
title: Skapa en avskrivningsjournal för en kund
description: Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd97f91f1ba53b56150b556fffdfed10a0c8911a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140247"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="d3493-103">Skapa en avskrivningsjournal för en kund</span><span class="sxs-lookup"><span data-stu-id="d3493-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3493-104">Den här uppgiftsguiden innehåller information om hur du ställer in parametrar för avskrivningar och sedan skriver av transaktioner från sidan Inkasso, sidan Öppna kundfakturor och sidan Kund.</span><span class="sxs-lookup"><span data-stu-id="d3493-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="d3493-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d3493-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="d3493-106">Konfigurera avskrivningsparametrar</span><span class="sxs-lookup"><span data-stu-id="d3493-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="d3493-107">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="d3493-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="d3493-108">Klicka på fliken **Inkasso.**</span><span class="sxs-lookup"><span data-stu-id="d3493-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="d3493-109">Expandera eller komprimera avsnittet **Avskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d3493-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="d3493-110">**Avskrivningsjournalen** är den allmänna journal som ska innehålla de avskrivningstransaktioner som du skapar.</span><span class="sxs-lookup"><span data-stu-id="d3493-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="d3493-111">Du kan koppla en orsakskod till varje avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3493-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="d3493-112">Du kan åsidosätta den här standarden vid avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="d3493-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="d3493-113">Ange **Separat moms** till Ja om du vill separera momsen från den ursprungliga transaktionen i avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="d3493-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="d3493-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-114">Close the page.</span></span>
5. <span data-ttu-id="d3493-115">Gå till **Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="d3493-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="d3493-116">Avskrivningskontot ska användas som utgiftskonto eller reserveringsjustering i den allmänna journalen.</span><span class="sxs-lookup"><span data-stu-id="d3493-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="d3493-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="d3493-118">Skriv av en kundbalans på sidan Åldersfördelade saldon.</span><span class="sxs-lookup"><span data-stu-id="d3493-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="d3493-119">Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**.</span><span class="sxs-lookup"><span data-stu-id="d3493-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="d3493-120">Markera raden för den kund som du vill skriva av.</span><span class="sxs-lookup"><span data-stu-id="d3493-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="d3493-121">Markera till exempel raden med företaget Birch.</span><span class="sxs-lookup"><span data-stu-id="d3493-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="d3493-122">I **åtgärdsfönstret**, klicka på **Inkasso**.</span><span class="sxs-lookup"><span data-stu-id="d3493-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="d3493-123">Klicka på **Skriv av**.</span><span class="sxs-lookup"><span data-stu-id="d3493-123">Click **Write off**.</span></span>
5. <span data-ttu-id="d3493-124">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3493-124">Click **OK**.</span></span>
6. <span data-ttu-id="d3493-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-125">Close the page.</span></span>
7. <span data-ttu-id="d3493-126">Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalposter > Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="d3493-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="d3493-127">Välj journalbatchnumret för den journal som innehåller din avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3493-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="d3493-128">En rad skapas för att återföra kundbalansen.</span><span class="sxs-lookup"><span data-stu-id="d3493-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="d3493-129">En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.</span><span class="sxs-lookup"><span data-stu-id="d3493-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="d3493-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-130">Close the page.</span></span>
10. <span data-ttu-id="d3493-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="d3493-132">Skriv av transaktioner från inkassoformuläret.</span><span class="sxs-lookup"><span data-stu-id="d3493-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="d3493-133">Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**.</span><span class="sxs-lookup"><span data-stu-id="d3493-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="d3493-134">Välj namnet på kunden som har de transaktioner som du vill skriva av.</span><span class="sxs-lookup"><span data-stu-id="d3493-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="d3493-135">Välj till exempel Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="d3493-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="d3493-136">Markera raden för den första transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d3493-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="d3493-137">Markera raden för den andra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d3493-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="d3493-138">Klicka på **Skriv av**.</span><span class="sxs-lookup"><span data-stu-id="d3493-138">Click **Write off**.</span></span>
6. <span data-ttu-id="d3493-139">Skriv "Dåliga skulder" i fältet **Orsakskommentar**.</span><span class="sxs-lookup"><span data-stu-id="d3493-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="d3493-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3493-140">Click **OK**.</span></span>
8. <span data-ttu-id="d3493-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-141">Close the page.</span></span>
9. <span data-ttu-id="d3493-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-142">Close the page.</span></span>
10. <span data-ttu-id="d3493-143">Gå till **Redovisning > Journalposter > Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="d3493-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="d3493-144">Välj journalbatchnumret för den journal som innehåller din avskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3493-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="d3493-145">En rad skapas för att återföra kundbalansen.</span><span class="sxs-lookup"><span data-stu-id="d3493-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="d3493-146">En eller flera rader skapas för att bokföra avskrivningen till avskrivningskontot.</span><span class="sxs-lookup"><span data-stu-id="d3493-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="d3493-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-147">Close the page.</span></span>
13. <span data-ttu-id="d3493-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="d3493-149">Skriv av en faktura från sidan Öppna kundfakturor</span><span class="sxs-lookup"><span data-stu-id="d3493-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="d3493-150">Gå till **Navigeringsfönster > Moduler > Kundreskontra > Fakturor > Öppna kundfakturor**.</span><span class="sxs-lookup"><span data-stu-id="d3493-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="d3493-151">Markera raden för en faktura.</span><span class="sxs-lookup"><span data-stu-id="d3493-151">Mark the line for an invoice.</span></span> <span data-ttu-id="d3493-152">Markera till exempel raden för CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="d3493-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="d3493-153">Klicka på **Faktura** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="d3493-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="d3493-154">Klicka på **Skriv av**.</span><span class="sxs-lookup"><span data-stu-id="d3493-154">Click **Write off**.</span></span>
5. <span data-ttu-id="d3493-155">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3493-155">Click **OK**.</span></span>
6. <span data-ttu-id="d3493-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="d3493-157">Skriv av ett kundsaldo från sidan Kunder</span><span class="sxs-lookup"><span data-stu-id="d3493-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="d3493-158">Gå till **Leverantörsreskontra > Kunder > Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="d3493-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="d3493-159">Välj ett kundkonto.</span><span class="sxs-lookup"><span data-stu-id="d3493-159">Select a customer account.</span></span> <span data-ttu-id="d3493-160">Välj till exempel US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="d3493-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="d3493-161">I **åtgärdsfönstret**, klicka på **Inkasso**.</span><span class="sxs-lookup"><span data-stu-id="d3493-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="d3493-162">Klicka på **Skriv av**.</span><span class="sxs-lookup"><span data-stu-id="d3493-162">Click **Write off**.</span></span>
5. <span data-ttu-id="d3493-163">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3493-163">Click **OK**.</span></span>
6. <span data-ttu-id="d3493-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d3493-164">Close the page.</span></span>

