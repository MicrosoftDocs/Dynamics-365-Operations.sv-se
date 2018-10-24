---
title: "Valutaomvärdering i ett konsolideringsföretag"
description: "Detta avsnitt beskriver hur du omvärderar valuta i ett konsolideringsföretag."
author: ShylaThompson
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad0083018d2734cb1e36cbf5f94105376c57cdf9
ms.openlocfilehash: 76290564037ab6f5c7a1cd4508a819bd603e8148
ms.contentlocale: sv-se
ms.lasthandoff: 10/02/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="42297-103">Valutaomvärdering i ett konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="42297-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42297-104">När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas.</span><span class="sxs-lookup"><span data-stu-id="42297-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="42297-105">När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="42297-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="42297-106">Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon.</span><span class="sxs-lookup"><span data-stu-id="42297-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="42297-107">Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.</span><span class="sxs-lookup"><span data-stu-id="42297-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="42297-108">Följande exempel illustrerar bokföringsposter som skapas under processen.</span><span class="sxs-lookup"><span data-stu-id="42297-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="42297-109">Företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="42297-109">Company setup</span></span>
-   <span data-ttu-id="42297-110">**Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="42297-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="42297-111">**Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="42297-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="42297-112">**Vinsten** – reskontra 801500</span><span class="sxs-lookup"><span data-stu-id="42297-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="42297-113">**Förlusten** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="42297-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="42297-114">**Orealiserad vinst** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="42297-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="42297-115">**Orealiserad förlust** – reskontra 801400</span><span class="sxs-lookup"><span data-stu-id="42297-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="42297-116">Ursprungliga transaktioner</span><span class="sxs-lookup"><span data-stu-id="42297-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="42297-117">Kontantkvitto transaktioner i USMF</span><span class="sxs-lookup"><span data-stu-id="42297-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="42297-118">Datum</span><span class="sxs-lookup"><span data-stu-id="42297-118">Date</span></span>       | <span data-ttu-id="42297-119">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="42297-119">Ledger account</span></span>               | <span data-ttu-id="42297-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="42297-120">Currency</span></span> | <span data-ttu-id="42297-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="42297-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="42297-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="42297-122">10/11/2015</span></span> | <span data-ttu-id="42297-123">110110 – Kassa</span><span class="sxs-lookup"><span data-stu-id="42297-123">110110 – Cash</span></span>                | <span data-ttu-id="42297-124">USD</span><span class="sxs-lookup"><span data-stu-id="42297-124">USD</span></span>      | <span data-ttu-id="42297-125">500</span><span class="sxs-lookup"><span data-stu-id="42297-125">500</span></span>    |
| <span data-ttu-id="42297-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="42297-126">10/11/2015</span></span> | <span data-ttu-id="42297-127">130100 – Kundfordringar</span><span class="sxs-lookup"><span data-stu-id="42297-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="42297-128">USD</span><span class="sxs-lookup"><span data-stu-id="42297-128">USD</span></span>      | <span data-ttu-id="42297-129">-500</span><span class="sxs-lookup"><span data-stu-id="42297-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="42297-130">Valutakurser</span><span class="sxs-lookup"><span data-stu-id="42297-130">Exchange rates</span></span>

