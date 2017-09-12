---
title: "Valutaomvärdering i en konsolideringsföretag"
description: 
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="6d7fc-102">Valutaomvärdering i en konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="6d7fc-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="6d7fc-103">När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="6d7fc-104">När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="6d7fc-105">Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="6d7fc-106">Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="6d7fc-107">Följande exempel illustrerar bokföringsposter som skapas under processen.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="6d7fc-108">Företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="6d7fc-108">Company setup</span></span>
-   <span data-ttu-id="6d7fc-109">**Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="6d7fc-110">**Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="6d7fc-111">**Realiserad vinst ** – Redovisningskonto 801500</span><span class="sxs-lookup"><span data-stu-id="6d7fc-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="6d7fc-112">**Förlusten** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="6d7fc-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="6d7fc-113">**Orealiserad vinst** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="6d7fc-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="6d7fc-114">**Orealiserad förlust** – reskontra 801400</span><span class="sxs-lookup"><span data-stu-id="6d7fc-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="6d7fc-115">Ursprungliga transaktioner</span><span class="sxs-lookup"><span data-stu-id="6d7fc-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="6d7fc-116">Kontantkvitto transaktioner i USMF</span><span class="sxs-lookup"><span data-stu-id="6d7fc-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="6d7fc-117">Datum</span><span class="sxs-lookup"><span data-stu-id="6d7fc-117">Date</span></span>       | <span data-ttu-id="6d7fc-118">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="6d7fc-118">Ledger account</span></span>               | <span data-ttu-id="6d7fc-119">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-119">Currency</span></span> | <span data-ttu-id="6d7fc-120">Belopp</span><span class="sxs-lookup"><span data-stu-id="6d7fc-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="6d7fc-121">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-121">10/11/2015</span></span> | <span data-ttu-id="6d7fc-122">110110 – Kassa</span><span class="sxs-lookup"><span data-stu-id="6d7fc-122">110110 – Cash</span></span>                | <span data-ttu-id="6d7fc-123">USD</span><span class="sxs-lookup"><span data-stu-id="6d7fc-123">USD</span></span>      | <span data-ttu-id="6d7fc-124">500</span><span class="sxs-lookup"><span data-stu-id="6d7fc-124">500</span></span>    |
| <span data-ttu-id="6d7fc-125">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-125">10/11/2015</span></span> | <span data-ttu-id="6d7fc-126">130100 – Kundfordringar</span><span class="sxs-lookup"><span data-stu-id="6d7fc-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="6d7fc-127">USD</span><span class="sxs-lookup"><span data-stu-id="6d7fc-127">USD</span></span>      | <span data-ttu-id="6d7fc-128">-500</span><span class="sxs-lookup"><span data-stu-id="6d7fc-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="6d7fc-129">Valutakurser</span><span class="sxs-lookup"><span data-stu-id="6d7fc-129">Exchange rates</span></span>
| <span data-ttu-id="6d7fc-130">Från valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-130">From currency</span></span> | <span data-ttu-id="6d7fc-131">Till valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-131">To currency</span></span> | <span data-ttu-id="6d7fc-132">Startdatum</span><span class="sxs-lookup"><span data-stu-id="6d7fc-132">Start date</span></span> | <span data-ttu-id="6d7fc-133">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="6d7fc-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="6d7fc-134">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-134">EUR</span></span>           | <span data-ttu-id="6d7fc-135">USD</span><span class="sxs-lookup"><span data-stu-id="6d7fc-135">USD</span></span>         | <span data-ttu-id="6d7fc-136">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-136">10/1/2015</span></span>  | <span data-ttu-id="6d7fc-137">200</span><span class="sxs-lookup"><span data-stu-id="6d7fc-137">200</span></span>           |
| <span data-ttu-id="6d7fc-138">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-138">EUR</span></span>           | <span data-ttu-id="6d7fc-139">USD</span><span class="sxs-lookup"><span data-stu-id="6d7fc-139">USD</span></span>         | <span data-ttu-id="6d7fc-140">11-01 2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-140">11/1/2015</span></span>  | <span data-ttu-id="6d7fc-141">150</span><span class="sxs-lookup"><span data-stu-id="6d7fc-141">150</span></span>           |
| <span data-ttu-id="6d7fc-142">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-142">EUR</span></span>           | <span data-ttu-id="6d7fc-143">USD</span><span class="sxs-lookup"><span data-stu-id="6d7fc-143">USD</span></span>         | <span data-ttu-id="6d7fc-144">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="6d7fc-144">12/1/2012</span></span>  | <span data-ttu-id="6d7fc-145">100</span><span class="sxs-lookup"><span data-stu-id="6d7fc-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="6d7fc-146">Utföra konsolideringen för oktober 2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="6d7fc-147">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="6d7fc-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="6d7fc-148">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="6d7fc-148">Ledger account</span></span> | <span data-ttu-id="6d7fc-149">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-149">Currency</span></span> | <span data-ttu-id="6d7fc-150">Belopp</span><span class="sxs-lookup"><span data-stu-id="6d7fc-150">Amount</span></span> | <span data-ttu-id="6d7fc-151">Beräkning</span><span class="sxs-lookup"><span data-stu-id="6d7fc-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="6d7fc-152">110110</span><span class="sxs-lookup"><span data-stu-id="6d7fc-152">110110</span></span>         | <span data-ttu-id="6d7fc-153">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-153">EUR</span></span>      | <span data-ttu-id="6d7fc-154">250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-154">250</span></span>    | <span data-ttu-id="6d7fc-155">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="6d7fc-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="6d7fc-156">130100</span><span class="sxs-lookup"><span data-stu-id="6d7fc-156">130100</span></span>         | <span data-ttu-id="6d7fc-157">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-157">EUR</span></span>      | <span data-ttu-id="6d7fc-158">-250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-158">-250</span></span>   | <span data-ttu-id="6d7fc-159">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="6d7fc-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="6d7fc-160">Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="6d7fc-161">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="6d7fc-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="6d7fc-162">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="6d7fc-162">Ledger account</span></span> | <span data-ttu-id="6d7fc-163">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-163">Currency</span></span> | <span data-ttu-id="6d7fc-164">Belopp</span><span class="sxs-lookup"><span data-stu-id="6d7fc-164">Amount</span></span>  | <span data-ttu-id="6d7fc-165">Beräkning</span><span class="sxs-lookup"><span data-stu-id="6d7fc-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="6d7fc-166">110110</span><span class="sxs-lookup"><span data-stu-id="6d7fc-166">110110</span></span>         | <span data-ttu-id="6d7fc-167">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-167">EUR</span></span>      | <span data-ttu-id="6d7fc-168">333,33</span><span class="sxs-lookup"><span data-stu-id="6d7fc-168">333.33</span></span>  | <span data-ttu-id="6d7fc-169">Ursprungligt belopp av 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="6d7fc-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="6d7fc-170">130100</span><span class="sxs-lookup"><span data-stu-id="6d7fc-170">130100</span></span>         | <span data-ttu-id="6d7fc-171">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-171">EUR</span></span>      | <span data-ttu-id="6d7fc-172">-333,33</span><span class="sxs-lookup"><span data-stu-id="6d7fc-172">-333.33</span></span> | <span data-ttu-id="6d7fc-173">Ursprungligt belopp -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="6d7fc-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="6d7fc-174">801400</span><span class="sxs-lookup"><span data-stu-id="6d7fc-174">801400</span></span>         | <span data-ttu-id="6d7fc-175">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-175">EUR</span></span>      | <span data-ttu-id="6d7fc-176">83,33</span><span class="sxs-lookup"><span data-stu-id="6d7fc-176">83.33</span></span>   | <span data-ttu-id="6d7fc-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="6d7fc-178">801600</span><span class="sxs-lookup"><span data-stu-id="6d7fc-178">801600</span></span>         | <span data-ttu-id="6d7fc-179">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-179">EUR</span></span>      | <span data-ttu-id="6d7fc-180">-83,33</span><span class="sxs-lookup"><span data-stu-id="6d7fc-180">-83.33</span></span>  | <span data-ttu-id="6d7fc-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="6d7fc-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="6d7fc-182">Du kommer att se ytterligare transaktioner för rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="6d7fc-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="6d7fc-183">Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015</span><span class="sxs-lookup"><span data-stu-id="6d7fc-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="6d7fc-184">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="6d7fc-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="6d7fc-185">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="6d7fc-185">Ledger account</span></span> | <span data-ttu-id="6d7fc-186">Valuta</span><span class="sxs-lookup"><span data-stu-id="6d7fc-186">Currency</span></span> | <span data-ttu-id="6d7fc-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="6d7fc-187">Amount</span></span>  | <span data-ttu-id="6d7fc-188">Beräkning</span><span class="sxs-lookup"><span data-stu-id="6d7fc-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="6d7fc-189">110110</span><span class="sxs-lookup"><span data-stu-id="6d7fc-189">110110</span></span>         | <span data-ttu-id="6d7fc-190">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-190">EUR</span></span>      | <span data-ttu-id="6d7fc-191">500.00</span><span class="sxs-lookup"><span data-stu-id="6d7fc-191">500.00</span></span>  | <span data-ttu-id="6d7fc-192">Ursprungligt belopp av 500 × 1</span><span class="sxs-lookup"><span data-stu-id="6d7fc-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="6d7fc-193">130100</span><span class="sxs-lookup"><span data-stu-id="6d7fc-193">130100</span></span>         | <span data-ttu-id="6d7fc-194">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-194">EUR</span></span>      | <span data-ttu-id="6d7fc-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="6d7fc-195">-500.00</span></span> | <span data-ttu-id="6d7fc-196">Ursprungligt belopp -500 × 1</span><span class="sxs-lookup"><span data-stu-id="6d7fc-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="6d7fc-197">801400</span><span class="sxs-lookup"><span data-stu-id="6d7fc-197">801400</span></span>         | <span data-ttu-id="6d7fc-198">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-198">EUR</span></span>      | <span data-ttu-id="6d7fc-199">250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-199">250</span></span>     | <span data-ttu-id="6d7fc-200">500 – 333,33 = 166,67 166,67 83,33 + = 250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="6d7fc-201">801600</span><span class="sxs-lookup"><span data-stu-id="6d7fc-201">801600</span></span>         | <span data-ttu-id="6d7fc-202">Euro</span><span class="sxs-lookup"><span data-stu-id="6d7fc-202">EUR</span></span>      | <span data-ttu-id="6d7fc-203">-250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-203">-250</span></span>    | <span data-ttu-id="6d7fc-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="6d7fc-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






