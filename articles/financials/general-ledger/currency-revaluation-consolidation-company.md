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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b7f0a18910cbaed382971e47eb688c075e7e6a5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839435"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="c1606-103">Valutaomvärdering i ett konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="c1606-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1606-104">När du konsolidera data från en redovisningsvaluta till en annan måste du fortfarande köra valutaomvärdering om det sker en förändring i valutakurser, så att ditt konto saldo är korrekt omvärderas.</span><span class="sxs-lookup"><span data-stu-id="c1606-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="c1606-105">När du ursprungligen konsolidera data, använd **valutakursdifferens** flik för att välja den första växelkurser för översättning under konsolideringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="c1606-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="c1606-106">Efter en ny valutakurs registreras (t.ex. i nästa månad), du måste omvärdera den kontosaldon.</span><span class="sxs-lookup"><span data-stu-id="c1606-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="c1606-107">Den orealiserade vinster eller förluster som sedan uppdateras baserat på den nya växelkursen och datum.</span><span class="sxs-lookup"><span data-stu-id="c1606-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="c1606-108">Följande exempel illustrerar bokföringsposter som skapas under processen.</span><span class="sxs-lookup"><span data-stu-id="c1606-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="c1606-109">Företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="c1606-109">Company setup</span></span>
-   <span data-ttu-id="c1606-110">**Källa/driftbolaget (USMF)** – US dollar (USD) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="c1606-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="c1606-111">**Koncernens bolag (CON)** – EURO (EUR) används som redovisning och rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="c1606-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="c1606-112">**Vinsten** – reskontra 801500</span><span class="sxs-lookup"><span data-stu-id="c1606-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="c1606-113">**Förlusten** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="c1606-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="c1606-114">**Orealiserad vinst** – reskontra 801600</span><span class="sxs-lookup"><span data-stu-id="c1606-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="c1606-115">**Orealiserad förlust** – reskontra 801400</span><span class="sxs-lookup"><span data-stu-id="c1606-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="c1606-116">Ursprungliga transaktioner</span><span class="sxs-lookup"><span data-stu-id="c1606-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="c1606-117">Kontantkvitto transaktioner i USMF</span><span class="sxs-lookup"><span data-stu-id="c1606-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="c1606-118">Datum</span><span class="sxs-lookup"><span data-stu-id="c1606-118">Date</span></span>       | <span data-ttu-id="c1606-119">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="c1606-119">Ledger account</span></span>               | <span data-ttu-id="c1606-120">Valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-120">Currency</span></span> | <span data-ttu-id="c1606-121">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1606-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="c1606-122">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="c1606-122">10/11/2015</span></span> | <span data-ttu-id="c1606-123">110110 – Kassa</span><span class="sxs-lookup"><span data-stu-id="c1606-123">110110 – Cash</span></span>                | <span data-ttu-id="c1606-124">USD</span><span class="sxs-lookup"><span data-stu-id="c1606-124">USD</span></span>      | <span data-ttu-id="c1606-125">500</span><span class="sxs-lookup"><span data-stu-id="c1606-125">500</span></span>    |
| <span data-ttu-id="c1606-126">10/11/2015</span><span class="sxs-lookup"><span data-stu-id="c1606-126">10/11/2015</span></span> | <span data-ttu-id="c1606-127">130100 – Kundfordringar</span><span class="sxs-lookup"><span data-stu-id="c1606-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="c1606-128">USD</span><span class="sxs-lookup"><span data-stu-id="c1606-128">USD</span></span>      | <span data-ttu-id="c1606-129">-500</span><span class="sxs-lookup"><span data-stu-id="c1606-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="c1606-130">Valutakurser</span><span class="sxs-lookup"><span data-stu-id="c1606-130">Exchange rates</span></span>

