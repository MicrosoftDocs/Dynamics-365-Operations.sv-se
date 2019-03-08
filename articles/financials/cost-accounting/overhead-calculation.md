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
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "335127"
---
# <a name="overhead-calculation"></a><span data-ttu-id="81904-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="81904-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81904-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="81904-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="81904-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="81904-105">Term definition</span></span>
---------------

<span data-ttu-id="81904-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="81904-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="81904-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="81904-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="81904-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="81904-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="81904-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="81904-109">Rent</span></span>
-   <span data-ttu-id="81904-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-110">Electricity</span></span>
-   <span data-ttu-id="81904-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="81904-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="81904-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="81904-112">Overhead calculation overview</span></span>
<span data-ttu-id="81904-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="81904-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="81904-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="81904-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="81904-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="81904-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="81904-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="81904-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="81904-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="81904-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="81904-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="81904-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="81904-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="81904-119">Version type</span></span>
-   <span data-ttu-id="81904-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="81904-120">Date and time</span></span>
-   <span data-ttu-id="81904-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="81904-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="81904-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="81904-122">Fiscal year</span></span>
-   <span data-ttu-id="81904-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="81904-123">Fiscal period</span></span>

<span data-ttu-id="81904-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="81904-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="81904-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="81904-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="81904-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="81904-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="81904-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="81904-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="81904-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="81904-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="81904-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="81904-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="81904-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="81904-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="81904-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="81904-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="81904-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="81904-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="81904-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="81904-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="81904-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="81904-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="81904-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="81904-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="81904-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="81904-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="81904-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="81904-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="81904-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="81904-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="81904-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="81904-140">Main account</span></span></th>
<th><span data-ttu-id="81904-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="81904-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="81904-143">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-143">CC099</span></span></td>
<td><span data-ttu-id="81904-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-144">Default cost center</span></span></td>
<td><span data-ttu-id="81904-145">10001</span><span class="sxs-lookup"><span data-stu-id="81904-145">10001</span></span></td>
<td><span data-ttu-id="81904-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-146">Electricity</span></span></td>
<td><span data-ttu-id="81904-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="81904-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="81904-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="81904-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="81904-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="81904-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="81904-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="81904-151">Define the cost behavior rule</span></span>

<span data-ttu-id="81904-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="81904-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="81904-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="81904-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="81904-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="81904-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="81904-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="81904-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="81904-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="81904-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="81904-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="81904-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="81904-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="81904-159">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-160">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-160">Journal</span></span></th>
<th><span data-ttu-id="81904-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="81904-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="81904-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="81904-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="81904-163">version</span><span class="sxs-lookup"><span data-stu-id="81904-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-164">00001</span><span class="sxs-lookup"><span data-stu-id="81904-164">00001</span></span></td>
<td><span data-ttu-id="81904-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="81904-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="81904-166">Fiscal</span></span></td>
<td><span data-ttu-id="81904-167">2017</span><span class="sxs-lookup"><span data-stu-id="81904-167">2017</span></span></td>
<td><span data-ttu-id="81904-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="81904-168">Period 1</span></span></td>
<td><span data-ttu-id="81904-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="81904-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="81904-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="81904-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="81904-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-173">Cost element</span></span></th>
<th><span data-ttu-id="81904-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-174">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="81904-177">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-177">CC099</span></span></td>
<td><span data-ttu-id="81904-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-178">Default cost center</span></span></td>
<td><span data-ttu-id="81904-179">10001</span><span class="sxs-lookup"><span data-stu-id="81904-179">10001</span></span></td>
<td><span data-ttu-id="81904-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-180">Electricity</span></span></td>
<td><span data-ttu-id="81904-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="81904-181">Unclassified</span></span></td>
<td><span data-ttu-id="81904-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="81904-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="81904-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-185">Cost element</span></span></th>
<th><span data-ttu-id="81904-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-186">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-187">Amount</span></span></th>
<th><span data-ttu-id="81904-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-189">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-189">CC099</span></span></td>
<td><span data-ttu-id="81904-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-190">Default cost center</span></span></td>
<td><span data-ttu-id="81904-191">10001</span><span class="sxs-lookup"><span data-stu-id="81904-191">10001</span></span></td>
<td><span data-ttu-id="81904-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-192">Electricity</span></span></td>
<td><span data-ttu-id="81904-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="81904-193">Unclassified</span></span></td>
<td><span data-ttu-id="81904-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-194">10,000.00</span></span></td>
<td><span data-ttu-id="81904-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-196">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-196">CC099</span></span></td>
<td><span data-ttu-id="81904-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-197">Default cost center</span></span></td>
<td><span data-ttu-id="81904-198">10001</span><span class="sxs-lookup"><span data-stu-id="81904-198">10001</span></span></td>
<td><span data-ttu-id="81904-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-199">Electricity</span></span></td>
<td><span data-ttu-id="81904-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="81904-200">Unclassified</span></span></td>
<td><span data-ttu-id="81904-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-201">-10,000.00</span></span></td>
<td><span data-ttu-id="81904-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-203">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-203">CC099</span></span></td>
<td><span data-ttu-id="81904-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-204">Default cost center</span></span></td>
<td><span data-ttu-id="81904-205">10001</span><span class="sxs-lookup"><span data-stu-id="81904-205">10001</span></span></td>
<td><span data-ttu-id="81904-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-206">Electricity</span></span></td>
<td><span data-ttu-id="81904-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-207">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-208">1,000.00</span></span></td>
<td><span data-ttu-id="81904-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-210">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-210">CC099</span></span></td>
<td><span data-ttu-id="81904-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-211">Default cost center</span></span></td>
<td><span data-ttu-id="81904-212">10001</span><span class="sxs-lookup"><span data-stu-id="81904-212">10001</span></span></td>
<td><span data-ttu-id="81904-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-213">Electricity</span></span></td>
<td><span data-ttu-id="81904-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-214">Variable cost</span></span></td>
<td><span data-ttu-id="81904-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="81904-215">9,000.00</span></span></td>
<td><span data-ttu-id="81904-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="81904-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="81904-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="81904-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="81904-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="81904-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="81904-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="81904-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="81904-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="81904-221">Define the cost distribution rule</span></span>

