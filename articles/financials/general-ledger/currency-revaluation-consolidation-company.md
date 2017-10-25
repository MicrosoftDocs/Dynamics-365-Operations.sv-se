---
title: "Valutaomvärdering i ett konsolideringsföretag"
description: "Detta avsnitt beskriver hur du omvärderar valuta i ett konsolideringsföretag."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c91399e96c54f7cf9968a15e3fff90c3a71ca6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="96ca6-103">Valutaomvärdering i ett konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="96ca6-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="96ca6-104">När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas.</span><span class="sxs-lookup"><span data-stu-id="96ca6-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="96ca6-105">När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="96ca6-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="96ca6-106">Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon.</span><span class="sxs-lookup"><span data-stu-id="96ca6-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="96ca6-107">Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.</span><span class="sxs-lookup"><span data-stu-id="96ca6-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="96ca6-108">Följande exempel illustrerar bokföringsposter som skapas under processen.</span><span class="sxs-lookup"><span data-stu-id="96ca6-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="96ca6-109">Företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="96ca6-109">Company setup</span></span>
-   <span data-ttu-id="96ca6-110">**Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="96ca6-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="96ca6-111">**Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="96ca6-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="96ca6-112">**Realiserad vinst ** – Redovisningskonto 801500</span><span class="sxs-lookup"><span data-stu-id="96ca6-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="96ca6-113">**Förlusten** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="96ca6-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="96ca6-114">**Orealiserad vinst** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="96ca6-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="96ca6-115">**Orealiserad förlust** – reskontra 801400</span><span class="sxs-lookup"><span data-stu-id="96ca6-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="96ca6-116">Ursprungliga transaktioner</span><span class="sxs-lookup"><span data-stu-id="96ca6-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="96ca6-117">Kontantkvitto transaktioner i USMF</span><span class="sxs-lookup"><span data-stu-id="96ca6-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="96ca6-118">Datum</span><span class="sxs-lookup"><span data-stu-id="96ca6-118">Date</span></span>       | <span data-ttu-id="96ca6-119">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="96ca6-119">Ledger account</span></span>               | <span data-ttu-id="96ca6-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-120">Currency</span></span> | <span data-ttu-id="96ca6-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="96ca6-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="96ca6-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-122">10/11/2015</span></span> | <span data-ttu-id="96ca6-123">110110 – Kassa</span><span class="sxs-lookup"><span data-stu-id="96ca6-123">110110 – Cash</span></span>                | <span data-ttu-id="96ca6-124">USD</span><span class="sxs-lookup"><span data-stu-id="96ca6-124">USD</span></span>      | <span data-ttu-id="96ca6-125">500</span><span class="sxs-lookup"><span data-stu-id="96ca6-125">500</span></span>    |
| <span data-ttu-id="96ca6-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-126">10/11/2015</span></span> | <span data-ttu-id="96ca6-127">130100 – Kundfordringar</span><span class="sxs-lookup"><span data-stu-id="96ca6-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="96ca6-128">USD</span><span class="sxs-lookup"><span data-stu-id="96ca6-128">USD</span></span>      | <span data-ttu-id="96ca6-129">-500</span><span class="sxs-lookup"><span data-stu-id="96ca6-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="96ca6-130">Valutakurser</span><span class="sxs-lookup"><span data-stu-id="96ca6-130">Exchange rates</span></span>
| <span data-ttu-id="96ca6-131">Från valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-131">From currency</span></span> | <span data-ttu-id="96ca6-132">Till valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-132">To currency</span></span> | <span data-ttu-id="96ca6-133">Startdatum</span><span class="sxs-lookup"><span data-stu-id="96ca6-133">Start date</span></span> | <span data-ttu-id="96ca6-134">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="96ca6-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="96ca6-135">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-135">EUR</span></span>           | <span data-ttu-id="96ca6-136">USD</span><span class="sxs-lookup"><span data-stu-id="96ca6-136">USD</span></span>         | <span data-ttu-id="96ca6-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-137">10/1/2015</span></span>  | <span data-ttu-id="96ca6-138">200</span><span class="sxs-lookup"><span data-stu-id="96ca6-138">200</span></span>           |
| <span data-ttu-id="96ca6-139">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-139">EUR</span></span>           | <span data-ttu-id="96ca6-140">USD</span><span class="sxs-lookup"><span data-stu-id="96ca6-140">USD</span></span>         | <span data-ttu-id="96ca6-141">11-01 2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-141">11/1/2015</span></span>  | <span data-ttu-id="96ca6-142">150</span><span class="sxs-lookup"><span data-stu-id="96ca6-142">150</span></span>           |
| <span data-ttu-id="96ca6-143">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-143">EUR</span></span>           | <span data-ttu-id="96ca6-144">USD</span><span class="sxs-lookup"><span data-stu-id="96ca6-144">USD</span></span>         | <span data-ttu-id="96ca6-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="96ca6-145">12/1/2012</span></span>  | <span data-ttu-id="96ca6-146">100</span><span class="sxs-lookup"><span data-stu-id="96ca6-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="96ca6-147">Utföra konsolideringen för oktober 2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="96ca6-148">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="96ca6-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="96ca6-149">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="96ca6-149">Ledger account</span></span> | <span data-ttu-id="96ca6-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-150">Currency</span></span> | <span data-ttu-id="96ca6-151">Belopp</span><span class="sxs-lookup"><span data-stu-id="96ca6-151">Amount</span></span> | <span data-ttu-id="96ca6-152">Beräkning</span><span class="sxs-lookup"><span data-stu-id="96ca6-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="96ca6-153">110110</span><span class="sxs-lookup"><span data-stu-id="96ca6-153">110110</span></span>         | <span data-ttu-id="96ca6-154">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-154">EUR</span></span>      | <span data-ttu-id="96ca6-155">250</span><span class="sxs-lookup"><span data-stu-id="96ca6-155">250</span></span>    | <span data-ttu-id="96ca6-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="96ca6-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="96ca6-157">130100</span><span class="sxs-lookup"><span data-stu-id="96ca6-157">130100</span></span>         | <span data-ttu-id="96ca6-158">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-158">EUR</span></span>      | <span data-ttu-id="96ca6-159">-250</span><span class="sxs-lookup"><span data-stu-id="96ca6-159">-250</span></span>   | <span data-ttu-id="96ca6-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="96ca6-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="96ca6-161">Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="96ca6-162">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="96ca6-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="96ca6-163">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="96ca6-163">Ledger account</span></span> | <span data-ttu-id="96ca6-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-164">Currency</span></span> | <span data-ttu-id="96ca6-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="96ca6-165">Amount</span></span>  | <span data-ttu-id="96ca6-166">Beräkning</span><span class="sxs-lookup"><span data-stu-id="96ca6-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="96ca6-167">110110</span><span class="sxs-lookup"><span data-stu-id="96ca6-167">110110</span></span>         | <span data-ttu-id="96ca6-168">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-168">EUR</span></span>      | <span data-ttu-id="96ca6-169">333,33</span><span class="sxs-lookup"><span data-stu-id="96ca6-169">333.33</span></span>  | <span data-ttu-id="96ca6-170">Ursprungligt belopp av 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="96ca6-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="96ca6-171">130100</span><span class="sxs-lookup"><span data-stu-id="96ca6-171">130100</span></span>         | <span data-ttu-id="96ca6-172">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-172">EUR</span></span>      | <span data-ttu-id="96ca6-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="96ca6-173">-333.33</span></span> | <span data-ttu-id="96ca6-174">Ursprungligt belopp -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="96ca6-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="96ca6-175">801400</span><span class="sxs-lookup"><span data-stu-id="96ca6-175">801400</span></span>         | <span data-ttu-id="96ca6-176">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-176">EUR</span></span>      | <span data-ttu-id="96ca6-177">83,33</span><span class="sxs-lookup"><span data-stu-id="96ca6-177">83.33</span></span>   | <span data-ttu-id="96ca6-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="96ca6-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="96ca6-179">801600</span><span class="sxs-lookup"><span data-stu-id="96ca6-179">801600</span></span>         | <span data-ttu-id="96ca6-180">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-180">EUR</span></span>      | <span data-ttu-id="96ca6-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="96ca6-181">-83.33</span></span>  | <span data-ttu-id="96ca6-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="96ca6-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="96ca6-183">Du kommer att se ytterligare transaktioner för rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="96ca6-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="96ca6-184">Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015</span><span class="sxs-lookup"><span data-stu-id="96ca6-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="96ca6-185">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="96ca6-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="96ca6-186">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="96ca6-186">Ledger account</span></span> | <span data-ttu-id="96ca6-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="96ca6-187">Currency</span></span> | <span data-ttu-id="96ca6-188">Belopp</span><span class="sxs-lookup"><span data-stu-id="96ca6-188">Amount</span></span>  | <span data-ttu-id="96ca6-189">Beräkning</span><span class="sxs-lookup"><span data-stu-id="96ca6-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="96ca6-190">110110</span><span class="sxs-lookup"><span data-stu-id="96ca6-190">110110</span></span>         | <span data-ttu-id="96ca6-191">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-191">EUR</span></span>      | <span data-ttu-id="96ca6-192">500.00</span><span class="sxs-lookup"><span data-stu-id="96ca6-192">500.00</span></span>  | <span data-ttu-id="96ca6-193">Ursprungligt belopp av 500 × 1</span><span class="sxs-lookup"><span data-stu-id="96ca6-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="96ca6-194">130100</span><span class="sxs-lookup"><span data-stu-id="96ca6-194">130100</span></span>         | <span data-ttu-id="96ca6-195">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-195">EUR</span></span>      | <span data-ttu-id="96ca6-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="96ca6-196">-500.00</span></span> | <span data-ttu-id="96ca6-197">Ursprungligt belopp -500 × 1</span><span class="sxs-lookup"><span data-stu-id="96ca6-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="96ca6-198">801400</span><span class="sxs-lookup"><span data-stu-id="96ca6-198">801400</span></span>         | <span data-ttu-id="96ca6-199">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-199">EUR</span></span>      | <span data-ttu-id="96ca6-200">250</span><span class="sxs-lookup"><span data-stu-id="96ca6-200">250</span></span>     | <span data-ttu-id="96ca6-201">500 – 333,33 = 166,67 166,67 83,33 + = 250</span><span class="sxs-lookup"><span data-stu-id="96ca6-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="96ca6-202">801600</span><span class="sxs-lookup"><span data-stu-id="96ca6-202">801600</span></span>         | <span data-ttu-id="96ca6-203">Euro</span><span class="sxs-lookup"><span data-stu-id="96ca6-203">EUR</span></span>      | <span data-ttu-id="96ca6-204">-250</span><span class="sxs-lookup"><span data-stu-id="96ca6-204">-250</span></span>    | <span data-ttu-id="96ca6-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="96ca6-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |





