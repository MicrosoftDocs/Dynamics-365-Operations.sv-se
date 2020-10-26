---
title: Beräkning av indirekta kostnader
description: Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976485"
---
# <a name="overhead-calculation"></a><span data-ttu-id="04ae2-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="04ae2-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04ae2-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="04ae2-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="04ae2-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="04ae2-105">Term definition</span></span>
---------------

<span data-ttu-id="04ae2-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="04ae2-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="04ae2-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="04ae2-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="04ae2-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="04ae2-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="04ae2-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="04ae2-109">Rent</span></span>
-   <span data-ttu-id="04ae2-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-110">Electricity</span></span>
-   <span data-ttu-id="04ae2-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="04ae2-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="04ae2-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="04ae2-112">Overhead calculation overview</span></span>
<span data-ttu-id="04ae2-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="04ae2-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="04ae2-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="04ae2-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="04ae2-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="04ae2-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="04ae2-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="04ae2-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="04ae2-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="04ae2-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="04ae2-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="04ae2-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="04ae2-119">Version type</span></span>
-   <span data-ttu-id="04ae2-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="04ae2-120">Date and time</span></span>
-   <span data-ttu-id="04ae2-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="04ae2-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="04ae2-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="04ae2-122">Fiscal year</span></span>
-   <span data-ttu-id="04ae2-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="04ae2-123">Fiscal period</span></span>

<span data-ttu-id="04ae2-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="04ae2-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="04ae2-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="04ae2-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="04ae2-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="04ae2-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="04ae2-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="04ae2-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="04ae2-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="04ae2-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="04ae2-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="04ae2-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="04ae2-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="04ae2-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="04ae2-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="04ae2-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="04ae2-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="04ae2-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="04ae2-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="04ae2-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="04ae2-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="04ae2-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="04ae2-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="04ae2-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="04ae2-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="04ae2-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="04ae2-140">Main account</span></span></th>
<th><span data-ttu-id="04ae2-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="04ae2-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="04ae2-143">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-143">CC099</span></span></td>
<td><span data-ttu-id="04ae2-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-144">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-145">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-145">10001</span></span></td>
<td><span data-ttu-id="04ae2-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-146">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="04ae2-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="04ae2-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="04ae2-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="04ae2-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="04ae2-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="04ae2-151">Define the cost behavior rule</span></span>

<span data-ttu-id="04ae2-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="04ae2-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="04ae2-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="04ae2-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="04ae2-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="04ae2-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="04ae2-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="04ae2-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="04ae2-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="04ae2-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="04ae2-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="04ae2-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="04ae2-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="04ae2-159">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-160">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-160">Journal</span></span></th>
<th><span data-ttu-id="04ae2-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="04ae2-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="04ae2-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="04ae2-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="04ae2-163">version</span><span class="sxs-lookup"><span data-stu-id="04ae2-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-164">00001</span><span class="sxs-lookup"><span data-stu-id="04ae2-164">00001</span></span></td>
<td><span data-ttu-id="04ae2-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="04ae2-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="04ae2-166">Fiscal</span></span></td>
<td><span data-ttu-id="04ae2-167">2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-167">2017</span></span></td>
<td><span data-ttu-id="04ae2-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-168">Period 1</span></span></td>
<td><span data-ttu-id="04ae2-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="04ae2-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="04ae2-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-173">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-174">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="04ae2-177">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-177">CC099</span></span></td>
<td><span data-ttu-id="04ae2-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-178">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-179">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-179">10001</span></span></td>
<td><span data-ttu-id="04ae2-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-180">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="04ae2-181">Unclassified</span></span></td>
<td><span data-ttu-id="04ae2-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="04ae2-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04ae2-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-185">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-186">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-187">Amount</span></span></th>
<th><span data-ttu-id="04ae2-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-189">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-189">CC099</span></span></td>
<td><span data-ttu-id="04ae2-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-190">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-191">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-191">10001</span></span></td>
<td><span data-ttu-id="04ae2-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-192">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="04ae2-193">Unclassified</span></span></td>
<td><span data-ttu-id="04ae2-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-194">10,000.00</span></span></td>
<td><span data-ttu-id="04ae2-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-196">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-196">CC099</span></span></td>
<td><span data-ttu-id="04ae2-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-197">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-198">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-198">10001</span></span></td>
<td><span data-ttu-id="04ae2-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-199">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="04ae2-200">Unclassified</span></span></td>
<td><span data-ttu-id="04ae2-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-201">-10,000.00</span></span></td>
<td><span data-ttu-id="04ae2-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-203">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-203">CC099</span></span></td>
<td><span data-ttu-id="04ae2-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-204">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-205">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-205">10001</span></span></td>
<td><span data-ttu-id="04ae2-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-206">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-207">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-208">1,000.00</span></span></td>
<td><span data-ttu-id="04ae2-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-210">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-210">CC099</span></span></td>
<td><span data-ttu-id="04ae2-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-211">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-212">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-212">10001</span></span></td>
<td><span data-ttu-id="04ae2-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-213">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-214">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-215">9,000.00</span></span></td>
<td><span data-ttu-id="04ae2-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="04ae2-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="04ae2-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="04ae2-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="04ae2-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="04ae2-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="04ae2-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="04ae2-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="04ae2-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="04ae2-221">Define the cost distribution rule</span></span>

