---
title: "Beräkning av indirekta kostnader"
description: "Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 549e9b4b073a4e93dd3a1dd52dd6f43e7420a31b
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="ecee7-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="ecee7-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ecee7-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="ecee7-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ecee7-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="ecee7-105">Term definition</span></span>
---------------

<span data-ttu-id="ecee7-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="ecee7-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ecee7-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="ecee7-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ecee7-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="ecee7-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ecee7-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="ecee7-109">Rent</span></span>
-   <span data-ttu-id="ecee7-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-110">Electricity</span></span>
-   <span data-ttu-id="ecee7-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="ecee7-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ecee7-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="ecee7-112">Overhead calculation overview</span></span>
<span data-ttu-id="ecee7-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ecee7-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="ecee7-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ecee7-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="ecee7-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ecee7-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="ecee7-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ecee7-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="ecee7-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ecee7-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="ecee7-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ecee7-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="ecee7-119">Version type</span></span>
-   <span data-ttu-id="ecee7-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="ecee7-120">Date and time</span></span>
-   <span data-ttu-id="ecee7-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="ecee7-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ecee7-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="ecee7-122">Fiscal year</span></span>
-   <span data-ttu-id="ecee7-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="ecee7-123">Fiscal period</span></span>

<span data-ttu-id="ecee7-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="ecee7-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ecee7-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="ecee7-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ecee7-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="ecee7-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ecee7-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="ecee7-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ecee7-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="ecee7-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ecee7-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="ecee7-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ecee7-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ecee7-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ecee7-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ecee7-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="ecee7-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ecee7-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="ecee7-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ecee7-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ecee7-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="ecee7-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ecee7-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ecee7-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="ecee7-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="ecee7-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="ecee7-140">Main account</span></span></th>
<th><span data-ttu-id="ecee7-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="ecee7-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ecee7-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-143">CC099</span></span></td>
<td><span data-ttu-id="ecee7-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-144">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-145">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-145">10001</span></span></td>
<td><span data-ttu-id="ecee7-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-146">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ecee7-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ecee7-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ecee7-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="ecee7-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ecee7-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="ecee7-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ecee7-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="ecee7-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ecee7-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="ecee7-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ecee7-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ecee7-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ecee7-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="ecee7-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ecee7-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ecee7-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="ecee7-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ecee7-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="ecee7-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ecee7-159">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-160">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-160">Journal</span></span></th>
<th><span data-ttu-id="ecee7-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="ecee7-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ecee7-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="ecee7-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ecee7-163">version</span><span class="sxs-lookup"><span data-stu-id="ecee7-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-164">00001</span><span class="sxs-lookup"><span data-stu-id="ecee7-164">00001</span></span></td>
<td><span data-ttu-id="ecee7-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ecee7-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="ecee7-166">Fiscal</span></span></td>
<td><span data-ttu-id="ecee7-167">2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-167">2017</span></span></td>
<td><span data-ttu-id="ecee7-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-168">Period 1</span></span></td>
<td><span data-ttu-id="ecee7-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ecee7-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="ecee7-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-173">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ecee7-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-177">CC099</span></span></td>
<td><span data-ttu-id="ecee7-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-178">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-179">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-179">10001</span></span></td>
<td><span data-ttu-id="ecee7-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-180">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="ecee7-181">Unclassified</span></span></td>
<td><span data-ttu-id="ecee7-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ecee7-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="ecee7-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-185">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-187">Amount</span></span></th>
<th><span data-ttu-id="ecee7-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-189">CC099</span></span></td>
<td><span data-ttu-id="ecee7-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-190">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-191">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-191">10001</span></span></td>
<td><span data-ttu-id="ecee7-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-192">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="ecee7-193">Unclassified</span></span></td>
<td><span data-ttu-id="ecee7-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-194">10,000.00</span></span></td>
<td><span data-ttu-id="ecee7-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-196">CC099</span></span></td>
<td><span data-ttu-id="ecee7-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-197">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-198">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-198">10001</span></span></td>
<td><span data-ttu-id="ecee7-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-199">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="ecee7-200">Unclassified</span></span></td>
<td><span data-ttu-id="ecee7-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ecee7-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-203">CC099</span></span></td>
<td><span data-ttu-id="ecee7-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-204">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-205">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-205">10001</span></span></td>
<td><span data-ttu-id="ecee7-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-206">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-208">1,000.00</span></span></td>
<td><span data-ttu-id="ecee7-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-210">CC099</span></span></td>
<td><span data-ttu-id="ecee7-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-211">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-212">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-212">10001</span></span></td>
<td><span data-ttu-id="ecee7-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-213">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-214">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-215">9,000.00</span></span></td>
<td><span data-ttu-id="ecee7-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-217">Detaljerad information om kostnadsbeteende finns i Kostnadsbeteendepolicy.</span><span class="sxs-lookup"><span data-stu-id="ecee7-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="ecee7-218">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="ecee7-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ecee7-219">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="ecee7-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ecee7-220">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ecee7-221">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="ecee7-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ecee7-222">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="ecee7-222">Define the cost distribution rule</span></span>

<span data-ttu-id="ecee7-223">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="ecee7-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ecee7-224">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="ecee7-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ecee7-225">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ecee7-226">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ecee7-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ecee7-227">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="ecee7-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ecee7-228">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-229">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-229">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="ecee7-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-231">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-231">CC001</span></span></td>
<td><span data-ttu-id="ecee7-232">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-232">HR</span></span></td>
<td><span data-ttu-id="ecee7-233">1 000</span><span class="sxs-lookup"><span data-stu-id="ecee7-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-234">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-234">CC002</span></span></td>
<td><span data-ttu-id="ecee7-235">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-235">Finance</span></span></td>
<td><span data-ttu-id="ecee7-236">6,000</span><span class="sxs-lookup"><span data-stu-id="ecee7-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-237">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-237">CC003</span></span></td>
<td><span data-ttu-id="ecee7-238">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-238">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-239">0</span><span class="sxs-lookup"><span data-stu-id="ecee7-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-240">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="ecee7-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-241">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-241">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-242">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-242">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-243">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-243">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-244">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-245">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-245">CC001</span></span></td>
<td><span data-ttu-id="ecee7-246">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-246">HR</span></span></td>
<td><span data-ttu-id="ecee7-247">1 000</span><span class="sxs-lookup"><span data-stu-id="ecee7-247">1,000</span></span></td>
<td><span data-ttu-id="ecee7-248">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ecee7-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ecee7-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-250">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-250">CC002</span></span></td>
<td><span data-ttu-id="ecee7-251">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-251">Finance</span></span></td>
<td><span data-ttu-id="ecee7-252">6,000</span><span class="sxs-lookup"><span data-stu-id="ecee7-252">6,000</span></span></td>
<td><span data-ttu-id="ecee7-253">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ecee7-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ecee7-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-255">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-255">CC003</span></span></td>
<td><span data-ttu-id="ecee7-256">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-256">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-257">0</span><span class="sxs-lookup"><span data-stu-id="ecee7-257">0</span></span></td>
<td><span data-ttu-id="ecee7-258">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ecee7-259">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-260">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="ecee7-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ecee7-261">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="ecee7-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-262">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-262">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-263">Formel</span><span class="sxs-lookup"><span data-stu-id="ecee7-263">Formula</span></span></th>
<th><span data-ttu-id="ecee7-264">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-264">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-265">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-265">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-266">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-267">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-267">CC001</span></span></td>
<td><span data-ttu-id="ecee7-268">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-268">HR</span></span></td>
<td><span data-ttu-id="ecee7-269">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ecee7-270">1</span><span class="sxs-lookup"><span data-stu-id="ecee7-270">1</span></span></td>
<td><span data-ttu-id="ecee7-271">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ecee7-272">500.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-273">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-273">CC002</span></span></td>
<td><span data-ttu-id="ecee7-274">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-274">Finance</span></span></td>
<td><span data-ttu-id="ecee7-275">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ecee7-276">1</span><span class="sxs-lookup"><span data-stu-id="ecee7-276">1</span></span></td>
<td><span data-ttu-id="ecee7-277">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ecee7-278">500.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-279">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-279">CC003</span></span></td>
<td><span data-ttu-id="ecee7-280">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-280">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ecee7-282">0</span><span class="sxs-lookup"><span data-stu-id="ecee7-282">0</span></span></td>
<td><span data-ttu-id="ecee7-283">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ecee7-284">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ecee7-285">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-286">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-286">Journal</span></span></th>
<th><span data-ttu-id="ecee7-287">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="ecee7-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ecee7-288">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="ecee7-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ecee7-289">version</span><span class="sxs-lookup"><span data-stu-id="ecee7-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-290">00002</span><span class="sxs-lookup"><span data-stu-id="ecee7-290">00002</span></span></td>
<td><span data-ttu-id="ecee7-291">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="ecee7-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ecee7-292">Skatt</span><span class="sxs-lookup"><span data-stu-id="ecee7-292">Fiscal</span></span></td>
<td><span data-ttu-id="ecee7-293">2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-293">2017</span></span></td>
<td><span data-ttu-id="ecee7-294">Period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-294">Period 1</span></span></td>
<td><span data-ttu-id="ecee7-295">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ecee7-296">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="ecee7-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-297">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-298">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-299">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-299">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-300">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-300">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-301">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-302">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-303">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-303">CC099</span></span></td>
<td><span data-ttu-id="ecee7-304">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-304">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-305">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-305">10001</span></span></td>
<td><span data-ttu-id="ecee7-306">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-306">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-307">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-307">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-308">1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-309">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-310">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-310">CC099</span></span></td>
<td><span data-ttu-id="ecee7-311">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-311">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-312">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-312">10001</span></span></td>
<td><span data-ttu-id="ecee7-313">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-313">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-314">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-314">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ecee7-316">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="ecee7-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-317">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-318">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-318">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-319">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-319">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-320">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-320">Amount</span></span></th>
<th><span data-ttu-id="ecee7-321">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-322">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-322">CC099</span></span></td>
<td><span data-ttu-id="ecee7-323">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-323">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-324">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-324">10001</span></span></td>
<td><span data-ttu-id="ecee7-325">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-325">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-326">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-326">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-327">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-327">-1,000.00</span></span></td>
<td><span data-ttu-id="ecee7-328">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-329">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-329">CC001</span></span></td>
<td><span data-ttu-id="ecee7-330">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-330">HR</span></span></td>
<td><span data-ttu-id="ecee7-331">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-331">10001</span></span></td>
<td><span data-ttu-id="ecee7-332">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-332">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-333">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-333">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-334">500.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-334">500.00</span></span></td>
<td><span data-ttu-id="ecee7-335">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-336">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-336">CC002</span></span></td>
<td><span data-ttu-id="ecee7-337">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-337">Finance</span></span></td>
<td><span data-ttu-id="ecee7-338">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-338">10001</span></span></td>
<td><span data-ttu-id="ecee7-339">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-339">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-340">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-340">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-341">500.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-341">500.00</span></span></td>
<td><span data-ttu-id="ecee7-342">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-343">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-343">CC099</span></span></td>
<td><span data-ttu-id="ecee7-344">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="ecee7-344">Default cost center</span></span></td>
<td><span data-ttu-id="ecee7-345">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-345">10001</span></span></td>
<td><span data-ttu-id="ecee7-346">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-346">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-347">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-347">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-348">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-348">-9,000.00</span></span></td>
<td><span data-ttu-id="ecee7-349">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-350">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-350">CC001</span></span></td>
<td><span data-ttu-id="ecee7-351">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-351">HR</span></span></td>
<td><span data-ttu-id="ecee7-352">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-352">10001</span></span></td>
<td><span data-ttu-id="ecee7-353">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-353">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-354">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-354">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ecee7-355">1,285.71</span></span></td>
<td><span data-ttu-id="ecee7-356">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-357">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-357">CC002</span></span></td>
<td><span data-ttu-id="ecee7-358">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-358">Finance</span></span></td>
<td><span data-ttu-id="ecee7-359">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-359">10001</span></span></td>
<td><span data-ttu-id="ecee7-360">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-360">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-361">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-361">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ecee7-362">7,714.29</span></span></td>
<td><span data-ttu-id="ecee7-363">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-364">För detaljerad information om kostnadsfördelning och allokeringsunderlag, se Kostnadsfördelningspolicy och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="ecee7-365">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="ecee7-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ecee7-366">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ecee7-367">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ecee7-368">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="ecee7-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ecee7-369">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-369">Define the overhead rate</span></span>

<span data-ttu-id="ecee7-370">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ecee7-371">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="ecee7-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-372">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-372">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-373">Timmar</span><span class="sxs-lookup"><span data-stu-id="ecee7-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-374">Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-375">Project 1</span></span></td>
<td><span data-ttu-id="ecee7-376">3</span><span class="sxs-lookup"><span data-stu-id="ecee7-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-377">Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-378">Project 2</span></span></td>
<td><span data-ttu-id="ecee7-379">1</span><span class="sxs-lookup"><span data-stu-id="ecee7-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-380">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="ecee7-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-381">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-381">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-382">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-382">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-383">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-383">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-384">Enheter</span><span class="sxs-lookup"><span data-stu-id="ecee7-384">Units</span></span></th>
<th><span data-ttu-id="ecee7-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="ecee7-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-386">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-386">CC001</span></span></td>
<td><span data-ttu-id="ecee7-387">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-387">HR</span></span></td>
<td><span data-ttu-id="ecee7-388">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-388">10001</span></span></td>
<td><span data-ttu-id="ecee7-389">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-389">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-390">1</span><span class="sxs-lookup"><span data-stu-id="ecee7-390">1</span></span></td>
<td><span data-ttu-id="ecee7-391">10</span><span class="sxs-lookup"><span data-stu-id="ecee7-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-392">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-393">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-393">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-394">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-394">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-395">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-395">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-396">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-396">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-397">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-398">Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-399">Project 1</span></span></td>
<td><span data-ttu-id="ecee7-400">3</span><span class="sxs-lookup"><span data-stu-id="ecee7-400">3</span></span></td>
<td><span data-ttu-id="ecee7-401">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-401">10001</span></span></td>
<td><span data-ttu-id="ecee7-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ecee7-403">30,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-404">Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-405">Project 2</span></span></td>
<td><span data-ttu-id="ecee7-406">1</span><span class="sxs-lookup"><span data-stu-id="ecee7-406">1</span></span></td>
<td><span data-ttu-id="ecee7-407">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-407">10001</span></span></td>
<td><span data-ttu-id="ecee7-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ecee7-409">10,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ecee7-410">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-411">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-411">Journal</span></span></th>
<th><span data-ttu-id="ecee7-412">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="ecee7-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ecee7-413">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="ecee7-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ecee7-414">version</span><span class="sxs-lookup"><span data-stu-id="ecee7-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-415">00003</span><span class="sxs-lookup"><span data-stu-id="ecee7-415">00003</span></span></td>
<td><span data-ttu-id="ecee7-416">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ecee7-417">Skatt</span><span class="sxs-lookup"><span data-stu-id="ecee7-417">Fiscal</span></span></td>
<td><span data-ttu-id="ecee7-418">2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-418">2017</span></span></td>
<td><span data-ttu-id="ecee7-419">Period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-419">Period 1</span></span></td>
<td><span data-ttu-id="ecee7-420">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ecee7-421">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="ecee7-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-422">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-423">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-423">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-424">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-425">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-426">Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-427">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-428">3,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-429">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-430">Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-431">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-432">1,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ecee7-433">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="ecee7-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-434">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-435">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-435">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-436">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-436">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-437">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-437">Amount</span></span></th>
<th><span data-ttu-id="ecee7-438">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="ecee7-439">CC0001</span></span></td>
<td><span data-ttu-id="ecee7-440">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-440">HR</span></span></td>
<td><span data-ttu-id="ecee7-441">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-441">10001</span></span></td>
<td><span data-ttu-id="ecee7-442">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-442">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-443">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-443">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-444">-30.00</span></span></td>
<td><span data-ttu-id="ecee7-445">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-446">Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-447">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ecee7-448">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-448">10001</span></span></td>
<td><span data-ttu-id="ecee7-449">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-449">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-450">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-450">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-451">30,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-451">30.00</span></span></td>
<td><span data-ttu-id="ecee7-452">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-453">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-453">CC001</span></span></td>
<td><span data-ttu-id="ecee7-454">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-454">HR</span></span></td>
<td><span data-ttu-id="ecee7-455">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-455">10001</span></span></td>
<td><span data-ttu-id="ecee7-456">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-456">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-457">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-457">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-458">-10.00</span></span></td>
<td><span data-ttu-id="ecee7-459">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-460">Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-461">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ecee7-462">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-462">10001</span></span></td>
<td><span data-ttu-id="ecee7-463">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-463">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-464">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-464">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-465">10,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-465">10.00</span></span></td>
<td><span data-ttu-id="ecee7-466">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-467">Detaljerad information om policy för indirekt kostnad finns i Policy för indirekt kostnad och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="ecee7-468">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="ecee7-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ecee7-469">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="ecee7-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ecee7-470">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ecee7-471">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="ecee7-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="ecee7-472">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ecee7-473">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="ecee7-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ecee7-474">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="ecee7-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ecee7-475">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="ecee7-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ecee7-476">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="ecee7-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ecee7-477">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ecee7-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ecee7-478">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="ecee7-478">Define the cost allocation</span></span>

<span data-ttu-id="ecee7-479">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="ecee7-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ecee7-480">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ecee7-481">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="ecee7-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-482">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-482">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-483">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="ecee7-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-484">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-484">CC002</span></span></td>
<td><span data-ttu-id="ecee7-485">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-485">Finance</span></span></td>
<td><span data-ttu-id="ecee7-486">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-487">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-487">CC003</span></span></td>
<td><span data-ttu-id="ecee7-488">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-488">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-489">55</span><span class="sxs-lookup"><span data-stu-id="ecee7-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-490">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-490">CC004</span></span></td>
<td><span data-ttu-id="ecee7-491">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-491">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-492">10</span><span class="sxs-lookup"><span data-stu-id="ecee7-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-493">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ecee7-494">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="ecee7-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-495">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-495">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-496">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="ecee7-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-497">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-497">CC003</span></span></td>
<td><span data-ttu-id="ecee7-498">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-498">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-499">65</span><span class="sxs-lookup"><span data-stu-id="ecee7-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-500">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-500">CC004</span></span></td>
<td><span data-ttu-id="ecee7-501">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-501">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-502">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-503">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ecee7-504">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="ecee7-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-505">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-505">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-506">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="ecee7-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-507">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-508">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-509">60</span><span class="sxs-lookup"><span data-stu-id="ecee7-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-510">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-511">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-512">20</span><span class="sxs-lookup"><span data-stu-id="ecee7-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-513">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="ecee7-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ecee7-514">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="ecee7-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-515">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-515">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-516">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="ecee7-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-517">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-518">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-519">80</span><span class="sxs-lookup"><span data-stu-id="ecee7-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-520">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-521">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-522">15</span><span class="sxs-lookup"><span data-stu-id="ecee7-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-523">**Obs:** i Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="ecee7-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ecee7-524">Mer detaljerad information om provider av statistiska mått finns i Providermallar för statistiska mätningar.</span><span class="sxs-lookup"><span data-stu-id="ecee7-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="ecee7-525">(Observera att det här avsnittet är inte klart, men kommer snart.) I följande tabell visas resultatet när HR-tjänsten används som ett allokeringsunderlag för totalkostnaden (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="ecee7-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-526">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-526">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-527">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-527">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-528">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-528">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-529">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-529">Amount</span></span></th>
<th><span data-ttu-id="ecee7-530">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-531">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-531">CC002</span></span></td>
<td><span data-ttu-id="ecee7-532">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-532">Finance</span></span></td>
<td><span data-ttu-id="ecee7-533">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-533">35</span></span></td>
<td><span data-ttu-id="ecee7-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ecee7-535">175.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-535">175.00</span></span></td>
<td><span data-ttu-id="ecee7-536">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-537">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-537">CC003</span></span></td>
<td><span data-ttu-id="ecee7-538">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-538">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-539">55</span><span class="sxs-lookup"><span data-stu-id="ecee7-539">55</span></span></td>
<td><span data-ttu-id="ecee7-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ecee7-541">275.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-541">275.00</span></span></td>
<td><span data-ttu-id="ecee7-542">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-543">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-543">CC004</span></span></td>
<td><span data-ttu-id="ecee7-544">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-544">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-545">10</span><span class="sxs-lookup"><span data-stu-id="ecee7-545">10</span></span></td>
<td><span data-ttu-id="ecee7-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ecee7-547">50,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-547">50.00</span></span></td>
<td><span data-ttu-id="ecee7-548">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-549">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-549">CC002</span></span></td>
<td><span data-ttu-id="ecee7-550">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-550">Finance</span></span></td>
<td><span data-ttu-id="ecee7-551">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-551">35</span></span></td>
<td><span data-ttu-id="ecee7-552">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ecee7-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ecee7-553">436.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-553">436.00</span></span></td>
<td><span data-ttu-id="ecee7-554">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-555">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-555">CC003</span></span></td>
<td><span data-ttu-id="ecee7-556">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-556">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-557">55</span><span class="sxs-lookup"><span data-stu-id="ecee7-557">55</span></span></td>
<td><span data-ttu-id="ecee7-558">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ecee7-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ecee7-559">685.14</span><span class="sxs-lookup"><span data-stu-id="ecee7-559">685.14</span></span></td>
<td><span data-ttu-id="ecee7-560">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-561">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-561">CC004</span></span></td>
<td><span data-ttu-id="ecee7-562">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-562">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-563">10</span><span class="sxs-lookup"><span data-stu-id="ecee7-563">10</span></span></td>
<td><span data-ttu-id="ecee7-564">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="ecee7-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ecee7-565">124.57</span><span class="sxs-lookup"><span data-stu-id="ecee7-565">124.57</span></span></td>
<td><span data-ttu-id="ecee7-566">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-567">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="ecee7-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-568">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-568">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-569">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-569">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-570">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-570">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-571">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-571">Amount</span></span></th>
<th><span data-ttu-id="ecee7-572">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-573">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-573">CC003</span></span></td>
<td><span data-ttu-id="ecee7-574">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-574">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-575">65</span><span class="sxs-lookup"><span data-stu-id="ecee7-575">65</span></span></td>
<td><span data-ttu-id="ecee7-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ecee7-577">438.75</span><span class="sxs-lookup"><span data-stu-id="ecee7-577">438.75</span></span></td>
<td><span data-ttu-id="ecee7-578">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-579">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-579">CC004</span></span></td>
<td><span data-ttu-id="ecee7-580">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-580">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-581">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-581">35</span></span></td>
<td><span data-ttu-id="ecee7-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ecee7-583">236.25</span><span class="sxs-lookup"><span data-stu-id="ecee7-583">236.25</span></span></td>
<td><span data-ttu-id="ecee7-584">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-585">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-585">CC003</span></span></td>
<td><span data-ttu-id="ecee7-586">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-586">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-587">65</span><span class="sxs-lookup"><span data-stu-id="ecee7-587">65</span></span></td>
<td><span data-ttu-id="ecee7-588">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ecee7-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ecee7-589">5,297.69</span></span></td>
<td><span data-ttu-id="ecee7-590">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-591">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-591">CC004</span></span></td>
<td><span data-ttu-id="ecee7-592">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-592">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-593">35</span><span class="sxs-lookup"><span data-stu-id="ecee7-593">35</span></span></td>
<td><span data-ttu-id="ecee7-594">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ecee7-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ecee7-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ecee7-595">2,852.60</span></span></td>
<td><span data-ttu-id="ecee7-596">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-597">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="ecee7-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-598">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-598">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-599">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-599">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-600">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-600">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-601">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-601">Amount</span></span></th>
<th><span data-ttu-id="ecee7-602">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-603">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-604">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-605">60</span><span class="sxs-lookup"><span data-stu-id="ecee7-605">60</span></span></td>
<td><span data-ttu-id="ecee7-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ecee7-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ecee7-607">535.31</span><span class="sxs-lookup"><span data-stu-id="ecee7-607">535.31</span></span></td>
<td><span data-ttu-id="ecee7-608">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-609">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-610">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-611">20</span><span class="sxs-lookup"><span data-stu-id="ecee7-611">20</span></span></td>
<td><span data-ttu-id="ecee7-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ecee7-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ecee7-613">178.44</span><span class="sxs-lookup"><span data-stu-id="ecee7-613">178.44</span></span></td>
<td><span data-ttu-id="ecee7-614">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-615">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-616">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-617">60</span><span class="sxs-lookup"><span data-stu-id="ecee7-617">60</span></span></td>
<td><span data-ttu-id="ecee7-618">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ecee7-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ecee7-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ecee7-619">4,487.12</span></span></td>
<td><span data-ttu-id="ecee7-620">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-621">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-622">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-623">20</span><span class="sxs-lookup"><span data-stu-id="ecee7-623">20</span></span></td>
<td><span data-ttu-id="ecee7-624">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ecee7-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ecee7-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ecee7-625">1,495.71</span></span></td>
<td><span data-ttu-id="ecee7-626">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ecee7-627">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="ecee7-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-628">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-628">Cost object</span></span></th>
<th><span data-ttu-id="ecee7-629">Storlek</span><span class="sxs-lookup"><span data-stu-id="ecee7-629">Magnitude</span></span></th>
<th><span data-ttu-id="ecee7-630">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="ecee7-630">Allocation factor</span></span></th>
<th><span data-ttu-id="ecee7-631">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-631">Amount</span></span></th>
<th><span data-ttu-id="ecee7-632">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-633">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-634">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-635">80</span><span class="sxs-lookup"><span data-stu-id="ecee7-635">80</span></span></td>
<td><span data-ttu-id="ecee7-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ecee7-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ecee7-637">241.05</span><span class="sxs-lookup"><span data-stu-id="ecee7-637">241.05</span></span></td>
<td><span data-ttu-id="ecee7-638">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-639">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-640">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-641">15</span><span class="sxs-lookup"><span data-stu-id="ecee7-641">15</span></span></td>
<td><span data-ttu-id="ecee7-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ecee7-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ecee7-643">45.20</span><span class="sxs-lookup"><span data-stu-id="ecee7-643">45.20</span></span></td>
<td><span data-ttu-id="ecee7-644">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-645">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-646">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-647">80</span><span class="sxs-lookup"><span data-stu-id="ecee7-647">80</span></span></td>
<td><span data-ttu-id="ecee7-648">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ecee7-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ecee7-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ecee7-649">2,507.09</span></span></td>
<td><span data-ttu-id="ecee7-650">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-651">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-652">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-653">15</span><span class="sxs-lookup"><span data-stu-id="ecee7-653">15</span></span></td>
<td><span data-ttu-id="ecee7-654">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ecee7-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ecee7-655">470.08</span><span class="sxs-lookup"><span data-stu-id="ecee7-655">470.08</span></span></td>
<td><span data-ttu-id="ecee7-656">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ecee7-657">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="ecee7-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-658">Journal</span><span class="sxs-lookup"><span data-stu-id="ecee7-658">Journal</span></span></th>
<th><span data-ttu-id="ecee7-659">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="ecee7-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ecee7-660">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="ecee7-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ecee7-661">version</span><span class="sxs-lookup"><span data-stu-id="ecee7-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-662">00004</span><span class="sxs-lookup"><span data-stu-id="ecee7-662">00004</span></span></td>
<td><span data-ttu-id="ecee7-663">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="ecee7-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ecee7-664">Skatt</span><span class="sxs-lookup"><span data-stu-id="ecee7-664">Fiscal</span></span></td>
<td><span data-ttu-id="ecee7-665">2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-665">2017</span></span></td>
<td><span data-ttu-id="ecee7-666">Period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-666">Period 1</span></span></td>
<td><span data-ttu-id="ecee7-667">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ecee7-668">Journalrader</span><span class="sxs-lookup"><span data-stu-id="ecee7-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ecee7-669">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-670">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-671">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-671">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-672">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-672">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-673">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-674">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-675">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-675">CC001</span></span></td>
<td><span data-ttu-id="ecee7-676">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-676">HR</span></span></td>
<td><span data-ttu-id="ecee7-677">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-677">10001</span></span></td>
<td><span data-ttu-id="ecee7-678">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-678">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-679">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-679">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-680">500.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-681">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-682">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-682">CC001</span></span></td>
<td><span data-ttu-id="ecee7-683">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-683">HR</span></span></td>
<td><span data-ttu-id="ecee7-684">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-684">10001</span></span></td>
<td><span data-ttu-id="ecee7-685">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-685">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-686">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-686">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ecee7-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-688">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-689">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-689">CC002</span></span></td>
<td><span data-ttu-id="ecee7-690">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-690">Finance</span></span></td>
<td><span data-ttu-id="ecee7-691">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-691">10001</span></span></td>
<td><span data-ttu-id="ecee7-692">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-692">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-693">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-693">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-694">675.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-695">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-696">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-696">CC002</span></span></td>
<td><span data-ttu-id="ecee7-697">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-697">Finance</span></span></td>
<td><span data-ttu-id="ecee7-698">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-698">10001</span></span></td>
<td><span data-ttu-id="ecee7-699">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-699">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-700">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-700">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ecee7-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-702">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-703">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-703">CC003</span></span></td>
<td><span data-ttu-id="ecee7-704">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-704">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-705">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-705">10001</span></span></td>
<td><span data-ttu-id="ecee7-706">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-706">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-707">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-707">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-708">713.75</span><span class="sxs-lookup"><span data-stu-id="ecee7-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-709">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-710">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-710">CC003</span></span></td>
<td><span data-ttu-id="ecee7-711">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-711">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-712">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-712">10001</span></span></td>
<td><span data-ttu-id="ecee7-713">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-713">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-714">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-714">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ecee7-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-716">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-717">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-717">CC003</span></span></td>
<td><span data-ttu-id="ecee7-718">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-718">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-719">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-719">10001</span></span></td>
<td><span data-ttu-id="ecee7-720">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-720">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-721">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-721">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-722">286.25</span><span class="sxs-lookup"><span data-stu-id="ecee7-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-723">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-724">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-724">CC003</span></span></td>
<td><span data-ttu-id="ecee7-725">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-725">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-726">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-726">10001</span></span></td>
<td><span data-ttu-id="ecee7-727">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-727">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-728">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-728">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ecee7-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-730">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-731">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-732">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-733">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-733">10001</span></span></td>
<td><span data-ttu-id="ecee7-734">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-734">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-735">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-735">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-736">776.36</span><span class="sxs-lookup"><span data-stu-id="ecee7-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-737">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-738">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-739">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-740">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-740">10001</span></span></td>
<td><span data-ttu-id="ecee7-741">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-741">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-742">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-742">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ecee7-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-744">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-745">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-746">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-747">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-747">10001</span></span></td>
<td><span data-ttu-id="ecee7-748">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-748">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-749">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-749">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-750">223.64</span><span class="sxs-lookup"><span data-stu-id="ecee7-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-751">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="ecee7-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-752">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-753">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-754">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-754">10001</span></span></td>
<td><span data-ttu-id="ecee7-755">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-755">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-756">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-756">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ecee7-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ecee7-758">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="ecee7-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ecee7-759">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ecee7-760">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-760">Cost element</span></span></th>
<th><span data-ttu-id="ecee7-761">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="ecee7-761">Cost behavior</span></span></th>
<th><span data-ttu-id="ecee7-762">Belopp</span><span class="sxs-lookup"><span data-stu-id="ecee7-762">Amount</span></span></th>
<th><span data-ttu-id="ecee7-763">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="ecee7-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ecee7-764">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-764">CC001</span></span></td>
<td><span data-ttu-id="ecee7-765">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-765">HR</span></span></td>
<td><span data-ttu-id="ecee7-766">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-766">10001</span></span></td>
<td><span data-ttu-id="ecee7-767">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-767">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-768">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-768">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-769">-500.00</span></span></td>
<td><span data-ttu-id="ecee7-770">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-771">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-771">CC002</span></span></td>
<td><span data-ttu-id="ecee7-772">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-772">Finance</span></span></td>
<td><span data-ttu-id="ecee7-773">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-773">10001</span></span></td>
<td><span data-ttu-id="ecee7-774">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-774">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-775">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-775">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-776">175.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-776">175.00</span></span></td>
<td><span data-ttu-id="ecee7-777">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-778">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-778">CC003</span></span></td>
<td><span data-ttu-id="ecee7-779">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-779">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-780">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-780">10001</span></span></td>
<td><span data-ttu-id="ecee7-781">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-781">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-782">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-782">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-783">275.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-783">275.00</span></span></td>
<td><span data-ttu-id="ecee7-784">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-785">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-785">CC004</span></span></td>
<td><span data-ttu-id="ecee7-786">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-786">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-787">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-787">10001</span></span></td>
<td><span data-ttu-id="ecee7-788">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-788">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-789">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-789">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-790">50,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-790">50,00</span></span></td>
<td><span data-ttu-id="ecee7-791">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-792">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-792">CC001</span></span></td>
<td><span data-ttu-id="ecee7-793">Personal</span><span class="sxs-lookup"><span data-stu-id="ecee7-793">HR</span></span></td>
<td><span data-ttu-id="ecee7-794">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-794">10001</span></span></td>
<td><span data-ttu-id="ecee7-795">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-795">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-796">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-796">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-797">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="ecee7-797">-1,245.71</span></span></td>
<td><span data-ttu-id="ecee7-798">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-799">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-799">CC002</span></span></td>
<td><span data-ttu-id="ecee7-800">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-800">Finance</span></span></td>
<td><span data-ttu-id="ecee7-801">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-801">10001</span></span></td>
<td><span data-ttu-id="ecee7-802">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-802">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-803">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-803">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-804">436.00</span><span class="sxs-lookup"><span data-stu-id="ecee7-804">436.00</span></span></td>
<td><span data-ttu-id="ecee7-805">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-806">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-806">CC003</span></span></td>
<td><span data-ttu-id="ecee7-807">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-807">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-808">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-808">10001</span></span></td>
<td><span data-ttu-id="ecee7-809">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-809">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-810">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-810">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-811">685.14</span><span class="sxs-lookup"><span data-stu-id="ecee7-811">685.14</span></span></td>
<td><span data-ttu-id="ecee7-812">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-813">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-813">CC004</span></span></td>
<td><span data-ttu-id="ecee7-814">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-814">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-815">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-815">10001</span></span></td>
<td><span data-ttu-id="ecee7-816">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-816">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-817">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-817">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-818">124.57</span><span class="sxs-lookup"><span data-stu-id="ecee7-818">124.57</span></span></td>
<td><span data-ttu-id="ecee7-819">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-820">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-820">CC002</span></span></td>
<td><span data-ttu-id="ecee7-821">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-821">Finance</span></span></td>
<td><span data-ttu-id="ecee7-822">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-822">10001</span></span></td>
<td><span data-ttu-id="ecee7-823">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-823">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-824">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-824">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-825">-675.00</span></span></td>
<td><span data-ttu-id="ecee7-826">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-827">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-827">CC003</span></span></td>
<td><span data-ttu-id="ecee7-828">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-828">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-829">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-829">10001</span></span></td>
<td><span data-ttu-id="ecee7-830">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-830">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-831">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-831">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-832">438.75</span><span class="sxs-lookup"><span data-stu-id="ecee7-832">438.75</span></span></td>
<td><span data-ttu-id="ecee7-833">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-834">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-834">CC004</span></span></td>
<td><span data-ttu-id="ecee7-835">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-835">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-836">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-836">10001</span></span></td>
<td><span data-ttu-id="ecee7-837">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-837">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-838">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-838">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-839">236.25</span><span class="sxs-lookup"><span data-stu-id="ecee7-839">236.25</span></span></td>
<td><span data-ttu-id="ecee7-840">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-841">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-841">CC002</span></span></td>
<td><span data-ttu-id="ecee7-842">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="ecee7-842">Finance</span></span></td>
<td><span data-ttu-id="ecee7-843">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-843">10001</span></span></td>
<td><span data-ttu-id="ecee7-844">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-844">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-845">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-845">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-846">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="ecee7-846">-8,150.29</span></span></td>
<td><span data-ttu-id="ecee7-847">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-848">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-848">CC003</span></span></td>
<td><span data-ttu-id="ecee7-849">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-849">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-850">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-850">10001</span></span></td>
<td><span data-ttu-id="ecee7-851">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-851">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-852">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-852">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ecee7-853">5,297.69</span></span></td>
<td><span data-ttu-id="ecee7-854">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-855">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-855">CC004</span></span></td>
<td><span data-ttu-id="ecee7-856">Paketering</span><span class="sxs-lookup"><span data-stu-id="ecee7-856">Packaging</span></span></td>
<td><span data-ttu-id="ecee7-857">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-857">10001</span></span></td>
<td><span data-ttu-id="ecee7-858">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-858">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-859">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-859">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ecee7-860">2,852.60</span></span></td>
<td><span data-ttu-id="ecee7-861">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-862">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-862">CC003</span></span></td>
<td><span data-ttu-id="ecee7-863">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-863">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-864">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-864">10001</span></span></td>
<td><span data-ttu-id="ecee7-865">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-865">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-866">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-866">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="ecee7-867">-713.75</span></span></td>
<td><span data-ttu-id="ecee7-868">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-869">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-870">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-871">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-871">10001</span></span></td>
<td><span data-ttu-id="ecee7-872">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-872">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-873">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-873">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-874">535.31</span><span class="sxs-lookup"><span data-stu-id="ecee7-874">535.31</span></span></td>
<td><span data-ttu-id="ecee7-875">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-876">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-877">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-878">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-878">10001</span></span></td>
<td><span data-ttu-id="ecee7-879">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-879">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-880">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-880">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-881">178.44</span><span class="sxs-lookup"><span data-stu-id="ecee7-881">178.44</span></span></td>
<td><span data-ttu-id="ecee7-882">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-883">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-883">CC003</span></span></td>
<td><span data-ttu-id="ecee7-884">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-884">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-885">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-885">10001</span></span></td>
<td><span data-ttu-id="ecee7-886">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-886">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-887">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-887">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-888">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="ecee7-888">-5,982.83</span></span></td>
<td><span data-ttu-id="ecee7-889">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-890">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-891">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-892">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-892">10001</span></span></td>
<td><span data-ttu-id="ecee7-893">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-893">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-894">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-894">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ecee7-895">4,487.12</span></span></td>
<td><span data-ttu-id="ecee7-896">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-897">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-898">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-899">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-899">10001</span></span></td>
<td><span data-ttu-id="ecee7-900">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-900">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-901">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-901">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ecee7-902">1,495.71</span></span></td>
<td><span data-ttu-id="ecee7-903">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-904">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-904">CC003</span></span></td>
<td><span data-ttu-id="ecee7-905">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-905">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-906">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-906">10001</span></span></td>
<td><span data-ttu-id="ecee7-907">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-907">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-908">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-908">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="ecee7-909">-286.25</span></span></td>
<td><span data-ttu-id="ecee7-910">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-911">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-912">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-913">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-913">10001</span></span></td>
<td><span data-ttu-id="ecee7-914">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-914">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-915">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-915">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-916">241.05</span><span class="sxs-lookup"><span data-stu-id="ecee7-916">241.05</span></span></td>
<td><span data-ttu-id="ecee7-917">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-918">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-919">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-920">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-920">10001</span></span></td>
<td><span data-ttu-id="ecee7-921">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-921">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-922">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-922">Fixed cost</span></span></td>
<td><span data-ttu-id="ecee7-923">45.20</span><span class="sxs-lookup"><span data-stu-id="ecee7-923">45.20</span></span></td>
<td><span data-ttu-id="ecee7-924">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-925">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-925">CC003</span></span></td>
<td><span data-ttu-id="ecee7-926">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="ecee7-926">Assembly</span></span></td>
<td><span data-ttu-id="ecee7-927">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-927">10001</span></span></td>
<td><span data-ttu-id="ecee7-928">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-928">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-929">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-929">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-930">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="ecee7-930">-2,977.17</span></span></td>
<td><span data-ttu-id="ecee7-931">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-932">Prod 1</span></span></td>
<td><span data-ttu-id="ecee7-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-933">Product 1</span></span></td>
<td><span data-ttu-id="ecee7-934">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-934">10001</span></span></td>
<td><span data-ttu-id="ecee7-935">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-935">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-936">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-936">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ecee7-937">2,507.09</span></span></td>
<td><span data-ttu-id="ecee7-938">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ecee7-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-939">Prod 2</span></span></td>
<td><span data-ttu-id="ecee7-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-940">Product 2</span></span></td>
<td><span data-ttu-id="ecee7-941">10001</span><span class="sxs-lookup"><span data-stu-id="ecee7-941">10001</span></span></td>
<td><span data-ttu-id="ecee7-942">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-942">Electricity</span></span></td>
<td><span data-ttu-id="ecee7-943">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-943">Variable cost</span></span></td>
<td><span data-ttu-id="ecee7-944">470.08</span><span class="sxs-lookup"><span data-stu-id="ecee7-944">470.08</span></span></td>
<td><span data-ttu-id="ecee7-945">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="ecee7-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ecee7-946">Slutsats</span><span class="sxs-lookup"><span data-stu-id="ecee7-946">Conclusion</span></span>
<span data-ttu-id="ecee7-947">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="ecee7-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ecee7-948">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="ecee7-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ecee7-949">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="ecee7-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ecee7-950">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="ecee7-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ecee7-951">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="ecee7-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ecee7-952">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="ecee7-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ecee7-953">Totalt</span><span class="sxs-lookup"><span data-stu-id="ecee7-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ecee7-954">CC099</span><span class="sxs-lookup"><span data-stu-id="ecee7-954">CC099</span></span></th>
<th><span data-ttu-id="ecee7-955">CC001</span><span class="sxs-lookup"><span data-stu-id="ecee7-955">CC001</span></span></th>
<th><span data-ttu-id="ecee7-956">CC002</span><span class="sxs-lookup"><span data-stu-id="ecee7-956">CC002</span></span></th>
<th><span data-ttu-id="ecee7-957">CC003</span><span class="sxs-lookup"><span data-stu-id="ecee7-957">CC003</span></span></th>
<th><span data-ttu-id="ecee7-958">CC004</span><span class="sxs-lookup"><span data-stu-id="ecee7-958">CC004</span></span></th>
<th><span data-ttu-id="ecee7-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-959">Proj 1</span></span></th>
<th><span data-ttu-id="ecee7-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-960">Proj 2</span></span></th>
<th><span data-ttu-id="ecee7-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ecee7-961">Prod 1</span></span></th>
<th><span data-ttu-id="ecee7-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ecee7-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ecee7-963">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="ecee7-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ecee7-973">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="ecee7-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ecee7-975">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-978">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-979">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-980">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-981">776.36</span><span class="sxs-lookup"><span data-stu-id="ecee7-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-982">223.64</span><span class="sxs-lookup"><span data-stu-id="ecee7-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ecee7-984">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="ecee7-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-985">000</span><span class="sxs-lookup"><span data-stu-id="ecee7-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-987">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-988">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-989">0,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-990">30,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-991">10,00</span><span class="sxs-lookup"><span data-stu-id="ecee7-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ecee7-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ecee7-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ecee7-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ecee7-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ecee7-995">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="ecee7-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ecee7-996">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ecee7-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ecee7-997">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="ecee7-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ecee7-998">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="ecee7-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ecee7-999">Mer information finns i Policy för kostnadssummering.</span><span class="sxs-lookup"><span data-stu-id="ecee7-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="ecee7-1000">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="ecee7-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




