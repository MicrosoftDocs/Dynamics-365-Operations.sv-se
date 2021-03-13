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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: d60248f2bd6774b2e9afdb3632b6eb31d67349ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009528"
---
# <a name="overhead-calculation"></a><span data-ttu-id="c1457-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="c1457-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1457-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="c1457-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="c1457-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="c1457-105">Term definition</span></span>
---------------

<span data-ttu-id="c1457-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="c1457-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c1457-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="c1457-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c1457-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="c1457-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c1457-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="c1457-109">Rent</span></span>
-   <span data-ttu-id="c1457-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-110">Electricity</span></span>
-   <span data-ttu-id="c1457-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="c1457-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c1457-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="c1457-112">Overhead calculation overview</span></span>
<span data-ttu-id="c1457-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="c1457-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c1457-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="c1457-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c1457-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="c1457-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c1457-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="c1457-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c1457-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="c1457-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c1457-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="c1457-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c1457-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="c1457-119">Version type</span></span>
-   <span data-ttu-id="c1457-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="c1457-120">Date and time</span></span>
-   <span data-ttu-id="c1457-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="c1457-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c1457-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="c1457-122">Fiscal year</span></span>
-   <span data-ttu-id="c1457-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="c1457-123">Fiscal period</span></span>

<span data-ttu-id="c1457-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="c1457-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c1457-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="c1457-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c1457-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="c1457-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c1457-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="c1457-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c1457-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="c1457-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c1457-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="c1457-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c1457-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="c1457-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="c1457-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c1457-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c1457-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="c1457-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c1457-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="c1457-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c1457-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="c1457-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c1457-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="c1457-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c1457-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="c1457-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c1457-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="c1457-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="c1457-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="c1457-140">Main account</span></span></th>
<th><span data-ttu-id="c1457-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="c1457-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c1457-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-143">CC099</span></span></td>
<td><span data-ttu-id="c1457-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-144">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-145">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-145">10001</span></span></td>
<td><span data-ttu-id="c1457-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-146">Electricity</span></span></td>
<td><span data-ttu-id="c1457-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c1457-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c1457-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="c1457-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c1457-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="c1457-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c1457-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="c1457-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c1457-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="c1457-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c1457-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="c1457-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c1457-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c1457-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c1457-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="c1457-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c1457-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c1457-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="c1457-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c1457-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="c1457-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c1457-159">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-160">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-160">Journal</span></span></th>
<th><span data-ttu-id="c1457-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="c1457-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c1457-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="c1457-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c1457-163">version</span><span class="sxs-lookup"><span data-stu-id="c1457-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-164">00001</span><span class="sxs-lookup"><span data-stu-id="c1457-164">00001</span></span></td>
<td><span data-ttu-id="c1457-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c1457-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="c1457-166">Fiscal</span></span></td>
<td><span data-ttu-id="c1457-167">2017</span><span class="sxs-lookup"><span data-stu-id="c1457-167">2017</span></span></td>
<td><span data-ttu-id="c1457-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-168">Period 1</span></span></td>
<td><span data-ttu-id="c1457-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c1457-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="c1457-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-173">Cost element</span></span></th>
<th><span data-ttu-id="c1457-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c1457-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-177">CC099</span></span></td>
<td><span data-ttu-id="c1457-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-178">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-179">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-179">10001</span></span></td>
<td><span data-ttu-id="c1457-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-180">Electricity</span></span></td>
<td><span data-ttu-id="c1457-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="c1457-181">Unclassified</span></span></td>
<td><span data-ttu-id="c1457-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c1457-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="c1457-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-185">Cost element</span></span></th>
<th><span data-ttu-id="c1457-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-187">Amount</span></span></th>
<th><span data-ttu-id="c1457-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-189">CC099</span></span></td>
<td><span data-ttu-id="c1457-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-190">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-191">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-191">10001</span></span></td>
<td><span data-ttu-id="c1457-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-192">Electricity</span></span></td>
<td><span data-ttu-id="c1457-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="c1457-193">Unclassified</span></span></td>
<td><span data-ttu-id="c1457-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-194">10,000.00</span></span></td>
<td><span data-ttu-id="c1457-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-196">CC099</span></span></td>
<td><span data-ttu-id="c1457-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-197">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-198">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-198">10001</span></span></td>
<td><span data-ttu-id="c1457-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-199">Electricity</span></span></td>
<td><span data-ttu-id="c1457-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="c1457-200">Unclassified</span></span></td>
<td><span data-ttu-id="c1457-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c1457-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-203">CC099</span></span></td>
<td><span data-ttu-id="c1457-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-204">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-205">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-205">10001</span></span></td>
<td><span data-ttu-id="c1457-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-206">Electricity</span></span></td>
<td><span data-ttu-id="c1457-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-208">1,000.00</span></span></td>
<td><span data-ttu-id="c1457-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-210">CC099</span></span></td>
<td><span data-ttu-id="c1457-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-211">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-212">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-212">10001</span></span></td>
<td><span data-ttu-id="c1457-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-213">Electricity</span></span></td>
<td><span data-ttu-id="c1457-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-214">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c1457-215">9,000.00</span></span></td>
<td><span data-ttu-id="c1457-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c1457-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c1457-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="c1457-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c1457-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c1457-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c1457-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="c1457-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c1457-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="c1457-221">Define the cost distribution rule</span></span>

<span data-ttu-id="c1457-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="c1457-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c1457-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="c1457-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c1457-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="c1457-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c1457-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c1457-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c1457-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="c1457-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c1457-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c1457-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-228">Cost object</span></span></th>
<th><span data-ttu-id="c1457-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="c1457-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-230">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-230">CC001</span></span></td>
<td><span data-ttu-id="c1457-231">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-231">HR</span></span></td>
<td><span data-ttu-id="c1457-232">1 000</span><span class="sxs-lookup"><span data-stu-id="c1457-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-233">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-233">CC002</span></span></td>
<td><span data-ttu-id="c1457-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-234">Finance</span></span></td>
<td><span data-ttu-id="c1457-235">6,000</span><span class="sxs-lookup"><span data-stu-id="c1457-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-236">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-236">CC003</span></span></td>
<td><span data-ttu-id="c1457-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-237">Assembly</span></span></td>
<td><span data-ttu-id="c1457-238">0</span><span class="sxs-lookup"><span data-stu-id="c1457-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="c1457-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-240">Cost object</span></span></th>
<th><span data-ttu-id="c1457-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-241">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-242">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-244">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-244">CC001</span></span></td>
<td><span data-ttu-id="c1457-245">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-245">HR</span></span></td>
<td><span data-ttu-id="c1457-246">1 000</span><span class="sxs-lookup"><span data-stu-id="c1457-246">1,000</span></span></td>
<td><span data-ttu-id="c1457-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c1457-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c1457-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-249">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-249">CC002</span></span></td>
<td><span data-ttu-id="c1457-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-250">Finance</span></span></td>
<td><span data-ttu-id="c1457-251">6,000</span><span class="sxs-lookup"><span data-stu-id="c1457-251">6,000</span></span></td>
<td><span data-ttu-id="c1457-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c1457-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c1457-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-254">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-254">CC003</span></span></td>
<td><span data-ttu-id="c1457-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-255">Assembly</span></span></td>
<td><span data-ttu-id="c1457-256">0</span><span class="sxs-lookup"><span data-stu-id="c1457-256">0</span></span></td>
<td><span data-ttu-id="c1457-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c1457-258">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="c1457-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c1457-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="c1457-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-261">Cost object</span></span></th>
<th><span data-ttu-id="c1457-262">Formel</span><span class="sxs-lookup"><span data-stu-id="c1457-262">Formula</span></span></th>
<th><span data-ttu-id="c1457-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-263">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-264">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-266">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-266">CC001</span></span></td>
<td><span data-ttu-id="c1457-267">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-267">HR</span></span></td>
<td><span data-ttu-id="c1457-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c1457-269">1</span><span class="sxs-lookup"><span data-stu-id="c1457-269">1</span></span></td>
<td><span data-ttu-id="c1457-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c1457-271">500.00</span><span class="sxs-lookup"><span data-stu-id="c1457-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-272">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-272">CC002</span></span></td>
<td><span data-ttu-id="c1457-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-273">Finance</span></span></td>
<td><span data-ttu-id="c1457-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c1457-275">1</span><span class="sxs-lookup"><span data-stu-id="c1457-275">1</span></span></td>
<td><span data-ttu-id="c1457-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c1457-277">500.00</span><span class="sxs-lookup"><span data-stu-id="c1457-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-278">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-278">CC003</span></span></td>
<td><span data-ttu-id="c1457-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-279">Assembly</span></span></td>
<td><span data-ttu-id="c1457-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c1457-281">0</span><span class="sxs-lookup"><span data-stu-id="c1457-281">0</span></span></td>
<td><span data-ttu-id="c1457-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c1457-283">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c1457-284">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-285">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-285">Journal</span></span></th>
<th><span data-ttu-id="c1457-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="c1457-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c1457-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="c1457-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c1457-288">version</span><span class="sxs-lookup"><span data-stu-id="c1457-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-289">00002</span><span class="sxs-lookup"><span data-stu-id="c1457-289">00002</span></span></td>
<td><span data-ttu-id="c1457-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="c1457-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c1457-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="c1457-291">Fiscal</span></span></td>
<td><span data-ttu-id="c1457-292">2017</span><span class="sxs-lookup"><span data-stu-id="c1457-292">2017</span></span></td>
<td><span data-ttu-id="c1457-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-293">Period 1</span></span></td>
<td><span data-ttu-id="c1457-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c1457-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="c1457-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-298">Cost element</span></span></th>
<th><span data-ttu-id="c1457-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-299">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-302">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-302">CC099</span></span></td>
<td><span data-ttu-id="c1457-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-303">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-304">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-304">10001</span></span></td>
<td><span data-ttu-id="c1457-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-305">Electricity</span></span></td>
<td><span data-ttu-id="c1457-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-306">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-309">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-309">CC099</span></span></td>
<td><span data-ttu-id="c1457-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-310">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-311">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-311">10001</span></span></td>
<td><span data-ttu-id="c1457-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-312">Electricity</span></span></td>
<td><span data-ttu-id="c1457-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-313">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c1457-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c1457-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="c1457-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-317">Cost element</span></span></th>
<th><span data-ttu-id="c1457-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-318">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-319">Amount</span></span></th>
<th><span data-ttu-id="c1457-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-321">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-321">CC099</span></span></td>
<td><span data-ttu-id="c1457-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-322">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-323">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-323">10001</span></span></td>
<td><span data-ttu-id="c1457-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-324">Electricity</span></span></td>
<td><span data-ttu-id="c1457-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-325">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-326">-1,000.00</span></span></td>
<td><span data-ttu-id="c1457-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-328">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-328">CC001</span></span></td>
<td><span data-ttu-id="c1457-329">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-329">HR</span></span></td>
<td><span data-ttu-id="c1457-330">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-330">10001</span></span></td>
<td><span data-ttu-id="c1457-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-331">Electricity</span></span></td>
<td><span data-ttu-id="c1457-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-332">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-333">500.00</span><span class="sxs-lookup"><span data-stu-id="c1457-333">500.00</span></span></td>
<td><span data-ttu-id="c1457-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-335">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-335">CC002</span></span></td>
<td><span data-ttu-id="c1457-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-336">Finance</span></span></td>
<td><span data-ttu-id="c1457-337">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-337">10001</span></span></td>
<td><span data-ttu-id="c1457-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-338">Electricity</span></span></td>
<td><span data-ttu-id="c1457-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-339">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-340">500.00</span><span class="sxs-lookup"><span data-stu-id="c1457-340">500.00</span></span></td>
<td><span data-ttu-id="c1457-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-342">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-342">CC099</span></span></td>
<td><span data-ttu-id="c1457-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="c1457-343">Default cost center</span></span></td>
<td><span data-ttu-id="c1457-344">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-344">10001</span></span></td>
<td><span data-ttu-id="c1457-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-345">Electricity</span></span></td>
<td><span data-ttu-id="c1457-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-346">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="c1457-347">-9,000.00</span></span></td>
<td><span data-ttu-id="c1457-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-349">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-349">CC001</span></span></td>
<td><span data-ttu-id="c1457-350">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-350">HR</span></span></td>
<td><span data-ttu-id="c1457-351">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-351">10001</span></span></td>
<td><span data-ttu-id="c1457-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-352">Electricity</span></span></td>
<td><span data-ttu-id="c1457-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-353">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c1457-354">1,285.71</span></span></td>
<td><span data-ttu-id="c1457-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-356">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-356">CC002</span></span></td>
<td><span data-ttu-id="c1457-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-357">Finance</span></span></td>
<td><span data-ttu-id="c1457-358">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-358">10001</span></span></td>
<td><span data-ttu-id="c1457-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-359">Electricity</span></span></td>
<td><span data-ttu-id="c1457-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-360">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c1457-361">7,714.29</span></span></td>
<td><span data-ttu-id="c1457-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c1457-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c1457-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c1457-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c1457-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="c1457-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c1457-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-367">Define the overhead rate</span></span>

