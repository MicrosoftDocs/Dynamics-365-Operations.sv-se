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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448194"
---
# <a name="dual-reporting"></a><span data-ttu-id="b331f-103">Dubbel rapportering</span><span class="sxs-lookup"><span data-stu-id="b331f-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b331f-104">I det här avsnittet får du hjälp med ett exempel som visar hur du kan uppfylla kraven för både IFRS-rapportering (International Financial Reporting Standard) och lagstadgad rapportering i Tillgångsleasing.</span><span class="sxs-lookup"><span data-stu-id="b331f-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="b331f-105">Det är viktigt att känna till bokföringsskikt i Microsoft Dynamics 365 Finance och det gör att exemplet blir lättare att förstå.</span><span class="sxs-lookup"><span data-stu-id="b331f-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="b331f-106">Exempel</span><span class="sxs-lookup"><span data-stu-id="b331f-106">Example</span></span>

<span data-ttu-id="b331f-107">I följande exempel redovisas en leasing enligt italiensk lagstadgad rapportering med hjälp av både kontantmetoden och IFRS-rapporteringsmetoder.</span><span class="sxs-lookup"><span data-stu-id="b331f-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="b331f-108">Företaget måste upprätta tre räkenskapsböcker för både de italienska lagstadgade kraven och IFRS 16-kraven.</span><span class="sxs-lookup"><span data-stu-id="b331f-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="b331f-109">En bok krävs för IFRS 16, en bok krävs för lagstadgade krav, och en bok krävs för att automatiskt återföra lagstadgade bokföringar.</span><span class="sxs-lookup"><span data-stu-id="b331f-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="b331f-110">Räkenskapsböckerna ställs in på det sätt som visas i följande tabeller.</span><span class="sxs-lookup"><span data-stu-id="b331f-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="b331f-111">**IFRS 16-räkenskapsbok**</span><span class="sxs-lookup"><span data-stu-id="b331f-111">**IFRS 16 book**</span></span>

<span data-ttu-id="b331f-112">IFRS 16-boken har ställts in så att den överensstämmer med IFRS 16-redovisningsstandarden.</span><span class="sxs-lookup"><span data-stu-id="b331f-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="b331f-113">Alla transaktioner som bokförs i den här boken kommer att bokföras i ett anpassat skikt.</span><span class="sxs-lookup"><span data-stu-id="b331f-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="b331f-114">Namn</span><span class="sxs-lookup"><span data-stu-id="b331f-114">Name</span></span>                                    | <span data-ttu-id="b331f-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="b331f-116">Typ av bok</span><span class="sxs-lookup"><span data-stu-id="b331f-116">Book type</span></span>                               | <span data-ttu-id="b331f-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="b331f-117">IFRS 16</span></span>        |
| <span data-ttu-id="b331f-118">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-118">Book description</span></span>                        | <span data-ttu-id="b331f-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="b331f-119">IFRS 16</span></span>        |
| <span data-ttu-id="b331f-120">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="b331f-120">Posting Layer</span></span>                           | <span data-ttu-id="b331f-121">Anpassat skikt 1</span><span class="sxs-lookup"><span data-stu-id="b331f-121">Custom layer 1</span></span> |
| <span data-ttu-id="b331f-122">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="b331f-122">Lease Type</span></span>                              | <span data-ttu-id="b331f-123">Finance</span><span class="sxs-lookup"><span data-stu-id="b331f-123">Finance</span></span>        |
| <span data-ttu-id="b331f-124">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="b331f-124">Accounting Framework</span></span>                    | <span data-ttu-id="b331f-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="b331f-125">IFRS 16</span></span>        |
| <span data-ttu-id="b331f-126">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="b331f-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b331f-127">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-127">0.00</span></span>           |
| <span data-ttu-id="b331f-128">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="b331f-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b331f-129">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-129">0.00</span></span>           |
| <span data-ttu-id="b331f-130">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-130">Short-term threshold</span></span>                    | <span data-ttu-id="b331f-131">12</span><span class="sxs-lookup"><span data-stu-id="b331f-131">12</span></span>             |
| <span data-ttu-id="b331f-132">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-132">Low Value Threshold</span></span>                     | <span data-ttu-id="b331f-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-133">5,000.00</span></span>       |
| <span data-ttu-id="b331f-134">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-134">Pay to Vendor</span></span>                           | <span data-ttu-id="b331f-135">Nr</span><span class="sxs-lookup"><span data-stu-id="b331f-135">No</span></span>             |

<span data-ttu-id="b331f-136">**Lagstadgad räkenskapsbok**</span><span class="sxs-lookup"><span data-stu-id="b331f-136">**Statutory book**</span></span>

<span data-ttu-id="b331f-137">Den lagstadgade räkenskapsboken är kontantmetodsbok där företaget redovisar leasingkostnaden som det kontantbelopp som betalas varje månad som hyra.</span><span class="sxs-lookup"><span data-stu-id="b331f-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="b331f-138">Boken skapar inte någon tillgång med nyttjanderätt (ROU) eller leasingskuld.</span><span class="sxs-lookup"><span data-stu-id="b331f-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="b331f-139">Namn</span><span class="sxs-lookup"><span data-stu-id="b331f-139">Name</span></span>                                    | <span data-ttu-id="b331f-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="b331f-141">Typ av bok</span><span class="sxs-lookup"><span data-stu-id="b331f-141">Book type</span></span>                               | <span data-ttu-id="b331f-142">Lagstadgad</span><span class="sxs-lookup"><span data-stu-id="b331f-142">Statutory</span></span>   |
| <span data-ttu-id="b331f-143">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-143">Book description</span></span>                        | <span data-ttu-id="b331f-144">Lokal GAAP</span><span class="sxs-lookup"><span data-stu-id="b331f-144">Local GAAP</span></span>  |
| <span data-ttu-id="b331f-145">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="b331f-145">Posting Layer</span></span>                           | <span data-ttu-id="b331f-146">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-146">Current</span></span>     |
| <span data-ttu-id="b331f-147">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="b331f-147">Lease Type</span></span>                              | <span data-ttu-id="b331f-148">Automatisk</span><span class="sxs-lookup"><span data-stu-id="b331f-148">Automatic</span></span>   |
| <span data-ttu-id="b331f-149">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="b331f-149">Accounting Framework</span></span>                    | <span data-ttu-id="b331f-150">Kontantunderlag</span><span class="sxs-lookup"><span data-stu-id="b331f-150">Cash basis</span></span>  |
| <span data-ttu-id="b331f-151">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="b331f-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b331f-152">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-152">0.00</span></span>        |
| <span data-ttu-id="b331f-153">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="b331f-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b331f-154">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-154">0.00</span></span>        |
| <span data-ttu-id="b331f-155">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-155">Short-term threshold</span></span>                    | <span data-ttu-id="b331f-156">0</span><span class="sxs-lookup"><span data-stu-id="b331f-156">0</span></span>           |
| <span data-ttu-id="b331f-157">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-157">Low Value Threshold</span></span>                     | <span data-ttu-id="b331f-158">0</span><span class="sxs-lookup"><span data-stu-id="b331f-158">0</span></span>           |
| <span data-ttu-id="b331f-159">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-159">Pay to Vendor</span></span>                           | <span data-ttu-id="b331f-160">Nr</span><span class="sxs-lookup"><span data-stu-id="b331f-160">No</span></span>          |

<span data-ttu-id="b331f-161">**Lagstadgad återföringsbok**</span><span class="sxs-lookup"><span data-stu-id="b331f-161">**Statutory reversal book**</span></span>

<span data-ttu-id="b331f-162">Den lagstadgade återföringsboken ställs in på samma sätt som den lagstadgade räkenskapsboken.</span><span class="sxs-lookup"><span data-stu-id="b331f-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="b331f-163">Namn</span><span class="sxs-lookup"><span data-stu-id="b331f-163">Name</span></span>                                    | <span data-ttu-id="b331f-164">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="b331f-165">Boktyp</span><span class="sxs-lookup"><span data-stu-id="b331f-165">Book type</span></span>                               | <span data-ttu-id="b331f-166">Lagstadgad – återföring</span><span class="sxs-lookup"><span data-stu-id="b331f-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="b331f-167">Bokbeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-167">Book description</span></span>                        | <span data-ttu-id="b331f-168">Räkenskapsbok för att återföra den lagstadgade räkenskapsboken</span><span class="sxs-lookup"><span data-stu-id="b331f-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="b331f-169">Bokföringsskikt</span><span class="sxs-lookup"><span data-stu-id="b331f-169">Posting Layer</span></span>                           | <span data-ttu-id="b331f-170">Anpassat skikt 1</span><span class="sxs-lookup"><span data-stu-id="b331f-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="b331f-171">Leasingtyp</span><span class="sxs-lookup"><span data-stu-id="b331f-171">Lease Type</span></span>                              | <span data-ttu-id="b331f-172">Automatisk</span><span class="sxs-lookup"><span data-stu-id="b331f-172">Automatic</span></span>                      |
| <span data-ttu-id="b331f-173">Ramverk för redovisning</span><span class="sxs-lookup"><span data-stu-id="b331f-173">Accounting Framework</span></span>                    | <span data-ttu-id="b331f-174">Kontantunderlag</span><span class="sxs-lookup"><span data-stu-id="b331f-174">Cash basis</span></span>                     |
| <span data-ttu-id="b331f-175">Inställning av leasingperiod/livslängd</span><span class="sxs-lookup"><span data-stu-id="b331f-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="b331f-176">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-176">0.00</span></span>                           |
| <span data-ttu-id="b331f-177">Inställning av aktuellt värde/tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="b331f-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="b331f-178">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-178">0.00</span></span>                           |
| <span data-ttu-id="b331f-179">Korttidströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-179">Short-term threshold</span></span>                    | <span data-ttu-id="b331f-180">0</span><span class="sxs-lookup"><span data-stu-id="b331f-180">0</span></span>                              |
| <span data-ttu-id="b331f-181">Lågvärdeströskel</span><span class="sxs-lookup"><span data-stu-id="b331f-181">Low Value Threshold</span></span>                     | <span data-ttu-id="b331f-182">0</span><span class="sxs-lookup"><span data-stu-id="b331f-182">0</span></span>                              |
| <span data-ttu-id="b331f-183">Betala till leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-183">Pay to Vendor</span></span>                           | <span data-ttu-id="b331f-184">Nr</span><span class="sxs-lookup"><span data-stu-id="b331f-184">No</span></span>                             |

<span data-ttu-id="b331f-185">I det här exemplet har en leasing skapats med följande inställningar på flikarna **Allmänt** och **Betalningsplanrader**.</span><span class="sxs-lookup"><span data-stu-id="b331f-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="b331f-186">**Fliken Allmänt**</span><span class="sxs-lookup"><span data-stu-id="b331f-186">**General tab**</span></span>

| <span data-ttu-id="b331f-187">Fält</span><span class="sxs-lookup"><span data-stu-id="b331f-187">Field</span></span>                      | <span data-ttu-id="b331f-188">Värde</span><span class="sxs-lookup"><span data-stu-id="b331f-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="b331f-189">Marginell låneränta</span><span class="sxs-lookup"><span data-stu-id="b331f-189">Incremental borrowing rate</span></span> | <span data-ttu-id="b331f-190">5 %</span><span class="sxs-lookup"><span data-stu-id="b331f-190">5%</span></span>               |
| <span data-ttu-id="b331f-191">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b331f-191">Commencement date</span></span>          | <span data-ttu-id="b331f-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="b331f-192">1/1/2020</span></span>         |
| <span data-ttu-id="b331f-193">Leasinggrupp</span><span class="sxs-lookup"><span data-stu-id="b331f-193">Lease group</span></span>                | <span data-ttu-id="b331f-194">Byggnader</span><span class="sxs-lookup"><span data-stu-id="b331f-194">Buildings</span></span>        |
| <span data-ttu-id="b331f-195">Leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-195">Vendor</span></span>                     | <span data-ttu-id="b331f-196">1001</span><span class="sxs-lookup"><span data-stu-id="b331f-196">1001</span></span>             |
| <span data-ttu-id="b331f-197">Tillgångens verkliga värde</span><span class="sxs-lookup"><span data-stu-id="b331f-197">Fair value of the asset</span></span>    | <span data-ttu-id="b331f-198">245,000</span><span class="sxs-lookup"><span data-stu-id="b331f-198">245,000</span></span>          |
| <span data-ttu-id="b331f-199">Tillgångens livslängd</span><span class="sxs-lookup"><span data-stu-id="b331f-199">Asset useful life</span></span>          | <span data-ttu-id="b331f-200">120</span><span class="sxs-lookup"><span data-stu-id="b331f-200">120</span></span>              |
| <span data-ttu-id="b331f-201">Typ av annuitet</span><span class="sxs-lookup"><span data-stu-id="b331f-201">Annuity type</span></span>               | <span data-ttu-id="b331f-202">Vanlig annuitet</span><span class="sxs-lookup"><span data-stu-id="b331f-202">Ordinary annuity</span></span> |
| <span data-ttu-id="b331f-203">Intervall för sammanslagning</span><span class="sxs-lookup"><span data-stu-id="b331f-203">Compounding interval</span></span>       | <span data-ttu-id="b331f-204">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b331f-204">Monthly</span></span>          |

<span data-ttu-id="b331f-205">**Fliken Betalningsplanrader**</span><span class="sxs-lookup"><span data-stu-id="b331f-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="b331f-206">Fält</span><span class="sxs-lookup"><span data-stu-id="b331f-206">Field</span></span>             | <span data-ttu-id="b331f-207">Värde</span><span class="sxs-lookup"><span data-stu-id="b331f-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="b331f-208">Startdatum</span><span class="sxs-lookup"><span data-stu-id="b331f-208">Start date</span></span>        | <span data-ttu-id="b331f-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="b331f-209">1/1/2020</span></span>   |
| <span data-ttu-id="b331f-210">Periodintervall</span><span class="sxs-lookup"><span data-stu-id="b331f-210">Period interval</span></span>   | <span data-ttu-id="b331f-211">Månader</span><span class="sxs-lookup"><span data-stu-id="b331f-211">Months</span></span>     |
| <span data-ttu-id="b331f-212">Perioder</span><span class="sxs-lookup"><span data-stu-id="b331f-212">Periods</span></span>           | <span data-ttu-id="b331f-213">24</span><span class="sxs-lookup"><span data-stu-id="b331f-213">24</span></span>         |
| <span data-ttu-id="b331f-214">Slutdatum</span><span class="sxs-lookup"><span data-stu-id="b331f-214">End date</span></span>          | <span data-ttu-id="b331f-215">12/31/2020</span><span class="sxs-lookup"><span data-stu-id="b331f-215">12/31/2020</span></span> |
| <span data-ttu-id="b331f-216">Lönefrekvens</span><span class="sxs-lookup"><span data-stu-id="b331f-216">Payment frequency</span></span> | <span data-ttu-id="b331f-217">Månatlig</span><span class="sxs-lookup"><span data-stu-id="b331f-217">Monthly</span></span>    |
| <span data-ttu-id="b331f-218">Betalningsbelopp</span><span class="sxs-lookup"><span data-stu-id="b331f-218">Payment amount</span></span>    | <span data-ttu-id="b331f-219">1 000</span><span class="sxs-lookup"><span data-stu-id="b331f-219">1,000</span></span>      |

<span data-ttu-id="b331f-220">Om du vill redovisa denna leasing inom två ramverk använder du ett aktuellt bokföringsskikt och ett anpassat bokföringsskikt.</span><span class="sxs-lookup"><span data-stu-id="b331f-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="b331f-221">Följande tabell visar ett exempel på varje journalpost som måste visa ekonomin rättvist enligt respektive rapporteringsstandard.</span><span class="sxs-lookup"><span data-stu-id="b331f-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="b331f-222">En detaljerad beskrivning av varje journalpost för den första månaden av leasingen tillhandahålls efteråt.</span><span class="sxs-lookup"><span data-stu-id="b331f-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="b331f-223">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="b331f-224">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="b331f-225">Lagstadgad räkenskapsbok (aktuellt skikt)</span><span class="sxs-lookup"><span data-stu-id="b331f-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b331f-226">Summa aktuellt skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-226">Current layer total</span></span></th>
<th><span data-ttu-id="b331f-227">Återföringsbok (anpassat skikt)</span><span class="sxs-lookup"><span data-stu-id="b331f-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="b331f-228">IFRS 16-bok (anpassat skikt)</span><span class="sxs-lookup"><span data-stu-id="b331f-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b331f-229">Summa aktuellt skikt + anpassat skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b331f-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="b331f-230">JE-100</span></span></th>
<th><span data-ttu-id="b331f-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="b331f-231">JE-110</span></span></th>
<th><span data-ttu-id="b331f-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="b331f-232">JE-120</span></span></th>
<th><span data-ttu-id="b331f-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="b331f-233">JE-130</span></span></th>
<th><span data-ttu-id="b331f-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="b331f-234">JE-140</span></span></th>
<th><span data-ttu-id="b331f-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="b331f-235">JE-150</span></span></th>
<th><span data-ttu-id="b331f-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="b331f-236">JE-160</span></span></th>
<th><span data-ttu-id="b331f-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="b331f-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b331f-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b331f-246">1</span><span class="sxs-lookup"><span data-stu-id="b331f-246">1</span></span></td>
<td><span data-ttu-id="b331f-247">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-247">Lease expense</span></span></td>
<td><span data-ttu-id="b331f-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-249">1,000.00</span></span></td>
<td><span data-ttu-id="b331f-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="b331f-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-251">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-252">2</span><span class="sxs-lookup"><span data-stu-id="b331f-252">2</span></span></td>
<td><span data-ttu-id="b331f-253">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="b331f-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-254">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-255">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-256">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-257">3</span><span class="sxs-lookup"><span data-stu-id="b331f-257">3</span></span></td>
<td><span data-ttu-id="b331f-258">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-259">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-260">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-261">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-262">4</span><span class="sxs-lookup"><span data-stu-id="b331f-262">4</span></span></td>
<td><span data-ttu-id="b331f-263">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-263">Clearing account</span></span></td>
<td><span data-ttu-id="b331f-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="b331f-264">-1,000.00</span></span></td>
<td><span data-ttu-id="b331f-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-266">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-266">0.00</span></span></td>
<td><span data-ttu-id="b331f-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="b331f-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-269">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-270">5</span><span class="sxs-lookup"><span data-stu-id="b331f-270">5</span></span></td>
<td><span data-ttu-id="b331f-271">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="b331f-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-272">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-272">-1,008.00</span></span></td>
<td><span data-ttu-id="b331f-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b331f-273">1,008.00</span></span></td>
<td><span data-ttu-id="b331f-274">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-275">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-276">6</span><span class="sxs-lookup"><span data-stu-id="b331f-276">6</span></span></td>
<td><span data-ttu-id="b331f-277">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="b331f-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-278">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="b331f-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b331f-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-281">7</span><span class="sxs-lookup"><span data-stu-id="b331f-281">7</span></span></td>
<td><span data-ttu-id="b331f-282">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="b331f-284">-22,794.00</span></span></td>
<td><span data-ttu-id="b331f-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-285">1,000.00</span></span></td>
<td><span data-ttu-id="b331f-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="b331f-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="b331f-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-288">8</span><span class="sxs-lookup"><span data-stu-id="b331f-288">8</span></span></td>
<td><span data-ttu-id="b331f-289">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-290">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-291">94.97</span><span class="sxs-lookup"><span data-stu-id="b331f-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-292">94.97</span><span class="sxs-lookup"><span data-stu-id="b331f-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-293">9</span><span class="sxs-lookup"><span data-stu-id="b331f-293">9</span></span></td>
<td><span data-ttu-id="b331f-294">Kontanter</span><span class="sxs-lookup"><span data-stu-id="b331f-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-295">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-295">-1,008.00</span></span></td>
<td><span data-ttu-id="b331f-296">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-297">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-298">10</span><span class="sxs-lookup"><span data-stu-id="b331f-298">10</span></span></td>
<td><span data-ttu-id="b331f-299">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-300">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-301">949.75</span><span class="sxs-lookup"><span data-stu-id="b331f-301">949.75</span></span></td>
<td><span data-ttu-id="b331f-302">949.75</span><span class="sxs-lookup"><span data-stu-id="b331f-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-303">11</span><span class="sxs-lookup"><span data-stu-id="b331f-303">11</span></span></td>
<td><span data-ttu-id="b331f-304">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-305">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="b331f-306">-949.75</span></span></td>
<td><span data-ttu-id="b331f-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="b331f-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b331f-308">Som tabellen ovan visar måste tre böcker rapportera enligt både lagstadgad rapportering och IFRS-rapportering.</span><span class="sxs-lookup"><span data-stu-id="b331f-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="b331f-309">Den lagstadgade boken registrerar leasingbetalningen enligt reglerna för kontantredovisning enligt det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="b331f-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="b331f-310">Den lagstadgade återföringsboken återför de lagstadgade journalposterna.</span><span class="sxs-lookup"><span data-stu-id="b331f-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="b331f-311">IFRS 16-boken skapar de journalposter som krävs enligt IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="b331f-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="b331f-312">Du behöver bara ange en leasing en gång.</span><span class="sxs-lookup"><span data-stu-id="b331f-312">You must enter a lease only one time.</span></span> <span data-ttu-id="b331f-313">Du kan sedan öppna sidan **Böcker** för att visa du alla böcker som är associerade till leasingen.</span><span class="sxs-lookup"><span data-stu-id="b331f-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="b331f-314">När du skapar böckerna måste alla tre vara associerade med samma leasingpost.</span><span class="sxs-lookup"><span data-stu-id="b331f-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="b331f-315">Den första journalposten registrerar leasingkostnaden enligt den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="b331f-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="b331f-316">Du kan skapa betalningarna antingen i en batch eller genom att välja betalningsplanen i den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="b331f-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="b331f-317">I det här exemplet skapas följande journalpost för den lagstadgade boken från betalningsplanen.</span><span class="sxs-lookup"><span data-stu-id="b331f-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="b331f-318">Leasingbetalning – 1/31/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="b331f-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="b331f-319">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-319">Account type</span></span> | <span data-ttu-id="b331f-320">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-320">Account number</span></span> | <span data-ttu-id="b331f-321">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-321">Layer</span></span>   | <span data-ttu-id="b331f-322">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-322">Account description</span></span> | <span data-ttu-id="b331f-323">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-323">Debit</span></span>    | <span data-ttu-id="b331f-324">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b331f-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-325">Ledger</span></span>       | <span data-ttu-id="b331f-326">1</span><span class="sxs-lookup"><span data-stu-id="b331f-326">1</span></span>              | <span data-ttu-id="b331f-327">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-327">Current</span></span> | <span data-ttu-id="b331f-328">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-328">Lease expense</span></span>       | <span data-ttu-id="b331f-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-329">1,000.00</span></span> |          |
| <span data-ttu-id="b331f-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-330">Ledger</span></span>       | <span data-ttu-id="b331f-331">4</span><span class="sxs-lookup"><span data-stu-id="b331f-331">4</span></span>              | <span data-ttu-id="b331f-332">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-332">Current</span></span> | <span data-ttu-id="b331f-333">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-333">Clearing account</span></span>    |          | <span data-ttu-id="b331f-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-334">1,000.00</span></span> |

