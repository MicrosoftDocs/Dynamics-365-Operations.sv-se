---
title: Valutaomvärdering i ett konsolideringsföretag
description: Detta avsnitt beskriver hur du omvärderar valuta i ett konsolideringsföretag.
author: ShylaThompson
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: 76290564037ab6f5c7a1cd4508a819bd603e8148
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567293"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="e7842-103">Valutaomvärdering i ett konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="e7842-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7842-104">När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas.</span><span class="sxs-lookup"><span data-stu-id="e7842-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="e7842-105">När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="e7842-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="e7842-106">Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon.</span><span class="sxs-lookup"><span data-stu-id="e7842-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="e7842-107">Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.</span><span class="sxs-lookup"><span data-stu-id="e7842-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="e7842-108">Följande exempel illustrerar bokföringsposter som skapas under processen.</span><span class="sxs-lookup"><span data-stu-id="e7842-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="e7842-109">Företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="e7842-109">Company setup</span></span>
-   <span data-ttu-id="e7842-110">**Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="e7842-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="e7842-111">**Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="e7842-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="e7842-112">**Vinsten** – reskontra 801500</span><span class="sxs-lookup"><span data-stu-id="e7842-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="e7842-113">**Förlusten** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="e7842-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="e7842-114">**Orealiserad vinst** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="e7842-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="e7842-115">**Orealiserad förlust** – reskontra 801400</span><span class="sxs-lookup"><span data-stu-id="e7842-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="e7842-116">Ursprungliga transaktioner</span><span class="sxs-lookup"><span data-stu-id="e7842-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="e7842-117">Kontantkvitto transaktioner i USMF</span><span class="sxs-lookup"><span data-stu-id="e7842-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="e7842-118">Datum</span><span class="sxs-lookup"><span data-stu-id="e7842-118">Date</span></span>       | <span data-ttu-id="e7842-119">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="e7842-119">Ledger account</span></span>               | <span data-ttu-id="e7842-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-120">Currency</span></span> | <span data-ttu-id="e7842-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="e7842-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="e7842-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="e7842-122">10/11/2015</span></span> | <span data-ttu-id="e7842-123">110110 – Kassa</span><span class="sxs-lookup"><span data-stu-id="e7842-123">110110 – Cash</span></span>                | <span data-ttu-id="e7842-124">USD</span><span class="sxs-lookup"><span data-stu-id="e7842-124">USD</span></span>      | <span data-ttu-id="e7842-125">500</span><span class="sxs-lookup"><span data-stu-id="e7842-125">500</span></span>    |
| <span data-ttu-id="e7842-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="e7842-126">10/11/2015</span></span> | <span data-ttu-id="e7842-127">130100 – Kundfordringar</span><span class="sxs-lookup"><span data-stu-id="e7842-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="e7842-128">USD</span><span class="sxs-lookup"><span data-stu-id="e7842-128">USD</span></span>      | <span data-ttu-id="e7842-129">-500</span><span class="sxs-lookup"><span data-stu-id="e7842-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="e7842-130">Valutakurser</span><span class="sxs-lookup"><span data-stu-id="e7842-130">Exchange rates</span></span>