<span data-ttu-id="81904-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="81904-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="81904-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="81904-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="81904-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="81904-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="81904-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="81904-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="81904-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="81904-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="81904-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="81904-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-228">Cost object</span></span></th>
<th><span data-ttu-id="81904-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="81904-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-230">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-230">CC001</span></span></td>
<td><span data-ttu-id="81904-231">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-231">HR</span></span></td>
<td><span data-ttu-id="81904-232">1 000</span><span class="sxs-lookup"><span data-stu-id="81904-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-233">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-233">CC002</span></span></td>
<td><span data-ttu-id="81904-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-234">Finance</span></span></td>
<td><span data-ttu-id="81904-235">6,000</span><span class="sxs-lookup"><span data-stu-id="81904-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-236">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-236">CC003</span></span></td>
<td><span data-ttu-id="81904-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-237">Assembly</span></span></td>
<td><span data-ttu-id="81904-238">0</span><span class="sxs-lookup"><span data-stu-id="81904-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="81904-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-240">Cost object</span></span></th>
<th><span data-ttu-id="81904-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-241">Magnitude</span></span></th>
<th><span data-ttu-id="81904-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-242">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-244">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-244">CC001</span></span></td>
<td><span data-ttu-id="81904-245">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-245">HR</span></span></td>
<td><span data-ttu-id="81904-246">1 000</span><span class="sxs-lookup"><span data-stu-id="81904-246">1,000</span></span></td>
<td><span data-ttu-id="81904-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="81904-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="81904-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-249">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-249">CC002</span></span></td>
<td><span data-ttu-id="81904-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-250">Finance</span></span></td>
<td><span data-ttu-id="81904-251">6,000</span><span class="sxs-lookup"><span data-stu-id="81904-251">6,000</span></span></td>
<td><span data-ttu-id="81904-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="81904-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="81904-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-254">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-254">CC003</span></span></td>
<td><span data-ttu-id="81904-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-255">Assembly</span></span></td>
<td><span data-ttu-id="81904-256">0</span><span class="sxs-lookup"><span data-stu-id="81904-256">0</span></span></td>
<td><span data-ttu-id="81904-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="81904-258">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="81904-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="81904-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="81904-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-261">Cost object</span></span></th>
<th><span data-ttu-id="81904-262">Formel</span><span class="sxs-lookup"><span data-stu-id="81904-262">Formula</span></span></th>
<th><span data-ttu-id="81904-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-263">Magnitude</span></span></th>
<th><span data-ttu-id="81904-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-264">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-266">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-266">CC001</span></span></td>
<td><span data-ttu-id="81904-267">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-267">HR</span></span></td>
<td><span data-ttu-id="81904-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="81904-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="81904-269">1</span><span class="sxs-lookup"><span data-stu-id="81904-269">1</span></span></td>
<td><span data-ttu-id="81904-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="81904-271">500.00</span><span class="sxs-lookup"><span data-stu-id="81904-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-272">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-272">CC002</span></span></td>
<td><span data-ttu-id="81904-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-273">Finance</span></span></td>
<td><span data-ttu-id="81904-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="81904-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="81904-275">1</span><span class="sxs-lookup"><span data-stu-id="81904-275">1</span></span></td>
<td><span data-ttu-id="81904-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="81904-277">500.00</span><span class="sxs-lookup"><span data-stu-id="81904-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-278">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-278">CC003</span></span></td>
<td><span data-ttu-id="81904-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-279">Assembly</span></span></td>
<td><span data-ttu-id="81904-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="81904-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="81904-281">0</span><span class="sxs-lookup"><span data-stu-id="81904-281">0</span></span></td>
<td><span data-ttu-id="81904-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="81904-283">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="81904-284">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-285">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-285">Journal</span></span></th>
<th><span data-ttu-id="81904-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="81904-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="81904-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="81904-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="81904-288">version</span><span class="sxs-lookup"><span data-stu-id="81904-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-289">00002</span><span class="sxs-lookup"><span data-stu-id="81904-289">00002</span></span></td>
<td><span data-ttu-id="81904-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="81904-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="81904-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="81904-291">Fiscal</span></span></td>
<td><span data-ttu-id="81904-292">2017</span><span class="sxs-lookup"><span data-stu-id="81904-292">2017</span></span></td>
<td><span data-ttu-id="81904-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="81904-293">Period 1</span></span></td>
<td><span data-ttu-id="81904-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="81904-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="81904-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="81904-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="81904-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-298">Cost element</span></span></th>
<th><span data-ttu-id="81904-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-299">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-302">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-302">CC099</span></span></td>
<td><span data-ttu-id="81904-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-303">Default cost center</span></span></td>
<td><span data-ttu-id="81904-304">10001</span><span class="sxs-lookup"><span data-stu-id="81904-304">10001</span></span></td>
<td><span data-ttu-id="81904-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-305">Electricity</span></span></td>
<td><span data-ttu-id="81904-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-306">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-309">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-309">CC099</span></span></td>
<td><span data-ttu-id="81904-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-310">Default cost center</span></span></td>
<td><span data-ttu-id="81904-311">10001</span><span class="sxs-lookup"><span data-stu-id="81904-311">10001</span></span></td>
<td><span data-ttu-id="81904-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-312">Electricity</span></span></td>
<td><span data-ttu-id="81904-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-313">Variable cost</span></span></td>
<td><span data-ttu-id="81904-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="81904-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="81904-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="81904-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-317">Cost element</span></span></th>
<th><span data-ttu-id="81904-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-318">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-319">Amount</span></span></th>
<th><span data-ttu-id="81904-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-321">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-321">CC099</span></span></td>
<td><span data-ttu-id="81904-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-322">Default cost center</span></span></td>
<td><span data-ttu-id="81904-323">10001</span><span class="sxs-lookup"><span data-stu-id="81904-323">10001</span></span></td>
<td><span data-ttu-id="81904-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-324">Electricity</span></span></td>
<td><span data-ttu-id="81904-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-325">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-326">-1,000.00</span></span></td>
<td><span data-ttu-id="81904-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-328">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-328">CC001</span></span></td>
<td><span data-ttu-id="81904-329">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-329">HR</span></span></td>
<td><span data-ttu-id="81904-330">10001</span><span class="sxs-lookup"><span data-stu-id="81904-330">10001</span></span></td>
<td><span data-ttu-id="81904-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-331">Electricity</span></span></td>
<td><span data-ttu-id="81904-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-332">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-333">500.00</span><span class="sxs-lookup"><span data-stu-id="81904-333">500.00</span></span></td>
<td><span data-ttu-id="81904-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-335">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-335">CC002</span></span></td>
<td><span data-ttu-id="81904-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-336">Finance</span></span></td>
<td><span data-ttu-id="81904-337">10001</span><span class="sxs-lookup"><span data-stu-id="81904-337">10001</span></span></td>
<td><span data-ttu-id="81904-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-338">Electricity</span></span></td>
<td><span data-ttu-id="81904-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-339">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-340">500.00</span><span class="sxs-lookup"><span data-stu-id="81904-340">500.00</span></span></td>
<td><span data-ttu-id="81904-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-342">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-342">CC099</span></span></td>
<td><span data-ttu-id="81904-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="81904-343">Default cost center</span></span></td>
<td><span data-ttu-id="81904-344">10001</span><span class="sxs-lookup"><span data-stu-id="81904-344">10001</span></span></td>
<td><span data-ttu-id="81904-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-345">Electricity</span></span></td>
<td><span data-ttu-id="81904-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-346">Variable cost</span></span></td>
<td><span data-ttu-id="81904-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="81904-347">-9,000.00</span></span></td>
<td><span data-ttu-id="81904-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-349">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-349">CC001</span></span></td>
<td><span data-ttu-id="81904-350">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-350">HR</span></span></td>
<td><span data-ttu-id="81904-351">10001</span><span class="sxs-lookup"><span data-stu-id="81904-351">10001</span></span></td>
<td><span data-ttu-id="81904-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-352">Electricity</span></span></td>
<td><span data-ttu-id="81904-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-353">Variable cost</span></span></td>
<td><span data-ttu-id="81904-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="81904-354">1,285.71</span></span></td>
<td><span data-ttu-id="81904-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-356">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-356">CC002</span></span></td>
<td><span data-ttu-id="81904-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-357">Finance</span></span></td>
<td><span data-ttu-id="81904-358">10001</span><span class="sxs-lookup"><span data-stu-id="81904-358">10001</span></span></td>
<td><span data-ttu-id="81904-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-359">Electricity</span></span></td>
<td><span data-ttu-id="81904-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-360">Variable cost</span></span></td>
<td><span data-ttu-id="81904-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="81904-361">7,714.29</span></span></td>
<td><span data-ttu-id="81904-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="81904-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="81904-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="81904-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="81904-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="81904-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="81904-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="81904-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-367">Define the overhead rate</span></span>

