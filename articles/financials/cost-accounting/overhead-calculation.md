---
title: "Beräkning av indirekta kostnader"
description: "Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: sv-se
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="531b6-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="531b6-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="531b6-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="531b6-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="531b6-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="531b6-105">Term definition</span></span>
---------------

<span data-ttu-id="531b6-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="531b6-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="531b6-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="531b6-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="531b6-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="531b6-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="531b6-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="531b6-109">Rent</span></span>
-   <span data-ttu-id="531b6-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-110">Electricity</span></span>
-   <span data-ttu-id="531b6-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="531b6-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="531b6-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="531b6-112">Overhead calculation overview</span></span>
<span data-ttu-id="531b6-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="531b6-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="531b6-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="531b6-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="531b6-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="531b6-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="531b6-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="531b6-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="531b6-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="531b6-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="531b6-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="531b6-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="531b6-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="531b6-119">Version type</span></span>
-   <span data-ttu-id="531b6-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="531b6-120">Date and time</span></span>
-   <span data-ttu-id="531b6-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="531b6-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="531b6-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="531b6-122">Fiscal year</span></span>
-   <span data-ttu-id="531b6-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="531b6-123">Fiscal period</span></span>

<span data-ttu-id="531b6-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="531b6-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="531b6-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="531b6-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="531b6-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="531b6-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="531b6-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="531b6-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="531b6-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="531b6-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="531b6-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="531b6-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="531b6-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="531b6-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="531b6-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="531b6-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="531b6-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="531b6-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="531b6-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="531b6-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="531b6-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="531b6-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="531b6-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="531b6-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="531b6-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="531b6-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="531b6-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="531b6-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="531b6-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="531b6-140">Main account</span></span></th>
<th><span data-ttu-id="531b6-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="531b6-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="531b6-143">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-143">CC099</span></span></td>
<td><span data-ttu-id="531b6-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-144">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-145">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-145">10001</span></span></td>
<td><span data-ttu-id="531b6-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-146">Electricity</span></span></td>
<td><span data-ttu-id="531b6-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="531b6-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="531b6-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="531b6-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="531b6-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="531b6-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="531b6-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="531b6-151">Define the cost behavior rule</span></span>

<span data-ttu-id="531b6-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="531b6-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="531b6-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="531b6-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="531b6-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="531b6-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="531b6-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="531b6-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="531b6-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="531b6-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="531b6-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="531b6-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="531b6-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="531b6-159">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-160">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-160">Journal</span></span></th>
<th><span data-ttu-id="531b6-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="531b6-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="531b6-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="531b6-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="531b6-163">version</span><span class="sxs-lookup"><span data-stu-id="531b6-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-164">00001</span><span class="sxs-lookup"><span data-stu-id="531b6-164">00001</span></span></td>
<td><span data-ttu-id="531b6-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="531b6-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="531b6-166">Fiscal</span></span></td>
<td><span data-ttu-id="531b6-167">2017</span><span class="sxs-lookup"><span data-stu-id="531b6-167">2017</span></span></td>
<td><span data-ttu-id="531b6-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-168">Period 1</span></span></td>
<td><span data-ttu-id="531b6-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="531b6-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="531b6-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-173">Cost element</span></span></th>
<th><span data-ttu-id="531b6-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-174">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="531b6-177">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-177">CC099</span></span></td>
<td><span data-ttu-id="531b6-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-178">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-179">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-179">10001</span></span></td>
<td><span data-ttu-id="531b6-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-180">Electricity</span></span></td>
<td><span data-ttu-id="531b6-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="531b6-181">Unclassified</span></span></td>
<td><span data-ttu-id="531b6-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="531b6-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="531b6-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-185">Cost element</span></span></th>
<th><span data-ttu-id="531b6-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-186">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-187">Amount</span></span></th>
<th><span data-ttu-id="531b6-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-189">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-189">CC099</span></span></td>
<td><span data-ttu-id="531b6-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-190">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-191">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-191">10001</span></span></td>
<td><span data-ttu-id="531b6-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-192">Electricity</span></span></td>
<td><span data-ttu-id="531b6-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="531b6-193">Unclassified</span></span></td>
<td><span data-ttu-id="531b6-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-194">10,000.00</span></span></td>
<td><span data-ttu-id="531b6-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-196">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-196">CC099</span></span></td>
<td><span data-ttu-id="531b6-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-197">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-198">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-198">10001</span></span></td>
<td><span data-ttu-id="531b6-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-199">Electricity</span></span></td>
<td><span data-ttu-id="531b6-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="531b6-200">Unclassified</span></span></td>
<td><span data-ttu-id="531b6-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-201">-10,000.00</span></span></td>
<td><span data-ttu-id="531b6-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-203">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-203">CC099</span></span></td>
<td><span data-ttu-id="531b6-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-204">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-205">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-205">10001</span></span></td>
<td><span data-ttu-id="531b6-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-206">Electricity</span></span></td>
<td><span data-ttu-id="531b6-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-207">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-208">1,000.00</span></span></td>
<td><span data-ttu-id="531b6-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-210">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-210">CC099</span></span></td>
<td><span data-ttu-id="531b6-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-211">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-212">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-212">10001</span></span></td>
<td><span data-ttu-id="531b6-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-213">Electricity</span></span></td>
<td><span data-ttu-id="531b6-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-214">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="531b6-215">9,000.00</span></span></td>
<td><span data-ttu-id="531b6-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="531b6-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="531b6-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="531b6-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="531b6-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="531b6-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="531b6-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="531b6-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="531b6-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="531b6-221">Define the cost distribution rule</span></span>

