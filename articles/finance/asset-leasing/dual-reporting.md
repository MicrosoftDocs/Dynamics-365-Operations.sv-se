---
title: Dubbel rapportering
description: I det här avsnittet får du hjälp med ett exempel som visar hur du kan uppfylla kraven för både IFRS-rapportering (International Financial Reporting Standard) och lagstadgad rapportering i Tillgångsleasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a7d9b3ea3d4f1d48b8a7326bd5a01d3119310c62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003191"
---
# <a name="dual-reporting"></a><span data-ttu-id="ef610-103">Dubbel rapportering</span><span class="sxs-lookup"><span data-stu-id="ef610-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef610-104">I det här avsnittet får du hjälp med ett exempel som visar hur du kan uppfylla kraven för både IFRS-rapportering (International Financial Reporting Standard) och lagstadgad rapportering i Tillgångsleasing.</span><span class="sxs-lookup"><span data-stu-id="ef610-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="ef610-105">Det är viktigt att känna till bokföringsskikt i Microsoft Dynamics 365 Finance och det gör att exemplet blir lättare att förstå.</span><span class="sxs-lookup"><span data-stu-id="ef610-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="ef610-106">Exempel</span><span class="sxs-lookup"><span data-stu-id="ef610-106">Example</span></span>

<span data-ttu-id="ef610-107">I följande exempel redovisas en leasing enligt italiensk lagstadgad rapportering med hjälp av både kontantmetoden och IFRS-rapporteringsmetoder.</span><span class="sxs-lookup"><span data-stu-id="ef610-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="ef610-108">Företaget måste upprätta tre räkenskapsböcker för både de italienska lagstadgade kraven och IFRS 16-kraven.</span><span class="sxs-lookup"><span data-stu-id="ef610-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="ef610-109">En bok krävs för IFRS 16, en bok krävs för lagstadgade krav, och en bok krävs för att automatiskt återföra lagstadgade bokföringar.</span><span class="sxs-lookup"><span data-stu-id="ef610-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="ef610-110">Räkenskapsböckerna ställs in på det sätt som visas i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="ef610-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="ef610-111">**IFRS 16-räkenskapsbok**</span><span class="sxs-lookup"><span data-stu-id="ef610-111">**IFRS 16 book**</span></span>

<span data-ttu-id="ef610-112">IFRS 16-boken har ställts in så att den överensstämmer med IFRS 16-redovisningsstandarden.</span><span class="sxs-lookup"><span data-stu-id="ef610-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="ef610-113">Alla transaktioner som bokförs i den här boken kommer att bokföras i ett anpassat skikt.</span><span class="sxs-lookup"><span data-stu-id="ef610-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="ef610-114">Namn</span><span class="sxs-lookup"><span data-stu-id="ef610-114">Name</span></span>                                    | <span data-ttu-id="ef610-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="ef610-116">Typ av bok</span><span class="sxs-lookup"><span data-stu-id="ef610-116">Book type</span></span>                               | <span data-ttu-id="ef610-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ef610-117">IFRS 16</span></span>        |
| <span data-ttu-id="ef610-118">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-118">Book description</span></span>                        | <span data-ttu-id="ef610-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ef610-119">IFRS 16</span></span>        |
| <span data-ttu-id="ef610-120">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="ef610-120">Posting Layer</span></span>                           | <span data-ttu-id="ef610-121">Anpassat skikt 1</span><span class="sxs-lookup"><span data-stu-id="ef610-121">Custom layer 1</span></span> |
| <span data-ttu-id="ef610-122">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="ef610-122">Lease Type</span></span>                              | <span data-ttu-id="ef610-123">Finance</span><span class="sxs-lookup"><span data-stu-id="ef610-123">Finance</span></span>        |
| <span data-ttu-id="ef610-124">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="ef610-124">Accounting Framework</span></span>                    | <span data-ttu-id="ef610-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ef610-125">IFRS 16</span></span>        |
| <span data-ttu-id="ef610-126">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="ef610-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ef610-127">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-127">0.00</span></span>           |
| <span data-ttu-id="ef610-128">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="ef610-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ef610-129">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-129">0.00</span></span>           |
| <span data-ttu-id="ef610-130">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-130">Short-term threshold</span></span>                    | <span data-ttu-id="ef610-131">12</span><span class="sxs-lookup"><span data-stu-id="ef610-131">12</span></span>             |
| <span data-ttu-id="ef610-132">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-132">Low Value Threshold</span></span>                     | <span data-ttu-id="ef610-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-133">5,000.00</span></span>       |
| <span data-ttu-id="ef610-134">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-134">Pay to Vendor</span></span>                           | <span data-ttu-id="ef610-135">Nr</span><span class="sxs-lookup"><span data-stu-id="ef610-135">No</span></span>             |

<span data-ttu-id="ef610-136">**Lagstadgad räkenskapsbok**</span><span class="sxs-lookup"><span data-stu-id="ef610-136">**Statutory book**</span></span>

<span data-ttu-id="ef610-137">Den lagstadgade räkenskapsboken är kontantmetodsbok där företaget redovisar leasingkostnaden som det kontantbelopp som betalas varje månad som hyra.</span><span class="sxs-lookup"><span data-stu-id="ef610-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="ef610-138">Boken skapar inte någon tillgång med nyttjanderätt (ROU) eller leasingskuld.</span><span class="sxs-lookup"><span data-stu-id="ef610-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="ef610-139">Namn</span><span class="sxs-lookup"><span data-stu-id="ef610-139">Name</span></span>                                    | <span data-ttu-id="ef610-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="ef610-141">Typ av bok</span><span class="sxs-lookup"><span data-stu-id="ef610-141">Book type</span></span>                               | <span data-ttu-id="ef610-142">Lagstadgad</span><span class="sxs-lookup"><span data-stu-id="ef610-142">Statutory</span></span>   |
| <span data-ttu-id="ef610-143">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-143">Book description</span></span>                        | <span data-ttu-id="ef610-144">Lokal GAAP</span><span class="sxs-lookup"><span data-stu-id="ef610-144">Local GAAP</span></span>  |
| <span data-ttu-id="ef610-145">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="ef610-145">Posting Layer</span></span>                           | <span data-ttu-id="ef610-146">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-146">Current</span></span>     |
| <span data-ttu-id="ef610-147">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="ef610-147">Lease Type</span></span>                              | <span data-ttu-id="ef610-148">Automatisk</span><span class="sxs-lookup"><span data-stu-id="ef610-148">Automatic</span></span>   |
| <span data-ttu-id="ef610-149">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="ef610-149">Accounting Framework</span></span>                    | <span data-ttu-id="ef610-150">Kontantunderlag</span><span class="sxs-lookup"><span data-stu-id="ef610-150">Cash basis</span></span>  |
| <span data-ttu-id="ef610-151">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="ef610-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ef610-152">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-152">0.00</span></span>        |
| <span data-ttu-id="ef610-153">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="ef610-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ef610-154">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-154">0.00</span></span>        |
| <span data-ttu-id="ef610-155">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-155">Short-term threshold</span></span>                    | <span data-ttu-id="ef610-156">0</span><span class="sxs-lookup"><span data-stu-id="ef610-156">0</span></span>           |
| <span data-ttu-id="ef610-157">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-157">Low Value Threshold</span></span>                     | <span data-ttu-id="ef610-158">0</span><span class="sxs-lookup"><span data-stu-id="ef610-158">0</span></span>           |
| <span data-ttu-id="ef610-159">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-159">Pay to Vendor</span></span>                           | <span data-ttu-id="ef610-160">Nr</span><span class="sxs-lookup"><span data-stu-id="ef610-160">No</span></span>          |

<span data-ttu-id="ef610-161">**Lagstadgad återföringsbok**</span><span class="sxs-lookup"><span data-stu-id="ef610-161">**Statutory reversal book**</span></span>

<span data-ttu-id="ef610-162">Den lagstadgade återföringsboken ställs in på samma sätt som den lagstadgade räkenskapsboken.</span><span class="sxs-lookup"><span data-stu-id="ef610-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="ef610-163">Namn</span><span class="sxs-lookup"><span data-stu-id="ef610-163">Name</span></span>                                    | <span data-ttu-id="ef610-164">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="ef610-165">Boktyp</span><span class="sxs-lookup"><span data-stu-id="ef610-165">Book type</span></span>                               | <span data-ttu-id="ef610-166">Lagstadgad – återföring</span><span class="sxs-lookup"><span data-stu-id="ef610-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="ef610-167">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-167">Book description</span></span>                        | <span data-ttu-id="ef610-168">Räkenskapsbok för att återföra den lagstadgade räkenskapsboken</span><span class="sxs-lookup"><span data-stu-id="ef610-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="ef610-169">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="ef610-169">Posting Layer</span></span>                           | <span data-ttu-id="ef610-170">Anpassat skikt 1</span><span class="sxs-lookup"><span data-stu-id="ef610-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="ef610-171">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="ef610-171">Lease Type</span></span>                              | <span data-ttu-id="ef610-172">Automatisk</span><span class="sxs-lookup"><span data-stu-id="ef610-172">Automatic</span></span>                      |
| <span data-ttu-id="ef610-173">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="ef610-173">Accounting Framework</span></span>                    | <span data-ttu-id="ef610-174">Kontantunderlag</span><span class="sxs-lookup"><span data-stu-id="ef610-174">Cash basis</span></span>                     |
| <span data-ttu-id="ef610-175">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="ef610-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ef610-176">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-176">0.00</span></span>                           |
| <span data-ttu-id="ef610-177">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="ef610-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ef610-178">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-178">0.00</span></span>                           |
| <span data-ttu-id="ef610-179">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-179">Short-term threshold</span></span>                    | <span data-ttu-id="ef610-180">0</span><span class="sxs-lookup"><span data-stu-id="ef610-180">0</span></span>                              |
| <span data-ttu-id="ef610-181">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="ef610-181">Low Value Threshold</span></span>                     | <span data-ttu-id="ef610-182">0</span><span class="sxs-lookup"><span data-stu-id="ef610-182">0</span></span>                              |
| <span data-ttu-id="ef610-183">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-183">Pay to Vendor</span></span>                           | <span data-ttu-id="ef610-184">Nr</span><span class="sxs-lookup"><span data-stu-id="ef610-184">No</span></span>                             |

<span data-ttu-id="ef610-185">I det här exemplet har en leasing skapats med följande inställningar på flikarna **Allmänt** och **Betalningsplanrader**.</span><span class="sxs-lookup"><span data-stu-id="ef610-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="ef610-186">**Fliken Allmänt**</span><span class="sxs-lookup"><span data-stu-id="ef610-186">**General tab**</span></span>