<span data-ttu-id="04ae2-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="04ae2-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="04ae2-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="04ae2-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="04ae2-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="04ae2-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="04ae2-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="04ae2-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="04ae2-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="04ae2-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="04ae2-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-228">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="04ae2-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-230">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-230">CC001</span></span></td>
<td><span data-ttu-id="04ae2-231">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-231">HR</span></span></td>
<td><span data-ttu-id="04ae2-232">1 000</span><span class="sxs-lookup"><span data-stu-id="04ae2-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-233">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-233">CC002</span></span></td>
<td><span data-ttu-id="04ae2-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-234">Finance</span></span></td>
<td><span data-ttu-id="04ae2-235">6,000</span><span class="sxs-lookup"><span data-stu-id="04ae2-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-236">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-236">CC003</span></span></td>
<td><span data-ttu-id="04ae2-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-237">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-238">0</span><span class="sxs-lookup"><span data-stu-id="04ae2-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="04ae2-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-240">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-241">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-242">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-244">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-244">CC001</span></span></td>
<td><span data-ttu-id="04ae2-245">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-245">HR</span></span></td>
<td><span data-ttu-id="04ae2-246">1 000</span><span class="sxs-lookup"><span data-stu-id="04ae2-246">1,000</span></span></td>
<td><span data-ttu-id="04ae2-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="04ae2-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="04ae2-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-249">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-249">CC002</span></span></td>
<td><span data-ttu-id="04ae2-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-250">Finance</span></span></td>
<td><span data-ttu-id="04ae2-251">6,000</span><span class="sxs-lookup"><span data-stu-id="04ae2-251">6,000</span></span></td>
<td><span data-ttu-id="04ae2-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="04ae2-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="04ae2-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-254">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-254">CC003</span></span></td>
<td><span data-ttu-id="04ae2-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-255">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-256">0</span><span class="sxs-lookup"><span data-stu-id="04ae2-256">0</span></span></td>
<td><span data-ttu-id="04ae2-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="04ae2-258">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="04ae2-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="04ae2-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="04ae2-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-261">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-262">Formel</span><span class="sxs-lookup"><span data-stu-id="04ae2-262">Formula</span></span></th>
<th><span data-ttu-id="04ae2-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-263">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-264">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-266">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-266">CC001</span></span></td>
<td><span data-ttu-id="04ae2-267">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-267">HR</span></span></td>
<td><span data-ttu-id="04ae2-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="04ae2-269">1</span><span class="sxs-lookup"><span data-stu-id="04ae2-269">1</span></span></td>
<td><span data-ttu-id="04ae2-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="04ae2-271">500.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-272">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-272">CC002</span></span></td>
<td><span data-ttu-id="04ae2-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-273">Finance</span></span></td>
<td><span data-ttu-id="04ae2-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="04ae2-275">1</span><span class="sxs-lookup"><span data-stu-id="04ae2-275">1</span></span></td>
<td><span data-ttu-id="04ae2-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="04ae2-277">500.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-278">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-278">CC003</span></span></td>
<td><span data-ttu-id="04ae2-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-279">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="04ae2-281">0</span><span class="sxs-lookup"><span data-stu-id="04ae2-281">0</span></span></td>
<td><span data-ttu-id="04ae2-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="04ae2-283">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="04ae2-284">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-285">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-285">Journal</span></span></th>
<th><span data-ttu-id="04ae2-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="04ae2-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="04ae2-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="04ae2-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="04ae2-288">version</span><span class="sxs-lookup"><span data-stu-id="04ae2-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-289">00002</span><span class="sxs-lookup"><span data-stu-id="04ae2-289">00002</span></span></td>
<td><span data-ttu-id="04ae2-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="04ae2-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="04ae2-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="04ae2-291">Fiscal</span></span></td>
<td><span data-ttu-id="04ae2-292">2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-292">2017</span></span></td>
<td><span data-ttu-id="04ae2-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-293">Period 1</span></span></td>
<td><span data-ttu-id="04ae2-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="04ae2-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="04ae2-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-298">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-299">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-302">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-302">CC099</span></span></td>
<td><span data-ttu-id="04ae2-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-303">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-304">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-304">10001</span></span></td>
<td><span data-ttu-id="04ae2-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-305">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-306">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-309">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-309">CC099</span></span></td>
<td><span data-ttu-id="04ae2-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-310">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-311">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-311">10001</span></span></td>
<td><span data-ttu-id="04ae2-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-312">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-313">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="04ae2-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04ae2-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-317">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-318">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-319">Amount</span></span></th>
<th><span data-ttu-id="04ae2-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-321">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-321">CC099</span></span></td>
<td><span data-ttu-id="04ae2-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-322">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-323">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-323">10001</span></span></td>
<td><span data-ttu-id="04ae2-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-324">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-325">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-326">-1,000.00</span></span></td>
<td><span data-ttu-id="04ae2-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-328">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-328">CC001</span></span></td>
<td><span data-ttu-id="04ae2-329">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-329">HR</span></span></td>
<td><span data-ttu-id="04ae2-330">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-330">10001</span></span></td>
<td><span data-ttu-id="04ae2-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-331">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-332">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-333">500.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-333">500.00</span></span></td>
<td><span data-ttu-id="04ae2-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-335">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-335">CC002</span></span></td>
<td><span data-ttu-id="04ae2-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-336">Finance</span></span></td>
<td><span data-ttu-id="04ae2-337">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-337">10001</span></span></td>
<td><span data-ttu-id="04ae2-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-338">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-339">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-340">500.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-340">500.00</span></span></td>
<td><span data-ttu-id="04ae2-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-342">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-342">CC099</span></span></td>
<td><span data-ttu-id="04ae2-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="04ae2-343">Default cost center</span></span></td>
<td><span data-ttu-id="04ae2-344">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-344">10001</span></span></td>
<td><span data-ttu-id="04ae2-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-345">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-346">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-347">-9,000.00</span></span></td>
<td><span data-ttu-id="04ae2-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-349">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-349">CC001</span></span></td>
<td><span data-ttu-id="04ae2-350">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-350">HR</span></span></td>
<td><span data-ttu-id="04ae2-351">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-351">10001</span></span></td>
<td><span data-ttu-id="04ae2-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-352">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-353">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="04ae2-354">1,285.71</span></span></td>
<td><span data-ttu-id="04ae2-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-356">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-356">CC002</span></span></td>
<td><span data-ttu-id="04ae2-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-357">Finance</span></span></td>
<td><span data-ttu-id="04ae2-358">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-358">10001</span></span></td>
<td><span data-ttu-id="04ae2-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-359">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-360">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="04ae2-361">7,714.29</span></span></td>
<td><span data-ttu-id="04ae2-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="04ae2-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="04ae2-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="04ae2-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="04ae2-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="04ae2-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="04ae2-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-367">Define the overhead rate</span></span>

<span data-ttu-id="04ae2-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="04ae2-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="04ae2-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-370">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="04ae2-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-372">Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-373">Project 1</span></span></td>
<td><span data-ttu-id="04ae2-374">3</span><span class="sxs-lookup"><span data-stu-id="04ae2-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-375">Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-376">Project 2</span></span></td>
<td><span data-ttu-id="04ae2-377">1</span><span class="sxs-lookup"><span data-stu-id="04ae2-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="04ae2-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-379">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-380">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-381">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="04ae2-382">Units</span></span></th>
<th><span data-ttu-id="04ae2-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="04ae2-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-384">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-384">CC001</span></span></td>
<td><span data-ttu-id="04ae2-385">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-385">HR</span></span></td>
<td><span data-ttu-id="04ae2-386">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-386">10001</span></span></td>
<td><span data-ttu-id="04ae2-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-387">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-388">1</span><span class="sxs-lookup"><span data-stu-id="04ae2-388">1</span></span></td>
<td><span data-ttu-id="04ae2-389">10</span><span class="sxs-lookup"><span data-stu-id="04ae2-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="04ae2-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-391">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-392">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-393">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-394">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-396">Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-397">Project 1</span></span></td>
<td><span data-ttu-id="04ae2-398">3</span><span class="sxs-lookup"><span data-stu-id="04ae2-398">3</span></span></td>
<td><span data-ttu-id="04ae2-399">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-399">10001</span></span></td>
<td><span data-ttu-id="04ae2-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="04ae2-401">30,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-402">Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-403">Project 2</span></span></td>
<td><span data-ttu-id="04ae2-404">1</span><span class="sxs-lookup"><span data-stu-id="04ae2-404">1</span></span></td>
<td><span data-ttu-id="04ae2-405">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-405">10001</span></span></td>
<td><span data-ttu-id="04ae2-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="04ae2-407">10,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="04ae2-408">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-409">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-409">Journal</span></span></th>
<th><span data-ttu-id="04ae2-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="04ae2-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="04ae2-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="04ae2-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="04ae2-412">version</span><span class="sxs-lookup"><span data-stu-id="04ae2-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-413">00003</span><span class="sxs-lookup"><span data-stu-id="04ae2-413">00003</span></span></td>
<td><span data-ttu-id="04ae2-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="04ae2-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="04ae2-415">Fiscal</span></span></td>
<td><span data-ttu-id="04ae2-416">2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-416">2017</span></span></td>
<td><span data-ttu-id="04ae2-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-417">Period 1</span></span></td>
<td><span data-ttu-id="04ae2-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="04ae2-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="04ae2-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-421">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-424">Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-426">3,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-428">Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-430">1,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="04ae2-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04ae2-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-433">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-434">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-435">Amount</span></span></th>
<th><span data-ttu-id="04ae2-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="04ae2-437">CC0001</span></span></td>
<td><span data-ttu-id="04ae2-438">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-438">HR</span></span></td>
<td><span data-ttu-id="04ae2-439">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-439">10001</span></span></td>
<td><span data-ttu-id="04ae2-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-440">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-441">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-442">-30.00</span></span></td>
<td><span data-ttu-id="04ae2-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-444">Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="04ae2-446">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-446">10001</span></span></td>
<td><span data-ttu-id="04ae2-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-447">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-448">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-449">30,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-449">30.00</span></span></td>
<td><span data-ttu-id="04ae2-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-451">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-451">CC001</span></span></td>
<td><span data-ttu-id="04ae2-452">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-452">HR</span></span></td>
<td><span data-ttu-id="04ae2-453">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-453">10001</span></span></td>
<td><span data-ttu-id="04ae2-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-454">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-455">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-456">-10.00</span></span></td>
<td><span data-ttu-id="04ae2-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-458">Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="04ae2-460">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-460">10001</span></span></td>
<td><span data-ttu-id="04ae2-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-461">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-462">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-463">10,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-463">10.00</span></span></td>
<td><span data-ttu-id="04ae2-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="04ae2-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="04ae2-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="04ae2-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="04ae2-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="04ae2-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="04ae2-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="04ae2-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="04ae2-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="04ae2-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="04ae2-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="04ae2-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="04ae2-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="04ae2-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="04ae2-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="04ae2-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="04ae2-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="04ae2-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="04ae2-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="04ae2-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="04ae2-475">Define the cost allocation</span></span>