<span data-ttu-id="531b6-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="531b6-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="531b6-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="531b6-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="531b6-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="531b6-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="531b6-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="531b6-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="531b6-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="531b6-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="531b6-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="531b6-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-228">Cost object</span></span></th>
<th><span data-ttu-id="531b6-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="531b6-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-230">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-230">CC001</span></span></td>
<td><span data-ttu-id="531b6-231">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-231">HR</span></span></td>
<td><span data-ttu-id="531b6-232">1 000</span><span class="sxs-lookup"><span data-stu-id="531b6-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-233">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-233">CC002</span></span></td>
<td><span data-ttu-id="531b6-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-234">Finance</span></span></td>
<td><span data-ttu-id="531b6-235">6,000</span><span class="sxs-lookup"><span data-stu-id="531b6-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-236">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-236">CC003</span></span></td>
<td><span data-ttu-id="531b6-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-237">Assembly</span></span></td>
<td><span data-ttu-id="531b6-238">0</span><span class="sxs-lookup"><span data-stu-id="531b6-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="531b6-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-240">Cost object</span></span></th>
<th><span data-ttu-id="531b6-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-241">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-242">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-244">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-244">CC001</span></span></td>
<td><span data-ttu-id="531b6-245">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-245">HR</span></span></td>
<td><span data-ttu-id="531b6-246">1 000</span><span class="sxs-lookup"><span data-stu-id="531b6-246">1,000</span></span></td>
<td><span data-ttu-id="531b6-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="531b6-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="531b6-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-249">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-249">CC002</span></span></td>
<td><span data-ttu-id="531b6-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-250">Finance</span></span></td>
<td><span data-ttu-id="531b6-251">6,000</span><span class="sxs-lookup"><span data-stu-id="531b6-251">6,000</span></span></td>
<td><span data-ttu-id="531b6-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="531b6-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="531b6-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-254">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-254">CC003</span></span></td>
<td><span data-ttu-id="531b6-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-255">Assembly</span></span></td>
<td><span data-ttu-id="531b6-256">0</span><span class="sxs-lookup"><span data-stu-id="531b6-256">0</span></span></td>
<td><span data-ttu-id="531b6-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="531b6-258">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="531b6-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="531b6-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="531b6-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-261">Cost object</span></span></th>
<th><span data-ttu-id="531b6-262">Formel</span><span class="sxs-lookup"><span data-stu-id="531b6-262">Formula</span></span></th>
<th><span data-ttu-id="531b6-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-263">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-264">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-266">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-266">CC001</span></span></td>
<td><span data-ttu-id="531b6-267">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-267">HR</span></span></td>
<td><span data-ttu-id="531b6-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="531b6-269">1</span><span class="sxs-lookup"><span data-stu-id="531b6-269">1</span></span></td>
<td><span data-ttu-id="531b6-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="531b6-271">500.00</span><span class="sxs-lookup"><span data-stu-id="531b6-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-272">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-272">CC002</span></span></td>
<td><span data-ttu-id="531b6-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-273">Finance</span></span></td>
<td><span data-ttu-id="531b6-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="531b6-275">1</span><span class="sxs-lookup"><span data-stu-id="531b6-275">1</span></span></td>
<td><span data-ttu-id="531b6-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="531b6-277">500.00</span><span class="sxs-lookup"><span data-stu-id="531b6-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-278">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-278">CC003</span></span></td>
<td><span data-ttu-id="531b6-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-279">Assembly</span></span></td>
<td><span data-ttu-id="531b6-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="531b6-281">0</span><span class="sxs-lookup"><span data-stu-id="531b6-281">0</span></span></td>
<td><span data-ttu-id="531b6-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="531b6-283">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="531b6-284">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-285">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-285">Journal</span></span></th>
<th><span data-ttu-id="531b6-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="531b6-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="531b6-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="531b6-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="531b6-288">version</span><span class="sxs-lookup"><span data-stu-id="531b6-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-289">00002</span><span class="sxs-lookup"><span data-stu-id="531b6-289">00002</span></span></td>
<td><span data-ttu-id="531b6-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="531b6-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="531b6-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="531b6-291">Fiscal</span></span></td>
<td><span data-ttu-id="531b6-292">2017</span><span class="sxs-lookup"><span data-stu-id="531b6-292">2017</span></span></td>
<td><span data-ttu-id="531b6-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-293">Period 1</span></span></td>
<td><span data-ttu-id="531b6-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="531b6-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="531b6-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-298">Cost element</span></span></th>
<th><span data-ttu-id="531b6-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-299">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-302">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-302">CC099</span></span></td>
<td><span data-ttu-id="531b6-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-303">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-304">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-304">10001</span></span></td>
<td><span data-ttu-id="531b6-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-305">Electricity</span></span></td>
<td><span data-ttu-id="531b6-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-306">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-309">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-309">CC099</span></span></td>
<td><span data-ttu-id="531b6-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-310">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-311">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-311">10001</span></span></td>
<td><span data-ttu-id="531b6-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-312">Electricity</span></span></td>
<td><span data-ttu-id="531b6-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-313">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="531b6-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="531b6-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="531b6-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-317">Cost element</span></span></th>
<th><span data-ttu-id="531b6-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-318">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-319">Amount</span></span></th>
<th><span data-ttu-id="531b6-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-321">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-321">CC099</span></span></td>
<td><span data-ttu-id="531b6-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-322">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-323">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-323">10001</span></span></td>
<td><span data-ttu-id="531b6-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-324">Electricity</span></span></td>
<td><span data-ttu-id="531b6-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-325">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-326">-1,000.00</span></span></td>
<td><span data-ttu-id="531b6-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-328">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-328">CC001</span></span></td>
<td><span data-ttu-id="531b6-329">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-329">HR</span></span></td>
<td><span data-ttu-id="531b6-330">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-330">10001</span></span></td>
<td><span data-ttu-id="531b6-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-331">Electricity</span></span></td>
<td><span data-ttu-id="531b6-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-332">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-333">500.00</span><span class="sxs-lookup"><span data-stu-id="531b6-333">500.00</span></span></td>
<td><span data-ttu-id="531b6-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-335">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-335">CC002</span></span></td>
<td><span data-ttu-id="531b6-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-336">Finance</span></span></td>
<td><span data-ttu-id="531b6-337">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-337">10001</span></span></td>
<td><span data-ttu-id="531b6-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-338">Electricity</span></span></td>
<td><span data-ttu-id="531b6-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-339">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-340">500.00</span><span class="sxs-lookup"><span data-stu-id="531b6-340">500.00</span></span></td>
<td><span data-ttu-id="531b6-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-342">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-342">CC099</span></span></td>
<td><span data-ttu-id="531b6-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="531b6-343">Default cost center</span></span></td>
<td><span data-ttu-id="531b6-344">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-344">10001</span></span></td>
<td><span data-ttu-id="531b6-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-345">Electricity</span></span></td>
<td><span data-ttu-id="531b6-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-346">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="531b6-347">-9,000.00</span></span></td>
<td><span data-ttu-id="531b6-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-349">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-349">CC001</span></span></td>
<td><span data-ttu-id="531b6-350">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-350">HR</span></span></td>
<td><span data-ttu-id="531b6-351">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-351">10001</span></span></td>
<td><span data-ttu-id="531b6-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-352">Electricity</span></span></td>
<td><span data-ttu-id="531b6-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-353">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="531b6-354">1,285.71</span></span></td>
<td><span data-ttu-id="531b6-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-356">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-356">CC002</span></span></td>
<td><span data-ttu-id="531b6-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-357">Finance</span></span></td>
<td><span data-ttu-id="531b6-358">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-358">10001</span></span></td>
<td><span data-ttu-id="531b6-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-359">Electricity</span></span></td>
<td><span data-ttu-id="531b6-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-360">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="531b6-361">7,714.29</span></span></td>
<td><span data-ttu-id="531b6-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="531b6-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="531b6-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="531b6-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="531b6-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="531b6-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="531b6-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-367">Define the overhead rate</span></span>