| <span data-ttu-id="ef610-187">Fält</span><span class="sxs-lookup"><span data-stu-id="ef610-187">Field</span></span>                      | <span data-ttu-id="ef610-188">Värde</span><span class="sxs-lookup"><span data-stu-id="ef610-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="ef610-189">Marginell låneränta</span><span class="sxs-lookup"><span data-stu-id="ef610-189">Incremental borrowing rate</span></span> | <span data-ttu-id="ef610-190">5 %</span><span class="sxs-lookup"><span data-stu-id="ef610-190">5%</span></span>               |
| <span data-ttu-id="ef610-191">Startdatum</span><span class="sxs-lookup"><span data-stu-id="ef610-191">Commencement date</span></span>          | <span data-ttu-id="ef610-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="ef610-192">1/1/2020</span></span>         |
| <span data-ttu-id="ef610-193">Leasinggrupp</span><span class="sxs-lookup"><span data-stu-id="ef610-193">Lease group</span></span>                | <span data-ttu-id="ef610-194">Byggnader</span><span class="sxs-lookup"><span data-stu-id="ef610-194">Buildings</span></span>        |
| <span data-ttu-id="ef610-195">Leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-195">Vendor</span></span>                     | <span data-ttu-id="ef610-196">1001</span><span class="sxs-lookup"><span data-stu-id="ef610-196">1001</span></span>             |
| <span data-ttu-id="ef610-197">Tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="ef610-197">Fair value of the asset</span></span>    | <span data-ttu-id="ef610-198">245,000</span><span class="sxs-lookup"><span data-stu-id="ef610-198">245,000</span></span>          |
| <span data-ttu-id="ef610-199">Tillgångens livslängd</span><span class="sxs-lookup"><span data-stu-id="ef610-199">Asset useful life</span></span>          | <span data-ttu-id="ef610-200">120</span><span class="sxs-lookup"><span data-stu-id="ef610-200">120</span></span>              |
| <span data-ttu-id="ef610-201">Typ av annuitet</span><span class="sxs-lookup"><span data-stu-id="ef610-201">Annuity type</span></span>               | <span data-ttu-id="ef610-202">Vanlig annuitet</span><span class="sxs-lookup"><span data-stu-id="ef610-202">Ordinary annuity</span></span> |
| <span data-ttu-id="ef610-203">Intervall för sammanslagning</span><span class="sxs-lookup"><span data-stu-id="ef610-203">Compounding interval</span></span>       | <span data-ttu-id="ef610-204">Månatlig</span><span class="sxs-lookup"><span data-stu-id="ef610-204">Monthly</span></span>          |

<span data-ttu-id="ef610-205">**Fliken Betalningsplanrader**</span><span class="sxs-lookup"><span data-stu-id="ef610-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="ef610-206">Fält</span><span class="sxs-lookup"><span data-stu-id="ef610-206">Field</span></span>             | <span data-ttu-id="ef610-207">Värde</span><span class="sxs-lookup"><span data-stu-id="ef610-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="ef610-208">Startdatum</span><span class="sxs-lookup"><span data-stu-id="ef610-208">Start date</span></span>        | <span data-ttu-id="ef610-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="ef610-209">1/1/2020</span></span>   |
| <span data-ttu-id="ef610-210">Periodintervall</span><span class="sxs-lookup"><span data-stu-id="ef610-210">Period interval</span></span>   | <span data-ttu-id="ef610-211">Månader</span><span class="sxs-lookup"><span data-stu-id="ef610-211">Months</span></span>     |
| <span data-ttu-id="ef610-212">Perioder</span><span class="sxs-lookup"><span data-stu-id="ef610-212">Periods</span></span>           | <span data-ttu-id="ef610-213">24</span><span class="sxs-lookup"><span data-stu-id="ef610-213">24</span></span>         |
| <span data-ttu-id="ef610-214">Slutdatum</span><span class="sxs-lookup"><span data-stu-id="ef610-214">End date</span></span>          | <span data-ttu-id="ef610-215">12/31/2020</span><span class="sxs-lookup"><span data-stu-id="ef610-215">12/31/2020</span></span> |
| <span data-ttu-id="ef610-216">Lönefrekvens</span><span class="sxs-lookup"><span data-stu-id="ef610-216">Payment frequency</span></span> | <span data-ttu-id="ef610-217">Månatlig</span><span class="sxs-lookup"><span data-stu-id="ef610-217">Monthly</span></span>    |
| <span data-ttu-id="ef610-218">Betalningsbelopp</span><span class="sxs-lookup"><span data-stu-id="ef610-218">Payment amount</span></span>    | <span data-ttu-id="ef610-219">1 000</span><span class="sxs-lookup"><span data-stu-id="ef610-219">1,000</span></span>      |

<span data-ttu-id="ef610-220">Om du vill redovisa denna leasing inom två ramverk använder du ett aktuellt bokföringsskikt och ett anpassat bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="ef610-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="ef610-221">Följande tabell visar ett exempel på varje journalpost som måste visa ekonomin rättvist enligt respektive rapporteringsstandard.</span><span class="sxs-lookup"><span data-stu-id="ef610-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="ef610-222">En detaljerad beskrivning av varje journalpost för den första månaden av leasingen tillhandahålls efteråt.</span><span class="sxs-lookup"><span data-stu-id="ef610-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="ef610-223">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="ef610-224">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="ef610-225">Lagstadgad räkenskapsbok (aktuellt skikt)</span><span class="sxs-lookup"><span data-stu-id="ef610-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ef610-226">Summa aktuellt skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-226">Current layer total</span></span></th>
<th><span data-ttu-id="ef610-227">Återföringsbok (anpassat skikt)</span><span class="sxs-lookup"><span data-stu-id="ef610-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="ef610-228">IFRS 16-bok (anpassat skikt)</span><span class="sxs-lookup"><span data-stu-id="ef610-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ef610-229">Summa aktuellt skikt + anpassat skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ef610-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="ef610-230">JE-100</span></span></th>
<th><span data-ttu-id="ef610-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="ef610-231">JE-110</span></span></th>
<th><span data-ttu-id="ef610-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="ef610-232">JE-120</span></span></th>
<th><span data-ttu-id="ef610-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="ef610-233">JE-130</span></span></th>
<th><span data-ttu-id="ef610-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="ef610-234">JE-140</span></span></th>
<th><span data-ttu-id="ef610-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="ef610-235">JE-150</span></span></th>
<th><span data-ttu-id="ef610-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="ef610-236">JE-160</span></span></th>
<th><span data-ttu-id="ef610-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="ef610-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ef610-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ef610-246">1</span><span class="sxs-lookup"><span data-stu-id="ef610-246">1</span></span></td>
<td><span data-ttu-id="ef610-247">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-247">Lease expense</span></span></td>
<td><span data-ttu-id="ef610-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-249">1,000.00</span></span></td>
<td><span data-ttu-id="ef610-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ef610-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-251">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-252">2</span><span class="sxs-lookup"><span data-stu-id="ef610-252">2</span></span></td>
<td><span data-ttu-id="ef610-253">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="ef610-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-254">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-255">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-256">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-257">3</span><span class="sxs-lookup"><span data-stu-id="ef610-257">3</span></span></td>
<td><span data-ttu-id="ef610-258">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-259">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-260">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-261">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-262">4</span><span class="sxs-lookup"><span data-stu-id="ef610-262">4</span></span></td>
<td><span data-ttu-id="ef610-263">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-263">Clearing account</span></span></td>
<td><span data-ttu-id="ef610-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ef610-264">-1,000.00</span></span></td>
<td><span data-ttu-id="ef610-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-266">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-266">0.00</span></span></td>
<td><span data-ttu-id="ef610-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ef610-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-269">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-270">5</span><span class="sxs-lookup"><span data-stu-id="ef610-270">5</span></span></td>
<td><span data-ttu-id="ef610-271">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="ef610-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-272">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-272">-1,008.00</span></span></td>
<td><span data-ttu-id="ef610-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ef610-273">1,008.00</span></span></td>
<td><span data-ttu-id="ef610-274">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-275">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-276">6</span><span class="sxs-lookup"><span data-stu-id="ef610-276">6</span></span></td>
<td><span data-ttu-id="ef610-277">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="ef610-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-278">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="ef610-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ef610-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-281">7</span><span class="sxs-lookup"><span data-stu-id="ef610-281">7</span></span></td>
<td><span data-ttu-id="ef610-282">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-283">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="ef610-284">-22,794.00</span></span></td>
<td><span data-ttu-id="ef610-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-285">1,000.00</span></span></td>
<td><span data-ttu-id="ef610-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="ef610-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="ef610-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-288">8</span><span class="sxs-lookup"><span data-stu-id="ef610-288">8</span></span></td>
<td><span data-ttu-id="ef610-289">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-290">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-291">94.97</span><span class="sxs-lookup"><span data-stu-id="ef610-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-292">94.97</span><span class="sxs-lookup"><span data-stu-id="ef610-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-293">9</span><span class="sxs-lookup"><span data-stu-id="ef610-293">9</span></span></td>
<td><span data-ttu-id="ef610-294">Kontanter</span><span class="sxs-lookup"><span data-stu-id="ef610-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-295">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-295">-1,008.00</span></span></td>
<td><span data-ttu-id="ef610-296">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-297">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-298">10</span><span class="sxs-lookup"><span data-stu-id="ef610-298">10</span></span></td>
<td><span data-ttu-id="ef610-299">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-300">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-301">949.75</span><span class="sxs-lookup"><span data-stu-id="ef610-301">949.75</span></span></td>
<td><span data-ttu-id="ef610-302">949.75</span><span class="sxs-lookup"><span data-stu-id="ef610-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-303">11</span><span class="sxs-lookup"><span data-stu-id="ef610-303">11</span></span></td>
<td><span data-ttu-id="ef610-304">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-305">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="ef610-306">-949.75</span></span></td>
<td><span data-ttu-id="ef610-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="ef610-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ef610-308">Som tabellen ovan visar måste tre böcker rapportera enligt både lagstadgad rapportering och IFRS-rapportering.</span><span class="sxs-lookup"><span data-stu-id="ef610-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="ef610-309">Den lagstadgade boken registrerar leasingbetalningen enligt reglerna för kontantredovisning enligt det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="ef610-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="ef610-310">Den lagstadgade återföringsboken återför de lagstadgade journalposterna.</span><span class="sxs-lookup"><span data-stu-id="ef610-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="ef610-311">IFRS 16-boken skapar de journalposter som krävs enligt IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="ef610-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="ef610-312">Du behöver bara ange en leasing en gång.</span><span class="sxs-lookup"><span data-stu-id="ef610-312">You must enter a lease only one time.</span></span> <span data-ttu-id="ef610-313">Du kan sedan öppna sidan **Böcker** för att visa du alla böcker som är associerade till leasingen.</span><span class="sxs-lookup"><span data-stu-id="ef610-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="ef610-314">När du skapar böckerna måste alla tre vara associerade med samma leasingpost.</span><span class="sxs-lookup"><span data-stu-id="ef610-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="ef610-315">Den första journalposten registrerar leasingkostnaden enligt den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="ef610-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="ef610-316">Du kan skapa betalningarna antingen i en batch eller genom att välja betalningsplanen i den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="ef610-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="ef610-317">I det här exemplet skapas följande journalpost för den lagstadgade boken från betalningsplanen.</span><span class="sxs-lookup"><span data-stu-id="ef610-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="ef610-318">Leasingbetalning – 1/31/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="ef610-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="ef610-319">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-319">Account type</span></span> | <span data-ttu-id="ef610-320">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-320">Account number</span></span> | <span data-ttu-id="ef610-321">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-321">Layer</span></span>   | <span data-ttu-id="ef610-322">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-322">Account description</span></span> | <span data-ttu-id="ef610-323">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-323">Debit</span></span>    | <span data-ttu-id="ef610-324">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ef610-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-325">Ledger</span></span>       | <span data-ttu-id="ef610-326">1</span><span class="sxs-lookup"><span data-stu-id="ef610-326">1</span></span>              | <span data-ttu-id="ef610-327">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-327">Current</span></span> | <span data-ttu-id="ef610-328">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-328">Lease expense</span></span>       | <span data-ttu-id="ef610-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-329">1,000.00</span></span> |          |
| <span data-ttu-id="ef610-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-330">Ledger</span></span>       | <span data-ttu-id="ef610-331">4</span><span class="sxs-lookup"><span data-stu-id="ef610-331">4</span></span>              | <span data-ttu-id="ef610-332">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-332">Current</span></span> | <span data-ttu-id="ef610-333">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-333">Clearing account</span></span>    |          | <span data-ttu-id="ef610-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-334">1,000.00</span></span> |

<span data-ttu-id="ef610-335">En ansvarig för leverantörsreskontra använder Dynamics 365-standardfunktioner för att skapa en faktura för att betala för leasingen utanför tillgångsleasing.</span><span class="sxs-lookup"><span data-stu-id="ef610-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="ef610-336">I stället för att välja **Leasingkostnad** som debetkonto väljer leverantörsreskontraansvarig ett clearingkonto för att generera följande post.</span><span class="sxs-lookup"><span data-stu-id="ef610-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="ef610-337">AP-process – 1/31/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="ef610-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="ef610-338">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-338">Account type</span></span> | <span data-ttu-id="ef610-339">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-339">Account number</span></span> | <span data-ttu-id="ef610-340">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-340">Layer</span></span>   | <span data-ttu-id="ef610-341">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-341">Account description</span></span> | <span data-ttu-id="ef610-342">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-342">Debit</span></span>    | <span data-ttu-id="ef610-343">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ef610-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-344">Ledger</span></span>       | <span data-ttu-id="ef610-345">4</span><span class="sxs-lookup"><span data-stu-id="ef610-345">4</span></span>              | <span data-ttu-id="ef610-346">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-346">Current</span></span> | <span data-ttu-id="ef610-347">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-347">Clearing account</span></span>    | <span data-ttu-id="ef610-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-348">1,000.00</span></span> |          |
| <span data-ttu-id="ef610-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-349">Ledger</span></span>       | <span data-ttu-id="ef610-350">2</span><span class="sxs-lookup"><span data-stu-id="ef610-350">2</span></span>              | <span data-ttu-id="ef610-351">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-351">Current</span></span> | <span data-ttu-id="ef610-352">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="ef610-352">Bank fee</span></span>            | <span data-ttu-id="ef610-353">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-353">3.00</span></span>     |          |
| <span data-ttu-id="ef610-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-354">Ledger</span></span>       | <span data-ttu-id="ef610-355">3</span><span class="sxs-lookup"><span data-stu-id="ef610-355">3</span></span>              | <span data-ttu-id="ef610-356">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-356">Current</span></span> | <span data-ttu-id="ef610-357">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-357">VAT expense</span></span>         | <span data-ttu-id="ef610-358">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-358">5.00</span></span>     |          |
| <span data-ttu-id="ef610-359">Leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-359">Vendor</span></span>       | <span data-ttu-id="ef610-360">5</span><span class="sxs-lookup"><span data-stu-id="ef610-360">5</span></span>              | <span data-ttu-id="ef610-361">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-361">Current</span></span> | <span data-ttu-id="ef610-362">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="ef610-362">Accounts payable</span></span>    |          | <span data-ttu-id="ef610-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ef610-363">1,008.00</span></span> |

<span data-ttu-id="ef610-364">När utdraget utfärdas till leverantören följer du den vanliga betalningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ef610-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="ef610-365">Under den här processen skapas följande journalpost.</span><span class="sxs-lookup"><span data-stu-id="ef610-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="ef610-366">Kontantbetalning – 1/31/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="ef610-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="ef610-367">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-367">Account type</span></span> | <span data-ttu-id="ef610-368">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-368">Account number</span></span> | <span data-ttu-id="ef610-369">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-369">Layer</span></span>   | <span data-ttu-id="ef610-370">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-370">Account description</span></span> | <span data-ttu-id="ef610-371">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-371">Debit</span></span>    | <span data-ttu-id="ef610-372">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ef610-373">Leverantör</span><span class="sxs-lookup"><span data-stu-id="ef610-373">Vendor</span></span>       | <span data-ttu-id="ef610-374">5</span><span class="sxs-lookup"><span data-stu-id="ef610-374">5</span></span>              | <span data-ttu-id="ef610-375">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-375">Current</span></span> | <span data-ttu-id="ef610-376">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="ef610-376">Accounts Payable</span></span>    | <span data-ttu-id="ef610-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ef610-377">1,008.00</span></span> |          |
| <span data-ttu-id="ef610-378">Bank</span><span class="sxs-lookup"><span data-stu-id="ef610-378">Bank</span></span>         | <span data-ttu-id="ef610-379">9</span><span class="sxs-lookup"><span data-stu-id="ef610-379">9</span></span>              | <span data-ttu-id="ef610-380">Aktuella</span><span class="sxs-lookup"><span data-stu-id="ef610-380">Current</span></span> | <span data-ttu-id="ef610-381">Kontanter</span><span class="sxs-lookup"><span data-stu-id="ef610-381">Cash</span></span>                |          | <span data-ttu-id="ef610-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ef610-382">1,008.00</span></span> |

<span data-ttu-id="ef610-383">I det här skedet har du rapporterat den här leasingen fullständigt enligt lagstadgade rapporteringsbehov och kan generera en råbalans med hjälp av det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="ef610-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="ef610-384">Systemet returnerar en råbalans med följande siffror.</span><span class="sxs-lookup"><span data-stu-id="ef610-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="ef610-385">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="ef610-386">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="ef610-387">Lagstadgad räkenskapsbok (aktuellt skikt)</span><span class="sxs-lookup"><span data-stu-id="ef610-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ef610-388">Summa aktuellt skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ef610-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="ef610-389">JE-100</span></span></th>
<th><span data-ttu-id="ef610-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="ef610-390">JE-110</span></span></th>
<th><span data-ttu-id="ef610-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="ef610-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ef610-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ef610-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ef610-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ef610-395">1</span><span class="sxs-lookup"><span data-stu-id="ef610-395">1</span></span></td>
<td><span data-ttu-id="ef610-396">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-396">Lease expense</span></span></td>
<td><span data-ttu-id="ef610-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-399">2</span><span class="sxs-lookup"><span data-stu-id="ef610-399">2</span></span></td>
<td><span data-ttu-id="ef610-400">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="ef610-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-401">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-402">3.00</span><span class="sxs-lookup"><span data-stu-id="ef610-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-403">3</span><span class="sxs-lookup"><span data-stu-id="ef610-403">3</span></span></td>
<td><span data-ttu-id="ef610-404">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-405">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-406">5.00</span><span class="sxs-lookup"><span data-stu-id="ef610-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-407">4</span><span class="sxs-lookup"><span data-stu-id="ef610-407">4</span></span></td>
<td><span data-ttu-id="ef610-408">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-408">Clearing account</span></span></td>
<td><span data-ttu-id="ef610-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ef610-409">-1,000.00</span></span></td>
<td><span data-ttu-id="ef610-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-411">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-412">5</span><span class="sxs-lookup"><span data-stu-id="ef610-412">5</span></span></td>
<td><span data-ttu-id="ef610-413">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="ef610-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="ef610-414">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-414">-1,008.00</span></span></td>
<td><span data-ttu-id="ef610-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ef610-415">1,008.00</span></span></td>
<td><span data-ttu-id="ef610-416">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-417">6</span><span class="sxs-lookup"><span data-stu-id="ef610-417">6</span></span></td>
<td><span data-ttu-id="ef610-418">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="ef610-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-419">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-420">7</span><span class="sxs-lookup"><span data-stu-id="ef610-420">7</span></span></td>
<td><span data-ttu-id="ef610-421">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-422">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-423">8</span><span class="sxs-lookup"><span data-stu-id="ef610-423">8</span></span></td>
<td><span data-ttu-id="ef610-424">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-425">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-426">9</span><span class="sxs-lookup"><span data-stu-id="ef610-426">9</span></span></td>
<td><span data-ttu-id="ef610-427">Kontanter</span><span class="sxs-lookup"><span data-stu-id="ef610-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-428">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-428">-1,008.00</span></span></td>
<td><span data-ttu-id="ef610-429">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="ef610-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-430">10</span><span class="sxs-lookup"><span data-stu-id="ef610-430">10</span></span></td>
<td><span data-ttu-id="ef610-431">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-432">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ef610-433">11</span><span class="sxs-lookup"><span data-stu-id="ef610-433">11</span></span></td>
<td><span data-ttu-id="ef610-434">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ef610-435">0,00</span><span class="sxs-lookup"><span data-stu-id="ef610-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ef610-436">Om du vill använda IFRS 16 siffror för att köra samma råbalans måste de lagstadgade redovisningsjournalposterna återföras och IFRS 16-journalposterna måste bokföras.</span><span class="sxs-lookup"><span data-stu-id="ef610-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="ef610-437">För att återföra de lagstadgade journalposterna inkluderar det här exemplet en lagstadgad återföringsbok som har samma inställningar som den lagstadgade boken men en motsatt bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="ef610-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="ef610-438">Till exempel, den lagstadgade boken *debiterade* ett konto för leasingkostnader, men återföringsboken kommer att *kreditera* det här kontot.</span><span class="sxs-lookup"><span data-stu-id="ef610-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="ef610-439">Dessa relationer är lätta att definiera i bokföringskontona för tillgångsleasing på sidan med **parametrar för tillgångsleasing** (**Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**).</span><span class="sxs-lookup"><span data-stu-id="ef610-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="ef610-440">När samma process som användes för den lagstadgade boken används för återföringsboken, skapas följande journalpost.</span><span class="sxs-lookup"><span data-stu-id="ef610-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="ef610-441">Skillnaden är att återföringsboken bokför återföringstransaktionerna från den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="ef610-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="ef610-442">Återföringsposterna görs också i det anpassade skiktet.</span><span class="sxs-lookup"><span data-stu-id="ef610-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="ef610-443">När en råbalans körs på det aktuella skiktet inkluderas inte återföringsjournalposterna.</span><span class="sxs-lookup"><span data-stu-id="ef610-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="ef610-444">Leasingbetalning – 1/31/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="ef610-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="ef610-445">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-445">Account type</span></span> | <span data-ttu-id="ef610-446">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-446">Account number</span></span> | <span data-ttu-id="ef610-447">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-447">Layer</span></span>  | <span data-ttu-id="ef610-448">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-448">Account description</span></span> | <span data-ttu-id="ef610-449">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-449">Debit</span></span>    | <span data-ttu-id="ef610-450">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="ef610-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-451">Ledger</span></span>       | <span data-ttu-id="ef610-452">4</span><span class="sxs-lookup"><span data-stu-id="ef610-452">4</span></span>              | <span data-ttu-id="ef610-453">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-453">Custom</span></span> | <span data-ttu-id="ef610-454">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-454">Clearing account</span></span>    | <span data-ttu-id="ef610-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-455">1,000.00</span></span> |          |
| <span data-ttu-id="ef610-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-456">Ledger</span></span>       | <span data-ttu-id="ef610-457">1</span><span class="sxs-lookup"><span data-stu-id="ef610-457">1</span></span>              | <span data-ttu-id="ef610-458">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-458">Custom</span></span> | <span data-ttu-id="ef610-459">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-459">Lease expense</span></span>       |          | <span data-ttu-id="ef610-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-460">1,000.00</span></span> |

<span data-ttu-id="ef610-461">Nu när du har eliminerat lagstadgade journalposter ska du bokföras alla de journalposter som IFRS 16 kräver i IFRS 16-boken.</span><span class="sxs-lookup"><span data-stu-id="ef610-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="ef610-462">Dessa poster inkluderar den första redovisningen av tillgången med nyttjanderätt och skulden, samt posten med ränta och avskrivning.</span><span class="sxs-lookup"><span data-stu-id="ef610-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="ef610-463">Första redovisningstillfälle – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="ef610-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="ef610-464">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-464">Account type</span></span> | <span data-ttu-id="ef610-465">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-465">Account number</span></span> | <span data-ttu-id="ef610-466">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-466">Layer</span></span>  | <span data-ttu-id="ef610-467">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-467">Account description</span></span>      | <span data-ttu-id="ef610-468">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-468">Debit</span></span>     | <span data-ttu-id="ef610-469">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="ef610-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-470">Ledger</span></span>       | <span data-ttu-id="ef610-471">6</span><span class="sxs-lookup"><span data-stu-id="ef610-471">6</span></span>              | <span data-ttu-id="ef610-472">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-472">Custom</span></span> | <span data-ttu-id="ef610-473">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="ef610-473">ROU Asset</span></span>                | <span data-ttu-id="ef610-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ef610-474">22,793.90</span></span> |           |
| <span data-ttu-id="ef610-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-475">Ledger</span></span>       | <span data-ttu-id="ef610-476">7</span><span class="sxs-lookup"><span data-stu-id="ef610-476">7</span></span>              | <span data-ttu-id="ef610-477">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-477">Custom</span></span> | <span data-ttu-id="ef610-478">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-478">Finance lease obligation</span></span> |           | <span data-ttu-id="ef610-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ef610-479">22,793.90</span></span> |