<span data-ttu-id="b331f-335">En ansvarig för leverantörsreskontra använder Dynamics 365-standardfunktioner för att skapa en faktura för att betala för leasingen utanför tillgångsleasing.</span><span class="sxs-lookup"><span data-stu-id="b331f-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="b331f-336">I stället för att välja **Leasingkostnad** som debetkonto väljer leverantörsreskontraansvarig ett clearingkonto för att generera följande post.</span><span class="sxs-lookup"><span data-stu-id="b331f-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="b331f-337">AP-process – 1/31/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="b331f-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="b331f-338">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-338">Account type</span></span> | <span data-ttu-id="b331f-339">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-339">Account number</span></span> | <span data-ttu-id="b331f-340">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-340">Layer</span></span>   | <span data-ttu-id="b331f-341">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-341">Account description</span></span> | <span data-ttu-id="b331f-342">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-342">Debit</span></span>    | <span data-ttu-id="b331f-343">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b331f-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-344">Ledger</span></span>       | <span data-ttu-id="b331f-345">4</span><span class="sxs-lookup"><span data-stu-id="b331f-345">4</span></span>              | <span data-ttu-id="b331f-346">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-346">Current</span></span> | <span data-ttu-id="b331f-347">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-347">Clearing account</span></span>    | <span data-ttu-id="b331f-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-348">1,000.00</span></span> |          |
| <span data-ttu-id="b331f-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-349">Ledger</span></span>       | <span data-ttu-id="b331f-350">2</span><span class="sxs-lookup"><span data-stu-id="b331f-350">2</span></span>              | <span data-ttu-id="b331f-351">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-351">Current</span></span> | <span data-ttu-id="b331f-352">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="b331f-352">Bank fee</span></span>            | <span data-ttu-id="b331f-353">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-353">3.00</span></span>     |          |
| <span data-ttu-id="b331f-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-354">Ledger</span></span>       | <span data-ttu-id="b331f-355">3</span><span class="sxs-lookup"><span data-stu-id="b331f-355">3</span></span>              | <span data-ttu-id="b331f-356">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-356">Current</span></span> | <span data-ttu-id="b331f-357">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-357">VAT expense</span></span>         | <span data-ttu-id="b331f-358">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-358">5.00</span></span>     |          |
| <span data-ttu-id="b331f-359">Leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-359">Vendor</span></span>       | <span data-ttu-id="b331f-360">5</span><span class="sxs-lookup"><span data-stu-id="b331f-360">5</span></span>              | <span data-ttu-id="b331f-361">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-361">Current</span></span> | <span data-ttu-id="b331f-362">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="b331f-362">Accounts payable</span></span>    |          | <span data-ttu-id="b331f-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b331f-363">1,008.00</span></span> |

<span data-ttu-id="b331f-364">När utdraget utfärdas till leverantören följer du den vanliga betalningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b331f-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="b331f-365">Under den här processen skapas följande journalpost.</span><span class="sxs-lookup"><span data-stu-id="b331f-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="b331f-366">Kontantbetalning – 1/31/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="b331f-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="b331f-367">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-367">Account type</span></span> | <span data-ttu-id="b331f-368">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-368">Account number</span></span> | <span data-ttu-id="b331f-369">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-369">Layer</span></span>   | <span data-ttu-id="b331f-370">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-370">Account description</span></span> | <span data-ttu-id="b331f-371">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-371">Debit</span></span>    | <span data-ttu-id="b331f-372">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="b331f-373">Leverantör</span><span class="sxs-lookup"><span data-stu-id="b331f-373">Vendor</span></span>       | <span data-ttu-id="b331f-374">5</span><span class="sxs-lookup"><span data-stu-id="b331f-374">5</span></span>              | <span data-ttu-id="b331f-375">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-375">Current</span></span> | <span data-ttu-id="b331f-376">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="b331f-376">Accounts Payable</span></span>    | <span data-ttu-id="b331f-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b331f-377">1,008.00</span></span> |          |
| <span data-ttu-id="b331f-378">Bank</span><span class="sxs-lookup"><span data-stu-id="b331f-378">Bank</span></span>         | <span data-ttu-id="b331f-379">9</span><span class="sxs-lookup"><span data-stu-id="b331f-379">9</span></span>              | <span data-ttu-id="b331f-380">Aktuella</span><span class="sxs-lookup"><span data-stu-id="b331f-380">Current</span></span> | <span data-ttu-id="b331f-381">Kontanter</span><span class="sxs-lookup"><span data-stu-id="b331f-381">Cash</span></span>                |          | <span data-ttu-id="b331f-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b331f-382">1,008.00</span></span> |

<span data-ttu-id="b331f-383">I det här skedet har du rapporterat den här leasingen fullständigt enligt lagstadgade rapporteringsbehov och kan generera en råbalans med hjälp av det aktuella skiktet.</span><span class="sxs-lookup"><span data-stu-id="b331f-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="b331f-384">Systemet returnerar en råbalans med följande siffror.</span><span class="sxs-lookup"><span data-stu-id="b331f-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="b331f-385">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="b331f-386">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="b331f-387">Lagstadgad räkenskapsbok (aktuellt skikt)</span><span class="sxs-lookup"><span data-stu-id="b331f-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="b331f-388">Summa aktuellt skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b331f-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="b331f-389">JE-100</span></span></th>
<th><span data-ttu-id="b331f-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="b331f-390">JE-110</span></span></th>
<th><span data-ttu-id="b331f-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="b331f-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="b331f-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="b331f-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="b331f-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b331f-395">1</span><span class="sxs-lookup"><span data-stu-id="b331f-395">1</span></span></td>
<td><span data-ttu-id="b331f-396">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-396">Lease expense</span></span></td>
<td><span data-ttu-id="b331f-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-399">2</span><span class="sxs-lookup"><span data-stu-id="b331f-399">2</span></span></td>
<td><span data-ttu-id="b331f-400">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="b331f-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-401">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-402">3.00</span><span class="sxs-lookup"><span data-stu-id="b331f-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-403">3</span><span class="sxs-lookup"><span data-stu-id="b331f-403">3</span></span></td>
<td><span data-ttu-id="b331f-404">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-405">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-406">5.00</span><span class="sxs-lookup"><span data-stu-id="b331f-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-407">4</span><span class="sxs-lookup"><span data-stu-id="b331f-407">4</span></span></td>
<td><span data-ttu-id="b331f-408">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-408">Clearing account</span></span></td>
<td><span data-ttu-id="b331f-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="b331f-409">-1,000.00</span></span></td>
<td><span data-ttu-id="b331f-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-411">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-412">5</span><span class="sxs-lookup"><span data-stu-id="b331f-412">5</span></span></td>
<td><span data-ttu-id="b331f-413">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="b331f-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="b331f-414">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-414">-1,008.00</span></span></td>
<td><span data-ttu-id="b331f-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="b331f-415">1,008.00</span></span></td>
<td><span data-ttu-id="b331f-416">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-417">6</span><span class="sxs-lookup"><span data-stu-id="b331f-417">6</span></span></td>
<td><span data-ttu-id="b331f-418">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="b331f-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-419">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-420">7</span><span class="sxs-lookup"><span data-stu-id="b331f-420">7</span></span></td>
<td><span data-ttu-id="b331f-421">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-422">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-423">8</span><span class="sxs-lookup"><span data-stu-id="b331f-423">8</span></span></td>
<td><span data-ttu-id="b331f-424">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-425">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-426">9</span><span class="sxs-lookup"><span data-stu-id="b331f-426">9</span></span></td>
<td><span data-ttu-id="b331f-427">Kontanter</span><span class="sxs-lookup"><span data-stu-id="b331f-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-428">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-428">-1,008.00</span></span></td>
<td><span data-ttu-id="b331f-429">-1 008,00</span><span class="sxs-lookup"><span data-stu-id="b331f-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-430">10</span><span class="sxs-lookup"><span data-stu-id="b331f-430">10</span></span></td>
<td><span data-ttu-id="b331f-431">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-432">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b331f-433">11</span><span class="sxs-lookup"><span data-stu-id="b331f-433">11</span></span></td>
<td><span data-ttu-id="b331f-434">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="b331f-435">0,00</span><span class="sxs-lookup"><span data-stu-id="b331f-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b331f-436">Om du vill använda IFRS 16 siffror för att köra samma råbalans måste de lagstadgade redovisningsjournalposterna återföras och IFRS 16-journalposterna måste bokföras.</span><span class="sxs-lookup"><span data-stu-id="b331f-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="b331f-437">För att återföra de lagstadgade journalposterna inkluderar det här exemplet en lagstadgad återföringsbok som har samma inställningar som den lagstadgade boken men en motsatt bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="b331f-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="b331f-438">Till exempel, den lagstadgade boken *debiterade* ett konto för leasingkostnader, men återföringsboken kommer att *kreditera* det här kontot.</span><span class="sxs-lookup"><span data-stu-id="b331f-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="b331f-439">Dessa relationer är lätta att definiera i bokföringskontona för tillgångsleasing på sidan med **parametrar för tillgångsleasing** (**Leasing av tillgångar \> Konfigurera \> Parametrar för tillgångsleasing**).</span><span class="sxs-lookup"><span data-stu-id="b331f-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="b331f-440">När samma process som användes för den lagstadgade boken används för återföringsboken, skapas följande journalpost.</span><span class="sxs-lookup"><span data-stu-id="b331f-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="b331f-441">Skillnaden är att återföringsboken bokför återföringstransaktionerna från den lagstadgade boken.</span><span class="sxs-lookup"><span data-stu-id="b331f-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="b331f-442">Återföringsposterna görs också i det anpassade skiktet.</span><span class="sxs-lookup"><span data-stu-id="b331f-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="b331f-443">När en råbalans körs på det aktuella skiktet inkluderas inte återföringsjournalposterna.</span><span class="sxs-lookup"><span data-stu-id="b331f-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="b331f-444">Leasingbetalning – 1/31/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="b331f-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="b331f-445">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-445">Account type</span></span> | <span data-ttu-id="b331f-446">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-446">Account number</span></span> | <span data-ttu-id="b331f-447">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-447">Layer</span></span>  | <span data-ttu-id="b331f-448">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-448">Account description</span></span> | <span data-ttu-id="b331f-449">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-449">Debit</span></span>    | <span data-ttu-id="b331f-450">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="b331f-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-451">Ledger</span></span>       | <span data-ttu-id="b331f-452">4</span><span class="sxs-lookup"><span data-stu-id="b331f-452">4</span></span>              | <span data-ttu-id="b331f-453">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-453">Custom</span></span> | <span data-ttu-id="b331f-454">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-454">Clearing account</span></span>    | <span data-ttu-id="b331f-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-455">1,000.00</span></span> |          |
| <span data-ttu-id="b331f-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-456">Ledger</span></span>       | <span data-ttu-id="b331f-457">1</span><span class="sxs-lookup"><span data-stu-id="b331f-457">1</span></span>              | <span data-ttu-id="b331f-458">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-458">Custom</span></span> | <span data-ttu-id="b331f-459">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-459">Lease expense</span></span>       |          | <span data-ttu-id="b331f-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-460">1,000.00</span></span> |

<span data-ttu-id="b331f-461">Nu när du har eliminerat lagstadgade journalposter ska du bokföras alla de journalposter som IFRS 16 kräver i IFRS 16-boken.</span><span class="sxs-lookup"><span data-stu-id="b331f-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="b331f-462">Dessa poster inkluderar den första redovisningen av tillgången med nyttjanderätt och skulden, samt posten med ränta och avskrivning.</span><span class="sxs-lookup"><span data-stu-id="b331f-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="b331f-463">Första redovisningstillfälle – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="b331f-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="b331f-464">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-464">Account type</span></span> | <span data-ttu-id="b331f-465">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-465">Account number</span></span> | <span data-ttu-id="b331f-466">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-466">Layer</span></span>  | <span data-ttu-id="b331f-467">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-467">Account description</span></span>      | <span data-ttu-id="b331f-468">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-468">Debit</span></span>     | <span data-ttu-id="b331f-469">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="b331f-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-470">Ledger</span></span>       | <span data-ttu-id="b331f-471">6</span><span class="sxs-lookup"><span data-stu-id="b331f-471">6</span></span>              | <span data-ttu-id="b331f-472">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-472">Custom</span></span> | <span data-ttu-id="b331f-473">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="b331f-473">ROU Asset</span></span>                | <span data-ttu-id="b331f-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b331f-474">22,793.90</span></span> |           |
| <span data-ttu-id="b331f-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-475">Ledger</span></span>       | <span data-ttu-id="b331f-476">7</span><span class="sxs-lookup"><span data-stu-id="b331f-476">7</span></span>              | <span data-ttu-id="b331f-477">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-477">Custom</span></span> | <span data-ttu-id="b331f-478">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-478">Finance lease obligation</span></span> |           | <span data-ttu-id="b331f-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="b331f-479">22,793.90</span></span> |