<span data-ttu-id="81904-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="81904-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="81904-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="81904-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-370">Cost object</span></span></th>
<th><span data-ttu-id="81904-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="81904-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-372">Proj 1</span></span></td>
<td><span data-ttu-id="81904-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="81904-373">Project 1</span></span></td>
<td><span data-ttu-id="81904-374">3</span><span class="sxs-lookup"><span data-stu-id="81904-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-375">Proj 2</span></span></td>
<td><span data-ttu-id="81904-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="81904-376">Project 2</span></span></td>
<td><span data-ttu-id="81904-377">1</span><span class="sxs-lookup"><span data-stu-id="81904-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="81904-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-379">Cost object</span></span></th>
<th><span data-ttu-id="81904-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-380">Cost element</span></span></th>
<th><span data-ttu-id="81904-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-381">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="81904-382">Units</span></span></th>
<th><span data-ttu-id="81904-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="81904-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-384">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-384">CC001</span></span></td>
<td><span data-ttu-id="81904-385">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-385">HR</span></span></td>
<td><span data-ttu-id="81904-386">10001</span><span class="sxs-lookup"><span data-stu-id="81904-386">10001</span></span></td>
<td><span data-ttu-id="81904-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-387">Variable cost</span></span></td>
<td><span data-ttu-id="81904-388">1</span><span class="sxs-lookup"><span data-stu-id="81904-388">1</span></span></td>
<td><span data-ttu-id="81904-389">10</span><span class="sxs-lookup"><span data-stu-id="81904-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="81904-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-391">Cost object</span></span></th>
<th><span data-ttu-id="81904-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-392">Magnitude</span></span></th>
<th><span data-ttu-id="81904-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-393">Cost element</span></span></th>
<th><span data-ttu-id="81904-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-394">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-396">Proj 1</span></span></td>
<td><span data-ttu-id="81904-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="81904-397">Project 1</span></span></td>
<td><span data-ttu-id="81904-398">3</span><span class="sxs-lookup"><span data-stu-id="81904-398">3</span></span></td>
<td><span data-ttu-id="81904-399">10001</span><span class="sxs-lookup"><span data-stu-id="81904-399">10001</span></span></td>
<td><span data-ttu-id="81904-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="81904-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="81904-401">30,00</span><span class="sxs-lookup"><span data-stu-id="81904-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-402">Proj 2</span></span></td>
<td><span data-ttu-id="81904-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="81904-403">Project 2</span></span></td>
<td><span data-ttu-id="81904-404">1</span><span class="sxs-lookup"><span data-stu-id="81904-404">1</span></span></td>
<td><span data-ttu-id="81904-405">10001</span><span class="sxs-lookup"><span data-stu-id="81904-405">10001</span></span></td>
<td><span data-ttu-id="81904-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="81904-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="81904-407">10,00</span><span class="sxs-lookup"><span data-stu-id="81904-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="81904-408">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-409">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-409">Journal</span></span></th>
<th><span data-ttu-id="81904-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="81904-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="81904-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="81904-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="81904-412">version</span><span class="sxs-lookup"><span data-stu-id="81904-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-413">00003</span><span class="sxs-lookup"><span data-stu-id="81904-413">00003</span></span></td>
<td><span data-ttu-id="81904-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="81904-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="81904-415">Fiscal</span></span></td>
<td><span data-ttu-id="81904-416">2017</span><span class="sxs-lookup"><span data-stu-id="81904-416">2017</span></span></td>
<td><span data-ttu-id="81904-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="81904-417">Period 1</span></span></td>
<td><span data-ttu-id="81904-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="81904-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="81904-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="81904-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="81904-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-421">Cost object</span></span></th>
<th><span data-ttu-id="81904-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-424">Proj 1</span></span></td>
<td><span data-ttu-id="81904-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="81904-426">3,00</span><span class="sxs-lookup"><span data-stu-id="81904-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-428">Proj 2</span></span></td>
<td><span data-ttu-id="81904-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="81904-430">1,00</span><span class="sxs-lookup"><span data-stu-id="81904-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="81904-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="81904-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-433">Cost element</span></span></th>
<th><span data-ttu-id="81904-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-434">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-435">Amount</span></span></th>
<th><span data-ttu-id="81904-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="81904-437">CC0001</span></span></td>
<td><span data-ttu-id="81904-438">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-438">HR</span></span></td>
<td><span data-ttu-id="81904-439">10001</span><span class="sxs-lookup"><span data-stu-id="81904-439">10001</span></span></td>
<td><span data-ttu-id="81904-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-440">Electricity</span></span></td>
<td><span data-ttu-id="81904-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-441">Variable cost</span></span></td>
<td><span data-ttu-id="81904-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="81904-442">-30.00</span></span></td>
<td><span data-ttu-id="81904-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-444">Proj 1</span></span></td>
<td><span data-ttu-id="81904-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="81904-446">10001</span><span class="sxs-lookup"><span data-stu-id="81904-446">10001</span></span></td>
<td><span data-ttu-id="81904-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-447">Electricity</span></span></td>
<td><span data-ttu-id="81904-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-448">Variable cost</span></span></td>
<td><span data-ttu-id="81904-449">30,00</span><span class="sxs-lookup"><span data-stu-id="81904-449">30.00</span></span></td>
<td><span data-ttu-id="81904-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-451">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-451">CC001</span></span></td>
<td><span data-ttu-id="81904-452">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-452">HR</span></span></td>
<td><span data-ttu-id="81904-453">10001</span><span class="sxs-lookup"><span data-stu-id="81904-453">10001</span></span></td>
<td><span data-ttu-id="81904-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-454">Electricity</span></span></td>
<td><span data-ttu-id="81904-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-455">Variable cost</span></span></td>
<td><span data-ttu-id="81904-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="81904-456">-10.00</span></span></td>
<td><span data-ttu-id="81904-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-458">Proj 2</span></span></td>
<td><span data-ttu-id="81904-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="81904-460">10001</span><span class="sxs-lookup"><span data-stu-id="81904-460">10001</span></span></td>
<td><span data-ttu-id="81904-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-461">Electricity</span></span></td>
<td><span data-ttu-id="81904-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-462">Variable cost</span></span></td>
<td><span data-ttu-id="81904-463">10,00</span><span class="sxs-lookup"><span data-stu-id="81904-463">10.00</span></span></td>
<td><span data-ttu-id="81904-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="81904-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="81904-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="81904-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="81904-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="81904-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="81904-468">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="81904-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="81904-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="81904-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="81904-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="81904-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="81904-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="81904-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="81904-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="81904-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="81904-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="81904-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="81904-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="81904-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="81904-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="81904-475">Define the cost allocation</span></span>

<span data-ttu-id="81904-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="81904-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="81904-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="81904-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="81904-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="81904-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-479">Cost object</span></span></th>
<th><span data-ttu-id="81904-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="81904-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-481">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-481">CC002</span></span></td>
<td><span data-ttu-id="81904-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-482">Finance</span></span></td>
<td><span data-ttu-id="81904-483">35</span><span class="sxs-lookup"><span data-stu-id="81904-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-484">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-484">CC003</span></span></td>
<td><span data-ttu-id="81904-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-485">Assembly</span></span></td>
<td><span data-ttu-id="81904-486">55</span><span class="sxs-lookup"><span data-stu-id="81904-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-487">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-487">CC004</span></span></td>
<td><span data-ttu-id="81904-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-488">Packaging</span></span></td>
<td><span data-ttu-id="81904-489">10</span><span class="sxs-lookup"><span data-stu-id="81904-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="81904-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="81904-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="81904-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-492">Cost object</span></span></th>
<th><span data-ttu-id="81904-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="81904-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-494">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-494">CC003</span></span></td>
<td><span data-ttu-id="81904-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-495">Assembly</span></span></td>
<td><span data-ttu-id="81904-496">65</span><span class="sxs-lookup"><span data-stu-id="81904-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-497">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-497">CC004</span></span></td>
<td><span data-ttu-id="81904-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-498">Packaging</span></span></td>
<td><span data-ttu-id="81904-499">35</span><span class="sxs-lookup"><span data-stu-id="81904-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="81904-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="81904-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="81904-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-502">Cost object</span></span></th>
<th><span data-ttu-id="81904-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="81904-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-504">Prod 1</span></span></td>
<td><span data-ttu-id="81904-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-505">Product 1</span></span></td>
<td><span data-ttu-id="81904-506">60</span><span class="sxs-lookup"><span data-stu-id="81904-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-507">Prod 2</span></span></td>
<td><span data-ttu-id="81904-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-508">Product 2</span></span></td>
<td><span data-ttu-id="81904-509">20</span><span class="sxs-lookup"><span data-stu-id="81904-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="81904-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="81904-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="81904-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-512">Cost object</span></span></th>
<th><span data-ttu-id="81904-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="81904-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-514">Prod 1</span></span></td>
<td><span data-ttu-id="81904-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-515">Product 1</span></span></td>
<td><span data-ttu-id="81904-516">80</span><span class="sxs-lookup"><span data-stu-id="81904-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-517">Prod 2</span></span></td>
<td><span data-ttu-id="81904-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-518">Product 2</span></span></td>
<td><span data-ttu-id="81904-519">15</span><span class="sxs-lookup"><span data-stu-id="81904-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="81904-520">I Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="81904-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="81904-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="81904-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="81904-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="81904-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-523">Cost object</span></span></th>
<th><span data-ttu-id="81904-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-524">Magnitude</span></span></th>
<th><span data-ttu-id="81904-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-525">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-526">Amount</span></span></th>
<th><span data-ttu-id="81904-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-528">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-528">CC002</span></span></td>
<td><span data-ttu-id="81904-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-529">Finance</span></span></td>
<td><span data-ttu-id="81904-530">35</span><span class="sxs-lookup"><span data-stu-id="81904-530">35</span></span></td>
<td><span data-ttu-id="81904-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="81904-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="81904-532">175.00</span><span class="sxs-lookup"><span data-stu-id="81904-532">175.00</span></span></td>
<td><span data-ttu-id="81904-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-534">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-534">CC003</span></span></td>
<td><span data-ttu-id="81904-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-535">Assembly</span></span></td>
<td><span data-ttu-id="81904-536">55</span><span class="sxs-lookup"><span data-stu-id="81904-536">55</span></span></td>
<td><span data-ttu-id="81904-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="81904-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="81904-538">275.00</span><span class="sxs-lookup"><span data-stu-id="81904-538">275.00</span></span></td>
<td><span data-ttu-id="81904-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-540">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-540">CC004</span></span></td>
<td><span data-ttu-id="81904-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-541">Packaging</span></span></td>
<td><span data-ttu-id="81904-542">10</span><span class="sxs-lookup"><span data-stu-id="81904-542">10</span></span></td>
<td><span data-ttu-id="81904-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="81904-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="81904-544">50,00</span><span class="sxs-lookup"><span data-stu-id="81904-544">50.00</span></span></td>
<td><span data-ttu-id="81904-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-546">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-546">CC002</span></span></td>
<td><span data-ttu-id="81904-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-547">Finance</span></span></td>
<td><span data-ttu-id="81904-548">35</span><span class="sxs-lookup"><span data-stu-id="81904-548">35</span></span></td>
<td><span data-ttu-id="81904-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="81904-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="81904-550">436.00</span><span class="sxs-lookup"><span data-stu-id="81904-550">436.00</span></span></td>
<td><span data-ttu-id="81904-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-552">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-552">CC003</span></span></td>
<td><span data-ttu-id="81904-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-553">Assembly</span></span></td>
<td><span data-ttu-id="81904-554">55</span><span class="sxs-lookup"><span data-stu-id="81904-554">55</span></span></td>
<td><span data-ttu-id="81904-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="81904-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="81904-556">685.14</span><span class="sxs-lookup"><span data-stu-id="81904-556">685.14</span></span></td>
<td><span data-ttu-id="81904-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-558">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-558">CC004</span></span></td>
<td><span data-ttu-id="81904-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-559">Packaging</span></span></td>
<td><span data-ttu-id="81904-560">10</span><span class="sxs-lookup"><span data-stu-id="81904-560">10</span></span></td>
<td><span data-ttu-id="81904-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="81904-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="81904-562">124.57</span><span class="sxs-lookup"><span data-stu-id="81904-562">124.57</span></span></td>
<td><span data-ttu-id="81904-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="81904-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-565">Cost object</span></span></th>
<th><span data-ttu-id="81904-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-566">Magnitude</span></span></th>
<th><span data-ttu-id="81904-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-567">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-568">Amount</span></span></th>
<th><span data-ttu-id="81904-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-570">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-570">CC003</span></span></td>
<td><span data-ttu-id="81904-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-571">Assembly</span></span></td>
<td><span data-ttu-id="81904-572">65</span><span class="sxs-lookup"><span data-stu-id="81904-572">65</span></span></td>
<td><span data-ttu-id="81904-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="81904-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="81904-574">438.75</span><span class="sxs-lookup"><span data-stu-id="81904-574">438.75</span></span></td>
<td><span data-ttu-id="81904-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-576">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-576">CC004</span></span></td>
<td><span data-ttu-id="81904-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-577">Packaging</span></span></td>
<td><span data-ttu-id="81904-578">35</span><span class="sxs-lookup"><span data-stu-id="81904-578">35</span></span></td>
<td><span data-ttu-id="81904-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="81904-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="81904-580">236.25</span><span class="sxs-lookup"><span data-stu-id="81904-580">236.25</span></span></td>
<td><span data-ttu-id="81904-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-582">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-582">CC003</span></span></td>
<td><span data-ttu-id="81904-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-583">Assembly</span></span></td>
<td><span data-ttu-id="81904-584">65</span><span class="sxs-lookup"><span data-stu-id="81904-584">65</span></span></td>
<td><span data-ttu-id="81904-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="81904-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="81904-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="81904-586">5,297.69</span></span></td>
<td><span data-ttu-id="81904-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-588">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-588">CC004</span></span></td>
<td><span data-ttu-id="81904-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-589">Packaging</span></span></td>
<td><span data-ttu-id="81904-590">35</span><span class="sxs-lookup"><span data-stu-id="81904-590">35</span></span></td>
<td><span data-ttu-id="81904-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="81904-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="81904-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="81904-592">2,852.60</span></span></td>
<td><span data-ttu-id="81904-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="81904-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-595">Cost object</span></span></th>
<th><span data-ttu-id="81904-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-596">Magnitude</span></span></th>
<th><span data-ttu-id="81904-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-597">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-598">Amount</span></span></th>
<th><span data-ttu-id="81904-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-600">Prod 1</span></span></td>
<td><span data-ttu-id="81904-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-601">Product 1</span></span></td>
<td><span data-ttu-id="81904-602">60</span><span class="sxs-lookup"><span data-stu-id="81904-602">60</span></span></td>
<td><span data-ttu-id="81904-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="81904-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="81904-604">535.31</span><span class="sxs-lookup"><span data-stu-id="81904-604">535.31</span></span></td>
<td><span data-ttu-id="81904-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-606">Prod 2</span></span></td>
<td><span data-ttu-id="81904-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-607">Product 2</span></span></td>
<td><span data-ttu-id="81904-608">20</span><span class="sxs-lookup"><span data-stu-id="81904-608">20</span></span></td>
<td><span data-ttu-id="81904-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="81904-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="81904-610">178.44</span><span class="sxs-lookup"><span data-stu-id="81904-610">178.44</span></span></td>
<td><span data-ttu-id="81904-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-612">Prod 1</span></span></td>
<td><span data-ttu-id="81904-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-613">Product 1</span></span></td>
<td><span data-ttu-id="81904-614">60</span><span class="sxs-lookup"><span data-stu-id="81904-614">60</span></span></td>
<td><span data-ttu-id="81904-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="81904-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="81904-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="81904-616">4,487.12</span></span></td>
<td><span data-ttu-id="81904-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-618">Prod 2</span></span></td>
<td><span data-ttu-id="81904-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-619">Product 2</span></span></td>
<td><span data-ttu-id="81904-620">20</span><span class="sxs-lookup"><span data-stu-id="81904-620">20</span></span></td>
<td><span data-ttu-id="81904-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="81904-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="81904-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="81904-622">1,495.71</span></span></td>
<td><span data-ttu-id="81904-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="81904-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="81904-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-625">Cost object</span></span></th>
<th><span data-ttu-id="81904-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="81904-626">Magnitude</span></span></th>
<th><span data-ttu-id="81904-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="81904-627">Allocation factor</span></span></th>
<th><span data-ttu-id="81904-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-628">Amount</span></span></th>
<th><span data-ttu-id="81904-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-630">Prod 1</span></span></td>
<td><span data-ttu-id="81904-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-631">Product 1</span></span></td>
<td><span data-ttu-id="81904-632">80</span><span class="sxs-lookup"><span data-stu-id="81904-632">80</span></span></td>
<td><span data-ttu-id="81904-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="81904-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="81904-634">241.05</span><span class="sxs-lookup"><span data-stu-id="81904-634">241.05</span></span></td>
<td><span data-ttu-id="81904-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-636">Prod 2</span></span></td>
<td><span data-ttu-id="81904-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-637">Product 2</span></span></td>
<td><span data-ttu-id="81904-638">15</span><span class="sxs-lookup"><span data-stu-id="81904-638">15</span></span></td>
<td><span data-ttu-id="81904-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="81904-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="81904-640">45.20</span><span class="sxs-lookup"><span data-stu-id="81904-640">45.20</span></span></td>
<td><span data-ttu-id="81904-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-642">Prod 1</span></span></td>
<td><span data-ttu-id="81904-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-643">Product 1</span></span></td>
<td><span data-ttu-id="81904-644">80</span><span class="sxs-lookup"><span data-stu-id="81904-644">80</span></span></td>
<td><span data-ttu-id="81904-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="81904-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="81904-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="81904-646">2,507.09</span></span></td>
<td><span data-ttu-id="81904-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-648">Prod 2</span></span></td>
<td><span data-ttu-id="81904-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-649">Product 2</span></span></td>
<td><span data-ttu-id="81904-650">15</span><span class="sxs-lookup"><span data-stu-id="81904-650">15</span></span></td>
<td><span data-ttu-id="81904-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="81904-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="81904-652">470.08</span><span class="sxs-lookup"><span data-stu-id="81904-652">470.08</span></span></td>
<td><span data-ttu-id="81904-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="81904-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="81904-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-655">Journal</span><span class="sxs-lookup"><span data-stu-id="81904-655">Journal</span></span></th>
<th><span data-ttu-id="81904-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="81904-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="81904-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="81904-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="81904-658">version</span><span class="sxs-lookup"><span data-stu-id="81904-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-659">00004</span><span class="sxs-lookup"><span data-stu-id="81904-659">00004</span></span></td>
<td><span data-ttu-id="81904-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="81904-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="81904-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="81904-661">Fiscal</span></span></td>
<td><span data-ttu-id="81904-662">2017</span><span class="sxs-lookup"><span data-stu-id="81904-662">2017</span></span></td>
<td><span data-ttu-id="81904-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="81904-663">Period 1</span></span></td>
<td><span data-ttu-id="81904-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="81904-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="81904-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="81904-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="81904-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="81904-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-668">Cost element</span></span></th>
<th><span data-ttu-id="81904-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-669">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-672">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-672">CC001</span></span></td>
<td><span data-ttu-id="81904-673">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-673">HR</span></span></td>
<td><span data-ttu-id="81904-674">10001</span><span class="sxs-lookup"><span data-stu-id="81904-674">10001</span></span></td>
<td><span data-ttu-id="81904-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-675">Electricity</span></span></td>
<td><span data-ttu-id="81904-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-676">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-677">500.00</span><span class="sxs-lookup"><span data-stu-id="81904-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-679">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-679">CC001</span></span></td>
<td><span data-ttu-id="81904-680">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-680">HR</span></span></td>
<td><span data-ttu-id="81904-681">10001</span><span class="sxs-lookup"><span data-stu-id="81904-681">10001</span></span></td>
<td><span data-ttu-id="81904-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-682">Electricity</span></span></td>
<td><span data-ttu-id="81904-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-683">Variable cost</span></span></td>
<td><span data-ttu-id="81904-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="81904-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-686">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-686">CC002</span></span></td>
<td><span data-ttu-id="81904-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-687">Finance</span></span></td>
<td><span data-ttu-id="81904-688">10001</span><span class="sxs-lookup"><span data-stu-id="81904-688">10001</span></span></td>
<td><span data-ttu-id="81904-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-689">Electricity</span></span></td>
<td><span data-ttu-id="81904-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-690">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-691">675.00</span><span class="sxs-lookup"><span data-stu-id="81904-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-693">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-693">CC002</span></span></td>
<td><span data-ttu-id="81904-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-694">Finance</span></span></td>
<td><span data-ttu-id="81904-695">10001</span><span class="sxs-lookup"><span data-stu-id="81904-695">10001</span></span></td>
<td><span data-ttu-id="81904-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-696">Electricity</span></span></td>
<td><span data-ttu-id="81904-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-697">Variable cost</span></span></td>
<td><span data-ttu-id="81904-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="81904-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-700">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-700">CC003</span></span></td>
<td><span data-ttu-id="81904-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-701">Assembly</span></span></td>
<td><span data-ttu-id="81904-702">10001</span><span class="sxs-lookup"><span data-stu-id="81904-702">10001</span></span></td>
<td><span data-ttu-id="81904-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-703">Electricity</span></span></td>
<td><span data-ttu-id="81904-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-704">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-705">713.75</span><span class="sxs-lookup"><span data-stu-id="81904-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-707">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-707">CC003</span></span></td>
<td><span data-ttu-id="81904-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-708">Assembly</span></span></td>
<td><span data-ttu-id="81904-709">10001</span><span class="sxs-lookup"><span data-stu-id="81904-709">10001</span></span></td>
<td><span data-ttu-id="81904-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-710">Electricity</span></span></td>
<td><span data-ttu-id="81904-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-711">Variable cost</span></span></td>
<td><span data-ttu-id="81904-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="81904-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-714">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-714">CC003</span></span></td>
<td><span data-ttu-id="81904-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-715">Packaging</span></span></td>
<td><span data-ttu-id="81904-716">10001</span><span class="sxs-lookup"><span data-stu-id="81904-716">10001</span></span></td>
<td><span data-ttu-id="81904-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-717">Electricity</span></span></td>
<td><span data-ttu-id="81904-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-718">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-719">286.25</span><span class="sxs-lookup"><span data-stu-id="81904-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-721">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-721">CC003</span></span></td>
<td><span data-ttu-id="81904-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-722">Packaging</span></span></td>
<td><span data-ttu-id="81904-723">10001</span><span class="sxs-lookup"><span data-stu-id="81904-723">10001</span></span></td>
<td><span data-ttu-id="81904-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-724">Electricity</span></span></td>
<td><span data-ttu-id="81904-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-725">Variable cost</span></span></td>
<td><span data-ttu-id="81904-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="81904-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-728">Prod 1</span></span></td>
<td><span data-ttu-id="81904-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-729">Product 1</span></span></td>
<td><span data-ttu-id="81904-730">10001</span><span class="sxs-lookup"><span data-stu-id="81904-730">10001</span></span></td>
<td><span data-ttu-id="81904-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-731">Electricity</span></span></td>
<td><span data-ttu-id="81904-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-732">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-733">776.36</span><span class="sxs-lookup"><span data-stu-id="81904-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-735">Prod 1</span></span></td>
<td><span data-ttu-id="81904-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-736">Product 1</span></span></td>
<td><span data-ttu-id="81904-737">10001</span><span class="sxs-lookup"><span data-stu-id="81904-737">10001</span></span></td>
<td><span data-ttu-id="81904-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-738">Electricity</span></span></td>
<td><span data-ttu-id="81904-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-739">Variable cost</span></span></td>
<td><span data-ttu-id="81904-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="81904-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-742">Prod 2</span></span></td>
<td><span data-ttu-id="81904-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-743">Product 1</span></span></td>
<td><span data-ttu-id="81904-744">10001</span><span class="sxs-lookup"><span data-stu-id="81904-744">10001</span></span></td>
<td><span data-ttu-id="81904-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-745">Electricity</span></span></td>
<td><span data-ttu-id="81904-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-746">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-747">223.64</span><span class="sxs-lookup"><span data-stu-id="81904-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="81904-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-749">Prod 2</span></span></td>
<td><span data-ttu-id="81904-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-750">Product 1</span></span></td>
<td><span data-ttu-id="81904-751">10001</span><span class="sxs-lookup"><span data-stu-id="81904-751">10001</span></span></td>
<td><span data-ttu-id="81904-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-752">Electricity</span></span></td>
<td><span data-ttu-id="81904-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-753">Variable cost</span></span></td>
<td><span data-ttu-id="81904-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="81904-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="81904-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="81904-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="81904-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="81904-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-757">Cost element</span></span></th>
<th><span data-ttu-id="81904-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="81904-758">Cost behavior</span></span></th>
<th><span data-ttu-id="81904-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="81904-759">Amount</span></span></th>
<th><span data-ttu-id="81904-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="81904-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="81904-761">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-761">CC001</span></span></td>
<td><span data-ttu-id="81904-762">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-762">HR</span></span></td>
<td><span data-ttu-id="81904-763">10001</span><span class="sxs-lookup"><span data-stu-id="81904-763">10001</span></span></td>
<td><span data-ttu-id="81904-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-764">Electricity</span></span></td>
<td><span data-ttu-id="81904-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-765">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="81904-766">-500.00</span></span></td>
<td><span data-ttu-id="81904-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-768">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-768">CC002</span></span></td>
<td><span data-ttu-id="81904-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-769">Finance</span></span></td>
<td><span data-ttu-id="81904-770">10001</span><span class="sxs-lookup"><span data-stu-id="81904-770">10001</span></span></td>
<td><span data-ttu-id="81904-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-771">Electricity</span></span></td>
<td><span data-ttu-id="81904-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-772">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-773">175.00</span><span class="sxs-lookup"><span data-stu-id="81904-773">175.00</span></span></td>
<td><span data-ttu-id="81904-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-775">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-775">CC003</span></span></td>
<td><span data-ttu-id="81904-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-776">Assembly</span></span></td>
<td><span data-ttu-id="81904-777">10001</span><span class="sxs-lookup"><span data-stu-id="81904-777">10001</span></span></td>
<td><span data-ttu-id="81904-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-778">Electricity</span></span></td>
<td><span data-ttu-id="81904-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-779">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-780">275.00</span><span class="sxs-lookup"><span data-stu-id="81904-780">275.00</span></span></td>
<td><span data-ttu-id="81904-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-782">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-782">CC004</span></span></td>
<td><span data-ttu-id="81904-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-783">Packaging</span></span></td>
<td><span data-ttu-id="81904-784">10001</span><span class="sxs-lookup"><span data-stu-id="81904-784">10001</span></span></td>
<td><span data-ttu-id="81904-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-785">Electricity</span></span></td>
<td><span data-ttu-id="81904-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-786">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-787">50,00</span><span class="sxs-lookup"><span data-stu-id="81904-787">50,00</span></span></td>
<td><span data-ttu-id="81904-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-789">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-789">CC001</span></span></td>
<td><span data-ttu-id="81904-790">Personal</span><span class="sxs-lookup"><span data-stu-id="81904-790">HR</span></span></td>
<td><span data-ttu-id="81904-791">10001</span><span class="sxs-lookup"><span data-stu-id="81904-791">10001</span></span></td>
<td><span data-ttu-id="81904-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-792">Electricity</span></span></td>
<td><span data-ttu-id="81904-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-793">Variable cost</span></span></td>
<td><span data-ttu-id="81904-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="81904-794">-1,245.71</span></span></td>
<td><span data-ttu-id="81904-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-796">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-796">CC002</span></span></td>
<td><span data-ttu-id="81904-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-797">Finance</span></span></td>
<td><span data-ttu-id="81904-798">10001</span><span class="sxs-lookup"><span data-stu-id="81904-798">10001</span></span></td>
<td><span data-ttu-id="81904-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-799">Electricity</span></span></td>
<td><span data-ttu-id="81904-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-800">Variable cost</span></span></td>
<td><span data-ttu-id="81904-801">436.00</span><span class="sxs-lookup"><span data-stu-id="81904-801">436.00</span></span></td>
<td><span data-ttu-id="81904-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-803">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-803">CC003</span></span></td>
<td><span data-ttu-id="81904-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-804">Assembly</span></span></td>
<td><span data-ttu-id="81904-805">10001</span><span class="sxs-lookup"><span data-stu-id="81904-805">10001</span></span></td>
<td><span data-ttu-id="81904-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-806">Electricity</span></span></td>
<td><span data-ttu-id="81904-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-807">Variable cost</span></span></td>
<td><span data-ttu-id="81904-808">685.14</span><span class="sxs-lookup"><span data-stu-id="81904-808">685.14</span></span></td>
<td><span data-ttu-id="81904-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-810">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-810">CC004</span></span></td>
<td><span data-ttu-id="81904-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-811">Packaging</span></span></td>
<td><span data-ttu-id="81904-812">10001</span><span class="sxs-lookup"><span data-stu-id="81904-812">10001</span></span></td>
<td><span data-ttu-id="81904-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-813">Electricity</span></span></td>
<td><span data-ttu-id="81904-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-814">Variable cost</span></span></td>
<td><span data-ttu-id="81904-815">124.57</span><span class="sxs-lookup"><span data-stu-id="81904-815">124.57</span></span></td>
<td><span data-ttu-id="81904-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-817">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-817">CC002</span></span></td>
<td><span data-ttu-id="81904-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-818">Finance</span></span></td>
<td><span data-ttu-id="81904-819">10001</span><span class="sxs-lookup"><span data-stu-id="81904-819">10001</span></span></td>
<td><span data-ttu-id="81904-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-820">Electricity</span></span></td>
<td><span data-ttu-id="81904-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-821">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="81904-822">-675.00</span></span></td>
<td><span data-ttu-id="81904-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-824">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-824">CC003</span></span></td>
<td><span data-ttu-id="81904-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-825">Assembly</span></span></td>
<td><span data-ttu-id="81904-826">10001</span><span class="sxs-lookup"><span data-stu-id="81904-826">10001</span></span></td>
<td><span data-ttu-id="81904-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-827">Electricity</span></span></td>
<td><span data-ttu-id="81904-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-828">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-829">438.75</span><span class="sxs-lookup"><span data-stu-id="81904-829">438.75</span></span></td>
<td><span data-ttu-id="81904-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-831">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-831">CC004</span></span></td>
<td><span data-ttu-id="81904-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-832">Packaging</span></span></td>
<td><span data-ttu-id="81904-833">10001</span><span class="sxs-lookup"><span data-stu-id="81904-833">10001</span></span></td>
<td><span data-ttu-id="81904-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-834">Electricity</span></span></td>
<td><span data-ttu-id="81904-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-835">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-836">236.25</span><span class="sxs-lookup"><span data-stu-id="81904-836">236.25</span></span></td>
<td><span data-ttu-id="81904-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-838">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-838">CC002</span></span></td>
<td><span data-ttu-id="81904-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="81904-839">Finance</span></span></td>
<td><span data-ttu-id="81904-840">10001</span><span class="sxs-lookup"><span data-stu-id="81904-840">10001</span></span></td>
<td><span data-ttu-id="81904-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-841">Electricity</span></span></td>
<td><span data-ttu-id="81904-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-842">Variable cost</span></span></td>
<td><span data-ttu-id="81904-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="81904-843">-8,150.29</span></span></td>
<td><span data-ttu-id="81904-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-845">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-845">CC003</span></span></td>
<td><span data-ttu-id="81904-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-846">Assembly</span></span></td>
<td><span data-ttu-id="81904-847">10001</span><span class="sxs-lookup"><span data-stu-id="81904-847">10001</span></span></td>
<td><span data-ttu-id="81904-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-848">Electricity</span></span></td>
<td><span data-ttu-id="81904-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-849">Variable cost</span></span></td>
<td><span data-ttu-id="81904-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="81904-850">5,297.69</span></span></td>
<td><span data-ttu-id="81904-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-852">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-852">CC004</span></span></td>
<td><span data-ttu-id="81904-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="81904-853">Packaging</span></span></td>
<td><span data-ttu-id="81904-854">10001</span><span class="sxs-lookup"><span data-stu-id="81904-854">10001</span></span></td>
<td><span data-ttu-id="81904-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-855">Electricity</span></span></td>
<td><span data-ttu-id="81904-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-856">Variable cost</span></span></td>
<td><span data-ttu-id="81904-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="81904-857">2,852.60</span></span></td>
<td><span data-ttu-id="81904-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-859">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-859">CC003</span></span></td>
<td><span data-ttu-id="81904-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-860">Assembly</span></span></td>
<td><span data-ttu-id="81904-861">10001</span><span class="sxs-lookup"><span data-stu-id="81904-861">10001</span></span></td>
<td><span data-ttu-id="81904-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-862">Electricity</span></span></td>
<td><span data-ttu-id="81904-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-863">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="81904-864">-713.75</span></span></td>
<td><span data-ttu-id="81904-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-866">Prod 1</span></span></td>
<td><span data-ttu-id="81904-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-867">Product 1</span></span></td>
<td><span data-ttu-id="81904-868">10001</span><span class="sxs-lookup"><span data-stu-id="81904-868">10001</span></span></td>
<td><span data-ttu-id="81904-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-869">Electricity</span></span></td>
<td><span data-ttu-id="81904-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-870">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-871">535.31</span><span class="sxs-lookup"><span data-stu-id="81904-871">535.31</span></span></td>
<td><span data-ttu-id="81904-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-873">Prod 2</span></span></td>
<td><span data-ttu-id="81904-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-874">Product 2</span></span></td>
<td><span data-ttu-id="81904-875">10001</span><span class="sxs-lookup"><span data-stu-id="81904-875">10001</span></span></td>
<td><span data-ttu-id="81904-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-876">Electricity</span></span></td>
<td><span data-ttu-id="81904-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-877">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-878">178.44</span><span class="sxs-lookup"><span data-stu-id="81904-878">178.44</span></span></td>
<td><span data-ttu-id="81904-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-880">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-880">CC003</span></span></td>
<td><span data-ttu-id="81904-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-881">Assembly</span></span></td>
<td><span data-ttu-id="81904-882">10001</span><span class="sxs-lookup"><span data-stu-id="81904-882">10001</span></span></td>
<td><span data-ttu-id="81904-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-883">Electricity</span></span></td>
<td><span data-ttu-id="81904-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-884">Variable cost</span></span></td>
<td><span data-ttu-id="81904-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="81904-885">-5,982.83</span></span></td>
<td><span data-ttu-id="81904-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-887">Prod 1</span></span></td>
<td><span data-ttu-id="81904-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-888">Product 1</span></span></td>
<td><span data-ttu-id="81904-889">10001</span><span class="sxs-lookup"><span data-stu-id="81904-889">10001</span></span></td>
<td><span data-ttu-id="81904-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-890">Electricity</span></span></td>
<td><span data-ttu-id="81904-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-891">Variable cost</span></span></td>
<td><span data-ttu-id="81904-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="81904-892">4,487.12</span></span></td>
<td><span data-ttu-id="81904-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-894">Prod 2</span></span></td>
<td><span data-ttu-id="81904-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-895">Product 2</span></span></td>
<td><span data-ttu-id="81904-896">10001</span><span class="sxs-lookup"><span data-stu-id="81904-896">10001</span></span></td>
<td><span data-ttu-id="81904-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-897">Electricity</span></span></td>
<td><span data-ttu-id="81904-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-898">Variable cost</span></span></td>
<td><span data-ttu-id="81904-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="81904-899">1,495.71</span></span></td>
<td><span data-ttu-id="81904-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-901">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-901">CC003</span></span></td>
<td><span data-ttu-id="81904-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-902">Assembly</span></span></td>
<td><span data-ttu-id="81904-903">10001</span><span class="sxs-lookup"><span data-stu-id="81904-903">10001</span></span></td>
<td><span data-ttu-id="81904-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-904">Electricity</span></span></td>
<td><span data-ttu-id="81904-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-905">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="81904-906">-286.25</span></span></td>
<td><span data-ttu-id="81904-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-908">Prod 1</span></span></td>
<td><span data-ttu-id="81904-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-909">Product 1</span></span></td>
<td><span data-ttu-id="81904-910">10001</span><span class="sxs-lookup"><span data-stu-id="81904-910">10001</span></span></td>
<td><span data-ttu-id="81904-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-911">Electricity</span></span></td>
<td><span data-ttu-id="81904-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-912">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-913">241.05</span><span class="sxs-lookup"><span data-stu-id="81904-913">241.05</span></span></td>
<td><span data-ttu-id="81904-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-915">Prod 2</span></span></td>
<td><span data-ttu-id="81904-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-916">Product 2</span></span></td>
<td><span data-ttu-id="81904-917">10001</span><span class="sxs-lookup"><span data-stu-id="81904-917">10001</span></span></td>
<td><span data-ttu-id="81904-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-918">Electricity</span></span></td>
<td><span data-ttu-id="81904-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-919">Fixed cost</span></span></td>
<td><span data-ttu-id="81904-920">45.20</span><span class="sxs-lookup"><span data-stu-id="81904-920">45.20</span></span></td>
<td><span data-ttu-id="81904-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-922">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-922">CC003</span></span></td>
<td><span data-ttu-id="81904-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="81904-923">Assembly</span></span></td>
<td><span data-ttu-id="81904-924">10001</span><span class="sxs-lookup"><span data-stu-id="81904-924">10001</span></span></td>
<td><span data-ttu-id="81904-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-925">Electricity</span></span></td>
<td><span data-ttu-id="81904-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-926">Variable cost</span></span></td>
<td><span data-ttu-id="81904-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="81904-927">-2,977.17</span></span></td>
<td><span data-ttu-id="81904-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-929">Prod 1</span></span></td>
<td><span data-ttu-id="81904-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="81904-930">Product 1</span></span></td>
<td><span data-ttu-id="81904-931">10001</span><span class="sxs-lookup"><span data-stu-id="81904-931">10001</span></span></td>
<td><span data-ttu-id="81904-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-932">Electricity</span></span></td>
<td><span data-ttu-id="81904-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-933">Variable cost</span></span></td>
<td><span data-ttu-id="81904-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="81904-934">2,507.09</span></span></td>
<td><span data-ttu-id="81904-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="81904-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-936">Prod 2</span></span></td>
<td><span data-ttu-id="81904-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="81904-937">Product 2</span></span></td>
<td><span data-ttu-id="81904-938">10001</span><span class="sxs-lookup"><span data-stu-id="81904-938">10001</span></span></td>
<td><span data-ttu-id="81904-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-939">Electricity</span></span></td>
<td><span data-ttu-id="81904-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-940">Variable cost</span></span></td>
<td><span data-ttu-id="81904-941">470.08</span><span class="sxs-lookup"><span data-stu-id="81904-941">470.08</span></span></td>
<td><span data-ttu-id="81904-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="81904-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="81904-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="81904-943">Conclusion</span></span>
<span data-ttu-id="81904-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="81904-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="81904-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="81904-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="81904-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="81904-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="81904-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="81904-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="81904-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="81904-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="81904-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="81904-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="81904-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="81904-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="81904-951">CC099</span><span class="sxs-lookup"><span data-stu-id="81904-951">CC099</span></span></th>
<th><span data-ttu-id="81904-952">CC001</span><span class="sxs-lookup"><span data-stu-id="81904-952">CC001</span></span></th>
<th><span data-ttu-id="81904-953">CC002</span><span class="sxs-lookup"><span data-stu-id="81904-953">CC002</span></span></th>
<th><span data-ttu-id="81904-954">CC003</span><span class="sxs-lookup"><span data-stu-id="81904-954">CC003</span></span></th>
<th><span data-ttu-id="81904-955">CC004</span><span class="sxs-lookup"><span data-stu-id="81904-955">CC004</span></span></th>
<th><span data-ttu-id="81904-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="81904-956">Proj 1</span></span></th>
<th><span data-ttu-id="81904-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="81904-957">Proj 2</span></span></th>
<th><span data-ttu-id="81904-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="81904-958">Prod 1</span></span></th>
<th><span data-ttu-id="81904-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="81904-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="81904-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="81904-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="81904-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="81904-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="81904-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="81904-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="81904-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-971">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="81904-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-973">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-974">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-975">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-976">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-977">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="81904-978">776.36</span><span class="sxs-lookup"><span data-stu-id="81904-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-979">223.64</span><span class="sxs-lookup"><span data-stu-id="81904-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="81904-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="81904-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-982">000</span><span class="sxs-lookup"><span data-stu-id="81904-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-983">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-984">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-985">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-986">0,00</span><span class="sxs-lookup"><span data-stu-id="81904-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-987">30,00</span><span class="sxs-lookup"><span data-stu-id="81904-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-988">10,00</span><span class="sxs-lookup"><span data-stu-id="81904-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="81904-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="81904-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="81904-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="81904-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="81904-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="81904-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="81904-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81904-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="81904-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="81904-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="81904-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="81904-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="81904-996">Mer information finns i [Samlade kostnader](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="81904-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