| <span data-ttu-id="c1606-131">Från valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-131">From currency</span></span> | <span data-ttu-id="c1606-132">Till valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-132">To currency</span></span> | <span data-ttu-id="c1606-133">Startdatum</span><span class="sxs-lookup"><span data-stu-id="c1606-133">Start date</span></span> | <span data-ttu-id="c1606-134">Valutakurs</span><span class="sxs-lookup"><span data-stu-id="c1606-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="c1606-135">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-135">EUR</span></span>           | <span data-ttu-id="c1606-136">USD</span><span class="sxs-lookup"><span data-stu-id="c1606-136">USD</span></span>         | <span data-ttu-id="c1606-137">10/1/2015</span><span class="sxs-lookup"><span data-stu-id="c1606-137">10/1/2015</span></span>  | <span data-ttu-id="c1606-138">200</span><span class="sxs-lookup"><span data-stu-id="c1606-138">200</span></span>           |
| <span data-ttu-id="c1606-139">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-139">EUR</span></span>           | <span data-ttu-id="c1606-140">USD</span><span class="sxs-lookup"><span data-stu-id="c1606-140">USD</span></span>         | <span data-ttu-id="c1606-141">11-01 2015</span><span class="sxs-lookup"><span data-stu-id="c1606-141">11/1/2015</span></span>  | <span data-ttu-id="c1606-142">150</span><span class="sxs-lookup"><span data-stu-id="c1606-142">150</span></span>           |
| <span data-ttu-id="c1606-143">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-143">EUR</span></span>           | <span data-ttu-id="c1606-144">USD</span><span class="sxs-lookup"><span data-stu-id="c1606-144">USD</span></span>         | <span data-ttu-id="c1606-145">12/1/2012</span><span class="sxs-lookup"><span data-stu-id="c1606-145">12/1/2012</span></span>  | <span data-ttu-id="c1606-146">100</span><span class="sxs-lookup"><span data-stu-id="c1606-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="c1606-147">Utföra konsolideringen för oktober 2015</span><span class="sxs-lookup"><span data-stu-id="c1606-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c1606-148">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="c1606-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="c1606-149">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="c1606-149">Ledger account</span></span> | <span data-ttu-id="c1606-150">Valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-150">Currency</span></span> | <span data-ttu-id="c1606-151">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1606-151">Amount</span></span> | <span data-ttu-id="c1606-152">Beräkning</span><span class="sxs-lookup"><span data-stu-id="c1606-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="c1606-153">110110</span><span class="sxs-lookup"><span data-stu-id="c1606-153">110110</span></span>         | <span data-ttu-id="c1606-154">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-154">EUR</span></span>      | <span data-ttu-id="c1606-155">250</span><span class="sxs-lookup"><span data-stu-id="c1606-155">250</span></span>    | <span data-ttu-id="c1606-156">500 USD × 50 %</span><span class="sxs-lookup"><span data-stu-id="c1606-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="c1606-157">130100</span><span class="sxs-lookup"><span data-stu-id="c1606-157">130100</span></span>         | <span data-ttu-id="c1606-158">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-158">EUR</span></span>      | <span data-ttu-id="c1606-159">-250</span><span class="sxs-lookup"><span data-stu-id="c1606-159">-250</span></span>   | <span data-ttu-id="c1606-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="c1606-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="c1606-161">Utföra valutaomvärdering för räkenskaper från den 1 oktober 2015, genom den 30 November, 2015</span><span class="sxs-lookup"><span data-stu-id="c1606-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c1606-162">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="c1606-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="c1606-163">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="c1606-163">Ledger account</span></span> | <span data-ttu-id="c1606-164">Valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-164">Currency</span></span> | <span data-ttu-id="c1606-165">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1606-165">Amount</span></span>  | <span data-ttu-id="c1606-166">Beräkning</span><span class="sxs-lookup"><span data-stu-id="c1606-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="c1606-167">110110</span><span class="sxs-lookup"><span data-stu-id="c1606-167">110110</span></span>         | <span data-ttu-id="c1606-168">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-168">EUR</span></span>      | <span data-ttu-id="c1606-169">333,33</span><span class="sxs-lookup"><span data-stu-id="c1606-169">333.33</span></span>  | <span data-ttu-id="c1606-170">Ursprungligt belopp av 500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="c1606-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="c1606-171">130100</span><span class="sxs-lookup"><span data-stu-id="c1606-171">130100</span></span>         | <span data-ttu-id="c1606-172">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-172">EUR</span></span>      | <span data-ttu-id="c1606-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="c1606-173">-333.33</span></span> | <span data-ttu-id="c1606-174">Ursprungligt belopp -500 × 66,6667 %</span><span class="sxs-lookup"><span data-stu-id="c1606-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="c1606-175">801400</span><span class="sxs-lookup"><span data-stu-id="c1606-175">801400</span></span>         | <span data-ttu-id="c1606-176">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-176">EUR</span></span>      | <span data-ttu-id="c1606-177">83,33</span><span class="sxs-lookup"><span data-stu-id="c1606-177">83.33</span></span>   | <span data-ttu-id="c1606-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="c1606-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="c1606-179">801600</span><span class="sxs-lookup"><span data-stu-id="c1606-179">801600</span></span>         | <span data-ttu-id="c1606-180">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-180">EUR</span></span>      | <span data-ttu-id="c1606-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="c1606-181">-83.33</span></span>  | <span data-ttu-id="c1606-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="c1606-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="c1606-183">Du kommer att se ytterligare transaktioner för rapportering valuta.</span><span class="sxs-lookup"><span data-stu-id="c1606-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="c1606-184">Utföra valutaomvärdering för räkenskaper från 1 oktober 2015 till 31 December 2015</span><span class="sxs-lookup"><span data-stu-id="c1606-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="c1606-185">Saldon i fältet konsolideringsföretag</span><span class="sxs-lookup"><span data-stu-id="c1606-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="c1606-186">Redovisningskonto</span><span class="sxs-lookup"><span data-stu-id="c1606-186">Ledger account</span></span> | <span data-ttu-id="c1606-187">Valuta</span><span class="sxs-lookup"><span data-stu-id="c1606-187">Currency</span></span> | <span data-ttu-id="c1606-188">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1606-188">Amount</span></span>  | <span data-ttu-id="c1606-189">Beräkning</span><span class="sxs-lookup"><span data-stu-id="c1606-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="c1606-190">110110</span><span class="sxs-lookup"><span data-stu-id="c1606-190">110110</span></span>         | <span data-ttu-id="c1606-191">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-191">EUR</span></span>      | <span data-ttu-id="c1606-192">500.00</span><span class="sxs-lookup"><span data-stu-id="c1606-192">500.00</span></span>  | <span data-ttu-id="c1606-193">Ursprungligt belopp av 500 × 1</span><span class="sxs-lookup"><span data-stu-id="c1606-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="c1606-194">130100</span><span class="sxs-lookup"><span data-stu-id="c1606-194">130100</span></span>         | <span data-ttu-id="c1606-195">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-195">EUR</span></span>      | <span data-ttu-id="c1606-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="c1606-196">-500.00</span></span> | <span data-ttu-id="c1606-197">Ursprungligt belopp -500 × 1</span><span class="sxs-lookup"><span data-stu-id="c1606-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="c1606-198">801400</span><span class="sxs-lookup"><span data-stu-id="c1606-198">801400</span></span>         | <span data-ttu-id="c1606-199">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-199">EUR</span></span>      | <span data-ttu-id="c1606-200">250</span><span class="sxs-lookup"><span data-stu-id="c1606-200">250</span></span>     | <span data-ttu-id="c1606-201">500 – 333,33 = 166,67 166,67 83,33 + = 250</span><span class="sxs-lookup"><span data-stu-id="c1606-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="c1606-202">801600</span><span class="sxs-lookup"><span data-stu-id="c1606-202">801600</span></span>         | <span data-ttu-id="c1606-203">Euro</span><span class="sxs-lookup"><span data-stu-id="c1606-203">EUR</span></span>      | <span data-ttu-id="c1606-204">-250</span><span class="sxs-lookup"><span data-stu-id="c1606-204">-250</span></span>    | <span data-ttu-id="c1606-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="c1606-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |





