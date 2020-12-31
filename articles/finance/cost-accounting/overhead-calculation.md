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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448118"
---
# <a name="overhead-calculation"></a><span data-ttu-id="08bf1-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="08bf1-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08bf1-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="08bf1-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="08bf1-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="08bf1-105">Term definition</span></span>
---------------

<span data-ttu-id="08bf1-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="08bf1-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="08bf1-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="08bf1-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="08bf1-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="08bf1-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="08bf1-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="08bf1-109">Rent</span></span>
-   <span data-ttu-id="08bf1-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-110">Electricity</span></span>
-   <span data-ttu-id="08bf1-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="08bf1-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="08bf1-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="08bf1-112">Overhead calculation overview</span></span>
<span data-ttu-id="08bf1-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="08bf1-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="08bf1-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="08bf1-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="08bf1-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="08bf1-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="08bf1-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="08bf1-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="08bf1-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="08bf1-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="08bf1-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="08bf1-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="08bf1-119">Version type</span></span>
-   <span data-ttu-id="08bf1-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="08bf1-120">Date and time</span></span>
-   <span data-ttu-id="08bf1-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="08bf1-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="08bf1-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="08bf1-122">Fiscal year</span></span>
-   <span data-ttu-id="08bf1-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="08bf1-123">Fiscal period</span></span>

<span data-ttu-id="08bf1-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="08bf1-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="08bf1-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="08bf1-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="08bf1-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="08bf1-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="08bf1-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="08bf1-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="08bf1-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="08bf1-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="08bf1-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="08bf1-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="08bf1-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="08bf1-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="08bf1-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="08bf1-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="08bf1-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="08bf1-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="08bf1-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="08bf1-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="08bf1-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="08bf1-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="08bf1-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="08bf1-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="08bf1-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="08bf1-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="08bf1-140">Main account</span></span></th>
<th><span data-ttu-id="08bf1-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="08bf1-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="08bf1-143">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-143">CC099</span></span></td>
<td><span data-ttu-id="08bf1-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-144">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-145">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-145">10001</span></span></td>
<td><span data-ttu-id="08bf1-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-146">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="08bf1-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="08bf1-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="08bf1-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="08bf1-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="08bf1-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="08bf1-151">Define the cost behavior rule</span></span>

<span data-ttu-id="08bf1-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="08bf1-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="08bf1-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="08bf1-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="08bf1-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="08bf1-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="08bf1-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="08bf1-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="08bf1-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="08bf1-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="08bf1-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="08bf1-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="08bf1-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="08bf1-159">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-160">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-160">Journal</span></span></th>
<th><span data-ttu-id="08bf1-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="08bf1-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="08bf1-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="08bf1-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="08bf1-163">version</span><span class="sxs-lookup"><span data-stu-id="08bf1-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-164">00001</span><span class="sxs-lookup"><span data-stu-id="08bf1-164">00001</span></span></td>
<td><span data-ttu-id="08bf1-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="08bf1-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="08bf1-166">Fiscal</span></span></td>
<td><span data-ttu-id="08bf1-167">2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-167">2017</span></span></td>
<td><span data-ttu-id="08bf1-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-168">Period 1</span></span></td>
<td><span data-ttu-id="08bf1-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="08bf1-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="08bf1-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-173">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-174">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="08bf1-177">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-177">CC099</span></span></td>
<td><span data-ttu-id="08bf1-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-178">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-179">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-179">10001</span></span></td>
<td><span data-ttu-id="08bf1-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-180">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="08bf1-181">Unclassified</span></span></td>
<td><span data-ttu-id="08bf1-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="08bf1-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="08bf1-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-185">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-186">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-187">Amount</span></span></th>
<th><span data-ttu-id="08bf1-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-189">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-189">CC099</span></span></td>
<td><span data-ttu-id="08bf1-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-190">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-191">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-191">10001</span></span></td>
<td><span data-ttu-id="08bf1-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-192">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="08bf1-193">Unclassified</span></span></td>
<td><span data-ttu-id="08bf1-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-194">10,000.00</span></span></td>
<td><span data-ttu-id="08bf1-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-196">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-196">CC099</span></span></td>
<td><span data-ttu-id="08bf1-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-197">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-198">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-198">10001</span></span></td>
<td><span data-ttu-id="08bf1-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-199">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="08bf1-200">Unclassified</span></span></td>
<td><span data-ttu-id="08bf1-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-201">-10,000.00</span></span></td>
<td><span data-ttu-id="08bf1-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-203">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-203">CC099</span></span></td>
<td><span data-ttu-id="08bf1-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-204">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-205">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-205">10001</span></span></td>
<td><span data-ttu-id="08bf1-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-206">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-207">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-208">1,000.00</span></span></td>
<td><span data-ttu-id="08bf1-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-210">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-210">CC099</span></span></td>
<td><span data-ttu-id="08bf1-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-211">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-212">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-212">10001</span></span></td>
<td><span data-ttu-id="08bf1-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-213">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-214">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-215">9,000.00</span></span></td>
<td><span data-ttu-id="08bf1-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="08bf1-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="08bf1-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="08bf1-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="08bf1-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="08bf1-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="08bf1-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="08bf1-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="08bf1-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="08bf1-221">Define the cost distribution rule</span></span>