| <span data-ttu-id="42297-131">Från valuta</span><span class="sxs-lookup"><span data-stu-id="42297-131">From currency</span></span> | <span data-ttu-id="42297-132">Till valuta</span><span class="sxs-lookup"><span data-stu-id="42297-132">To currency</span></span> | <span data-ttu-id="42297-133">Startdatum</span><span class="sxs-lookup"><span data-stu-id="42297-133">Start date</span></span> | <span data-ttu-id="42297-134">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="42297-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="42297-135">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-135">EUR</span></span>           | <span data-ttu-id="42297-136">USD</span><span class="sxs-lookup"><span data-stu-id="42297-136">USD</span></span>         | <span data-ttu-id="42297-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="42297-137">10/1/2015</span></span>  | <span data-ttu-id="42297-138">200</span><span class="sxs-lookup"><span data-stu-id="42297-138">200</span></span>           |
| <span data-ttu-id="42297-139">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-139">EUR</span></span>           | <span data-ttu-id="42297-140">USD</span><span class="sxs-lookup"><span data-stu-id="42297-140">USD</span></span>         | <span data-ttu-id="42297-141">11-01 2015</span><span class="sxs-lookup"><span data-stu-id="42297-141">11/1/2015</span></span>  | <span data-ttu-id="42297-142">150</span><span class="sxs-lookup"><span data-stu-id="42297-142">150</span></span>           |
| <span data-ttu-id="42297-143">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-143">EUR</span></span>           | <span data-ttu-id="42297-144">USD</span><span class="sxs-lookup"><span data-stu-id="42297-144">USD</span></span>         | <span data-ttu-id="42297-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="42297-145">12/1/2012</span></span>  | <span data-ttu-id="42297-146">100</span><span class="sxs-lookup"><span data-stu-id="42297-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="42297-147">Utföra konsolideringen för oktober 2015</span><span class="sxs-lookup"><span data-stu-id="42297-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="42297-148">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="42297-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="42297-149">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="42297-149">Ledger account</span></span> | <span data-ttu-id="42297-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="42297-150">Currency</span></span> | <span data-ttu-id="42297-151">Belopp</span><span class="sxs-lookup"><span data-stu-id="42297-151">Amount</span></span> | <span data-ttu-id="42297-152">Beräkning</span><span class="sxs-lookup"><span data-stu-id="42297-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="42297-153">110110</span><span class="sxs-lookup"><span data-stu-id="42297-153">110110</span></span>         | <span data-ttu-id="42297-154">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-154">EUR</span></span>      | <span data-ttu-id="42297-155">250</span><span class="sxs-lookup"><span data-stu-id="42297-155">250</span></span>    | <span data-ttu-id="42297-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="42297-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="42297-157">130100</span><span class="sxs-lookup"><span data-stu-id="42297-157">130100</span></span>         | <span data-ttu-id="42297-158">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-158">EUR</span></span>      | <span data-ttu-id="42297-159">-250</span><span class="sxs-lookup"><span data-stu-id="42297-159">-250</span></span>   | <span data-ttu-id="42297-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="42297-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="42297-161">Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015</span><span class="sxs-lookup"><span data-stu-id="42297-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="42297-162">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="42297-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="42297-163">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="42297-163">Ledger account</span></span> | <span data-ttu-id="42297-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="42297-164">Currency</span></span> | <span data-ttu-id="42297-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="42297-165">Amount</span></span>  | <span data-ttu-id="42297-166">Beräkning</span><span class="sxs-lookup"><span data-stu-id="42297-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="42297-167">110110</span><span class="sxs-lookup"><span data-stu-id="42297-167">110110</span></span>         | <span data-ttu-id="42297-168">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-168">EUR</span></span>      | <span data-ttu-id="42297-169">333,33</span><span class="sxs-lookup"><span data-stu-id="42297-169">333.33</span></span>  | <span data-ttu-id="42297-170">Ursprungligt belopp av 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="42297-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="42297-171">130100</span><span class="sxs-lookup"><span data-stu-id="42297-171">130100</span></span>         | <span data-ttu-id="42297-172">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-172">EUR</span></span>      | <span data-ttu-id="42297-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="42297-173">-333.33</span></span> | <span data-ttu-id="42297-174">Ursprungligt belopp -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="42297-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="42297-175">801400</span><span class="sxs-lookup"><span data-stu-id="42297-175">801400</span></span>         | <span data-ttu-id="42297-176">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-176">EUR</span></span>      | <span data-ttu-id="42297-177">83,33</span><span class="sxs-lookup"><span data-stu-id="42297-177">83.33</span></span>   | <span data-ttu-id="42297-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="42297-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="42297-179">801600</span><span class="sxs-lookup"><span data-stu-id="42297-179">801600</span></span>         | <span data-ttu-id="42297-180">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-180">EUR</span></span>      | <span data-ttu-id="42297-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="42297-181">-83.33</span></span>  | <span data-ttu-id="42297-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="42297-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="42297-183">Du kommer att se ytterligare transaktioner för rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="42297-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="42297-184">Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015</span><span class="sxs-lookup"><span data-stu-id="42297-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="42297-185">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="42297-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="42297-186">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="42297-186">Ledger account</span></span> | <span data-ttu-id="42297-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="42297-187">Currency</span></span> | <span data-ttu-id="42297-188">Belopp</span><span class="sxs-lookup"><span data-stu-id="42297-188">Amount</span></span>  | <span data-ttu-id="42297-189">Beräkning</span><span class="sxs-lookup"><span data-stu-id="42297-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="42297-190">110110</span><span class="sxs-lookup"><span data-stu-id="42297-190">110110</span></span>         | <span data-ttu-id="42297-191">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-191">EUR</span></span>      | <span data-ttu-id="42297-192">500.00</span><span class="sxs-lookup"><span data-stu-id="42297-192">500.00</span></span>  | <span data-ttu-id="42297-193">Ursprungligt belopp av 500 × 1</span><span class="sxs-lookup"><span data-stu-id="42297-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="42297-194">130100</span><span class="sxs-lookup"><span data-stu-id="42297-194">130100</span></span>         | <span data-ttu-id="42297-195">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-195">EUR</span></span>      | <span data-ttu-id="42297-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="42297-196">-500.00</span></span> | <span data-ttu-id="42297-197">Ursprungligt belopp -500 × 1</span><span class="sxs-lookup"><span data-stu-id="42297-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="42297-198">801400</span><span class="sxs-lookup"><span data-stu-id="42297-198">801400</span></span>         | <span data-ttu-id="42297-199">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-199">EUR</span></span>      | <span data-ttu-id="42297-200">250</span><span class="sxs-lookup"><span data-stu-id="42297-200">250</span></span>     | <span data-ttu-id="42297-201">500 – 333,33 = 166,67 166,67 83,33 + = 250</span><span class="sxs-lookup"><span data-stu-id="42297-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="42297-202">801600</span><span class="sxs-lookup"><span data-stu-id="42297-202">801600</span></span>         | <span data-ttu-id="42297-203">Euro</span><span class="sxs-lookup"><span data-stu-id="42297-203">EUR</span></span>      | <span data-ttu-id="42297-204">-250</span><span class="sxs-lookup"><span data-stu-id="42297-204">-250</span></span>    | <span data-ttu-id="42297-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="42297-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