| <span data-ttu-id="e7842-131">Från valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-131">From currency</span></span> | <span data-ttu-id="e7842-132">Till valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-132">To currency</span></span> | <span data-ttu-id="e7842-133">Startdatum</span><span class="sxs-lookup"><span data-stu-id="e7842-133">Start date</span></span> | <span data-ttu-id="e7842-134">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="e7842-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="e7842-135">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-135">EUR</span></span>           | <span data-ttu-id="e7842-136">USD</span><span class="sxs-lookup"><span data-stu-id="e7842-136">USD</span></span>         | <span data-ttu-id="e7842-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="e7842-137">10/1/2015</span></span>  | <span data-ttu-id="e7842-138">200</span><span class="sxs-lookup"><span data-stu-id="e7842-138">200</span></span>           |
| <span data-ttu-id="e7842-139">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-139">EUR</span></span>           | <span data-ttu-id="e7842-140">USD</span><span class="sxs-lookup"><span data-stu-id="e7842-140">USD</span></span>         | <span data-ttu-id="e7842-141">11-01 2015</span><span class="sxs-lookup"><span data-stu-id="e7842-141">11/1/2015</span></span>  | <span data-ttu-id="e7842-142">150</span><span class="sxs-lookup"><span data-stu-id="e7842-142">150</span></span>           |
| <span data-ttu-id="e7842-143">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-143">EUR</span></span>           | <span data-ttu-id="e7842-144">USD</span><span class="sxs-lookup"><span data-stu-id="e7842-144">USD</span></span>         | <span data-ttu-id="e7842-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="e7842-145">12/1/2012</span></span>  | <span data-ttu-id="e7842-146">100</span><span class="sxs-lookup"><span data-stu-id="e7842-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="e7842-147">Utföra konsolideringen för oktober 2015</span><span class="sxs-lookup"><span data-stu-id="e7842-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e7842-148">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="e7842-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="e7842-149">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="e7842-149">Ledger account</span></span> | <span data-ttu-id="e7842-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-150">Currency</span></span> | <span data-ttu-id="e7842-151">Belopp</span><span class="sxs-lookup"><span data-stu-id="e7842-151">Amount</span></span> | <span data-ttu-id="e7842-152">Beräkning</span><span class="sxs-lookup"><span data-stu-id="e7842-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="e7842-153">110110</span><span class="sxs-lookup"><span data-stu-id="e7842-153">110110</span></span>         | <span data-ttu-id="e7842-154">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-154">EUR</span></span>      | <span data-ttu-id="e7842-155">250</span><span class="sxs-lookup"><span data-stu-id="e7842-155">250</span></span>    | <span data-ttu-id="e7842-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="e7842-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="e7842-157">130100</span><span class="sxs-lookup"><span data-stu-id="e7842-157">130100</span></span>         | <span data-ttu-id="e7842-158">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-158">EUR</span></span>      | <span data-ttu-id="e7842-159">-250</span><span class="sxs-lookup"><span data-stu-id="e7842-159">-250</span></span>   | <span data-ttu-id="e7842-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="e7842-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="e7842-161">Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015</span><span class="sxs-lookup"><span data-stu-id="e7842-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e7842-162">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="e7842-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="e7842-163">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="e7842-163">Ledger account</span></span> | <span data-ttu-id="e7842-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-164">Currency</span></span> | <span data-ttu-id="e7842-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="e7842-165">Amount</span></span>  | <span data-ttu-id="e7842-166">Beräkning</span><span class="sxs-lookup"><span data-stu-id="e7842-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="e7842-167">110110</span><span class="sxs-lookup"><span data-stu-id="e7842-167">110110</span></span>         | <span data-ttu-id="e7842-168">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-168">EUR</span></span>      | <span data-ttu-id="e7842-169">333,33</span><span class="sxs-lookup"><span data-stu-id="e7842-169">333.33</span></span>  | <span data-ttu-id="e7842-170">Ursprungligt belopp av 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="e7842-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="e7842-171">130100</span><span class="sxs-lookup"><span data-stu-id="e7842-171">130100</span></span>         | <span data-ttu-id="e7842-172">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-172">EUR</span></span>      | <span data-ttu-id="e7842-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="e7842-173">-333.33</span></span> | <span data-ttu-id="e7842-174">Ursprungligt belopp -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="e7842-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="e7842-175">801400</span><span class="sxs-lookup"><span data-stu-id="e7842-175">801400</span></span>         | <span data-ttu-id="e7842-176">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-176">EUR</span></span>      | <span data-ttu-id="e7842-177">83,33</span><span class="sxs-lookup"><span data-stu-id="e7842-177">83.33</span></span>   | <span data-ttu-id="e7842-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="e7842-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="e7842-179">801600</span><span class="sxs-lookup"><span data-stu-id="e7842-179">801600</span></span>         | <span data-ttu-id="e7842-180">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-180">EUR</span></span>      | <span data-ttu-id="e7842-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="e7842-181">-83.33</span></span>  | <span data-ttu-id="e7842-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="e7842-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="e7842-183">Du kommer att se ytterligare transaktioner för rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="e7842-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="e7842-184">Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015</span><span class="sxs-lookup"><span data-stu-id="e7842-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e7842-185">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="e7842-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="e7842-186">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="e7842-186">Ledger account</span></span> | <span data-ttu-id="e7842-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="e7842-187">Currency</span></span> | <span data-ttu-id="e7842-188">Belopp</span><span class="sxs-lookup"><span data-stu-id="e7842-188">Amount</span></span>  | <span data-ttu-id="e7842-189">Beräkning</span><span class="sxs-lookup"><span data-stu-id="e7842-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="e7842-190">110110</span><span class="sxs-lookup"><span data-stu-id="e7842-190">110110</span></span>         | <span data-ttu-id="e7842-191">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-191">EUR</span></span>      | <span data-ttu-id="e7842-192">500.00</span><span class="sxs-lookup"><span data-stu-id="e7842-192">500.00</span></span>  | <span data-ttu-id="e7842-193">Ursprungligt belopp av 500 × 1</span><span class="sxs-lookup"><span data-stu-id="e7842-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="e7842-194">130100</span><span class="sxs-lookup"><span data-stu-id="e7842-194">130100</span></span>         | <span data-ttu-id="e7842-195">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-195">EUR</span></span>      | <span data-ttu-id="e7842-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="e7842-196">-500.00</span></span> | <span data-ttu-id="e7842-197">Ursprungligt belopp -500 × 1</span><span class="sxs-lookup"><span data-stu-id="e7842-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="e7842-198">801400</span><span class="sxs-lookup"><span data-stu-id="e7842-198">801400</span></span>         | <span data-ttu-id="e7842-199">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-199">EUR</span></span>      | <span data-ttu-id="e7842-200">250</span><span class="sxs-lookup"><span data-stu-id="e7842-200">250</span></span>     | <span data-ttu-id="e7842-201">500 – 333,33 = 166,67 166,67 83,33 + = 250</span><span class="sxs-lookup"><span data-stu-id="e7842-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="e7842-202">801600</span><span class="sxs-lookup"><span data-stu-id="e7842-202">801600</span></span>         | <span data-ttu-id="e7842-203">Euro</span><span class="sxs-lookup"><span data-stu-id="e7842-203">EUR</span></span>      | <span data-ttu-id="e7842-204">-250</span><span class="sxs-lookup"><span data-stu-id="e7842-204">-250</span></span>    | <span data-ttu-id="e7842-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="e7842-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |





