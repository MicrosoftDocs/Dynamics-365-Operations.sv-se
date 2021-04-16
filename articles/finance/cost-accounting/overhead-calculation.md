---
title: Beräkning av indirekta kostnader
description: Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 2dddc22128621dc148a253cd568430587f294544
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822913"
---
# <a name="overhead-calculation"></a><span data-ttu-id="a3535-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="a3535-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3535-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="a3535-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="a3535-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="a3535-105">Term definition</span></span>
---------------

<span data-ttu-id="a3535-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="a3535-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="a3535-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="a3535-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="a3535-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="a3535-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="a3535-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="a3535-109">Rent</span></span>
-   <span data-ttu-id="a3535-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-110">Electricity</span></span>
-   <span data-ttu-id="a3535-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="a3535-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="a3535-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="a3535-112">Overhead calculation overview</span></span>
<span data-ttu-id="a3535-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="a3535-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="a3535-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="a3535-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="a3535-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="a3535-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="a3535-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="a3535-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="a3535-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="a3535-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="a3535-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="a3535-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="a3535-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="a3535-119">Version type</span></span>
-   <span data-ttu-id="a3535-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="a3535-120">Date and time</span></span>
-   <span data-ttu-id="a3535-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="a3535-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="a3535-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="a3535-122">Fiscal year</span></span>
-   <span data-ttu-id="a3535-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="a3535-123">Fiscal period</span></span>

<span data-ttu-id="a3535-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="a3535-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="a3535-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="a3535-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="a3535-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="a3535-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="a3535-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="a3535-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="a3535-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="a3535-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="a3535-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="a3535-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="a3535-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="a3535-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="a3535-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="a3535-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="a3535-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="a3535-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="a3535-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="a3535-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="a3535-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="a3535-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="a3535-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="a3535-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="a3535-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="a3535-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="a3535-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="a3535-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="a3535-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="a3535-140">Main account</span></span></th>
<th><span data-ttu-id="a3535-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="a3535-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="a3535-143">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-143">CC099</span></span></td>
<td><span data-ttu-id="a3535-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-144">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-145">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-145">10001</span></span></td>
<td><span data-ttu-id="a3535-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-146">Electricity</span></span></td>
<td><span data-ttu-id="a3535-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="a3535-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="a3535-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="a3535-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="a3535-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="a3535-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="a3535-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="a3535-151">Define the cost behavior rule</span></span>

<span data-ttu-id="a3535-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="a3535-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="a3535-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="a3535-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="a3535-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="a3535-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="a3535-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="a3535-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="a3535-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="a3535-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="a3535-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="a3535-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="a3535-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="a3535-159">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-160">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-160">Journal</span></span></th>
<th><span data-ttu-id="a3535-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="a3535-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3535-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="a3535-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3535-163">version</span><span class="sxs-lookup"><span data-stu-id="a3535-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-164">00001</span><span class="sxs-lookup"><span data-stu-id="a3535-164">00001</span></span></td>
<td><span data-ttu-id="a3535-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="a3535-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="a3535-166">Fiscal</span></span></td>
<td><span data-ttu-id="a3535-167">2017</span><span class="sxs-lookup"><span data-stu-id="a3535-167">2017</span></span></td>
<td><span data-ttu-id="a3535-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-168">Period 1</span></span></td>
<td><span data-ttu-id="a3535-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3535-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="a3535-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-173">Cost element</span></span></th>
<th><span data-ttu-id="a3535-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-174">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="a3535-177">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-177">CC099</span></span></td>
<td><span data-ttu-id="a3535-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-178">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-179">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-179">10001</span></span></td>
<td><span data-ttu-id="a3535-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-180">Electricity</span></span></td>
<td><span data-ttu-id="a3535-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="a3535-181">Unclassified</span></span></td>
<td><span data-ttu-id="a3535-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3535-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="a3535-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-185">Cost element</span></span></th>
<th><span data-ttu-id="a3535-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-186">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-187">Amount</span></span></th>
<th><span data-ttu-id="a3535-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-189">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-189">CC099</span></span></td>
<td><span data-ttu-id="a3535-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-190">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-191">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-191">10001</span></span></td>
<td><span data-ttu-id="a3535-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-192">Electricity</span></span></td>
<td><span data-ttu-id="a3535-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="a3535-193">Unclassified</span></span></td>
<td><span data-ttu-id="a3535-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-194">10,000.00</span></span></td>
<td><span data-ttu-id="a3535-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-196">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-196">CC099</span></span></td>
<td><span data-ttu-id="a3535-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-197">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-198">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-198">10001</span></span></td>
<td><span data-ttu-id="a3535-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-199">Electricity</span></span></td>
<td><span data-ttu-id="a3535-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="a3535-200">Unclassified</span></span></td>
<td><span data-ttu-id="a3535-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-201">-10,000.00</span></span></td>
<td><span data-ttu-id="a3535-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-203">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-203">CC099</span></span></td>
<td><span data-ttu-id="a3535-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-204">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-205">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-205">10001</span></span></td>
<td><span data-ttu-id="a3535-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-206">Electricity</span></span></td>
<td><span data-ttu-id="a3535-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-207">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-208">1,000.00</span></span></td>
<td><span data-ttu-id="a3535-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-210">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-210">CC099</span></span></td>
<td><span data-ttu-id="a3535-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-211">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-212">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-212">10001</span></span></td>
<td><span data-ttu-id="a3535-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-213">Electricity</span></span></td>
<td><span data-ttu-id="a3535-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-214">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a3535-215">9,000.00</span></span></td>
<td><span data-ttu-id="a3535-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="a3535-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="a3535-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="a3535-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="a3535-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="a3535-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="a3535-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="a3535-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="a3535-221">Define the cost distribution rule</span></span>

<span data-ttu-id="a3535-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="a3535-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="a3535-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="a3535-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="a3535-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="a3535-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="a3535-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="a3535-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="a3535-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="a3535-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="a3535-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="a3535-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-228">Cost object</span></span></th>
<th><span data-ttu-id="a3535-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="a3535-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-230">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-230">CC001</span></span></td>
<td><span data-ttu-id="a3535-231">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-231">HR</span></span></td>
<td><span data-ttu-id="a3535-232">1 000</span><span class="sxs-lookup"><span data-stu-id="a3535-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-233">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-233">CC002</span></span></td>
<td><span data-ttu-id="a3535-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-234">Finance</span></span></td>
<td><span data-ttu-id="a3535-235">6,000</span><span class="sxs-lookup"><span data-stu-id="a3535-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-236">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-236">CC003</span></span></td>
<td><span data-ttu-id="a3535-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-237">Assembly</span></span></td>
<td><span data-ttu-id="a3535-238">0</span><span class="sxs-lookup"><span data-stu-id="a3535-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="a3535-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-240">Cost object</span></span></th>
<th><span data-ttu-id="a3535-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-241">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-242">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-244">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-244">CC001</span></span></td>
<td><span data-ttu-id="a3535-245">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-245">HR</span></span></td>
<td><span data-ttu-id="a3535-246">1 000</span><span class="sxs-lookup"><span data-stu-id="a3535-246">1,000</span></span></td>
<td><span data-ttu-id="a3535-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3535-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a3535-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-249">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-249">CC002</span></span></td>
<td><span data-ttu-id="a3535-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-250">Finance</span></span></td>
<td><span data-ttu-id="a3535-251">6,000</span><span class="sxs-lookup"><span data-stu-id="a3535-251">6,000</span></span></td>
<td><span data-ttu-id="a3535-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3535-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a3535-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-254">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-254">CC003</span></span></td>
<td><span data-ttu-id="a3535-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-255">Assembly</span></span></td>
<td><span data-ttu-id="a3535-256">0</span><span class="sxs-lookup"><span data-stu-id="a3535-256">0</span></span></td>
<td><span data-ttu-id="a3535-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a3535-258">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="a3535-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="a3535-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="a3535-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-261">Cost object</span></span></th>
<th><span data-ttu-id="a3535-262">Formel</span><span class="sxs-lookup"><span data-stu-id="a3535-262">Formula</span></span></th>
<th><span data-ttu-id="a3535-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-263">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-264">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-266">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-266">CC001</span></span></td>
<td><span data-ttu-id="a3535-267">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-267">HR</span></span></td>
<td><span data-ttu-id="a3535-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3535-269">1</span><span class="sxs-lookup"><span data-stu-id="a3535-269">1</span></span></td>
<td><span data-ttu-id="a3535-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3535-271">500.00</span><span class="sxs-lookup"><span data-stu-id="a3535-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-272">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-272">CC002</span></span></td>
<td><span data-ttu-id="a3535-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-273">Finance</span></span></td>
<td><span data-ttu-id="a3535-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3535-275">1</span><span class="sxs-lookup"><span data-stu-id="a3535-275">1</span></span></td>
<td><span data-ttu-id="a3535-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3535-277">500.00</span><span class="sxs-lookup"><span data-stu-id="a3535-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-278">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-278">CC003</span></span></td>
<td><span data-ttu-id="a3535-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-279">Assembly</span></span></td>
<td><span data-ttu-id="a3535-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a3535-281">0</span><span class="sxs-lookup"><span data-stu-id="a3535-281">0</span></span></td>
<td><span data-ttu-id="a3535-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a3535-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a3535-284">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-285">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-285">Journal</span></span></th>
<th><span data-ttu-id="a3535-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="a3535-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3535-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="a3535-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3535-288">version</span><span class="sxs-lookup"><span data-stu-id="a3535-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-289">00002</span><span class="sxs-lookup"><span data-stu-id="a3535-289">00002</span></span></td>
<td><span data-ttu-id="a3535-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="a3535-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="a3535-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="a3535-291">Fiscal</span></span></td>
<td><span data-ttu-id="a3535-292">2017</span><span class="sxs-lookup"><span data-stu-id="a3535-292">2017</span></span></td>
<td><span data-ttu-id="a3535-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-293">Period 1</span></span></td>
<td><span data-ttu-id="a3535-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3535-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="a3535-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-298">Cost element</span></span></th>
<th><span data-ttu-id="a3535-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-299">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-302">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-302">CC099</span></span></td>
<td><span data-ttu-id="a3535-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-303">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-304">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-304">10001</span></span></td>
<td><span data-ttu-id="a3535-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-305">Electricity</span></span></td>
<td><span data-ttu-id="a3535-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-306">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-309">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-309">CC099</span></span></td>
<td><span data-ttu-id="a3535-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-310">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-311">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-311">10001</span></span></td>
<td><span data-ttu-id="a3535-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-312">Electricity</span></span></td>
<td><span data-ttu-id="a3535-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-313">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a3535-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3535-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="a3535-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-317">Cost element</span></span></th>
<th><span data-ttu-id="a3535-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-318">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-319">Amount</span></span></th>
<th><span data-ttu-id="a3535-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-321">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-321">CC099</span></span></td>
<td><span data-ttu-id="a3535-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-322">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-323">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-323">10001</span></span></td>
<td><span data-ttu-id="a3535-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-324">Electricity</span></span></td>
<td><span data-ttu-id="a3535-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-325">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-326">-1,000.00</span></span></td>
<td><span data-ttu-id="a3535-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-328">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-328">CC001</span></span></td>
<td><span data-ttu-id="a3535-329">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-329">HR</span></span></td>
<td><span data-ttu-id="a3535-330">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-330">10001</span></span></td>
<td><span data-ttu-id="a3535-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-331">Electricity</span></span></td>
<td><span data-ttu-id="a3535-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-332">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-333">500.00</span><span class="sxs-lookup"><span data-stu-id="a3535-333">500.00</span></span></td>
<td><span data-ttu-id="a3535-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-335">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-335">CC002</span></span></td>
<td><span data-ttu-id="a3535-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-336">Finance</span></span></td>
<td><span data-ttu-id="a3535-337">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-337">10001</span></span></td>
<td><span data-ttu-id="a3535-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-338">Electricity</span></span></td>
<td><span data-ttu-id="a3535-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-339">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-340">500.00</span><span class="sxs-lookup"><span data-stu-id="a3535-340">500.00</span></span></td>
<td><span data-ttu-id="a3535-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-342">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-342">CC099</span></span></td>
<td><span data-ttu-id="a3535-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="a3535-343">Default cost center</span></span></td>
<td><span data-ttu-id="a3535-344">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-344">10001</span></span></td>
<td><span data-ttu-id="a3535-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-345">Electricity</span></span></td>
<td><span data-ttu-id="a3535-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-346">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="a3535-347">-9,000.00</span></span></td>
<td><span data-ttu-id="a3535-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-349">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-349">CC001</span></span></td>
<td><span data-ttu-id="a3535-350">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-350">HR</span></span></td>
<td><span data-ttu-id="a3535-351">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-351">10001</span></span></td>
<td><span data-ttu-id="a3535-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-352">Electricity</span></span></td>
<td><span data-ttu-id="a3535-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-353">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a3535-354">1,285.71</span></span></td>
<td><span data-ttu-id="a3535-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-356">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-356">CC002</span></span></td>
<td><span data-ttu-id="a3535-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-357">Finance</span></span></td>
<td><span data-ttu-id="a3535-358">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-358">10001</span></span></td>
<td><span data-ttu-id="a3535-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-359">Electricity</span></span></td>
<td><span data-ttu-id="a3535-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-360">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a3535-361">7,714.29</span></span></td>
<td><span data-ttu-id="a3535-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="a3535-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="a3535-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="a3535-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="a3535-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="a3535-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-367">Define the overhead rate</span></span>

<span data-ttu-id="a3535-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="a3535-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="a3535-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-370">Cost object</span></span></th>
<th><span data-ttu-id="a3535-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="a3535-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-372">Proj 1</span></span></td>
<td><span data-ttu-id="a3535-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-373">Project 1</span></span></td>
<td><span data-ttu-id="a3535-374">3</span><span class="sxs-lookup"><span data-stu-id="a3535-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-375">Proj 2</span></span></td>
<td><span data-ttu-id="a3535-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-376">Project 2</span></span></td>
<td><span data-ttu-id="a3535-377">1</span><span class="sxs-lookup"><span data-stu-id="a3535-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="a3535-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-379">Cost object</span></span></th>
<th><span data-ttu-id="a3535-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-380">Cost element</span></span></th>
<th><span data-ttu-id="a3535-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-381">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="a3535-382">Units</span></span></th>
<th><span data-ttu-id="a3535-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="a3535-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-384">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-384">CC001</span></span></td>
<td><span data-ttu-id="a3535-385">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-385">HR</span></span></td>
<td><span data-ttu-id="a3535-386">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-386">10001</span></span></td>
<td><span data-ttu-id="a3535-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-387">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-388">1</span><span class="sxs-lookup"><span data-stu-id="a3535-388">1</span></span></td>
<td><span data-ttu-id="a3535-389">10</span><span class="sxs-lookup"><span data-stu-id="a3535-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="a3535-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-391">Cost object</span></span></th>
<th><span data-ttu-id="a3535-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-392">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-393">Cost element</span></span></th>
<th><span data-ttu-id="a3535-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-394">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-396">Proj 1</span></span></td>
<td><span data-ttu-id="a3535-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-397">Project 1</span></span></td>
<td><span data-ttu-id="a3535-398">3</span><span class="sxs-lookup"><span data-stu-id="a3535-398">3</span></span></td>
<td><span data-ttu-id="a3535-399">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-399">10001</span></span></td>
<td><span data-ttu-id="a3535-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a3535-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a3535-401">30,00</span><span class="sxs-lookup"><span data-stu-id="a3535-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-402">Proj 2</span></span></td>
<td><span data-ttu-id="a3535-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-403">Project 2</span></span></td>
<td><span data-ttu-id="a3535-404">1</span><span class="sxs-lookup"><span data-stu-id="a3535-404">1</span></span></td>
<td><span data-ttu-id="a3535-405">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-405">10001</span></span></td>
<td><span data-ttu-id="a3535-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="a3535-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a3535-407">10,00</span><span class="sxs-lookup"><span data-stu-id="a3535-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a3535-408">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-409">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-409">Journal</span></span></th>
<th><span data-ttu-id="a3535-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="a3535-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3535-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="a3535-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3535-412">version</span><span class="sxs-lookup"><span data-stu-id="a3535-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-413">00003</span><span class="sxs-lookup"><span data-stu-id="a3535-413">00003</span></span></td>
<td><span data-ttu-id="a3535-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="a3535-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="a3535-415">Fiscal</span></span></td>
<td><span data-ttu-id="a3535-416">2017</span><span class="sxs-lookup"><span data-stu-id="a3535-416">2017</span></span></td>
<td><span data-ttu-id="a3535-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-417">Period 1</span></span></td>
<td><span data-ttu-id="a3535-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="a3535-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="a3535-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-421">Cost object</span></span></th>
<th><span data-ttu-id="a3535-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-424">Proj 1</span></span></td>
<td><span data-ttu-id="a3535-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a3535-426">3,00</span><span class="sxs-lookup"><span data-stu-id="a3535-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-428">Proj 2</span></span></td>
<td><span data-ttu-id="a3535-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a3535-430">1,00</span><span class="sxs-lookup"><span data-stu-id="a3535-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3535-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="a3535-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-433">Cost element</span></span></th>
<th><span data-ttu-id="a3535-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-434">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-435">Amount</span></span></th>
<th><span data-ttu-id="a3535-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="a3535-437">CC0001</span></span></td>
<td><span data-ttu-id="a3535-438">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-438">HR</span></span></td>
<td><span data-ttu-id="a3535-439">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-439">10001</span></span></td>
<td><span data-ttu-id="a3535-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-440">Electricity</span></span></td>
<td><span data-ttu-id="a3535-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-441">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="a3535-442">-30.00</span></span></td>
<td><span data-ttu-id="a3535-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-444">Proj 1</span></span></td>
<td><span data-ttu-id="a3535-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a3535-446">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-446">10001</span></span></td>
<td><span data-ttu-id="a3535-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-447">Electricity</span></span></td>
<td><span data-ttu-id="a3535-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-448">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-449">30,00</span><span class="sxs-lookup"><span data-stu-id="a3535-449">30.00</span></span></td>
<td><span data-ttu-id="a3535-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-451">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-451">CC001</span></span></td>
<td><span data-ttu-id="a3535-452">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-452">HR</span></span></td>
<td><span data-ttu-id="a3535-453">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-453">10001</span></span></td>
<td><span data-ttu-id="a3535-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-454">Electricity</span></span></td>
<td><span data-ttu-id="a3535-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-455">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="a3535-456">-10.00</span></span></td>
<td><span data-ttu-id="a3535-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-458">Proj 2</span></span></td>
<td><span data-ttu-id="a3535-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a3535-460">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-460">10001</span></span></td>
<td><span data-ttu-id="a3535-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-461">Electricity</span></span></td>
<td><span data-ttu-id="a3535-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-462">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-463">10,00</span><span class="sxs-lookup"><span data-stu-id="a3535-463">10.00</span></span></td>
<td><span data-ttu-id="a3535-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="a3535-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="a3535-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="a3535-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="a3535-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="a3535-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="a3535-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="a3535-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="a3535-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="a3535-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="a3535-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="a3535-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="a3535-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="a3535-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="a3535-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="a3535-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="a3535-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="a3535-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="a3535-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="a3535-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="a3535-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="a3535-475">Define the cost allocation</span></span>

<span data-ttu-id="a3535-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="a3535-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="a3535-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="a3535-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="a3535-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-479">Cost object</span></span></th>
<th><span data-ttu-id="a3535-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="a3535-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-481">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-481">CC002</span></span></td>
<td><span data-ttu-id="a3535-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-482">Finance</span></span></td>
<td><span data-ttu-id="a3535-483">35</span><span class="sxs-lookup"><span data-stu-id="a3535-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-484">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-484">CC003</span></span></td>
<td><span data-ttu-id="a3535-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-485">Assembly</span></span></td>
<td><span data-ttu-id="a3535-486">55</span><span class="sxs-lookup"><span data-stu-id="a3535-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-487">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-487">CC004</span></span></td>
<td><span data-ttu-id="a3535-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-488">Packaging</span></span></td>
<td><span data-ttu-id="a3535-489">10</span><span class="sxs-lookup"><span data-stu-id="a3535-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="a3535-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="a3535-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-492">Cost object</span></span></th>
<th><span data-ttu-id="a3535-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="a3535-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-494">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-494">CC003</span></span></td>
<td><span data-ttu-id="a3535-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-495">Assembly</span></span></td>
<td><span data-ttu-id="a3535-496">65</span><span class="sxs-lookup"><span data-stu-id="a3535-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-497">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-497">CC004</span></span></td>
<td><span data-ttu-id="a3535-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-498">Packaging</span></span></td>
<td><span data-ttu-id="a3535-499">35</span><span class="sxs-lookup"><span data-stu-id="a3535-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="a3535-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="a3535-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-502">Cost object</span></span></th>
<th><span data-ttu-id="a3535-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="a3535-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-504">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-505">Product 1</span></span></td>
<td><span data-ttu-id="a3535-506">60</span><span class="sxs-lookup"><span data-stu-id="a3535-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-507">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-508">Product 2</span></span></td>
<td><span data-ttu-id="a3535-509">20</span><span class="sxs-lookup"><span data-stu-id="a3535-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a3535-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="a3535-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="a3535-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-512">Cost object</span></span></th>
<th><span data-ttu-id="a3535-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="a3535-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-514">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-515">Product 1</span></span></td>
<td><span data-ttu-id="a3535-516">80</span><span class="sxs-lookup"><span data-stu-id="a3535-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-517">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-518">Product 2</span></span></td>
<td><span data-ttu-id="a3535-519">15</span><span class="sxs-lookup"><span data-stu-id="a3535-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a3535-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="a3535-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="a3535-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="a3535-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="a3535-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="a3535-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-523">Cost object</span></span></th>
<th><span data-ttu-id="a3535-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-524">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-525">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-526">Amount</span></span></th>
<th><span data-ttu-id="a3535-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-528">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-528">CC002</span></span></td>
<td><span data-ttu-id="a3535-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-529">Finance</span></span></td>
<td><span data-ttu-id="a3535-530">35</span><span class="sxs-lookup"><span data-stu-id="a3535-530">35</span></span></td>
<td><span data-ttu-id="a3535-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3535-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3535-532">175.00</span><span class="sxs-lookup"><span data-stu-id="a3535-532">175.00</span></span></td>
<td><span data-ttu-id="a3535-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-534">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-534">CC003</span></span></td>
<td><span data-ttu-id="a3535-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-535">Assembly</span></span></td>
<td><span data-ttu-id="a3535-536">55</span><span class="sxs-lookup"><span data-stu-id="a3535-536">55</span></span></td>
<td><span data-ttu-id="a3535-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3535-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3535-538">275.00</span><span class="sxs-lookup"><span data-stu-id="a3535-538">275.00</span></span></td>
<td><span data-ttu-id="a3535-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-540">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-540">CC004</span></span></td>
<td><span data-ttu-id="a3535-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-541">Packaging</span></span></td>
<td><span data-ttu-id="a3535-542">10</span><span class="sxs-lookup"><span data-stu-id="a3535-542">10</span></span></td>
<td><span data-ttu-id="a3535-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="a3535-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a3535-544">50,00</span><span class="sxs-lookup"><span data-stu-id="a3535-544">50.00</span></span></td>
<td><span data-ttu-id="a3535-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-546">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-546">CC002</span></span></td>
<td><span data-ttu-id="a3535-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-547">Finance</span></span></td>
<td><span data-ttu-id="a3535-548">35</span><span class="sxs-lookup"><span data-stu-id="a3535-548">35</span></span></td>
<td><span data-ttu-id="a3535-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="a3535-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3535-550">436.00</span><span class="sxs-lookup"><span data-stu-id="a3535-550">436.00</span></span></td>
<td><span data-ttu-id="a3535-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-552">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-552">CC003</span></span></td>
<td><span data-ttu-id="a3535-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-553">Assembly</span></span></td>
<td><span data-ttu-id="a3535-554">55</span><span class="sxs-lookup"><span data-stu-id="a3535-554">55</span></span></td>
<td><span data-ttu-id="a3535-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="a3535-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3535-556">685.14</span><span class="sxs-lookup"><span data-stu-id="a3535-556">685.14</span></span></td>
<td><span data-ttu-id="a3535-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-558">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-558">CC004</span></span></td>
<td><span data-ttu-id="a3535-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-559">Packaging</span></span></td>
<td><span data-ttu-id="a3535-560">10</span><span class="sxs-lookup"><span data-stu-id="a3535-560">10</span></span></td>
<td><span data-ttu-id="a3535-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="a3535-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a3535-562">124.57</span><span class="sxs-lookup"><span data-stu-id="a3535-562">124.57</span></span></td>
<td><span data-ttu-id="a3535-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="a3535-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-565">Cost object</span></span></th>
<th><span data-ttu-id="a3535-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-566">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-567">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-568">Amount</span></span></th>
<th><span data-ttu-id="a3535-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-570">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-570">CC003</span></span></td>
<td><span data-ttu-id="a3535-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-571">Assembly</span></span></td>
<td><span data-ttu-id="a3535-572">65</span><span class="sxs-lookup"><span data-stu-id="a3535-572">65</span></span></td>
<td><span data-ttu-id="a3535-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a3535-574">438.75</span><span class="sxs-lookup"><span data-stu-id="a3535-574">438.75</span></span></td>
<td><span data-ttu-id="a3535-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-576">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-576">CC004</span></span></td>
<td><span data-ttu-id="a3535-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-577">Packaging</span></span></td>
<td><span data-ttu-id="a3535-578">35</span><span class="sxs-lookup"><span data-stu-id="a3535-578">35</span></span></td>
<td><span data-ttu-id="a3535-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a3535-580">236.25</span><span class="sxs-lookup"><span data-stu-id="a3535-580">236.25</span></span></td>
<td><span data-ttu-id="a3535-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-582">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-582">CC003</span></span></td>
<td><span data-ttu-id="a3535-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-583">Assembly</span></span></td>
<td><span data-ttu-id="a3535-584">65</span><span class="sxs-lookup"><span data-stu-id="a3535-584">65</span></span></td>
<td><span data-ttu-id="a3535-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a3535-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a3535-586">5,297.69</span></span></td>
<td><span data-ttu-id="a3535-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-588">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-588">CC004</span></span></td>
<td><span data-ttu-id="a3535-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-589">Packaging</span></span></td>
<td><span data-ttu-id="a3535-590">35</span><span class="sxs-lookup"><span data-stu-id="a3535-590">35</span></span></td>
<td><span data-ttu-id="a3535-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="a3535-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a3535-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a3535-592">2,852.60</span></span></td>
<td><span data-ttu-id="a3535-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="a3535-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-595">Cost object</span></span></th>
<th><span data-ttu-id="a3535-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-596">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-597">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-598">Amount</span></span></th>
<th><span data-ttu-id="a3535-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-600">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-601">Product 1</span></span></td>
<td><span data-ttu-id="a3535-602">60</span><span class="sxs-lookup"><span data-stu-id="a3535-602">60</span></span></td>
<td><span data-ttu-id="a3535-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a3535-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a3535-604">535.31</span><span class="sxs-lookup"><span data-stu-id="a3535-604">535.31</span></span></td>
<td><span data-ttu-id="a3535-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-606">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-607">Product 2</span></span></td>
<td><span data-ttu-id="a3535-608">20</span><span class="sxs-lookup"><span data-stu-id="a3535-608">20</span></span></td>
<td><span data-ttu-id="a3535-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="a3535-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a3535-610">178.44</span><span class="sxs-lookup"><span data-stu-id="a3535-610">178.44</span></span></td>
<td><span data-ttu-id="a3535-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-612">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-613">Product 1</span></span></td>
<td><span data-ttu-id="a3535-614">60</span><span class="sxs-lookup"><span data-stu-id="a3535-614">60</span></span></td>
<td><span data-ttu-id="a3535-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a3535-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a3535-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a3535-616">4,487.12</span></span></td>
<td><span data-ttu-id="a3535-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-618">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-619">Product 2</span></span></td>
<td><span data-ttu-id="a3535-620">20</span><span class="sxs-lookup"><span data-stu-id="a3535-620">20</span></span></td>
<td><span data-ttu-id="a3535-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="a3535-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a3535-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a3535-622">1,495.71</span></span></td>
<td><span data-ttu-id="a3535-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3535-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="a3535-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-625">Cost object</span></span></th>
<th><span data-ttu-id="a3535-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="a3535-626">Magnitude</span></span></th>
<th><span data-ttu-id="a3535-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="a3535-627">Allocation factor</span></span></th>
<th><span data-ttu-id="a3535-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-628">Amount</span></span></th>
<th><span data-ttu-id="a3535-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-630">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-631">Product 1</span></span></td>
<td><span data-ttu-id="a3535-632">80</span><span class="sxs-lookup"><span data-stu-id="a3535-632">80</span></span></td>
<td><span data-ttu-id="a3535-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a3535-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a3535-634">241.05</span><span class="sxs-lookup"><span data-stu-id="a3535-634">241.05</span></span></td>
<td><span data-ttu-id="a3535-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-636">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-637">Product 2</span></span></td>
<td><span data-ttu-id="a3535-638">15</span><span class="sxs-lookup"><span data-stu-id="a3535-638">15</span></span></td>
<td><span data-ttu-id="a3535-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="a3535-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a3535-640">45.20</span><span class="sxs-lookup"><span data-stu-id="a3535-640">45.20</span></span></td>
<td><span data-ttu-id="a3535-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-642">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-643">Product 1</span></span></td>
<td><span data-ttu-id="a3535-644">80</span><span class="sxs-lookup"><span data-stu-id="a3535-644">80</span></span></td>
<td><span data-ttu-id="a3535-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a3535-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a3535-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a3535-646">2,507.09</span></span></td>
<td><span data-ttu-id="a3535-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-648">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-649">Product 2</span></span></td>
<td><span data-ttu-id="a3535-650">15</span><span class="sxs-lookup"><span data-stu-id="a3535-650">15</span></span></td>
<td><span data-ttu-id="a3535-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="a3535-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a3535-652">470.08</span><span class="sxs-lookup"><span data-stu-id="a3535-652">470.08</span></span></td>
<td><span data-ttu-id="a3535-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a3535-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="a3535-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-655">Journal</span><span class="sxs-lookup"><span data-stu-id="a3535-655">Journal</span></span></th>
<th><span data-ttu-id="a3535-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="a3535-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a3535-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="a3535-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a3535-658">version</span><span class="sxs-lookup"><span data-stu-id="a3535-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-659">00004</span><span class="sxs-lookup"><span data-stu-id="a3535-659">00004</span></span></td>
<td><span data-ttu-id="a3535-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="a3535-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="a3535-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="a3535-661">Fiscal</span></span></td>
<td><span data-ttu-id="a3535-662">2017</span><span class="sxs-lookup"><span data-stu-id="a3535-662">2017</span></span></td>
<td><span data-ttu-id="a3535-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-663">Period 1</span></span></td>
<td><span data-ttu-id="a3535-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="a3535-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="a3535-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="a3535-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a3535-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-668">Cost element</span></span></th>
<th><span data-ttu-id="a3535-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-669">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-672">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-672">CC001</span></span></td>
<td><span data-ttu-id="a3535-673">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-673">HR</span></span></td>
<td><span data-ttu-id="a3535-674">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-674">10001</span></span></td>
<td><span data-ttu-id="a3535-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-675">Electricity</span></span></td>
<td><span data-ttu-id="a3535-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-676">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-677">500.00</span><span class="sxs-lookup"><span data-stu-id="a3535-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-679">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-679">CC001</span></span></td>
<td><span data-ttu-id="a3535-680">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-680">HR</span></span></td>
<td><span data-ttu-id="a3535-681">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-681">10001</span></span></td>
<td><span data-ttu-id="a3535-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-682">Electricity</span></span></td>
<td><span data-ttu-id="a3535-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-683">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="a3535-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-686">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-686">CC002</span></span></td>
<td><span data-ttu-id="a3535-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-687">Finance</span></span></td>
<td><span data-ttu-id="a3535-688">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-688">10001</span></span></td>
<td><span data-ttu-id="a3535-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-689">Electricity</span></span></td>
<td><span data-ttu-id="a3535-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-690">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-691">675.00</span><span class="sxs-lookup"><span data-stu-id="a3535-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-693">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-693">CC002</span></span></td>
<td><span data-ttu-id="a3535-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-694">Finance</span></span></td>
<td><span data-ttu-id="a3535-695">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-695">10001</span></span></td>
<td><span data-ttu-id="a3535-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-696">Electricity</span></span></td>
<td><span data-ttu-id="a3535-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-697">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="a3535-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-700">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-700">CC003</span></span></td>
<td><span data-ttu-id="a3535-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-701">Assembly</span></span></td>
<td><span data-ttu-id="a3535-702">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-702">10001</span></span></td>
<td><span data-ttu-id="a3535-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-703">Electricity</span></span></td>
<td><span data-ttu-id="a3535-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-704">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-705">713.75</span><span class="sxs-lookup"><span data-stu-id="a3535-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-707">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-707">CC003</span></span></td>
<td><span data-ttu-id="a3535-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-708">Assembly</span></span></td>
<td><span data-ttu-id="a3535-709">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-709">10001</span></span></td>
<td><span data-ttu-id="a3535-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-710">Electricity</span></span></td>
<td><span data-ttu-id="a3535-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-711">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="a3535-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-714">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-714">CC003</span></span></td>
<td><span data-ttu-id="a3535-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-715">Packaging</span></span></td>
<td><span data-ttu-id="a3535-716">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-716">10001</span></span></td>
<td><span data-ttu-id="a3535-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-717">Electricity</span></span></td>
<td><span data-ttu-id="a3535-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-718">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-719">286.25</span><span class="sxs-lookup"><span data-stu-id="a3535-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-721">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-721">CC003</span></span></td>
<td><span data-ttu-id="a3535-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-722">Packaging</span></span></td>
<td><span data-ttu-id="a3535-723">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-723">10001</span></span></td>
<td><span data-ttu-id="a3535-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-724">Electricity</span></span></td>
<td><span data-ttu-id="a3535-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-725">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="a3535-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-728">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-729">Product 1</span></span></td>
<td><span data-ttu-id="a3535-730">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-730">10001</span></span></td>
<td><span data-ttu-id="a3535-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-731">Electricity</span></span></td>
<td><span data-ttu-id="a3535-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-732">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-733">776.36</span><span class="sxs-lookup"><span data-stu-id="a3535-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-735">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-736">Product 1</span></span></td>
<td><span data-ttu-id="a3535-737">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-737">10001</span></span></td>
<td><span data-ttu-id="a3535-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-738">Electricity</span></span></td>
<td><span data-ttu-id="a3535-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-739">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a3535-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-742">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-743">Product 1</span></span></td>
<td><span data-ttu-id="a3535-744">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-744">10001</span></span></td>
<td><span data-ttu-id="a3535-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-745">Electricity</span></span></td>
<td><span data-ttu-id="a3535-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-746">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-747">223.64</span><span class="sxs-lookup"><span data-stu-id="a3535-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="a3535-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-749">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-750">Product 1</span></span></td>
<td><span data-ttu-id="a3535-751">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-751">10001</span></span></td>
<td><span data-ttu-id="a3535-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-752">Electricity</span></span></td>
<td><span data-ttu-id="a3535-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-753">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a3535-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a3535-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="a3535-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a3535-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a3535-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-757">Cost element</span></span></th>
<th><span data-ttu-id="a3535-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="a3535-758">Cost behavior</span></span></th>
<th><span data-ttu-id="a3535-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="a3535-759">Amount</span></span></th>
<th><span data-ttu-id="a3535-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="a3535-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a3535-761">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-761">CC001</span></span></td>
<td><span data-ttu-id="a3535-762">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-762">HR</span></span></td>
<td><span data-ttu-id="a3535-763">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-763">10001</span></span></td>
<td><span data-ttu-id="a3535-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-764">Electricity</span></span></td>
<td><span data-ttu-id="a3535-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-765">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="a3535-766">-500.00</span></span></td>
<td><span data-ttu-id="a3535-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-768">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-768">CC002</span></span></td>
<td><span data-ttu-id="a3535-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-769">Finance</span></span></td>
<td><span data-ttu-id="a3535-770">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-770">10001</span></span></td>
<td><span data-ttu-id="a3535-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-771">Electricity</span></span></td>
<td><span data-ttu-id="a3535-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-772">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-773">175.00</span><span class="sxs-lookup"><span data-stu-id="a3535-773">175.00</span></span></td>
<td><span data-ttu-id="a3535-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-775">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-775">CC003</span></span></td>
<td><span data-ttu-id="a3535-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-776">Assembly</span></span></td>
<td><span data-ttu-id="a3535-777">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-777">10001</span></span></td>
<td><span data-ttu-id="a3535-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-778">Electricity</span></span></td>
<td><span data-ttu-id="a3535-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-779">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-780">275.00</span><span class="sxs-lookup"><span data-stu-id="a3535-780">275.00</span></span></td>
<td><span data-ttu-id="a3535-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-782">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-782">CC004</span></span></td>
<td><span data-ttu-id="a3535-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-783">Packaging</span></span></td>
<td><span data-ttu-id="a3535-784">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-784">10001</span></span></td>
<td><span data-ttu-id="a3535-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-785">Electricity</span></span></td>
<td><span data-ttu-id="a3535-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-786">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-787">50,00</span><span class="sxs-lookup"><span data-stu-id="a3535-787">50,00</span></span></td>
<td><span data-ttu-id="a3535-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-789">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-789">CC001</span></span></td>
<td><span data-ttu-id="a3535-790">Personal</span><span class="sxs-lookup"><span data-stu-id="a3535-790">HR</span></span></td>
<td><span data-ttu-id="a3535-791">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-791">10001</span></span></td>
<td><span data-ttu-id="a3535-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-792">Electricity</span></span></td>
<td><span data-ttu-id="a3535-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-793">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="a3535-794">-1,245.71</span></span></td>
<td><span data-ttu-id="a3535-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-796">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-796">CC002</span></span></td>
<td><span data-ttu-id="a3535-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-797">Finance</span></span></td>
<td><span data-ttu-id="a3535-798">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-798">10001</span></span></td>
<td><span data-ttu-id="a3535-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-799">Electricity</span></span></td>
<td><span data-ttu-id="a3535-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-800">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-801">436.00</span><span class="sxs-lookup"><span data-stu-id="a3535-801">436.00</span></span></td>
<td><span data-ttu-id="a3535-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-803">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-803">CC003</span></span></td>
<td><span data-ttu-id="a3535-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-804">Assembly</span></span></td>
<td><span data-ttu-id="a3535-805">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-805">10001</span></span></td>
<td><span data-ttu-id="a3535-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-806">Electricity</span></span></td>
<td><span data-ttu-id="a3535-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-807">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-808">685.14</span><span class="sxs-lookup"><span data-stu-id="a3535-808">685.14</span></span></td>
<td><span data-ttu-id="a3535-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-810">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-810">CC004</span></span></td>
<td><span data-ttu-id="a3535-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-811">Packaging</span></span></td>
<td><span data-ttu-id="a3535-812">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-812">10001</span></span></td>
<td><span data-ttu-id="a3535-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-813">Electricity</span></span></td>
<td><span data-ttu-id="a3535-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-814">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-815">124.57</span><span class="sxs-lookup"><span data-stu-id="a3535-815">124.57</span></span></td>
<td><span data-ttu-id="a3535-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-817">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-817">CC002</span></span></td>
<td><span data-ttu-id="a3535-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-818">Finance</span></span></td>
<td><span data-ttu-id="a3535-819">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-819">10001</span></span></td>
<td><span data-ttu-id="a3535-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-820">Electricity</span></span></td>
<td><span data-ttu-id="a3535-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-821">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="a3535-822">-675.00</span></span></td>
<td><span data-ttu-id="a3535-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-824">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-824">CC003</span></span></td>
<td><span data-ttu-id="a3535-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-825">Assembly</span></span></td>
<td><span data-ttu-id="a3535-826">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-826">10001</span></span></td>
<td><span data-ttu-id="a3535-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-827">Electricity</span></span></td>
<td><span data-ttu-id="a3535-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-828">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-829">438.75</span><span class="sxs-lookup"><span data-stu-id="a3535-829">438.75</span></span></td>
<td><span data-ttu-id="a3535-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-831">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-831">CC004</span></span></td>
<td><span data-ttu-id="a3535-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-832">Packaging</span></span></td>
<td><span data-ttu-id="a3535-833">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-833">10001</span></span></td>
<td><span data-ttu-id="a3535-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-834">Electricity</span></span></td>
<td><span data-ttu-id="a3535-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-835">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-836">236.25</span><span class="sxs-lookup"><span data-stu-id="a3535-836">236.25</span></span></td>
<td><span data-ttu-id="a3535-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-838">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-838">CC002</span></span></td>
<td><span data-ttu-id="a3535-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="a3535-839">Finance</span></span></td>
<td><span data-ttu-id="a3535-840">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-840">10001</span></span></td>
<td><span data-ttu-id="a3535-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-841">Electricity</span></span></td>
<td><span data-ttu-id="a3535-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-842">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="a3535-843">-8,150.29</span></span></td>
<td><span data-ttu-id="a3535-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-845">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-845">CC003</span></span></td>
<td><span data-ttu-id="a3535-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-846">Assembly</span></span></td>
<td><span data-ttu-id="a3535-847">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-847">10001</span></span></td>
<td><span data-ttu-id="a3535-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-848">Electricity</span></span></td>
<td><span data-ttu-id="a3535-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-849">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a3535-850">5,297.69</span></span></td>
<td><span data-ttu-id="a3535-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-852">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-852">CC004</span></span></td>
<td><span data-ttu-id="a3535-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="a3535-853">Packaging</span></span></td>
<td><span data-ttu-id="a3535-854">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-854">10001</span></span></td>
<td><span data-ttu-id="a3535-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-855">Electricity</span></span></td>
<td><span data-ttu-id="a3535-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-856">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a3535-857">2,852.60</span></span></td>
<td><span data-ttu-id="a3535-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-859">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-859">CC003</span></span></td>
<td><span data-ttu-id="a3535-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-860">Assembly</span></span></td>
<td><span data-ttu-id="a3535-861">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-861">10001</span></span></td>
<td><span data-ttu-id="a3535-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-862">Electricity</span></span></td>
<td><span data-ttu-id="a3535-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-863">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="a3535-864">-713.75</span></span></td>
<td><span data-ttu-id="a3535-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-866">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-867">Product 1</span></span></td>
<td><span data-ttu-id="a3535-868">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-868">10001</span></span></td>
<td><span data-ttu-id="a3535-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-869">Electricity</span></span></td>
<td><span data-ttu-id="a3535-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-870">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-871">535.31</span><span class="sxs-lookup"><span data-stu-id="a3535-871">535.31</span></span></td>
<td><span data-ttu-id="a3535-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-873">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-874">Product 2</span></span></td>
<td><span data-ttu-id="a3535-875">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-875">10001</span></span></td>
<td><span data-ttu-id="a3535-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-876">Electricity</span></span></td>
<td><span data-ttu-id="a3535-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-877">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-878">178.44</span><span class="sxs-lookup"><span data-stu-id="a3535-878">178.44</span></span></td>
<td><span data-ttu-id="a3535-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-880">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-880">CC003</span></span></td>
<td><span data-ttu-id="a3535-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-881">Assembly</span></span></td>
<td><span data-ttu-id="a3535-882">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-882">10001</span></span></td>
<td><span data-ttu-id="a3535-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-883">Electricity</span></span></td>
<td><span data-ttu-id="a3535-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-884">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="a3535-885">-5,982.83</span></span></td>
<td><span data-ttu-id="a3535-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-887">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-888">Product 1</span></span></td>
<td><span data-ttu-id="a3535-889">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-889">10001</span></span></td>
<td><span data-ttu-id="a3535-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-890">Electricity</span></span></td>
<td><span data-ttu-id="a3535-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-891">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a3535-892">4,487.12</span></span></td>
<td><span data-ttu-id="a3535-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-894">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-895">Product 2</span></span></td>
<td><span data-ttu-id="a3535-896">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-896">10001</span></span></td>
<td><span data-ttu-id="a3535-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-897">Electricity</span></span></td>
<td><span data-ttu-id="a3535-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-898">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a3535-899">1,495.71</span></span></td>
<td><span data-ttu-id="a3535-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-901">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-901">CC003</span></span></td>
<td><span data-ttu-id="a3535-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-902">Assembly</span></span></td>
<td><span data-ttu-id="a3535-903">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-903">10001</span></span></td>
<td><span data-ttu-id="a3535-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-904">Electricity</span></span></td>
<td><span data-ttu-id="a3535-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-905">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="a3535-906">-286.25</span></span></td>
<td><span data-ttu-id="a3535-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-908">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-909">Product 1</span></span></td>
<td><span data-ttu-id="a3535-910">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-910">10001</span></span></td>
<td><span data-ttu-id="a3535-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-911">Electricity</span></span></td>
<td><span data-ttu-id="a3535-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-912">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-913">241.05</span><span class="sxs-lookup"><span data-stu-id="a3535-913">241.05</span></span></td>
<td><span data-ttu-id="a3535-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-915">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-916">Product 2</span></span></td>
<td><span data-ttu-id="a3535-917">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-917">10001</span></span></td>
<td><span data-ttu-id="a3535-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-918">Electricity</span></span></td>
<td><span data-ttu-id="a3535-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-919">Fixed cost</span></span></td>
<td><span data-ttu-id="a3535-920">45.20</span><span class="sxs-lookup"><span data-stu-id="a3535-920">45.20</span></span></td>
<td><span data-ttu-id="a3535-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-922">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-922">CC003</span></span></td>
<td><span data-ttu-id="a3535-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="a3535-923">Assembly</span></span></td>
<td><span data-ttu-id="a3535-924">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-924">10001</span></span></td>
<td><span data-ttu-id="a3535-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-925">Electricity</span></span></td>
<td><span data-ttu-id="a3535-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-926">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="a3535-927">-2,977.17</span></span></td>
<td><span data-ttu-id="a3535-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-929">Prod 1</span></span></td>
<td><span data-ttu-id="a3535-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="a3535-930">Product 1</span></span></td>
<td><span data-ttu-id="a3535-931">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-931">10001</span></span></td>
<td><span data-ttu-id="a3535-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-932">Electricity</span></span></td>
<td><span data-ttu-id="a3535-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-933">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a3535-934">2,507.09</span></span></td>
<td><span data-ttu-id="a3535-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a3535-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-936">Prod 2</span></span></td>
<td><span data-ttu-id="a3535-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="a3535-937">Product 2</span></span></td>
<td><span data-ttu-id="a3535-938">10001</span><span class="sxs-lookup"><span data-stu-id="a3535-938">10001</span></span></td>
<td><span data-ttu-id="a3535-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-939">Electricity</span></span></td>
<td><span data-ttu-id="a3535-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-940">Variable cost</span></span></td>
<td><span data-ttu-id="a3535-941">470.08</span><span class="sxs-lookup"><span data-stu-id="a3535-941">470.08</span></span></td>
<td><span data-ttu-id="a3535-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="a3535-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="a3535-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="a3535-943">Conclusion</span></span>
<span data-ttu-id="a3535-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="a3535-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="a3535-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="a3535-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="a3535-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a3535-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="a3535-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="a3535-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="a3535-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="a3535-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="a3535-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="a3535-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="a3535-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="a3535-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a3535-951">CC099</span><span class="sxs-lookup"><span data-stu-id="a3535-951">CC099</span></span></th>
<th><span data-ttu-id="a3535-952">CC001</span><span class="sxs-lookup"><span data-stu-id="a3535-952">CC001</span></span></th>
<th><span data-ttu-id="a3535-953">CC002</span><span class="sxs-lookup"><span data-stu-id="a3535-953">CC002</span></span></th>
<th><span data-ttu-id="a3535-954">CC003</span><span class="sxs-lookup"><span data-stu-id="a3535-954">CC003</span></span></th>
<th><span data-ttu-id="a3535-955">CC004</span><span class="sxs-lookup"><span data-stu-id="a3535-955">CC004</span></span></th>
<th><span data-ttu-id="a3535-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a3535-956">Proj 1</span></span></th>
<th><span data-ttu-id="a3535-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a3535-957">Proj 2</span></span></th>
<th><span data-ttu-id="a3535-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="a3535-958">Prod 1</span></span></th>
<th><span data-ttu-id="a3535-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="a3535-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="a3535-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="a3535-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a3535-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="a3535-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="a3535-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-971">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="a3535-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-973">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-974">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-975">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-976">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-977">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a3535-978">776.36</span><span class="sxs-lookup"><span data-stu-id="a3535-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-979">223.64</span><span class="sxs-lookup"><span data-stu-id="a3535-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="a3535-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="a3535-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-982">000</span><span class="sxs-lookup"><span data-stu-id="a3535-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-983">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-984">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-985">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-986">0,00</span><span class="sxs-lookup"><span data-stu-id="a3535-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-987">30,00</span><span class="sxs-lookup"><span data-stu-id="a3535-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-988">10,00</span><span class="sxs-lookup"><span data-stu-id="a3535-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a3535-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a3535-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a3535-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="a3535-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a3535-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="a3535-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="a3535-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3535-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="a3535-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="a3535-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="a3535-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="a3535-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="a3535-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="a3535-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]