<span data-ttu-id="08bf1-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="08bf1-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="08bf1-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="08bf1-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="08bf1-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="08bf1-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="08bf1-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="08bf1-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="08bf1-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="08bf1-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="08bf1-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-228">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="08bf1-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-230">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-230">CC001</span></span></td>
<td><span data-ttu-id="08bf1-231">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-231">HR</span></span></td>
<td><span data-ttu-id="08bf1-232">1 000</span><span class="sxs-lookup"><span data-stu-id="08bf1-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-233">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-233">CC002</span></span></td>
<td><span data-ttu-id="08bf1-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-234">Finance</span></span></td>
<td><span data-ttu-id="08bf1-235">6,000</span><span class="sxs-lookup"><span data-stu-id="08bf1-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-236">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-236">CC003</span></span></td>
<td><span data-ttu-id="08bf1-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-237">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-238">0</span><span class="sxs-lookup"><span data-stu-id="08bf1-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="08bf1-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-240">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-241">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-242">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-244">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-244">CC001</span></span></td>
<td><span data-ttu-id="08bf1-245">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-245">HR</span></span></td>
<td><span data-ttu-id="08bf1-246">1 000</span><span class="sxs-lookup"><span data-stu-id="08bf1-246">1,000</span></span></td>
<td><span data-ttu-id="08bf1-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="08bf1-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="08bf1-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-249">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-249">CC002</span></span></td>
<td><span data-ttu-id="08bf1-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-250">Finance</span></span></td>
<td><span data-ttu-id="08bf1-251">6,000</span><span class="sxs-lookup"><span data-stu-id="08bf1-251">6,000</span></span></td>
<td><span data-ttu-id="08bf1-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="08bf1-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="08bf1-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-254">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-254">CC003</span></span></td>
<td><span data-ttu-id="08bf1-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-255">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-256">0</span><span class="sxs-lookup"><span data-stu-id="08bf1-256">0</span></span></td>
<td><span data-ttu-id="08bf1-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="08bf1-258">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="08bf1-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="08bf1-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="08bf1-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-261">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-262">Formel</span><span class="sxs-lookup"><span data-stu-id="08bf1-262">Formula</span></span></th>
<th><span data-ttu-id="08bf1-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-263">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-264">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-266">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-266">CC001</span></span></td>
<td><span data-ttu-id="08bf1-267">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-267">HR</span></span></td>
<td><span data-ttu-id="08bf1-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="08bf1-269">1</span><span class="sxs-lookup"><span data-stu-id="08bf1-269">1</span></span></td>
<td><span data-ttu-id="08bf1-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="08bf1-271">500.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-272">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-272">CC002</span></span></td>
<td><span data-ttu-id="08bf1-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-273">Finance</span></span></td>
<td><span data-ttu-id="08bf1-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="08bf1-275">1</span><span class="sxs-lookup"><span data-stu-id="08bf1-275">1</span></span></td>
<td><span data-ttu-id="08bf1-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="08bf1-277">500.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-278">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-278">CC003</span></span></td>
<td><span data-ttu-id="08bf1-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-279">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="08bf1-281">0</span><span class="sxs-lookup"><span data-stu-id="08bf1-281">0</span></span></td>
<td><span data-ttu-id="08bf1-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="08bf1-283">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="08bf1-284">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-285">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-285">Journal</span></span></th>
<th><span data-ttu-id="08bf1-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="08bf1-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="08bf1-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="08bf1-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="08bf1-288">version</span><span class="sxs-lookup"><span data-stu-id="08bf1-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-289">00002</span><span class="sxs-lookup"><span data-stu-id="08bf1-289">00002</span></span></td>
<td><span data-ttu-id="08bf1-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="08bf1-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="08bf1-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="08bf1-291">Fiscal</span></span></td>
<td><span data-ttu-id="08bf1-292">2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-292">2017</span></span></td>
<td><span data-ttu-id="08bf1-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-293">Period 1</span></span></td>
<td><span data-ttu-id="08bf1-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="08bf1-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="08bf1-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-298">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-299">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-302">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-302">CC099</span></span></td>
<td><span data-ttu-id="08bf1-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-303">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-304">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-304">10001</span></span></td>
<td><span data-ttu-id="08bf1-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-305">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-306">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-309">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-309">CC099</span></span></td>
<td><span data-ttu-id="08bf1-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-310">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-311">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-311">10001</span></span></td>
<td><span data-ttu-id="08bf1-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-312">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-313">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="08bf1-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="08bf1-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-317">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-318">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-319">Amount</span></span></th>
<th><span data-ttu-id="08bf1-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-321">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-321">CC099</span></span></td>
<td><span data-ttu-id="08bf1-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-322">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-323">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-323">10001</span></span></td>
<td><span data-ttu-id="08bf1-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-324">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-325">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-326">-1,000.00</span></span></td>
<td><span data-ttu-id="08bf1-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-328">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-328">CC001</span></span></td>
<td><span data-ttu-id="08bf1-329">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-329">HR</span></span></td>
<td><span data-ttu-id="08bf1-330">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-330">10001</span></span></td>
<td><span data-ttu-id="08bf1-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-331">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-332">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-333">500.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-333">500.00</span></span></td>
<td><span data-ttu-id="08bf1-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-335">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-335">CC002</span></span></td>
<td><span data-ttu-id="08bf1-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-336">Finance</span></span></td>
<td><span data-ttu-id="08bf1-337">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-337">10001</span></span></td>
<td><span data-ttu-id="08bf1-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-338">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-339">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-340">500.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-340">500.00</span></span></td>
<td><span data-ttu-id="08bf1-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-342">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-342">CC099</span></span></td>
<td><span data-ttu-id="08bf1-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="08bf1-343">Default cost center</span></span></td>
<td><span data-ttu-id="08bf1-344">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-344">10001</span></span></td>
<td><span data-ttu-id="08bf1-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-345">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-346">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-347">-9,000.00</span></span></td>
<td><span data-ttu-id="08bf1-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-349">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-349">CC001</span></span></td>
<td><span data-ttu-id="08bf1-350">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-350">HR</span></span></td>
<td><span data-ttu-id="08bf1-351">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-351">10001</span></span></td>
<td><span data-ttu-id="08bf1-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-352">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-353">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="08bf1-354">1,285.71</span></span></td>
<td><span data-ttu-id="08bf1-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-356">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-356">CC002</span></span></td>
<td><span data-ttu-id="08bf1-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-357">Finance</span></span></td>
<td><span data-ttu-id="08bf1-358">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-358">10001</span></span></td>
<td><span data-ttu-id="08bf1-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-359">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-360">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="08bf1-361">7,714.29</span></span></td>
<td><span data-ttu-id="08bf1-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="08bf1-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="08bf1-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="08bf1-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="08bf1-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="08bf1-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="08bf1-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-367">Define the overhead rate</span></span>

<span data-ttu-id="08bf1-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="08bf1-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="08bf1-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-370">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="08bf1-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-372">Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-373">Project 1</span></span></td>
<td><span data-ttu-id="08bf1-374">3</span><span class="sxs-lookup"><span data-stu-id="08bf1-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-375">Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-376">Project 2</span></span></td>
<td><span data-ttu-id="08bf1-377">1</span><span class="sxs-lookup"><span data-stu-id="08bf1-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="08bf1-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-379">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-380">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-381">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="08bf1-382">Units</span></span></th>
<th><span data-ttu-id="08bf1-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="08bf1-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-384">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-384">CC001</span></span></td>
<td><span data-ttu-id="08bf1-385">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-385">HR</span></span></td>
<td><span data-ttu-id="08bf1-386">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-386">10001</span></span></td>
<td><span data-ttu-id="08bf1-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-387">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-388">1</span><span class="sxs-lookup"><span data-stu-id="08bf1-388">1</span></span></td>
<td><span data-ttu-id="08bf1-389">10</span><span class="sxs-lookup"><span data-stu-id="08bf1-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="08bf1-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-391">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-392">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-393">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-394">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-396">Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-397">Project 1</span></span></td>
<td><span data-ttu-id="08bf1-398">3</span><span class="sxs-lookup"><span data-stu-id="08bf1-398">3</span></span></td>
<td><span data-ttu-id="08bf1-399">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-399">10001</span></span></td>
<td><span data-ttu-id="08bf1-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="08bf1-401">30,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-402">Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-403">Project 2</span></span></td>
<td><span data-ttu-id="08bf1-404">1</span><span class="sxs-lookup"><span data-stu-id="08bf1-404">1</span></span></td>
<td><span data-ttu-id="08bf1-405">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-405">10001</span></span></td>
<td><span data-ttu-id="08bf1-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="08bf1-407">10,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="08bf1-408">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-409">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-409">Journal</span></span></th>
<th><span data-ttu-id="08bf1-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="08bf1-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="08bf1-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="08bf1-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="08bf1-412">version</span><span class="sxs-lookup"><span data-stu-id="08bf1-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-413">00003</span><span class="sxs-lookup"><span data-stu-id="08bf1-413">00003</span></span></td>
<td><span data-ttu-id="08bf1-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="08bf1-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="08bf1-415">Fiscal</span></span></td>
<td><span data-ttu-id="08bf1-416">2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-416">2017</span></span></td>
<td><span data-ttu-id="08bf1-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-417">Period 1</span></span></td>
<td><span data-ttu-id="08bf1-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="08bf1-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="08bf1-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-421">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-424">Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-426">3,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-428">Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-430">1,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="08bf1-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="08bf1-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-433">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-434">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-435">Amount</span></span></th>
<th><span data-ttu-id="08bf1-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="08bf1-437">CC0001</span></span></td>
<td><span data-ttu-id="08bf1-438">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-438">HR</span></span></td>
<td><span data-ttu-id="08bf1-439">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-439">10001</span></span></td>
<td><span data-ttu-id="08bf1-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-440">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-441">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-442">-30.00</span></span></td>
<td><span data-ttu-id="08bf1-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-444">Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="08bf1-446">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-446">10001</span></span></td>
<td><span data-ttu-id="08bf1-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-447">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-448">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-449">30,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-449">30.00</span></span></td>
<td><span data-ttu-id="08bf1-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-451">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-451">CC001</span></span></td>
<td><span data-ttu-id="08bf1-452">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-452">HR</span></span></td>
<td><span data-ttu-id="08bf1-453">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-453">10001</span></span></td>
<td><span data-ttu-id="08bf1-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-454">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-455">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-456">-10.00</span></span></td>
<td><span data-ttu-id="08bf1-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-458">Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="08bf1-460">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-460">10001</span></span></td>
<td><span data-ttu-id="08bf1-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-461">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-462">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-463">10,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-463">10.00</span></span></td>
<td><span data-ttu-id="08bf1-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="08bf1-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="08bf1-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="08bf1-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="08bf1-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="08bf1-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="08bf1-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="08bf1-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="08bf1-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="08bf1-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="08bf1-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="08bf1-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="08bf1-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="08bf1-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="08bf1-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="08bf1-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="08bf1-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="08bf1-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="08bf1-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="08bf1-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="08bf1-475">Define the cost allocation</span></span>

<span data-ttu-id="08bf1-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="08bf1-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="08bf1-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="08bf1-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="08bf1-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-479">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="08bf1-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-481">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-481">CC002</span></span></td>
<td><span data-ttu-id="08bf1-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-482">Finance</span></span></td>
<td><span data-ttu-id="08bf1-483">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-484">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-484">CC003</span></span></td>
<td><span data-ttu-id="08bf1-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-485">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-486">55</span><span class="sxs-lookup"><span data-stu-id="08bf1-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-487">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-487">CC004</span></span></td>
<td><span data-ttu-id="08bf1-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-488">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-489">10</span><span class="sxs-lookup"><span data-stu-id="08bf1-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="08bf1-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="08bf1-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-492">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="08bf1-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-494">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-494">CC003</span></span></td>
<td><span data-ttu-id="08bf1-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-495">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-496">65</span><span class="sxs-lookup"><span data-stu-id="08bf1-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-497">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-497">CC004</span></span></td>
<td><span data-ttu-id="08bf1-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-498">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-499">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="08bf1-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="08bf1-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-502">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="08bf1-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-504">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-505">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-506">60</span><span class="sxs-lookup"><span data-stu-id="08bf1-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-507">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-508">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-509">20</span><span class="sxs-lookup"><span data-stu-id="08bf1-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="08bf1-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="08bf1-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="08bf1-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-512">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="08bf1-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-514">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-515">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-516">80</span><span class="sxs-lookup"><span data-stu-id="08bf1-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-517">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-518">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-519">15</span><span class="sxs-lookup"><span data-stu-id="08bf1-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="08bf1-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="08bf1-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="08bf1-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="08bf1-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="08bf1-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="08bf1-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-523">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-524">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-525">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-526">Amount</span></span></th>
<th><span data-ttu-id="08bf1-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-528">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-528">CC002</span></span></td>
<td><span data-ttu-id="08bf1-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-529">Finance</span></span></td>
<td><span data-ttu-id="08bf1-530">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-530">35</span></span></td>
<td><span data-ttu-id="08bf1-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="08bf1-532">175.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-532">175.00</span></span></td>
<td><span data-ttu-id="08bf1-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-534">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-534">CC003</span></span></td>
<td><span data-ttu-id="08bf1-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-535">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-536">55</span><span class="sxs-lookup"><span data-stu-id="08bf1-536">55</span></span></td>
<td><span data-ttu-id="08bf1-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="08bf1-538">275.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-538">275.00</span></span></td>
<td><span data-ttu-id="08bf1-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-540">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-540">CC004</span></span></td>
<td><span data-ttu-id="08bf1-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-541">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-542">10</span><span class="sxs-lookup"><span data-stu-id="08bf1-542">10</span></span></td>
<td><span data-ttu-id="08bf1-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="08bf1-544">50,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-544">50.00</span></span></td>
<td><span data-ttu-id="08bf1-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-546">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-546">CC002</span></span></td>
<td><span data-ttu-id="08bf1-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-547">Finance</span></span></td>
<td><span data-ttu-id="08bf1-548">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-548">35</span></span></td>
<td><span data-ttu-id="08bf1-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="08bf1-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="08bf1-550">436.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-550">436.00</span></span></td>
<td><span data-ttu-id="08bf1-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-552">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-552">CC003</span></span></td>
<td><span data-ttu-id="08bf1-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-553">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-554">55</span><span class="sxs-lookup"><span data-stu-id="08bf1-554">55</span></span></td>
<td><span data-ttu-id="08bf1-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="08bf1-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="08bf1-556">685.14</span><span class="sxs-lookup"><span data-stu-id="08bf1-556">685.14</span></span></td>
<td><span data-ttu-id="08bf1-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-558">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-558">CC004</span></span></td>
<td><span data-ttu-id="08bf1-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-559">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-560">10</span><span class="sxs-lookup"><span data-stu-id="08bf1-560">10</span></span></td>
<td><span data-ttu-id="08bf1-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="08bf1-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="08bf1-562">124.57</span><span class="sxs-lookup"><span data-stu-id="08bf1-562">124.57</span></span></td>
<td><span data-ttu-id="08bf1-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="08bf1-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-565">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-566">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-567">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-568">Amount</span></span></th>
<th><span data-ttu-id="08bf1-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-570">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-570">CC003</span></span></td>
<td><span data-ttu-id="08bf1-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-571">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-572">65</span><span class="sxs-lookup"><span data-stu-id="08bf1-572">65</span></span></td>
<td><span data-ttu-id="08bf1-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="08bf1-574">438.75</span><span class="sxs-lookup"><span data-stu-id="08bf1-574">438.75</span></span></td>
<td><span data-ttu-id="08bf1-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-576">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-576">CC004</span></span></td>
<td><span data-ttu-id="08bf1-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-577">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-578">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-578">35</span></span></td>
<td><span data-ttu-id="08bf1-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="08bf1-580">236.25</span><span class="sxs-lookup"><span data-stu-id="08bf1-580">236.25</span></span></td>
<td><span data-ttu-id="08bf1-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-582">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-582">CC003</span></span></td>
<td><span data-ttu-id="08bf1-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-583">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-584">65</span><span class="sxs-lookup"><span data-stu-id="08bf1-584">65</span></span></td>
<td><span data-ttu-id="08bf1-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="08bf1-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="08bf1-586">5,297.69</span></span></td>
<td><span data-ttu-id="08bf1-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-588">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-588">CC004</span></span></td>
<td><span data-ttu-id="08bf1-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-589">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-590">35</span><span class="sxs-lookup"><span data-stu-id="08bf1-590">35</span></span></td>
<td><span data-ttu-id="08bf1-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="08bf1-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="08bf1-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="08bf1-592">2,852.60</span></span></td>
<td><span data-ttu-id="08bf1-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="08bf1-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-595">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-596">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-597">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-598">Amount</span></span></th>
<th><span data-ttu-id="08bf1-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-600">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-601">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-602">60</span><span class="sxs-lookup"><span data-stu-id="08bf1-602">60</span></span></td>
<td><span data-ttu-id="08bf1-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="08bf1-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="08bf1-604">535.31</span><span class="sxs-lookup"><span data-stu-id="08bf1-604">535.31</span></span></td>
<td><span data-ttu-id="08bf1-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-606">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-607">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-608">20</span><span class="sxs-lookup"><span data-stu-id="08bf1-608">20</span></span></td>
<td><span data-ttu-id="08bf1-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="08bf1-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="08bf1-610">178.44</span><span class="sxs-lookup"><span data-stu-id="08bf1-610">178.44</span></span></td>
<td><span data-ttu-id="08bf1-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-612">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-613">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-614">60</span><span class="sxs-lookup"><span data-stu-id="08bf1-614">60</span></span></td>
<td><span data-ttu-id="08bf1-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="08bf1-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="08bf1-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="08bf1-616">4,487.12</span></span></td>
<td><span data-ttu-id="08bf1-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-618">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-619">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-620">20</span><span class="sxs-lookup"><span data-stu-id="08bf1-620">20</span></span></td>
<td><span data-ttu-id="08bf1-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="08bf1-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="08bf1-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="08bf1-622">1,495.71</span></span></td>
<td><span data-ttu-id="08bf1-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="08bf1-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="08bf1-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-625">Cost object</span></span></th>
<th><span data-ttu-id="08bf1-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="08bf1-626">Magnitude</span></span></th>
<th><span data-ttu-id="08bf1-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="08bf1-627">Allocation factor</span></span></th>
<th><span data-ttu-id="08bf1-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-628">Amount</span></span></th>
<th><span data-ttu-id="08bf1-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-630">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-631">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-632">80</span><span class="sxs-lookup"><span data-stu-id="08bf1-632">80</span></span></td>
<td><span data-ttu-id="08bf1-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="08bf1-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="08bf1-634">241.05</span><span class="sxs-lookup"><span data-stu-id="08bf1-634">241.05</span></span></td>
<td><span data-ttu-id="08bf1-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-636">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-637">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-638">15</span><span class="sxs-lookup"><span data-stu-id="08bf1-638">15</span></span></td>
<td><span data-ttu-id="08bf1-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="08bf1-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="08bf1-640">45.20</span><span class="sxs-lookup"><span data-stu-id="08bf1-640">45.20</span></span></td>
<td><span data-ttu-id="08bf1-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-642">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-643">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-644">80</span><span class="sxs-lookup"><span data-stu-id="08bf1-644">80</span></span></td>
<td><span data-ttu-id="08bf1-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="08bf1-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="08bf1-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="08bf1-646">2,507.09</span></span></td>
<td><span data-ttu-id="08bf1-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-648">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-649">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-650">15</span><span class="sxs-lookup"><span data-stu-id="08bf1-650">15</span></span></td>
<td><span data-ttu-id="08bf1-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="08bf1-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="08bf1-652">470.08</span><span class="sxs-lookup"><span data-stu-id="08bf1-652">470.08</span></span></td>
<td><span data-ttu-id="08bf1-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="08bf1-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="08bf1-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-655">Journal</span><span class="sxs-lookup"><span data-stu-id="08bf1-655">Journal</span></span></th>
<th><span data-ttu-id="08bf1-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="08bf1-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="08bf1-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="08bf1-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="08bf1-658">version</span><span class="sxs-lookup"><span data-stu-id="08bf1-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-659">00004</span><span class="sxs-lookup"><span data-stu-id="08bf1-659">00004</span></span></td>
<td><span data-ttu-id="08bf1-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="08bf1-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="08bf1-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="08bf1-661">Fiscal</span></span></td>
<td><span data-ttu-id="08bf1-662">2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-662">2017</span></span></td>
<td><span data-ttu-id="08bf1-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-663">Period 1</span></span></td>
<td><span data-ttu-id="08bf1-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="08bf1-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="08bf1-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="08bf1-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-668">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-669">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-672">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-672">CC001</span></span></td>
<td><span data-ttu-id="08bf1-673">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-673">HR</span></span></td>
<td><span data-ttu-id="08bf1-674">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-674">10001</span></span></td>
<td><span data-ttu-id="08bf1-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-675">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-676">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-677">500.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-679">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-679">CC001</span></span></td>
<td><span data-ttu-id="08bf1-680">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-680">HR</span></span></td>
<td><span data-ttu-id="08bf1-681">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-681">10001</span></span></td>
<td><span data-ttu-id="08bf1-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-682">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-683">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="08bf1-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-686">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-686">CC002</span></span></td>
<td><span data-ttu-id="08bf1-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-687">Finance</span></span></td>
<td><span data-ttu-id="08bf1-688">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-688">10001</span></span></td>
<td><span data-ttu-id="08bf1-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-689">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-690">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-691">675.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-693">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-693">CC002</span></span></td>
<td><span data-ttu-id="08bf1-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-694">Finance</span></span></td>
<td><span data-ttu-id="08bf1-695">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-695">10001</span></span></td>
<td><span data-ttu-id="08bf1-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-696">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-697">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="08bf1-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-700">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-700">CC003</span></span></td>
<td><span data-ttu-id="08bf1-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-701">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-702">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-702">10001</span></span></td>
<td><span data-ttu-id="08bf1-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-703">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-704">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-705">713.75</span><span class="sxs-lookup"><span data-stu-id="08bf1-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-707">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-707">CC003</span></span></td>
<td><span data-ttu-id="08bf1-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-708">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-709">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-709">10001</span></span></td>
<td><span data-ttu-id="08bf1-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-710">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-711">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="08bf1-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-714">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-714">CC003</span></span></td>
<td><span data-ttu-id="08bf1-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-715">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-716">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-716">10001</span></span></td>
<td><span data-ttu-id="08bf1-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-717">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-718">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-719">286.25</span><span class="sxs-lookup"><span data-stu-id="08bf1-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-721">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-721">CC003</span></span></td>
<td><span data-ttu-id="08bf1-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-722">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-723">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-723">10001</span></span></td>
<td><span data-ttu-id="08bf1-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-724">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-725">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="08bf1-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-728">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-729">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-730">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-730">10001</span></span></td>
<td><span data-ttu-id="08bf1-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-731">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-732">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-733">776.36</span><span class="sxs-lookup"><span data-stu-id="08bf1-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-735">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-736">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-737">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-737">10001</span></span></td>
<td><span data-ttu-id="08bf1-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-738">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-739">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="08bf1-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-742">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-743">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-744">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-744">10001</span></span></td>
<td><span data-ttu-id="08bf1-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-745">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-746">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-747">223.64</span><span class="sxs-lookup"><span data-stu-id="08bf1-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="08bf1-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-749">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-750">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-751">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-751">10001</span></span></td>
<td><span data-ttu-id="08bf1-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-752">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-753">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="08bf1-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="08bf1-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="08bf1-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="08bf1-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="08bf1-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-757">Cost element</span></span></th>
<th><span data-ttu-id="08bf1-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="08bf1-758">Cost behavior</span></span></th>
<th><span data-ttu-id="08bf1-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="08bf1-759">Amount</span></span></th>
<th><span data-ttu-id="08bf1-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="08bf1-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="08bf1-761">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-761">CC001</span></span></td>
<td><span data-ttu-id="08bf1-762">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-762">HR</span></span></td>
<td><span data-ttu-id="08bf1-763">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-763">10001</span></span></td>
<td><span data-ttu-id="08bf1-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-764">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-765">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-766">-500.00</span></span></td>
<td><span data-ttu-id="08bf1-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-768">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-768">CC002</span></span></td>
<td><span data-ttu-id="08bf1-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-769">Finance</span></span></td>
<td><span data-ttu-id="08bf1-770">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-770">10001</span></span></td>
<td><span data-ttu-id="08bf1-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-771">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-772">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-773">175.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-773">175.00</span></span></td>
<td><span data-ttu-id="08bf1-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-775">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-775">CC003</span></span></td>
<td><span data-ttu-id="08bf1-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-776">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-777">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-777">10001</span></span></td>
<td><span data-ttu-id="08bf1-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-778">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-779">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-780">275.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-780">275.00</span></span></td>
<td><span data-ttu-id="08bf1-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-782">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-782">CC004</span></span></td>
<td><span data-ttu-id="08bf1-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-783">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-784">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-784">10001</span></span></td>
<td><span data-ttu-id="08bf1-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-785">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-786">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-787">50,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-787">50,00</span></span></td>
<td><span data-ttu-id="08bf1-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-789">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-789">CC001</span></span></td>
<td><span data-ttu-id="08bf1-790">Personal</span><span class="sxs-lookup"><span data-stu-id="08bf1-790">HR</span></span></td>
<td><span data-ttu-id="08bf1-791">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-791">10001</span></span></td>
<td><span data-ttu-id="08bf1-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-792">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-793">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="08bf1-794">-1,245.71</span></span></td>
<td><span data-ttu-id="08bf1-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-796">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-796">CC002</span></span></td>
<td><span data-ttu-id="08bf1-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-797">Finance</span></span></td>
<td><span data-ttu-id="08bf1-798">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-798">10001</span></span></td>
<td><span data-ttu-id="08bf1-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-799">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-800">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-801">436.00</span><span class="sxs-lookup"><span data-stu-id="08bf1-801">436.00</span></span></td>
<td><span data-ttu-id="08bf1-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-803">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-803">CC003</span></span></td>
<td><span data-ttu-id="08bf1-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-804">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-805">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-805">10001</span></span></td>
<td><span data-ttu-id="08bf1-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-806">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-807">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-808">685.14</span><span class="sxs-lookup"><span data-stu-id="08bf1-808">685.14</span></span></td>
<td><span data-ttu-id="08bf1-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-810">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-810">CC004</span></span></td>
<td><span data-ttu-id="08bf1-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-811">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-812">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-812">10001</span></span></td>
<td><span data-ttu-id="08bf1-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-813">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-814">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-815">124.57</span><span class="sxs-lookup"><span data-stu-id="08bf1-815">124.57</span></span></td>
<td><span data-ttu-id="08bf1-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-817">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-817">CC002</span></span></td>
<td><span data-ttu-id="08bf1-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-818">Finance</span></span></td>
<td><span data-ttu-id="08bf1-819">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-819">10001</span></span></td>
<td><span data-ttu-id="08bf1-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-820">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-821">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-822">-675.00</span></span></td>
<td><span data-ttu-id="08bf1-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-824">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-824">CC003</span></span></td>
<td><span data-ttu-id="08bf1-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-825">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-826">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-826">10001</span></span></td>
<td><span data-ttu-id="08bf1-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-827">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-828">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-829">438.75</span><span class="sxs-lookup"><span data-stu-id="08bf1-829">438.75</span></span></td>
<td><span data-ttu-id="08bf1-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-831">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-831">CC004</span></span></td>
<td><span data-ttu-id="08bf1-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-832">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-833">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-833">10001</span></span></td>
<td><span data-ttu-id="08bf1-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-834">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-835">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-836">236.25</span><span class="sxs-lookup"><span data-stu-id="08bf1-836">236.25</span></span></td>
<td><span data-ttu-id="08bf1-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-838">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-838">CC002</span></span></td>
<td><span data-ttu-id="08bf1-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="08bf1-839">Finance</span></span></td>
<td><span data-ttu-id="08bf1-840">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-840">10001</span></span></td>
<td><span data-ttu-id="08bf1-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-841">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-842">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="08bf1-843">-8,150.29</span></span></td>
<td><span data-ttu-id="08bf1-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-845">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-845">CC003</span></span></td>
<td><span data-ttu-id="08bf1-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-846">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-847">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-847">10001</span></span></td>
<td><span data-ttu-id="08bf1-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-848">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-849">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="08bf1-850">5,297.69</span></span></td>
<td><span data-ttu-id="08bf1-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-852">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-852">CC004</span></span></td>
<td><span data-ttu-id="08bf1-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="08bf1-853">Packaging</span></span></td>
<td><span data-ttu-id="08bf1-854">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-854">10001</span></span></td>
<td><span data-ttu-id="08bf1-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-855">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-856">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="08bf1-857">2,852.60</span></span></td>
<td><span data-ttu-id="08bf1-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-859">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-859">CC003</span></span></td>
<td><span data-ttu-id="08bf1-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-860">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-861">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-861">10001</span></span></td>
<td><span data-ttu-id="08bf1-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-862">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-863">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="08bf1-864">-713.75</span></span></td>
<td><span data-ttu-id="08bf1-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-866">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-867">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-868">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-868">10001</span></span></td>
<td><span data-ttu-id="08bf1-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-869">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-870">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-871">535.31</span><span class="sxs-lookup"><span data-stu-id="08bf1-871">535.31</span></span></td>
<td><span data-ttu-id="08bf1-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-873">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-874">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-875">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-875">10001</span></span></td>
<td><span data-ttu-id="08bf1-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-876">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-877">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-878">178.44</span><span class="sxs-lookup"><span data-stu-id="08bf1-878">178.44</span></span></td>
<td><span data-ttu-id="08bf1-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-880">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-880">CC003</span></span></td>
<td><span data-ttu-id="08bf1-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-881">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-882">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-882">10001</span></span></td>
<td><span data-ttu-id="08bf1-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-883">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-884">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="08bf1-885">-5,982.83</span></span></td>
<td><span data-ttu-id="08bf1-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-887">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-888">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-889">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-889">10001</span></span></td>
<td><span data-ttu-id="08bf1-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-890">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-891">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="08bf1-892">4,487.12</span></span></td>
<td><span data-ttu-id="08bf1-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-894">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-895">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-896">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-896">10001</span></span></td>
<td><span data-ttu-id="08bf1-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-897">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-898">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="08bf1-899">1,495.71</span></span></td>
<td><span data-ttu-id="08bf1-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-901">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-901">CC003</span></span></td>
<td><span data-ttu-id="08bf1-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-902">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-903">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-903">10001</span></span></td>
<td><span data-ttu-id="08bf1-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-904">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-905">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="08bf1-906">-286.25</span></span></td>
<td><span data-ttu-id="08bf1-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-908">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-909">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-910">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-910">10001</span></span></td>
<td><span data-ttu-id="08bf1-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-911">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-912">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-913">241.05</span><span class="sxs-lookup"><span data-stu-id="08bf1-913">241.05</span></span></td>
<td><span data-ttu-id="08bf1-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-915">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-916">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-917">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-917">10001</span></span></td>
<td><span data-ttu-id="08bf1-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-918">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-919">Fixed cost</span></span></td>
<td><span data-ttu-id="08bf1-920">45.20</span><span class="sxs-lookup"><span data-stu-id="08bf1-920">45.20</span></span></td>
<td><span data-ttu-id="08bf1-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-922">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-922">CC003</span></span></td>
<td><span data-ttu-id="08bf1-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="08bf1-923">Assembly</span></span></td>
<td><span data-ttu-id="08bf1-924">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-924">10001</span></span></td>
<td><span data-ttu-id="08bf1-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-925">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-926">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="08bf1-927">-2,977.17</span></span></td>
<td><span data-ttu-id="08bf1-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-929">Prod 1</span></span></td>
<td><span data-ttu-id="08bf1-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-930">Product 1</span></span></td>
<td><span data-ttu-id="08bf1-931">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-931">10001</span></span></td>
<td><span data-ttu-id="08bf1-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-932">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-933">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="08bf1-934">2,507.09</span></span></td>
<td><span data-ttu-id="08bf1-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="08bf1-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-936">Prod 2</span></span></td>
<td><span data-ttu-id="08bf1-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-937">Product 2</span></span></td>
<td><span data-ttu-id="08bf1-938">10001</span><span class="sxs-lookup"><span data-stu-id="08bf1-938">10001</span></span></td>
<td><span data-ttu-id="08bf1-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-939">Electricity</span></span></td>
<td><span data-ttu-id="08bf1-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-940">Variable cost</span></span></td>
<td><span data-ttu-id="08bf1-941">470.08</span><span class="sxs-lookup"><span data-stu-id="08bf1-941">470.08</span></span></td>
<td><span data-ttu-id="08bf1-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="08bf1-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="08bf1-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="08bf1-943">Conclusion</span></span>
<span data-ttu-id="08bf1-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="08bf1-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="08bf1-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="08bf1-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="08bf1-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="08bf1-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="08bf1-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="08bf1-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="08bf1-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="08bf1-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="08bf1-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="08bf1-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="08bf1-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="08bf1-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="08bf1-951">CC099</span><span class="sxs-lookup"><span data-stu-id="08bf1-951">CC099</span></span></th>
<th><span data-ttu-id="08bf1-952">CC001</span><span class="sxs-lookup"><span data-stu-id="08bf1-952">CC001</span></span></th>
<th><span data-ttu-id="08bf1-953">CC002</span><span class="sxs-lookup"><span data-stu-id="08bf1-953">CC002</span></span></th>
<th><span data-ttu-id="08bf1-954">CC003</span><span class="sxs-lookup"><span data-stu-id="08bf1-954">CC003</span></span></th>
<th><span data-ttu-id="08bf1-955">CC004</span><span class="sxs-lookup"><span data-stu-id="08bf1-955">CC004</span></span></th>
<th><span data-ttu-id="08bf1-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-956">Proj 1</span></span></th>
<th><span data-ttu-id="08bf1-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-957">Proj 2</span></span></th>
<th><span data-ttu-id="08bf1-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="08bf1-958">Prod 1</span></span></th>
<th><span data-ttu-id="08bf1-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="08bf1-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="08bf1-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="08bf1-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="08bf1-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="08bf1-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-971">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="08bf1-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-973">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-974">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-975">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-976">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-977">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-978">776.36</span><span class="sxs-lookup"><span data-stu-id="08bf1-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-979">223.64</span><span class="sxs-lookup"><span data-stu-id="08bf1-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="08bf1-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="08bf1-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-982">000</span><span class="sxs-lookup"><span data-stu-id="08bf1-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-983">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-984">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-985">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-986">0,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-987">30,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-988">10,00</span><span class="sxs-lookup"><span data-stu-id="08bf1-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="08bf1-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="08bf1-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="08bf1-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="08bf1-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="08bf1-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="08bf1-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="08bf1-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="08bf1-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="08bf1-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="08bf1-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="08bf1-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="08bf1-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="08bf1-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="08bf1-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