<span data-ttu-id="531b6-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="531b6-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="531b6-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-370">Cost object</span></span></th>
<th><span data-ttu-id="531b6-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="531b6-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-372">Proj 1</span></span></td>
<td><span data-ttu-id="531b6-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-373">Project 1</span></span></td>
<td><span data-ttu-id="531b6-374">3</span><span class="sxs-lookup"><span data-stu-id="531b6-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-375">Proj 2</span></span></td>
<td><span data-ttu-id="531b6-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-376">Project 2</span></span></td>
<td><span data-ttu-id="531b6-377">1</span><span class="sxs-lookup"><span data-stu-id="531b6-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="531b6-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-379">Cost object</span></span></th>
<th><span data-ttu-id="531b6-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-380">Cost element</span></span></th>
<th><span data-ttu-id="531b6-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-381">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="531b6-382">Units</span></span></th>
<th><span data-ttu-id="531b6-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="531b6-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-384">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-384">CC001</span></span></td>
<td><span data-ttu-id="531b6-385">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-385">HR</span></span></td>
<td><span data-ttu-id="531b6-386">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-386">10001</span></span></td>
<td><span data-ttu-id="531b6-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-387">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-388">1</span><span class="sxs-lookup"><span data-stu-id="531b6-388">1</span></span></td>
<td><span data-ttu-id="531b6-389">10</span><span class="sxs-lookup"><span data-stu-id="531b6-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="531b6-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-391">Cost object</span></span></th>
<th><span data-ttu-id="531b6-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-392">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-393">Cost element</span></span></th>
<th><span data-ttu-id="531b6-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-394">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-396">Proj 1</span></span></td>
<td><span data-ttu-id="531b6-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-397">Project 1</span></span></td>
<td><span data-ttu-id="531b6-398">3</span><span class="sxs-lookup"><span data-stu-id="531b6-398">3</span></span></td>
<td><span data-ttu-id="531b6-399">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-399">10001</span></span></td>
<td><span data-ttu-id="531b6-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="531b6-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="531b6-401">30,00</span><span class="sxs-lookup"><span data-stu-id="531b6-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-402">Proj 2</span></span></td>
<td><span data-ttu-id="531b6-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-403">Project 2</span></span></td>
<td><span data-ttu-id="531b6-404">1</span><span class="sxs-lookup"><span data-stu-id="531b6-404">1</span></span></td>
<td><span data-ttu-id="531b6-405">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-405">10001</span></span></td>
<td><span data-ttu-id="531b6-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="531b6-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="531b6-407">10,00</span><span class="sxs-lookup"><span data-stu-id="531b6-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="531b6-408">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-409">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-409">Journal</span></span></th>
<th><span data-ttu-id="531b6-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="531b6-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="531b6-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="531b6-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="531b6-412">version</span><span class="sxs-lookup"><span data-stu-id="531b6-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-413">00003</span><span class="sxs-lookup"><span data-stu-id="531b6-413">00003</span></span></td>
<td><span data-ttu-id="531b6-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="531b6-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="531b6-415">Fiscal</span></span></td>
<td><span data-ttu-id="531b6-416">2017</span><span class="sxs-lookup"><span data-stu-id="531b6-416">2017</span></span></td>
<td><span data-ttu-id="531b6-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-417">Period 1</span></span></td>
<td><span data-ttu-id="531b6-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="531b6-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="531b6-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-421">Cost object</span></span></th>
<th><span data-ttu-id="531b6-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-424">Proj 1</span></span></td>
<td><span data-ttu-id="531b6-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="531b6-426">3,00</span><span class="sxs-lookup"><span data-stu-id="531b6-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-428">Proj 2</span></span></td>
<td><span data-ttu-id="531b6-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="531b6-430">1,00</span><span class="sxs-lookup"><span data-stu-id="531b6-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="531b6-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="531b6-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-433">Cost element</span></span></th>
<th><span data-ttu-id="531b6-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-434">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-435">Amount</span></span></th>
<th><span data-ttu-id="531b6-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="531b6-437">CC0001</span></span></td>
<td><span data-ttu-id="531b6-438">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-438">HR</span></span></td>
<td><span data-ttu-id="531b6-439">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-439">10001</span></span></td>
<td><span data-ttu-id="531b6-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-440">Electricity</span></span></td>
<td><span data-ttu-id="531b6-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-441">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="531b6-442">-30.00</span></span></td>
<td><span data-ttu-id="531b6-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-444">Proj 1</span></span></td>
<td><span data-ttu-id="531b6-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="531b6-446">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-446">10001</span></span></td>
<td><span data-ttu-id="531b6-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-447">Electricity</span></span></td>
<td><span data-ttu-id="531b6-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-448">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-449">30,00</span><span class="sxs-lookup"><span data-stu-id="531b6-449">30.00</span></span></td>
<td><span data-ttu-id="531b6-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-451">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-451">CC001</span></span></td>
<td><span data-ttu-id="531b6-452">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-452">HR</span></span></td>
<td><span data-ttu-id="531b6-453">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-453">10001</span></span></td>
<td><span data-ttu-id="531b6-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-454">Electricity</span></span></td>
<td><span data-ttu-id="531b6-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-455">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="531b6-456">-10.00</span></span></td>
<td><span data-ttu-id="531b6-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-458">Proj 2</span></span></td>
<td><span data-ttu-id="531b6-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="531b6-460">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-460">10001</span></span></td>
<td><span data-ttu-id="531b6-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-461">Electricity</span></span></td>
<td><span data-ttu-id="531b6-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-462">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-463">10,00</span><span class="sxs-lookup"><span data-stu-id="531b6-463">10.00</span></span></td>
<td><span data-ttu-id="531b6-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="531b6-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="531b6-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="531b6-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="531b6-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="531b6-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="531b6-468">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="531b6-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="531b6-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="531b6-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="531b6-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="531b6-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="531b6-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="531b6-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="531b6-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="531b6-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="531b6-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="531b6-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="531b6-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="531b6-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="531b6-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="531b6-475">Define the cost allocation</span></span>

<span data-ttu-id="531b6-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="531b6-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="531b6-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="531b6-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="531b6-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-479">Cost object</span></span></th>
<th><span data-ttu-id="531b6-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="531b6-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-481">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-481">CC002</span></span></td>
<td><span data-ttu-id="531b6-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-482">Finance</span></span></td>
<td><span data-ttu-id="531b6-483">35</span><span class="sxs-lookup"><span data-stu-id="531b6-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-484">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-484">CC003</span></span></td>
<td><span data-ttu-id="531b6-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-485">Assembly</span></span></td>
<td><span data-ttu-id="531b6-486">55</span><span class="sxs-lookup"><span data-stu-id="531b6-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-487">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-487">CC004</span></span></td>
<td><span data-ttu-id="531b6-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-488">Packaging</span></span></td>
<td><span data-ttu-id="531b6-489">10</span><span class="sxs-lookup"><span data-stu-id="531b6-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="531b6-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="531b6-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-492">Cost object</span></span></th>
<th><span data-ttu-id="531b6-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="531b6-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-494">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-494">CC003</span></span></td>
<td><span data-ttu-id="531b6-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-495">Assembly</span></span></td>
<td><span data-ttu-id="531b6-496">65</span><span class="sxs-lookup"><span data-stu-id="531b6-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-497">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-497">CC004</span></span></td>
<td><span data-ttu-id="531b6-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-498">Packaging</span></span></td>
<td><span data-ttu-id="531b6-499">35</span><span class="sxs-lookup"><span data-stu-id="531b6-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="531b6-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="531b6-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-502">Cost object</span></span></th>
<th><span data-ttu-id="531b6-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="531b6-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-504">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-505">Product 1</span></span></td>
<td><span data-ttu-id="531b6-506">60</span><span class="sxs-lookup"><span data-stu-id="531b6-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-507">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-508">Product 2</span></span></td>
<td><span data-ttu-id="531b6-509">20</span><span class="sxs-lookup"><span data-stu-id="531b6-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="531b6-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="531b6-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="531b6-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-512">Cost object</span></span></th>
<th><span data-ttu-id="531b6-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="531b6-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-514">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-515">Product 1</span></span></td>
<td><span data-ttu-id="531b6-516">80</span><span class="sxs-lookup"><span data-stu-id="531b6-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-517">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-518">Product 2</span></span></td>
<td><span data-ttu-id="531b6-519">15</span><span class="sxs-lookup"><span data-stu-id="531b6-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="531b6-520">I Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="531b6-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="531b6-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="531b6-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="531b6-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="531b6-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-523">Cost object</span></span></th>
<th><span data-ttu-id="531b6-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-524">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-525">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-526">Amount</span></span></th>
<th><span data-ttu-id="531b6-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-528">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-528">CC002</span></span></td>
<td><span data-ttu-id="531b6-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-529">Finance</span></span></td>
<td><span data-ttu-id="531b6-530">35</span><span class="sxs-lookup"><span data-stu-id="531b6-530">35</span></span></td>
<td><span data-ttu-id="531b6-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="531b6-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="531b6-532">175.00</span><span class="sxs-lookup"><span data-stu-id="531b6-532">175.00</span></span></td>
<td><span data-ttu-id="531b6-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-534">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-534">CC003</span></span></td>
<td><span data-ttu-id="531b6-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-535">Assembly</span></span></td>
<td><span data-ttu-id="531b6-536">55</span><span class="sxs-lookup"><span data-stu-id="531b6-536">55</span></span></td>
<td><span data-ttu-id="531b6-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="531b6-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="531b6-538">275.00</span><span class="sxs-lookup"><span data-stu-id="531b6-538">275.00</span></span></td>
<td><span data-ttu-id="531b6-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-540">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-540">CC004</span></span></td>
<td><span data-ttu-id="531b6-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-541">Packaging</span></span></td>
<td><span data-ttu-id="531b6-542">10</span><span class="sxs-lookup"><span data-stu-id="531b6-542">10</span></span></td>
<td><span data-ttu-id="531b6-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="531b6-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="531b6-544">50,00</span><span class="sxs-lookup"><span data-stu-id="531b6-544">50.00</span></span></td>
<td><span data-ttu-id="531b6-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-546">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-546">CC002</span></span></td>
<td><span data-ttu-id="531b6-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-547">Finance</span></span></td>
<td><span data-ttu-id="531b6-548">35</span><span class="sxs-lookup"><span data-stu-id="531b6-548">35</span></span></td>
<td><span data-ttu-id="531b6-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="531b6-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="531b6-550">436.00</span><span class="sxs-lookup"><span data-stu-id="531b6-550">436.00</span></span></td>
<td><span data-ttu-id="531b6-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-552">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-552">CC003</span></span></td>
<td><span data-ttu-id="531b6-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-553">Assembly</span></span></td>
<td><span data-ttu-id="531b6-554">55</span><span class="sxs-lookup"><span data-stu-id="531b6-554">55</span></span></td>
<td><span data-ttu-id="531b6-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="531b6-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="531b6-556">685.14</span><span class="sxs-lookup"><span data-stu-id="531b6-556">685.14</span></span></td>
<td><span data-ttu-id="531b6-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-558">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-558">CC004</span></span></td>
<td><span data-ttu-id="531b6-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-559">Packaging</span></span></td>
<td><span data-ttu-id="531b6-560">10</span><span class="sxs-lookup"><span data-stu-id="531b6-560">10</span></span></td>
<td><span data-ttu-id="531b6-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="531b6-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="531b6-562">124.57</span><span class="sxs-lookup"><span data-stu-id="531b6-562">124.57</span></span></td>
<td><span data-ttu-id="531b6-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="531b6-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-565">Cost object</span></span></th>
<th><span data-ttu-id="531b6-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-566">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-567">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-568">Amount</span></span></th>
<th><span data-ttu-id="531b6-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-570">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-570">CC003</span></span></td>
<td><span data-ttu-id="531b6-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-571">Assembly</span></span></td>
<td><span data-ttu-id="531b6-572">65</span><span class="sxs-lookup"><span data-stu-id="531b6-572">65</span></span></td>
<td><span data-ttu-id="531b6-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="531b6-574">438.75</span><span class="sxs-lookup"><span data-stu-id="531b6-574">438.75</span></span></td>
<td><span data-ttu-id="531b6-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-576">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-576">CC004</span></span></td>
<td><span data-ttu-id="531b6-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-577">Packaging</span></span></td>
<td><span data-ttu-id="531b6-578">35</span><span class="sxs-lookup"><span data-stu-id="531b6-578">35</span></span></td>
<td><span data-ttu-id="531b6-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="531b6-580">236.25</span><span class="sxs-lookup"><span data-stu-id="531b6-580">236.25</span></span></td>
<td><span data-ttu-id="531b6-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-582">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-582">CC003</span></span></td>
<td><span data-ttu-id="531b6-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-583">Assembly</span></span></td>
<td><span data-ttu-id="531b6-584">65</span><span class="sxs-lookup"><span data-stu-id="531b6-584">65</span></span></td>
<td><span data-ttu-id="531b6-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="531b6-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="531b6-586">5,297.69</span></span></td>
<td><span data-ttu-id="531b6-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-588">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-588">CC004</span></span></td>
<td><span data-ttu-id="531b6-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-589">Packaging</span></span></td>
<td><span data-ttu-id="531b6-590">35</span><span class="sxs-lookup"><span data-stu-id="531b6-590">35</span></span></td>
<td><span data-ttu-id="531b6-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="531b6-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="531b6-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="531b6-592">2,852.60</span></span></td>
<td><span data-ttu-id="531b6-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="531b6-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-595">Cost object</span></span></th>
<th><span data-ttu-id="531b6-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-596">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-597">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-598">Amount</span></span></th>
<th><span data-ttu-id="531b6-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-600">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-601">Product 1</span></span></td>
<td><span data-ttu-id="531b6-602">60</span><span class="sxs-lookup"><span data-stu-id="531b6-602">60</span></span></td>
<td><span data-ttu-id="531b6-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="531b6-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="531b6-604">535.31</span><span class="sxs-lookup"><span data-stu-id="531b6-604">535.31</span></span></td>
<td><span data-ttu-id="531b6-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-606">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-607">Product 2</span></span></td>
<td><span data-ttu-id="531b6-608">20</span><span class="sxs-lookup"><span data-stu-id="531b6-608">20</span></span></td>
<td><span data-ttu-id="531b6-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="531b6-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="531b6-610">178.44</span><span class="sxs-lookup"><span data-stu-id="531b6-610">178.44</span></span></td>
<td><span data-ttu-id="531b6-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-612">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-613">Product 1</span></span></td>
<td><span data-ttu-id="531b6-614">60</span><span class="sxs-lookup"><span data-stu-id="531b6-614">60</span></span></td>
<td><span data-ttu-id="531b6-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="531b6-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="531b6-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="531b6-616">4,487.12</span></span></td>
<td><span data-ttu-id="531b6-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-618">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-619">Product 2</span></span></td>
<td><span data-ttu-id="531b6-620">20</span><span class="sxs-lookup"><span data-stu-id="531b6-620">20</span></span></td>
<td><span data-ttu-id="531b6-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="531b6-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="531b6-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="531b6-622">1,495.71</span></span></td>
<td><span data-ttu-id="531b6-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="531b6-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="531b6-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-625">Cost object</span></span></th>
<th><span data-ttu-id="531b6-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="531b6-626">Magnitude</span></span></th>
<th><span data-ttu-id="531b6-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="531b6-627">Allocation factor</span></span></th>
<th><span data-ttu-id="531b6-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-628">Amount</span></span></th>
<th><span data-ttu-id="531b6-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-630">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-631">Product 1</span></span></td>
<td><span data-ttu-id="531b6-632">80</span><span class="sxs-lookup"><span data-stu-id="531b6-632">80</span></span></td>
<td><span data-ttu-id="531b6-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="531b6-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="531b6-634">241.05</span><span class="sxs-lookup"><span data-stu-id="531b6-634">241.05</span></span></td>
<td><span data-ttu-id="531b6-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-636">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-637">Product 2</span></span></td>
<td><span data-ttu-id="531b6-638">15</span><span class="sxs-lookup"><span data-stu-id="531b6-638">15</span></span></td>
<td><span data-ttu-id="531b6-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="531b6-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="531b6-640">45.20</span><span class="sxs-lookup"><span data-stu-id="531b6-640">45.20</span></span></td>
<td><span data-ttu-id="531b6-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-642">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-643">Product 1</span></span></td>
<td><span data-ttu-id="531b6-644">80</span><span class="sxs-lookup"><span data-stu-id="531b6-644">80</span></span></td>
<td><span data-ttu-id="531b6-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="531b6-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="531b6-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="531b6-646">2,507.09</span></span></td>
<td><span data-ttu-id="531b6-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-648">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-649">Product 2</span></span></td>
<td><span data-ttu-id="531b6-650">15</span><span class="sxs-lookup"><span data-stu-id="531b6-650">15</span></span></td>
<td><span data-ttu-id="531b6-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="531b6-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="531b6-652">470.08</span><span class="sxs-lookup"><span data-stu-id="531b6-652">470.08</span></span></td>
<td><span data-ttu-id="531b6-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="531b6-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="531b6-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-655">Journal</span><span class="sxs-lookup"><span data-stu-id="531b6-655">Journal</span></span></th>
<th><span data-ttu-id="531b6-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="531b6-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="531b6-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="531b6-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="531b6-658">version</span><span class="sxs-lookup"><span data-stu-id="531b6-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-659">00004</span><span class="sxs-lookup"><span data-stu-id="531b6-659">00004</span></span></td>
<td><span data-ttu-id="531b6-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="531b6-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="531b6-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="531b6-661">Fiscal</span></span></td>
<td><span data-ttu-id="531b6-662">2017</span><span class="sxs-lookup"><span data-stu-id="531b6-662">2017</span></span></td>
<td><span data-ttu-id="531b6-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-663">Period 1</span></span></td>
<td><span data-ttu-id="531b6-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="531b6-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="531b6-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="531b6-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="531b6-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-668">Cost element</span></span></th>
<th><span data-ttu-id="531b6-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-669">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-672">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-672">CC001</span></span></td>
<td><span data-ttu-id="531b6-673">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-673">HR</span></span></td>
<td><span data-ttu-id="531b6-674">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-674">10001</span></span></td>
<td><span data-ttu-id="531b6-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-675">Electricity</span></span></td>
<td><span data-ttu-id="531b6-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-676">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-677">500.00</span><span class="sxs-lookup"><span data-stu-id="531b6-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-679">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-679">CC001</span></span></td>
<td><span data-ttu-id="531b6-680">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-680">HR</span></span></td>
<td><span data-ttu-id="531b6-681">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-681">10001</span></span></td>
<td><span data-ttu-id="531b6-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-682">Electricity</span></span></td>
<td><span data-ttu-id="531b6-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-683">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="531b6-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-686">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-686">CC002</span></span></td>
<td><span data-ttu-id="531b6-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-687">Finance</span></span></td>
<td><span data-ttu-id="531b6-688">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-688">10001</span></span></td>
<td><span data-ttu-id="531b6-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-689">Electricity</span></span></td>
<td><span data-ttu-id="531b6-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-690">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-691">675.00</span><span class="sxs-lookup"><span data-stu-id="531b6-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-693">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-693">CC002</span></span></td>
<td><span data-ttu-id="531b6-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-694">Finance</span></span></td>
<td><span data-ttu-id="531b6-695">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-695">10001</span></span></td>
<td><span data-ttu-id="531b6-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-696">Electricity</span></span></td>
<td><span data-ttu-id="531b6-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-697">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="531b6-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-700">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-700">CC003</span></span></td>
<td><span data-ttu-id="531b6-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-701">Assembly</span></span></td>
<td><span data-ttu-id="531b6-702">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-702">10001</span></span></td>
<td><span data-ttu-id="531b6-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-703">Electricity</span></span></td>
<td><span data-ttu-id="531b6-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-704">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-705">713.75</span><span class="sxs-lookup"><span data-stu-id="531b6-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-707">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-707">CC003</span></span></td>
<td><span data-ttu-id="531b6-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-708">Assembly</span></span></td>
<td><span data-ttu-id="531b6-709">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-709">10001</span></span></td>
<td><span data-ttu-id="531b6-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-710">Electricity</span></span></td>
<td><span data-ttu-id="531b6-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-711">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="531b6-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-714">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-714">CC003</span></span></td>
<td><span data-ttu-id="531b6-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-715">Packaging</span></span></td>
<td><span data-ttu-id="531b6-716">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-716">10001</span></span></td>
<td><span data-ttu-id="531b6-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-717">Electricity</span></span></td>
<td><span data-ttu-id="531b6-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-718">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-719">286.25</span><span class="sxs-lookup"><span data-stu-id="531b6-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-721">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-721">CC003</span></span></td>
<td><span data-ttu-id="531b6-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-722">Packaging</span></span></td>
<td><span data-ttu-id="531b6-723">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-723">10001</span></span></td>
<td><span data-ttu-id="531b6-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-724">Electricity</span></span></td>
<td><span data-ttu-id="531b6-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-725">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="531b6-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-728">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-729">Product 1</span></span></td>
<td><span data-ttu-id="531b6-730">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-730">10001</span></span></td>
<td><span data-ttu-id="531b6-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-731">Electricity</span></span></td>
<td><span data-ttu-id="531b6-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-732">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-733">776.36</span><span class="sxs-lookup"><span data-stu-id="531b6-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-735">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-736">Product 1</span></span></td>
<td><span data-ttu-id="531b6-737">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-737">10001</span></span></td>
<td><span data-ttu-id="531b6-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-738">Electricity</span></span></td>
<td><span data-ttu-id="531b6-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-739">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="531b6-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-742">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-743">Product 1</span></span></td>
<td><span data-ttu-id="531b6-744">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-744">10001</span></span></td>
<td><span data-ttu-id="531b6-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-745">Electricity</span></span></td>
<td><span data-ttu-id="531b6-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-746">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-747">223.64</span><span class="sxs-lookup"><span data-stu-id="531b6-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="531b6-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-749">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-750">Product 1</span></span></td>
<td><span data-ttu-id="531b6-751">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-751">10001</span></span></td>
<td><span data-ttu-id="531b6-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-752">Electricity</span></span></td>
<td><span data-ttu-id="531b6-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-753">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="531b6-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="531b6-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="531b6-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="531b6-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="531b6-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-757">Cost element</span></span></th>
<th><span data-ttu-id="531b6-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="531b6-758">Cost behavior</span></span></th>
<th><span data-ttu-id="531b6-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="531b6-759">Amount</span></span></th>
<th><span data-ttu-id="531b6-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="531b6-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="531b6-761">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-761">CC001</span></span></td>
<td><span data-ttu-id="531b6-762">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-762">HR</span></span></td>
<td><span data-ttu-id="531b6-763">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-763">10001</span></span></td>
<td><span data-ttu-id="531b6-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-764">Electricity</span></span></td>
<td><span data-ttu-id="531b6-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-765">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="531b6-766">-500.00</span></span></td>
<td><span data-ttu-id="531b6-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-768">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-768">CC002</span></span></td>
<td><span data-ttu-id="531b6-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-769">Finance</span></span></td>
<td><span data-ttu-id="531b6-770">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-770">10001</span></span></td>
<td><span data-ttu-id="531b6-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-771">Electricity</span></span></td>
<td><span data-ttu-id="531b6-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-772">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-773">175.00</span><span class="sxs-lookup"><span data-stu-id="531b6-773">175.00</span></span></td>
<td><span data-ttu-id="531b6-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-775">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-775">CC003</span></span></td>
<td><span data-ttu-id="531b6-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-776">Assembly</span></span></td>
<td><span data-ttu-id="531b6-777">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-777">10001</span></span></td>
<td><span data-ttu-id="531b6-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-778">Electricity</span></span></td>
<td><span data-ttu-id="531b6-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-779">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-780">275.00</span><span class="sxs-lookup"><span data-stu-id="531b6-780">275.00</span></span></td>
<td><span data-ttu-id="531b6-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-782">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-782">CC004</span></span></td>
<td><span data-ttu-id="531b6-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-783">Packaging</span></span></td>
<td><span data-ttu-id="531b6-784">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-784">10001</span></span></td>
<td><span data-ttu-id="531b6-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-785">Electricity</span></span></td>
<td><span data-ttu-id="531b6-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-786">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-787">50,00</span><span class="sxs-lookup"><span data-stu-id="531b6-787">50,00</span></span></td>
<td><span data-ttu-id="531b6-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-789">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-789">CC001</span></span></td>
<td><span data-ttu-id="531b6-790">Personal</span><span class="sxs-lookup"><span data-stu-id="531b6-790">HR</span></span></td>
<td><span data-ttu-id="531b6-791">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-791">10001</span></span></td>
<td><span data-ttu-id="531b6-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-792">Electricity</span></span></td>
<td><span data-ttu-id="531b6-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-793">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="531b6-794">-1,245.71</span></span></td>
<td><span data-ttu-id="531b6-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-796">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-796">CC002</span></span></td>
<td><span data-ttu-id="531b6-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-797">Finance</span></span></td>
<td><span data-ttu-id="531b6-798">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-798">10001</span></span></td>
<td><span data-ttu-id="531b6-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-799">Electricity</span></span></td>
<td><span data-ttu-id="531b6-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-800">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-801">436.00</span><span class="sxs-lookup"><span data-stu-id="531b6-801">436.00</span></span></td>
<td><span data-ttu-id="531b6-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-803">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-803">CC003</span></span></td>
<td><span data-ttu-id="531b6-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-804">Assembly</span></span></td>
<td><span data-ttu-id="531b6-805">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-805">10001</span></span></td>
<td><span data-ttu-id="531b6-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-806">Electricity</span></span></td>
<td><span data-ttu-id="531b6-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-807">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-808">685.14</span><span class="sxs-lookup"><span data-stu-id="531b6-808">685.14</span></span></td>
<td><span data-ttu-id="531b6-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-810">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-810">CC004</span></span></td>
<td><span data-ttu-id="531b6-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-811">Packaging</span></span></td>
<td><span data-ttu-id="531b6-812">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-812">10001</span></span></td>
<td><span data-ttu-id="531b6-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-813">Electricity</span></span></td>
<td><span data-ttu-id="531b6-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-814">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-815">124.57</span><span class="sxs-lookup"><span data-stu-id="531b6-815">124.57</span></span></td>
<td><span data-ttu-id="531b6-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-817">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-817">CC002</span></span></td>
<td><span data-ttu-id="531b6-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-818">Finance</span></span></td>
<td><span data-ttu-id="531b6-819">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-819">10001</span></span></td>
<td><span data-ttu-id="531b6-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-820">Electricity</span></span></td>
<td><span data-ttu-id="531b6-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-821">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="531b6-822">-675.00</span></span></td>
<td><span data-ttu-id="531b6-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-824">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-824">CC003</span></span></td>
<td><span data-ttu-id="531b6-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-825">Assembly</span></span></td>
<td><span data-ttu-id="531b6-826">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-826">10001</span></span></td>
<td><span data-ttu-id="531b6-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-827">Electricity</span></span></td>
<td><span data-ttu-id="531b6-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-828">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-829">438.75</span><span class="sxs-lookup"><span data-stu-id="531b6-829">438.75</span></span></td>
<td><span data-ttu-id="531b6-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-831">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-831">CC004</span></span></td>
<td><span data-ttu-id="531b6-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-832">Packaging</span></span></td>
<td><span data-ttu-id="531b6-833">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-833">10001</span></span></td>
<td><span data-ttu-id="531b6-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-834">Electricity</span></span></td>
<td><span data-ttu-id="531b6-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-835">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-836">236.25</span><span class="sxs-lookup"><span data-stu-id="531b6-836">236.25</span></span></td>
<td><span data-ttu-id="531b6-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-838">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-838">CC002</span></span></td>
<td><span data-ttu-id="531b6-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="531b6-839">Finance</span></span></td>
<td><span data-ttu-id="531b6-840">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-840">10001</span></span></td>
<td><span data-ttu-id="531b6-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-841">Electricity</span></span></td>
<td><span data-ttu-id="531b6-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-842">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="531b6-843">-8,150.29</span></span></td>
<td><span data-ttu-id="531b6-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-845">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-845">CC003</span></span></td>
<td><span data-ttu-id="531b6-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-846">Assembly</span></span></td>
<td><span data-ttu-id="531b6-847">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-847">10001</span></span></td>
<td><span data-ttu-id="531b6-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-848">Electricity</span></span></td>
<td><span data-ttu-id="531b6-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-849">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="531b6-850">5,297.69</span></span></td>
<td><span data-ttu-id="531b6-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-852">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-852">CC004</span></span></td>
<td><span data-ttu-id="531b6-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="531b6-853">Packaging</span></span></td>
<td><span data-ttu-id="531b6-854">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-854">10001</span></span></td>
<td><span data-ttu-id="531b6-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-855">Electricity</span></span></td>
<td><span data-ttu-id="531b6-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-856">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="531b6-857">2,852.60</span></span></td>
<td><span data-ttu-id="531b6-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-859">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-859">CC003</span></span></td>
<td><span data-ttu-id="531b6-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-860">Assembly</span></span></td>
<td><span data-ttu-id="531b6-861">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-861">10001</span></span></td>
<td><span data-ttu-id="531b6-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-862">Electricity</span></span></td>
<td><span data-ttu-id="531b6-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-863">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="531b6-864">-713.75</span></span></td>
<td><span data-ttu-id="531b6-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-866">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-867">Product 1</span></span></td>
<td><span data-ttu-id="531b6-868">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-868">10001</span></span></td>
<td><span data-ttu-id="531b6-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-869">Electricity</span></span></td>
<td><span data-ttu-id="531b6-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-870">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-871">535.31</span><span class="sxs-lookup"><span data-stu-id="531b6-871">535.31</span></span></td>
<td><span data-ttu-id="531b6-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-873">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-874">Product 2</span></span></td>
<td><span data-ttu-id="531b6-875">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-875">10001</span></span></td>
<td><span data-ttu-id="531b6-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-876">Electricity</span></span></td>
<td><span data-ttu-id="531b6-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-877">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-878">178.44</span><span class="sxs-lookup"><span data-stu-id="531b6-878">178.44</span></span></td>
<td><span data-ttu-id="531b6-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-880">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-880">CC003</span></span></td>
<td><span data-ttu-id="531b6-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-881">Assembly</span></span></td>
<td><span data-ttu-id="531b6-882">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-882">10001</span></span></td>
<td><span data-ttu-id="531b6-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-883">Electricity</span></span></td>
<td><span data-ttu-id="531b6-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-884">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="531b6-885">-5,982.83</span></span></td>
<td><span data-ttu-id="531b6-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-887">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-888">Product 1</span></span></td>
<td><span data-ttu-id="531b6-889">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-889">10001</span></span></td>
<td><span data-ttu-id="531b6-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-890">Electricity</span></span></td>
<td><span data-ttu-id="531b6-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-891">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="531b6-892">4,487.12</span></span></td>
<td><span data-ttu-id="531b6-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-894">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-895">Product 2</span></span></td>
<td><span data-ttu-id="531b6-896">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-896">10001</span></span></td>
<td><span data-ttu-id="531b6-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-897">Electricity</span></span></td>
<td><span data-ttu-id="531b6-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-898">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="531b6-899">1,495.71</span></span></td>
<td><span data-ttu-id="531b6-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-901">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-901">CC003</span></span></td>
<td><span data-ttu-id="531b6-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-902">Assembly</span></span></td>
<td><span data-ttu-id="531b6-903">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-903">10001</span></span></td>
<td><span data-ttu-id="531b6-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-904">Electricity</span></span></td>
<td><span data-ttu-id="531b6-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-905">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="531b6-906">-286.25</span></span></td>
<td><span data-ttu-id="531b6-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-908">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-909">Product 1</span></span></td>
<td><span data-ttu-id="531b6-910">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-910">10001</span></span></td>
<td><span data-ttu-id="531b6-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-911">Electricity</span></span></td>
<td><span data-ttu-id="531b6-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-912">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-913">241.05</span><span class="sxs-lookup"><span data-stu-id="531b6-913">241.05</span></span></td>
<td><span data-ttu-id="531b6-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-915">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-916">Product 2</span></span></td>
<td><span data-ttu-id="531b6-917">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-917">10001</span></span></td>
<td><span data-ttu-id="531b6-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-918">Electricity</span></span></td>
<td><span data-ttu-id="531b6-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-919">Fixed cost</span></span></td>
<td><span data-ttu-id="531b6-920">45.20</span><span class="sxs-lookup"><span data-stu-id="531b6-920">45.20</span></span></td>
<td><span data-ttu-id="531b6-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-922">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-922">CC003</span></span></td>
<td><span data-ttu-id="531b6-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="531b6-923">Assembly</span></span></td>
<td><span data-ttu-id="531b6-924">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-924">10001</span></span></td>
<td><span data-ttu-id="531b6-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-925">Electricity</span></span></td>
<td><span data-ttu-id="531b6-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-926">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="531b6-927">-2,977.17</span></span></td>
<td><span data-ttu-id="531b6-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-929">Prod 1</span></span></td>
<td><span data-ttu-id="531b6-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="531b6-930">Product 1</span></span></td>
<td><span data-ttu-id="531b6-931">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-931">10001</span></span></td>
<td><span data-ttu-id="531b6-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-932">Electricity</span></span></td>
<td><span data-ttu-id="531b6-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-933">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="531b6-934">2,507.09</span></span></td>
<td><span data-ttu-id="531b6-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="531b6-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-936">Prod 2</span></span></td>
<td><span data-ttu-id="531b6-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="531b6-937">Product 2</span></span></td>
<td><span data-ttu-id="531b6-938">10001</span><span class="sxs-lookup"><span data-stu-id="531b6-938">10001</span></span></td>
<td><span data-ttu-id="531b6-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-939">Electricity</span></span></td>
<td><span data-ttu-id="531b6-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-940">Variable cost</span></span></td>
<td><span data-ttu-id="531b6-941">470.08</span><span class="sxs-lookup"><span data-stu-id="531b6-941">470.08</span></span></td>
<td><span data-ttu-id="531b6-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="531b6-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="531b6-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="531b6-943">Conclusion</span></span>
<span data-ttu-id="531b6-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="531b6-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="531b6-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="531b6-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="531b6-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="531b6-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="531b6-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="531b6-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="531b6-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="531b6-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="531b6-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="531b6-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="531b6-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="531b6-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="531b6-951">CC099</span><span class="sxs-lookup"><span data-stu-id="531b6-951">CC099</span></span></th>
<th><span data-ttu-id="531b6-952">CC001</span><span class="sxs-lookup"><span data-stu-id="531b6-952">CC001</span></span></th>
<th><span data-ttu-id="531b6-953">CC002</span><span class="sxs-lookup"><span data-stu-id="531b6-953">CC002</span></span></th>
<th><span data-ttu-id="531b6-954">CC003</span><span class="sxs-lookup"><span data-stu-id="531b6-954">CC003</span></span></th>
<th><span data-ttu-id="531b6-955">CC004</span><span class="sxs-lookup"><span data-stu-id="531b6-955">CC004</span></span></th>
<th><span data-ttu-id="531b6-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="531b6-956">Proj 1</span></span></th>
<th><span data-ttu-id="531b6-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="531b6-957">Proj 2</span></span></th>
<th><span data-ttu-id="531b6-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="531b6-958">Prod 1</span></span></th>
<th><span data-ttu-id="531b6-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="531b6-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="531b6-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="531b6-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="531b6-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="531b6-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="531b6-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-971">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="531b6-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-973">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-974">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-975">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-976">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-977">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="531b6-978">776.36</span><span class="sxs-lookup"><span data-stu-id="531b6-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-979">223.64</span><span class="sxs-lookup"><span data-stu-id="531b6-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="531b6-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="531b6-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-982">000</span><span class="sxs-lookup"><span data-stu-id="531b6-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-983">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-984">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-985">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-986">0,00</span><span class="sxs-lookup"><span data-stu-id="531b6-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-987">30,00</span><span class="sxs-lookup"><span data-stu-id="531b6-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-988">10,00</span><span class="sxs-lookup"><span data-stu-id="531b6-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="531b6-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="531b6-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="531b6-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="531b6-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="531b6-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="531b6-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="531b6-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="531b6-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="531b6-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="531b6-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="531b6-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="531b6-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="531b6-996">Mer information finns i [Samlade kostnader](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="531b6-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