<span data-ttu-id="04ae2-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="04ae2-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="04ae2-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="04ae2-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="04ae2-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-479">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="04ae2-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-481">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-481">CC002</span></span></td>
<td><span data-ttu-id="04ae2-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-482">Finance</span></span></td>
<td><span data-ttu-id="04ae2-483">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-484">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-484">CC003</span></span></td>
<td><span data-ttu-id="04ae2-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-485">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-486">55</span><span class="sxs-lookup"><span data-stu-id="04ae2-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-487">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-487">CC004</span></span></td>
<td><span data-ttu-id="04ae2-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-488">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-489">10</span><span class="sxs-lookup"><span data-stu-id="04ae2-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="04ae2-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="04ae2-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-492">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="04ae2-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-494">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-494">CC003</span></span></td>
<td><span data-ttu-id="04ae2-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-495">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-496">65</span><span class="sxs-lookup"><span data-stu-id="04ae2-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-497">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-497">CC004</span></span></td>
<td><span data-ttu-id="04ae2-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-498">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-499">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="04ae2-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="04ae2-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-502">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="04ae2-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-504">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-505">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-506">60</span><span class="sxs-lookup"><span data-stu-id="04ae2-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-507">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-508">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-509">20</span><span class="sxs-lookup"><span data-stu-id="04ae2-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="04ae2-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="04ae2-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="04ae2-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-512">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="04ae2-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-514">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-515">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-516">80</span><span class="sxs-lookup"><span data-stu-id="04ae2-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-517">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-518">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-519">15</span><span class="sxs-lookup"><span data-stu-id="04ae2-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="04ae2-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="04ae2-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="04ae2-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="04ae2-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="04ae2-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="04ae2-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-523">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-524">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-525">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-526">Amount</span></span></th>
<th><span data-ttu-id="04ae2-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-528">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-528">CC002</span></span></td>
<td><span data-ttu-id="04ae2-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-529">Finance</span></span></td>
<td><span data-ttu-id="04ae2-530">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-530">35</span></span></td>
<td><span data-ttu-id="04ae2-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="04ae2-532">175.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-532">175.00</span></span></td>
<td><span data-ttu-id="04ae2-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-534">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-534">CC003</span></span></td>
<td><span data-ttu-id="04ae2-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-535">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-536">55</span><span class="sxs-lookup"><span data-stu-id="04ae2-536">55</span></span></td>
<td><span data-ttu-id="04ae2-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="04ae2-538">275.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-538">275.00</span></span></td>
<td><span data-ttu-id="04ae2-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-540">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-540">CC004</span></span></td>
<td><span data-ttu-id="04ae2-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-541">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-542">10</span><span class="sxs-lookup"><span data-stu-id="04ae2-542">10</span></span></td>
<td><span data-ttu-id="04ae2-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="04ae2-544">50,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-544">50.00</span></span></td>
<td><span data-ttu-id="04ae2-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-546">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-546">CC002</span></span></td>
<td><span data-ttu-id="04ae2-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-547">Finance</span></span></td>
<td><span data-ttu-id="04ae2-548">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-548">35</span></span></td>
<td><span data-ttu-id="04ae2-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="04ae2-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="04ae2-550">436.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-550">436.00</span></span></td>
<td><span data-ttu-id="04ae2-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-552">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-552">CC003</span></span></td>
<td><span data-ttu-id="04ae2-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-553">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-554">55</span><span class="sxs-lookup"><span data-stu-id="04ae2-554">55</span></span></td>
<td><span data-ttu-id="04ae2-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="04ae2-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="04ae2-556">685.14</span><span class="sxs-lookup"><span data-stu-id="04ae2-556">685.14</span></span></td>
<td><span data-ttu-id="04ae2-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-558">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-558">CC004</span></span></td>
<td><span data-ttu-id="04ae2-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-559">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-560">10</span><span class="sxs-lookup"><span data-stu-id="04ae2-560">10</span></span></td>
<td><span data-ttu-id="04ae2-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="04ae2-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="04ae2-562">124.57</span><span class="sxs-lookup"><span data-stu-id="04ae2-562">124.57</span></span></td>
<td><span data-ttu-id="04ae2-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="04ae2-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-565">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-566">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-567">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-568">Amount</span></span></th>
<th><span data-ttu-id="04ae2-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-570">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-570">CC003</span></span></td>
<td><span data-ttu-id="04ae2-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-571">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-572">65</span><span class="sxs-lookup"><span data-stu-id="04ae2-572">65</span></span></td>
<td><span data-ttu-id="04ae2-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="04ae2-574">438.75</span><span class="sxs-lookup"><span data-stu-id="04ae2-574">438.75</span></span></td>
<td><span data-ttu-id="04ae2-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-576">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-576">CC004</span></span></td>
<td><span data-ttu-id="04ae2-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-577">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-578">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-578">35</span></span></td>
<td><span data-ttu-id="04ae2-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="04ae2-580">236.25</span><span class="sxs-lookup"><span data-stu-id="04ae2-580">236.25</span></span></td>
<td><span data-ttu-id="04ae2-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-582">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-582">CC003</span></span></td>
<td><span data-ttu-id="04ae2-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-583">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-584">65</span><span class="sxs-lookup"><span data-stu-id="04ae2-584">65</span></span></td>
<td><span data-ttu-id="04ae2-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="04ae2-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="04ae2-586">5,297.69</span></span></td>
<td><span data-ttu-id="04ae2-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-588">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-588">CC004</span></span></td>
<td><span data-ttu-id="04ae2-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-589">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-590">35</span><span class="sxs-lookup"><span data-stu-id="04ae2-590">35</span></span></td>
<td><span data-ttu-id="04ae2-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="04ae2-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="04ae2-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="04ae2-592">2,852.60</span></span></td>
<td><span data-ttu-id="04ae2-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="04ae2-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-595">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-596">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-597">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-598">Amount</span></span></th>
<th><span data-ttu-id="04ae2-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-600">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-601">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-602">60</span><span class="sxs-lookup"><span data-stu-id="04ae2-602">60</span></span></td>
<td><span data-ttu-id="04ae2-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="04ae2-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="04ae2-604">535.31</span><span class="sxs-lookup"><span data-stu-id="04ae2-604">535.31</span></span></td>
<td><span data-ttu-id="04ae2-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-606">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-607">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-608">20</span><span class="sxs-lookup"><span data-stu-id="04ae2-608">20</span></span></td>
<td><span data-ttu-id="04ae2-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="04ae2-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="04ae2-610">178.44</span><span class="sxs-lookup"><span data-stu-id="04ae2-610">178.44</span></span></td>
<td><span data-ttu-id="04ae2-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-612">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-613">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-614">60</span><span class="sxs-lookup"><span data-stu-id="04ae2-614">60</span></span></td>
<td><span data-ttu-id="04ae2-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="04ae2-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="04ae2-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="04ae2-616">4,487.12</span></span></td>
<td><span data-ttu-id="04ae2-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-618">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-619">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-620">20</span><span class="sxs-lookup"><span data-stu-id="04ae2-620">20</span></span></td>
<td><span data-ttu-id="04ae2-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="04ae2-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="04ae2-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="04ae2-622">1,495.71</span></span></td>
<td><span data-ttu-id="04ae2-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="04ae2-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="04ae2-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-625">Cost object</span></span></th>
<th><span data-ttu-id="04ae2-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="04ae2-626">Magnitude</span></span></th>
<th><span data-ttu-id="04ae2-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="04ae2-627">Allocation factor</span></span></th>
<th><span data-ttu-id="04ae2-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-628">Amount</span></span></th>
<th><span data-ttu-id="04ae2-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-630">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-631">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-632">80</span><span class="sxs-lookup"><span data-stu-id="04ae2-632">80</span></span></td>
<td><span data-ttu-id="04ae2-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="04ae2-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="04ae2-634">241.05</span><span class="sxs-lookup"><span data-stu-id="04ae2-634">241.05</span></span></td>
<td><span data-ttu-id="04ae2-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-636">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-637">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-638">15</span><span class="sxs-lookup"><span data-stu-id="04ae2-638">15</span></span></td>
<td><span data-ttu-id="04ae2-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="04ae2-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="04ae2-640">45.20</span><span class="sxs-lookup"><span data-stu-id="04ae2-640">45.20</span></span></td>
<td><span data-ttu-id="04ae2-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-642">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-643">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-644">80</span><span class="sxs-lookup"><span data-stu-id="04ae2-644">80</span></span></td>
<td><span data-ttu-id="04ae2-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="04ae2-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="04ae2-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="04ae2-646">2,507.09</span></span></td>
<td><span data-ttu-id="04ae2-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-648">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-649">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-650">15</span><span class="sxs-lookup"><span data-stu-id="04ae2-650">15</span></span></td>
<td><span data-ttu-id="04ae2-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="04ae2-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="04ae2-652">470.08</span><span class="sxs-lookup"><span data-stu-id="04ae2-652">470.08</span></span></td>
<td><span data-ttu-id="04ae2-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="04ae2-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="04ae2-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-655">Journal</span><span class="sxs-lookup"><span data-stu-id="04ae2-655">Journal</span></span></th>
<th><span data-ttu-id="04ae2-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="04ae2-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="04ae2-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="04ae2-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="04ae2-658">version</span><span class="sxs-lookup"><span data-stu-id="04ae2-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-659">00004</span><span class="sxs-lookup"><span data-stu-id="04ae2-659">00004</span></span></td>
<td><span data-ttu-id="04ae2-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="04ae2-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="04ae2-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="04ae2-661">Fiscal</span></span></td>
<td><span data-ttu-id="04ae2-662">2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-662">2017</span></span></td>
<td><span data-ttu-id="04ae2-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-663">Period 1</span></span></td>
<td><span data-ttu-id="04ae2-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="04ae2-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="04ae2-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="04ae2-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-668">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-669">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-672">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-672">CC001</span></span></td>
<td><span data-ttu-id="04ae2-673">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-673">HR</span></span></td>
<td><span data-ttu-id="04ae2-674">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-674">10001</span></span></td>
<td><span data-ttu-id="04ae2-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-675">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-676">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-677">500.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-679">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-679">CC001</span></span></td>
<td><span data-ttu-id="04ae2-680">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-680">HR</span></span></td>
<td><span data-ttu-id="04ae2-681">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-681">10001</span></span></td>
<td><span data-ttu-id="04ae2-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-682">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-683">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="04ae2-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-686">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-686">CC002</span></span></td>
<td><span data-ttu-id="04ae2-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-687">Finance</span></span></td>
<td><span data-ttu-id="04ae2-688">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-688">10001</span></span></td>
<td><span data-ttu-id="04ae2-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-689">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-690">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-691">675.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-693">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-693">CC002</span></span></td>
<td><span data-ttu-id="04ae2-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-694">Finance</span></span></td>
<td><span data-ttu-id="04ae2-695">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-695">10001</span></span></td>
<td><span data-ttu-id="04ae2-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-696">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-697">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="04ae2-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-700">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-700">CC003</span></span></td>
<td><span data-ttu-id="04ae2-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-701">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-702">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-702">10001</span></span></td>
<td><span data-ttu-id="04ae2-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-703">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-704">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-705">713.75</span><span class="sxs-lookup"><span data-stu-id="04ae2-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-707">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-707">CC003</span></span></td>
<td><span data-ttu-id="04ae2-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-708">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-709">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-709">10001</span></span></td>
<td><span data-ttu-id="04ae2-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-710">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-711">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="04ae2-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-714">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-714">CC003</span></span></td>
<td><span data-ttu-id="04ae2-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-715">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-716">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-716">10001</span></span></td>
<td><span data-ttu-id="04ae2-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-717">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-718">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-719">286.25</span><span class="sxs-lookup"><span data-stu-id="04ae2-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-721">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-721">CC003</span></span></td>
<td><span data-ttu-id="04ae2-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-722">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-723">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-723">10001</span></span></td>
<td><span data-ttu-id="04ae2-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-724">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-725">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="04ae2-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-728">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-729">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-730">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-730">10001</span></span></td>
<td><span data-ttu-id="04ae2-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-731">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-732">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-733">776.36</span><span class="sxs-lookup"><span data-stu-id="04ae2-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-735">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-736">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-737">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-737">10001</span></span></td>
<td><span data-ttu-id="04ae2-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-738">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-739">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="04ae2-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-742">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-743">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-744">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-744">10001</span></span></td>
<td><span data-ttu-id="04ae2-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-745">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-746">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-747">223.64</span><span class="sxs-lookup"><span data-stu-id="04ae2-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="04ae2-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-749">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-750">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-751">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-751">10001</span></span></td>
<td><span data-ttu-id="04ae2-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-752">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-753">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="04ae2-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="04ae2-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="04ae2-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="04ae2-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="04ae2-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-757">Cost element</span></span></th>
<th><span data-ttu-id="04ae2-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="04ae2-758">Cost behavior</span></span></th>
<th><span data-ttu-id="04ae2-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="04ae2-759">Amount</span></span></th>
<th><span data-ttu-id="04ae2-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="04ae2-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="04ae2-761">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-761">CC001</span></span></td>
<td><span data-ttu-id="04ae2-762">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-762">HR</span></span></td>
<td><span data-ttu-id="04ae2-763">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-763">10001</span></span></td>
<td><span data-ttu-id="04ae2-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-764">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-765">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-766">-500.00</span></span></td>
<td><span data-ttu-id="04ae2-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-768">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-768">CC002</span></span></td>
<td><span data-ttu-id="04ae2-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-769">Finance</span></span></td>
<td><span data-ttu-id="04ae2-770">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-770">10001</span></span></td>
<td><span data-ttu-id="04ae2-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-771">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-772">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-773">175.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-773">175.00</span></span></td>
<td><span data-ttu-id="04ae2-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-775">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-775">CC003</span></span></td>
<td><span data-ttu-id="04ae2-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-776">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-777">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-777">10001</span></span></td>
<td><span data-ttu-id="04ae2-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-778">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-779">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-780">275.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-780">275.00</span></span></td>
<td><span data-ttu-id="04ae2-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-782">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-782">CC004</span></span></td>
<td><span data-ttu-id="04ae2-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-783">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-784">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-784">10001</span></span></td>
<td><span data-ttu-id="04ae2-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-785">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-786">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-787">50,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-787">50,00</span></span></td>
<td><span data-ttu-id="04ae2-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-789">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-789">CC001</span></span></td>
<td><span data-ttu-id="04ae2-790">Personal</span><span class="sxs-lookup"><span data-stu-id="04ae2-790">HR</span></span></td>
<td><span data-ttu-id="04ae2-791">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-791">10001</span></span></td>
<td><span data-ttu-id="04ae2-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-792">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-793">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="04ae2-794">-1,245.71</span></span></td>
<td><span data-ttu-id="04ae2-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-796">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-796">CC002</span></span></td>
<td><span data-ttu-id="04ae2-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-797">Finance</span></span></td>
<td><span data-ttu-id="04ae2-798">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-798">10001</span></span></td>
<td><span data-ttu-id="04ae2-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-799">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-800">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-801">436.00</span><span class="sxs-lookup"><span data-stu-id="04ae2-801">436.00</span></span></td>
<td><span data-ttu-id="04ae2-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-803">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-803">CC003</span></span></td>
<td><span data-ttu-id="04ae2-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-804">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-805">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-805">10001</span></span></td>
<td><span data-ttu-id="04ae2-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-806">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-807">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-808">685.14</span><span class="sxs-lookup"><span data-stu-id="04ae2-808">685.14</span></span></td>
<td><span data-ttu-id="04ae2-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-810">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-810">CC004</span></span></td>
<td><span data-ttu-id="04ae2-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-811">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-812">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-812">10001</span></span></td>
<td><span data-ttu-id="04ae2-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-813">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-814">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-815">124.57</span><span class="sxs-lookup"><span data-stu-id="04ae2-815">124.57</span></span></td>
<td><span data-ttu-id="04ae2-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-817">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-817">CC002</span></span></td>
<td><span data-ttu-id="04ae2-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-818">Finance</span></span></td>
<td><span data-ttu-id="04ae2-819">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-819">10001</span></span></td>
<td><span data-ttu-id="04ae2-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-820">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-821">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-822">-675.00</span></span></td>
<td><span data-ttu-id="04ae2-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-824">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-824">CC003</span></span></td>
<td><span data-ttu-id="04ae2-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-825">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-826">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-826">10001</span></span></td>
<td><span data-ttu-id="04ae2-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-827">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-828">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-829">438.75</span><span class="sxs-lookup"><span data-stu-id="04ae2-829">438.75</span></span></td>
<td><span data-ttu-id="04ae2-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-831">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-831">CC004</span></span></td>
<td><span data-ttu-id="04ae2-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-832">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-833">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-833">10001</span></span></td>
<td><span data-ttu-id="04ae2-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-834">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-835">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-836">236.25</span><span class="sxs-lookup"><span data-stu-id="04ae2-836">236.25</span></span></td>
<td><span data-ttu-id="04ae2-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-838">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-838">CC002</span></span></td>
<td><span data-ttu-id="04ae2-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="04ae2-839">Finance</span></span></td>
<td><span data-ttu-id="04ae2-840">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-840">10001</span></span></td>
<td><span data-ttu-id="04ae2-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-841">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-842">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="04ae2-843">-8,150.29</span></span></td>
<td><span data-ttu-id="04ae2-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-845">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-845">CC003</span></span></td>
<td><span data-ttu-id="04ae2-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-846">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-847">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-847">10001</span></span></td>
<td><span data-ttu-id="04ae2-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-848">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-849">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="04ae2-850">5,297.69</span></span></td>
<td><span data-ttu-id="04ae2-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-852">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-852">CC004</span></span></td>
<td><span data-ttu-id="04ae2-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="04ae2-853">Packaging</span></span></td>
<td><span data-ttu-id="04ae2-854">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-854">10001</span></span></td>
<td><span data-ttu-id="04ae2-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-855">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-856">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="04ae2-857">2,852.60</span></span></td>
<td><span data-ttu-id="04ae2-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-859">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-859">CC003</span></span></td>
<td><span data-ttu-id="04ae2-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-860">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-861">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-861">10001</span></span></td>
<td><span data-ttu-id="04ae2-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-862">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-863">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="04ae2-864">-713.75</span></span></td>
<td><span data-ttu-id="04ae2-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-866">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-867">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-868">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-868">10001</span></span></td>
<td><span data-ttu-id="04ae2-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-869">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-870">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-871">535.31</span><span class="sxs-lookup"><span data-stu-id="04ae2-871">535.31</span></span></td>
<td><span data-ttu-id="04ae2-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-873">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-874">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-875">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-875">10001</span></span></td>
<td><span data-ttu-id="04ae2-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-876">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-877">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-878">178.44</span><span class="sxs-lookup"><span data-stu-id="04ae2-878">178.44</span></span></td>
<td><span data-ttu-id="04ae2-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-880">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-880">CC003</span></span></td>
<td><span data-ttu-id="04ae2-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-881">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-882">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-882">10001</span></span></td>
<td><span data-ttu-id="04ae2-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-883">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-884">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="04ae2-885">-5,982.83</span></span></td>
<td><span data-ttu-id="04ae2-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-887">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-888">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-889">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-889">10001</span></span></td>
<td><span data-ttu-id="04ae2-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-890">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-891">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="04ae2-892">4,487.12</span></span></td>
<td><span data-ttu-id="04ae2-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-894">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-895">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-896">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-896">10001</span></span></td>
<td><span data-ttu-id="04ae2-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-897">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-898">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="04ae2-899">1,495.71</span></span></td>
<td><span data-ttu-id="04ae2-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-901">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-901">CC003</span></span></td>
<td><span data-ttu-id="04ae2-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-902">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-903">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-903">10001</span></span></td>
<td><span data-ttu-id="04ae2-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-904">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-905">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="04ae2-906">-286.25</span></span></td>
<td><span data-ttu-id="04ae2-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-908">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-909">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-910">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-910">10001</span></span></td>
<td><span data-ttu-id="04ae2-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-911">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-912">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-913">241.05</span><span class="sxs-lookup"><span data-stu-id="04ae2-913">241.05</span></span></td>
<td><span data-ttu-id="04ae2-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-915">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-916">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-917">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-917">10001</span></span></td>
<td><span data-ttu-id="04ae2-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-918">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-919">Fixed cost</span></span></td>
<td><span data-ttu-id="04ae2-920">45.20</span><span class="sxs-lookup"><span data-stu-id="04ae2-920">45.20</span></span></td>
<td><span data-ttu-id="04ae2-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-922">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-922">CC003</span></span></td>
<td><span data-ttu-id="04ae2-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="04ae2-923">Assembly</span></span></td>
<td><span data-ttu-id="04ae2-924">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-924">10001</span></span></td>
<td><span data-ttu-id="04ae2-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-925">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-926">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="04ae2-927">-2,977.17</span></span></td>
<td><span data-ttu-id="04ae2-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-929">Prod 1</span></span></td>
<td><span data-ttu-id="04ae2-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-930">Product 1</span></span></td>
<td><span data-ttu-id="04ae2-931">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-931">10001</span></span></td>
<td><span data-ttu-id="04ae2-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-932">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-933">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="04ae2-934">2,507.09</span></span></td>
<td><span data-ttu-id="04ae2-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="04ae2-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-936">Prod 2</span></span></td>
<td><span data-ttu-id="04ae2-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-937">Product 2</span></span></td>
<td><span data-ttu-id="04ae2-938">10001</span><span class="sxs-lookup"><span data-stu-id="04ae2-938">10001</span></span></td>
<td><span data-ttu-id="04ae2-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-939">Electricity</span></span></td>
<td><span data-ttu-id="04ae2-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-940">Variable cost</span></span></td>
<td><span data-ttu-id="04ae2-941">470.08</span><span class="sxs-lookup"><span data-stu-id="04ae2-941">470.08</span></span></td>
<td><span data-ttu-id="04ae2-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="04ae2-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="04ae2-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="04ae2-943">Conclusion</span></span>
<span data-ttu-id="04ae2-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="04ae2-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="04ae2-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="04ae2-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="04ae2-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="04ae2-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="04ae2-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="04ae2-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="04ae2-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="04ae2-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="04ae2-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="04ae2-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="04ae2-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="04ae2-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="04ae2-951">CC099</span><span class="sxs-lookup"><span data-stu-id="04ae2-951">CC099</span></span></th>
<th><span data-ttu-id="04ae2-952">CC001</span><span class="sxs-lookup"><span data-stu-id="04ae2-952">CC001</span></span></th>
<th><span data-ttu-id="04ae2-953">CC002</span><span class="sxs-lookup"><span data-stu-id="04ae2-953">CC002</span></span></th>
<th><span data-ttu-id="04ae2-954">CC003</span><span class="sxs-lookup"><span data-stu-id="04ae2-954">CC003</span></span></th>
<th><span data-ttu-id="04ae2-955">CC004</span><span class="sxs-lookup"><span data-stu-id="04ae2-955">CC004</span></span></th>
<th><span data-ttu-id="04ae2-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-956">Proj 1</span></span></th>
<th><span data-ttu-id="04ae2-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-957">Proj 2</span></span></th>
<th><span data-ttu-id="04ae2-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="04ae2-958">Prod 1</span></span></th>
<th><span data-ttu-id="04ae2-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="04ae2-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="04ae2-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="04ae2-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="04ae2-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="04ae2-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-971">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-971">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="04ae2-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-973">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-974">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-975">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-976">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-977">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-978">776.36</span><span class="sxs-lookup"><span data-stu-id="04ae2-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-979">223.64</span><span class="sxs-lookup"><span data-stu-id="04ae2-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="04ae2-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="04ae2-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-982">000</span><span class="sxs-lookup"><span data-stu-id="04ae2-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-983">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-984">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-985">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-986">0,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-987">30,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-988">10,00</span><span class="sxs-lookup"><span data-stu-id="04ae2-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="04ae2-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="04ae2-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="04ae2-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="04ae2-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="04ae2-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="04ae2-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="04ae2-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="04ae2-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="04ae2-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="04ae2-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="04ae2-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="04ae2-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="04ae2-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="04ae2-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