<span data-ttu-id="b331f-480">Leasingbetalningen bokförs som övriga leasingbetalningar.</span><span class="sxs-lookup"><span data-stu-id="b331f-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="b331f-481">Anledningen till att du använder clearingkontot är att säkerställa att kontanter endast krediteras en gång.</span><span class="sxs-lookup"><span data-stu-id="b331f-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="b331f-482">Leasingbetalning – 1/31/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="b331f-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="b331f-483">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-483">Account type</span></span> | <span data-ttu-id="b331f-484">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-484">Account number</span></span> | <span data-ttu-id="b331f-485">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-485">Layer</span></span>  | <span data-ttu-id="b331f-486">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-486">Account description</span></span>      | <span data-ttu-id="b331f-487">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-487">Debit</span></span>    | <span data-ttu-id="b331f-488">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="b331f-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-489">Ledger</span></span>       | <span data-ttu-id="b331f-490">7</span><span class="sxs-lookup"><span data-stu-id="b331f-490">7</span></span>              | <span data-ttu-id="b331f-491">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-491">Custom</span></span> | <span data-ttu-id="b331f-492">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-492">Finance lease obligation</span></span> | <span data-ttu-id="b331f-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-493">1,000.00</span></span> |          |
| <span data-ttu-id="b331f-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-494">Ledger</span></span>       | <span data-ttu-id="b331f-495">4</span><span class="sxs-lookup"><span data-stu-id="b331f-495">4</span></span>              | <span data-ttu-id="b331f-496">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-496">Custom</span></span> | <span data-ttu-id="b331f-497">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-497">Clearing account</span></span>         |          | <span data-ttu-id="b331f-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="b331f-498">1,000.00</span></span> |

<span data-ttu-id="b331f-499">Journalposten för räntekostnad genereras från planen för amortering av skulder.</span><span class="sxs-lookup"><span data-stu-id="b331f-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="b331f-500">Räntekostnad – 1/31/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="b331f-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="b331f-501">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-501">Account type</span></span> | <span data-ttu-id="b331f-502">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-502">Account number</span></span> | <span data-ttu-id="b331f-503">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-503">Layer</span></span>  | <span data-ttu-id="b331f-504">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-504">Account description</span></span>      | <span data-ttu-id="b331f-505">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-505">Debit</span></span> | <span data-ttu-id="b331f-506">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="b331f-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-507">Ledger</span></span>       | <span data-ttu-id="b331f-508">8</span><span class="sxs-lookup"><span data-stu-id="b331f-508">8</span></span>              | <span data-ttu-id="b331f-509">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-509">Custom</span></span> | <span data-ttu-id="b331f-510">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-510">Interest expense</span></span>         | <span data-ttu-id="b331f-511">94.97</span><span class="sxs-lookup"><span data-stu-id="b331f-511">94.97</span></span> |        |
| <span data-ttu-id="b331f-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-512">Ledger</span></span>       | <span data-ttu-id="b331f-513">7</span><span class="sxs-lookup"><span data-stu-id="b331f-513">7</span></span>              | <span data-ttu-id="b331f-514">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-514">Custom</span></span> | <span data-ttu-id="b331f-515">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-515">Finance lease obligation</span></span> |       | <span data-ttu-id="b331f-516">94.97</span><span class="sxs-lookup"><span data-stu-id="b331f-516">94.97</span></span>  |

<span data-ttu-id="b331f-517">Journalposten för avskrivningskostnad genereras från planen för avskrivning av tillgång.</span><span class="sxs-lookup"><span data-stu-id="b331f-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="b331f-518">Avskrivningsutgift – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="b331f-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="b331f-519">Kontotyp</span><span class="sxs-lookup"><span data-stu-id="b331f-519">Account type</span></span> | <span data-ttu-id="b331f-520">Kontonummer</span><span class="sxs-lookup"><span data-stu-id="b331f-520">Account number</span></span> | <span data-ttu-id="b331f-521">Skikt</span><span class="sxs-lookup"><span data-stu-id="b331f-521">Layer</span></span>  | <span data-ttu-id="b331f-522">Kontobeskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-522">Account description</span></span>      | <span data-ttu-id="b331f-523">Debet</span><span class="sxs-lookup"><span data-stu-id="b331f-523">Debit</span></span>  | <span data-ttu-id="b331f-524">Kredit</span><span class="sxs-lookup"><span data-stu-id="b331f-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="b331f-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-525">Ledger</span></span>       | <span data-ttu-id="b331f-526">10</span><span class="sxs-lookup"><span data-stu-id="b331f-526">10</span></span>             | <span data-ttu-id="b331f-527">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-527">Custom</span></span> | <span data-ttu-id="b331f-528">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-528">Depreciation expense</span></span>     | <span data-ttu-id="b331f-529">949.75</span><span class="sxs-lookup"><span data-stu-id="b331f-529">949.75</span></span> |        |
| <span data-ttu-id="b331f-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="b331f-530">Ledger</span></span>       | <span data-ttu-id="b331f-531">11</span><span class="sxs-lookup"><span data-stu-id="b331f-531">11</span></span>             | <span data-ttu-id="b331f-532">Anpassat</span><span class="sxs-lookup"><span data-stu-id="b331f-532">Custom</span></span> | <span data-ttu-id="b331f-533">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="b331f-534">949.75</span><span class="sxs-lookup"><span data-stu-id="b331f-534">949.75</span></span> |

<span data-ttu-id="b331f-535">När alla dessa journalposter har skapats och bokförts visas följande "anpassat skikt 1"-värden.</span><span class="sxs-lookup"><span data-stu-id="b331f-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="b331f-536">Lägg märke till att den sista kolumnen innehåller bankavgiften, kostnad för mervärdesskatt (moms) och en minskning av kontanter från det föregående skiktet, men att den inte innehåller lagstadgade rapporteringsjournalposter.</span><span class="sxs-lookup"><span data-stu-id="b331f-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="b331f-537">Därför får du verkliga funktioner för dubbla rapporter.</span><span class="sxs-lookup"><span data-stu-id="b331f-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="b331f-538">I det här skedet behöver företaget bara köra råbalansen och kombinera det aktuella skiktet och det anpassade skiktet för att skapa en IFRS råbalans.</span><span class="sxs-lookup"><span data-stu-id="b331f-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="b331f-539">Kontonr</span><span class="sxs-lookup"><span data-stu-id="b331f-539">Account No</span></span> | <span data-ttu-id="b331f-540">beskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-540">Description</span></span>              | <span data-ttu-id="b331f-541">Lagstadgad bok\-Aktuellt skikt\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-542">Lagstadgad bok\-Aktuellt skikt\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-543">Lagstadgad bok\-Aktuellt skikt\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-544">Aktuellt skikt \- Summa</span><span class="sxs-lookup"><span data-stu-id="b331f-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="b331f-545">Återföringsbok\-Anpassat skikt\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-546">IFRS 16-bok\-Anpassat skikt\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-547">IFRS 16-bok\-Anpassat skikt\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-548">IFRS 16-bok\-Anpassat skikt\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-549">IFRS 16-bok\-Anpassat skikt\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="b331f-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="b331f-550">Anpassat skikt \+ Aktuellt skikt \- Summa</span><span class="sxs-lookup"><span data-stu-id="b331f-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="b331f-551">1</span><span class="sxs-lookup"><span data-stu-id="b331f-551">1</span></span>          | <span data-ttu-id="b331f-552">Leasingkostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-552">Lease expense</span></span>            | <span data-ttu-id="b331f-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="b331f-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-554">1,000\.00</span></span>               |   | <span data-ttu-id="b331f-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="b331f-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="b331f-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-556">0\.00</span></span>                                   |
| <span data-ttu-id="b331f-557">2</span><span class="sxs-lookup"><span data-stu-id="b331f-557">2</span></span>          | <span data-ttu-id="b331f-558">Bankavgift</span><span class="sxs-lookup"><span data-stu-id="b331f-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="b331f-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="b331f-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b331f-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-561">3\.00</span></span>                                   |
| <span data-ttu-id="b331f-562">3</span><span class="sxs-lookup"><span data-stu-id="b331f-562">3</span></span>          | <span data-ttu-id="b331f-563">Momsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="b331f-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="b331f-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b331f-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-566">5\.00</span></span>                                   |
| <span data-ttu-id="b331f-567">4</span><span class="sxs-lookup"><span data-stu-id="b331f-567">4</span></span>          | <span data-ttu-id="b331f-568">Clearingkonto</span><span class="sxs-lookup"><span data-stu-id="b331f-568">Clearing account</span></span>         | <span data-ttu-id="b331f-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="b331f-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="b331f-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-571">0\.00</span></span>                   |   | <span data-ttu-id="b331f-572">1 000</span><span class="sxs-lookup"><span data-stu-id="b331f-572">1,000</span></span>                                           |                                                | <span data-ttu-id="b331f-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="b331f-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="b331f-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-574">0\.00</span></span>                                   |
| <span data-ttu-id="b331f-575">5</span><span class="sxs-lookup"><span data-stu-id="b331f-575">5</span></span>          | <span data-ttu-id="b331f-576">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="b331f-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="b331f-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="b331f-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-578">1,008\.00</span></span>                                         | <span data-ttu-id="b331f-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b331f-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-580">0\.00</span></span>                                   |
| <span data-ttu-id="b331f-581">6</span><span class="sxs-lookup"><span data-stu-id="b331f-581">6</span></span>          | <span data-ttu-id="b331f-582">Tillgång med nyttjanderätt</span><span class="sxs-lookup"><span data-stu-id="b331f-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="b331f-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="b331f-584">22,794</span><span class="sxs-lookup"><span data-stu-id="b331f-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="b331f-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="b331f-585">22,793\.90</span></span>                              |
| <span data-ttu-id="b331f-586">7</span><span class="sxs-lookup"><span data-stu-id="b331f-586">7</span></span>          | <span data-ttu-id="b331f-587">Finansiell leasingskyldighet</span><span class="sxs-lookup"><span data-stu-id="b331f-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="b331f-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="b331f-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="b331f-589">\-22,794</span></span>                                       | <span data-ttu-id="b331f-590">1 000</span><span class="sxs-lookup"><span data-stu-id="b331f-590">1,000</span></span>                                          | <span data-ttu-id="b331f-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="b331f-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="b331f-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="b331f-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="b331f-593">8</span><span class="sxs-lookup"><span data-stu-id="b331f-593">8</span></span>          | <span data-ttu-id="b331f-594">Räntekostnad</span><span class="sxs-lookup"><span data-stu-id="b331f-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="b331f-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="b331f-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="b331f-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="b331f-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="b331f-597">94\.97</span></span>                                  |
| <span data-ttu-id="b331f-598">9</span><span class="sxs-lookup"><span data-stu-id="b331f-598">9</span></span>          | <span data-ttu-id="b331f-599">Kontanter</span><span class="sxs-lookup"><span data-stu-id="b331f-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="b331f-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="b331f-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="b331f-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="b331f-603">10</span><span class="sxs-lookup"><span data-stu-id="b331f-603">10</span></span>         | <span data-ttu-id="b331f-604">Avskrivningsutgift</span><span class="sxs-lookup"><span data-stu-id="b331f-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="b331f-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="b331f-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="b331f-606">949\.75</span></span>                                        | <span data-ttu-id="b331f-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="b331f-607">949\.75</span></span>                                 |
| <span data-ttu-id="b331f-608">11</span><span class="sxs-lookup"><span data-stu-id="b331f-608">11</span></span>         | <span data-ttu-id="b331f-609">Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="b331f-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="b331f-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="b331f-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="b331f-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="b331f-611">\-949\.75</span></span>                                      | <span data-ttu-id="b331f-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="b331f-612">\-949\.75</span></span>                               |