<span data-ttu-id="ef610-480">Leasingbetalningen bokförs som övriga leasingbetalningar.</span><span class="sxs-lookup"><span data-stu-id="ef610-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="ef610-481">Anledningen till att du använder clearingkontot är att säkerställa att kontanter endast krediteras en gång.</span><span class="sxs-lookup"><span data-stu-id="ef610-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="ef610-482">Leasingbetalning – 1/31/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="ef610-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="ef610-483">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-483">Account type</span></span> | <span data-ttu-id="ef610-484">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-484">Account number</span></span> | <span data-ttu-id="ef610-485">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-485">Layer</span></span>  | <span data-ttu-id="ef610-486">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-486">Account description</span></span>      | <span data-ttu-id="ef610-487">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-487">Debit</span></span>    | <span data-ttu-id="ef610-488">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="ef610-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-489">Ledger</span></span>       | <span data-ttu-id="ef610-490">7</span><span class="sxs-lookup"><span data-stu-id="ef610-490">7</span></span>              | <span data-ttu-id="ef610-491">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-491">Custom</span></span> | <span data-ttu-id="ef610-492">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-492">Finance lease obligation</span></span> | <span data-ttu-id="ef610-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-493">1,000.00</span></span> |          |
| <span data-ttu-id="ef610-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-494">Ledger</span></span>       | <span data-ttu-id="ef610-495">4</span><span class="sxs-lookup"><span data-stu-id="ef610-495">4</span></span>              | <span data-ttu-id="ef610-496">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-496">Custom</span></span> | <span data-ttu-id="ef610-497">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-497">Clearing account</span></span>         |          | <span data-ttu-id="ef610-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ef610-498">1,000.00</span></span> |

<span data-ttu-id="ef610-499">Journalposten för räntekostnad genereras från planen för amortering av skulder.</span><span class="sxs-lookup"><span data-stu-id="ef610-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="ef610-500">Räntekostnad – 1/31/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="ef610-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="ef610-501">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-501">Account type</span></span> | <span data-ttu-id="ef610-502">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-502">Account number</span></span> | <span data-ttu-id="ef610-503">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-503">Layer</span></span>  | <span data-ttu-id="ef610-504">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-504">Account description</span></span>      | <span data-ttu-id="ef610-505">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-505">Debit</span></span> | <span data-ttu-id="ef610-506">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="ef610-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-507">Ledger</span></span>       | <span data-ttu-id="ef610-508">8</span><span class="sxs-lookup"><span data-stu-id="ef610-508">8</span></span>              | <span data-ttu-id="ef610-509">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-509">Custom</span></span> | <span data-ttu-id="ef610-510">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-510">Interest expense</span></span>         | <span data-ttu-id="ef610-511">94.97</span><span class="sxs-lookup"><span data-stu-id="ef610-511">94.97</span></span> |        |
| <span data-ttu-id="ef610-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-512">Ledger</span></span>       | <span data-ttu-id="ef610-513">7</span><span class="sxs-lookup"><span data-stu-id="ef610-513">7</span></span>              | <span data-ttu-id="ef610-514">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-514">Custom</span></span> | <span data-ttu-id="ef610-515">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-515">Finance lease obligation</span></span> |       | <span data-ttu-id="ef610-516">94.97</span><span class="sxs-lookup"><span data-stu-id="ef610-516">94.97</span></span>  |

<span data-ttu-id="ef610-517">Journalposten för avskrivningskostnad genereras från planen för avskrivning av tillgång.</span><span class="sxs-lookup"><span data-stu-id="ef610-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="ef610-518">Avskrivningsutgift – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="ef610-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="ef610-519">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="ef610-519">Account type</span></span> | <span data-ttu-id="ef610-520">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="ef610-520">Account number</span></span> | <span data-ttu-id="ef610-521">Skikt</span><span class="sxs-lookup"><span data-stu-id="ef610-521">Layer</span></span>  | <span data-ttu-id="ef610-522">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-522">Account description</span></span>      | <span data-ttu-id="ef610-523">Debet</span><span class="sxs-lookup"><span data-stu-id="ef610-523">Debit</span></span>  | <span data-ttu-id="ef610-524">Kredit</span><span class="sxs-lookup"><span data-stu-id="ef610-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="ef610-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-525">Ledger</span></span>       | <span data-ttu-id="ef610-526">10</span><span class="sxs-lookup"><span data-stu-id="ef610-526">10</span></span>             | <span data-ttu-id="ef610-527">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-527">Custom</span></span> | <span data-ttu-id="ef610-528">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-528">Depreciation expense</span></span>     | <span data-ttu-id="ef610-529">949.75</span><span class="sxs-lookup"><span data-stu-id="ef610-529">949.75</span></span> |        |
| <span data-ttu-id="ef610-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="ef610-530">Ledger</span></span>       | <span data-ttu-id="ef610-531">11</span><span class="sxs-lookup"><span data-stu-id="ef610-531">11</span></span>             | <span data-ttu-id="ef610-532">Anpassat</span><span class="sxs-lookup"><span data-stu-id="ef610-532">Custom</span></span> | <span data-ttu-id="ef610-533">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="ef610-534">949.75</span><span class="sxs-lookup"><span data-stu-id="ef610-534">949.75</span></span> |

<span data-ttu-id="ef610-535">När alla dessa journalposter har skapats och bokförts visas följande "anpassat skikt 1"-värden.</span><span class="sxs-lookup"><span data-stu-id="ef610-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="ef610-536">Lägg märke till att den sista kolumnen innehåller bankavgiften, kostnad för mervärdesskatt (moms) och en minskning av kontanter från det föregående skiktet, men att den inte innehåller lagstadgade rapporteringsjournalposter.</span><span class="sxs-lookup"><span data-stu-id="ef610-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="ef610-537">Därför får du verkliga funktioner för dubbla rapporter.</span><span class="sxs-lookup"><span data-stu-id="ef610-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="ef610-538">I det här skedet behöver företaget bara köra råbalansen och kombinera det aktuella skiktet och det anpassade skiktet för att skapa en IFRS råbalans.</span><span class="sxs-lookup"><span data-stu-id="ef610-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="ef610-539">Kontonr</span><span class="sxs-lookup"><span data-stu-id="ef610-539">Account No</span></span> | <span data-ttu-id="ef610-540">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-540">Description</span></span>              | <span data-ttu-id="ef610-541">Lagstadgad bok\-Aktuellt skikt\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-542">Lagstadgad bok\-Aktuellt skikt\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-543">Lagstadgad bok\-Aktuellt skikt\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-544">Aktuellt skikt \- Summa</span><span class="sxs-lookup"><span data-stu-id="ef610-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="ef610-545">Återföringsbok\-Anpassat skikt\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-546">IFRS 16-bok\-Anpassat skikt\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-547">IFRS 16-bok\-Anpassat skikt\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-548">IFRS 16-bok\-Anpassat skikt\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-549">IFRS 16-bok\-Anpassat skikt\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ef610-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="ef610-550">Anpassat skikt \+ Aktuellt skikt \- Summa</span><span class="sxs-lookup"><span data-stu-id="ef610-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="ef610-551">1</span><span class="sxs-lookup"><span data-stu-id="ef610-551">1</span></span>          | <span data-ttu-id="ef610-552">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-552">Lease expense</span></span>            | <span data-ttu-id="ef610-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="ef610-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-554">1,000\.00</span></span>               |   | <span data-ttu-id="ef610-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="ef610-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="ef610-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-556">0\.00</span></span>                                   |
| <span data-ttu-id="ef610-557">2</span><span class="sxs-lookup"><span data-stu-id="ef610-557">2</span></span>          | <span data-ttu-id="ef610-558">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="ef610-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="ef610-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="ef610-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ef610-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-561">3\.00</span></span>                                   |
| <span data-ttu-id="ef610-562">3</span><span class="sxs-lookup"><span data-stu-id="ef610-562">3</span></span>          | <span data-ttu-id="ef610-563">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="ef610-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="ef610-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ef610-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-566">5\.00</span></span>                                   |
| <span data-ttu-id="ef610-567">4</span><span class="sxs-lookup"><span data-stu-id="ef610-567">4</span></span>          | <span data-ttu-id="ef610-568">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="ef610-568">Clearing account</span></span>         | <span data-ttu-id="ef610-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="ef610-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="ef610-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-571">0\.00</span></span>                   |   | <span data-ttu-id="ef610-572">1 000</span><span class="sxs-lookup"><span data-stu-id="ef610-572">1,000</span></span>                                           |                                                | <span data-ttu-id="ef610-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="ef610-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="ef610-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-574">0\.00</span></span>                                   |
| <span data-ttu-id="ef610-575">5</span><span class="sxs-lookup"><span data-stu-id="ef610-575">5</span></span>          | <span data-ttu-id="ef610-576">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="ef610-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="ef610-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="ef610-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-578">1,008\.00</span></span>                                         | <span data-ttu-id="ef610-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ef610-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-580">0\.00</span></span>                                   |
| <span data-ttu-id="ef610-581">6</span><span class="sxs-lookup"><span data-stu-id="ef610-581">6</span></span>          | <span data-ttu-id="ef610-582">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="ef610-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="ef610-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="ef610-584">22,794</span><span class="sxs-lookup"><span data-stu-id="ef610-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="ef610-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="ef610-585">22,793\.90</span></span>                              |
| <span data-ttu-id="ef610-586">7</span><span class="sxs-lookup"><span data-stu-id="ef610-586">7</span></span>          | <span data-ttu-id="ef610-587">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="ef610-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="ef610-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="ef610-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="ef610-589">\-22,794</span></span>                                       | <span data-ttu-id="ef610-590">1 000</span><span class="sxs-lookup"><span data-stu-id="ef610-590">1,000</span></span>                                          | <span data-ttu-id="ef610-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="ef610-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="ef610-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="ef610-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="ef610-593">8</span><span class="sxs-lookup"><span data-stu-id="ef610-593">8</span></span>          | <span data-ttu-id="ef610-594">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="ef610-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="ef610-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="ef610-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="ef610-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="ef610-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="ef610-597">94\.97</span></span>                                  |
| <span data-ttu-id="ef610-598">9</span><span class="sxs-lookup"><span data-stu-id="ef610-598">9</span></span>          | <span data-ttu-id="ef610-599">Kontanter</span><span class="sxs-lookup"><span data-stu-id="ef610-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="ef610-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="ef610-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ef610-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="ef610-603">10</span><span class="sxs-lookup"><span data-stu-id="ef610-603">10</span></span>         | <span data-ttu-id="ef610-604">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="ef610-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="ef610-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="ef610-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="ef610-606">949\.75</span></span>                                        | <span data-ttu-id="ef610-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="ef610-607">949\.75</span></span>                                 |
| <span data-ttu-id="ef610-608">11</span><span class="sxs-lookup"><span data-stu-id="ef610-608">11</span></span>         | <span data-ttu-id="ef610-609">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="ef610-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="ef610-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="ef610-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="ef610-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="ef610-611">\-949\.75</span></span>                                      | <span data-ttu-id="ef610-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="ef610-612">\-949\.75</span></span>                               |