<span data-ttu-id="c1457-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c1457-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="c1457-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-370">Cost object</span></span></th>
<th><span data-ttu-id="c1457-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="c1457-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-372">Proj 1</span></span></td>
<td><span data-ttu-id="c1457-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-373">Project 1</span></span></td>
<td><span data-ttu-id="c1457-374">3</span><span class="sxs-lookup"><span data-stu-id="c1457-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-375">Proj 2</span></span></td>
<td><span data-ttu-id="c1457-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-376">Project 2</span></span></td>
<td><span data-ttu-id="c1457-377">1</span><span class="sxs-lookup"><span data-stu-id="c1457-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="c1457-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-379">Cost object</span></span></th>
<th><span data-ttu-id="c1457-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-380">Cost element</span></span></th>
<th><span data-ttu-id="c1457-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-381">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="c1457-382">Units</span></span></th>
<th><span data-ttu-id="c1457-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="c1457-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-384">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-384">CC001</span></span></td>
<td><span data-ttu-id="c1457-385">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-385">HR</span></span></td>
<td><span data-ttu-id="c1457-386">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-386">10001</span></span></td>
<td><span data-ttu-id="c1457-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-387">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-388">1</span><span class="sxs-lookup"><span data-stu-id="c1457-388">1</span></span></td>
<td><span data-ttu-id="c1457-389">10</span><span class="sxs-lookup"><span data-stu-id="c1457-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c1457-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-391">Cost object</span></span></th>
<th><span data-ttu-id="c1457-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-392">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-393">Cost element</span></span></th>
<th><span data-ttu-id="c1457-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-394">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-396">Proj 1</span></span></td>
<td><span data-ttu-id="c1457-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-397">Project 1</span></span></td>
<td><span data-ttu-id="c1457-398">3</span><span class="sxs-lookup"><span data-stu-id="c1457-398">3</span></span></td>
<td><span data-ttu-id="c1457-399">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-399">10001</span></span></td>
<td><span data-ttu-id="c1457-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c1457-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c1457-401">30,00</span><span class="sxs-lookup"><span data-stu-id="c1457-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-402">Proj 2</span></span></td>
<td><span data-ttu-id="c1457-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-403">Project 2</span></span></td>
<td><span data-ttu-id="c1457-404">1</span><span class="sxs-lookup"><span data-stu-id="c1457-404">1</span></span></td>
<td><span data-ttu-id="c1457-405">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-405">10001</span></span></td>
<td><span data-ttu-id="c1457-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="c1457-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c1457-407">10,00</span><span class="sxs-lookup"><span data-stu-id="c1457-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c1457-408">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-409">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-409">Journal</span></span></th>
<th><span data-ttu-id="c1457-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="c1457-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c1457-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="c1457-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c1457-412">version</span><span class="sxs-lookup"><span data-stu-id="c1457-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-413">00003</span><span class="sxs-lookup"><span data-stu-id="c1457-413">00003</span></span></td>
<td><span data-ttu-id="c1457-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c1457-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="c1457-415">Fiscal</span></span></td>
<td><span data-ttu-id="c1457-416">2017</span><span class="sxs-lookup"><span data-stu-id="c1457-416">2017</span></span></td>
<td><span data-ttu-id="c1457-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-417">Period 1</span></span></td>
<td><span data-ttu-id="c1457-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c1457-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="c1457-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-421">Cost object</span></span></th>
<th><span data-ttu-id="c1457-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-424">Proj 1</span></span></td>
<td><span data-ttu-id="c1457-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c1457-426">3,00</span><span class="sxs-lookup"><span data-stu-id="c1457-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-428">Proj 2</span></span></td>
<td><span data-ttu-id="c1457-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c1457-430">1,00</span><span class="sxs-lookup"><span data-stu-id="c1457-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c1457-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="c1457-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-433">Cost element</span></span></th>
<th><span data-ttu-id="c1457-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-434">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-435">Amount</span></span></th>
<th><span data-ttu-id="c1457-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="c1457-437">CC0001</span></span></td>
<td><span data-ttu-id="c1457-438">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-438">HR</span></span></td>
<td><span data-ttu-id="c1457-439">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-439">10001</span></span></td>
<td><span data-ttu-id="c1457-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-440">Electricity</span></span></td>
<td><span data-ttu-id="c1457-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-441">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="c1457-442">-30.00</span></span></td>
<td><span data-ttu-id="c1457-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-444">Proj 1</span></span></td>
<td><span data-ttu-id="c1457-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c1457-446">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-446">10001</span></span></td>
<td><span data-ttu-id="c1457-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-447">Electricity</span></span></td>
<td><span data-ttu-id="c1457-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-448">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-449">30,00</span><span class="sxs-lookup"><span data-stu-id="c1457-449">30.00</span></span></td>
<td><span data-ttu-id="c1457-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-451">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-451">CC001</span></span></td>
<td><span data-ttu-id="c1457-452">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-452">HR</span></span></td>
<td><span data-ttu-id="c1457-453">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-453">10001</span></span></td>
<td><span data-ttu-id="c1457-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-454">Electricity</span></span></td>
<td><span data-ttu-id="c1457-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-455">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="c1457-456">-10.00</span></span></td>
<td><span data-ttu-id="c1457-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-458">Proj 2</span></span></td>
<td><span data-ttu-id="c1457-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c1457-460">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-460">10001</span></span></td>
<td><span data-ttu-id="c1457-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-461">Electricity</span></span></td>
<td><span data-ttu-id="c1457-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-462">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-463">10,00</span><span class="sxs-lookup"><span data-stu-id="c1457-463">10.00</span></span></td>
<td><span data-ttu-id="c1457-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="c1457-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c1457-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="c1457-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c1457-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c1457-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c1457-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="c1457-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="c1457-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="c1457-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c1457-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="c1457-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c1457-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="c1457-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c1457-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="c1457-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c1457-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="c1457-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="c1457-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="c1457-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c1457-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="c1457-475">Define the cost allocation</span></span>

<span data-ttu-id="c1457-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="c1457-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c1457-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c1457-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="c1457-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-479">Cost object</span></span></th>
<th><span data-ttu-id="c1457-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="c1457-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-481">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-481">CC002</span></span></td>
<td><span data-ttu-id="c1457-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-482">Finance</span></span></td>
<td><span data-ttu-id="c1457-483">35</span><span class="sxs-lookup"><span data-stu-id="c1457-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-484">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-484">CC003</span></span></td>
<td><span data-ttu-id="c1457-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-485">Assembly</span></span></td>
<td><span data-ttu-id="c1457-486">55</span><span class="sxs-lookup"><span data-stu-id="c1457-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-487">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-487">CC004</span></span></td>
<td><span data-ttu-id="c1457-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-488">Packaging</span></span></td>
<td><span data-ttu-id="c1457-489">10</span><span class="sxs-lookup"><span data-stu-id="c1457-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c1457-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="c1457-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-492">Cost object</span></span></th>
<th><span data-ttu-id="c1457-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="c1457-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-494">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-494">CC003</span></span></td>
<td><span data-ttu-id="c1457-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-495">Assembly</span></span></td>
<td><span data-ttu-id="c1457-496">65</span><span class="sxs-lookup"><span data-stu-id="c1457-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-497">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-497">CC004</span></span></td>
<td><span data-ttu-id="c1457-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-498">Packaging</span></span></td>
<td><span data-ttu-id="c1457-499">35</span><span class="sxs-lookup"><span data-stu-id="c1457-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c1457-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="c1457-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-502">Cost object</span></span></th>
<th><span data-ttu-id="c1457-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="c1457-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-504">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-505">Product 1</span></span></td>
<td><span data-ttu-id="c1457-506">60</span><span class="sxs-lookup"><span data-stu-id="c1457-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-507">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-508">Product 2</span></span></td>
<td><span data-ttu-id="c1457-509">20</span><span class="sxs-lookup"><span data-stu-id="c1457-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="c1457-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c1457-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="c1457-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-512">Cost object</span></span></th>
<th><span data-ttu-id="c1457-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="c1457-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-514">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-515">Product 1</span></span></td>
<td><span data-ttu-id="c1457-516">80</span><span class="sxs-lookup"><span data-stu-id="c1457-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-517">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-518">Product 2</span></span></td>
<td><span data-ttu-id="c1457-519">15</span><span class="sxs-lookup"><span data-stu-id="c1457-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c1457-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="c1457-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c1457-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="c1457-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="c1457-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="c1457-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-523">Cost object</span></span></th>
<th><span data-ttu-id="c1457-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-524">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-525">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-526">Amount</span></span></th>
<th><span data-ttu-id="c1457-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-528">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-528">CC002</span></span></td>
<td><span data-ttu-id="c1457-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-529">Finance</span></span></td>
<td><span data-ttu-id="c1457-530">35</span><span class="sxs-lookup"><span data-stu-id="c1457-530">35</span></span></td>
<td><span data-ttu-id="c1457-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c1457-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c1457-532">175.00</span><span class="sxs-lookup"><span data-stu-id="c1457-532">175.00</span></span></td>
<td><span data-ttu-id="c1457-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-534">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-534">CC003</span></span></td>
<td><span data-ttu-id="c1457-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-535">Assembly</span></span></td>
<td><span data-ttu-id="c1457-536">55</span><span class="sxs-lookup"><span data-stu-id="c1457-536">55</span></span></td>
<td><span data-ttu-id="c1457-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c1457-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c1457-538">275.00</span><span class="sxs-lookup"><span data-stu-id="c1457-538">275.00</span></span></td>
<td><span data-ttu-id="c1457-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-540">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-540">CC004</span></span></td>
<td><span data-ttu-id="c1457-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-541">Packaging</span></span></td>
<td><span data-ttu-id="c1457-542">10</span><span class="sxs-lookup"><span data-stu-id="c1457-542">10</span></span></td>
<td><span data-ttu-id="c1457-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="c1457-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c1457-544">50,00</span><span class="sxs-lookup"><span data-stu-id="c1457-544">50.00</span></span></td>
<td><span data-ttu-id="c1457-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-546">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-546">CC002</span></span></td>
<td><span data-ttu-id="c1457-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-547">Finance</span></span></td>
<td><span data-ttu-id="c1457-548">35</span><span class="sxs-lookup"><span data-stu-id="c1457-548">35</span></span></td>
<td><span data-ttu-id="c1457-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="c1457-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c1457-550">436.00</span><span class="sxs-lookup"><span data-stu-id="c1457-550">436.00</span></span></td>
<td><span data-ttu-id="c1457-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-552">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-552">CC003</span></span></td>
<td><span data-ttu-id="c1457-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-553">Assembly</span></span></td>
<td><span data-ttu-id="c1457-554">55</span><span class="sxs-lookup"><span data-stu-id="c1457-554">55</span></span></td>
<td><span data-ttu-id="c1457-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="c1457-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c1457-556">685.14</span><span class="sxs-lookup"><span data-stu-id="c1457-556">685.14</span></span></td>
<td><span data-ttu-id="c1457-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-558">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-558">CC004</span></span></td>
<td><span data-ttu-id="c1457-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-559">Packaging</span></span></td>
<td><span data-ttu-id="c1457-560">10</span><span class="sxs-lookup"><span data-stu-id="c1457-560">10</span></span></td>
<td><span data-ttu-id="c1457-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="c1457-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c1457-562">124.57</span><span class="sxs-lookup"><span data-stu-id="c1457-562">124.57</span></span></td>
<td><span data-ttu-id="c1457-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="c1457-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-565">Cost object</span></span></th>
<th><span data-ttu-id="c1457-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-566">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-567">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-568">Amount</span></span></th>
<th><span data-ttu-id="c1457-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-570">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-570">CC003</span></span></td>
<td><span data-ttu-id="c1457-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-571">Assembly</span></span></td>
<td><span data-ttu-id="c1457-572">65</span><span class="sxs-lookup"><span data-stu-id="c1457-572">65</span></span></td>
<td><span data-ttu-id="c1457-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c1457-574">438.75</span><span class="sxs-lookup"><span data-stu-id="c1457-574">438.75</span></span></td>
<td><span data-ttu-id="c1457-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-576">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-576">CC004</span></span></td>
<td><span data-ttu-id="c1457-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-577">Packaging</span></span></td>
<td><span data-ttu-id="c1457-578">35</span><span class="sxs-lookup"><span data-stu-id="c1457-578">35</span></span></td>
<td><span data-ttu-id="c1457-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c1457-580">236.25</span><span class="sxs-lookup"><span data-stu-id="c1457-580">236.25</span></span></td>
<td><span data-ttu-id="c1457-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-582">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-582">CC003</span></span></td>
<td><span data-ttu-id="c1457-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-583">Assembly</span></span></td>
<td><span data-ttu-id="c1457-584">65</span><span class="sxs-lookup"><span data-stu-id="c1457-584">65</span></span></td>
<td><span data-ttu-id="c1457-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c1457-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c1457-586">5,297.69</span></span></td>
<td><span data-ttu-id="c1457-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-588">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-588">CC004</span></span></td>
<td><span data-ttu-id="c1457-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-589">Packaging</span></span></td>
<td><span data-ttu-id="c1457-590">35</span><span class="sxs-lookup"><span data-stu-id="c1457-590">35</span></span></td>
<td><span data-ttu-id="c1457-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="c1457-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c1457-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c1457-592">2,852.60</span></span></td>
<td><span data-ttu-id="c1457-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="c1457-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-595">Cost object</span></span></th>
<th><span data-ttu-id="c1457-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-596">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-597">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-598">Amount</span></span></th>
<th><span data-ttu-id="c1457-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-600">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-601">Product 1</span></span></td>
<td><span data-ttu-id="c1457-602">60</span><span class="sxs-lookup"><span data-stu-id="c1457-602">60</span></span></td>
<td><span data-ttu-id="c1457-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c1457-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c1457-604">535.31</span><span class="sxs-lookup"><span data-stu-id="c1457-604">535.31</span></span></td>
<td><span data-ttu-id="c1457-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-606">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-607">Product 2</span></span></td>
<td><span data-ttu-id="c1457-608">20</span><span class="sxs-lookup"><span data-stu-id="c1457-608">20</span></span></td>
<td><span data-ttu-id="c1457-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="c1457-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c1457-610">178.44</span><span class="sxs-lookup"><span data-stu-id="c1457-610">178.44</span></span></td>
<td><span data-ttu-id="c1457-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-612">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-613">Product 1</span></span></td>
<td><span data-ttu-id="c1457-614">60</span><span class="sxs-lookup"><span data-stu-id="c1457-614">60</span></span></td>
<td><span data-ttu-id="c1457-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c1457-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c1457-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c1457-616">4,487.12</span></span></td>
<td><span data-ttu-id="c1457-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-618">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-619">Product 2</span></span></td>
<td><span data-ttu-id="c1457-620">20</span><span class="sxs-lookup"><span data-stu-id="c1457-620">20</span></span></td>
<td><span data-ttu-id="c1457-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="c1457-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c1457-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c1457-622">1,495.71</span></span></td>
<td><span data-ttu-id="c1457-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1457-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="c1457-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-625">Cost object</span></span></th>
<th><span data-ttu-id="c1457-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="c1457-626">Magnitude</span></span></th>
<th><span data-ttu-id="c1457-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="c1457-627">Allocation factor</span></span></th>
<th><span data-ttu-id="c1457-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-628">Amount</span></span></th>
<th><span data-ttu-id="c1457-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-630">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-631">Product 1</span></span></td>
<td><span data-ttu-id="c1457-632">80</span><span class="sxs-lookup"><span data-stu-id="c1457-632">80</span></span></td>
<td><span data-ttu-id="c1457-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c1457-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c1457-634">241.05</span><span class="sxs-lookup"><span data-stu-id="c1457-634">241.05</span></span></td>
<td><span data-ttu-id="c1457-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-636">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-637">Product 2</span></span></td>
<td><span data-ttu-id="c1457-638">15</span><span class="sxs-lookup"><span data-stu-id="c1457-638">15</span></span></td>
<td><span data-ttu-id="c1457-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="c1457-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c1457-640">45.20</span><span class="sxs-lookup"><span data-stu-id="c1457-640">45.20</span></span></td>
<td><span data-ttu-id="c1457-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-642">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-643">Product 1</span></span></td>
<td><span data-ttu-id="c1457-644">80</span><span class="sxs-lookup"><span data-stu-id="c1457-644">80</span></span></td>
<td><span data-ttu-id="c1457-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c1457-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c1457-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c1457-646">2,507.09</span></span></td>
<td><span data-ttu-id="c1457-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-648">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-649">Product 2</span></span></td>
<td><span data-ttu-id="c1457-650">15</span><span class="sxs-lookup"><span data-stu-id="c1457-650">15</span></span></td>
<td><span data-ttu-id="c1457-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="c1457-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c1457-652">470.08</span><span class="sxs-lookup"><span data-stu-id="c1457-652">470.08</span></span></td>
<td><span data-ttu-id="c1457-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c1457-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="c1457-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-655">Journal</span><span class="sxs-lookup"><span data-stu-id="c1457-655">Journal</span></span></th>
<th><span data-ttu-id="c1457-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="c1457-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c1457-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="c1457-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c1457-658">version</span><span class="sxs-lookup"><span data-stu-id="c1457-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-659">00004</span><span class="sxs-lookup"><span data-stu-id="c1457-659">00004</span></span></td>
<td><span data-ttu-id="c1457-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="c1457-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c1457-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="c1457-661">Fiscal</span></span></td>
<td><span data-ttu-id="c1457-662">2017</span><span class="sxs-lookup"><span data-stu-id="c1457-662">2017</span></span></td>
<td><span data-ttu-id="c1457-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-663">Period 1</span></span></td>
<td><span data-ttu-id="c1457-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="c1457-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c1457-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="c1457-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c1457-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-668">Cost element</span></span></th>
<th><span data-ttu-id="c1457-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-669">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-672">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-672">CC001</span></span></td>
<td><span data-ttu-id="c1457-673">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-673">HR</span></span></td>
<td><span data-ttu-id="c1457-674">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-674">10001</span></span></td>
<td><span data-ttu-id="c1457-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-675">Electricity</span></span></td>
<td><span data-ttu-id="c1457-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-676">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-677">500.00</span><span class="sxs-lookup"><span data-stu-id="c1457-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-679">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-679">CC001</span></span></td>
<td><span data-ttu-id="c1457-680">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-680">HR</span></span></td>
<td><span data-ttu-id="c1457-681">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-681">10001</span></span></td>
<td><span data-ttu-id="c1457-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-682">Electricity</span></span></td>
<td><span data-ttu-id="c1457-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-683">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c1457-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-686">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-686">CC002</span></span></td>
<td><span data-ttu-id="c1457-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-687">Finance</span></span></td>
<td><span data-ttu-id="c1457-688">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-688">10001</span></span></td>
<td><span data-ttu-id="c1457-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-689">Electricity</span></span></td>
<td><span data-ttu-id="c1457-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-690">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-691">675.00</span><span class="sxs-lookup"><span data-stu-id="c1457-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-693">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-693">CC002</span></span></td>
<td><span data-ttu-id="c1457-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-694">Finance</span></span></td>
<td><span data-ttu-id="c1457-695">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-695">10001</span></span></td>
<td><span data-ttu-id="c1457-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-696">Electricity</span></span></td>
<td><span data-ttu-id="c1457-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-697">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c1457-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-700">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-700">CC003</span></span></td>
<td><span data-ttu-id="c1457-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-701">Assembly</span></span></td>
<td><span data-ttu-id="c1457-702">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-702">10001</span></span></td>
<td><span data-ttu-id="c1457-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-703">Electricity</span></span></td>
<td><span data-ttu-id="c1457-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-704">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-705">713.75</span><span class="sxs-lookup"><span data-stu-id="c1457-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-707">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-707">CC003</span></span></td>
<td><span data-ttu-id="c1457-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-708">Assembly</span></span></td>
<td><span data-ttu-id="c1457-709">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-709">10001</span></span></td>
<td><span data-ttu-id="c1457-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-710">Electricity</span></span></td>
<td><span data-ttu-id="c1457-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-711">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c1457-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-714">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-714">CC003</span></span></td>
<td><span data-ttu-id="c1457-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-715">Packaging</span></span></td>
<td><span data-ttu-id="c1457-716">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-716">10001</span></span></td>
<td><span data-ttu-id="c1457-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-717">Electricity</span></span></td>
<td><span data-ttu-id="c1457-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-718">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-719">286.25</span><span class="sxs-lookup"><span data-stu-id="c1457-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-721">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-721">CC003</span></span></td>
<td><span data-ttu-id="c1457-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-722">Packaging</span></span></td>
<td><span data-ttu-id="c1457-723">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-723">10001</span></span></td>
<td><span data-ttu-id="c1457-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-724">Electricity</span></span></td>
<td><span data-ttu-id="c1457-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-725">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c1457-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-728">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-729">Product 1</span></span></td>
<td><span data-ttu-id="c1457-730">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-730">10001</span></span></td>
<td><span data-ttu-id="c1457-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-731">Electricity</span></span></td>
<td><span data-ttu-id="c1457-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-732">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-733">776.36</span><span class="sxs-lookup"><span data-stu-id="c1457-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-735">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-736">Product 1</span></span></td>
<td><span data-ttu-id="c1457-737">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-737">10001</span></span></td>
<td><span data-ttu-id="c1457-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-738">Electricity</span></span></td>
<td><span data-ttu-id="c1457-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-739">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c1457-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-742">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-743">Product 1</span></span></td>
<td><span data-ttu-id="c1457-744">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-744">10001</span></span></td>
<td><span data-ttu-id="c1457-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-745">Electricity</span></span></td>
<td><span data-ttu-id="c1457-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-746">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-747">223.64</span><span class="sxs-lookup"><span data-stu-id="c1457-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="c1457-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-749">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-750">Product 1</span></span></td>
<td><span data-ttu-id="c1457-751">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-751">10001</span></span></td>
<td><span data-ttu-id="c1457-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-752">Electricity</span></span></td>
<td><span data-ttu-id="c1457-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-753">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c1457-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c1457-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="c1457-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c1457-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c1457-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-757">Cost element</span></span></th>
<th><span data-ttu-id="c1457-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="c1457-758">Cost behavior</span></span></th>
<th><span data-ttu-id="c1457-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="c1457-759">Amount</span></span></th>
<th><span data-ttu-id="c1457-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="c1457-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c1457-761">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-761">CC001</span></span></td>
<td><span data-ttu-id="c1457-762">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-762">HR</span></span></td>
<td><span data-ttu-id="c1457-763">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-763">10001</span></span></td>
<td><span data-ttu-id="c1457-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-764">Electricity</span></span></td>
<td><span data-ttu-id="c1457-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-765">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="c1457-766">-500.00</span></span></td>
<td><span data-ttu-id="c1457-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-768">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-768">CC002</span></span></td>
<td><span data-ttu-id="c1457-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-769">Finance</span></span></td>
<td><span data-ttu-id="c1457-770">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-770">10001</span></span></td>
<td><span data-ttu-id="c1457-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-771">Electricity</span></span></td>
<td><span data-ttu-id="c1457-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-772">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-773">175.00</span><span class="sxs-lookup"><span data-stu-id="c1457-773">175.00</span></span></td>
<td><span data-ttu-id="c1457-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-775">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-775">CC003</span></span></td>
<td><span data-ttu-id="c1457-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-776">Assembly</span></span></td>
<td><span data-ttu-id="c1457-777">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-777">10001</span></span></td>
<td><span data-ttu-id="c1457-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-778">Electricity</span></span></td>
<td><span data-ttu-id="c1457-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-779">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-780">275.00</span><span class="sxs-lookup"><span data-stu-id="c1457-780">275.00</span></span></td>
<td><span data-ttu-id="c1457-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-782">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-782">CC004</span></span></td>
<td><span data-ttu-id="c1457-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-783">Packaging</span></span></td>
<td><span data-ttu-id="c1457-784">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-784">10001</span></span></td>
<td><span data-ttu-id="c1457-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-785">Electricity</span></span></td>
<td><span data-ttu-id="c1457-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-786">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-787">50,00</span><span class="sxs-lookup"><span data-stu-id="c1457-787">50,00</span></span></td>
<td><span data-ttu-id="c1457-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-789">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-789">CC001</span></span></td>
<td><span data-ttu-id="c1457-790">Personal</span><span class="sxs-lookup"><span data-stu-id="c1457-790">HR</span></span></td>
<td><span data-ttu-id="c1457-791">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-791">10001</span></span></td>
<td><span data-ttu-id="c1457-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-792">Electricity</span></span></td>
<td><span data-ttu-id="c1457-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-793">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="c1457-794">-1,245.71</span></span></td>
<td><span data-ttu-id="c1457-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-796">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-796">CC002</span></span></td>
<td><span data-ttu-id="c1457-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-797">Finance</span></span></td>
<td><span data-ttu-id="c1457-798">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-798">10001</span></span></td>
<td><span data-ttu-id="c1457-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-799">Electricity</span></span></td>
<td><span data-ttu-id="c1457-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-800">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-801">436.00</span><span class="sxs-lookup"><span data-stu-id="c1457-801">436.00</span></span></td>
<td><span data-ttu-id="c1457-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-803">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-803">CC003</span></span></td>
<td><span data-ttu-id="c1457-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-804">Assembly</span></span></td>
<td><span data-ttu-id="c1457-805">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-805">10001</span></span></td>
<td><span data-ttu-id="c1457-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-806">Electricity</span></span></td>
<td><span data-ttu-id="c1457-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-807">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-808">685.14</span><span class="sxs-lookup"><span data-stu-id="c1457-808">685.14</span></span></td>
<td><span data-ttu-id="c1457-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-810">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-810">CC004</span></span></td>
<td><span data-ttu-id="c1457-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-811">Packaging</span></span></td>
<td><span data-ttu-id="c1457-812">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-812">10001</span></span></td>
<td><span data-ttu-id="c1457-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-813">Electricity</span></span></td>
<td><span data-ttu-id="c1457-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-814">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-815">124.57</span><span class="sxs-lookup"><span data-stu-id="c1457-815">124.57</span></span></td>
<td><span data-ttu-id="c1457-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-817">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-817">CC002</span></span></td>
<td><span data-ttu-id="c1457-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-818">Finance</span></span></td>
<td><span data-ttu-id="c1457-819">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-819">10001</span></span></td>
<td><span data-ttu-id="c1457-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-820">Electricity</span></span></td>
<td><span data-ttu-id="c1457-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-821">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="c1457-822">-675.00</span></span></td>
<td><span data-ttu-id="c1457-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-824">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-824">CC003</span></span></td>
<td><span data-ttu-id="c1457-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-825">Assembly</span></span></td>
<td><span data-ttu-id="c1457-826">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-826">10001</span></span></td>
<td><span data-ttu-id="c1457-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-827">Electricity</span></span></td>
<td><span data-ttu-id="c1457-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-828">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-829">438.75</span><span class="sxs-lookup"><span data-stu-id="c1457-829">438.75</span></span></td>
<td><span data-ttu-id="c1457-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-831">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-831">CC004</span></span></td>
<td><span data-ttu-id="c1457-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-832">Packaging</span></span></td>
<td><span data-ttu-id="c1457-833">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-833">10001</span></span></td>
<td><span data-ttu-id="c1457-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-834">Electricity</span></span></td>
<td><span data-ttu-id="c1457-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-835">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-836">236.25</span><span class="sxs-lookup"><span data-stu-id="c1457-836">236.25</span></span></td>
<td><span data-ttu-id="c1457-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-838">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-838">CC002</span></span></td>
<td><span data-ttu-id="c1457-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="c1457-839">Finance</span></span></td>
<td><span data-ttu-id="c1457-840">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-840">10001</span></span></td>
<td><span data-ttu-id="c1457-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-841">Electricity</span></span></td>
<td><span data-ttu-id="c1457-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-842">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="c1457-843">-8,150.29</span></span></td>
<td><span data-ttu-id="c1457-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-845">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-845">CC003</span></span></td>
<td><span data-ttu-id="c1457-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-846">Assembly</span></span></td>
<td><span data-ttu-id="c1457-847">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-847">10001</span></span></td>
<td><span data-ttu-id="c1457-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-848">Electricity</span></span></td>
<td><span data-ttu-id="c1457-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-849">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c1457-850">5,297.69</span></span></td>
<td><span data-ttu-id="c1457-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-852">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-852">CC004</span></span></td>
<td><span data-ttu-id="c1457-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="c1457-853">Packaging</span></span></td>
<td><span data-ttu-id="c1457-854">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-854">10001</span></span></td>
<td><span data-ttu-id="c1457-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-855">Electricity</span></span></td>
<td><span data-ttu-id="c1457-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-856">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c1457-857">2,852.60</span></span></td>
<td><span data-ttu-id="c1457-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-859">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-859">CC003</span></span></td>
<td><span data-ttu-id="c1457-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-860">Assembly</span></span></td>
<td><span data-ttu-id="c1457-861">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-861">10001</span></span></td>
<td><span data-ttu-id="c1457-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-862">Electricity</span></span></td>
<td><span data-ttu-id="c1457-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-863">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="c1457-864">-713.75</span></span></td>
<td><span data-ttu-id="c1457-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-866">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-867">Product 1</span></span></td>
<td><span data-ttu-id="c1457-868">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-868">10001</span></span></td>
<td><span data-ttu-id="c1457-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-869">Electricity</span></span></td>
<td><span data-ttu-id="c1457-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-870">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-871">535.31</span><span class="sxs-lookup"><span data-stu-id="c1457-871">535.31</span></span></td>
<td><span data-ttu-id="c1457-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-873">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-874">Product 2</span></span></td>
<td><span data-ttu-id="c1457-875">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-875">10001</span></span></td>
<td><span data-ttu-id="c1457-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-876">Electricity</span></span></td>
<td><span data-ttu-id="c1457-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-877">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-878">178.44</span><span class="sxs-lookup"><span data-stu-id="c1457-878">178.44</span></span></td>
<td><span data-ttu-id="c1457-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-880">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-880">CC003</span></span></td>
<td><span data-ttu-id="c1457-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-881">Assembly</span></span></td>
<td><span data-ttu-id="c1457-882">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-882">10001</span></span></td>
<td><span data-ttu-id="c1457-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-883">Electricity</span></span></td>
<td><span data-ttu-id="c1457-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-884">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="c1457-885">-5,982.83</span></span></td>
<td><span data-ttu-id="c1457-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-887">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-888">Product 1</span></span></td>
<td><span data-ttu-id="c1457-889">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-889">10001</span></span></td>
<td><span data-ttu-id="c1457-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-890">Electricity</span></span></td>
<td><span data-ttu-id="c1457-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-891">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c1457-892">4,487.12</span></span></td>
<td><span data-ttu-id="c1457-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-894">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-895">Product 2</span></span></td>
<td><span data-ttu-id="c1457-896">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-896">10001</span></span></td>
<td><span data-ttu-id="c1457-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-897">Electricity</span></span></td>
<td><span data-ttu-id="c1457-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-898">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c1457-899">1,495.71</span></span></td>
<td><span data-ttu-id="c1457-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-901">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-901">CC003</span></span></td>
<td><span data-ttu-id="c1457-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-902">Assembly</span></span></td>
<td><span data-ttu-id="c1457-903">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-903">10001</span></span></td>
<td><span data-ttu-id="c1457-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-904">Electricity</span></span></td>
<td><span data-ttu-id="c1457-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-905">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="c1457-906">-286.25</span></span></td>
<td><span data-ttu-id="c1457-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-908">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-909">Product 1</span></span></td>
<td><span data-ttu-id="c1457-910">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-910">10001</span></span></td>
<td><span data-ttu-id="c1457-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-911">Electricity</span></span></td>
<td><span data-ttu-id="c1457-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-912">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-913">241.05</span><span class="sxs-lookup"><span data-stu-id="c1457-913">241.05</span></span></td>
<td><span data-ttu-id="c1457-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-915">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-916">Product 2</span></span></td>
<td><span data-ttu-id="c1457-917">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-917">10001</span></span></td>
<td><span data-ttu-id="c1457-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-918">Electricity</span></span></td>
<td><span data-ttu-id="c1457-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-919">Fixed cost</span></span></td>
<td><span data-ttu-id="c1457-920">45.20</span><span class="sxs-lookup"><span data-stu-id="c1457-920">45.20</span></span></td>
<td><span data-ttu-id="c1457-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-922">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-922">CC003</span></span></td>
<td><span data-ttu-id="c1457-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="c1457-923">Assembly</span></span></td>
<td><span data-ttu-id="c1457-924">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-924">10001</span></span></td>
<td><span data-ttu-id="c1457-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-925">Electricity</span></span></td>
<td><span data-ttu-id="c1457-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-926">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="c1457-927">-2,977.17</span></span></td>
<td><span data-ttu-id="c1457-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-929">Prod 1</span></span></td>
<td><span data-ttu-id="c1457-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="c1457-930">Product 1</span></span></td>
<td><span data-ttu-id="c1457-931">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-931">10001</span></span></td>
<td><span data-ttu-id="c1457-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-932">Electricity</span></span></td>
<td><span data-ttu-id="c1457-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-933">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c1457-934">2,507.09</span></span></td>
<td><span data-ttu-id="c1457-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c1457-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-936">Prod 2</span></span></td>
<td><span data-ttu-id="c1457-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="c1457-937">Product 2</span></span></td>
<td><span data-ttu-id="c1457-938">10001</span><span class="sxs-lookup"><span data-stu-id="c1457-938">10001</span></span></td>
<td><span data-ttu-id="c1457-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-939">Electricity</span></span></td>
<td><span data-ttu-id="c1457-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-940">Variable cost</span></span></td>
<td><span data-ttu-id="c1457-941">470.08</span><span class="sxs-lookup"><span data-stu-id="c1457-941">470.08</span></span></td>
<td><span data-ttu-id="c1457-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="c1457-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c1457-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="c1457-943">Conclusion</span></span>
<span data-ttu-id="c1457-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="c1457-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c1457-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="c1457-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c1457-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="c1457-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c1457-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="c1457-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c1457-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="c1457-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c1457-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="c1457-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c1457-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="c1457-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c1457-951">CC099</span><span class="sxs-lookup"><span data-stu-id="c1457-951">CC099</span></span></th>
<th><span data-ttu-id="c1457-952">CC001</span><span class="sxs-lookup"><span data-stu-id="c1457-952">CC001</span></span></th>
<th><span data-ttu-id="c1457-953">CC002</span><span class="sxs-lookup"><span data-stu-id="c1457-953">CC002</span></span></th>
<th><span data-ttu-id="c1457-954">CC003</span><span class="sxs-lookup"><span data-stu-id="c1457-954">CC003</span></span></th>
<th><span data-ttu-id="c1457-955">CC004</span><span class="sxs-lookup"><span data-stu-id="c1457-955">CC004</span></span></th>
<th><span data-ttu-id="c1457-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c1457-956">Proj 1</span></span></th>
<th><span data-ttu-id="c1457-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c1457-957">Proj 2</span></span></th>
<th><span data-ttu-id="c1457-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="c1457-958">Prod 1</span></span></th>
<th><span data-ttu-id="c1457-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="c1457-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c1457-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="c1457-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c1457-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c1457-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="c1457-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-971">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="c1457-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-973">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-975">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c1457-978">776.36</span><span class="sxs-lookup"><span data-stu-id="c1457-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-979">223.64</span><span class="sxs-lookup"><span data-stu-id="c1457-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c1457-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="c1457-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-982">000</span><span class="sxs-lookup"><span data-stu-id="c1457-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-983">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-984">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-985">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c1457-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-987">30,00</span><span class="sxs-lookup"><span data-stu-id="c1457-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-988">10,00</span><span class="sxs-lookup"><span data-stu-id="c1457-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c1457-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c1457-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c1457-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="c1457-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c1457-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="c1457-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c1457-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c1457-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c1457-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="c1457-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c1457-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="c1457-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c1457-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="c1457-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



