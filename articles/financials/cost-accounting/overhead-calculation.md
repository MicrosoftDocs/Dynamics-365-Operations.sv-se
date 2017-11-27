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

# <a name="overhead-calculation"></a><span data-ttu-id="84c50-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="84c50-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="84c50-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="84c50-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="84c50-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="84c50-105">Term definition</span></span>
---------------

<span data-ttu-id="84c50-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="84c50-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="84c50-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="84c50-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="84c50-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="84c50-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="84c50-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="84c50-109">Rent</span></span>
-   <span data-ttu-id="84c50-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-110">Electricity</span></span>
-   <span data-ttu-id="84c50-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="84c50-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="84c50-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="84c50-112">Overhead calculation overview</span></span>
<span data-ttu-id="84c50-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="84c50-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="84c50-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="84c50-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="84c50-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="84c50-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="84c50-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="84c50-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="84c50-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="84c50-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="84c50-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="84c50-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="84c50-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="84c50-119">Version type</span></span>
-   <span data-ttu-id="84c50-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="84c50-120">Date and time</span></span>
-   <span data-ttu-id="84c50-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="84c50-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="84c50-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="84c50-122">Fiscal year</span></span>
-   <span data-ttu-id="84c50-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="84c50-123">Fiscal period</span></span>

<span data-ttu-id="84c50-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="84c50-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="84c50-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="84c50-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="84c50-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="84c50-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="84c50-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="84c50-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="84c50-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="84c50-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="84c50-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="84c50-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="84c50-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="84c50-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="84c50-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="84c50-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="84c50-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="84c50-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="84c50-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="84c50-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="84c50-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="84c50-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="84c50-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="84c50-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="84c50-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="84c50-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="84c50-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="84c50-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="84c50-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="84c50-140">Main account</span></span></th>
<th><span data-ttu-id="84c50-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="84c50-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="84c50-143">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-143">CC099</span></span></td>
<td><span data-ttu-id="84c50-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-144">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-145">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-145">10001</span></span></td>
<td><span data-ttu-id="84c50-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-146">Electricity</span></span></td>
<td><span data-ttu-id="84c50-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="84c50-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="84c50-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="84c50-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="84c50-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="84c50-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="84c50-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="84c50-151">Define the cost behavior rule</span></span>

<span data-ttu-id="84c50-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="84c50-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="84c50-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="84c50-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="84c50-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="84c50-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="84c50-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="84c50-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="84c50-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="84c50-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="84c50-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="84c50-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="84c50-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="84c50-159">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-160">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-160">Journal</span></span></th>
<th><span data-ttu-id="84c50-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="84c50-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="84c50-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="84c50-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="84c50-163">version</span><span class="sxs-lookup"><span data-stu-id="84c50-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-164">00001</span><span class="sxs-lookup"><span data-stu-id="84c50-164">00001</span></span></td>
<td><span data-ttu-id="84c50-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="84c50-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="84c50-166">Fiscal</span></span></td>
<td><span data-ttu-id="84c50-167">2017</span><span class="sxs-lookup"><span data-stu-id="84c50-167">2017</span></span></td>
<td><span data-ttu-id="84c50-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-168">Period 1</span></span></td>
<td><span data-ttu-id="84c50-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="84c50-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="84c50-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-173">Cost element</span></span></th>
<th><span data-ttu-id="84c50-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-174">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="84c50-177">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-177">CC099</span></span></td>
<td><span data-ttu-id="84c50-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-178">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-179">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-179">10001</span></span></td>
<td><span data-ttu-id="84c50-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-180">Electricity</span></span></td>
<td><span data-ttu-id="84c50-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="84c50-181">Unclassified</span></span></td>
<td><span data-ttu-id="84c50-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="84c50-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="84c50-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-185">Cost element</span></span></th>
<th><span data-ttu-id="84c50-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-186">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-187">Amount</span></span></th>
<th><span data-ttu-id="84c50-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-189">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-189">CC099</span></span></td>
<td><span data-ttu-id="84c50-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-190">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-191">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-191">10001</span></span></td>
<td><span data-ttu-id="84c50-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-192">Electricity</span></span></td>
<td><span data-ttu-id="84c50-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="84c50-193">Unclassified</span></span></td>
<td><span data-ttu-id="84c50-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-194">10,000.00</span></span></td>
<td><span data-ttu-id="84c50-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-196">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-196">CC099</span></span></td>
<td><span data-ttu-id="84c50-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-197">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-198">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-198">10001</span></span></td>
<td><span data-ttu-id="84c50-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-199">Electricity</span></span></td>
<td><span data-ttu-id="84c50-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="84c50-200">Unclassified</span></span></td>
<td><span data-ttu-id="84c50-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-201">-10,000.00</span></span></td>
<td><span data-ttu-id="84c50-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-203">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-203">CC099</span></span></td>
<td><span data-ttu-id="84c50-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-204">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-205">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-205">10001</span></span></td>
<td><span data-ttu-id="84c50-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-206">Electricity</span></span></td>
<td><span data-ttu-id="84c50-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-207">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-208">1,000.00</span></span></td>
<td><span data-ttu-id="84c50-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-210">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-210">CC099</span></span></td>
<td><span data-ttu-id="84c50-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-211">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-212">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-212">10001</span></span></td>
<td><span data-ttu-id="84c50-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-213">Electricity</span></span></td>
<td><span data-ttu-id="84c50-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-214">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="84c50-215">9,000.00</span></span></td>
<td><span data-ttu-id="84c50-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-217">Detaljerad information om kostnadsbeteende finns i Kostnadsbeteendepolicy.</span><span class="sxs-lookup"><span data-stu-id="84c50-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="84c50-218">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="84c50-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="84c50-219">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="84c50-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="84c50-220">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="84c50-221">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="84c50-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="84c50-222">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="84c50-222">Define the cost distribution rule</span></span>

<span data-ttu-id="84c50-223">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="84c50-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="84c50-224">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="84c50-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="84c50-225">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="84c50-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="84c50-226">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="84c50-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="84c50-227">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="84c50-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="84c50-228">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-229">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-229">Cost object</span></span></th>
<th><span data-ttu-id="84c50-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="84c50-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-231">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-231">CC001</span></span></td>
<td><span data-ttu-id="84c50-232">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-232">HR</span></span></td>
<td><span data-ttu-id="84c50-233">1 000</span><span class="sxs-lookup"><span data-stu-id="84c50-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-234">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-234">CC002</span></span></td>
<td><span data-ttu-id="84c50-235">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-235">Finance</span></span></td>
<td><span data-ttu-id="84c50-236">6,000</span><span class="sxs-lookup"><span data-stu-id="84c50-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-237">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-237">CC003</span></span></td>
<td><span data-ttu-id="84c50-238">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-238">Assembly</span></span></td>
<td><span data-ttu-id="84c50-239">0</span><span class="sxs-lookup"><span data-stu-id="84c50-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-240">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="84c50-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-241">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-241">Cost object</span></span></th>
<th><span data-ttu-id="84c50-242">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-242">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-243">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-243">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-244">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-245">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-245">CC001</span></span></td>
<td><span data-ttu-id="84c50-246">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-246">HR</span></span></td>
<td><span data-ttu-id="84c50-247">1 000</span><span class="sxs-lookup"><span data-stu-id="84c50-247">1,000</span></span></td>
<td><span data-ttu-id="84c50-248">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="84c50-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="84c50-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-250">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-250">CC002</span></span></td>
<td><span data-ttu-id="84c50-251">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-251">Finance</span></span></td>
<td><span data-ttu-id="84c50-252">6,000</span><span class="sxs-lookup"><span data-stu-id="84c50-252">6,000</span></span></td>
<td><span data-ttu-id="84c50-253">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="84c50-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="84c50-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-255">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-255">CC003</span></span></td>
<td><span data-ttu-id="84c50-256">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-256">Assembly</span></span></td>
<td><span data-ttu-id="84c50-257">0</span><span class="sxs-lookup"><span data-stu-id="84c50-257">0</span></span></td>
<td><span data-ttu-id="84c50-258">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="84c50-259">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-260">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="84c50-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="84c50-261">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="84c50-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-262">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-262">Cost object</span></span></th>
<th><span data-ttu-id="84c50-263">Formel</span><span class="sxs-lookup"><span data-stu-id="84c50-263">Formula</span></span></th>
<th><span data-ttu-id="84c50-264">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-264">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-265">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-265">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-266">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-267">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-267">CC001</span></span></td>
<td><span data-ttu-id="84c50-268">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-268">HR</span></span></td>
<td><span data-ttu-id="84c50-269">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="84c50-270">1</span><span class="sxs-lookup"><span data-stu-id="84c50-270">1</span></span></td>
<td><span data-ttu-id="84c50-271">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="84c50-272">500.00</span><span class="sxs-lookup"><span data-stu-id="84c50-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-273">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-273">CC002</span></span></td>
<td><span data-ttu-id="84c50-274">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-274">Finance</span></span></td>
<td><span data-ttu-id="84c50-275">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="84c50-276">1</span><span class="sxs-lookup"><span data-stu-id="84c50-276">1</span></span></td>
<td><span data-ttu-id="84c50-277">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="84c50-278">500.00</span><span class="sxs-lookup"><span data-stu-id="84c50-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-279">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-279">CC003</span></span></td>
<td><span data-ttu-id="84c50-280">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-280">Assembly</span></span></td>
<td><span data-ttu-id="84c50-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="84c50-282">0</span><span class="sxs-lookup"><span data-stu-id="84c50-282">0</span></span></td>
<td><span data-ttu-id="84c50-283">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="84c50-284">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="84c50-285">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-286">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-286">Journal</span></span></th>
<th><span data-ttu-id="84c50-287">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="84c50-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="84c50-288">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="84c50-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="84c50-289">version</span><span class="sxs-lookup"><span data-stu-id="84c50-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-290">00002</span><span class="sxs-lookup"><span data-stu-id="84c50-290">00002</span></span></td>
<td><span data-ttu-id="84c50-291">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="84c50-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="84c50-292">Skatt</span><span class="sxs-lookup"><span data-stu-id="84c50-292">Fiscal</span></span></td>
<td><span data-ttu-id="84c50-293">2017</span><span class="sxs-lookup"><span data-stu-id="84c50-293">2017</span></span></td>
<td><span data-ttu-id="84c50-294">Period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-294">Period 1</span></span></td>
<td><span data-ttu-id="84c50-295">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="84c50-296">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="84c50-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-297">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-298">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-299">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-299">Cost element</span></span></th>
<th><span data-ttu-id="84c50-300">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-300">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-301">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-302">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-303">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-303">CC099</span></span></td>
<td><span data-ttu-id="84c50-304">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-304">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-305">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-305">10001</span></span></td>
<td><span data-ttu-id="84c50-306">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-306">Electricity</span></span></td>
<td><span data-ttu-id="84c50-307">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-307">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-308">1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-309">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-310">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-310">CC099</span></span></td>
<td><span data-ttu-id="84c50-311">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-311">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-312">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-312">10001</span></span></td>
<td><span data-ttu-id="84c50-313">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-313">Electricity</span></span></td>
<td><span data-ttu-id="84c50-314">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-314">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="84c50-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="84c50-316">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="84c50-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-317">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-318">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-318">Cost element</span></span></th>
<th><span data-ttu-id="84c50-319">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-319">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-320">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-320">Amount</span></span></th>
<th><span data-ttu-id="84c50-321">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-322">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-322">CC099</span></span></td>
<td><span data-ttu-id="84c50-323">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-323">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-324">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-324">10001</span></span></td>
<td><span data-ttu-id="84c50-325">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-325">Electricity</span></span></td>
<td><span data-ttu-id="84c50-326">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-326">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-327">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-327">-1,000.00</span></span></td>
<td><span data-ttu-id="84c50-328">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-329">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-329">CC001</span></span></td>
<td><span data-ttu-id="84c50-330">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-330">HR</span></span></td>
<td><span data-ttu-id="84c50-331">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-331">10001</span></span></td>
<td><span data-ttu-id="84c50-332">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-332">Electricity</span></span></td>
<td><span data-ttu-id="84c50-333">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-333">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-334">500.00</span><span class="sxs-lookup"><span data-stu-id="84c50-334">500.00</span></span></td>
<td><span data-ttu-id="84c50-335">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-336">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-336">CC002</span></span></td>
<td><span data-ttu-id="84c50-337">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-337">Finance</span></span></td>
<td><span data-ttu-id="84c50-338">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-338">10001</span></span></td>
<td><span data-ttu-id="84c50-339">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-339">Electricity</span></span></td>
<td><span data-ttu-id="84c50-340">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-340">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-341">500.00</span><span class="sxs-lookup"><span data-stu-id="84c50-341">500.00</span></span></td>
<td><span data-ttu-id="84c50-342">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-343">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-343">CC099</span></span></td>
<td><span data-ttu-id="84c50-344">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="84c50-344">Default cost center</span></span></td>
<td><span data-ttu-id="84c50-345">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-345">10001</span></span></td>
<td><span data-ttu-id="84c50-346">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-346">Electricity</span></span></td>
<td><span data-ttu-id="84c50-347">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-347">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-348">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="84c50-348">-9,000.00</span></span></td>
<td><span data-ttu-id="84c50-349">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-350">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-350">CC001</span></span></td>
<td><span data-ttu-id="84c50-351">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-351">HR</span></span></td>
<td><span data-ttu-id="84c50-352">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-352">10001</span></span></td>
<td><span data-ttu-id="84c50-353">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-353">Electricity</span></span></td>
<td><span data-ttu-id="84c50-354">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-354">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="84c50-355">1,285.71</span></span></td>
<td><span data-ttu-id="84c50-356">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-357">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-357">CC002</span></span></td>
<td><span data-ttu-id="84c50-358">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-358">Finance</span></span></td>
<td><span data-ttu-id="84c50-359">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-359">10001</span></span></td>
<td><span data-ttu-id="84c50-360">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-360">Electricity</span></span></td>
<td><span data-ttu-id="84c50-361">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-361">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="84c50-362">7,714.29</span></span></td>
<td><span data-ttu-id="84c50-363">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-364">För detaljerad information om kostnadsfördelning och allokeringsunderlag, se Kostnadsfördelningspolicy och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="84c50-365">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="84c50-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="84c50-366">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="84c50-367">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="84c50-368">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="84c50-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="84c50-369">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-369">Define the overhead rate</span></span>

<span data-ttu-id="84c50-370">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="84c50-371">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="84c50-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-372">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-372">Cost object</span></span></th>
<th><span data-ttu-id="84c50-373">Timmar</span><span class="sxs-lookup"><span data-stu-id="84c50-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-374">Proj 1</span></span></td>
<td><span data-ttu-id="84c50-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-375">Project 1</span></span></td>
<td><span data-ttu-id="84c50-376">3</span><span class="sxs-lookup"><span data-stu-id="84c50-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-377">Proj 2</span></span></td>
<td><span data-ttu-id="84c50-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-378">Project 2</span></span></td>
<td><span data-ttu-id="84c50-379">1</span><span class="sxs-lookup"><span data-stu-id="84c50-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-380">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="84c50-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-381">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-381">Cost object</span></span></th>
<th><span data-ttu-id="84c50-382">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-382">Cost element</span></span></th>
<th><span data-ttu-id="84c50-383">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-383">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-384">Enheter</span><span class="sxs-lookup"><span data-stu-id="84c50-384">Units</span></span></th>
<th><span data-ttu-id="84c50-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="84c50-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-386">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-386">CC001</span></span></td>
<td><span data-ttu-id="84c50-387">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-387">HR</span></span></td>
<td><span data-ttu-id="84c50-388">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-388">10001</span></span></td>
<td><span data-ttu-id="84c50-389">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-389">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-390">1</span><span class="sxs-lookup"><span data-stu-id="84c50-390">1</span></span></td>
<td><span data-ttu-id="84c50-391">10</span><span class="sxs-lookup"><span data-stu-id="84c50-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-392">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-393">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-393">Cost object</span></span></th>
<th><span data-ttu-id="84c50-394">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-394">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-395">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-395">Cost element</span></span></th>
<th><span data-ttu-id="84c50-396">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-396">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-397">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-398">Proj 1</span></span></td>
<td><span data-ttu-id="84c50-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-399">Project 1</span></span></td>
<td><span data-ttu-id="84c50-400">3</span><span class="sxs-lookup"><span data-stu-id="84c50-400">3</span></span></td>
<td><span data-ttu-id="84c50-401">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-401">10001</span></span></td>
<td><span data-ttu-id="84c50-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="84c50-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="84c50-403">30,00</span><span class="sxs-lookup"><span data-stu-id="84c50-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-404">Proj 2</span></span></td>
<td><span data-ttu-id="84c50-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-405">Project 2</span></span></td>
<td><span data-ttu-id="84c50-406">1</span><span class="sxs-lookup"><span data-stu-id="84c50-406">1</span></span></td>
<td><span data-ttu-id="84c50-407">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-407">10001</span></span></td>
<td><span data-ttu-id="84c50-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="84c50-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="84c50-409">10,00</span><span class="sxs-lookup"><span data-stu-id="84c50-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="84c50-410">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-411">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-411">Journal</span></span></th>
<th><span data-ttu-id="84c50-412">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="84c50-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="84c50-413">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="84c50-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="84c50-414">version</span><span class="sxs-lookup"><span data-stu-id="84c50-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-415">00003</span><span class="sxs-lookup"><span data-stu-id="84c50-415">00003</span></span></td>
<td><span data-ttu-id="84c50-416">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="84c50-417">Skatt</span><span class="sxs-lookup"><span data-stu-id="84c50-417">Fiscal</span></span></td>
<td><span data-ttu-id="84c50-418">2017</span><span class="sxs-lookup"><span data-stu-id="84c50-418">2017</span></span></td>
<td><span data-ttu-id="84c50-419">Period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-419">Period 1</span></span></td>
<td><span data-ttu-id="84c50-420">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="84c50-421">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="84c50-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-422">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-423">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-423">Cost object</span></span></th>
<th><span data-ttu-id="84c50-424">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-425">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-426">Proj 1</span></span></td>
<td><span data-ttu-id="84c50-427">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="84c50-428">3,00</span><span class="sxs-lookup"><span data-stu-id="84c50-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-429">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-430">Proj 2</span></span></td>
<td><span data-ttu-id="84c50-431">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="84c50-432">1,00</span><span class="sxs-lookup"><span data-stu-id="84c50-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="84c50-433">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="84c50-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-434">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-435">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-435">Cost element</span></span></th>
<th><span data-ttu-id="84c50-436">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-436">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-437">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-437">Amount</span></span></th>
<th><span data-ttu-id="84c50-438">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="84c50-439">CC0001</span></span></td>
<td><span data-ttu-id="84c50-440">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-440">HR</span></span></td>
<td><span data-ttu-id="84c50-441">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-441">10001</span></span></td>
<td><span data-ttu-id="84c50-442">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-442">Electricity</span></span></td>
<td><span data-ttu-id="84c50-443">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-443">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="84c50-444">-30.00</span></span></td>
<td><span data-ttu-id="84c50-445">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-446">Proj 1</span></span></td>
<td><span data-ttu-id="84c50-447">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="84c50-448">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-448">10001</span></span></td>
<td><span data-ttu-id="84c50-449">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-449">Electricity</span></span></td>
<td><span data-ttu-id="84c50-450">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-450">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-451">30,00</span><span class="sxs-lookup"><span data-stu-id="84c50-451">30.00</span></span></td>
<td><span data-ttu-id="84c50-452">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-453">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-453">CC001</span></span></td>
<td><span data-ttu-id="84c50-454">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-454">HR</span></span></td>
<td><span data-ttu-id="84c50-455">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-455">10001</span></span></td>
<td><span data-ttu-id="84c50-456">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-456">Electricity</span></span></td>
<td><span data-ttu-id="84c50-457">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-457">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="84c50-458">-10.00</span></span></td>
<td><span data-ttu-id="84c50-459">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-460">Proj 2</span></span></td>
<td><span data-ttu-id="84c50-461">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="84c50-462">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-462">10001</span></span></td>
<td><span data-ttu-id="84c50-463">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-463">Electricity</span></span></td>
<td><span data-ttu-id="84c50-464">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-464">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-465">10,00</span><span class="sxs-lookup"><span data-stu-id="84c50-465">10.00</span></span></td>
<td><span data-ttu-id="84c50-466">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-467">Detaljerad information om policy för indirekt kostnad finns i Policy för indirekt kostnad och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="84c50-468">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="84c50-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="84c50-469">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="84c50-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="84c50-470">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="84c50-471">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="84c50-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="84c50-472">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="84c50-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="84c50-473">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="84c50-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="84c50-474">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="84c50-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="84c50-475">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="84c50-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="84c50-476">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="84c50-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="84c50-477">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="84c50-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="84c50-478">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="84c50-478">Define the cost allocation</span></span>

<span data-ttu-id="84c50-479">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="84c50-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="84c50-480">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="84c50-481">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="84c50-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-482">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-482">Cost object</span></span></th>
<th><span data-ttu-id="84c50-483">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="84c50-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-484">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-484">CC002</span></span></td>
<td><span data-ttu-id="84c50-485">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-485">Finance</span></span></td>
<td><span data-ttu-id="84c50-486">35</span><span class="sxs-lookup"><span data-stu-id="84c50-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-487">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-487">CC003</span></span></td>
<td><span data-ttu-id="84c50-488">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-488">Assembly</span></span></td>
<td><span data-ttu-id="84c50-489">55</span><span class="sxs-lookup"><span data-stu-id="84c50-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-490">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-490">CC004</span></span></td>
<td><span data-ttu-id="84c50-491">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-491">Packaging</span></span></td>
<td><span data-ttu-id="84c50-492">10</span><span class="sxs-lookup"><span data-stu-id="84c50-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-493">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="84c50-494">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="84c50-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-495">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-495">Cost object</span></span></th>
<th><span data-ttu-id="84c50-496">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="84c50-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-497">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-497">CC003</span></span></td>
<td><span data-ttu-id="84c50-498">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-498">Assembly</span></span></td>
<td><span data-ttu-id="84c50-499">65</span><span class="sxs-lookup"><span data-stu-id="84c50-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-500">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-500">CC004</span></span></td>
<td><span data-ttu-id="84c50-501">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-501">Packaging</span></span></td>
<td><span data-ttu-id="84c50-502">35</span><span class="sxs-lookup"><span data-stu-id="84c50-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-503">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="84c50-504">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="84c50-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-505">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-505">Cost object</span></span></th>
<th><span data-ttu-id="84c50-506">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="84c50-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-507">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-508">Product 1</span></span></td>
<td><span data-ttu-id="84c50-509">60</span><span class="sxs-lookup"><span data-stu-id="84c50-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-510">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-511">Product 2</span></span></td>
<td><span data-ttu-id="84c50-512">20</span><span class="sxs-lookup"><span data-stu-id="84c50-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-513">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="84c50-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="84c50-514">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="84c50-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-515">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-515">Cost object</span></span></th>
<th><span data-ttu-id="84c50-516">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="84c50-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-517">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-518">Product 1</span></span></td>
<td><span data-ttu-id="84c50-519">80</span><span class="sxs-lookup"><span data-stu-id="84c50-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-520">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-521">Product 2</span></span></td>
<td><span data-ttu-id="84c50-522">15</span><span class="sxs-lookup"><span data-stu-id="84c50-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-523">**Obs:** i Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="84c50-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="84c50-524">Mer detaljerad information om provider av statistiska mått finns i Providermallar för statistiska mätningar.</span><span class="sxs-lookup"><span data-stu-id="84c50-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="84c50-525">(Observera att det här avsnittet är inte klart, men kommer snart.) I följande tabell visas resultatet när HR-tjänsten används som ett allokeringsunderlag för totalkostnaden (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="84c50-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-526">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-526">Cost object</span></span></th>
<th><span data-ttu-id="84c50-527">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-527">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-528">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-528">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-529">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-529">Amount</span></span></th>
<th><span data-ttu-id="84c50-530">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-531">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-531">CC002</span></span></td>
<td><span data-ttu-id="84c50-532">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-532">Finance</span></span></td>
<td><span data-ttu-id="84c50-533">35</span><span class="sxs-lookup"><span data-stu-id="84c50-533">35</span></span></td>
<td><span data-ttu-id="84c50-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="84c50-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="84c50-535">175.00</span><span class="sxs-lookup"><span data-stu-id="84c50-535">175.00</span></span></td>
<td><span data-ttu-id="84c50-536">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-537">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-537">CC003</span></span></td>
<td><span data-ttu-id="84c50-538">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-538">Assembly</span></span></td>
<td><span data-ttu-id="84c50-539">55</span><span class="sxs-lookup"><span data-stu-id="84c50-539">55</span></span></td>
<td><span data-ttu-id="84c50-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="84c50-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="84c50-541">275.00</span><span class="sxs-lookup"><span data-stu-id="84c50-541">275.00</span></span></td>
<td><span data-ttu-id="84c50-542">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-543">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-543">CC004</span></span></td>
<td><span data-ttu-id="84c50-544">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-544">Packaging</span></span></td>
<td><span data-ttu-id="84c50-545">10</span><span class="sxs-lookup"><span data-stu-id="84c50-545">10</span></span></td>
<td><span data-ttu-id="84c50-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="84c50-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="84c50-547">50,00</span><span class="sxs-lookup"><span data-stu-id="84c50-547">50.00</span></span></td>
<td><span data-ttu-id="84c50-548">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-549">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-549">CC002</span></span></td>
<td><span data-ttu-id="84c50-550">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-550">Finance</span></span></td>
<td><span data-ttu-id="84c50-551">35</span><span class="sxs-lookup"><span data-stu-id="84c50-551">35</span></span></td>
<td><span data-ttu-id="84c50-552">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="84c50-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="84c50-553">436.00</span><span class="sxs-lookup"><span data-stu-id="84c50-553">436.00</span></span></td>
<td><span data-ttu-id="84c50-554">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-555">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-555">CC003</span></span></td>
<td><span data-ttu-id="84c50-556">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-556">Assembly</span></span></td>
<td><span data-ttu-id="84c50-557">55</span><span class="sxs-lookup"><span data-stu-id="84c50-557">55</span></span></td>
<td><span data-ttu-id="84c50-558">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="84c50-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="84c50-559">685.14</span><span class="sxs-lookup"><span data-stu-id="84c50-559">685.14</span></span></td>
<td><span data-ttu-id="84c50-560">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-561">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-561">CC004</span></span></td>
<td><span data-ttu-id="84c50-562">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-562">Packaging</span></span></td>
<td><span data-ttu-id="84c50-563">10</span><span class="sxs-lookup"><span data-stu-id="84c50-563">10</span></span></td>
<td><span data-ttu-id="84c50-564">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="84c50-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="84c50-565">124.57</span><span class="sxs-lookup"><span data-stu-id="84c50-565">124.57</span></span></td>
<td><span data-ttu-id="84c50-566">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-567">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="84c50-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-568">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-568">Cost object</span></span></th>
<th><span data-ttu-id="84c50-569">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-569">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-570">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-570">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-571">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-571">Amount</span></span></th>
<th><span data-ttu-id="84c50-572">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-573">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-573">CC003</span></span></td>
<td><span data-ttu-id="84c50-574">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-574">Assembly</span></span></td>
<td><span data-ttu-id="84c50-575">65</span><span class="sxs-lookup"><span data-stu-id="84c50-575">65</span></span></td>
<td><span data-ttu-id="84c50-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="84c50-577">438.75</span><span class="sxs-lookup"><span data-stu-id="84c50-577">438.75</span></span></td>
<td><span data-ttu-id="84c50-578">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-579">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-579">CC004</span></span></td>
<td><span data-ttu-id="84c50-580">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-580">Packaging</span></span></td>
<td><span data-ttu-id="84c50-581">35</span><span class="sxs-lookup"><span data-stu-id="84c50-581">35</span></span></td>
<td><span data-ttu-id="84c50-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="84c50-583">236.25</span><span class="sxs-lookup"><span data-stu-id="84c50-583">236.25</span></span></td>
<td><span data-ttu-id="84c50-584">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-585">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-585">CC003</span></span></td>
<td><span data-ttu-id="84c50-586">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-586">Assembly</span></span></td>
<td><span data-ttu-id="84c50-587">65</span><span class="sxs-lookup"><span data-stu-id="84c50-587">65</span></span></td>
<td><span data-ttu-id="84c50-588">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="84c50-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="84c50-589">5,297.69</span></span></td>
<td><span data-ttu-id="84c50-590">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-591">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-591">CC004</span></span></td>
<td><span data-ttu-id="84c50-592">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-592">Packaging</span></span></td>
<td><span data-ttu-id="84c50-593">35</span><span class="sxs-lookup"><span data-stu-id="84c50-593">35</span></span></td>
<td><span data-ttu-id="84c50-594">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="84c50-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="84c50-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="84c50-595">2,852.60</span></span></td>
<td><span data-ttu-id="84c50-596">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-597">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="84c50-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-598">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-598">Cost object</span></span></th>
<th><span data-ttu-id="84c50-599">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-599">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-600">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-600">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-601">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-601">Amount</span></span></th>
<th><span data-ttu-id="84c50-602">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-603">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-604">Product 1</span></span></td>
<td><span data-ttu-id="84c50-605">60</span><span class="sxs-lookup"><span data-stu-id="84c50-605">60</span></span></td>
<td><span data-ttu-id="84c50-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="84c50-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="84c50-607">535.31</span><span class="sxs-lookup"><span data-stu-id="84c50-607">535.31</span></span></td>
<td><span data-ttu-id="84c50-608">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-609">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-610">Product 2</span></span></td>
<td><span data-ttu-id="84c50-611">20</span><span class="sxs-lookup"><span data-stu-id="84c50-611">20</span></span></td>
<td><span data-ttu-id="84c50-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="84c50-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="84c50-613">178.44</span><span class="sxs-lookup"><span data-stu-id="84c50-613">178.44</span></span></td>
<td><span data-ttu-id="84c50-614">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-615">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-616">Product 1</span></span></td>
<td><span data-ttu-id="84c50-617">60</span><span class="sxs-lookup"><span data-stu-id="84c50-617">60</span></span></td>
<td><span data-ttu-id="84c50-618">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="84c50-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="84c50-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="84c50-619">4,487.12</span></span></td>
<td><span data-ttu-id="84c50-620">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-621">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-622">Product 2</span></span></td>
<td><span data-ttu-id="84c50-623">20</span><span class="sxs-lookup"><span data-stu-id="84c50-623">20</span></span></td>
<td><span data-ttu-id="84c50-624">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="84c50-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="84c50-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="84c50-625">1,495.71</span></span></td>
<td><span data-ttu-id="84c50-626">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="84c50-627">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="84c50-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-628">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-628">Cost object</span></span></th>
<th><span data-ttu-id="84c50-629">Storlek</span><span class="sxs-lookup"><span data-stu-id="84c50-629">Magnitude</span></span></th>
<th><span data-ttu-id="84c50-630">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="84c50-630">Allocation factor</span></span></th>
<th><span data-ttu-id="84c50-631">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-631">Amount</span></span></th>
<th><span data-ttu-id="84c50-632">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-633">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-634">Product 1</span></span></td>
<td><span data-ttu-id="84c50-635">80</span><span class="sxs-lookup"><span data-stu-id="84c50-635">80</span></span></td>
<td><span data-ttu-id="84c50-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="84c50-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="84c50-637">241.05</span><span class="sxs-lookup"><span data-stu-id="84c50-637">241.05</span></span></td>
<td><span data-ttu-id="84c50-638">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-639">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-640">Product 2</span></span></td>
<td><span data-ttu-id="84c50-641">15</span><span class="sxs-lookup"><span data-stu-id="84c50-641">15</span></span></td>
<td><span data-ttu-id="84c50-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="84c50-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="84c50-643">45.20</span><span class="sxs-lookup"><span data-stu-id="84c50-643">45.20</span></span></td>
<td><span data-ttu-id="84c50-644">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-645">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-646">Product 1</span></span></td>
<td><span data-ttu-id="84c50-647">80</span><span class="sxs-lookup"><span data-stu-id="84c50-647">80</span></span></td>
<td><span data-ttu-id="84c50-648">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="84c50-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="84c50-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="84c50-649">2,507.09</span></span></td>
<td><span data-ttu-id="84c50-650">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-651">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-652">Product 2</span></span></td>
<td><span data-ttu-id="84c50-653">15</span><span class="sxs-lookup"><span data-stu-id="84c50-653">15</span></span></td>
<td><span data-ttu-id="84c50-654">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="84c50-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="84c50-655">470.08</span><span class="sxs-lookup"><span data-stu-id="84c50-655">470.08</span></span></td>
<td><span data-ttu-id="84c50-656">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="84c50-657">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="84c50-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-658">Journal</span><span class="sxs-lookup"><span data-stu-id="84c50-658">Journal</span></span></th>
<th><span data-ttu-id="84c50-659">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="84c50-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="84c50-660">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="84c50-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="84c50-661">version</span><span class="sxs-lookup"><span data-stu-id="84c50-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-662">00004</span><span class="sxs-lookup"><span data-stu-id="84c50-662">00004</span></span></td>
<td><span data-ttu-id="84c50-663">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="84c50-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="84c50-664">Skatt</span><span class="sxs-lookup"><span data-stu-id="84c50-664">Fiscal</span></span></td>
<td><span data-ttu-id="84c50-665">2017</span><span class="sxs-lookup"><span data-stu-id="84c50-665">2017</span></span></td>
<td><span data-ttu-id="84c50-666">Period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-666">Period 1</span></span></td>
<td><span data-ttu-id="84c50-667">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="84c50-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="84c50-668">Journalrader</span><span class="sxs-lookup"><span data-stu-id="84c50-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="84c50-669">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-670">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-671">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-671">Cost element</span></span></th>
<th><span data-ttu-id="84c50-672">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-672">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-673">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-674">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-675">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-675">CC001</span></span></td>
<td><span data-ttu-id="84c50-676">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-676">HR</span></span></td>
<td><span data-ttu-id="84c50-677">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-677">10001</span></span></td>
<td><span data-ttu-id="84c50-678">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-678">Electricity</span></span></td>
<td><span data-ttu-id="84c50-679">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-679">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-680">500.00</span><span class="sxs-lookup"><span data-stu-id="84c50-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-681">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-682">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-682">CC001</span></span></td>
<td><span data-ttu-id="84c50-683">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-683">HR</span></span></td>
<td><span data-ttu-id="84c50-684">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-684">10001</span></span></td>
<td><span data-ttu-id="84c50-685">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-685">Electricity</span></span></td>
<td><span data-ttu-id="84c50-686">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-686">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="84c50-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-688">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-689">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-689">CC002</span></span></td>
<td><span data-ttu-id="84c50-690">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-690">Finance</span></span></td>
<td><span data-ttu-id="84c50-691">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-691">10001</span></span></td>
<td><span data-ttu-id="84c50-692">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-692">Electricity</span></span></td>
<td><span data-ttu-id="84c50-693">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-693">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-694">675.00</span><span class="sxs-lookup"><span data-stu-id="84c50-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-695">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-696">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-696">CC002</span></span></td>
<td><span data-ttu-id="84c50-697">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-697">Finance</span></span></td>
<td><span data-ttu-id="84c50-698">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-698">10001</span></span></td>
<td><span data-ttu-id="84c50-699">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-699">Electricity</span></span></td>
<td><span data-ttu-id="84c50-700">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-700">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="84c50-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-702">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-703">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-703">CC003</span></span></td>
<td><span data-ttu-id="84c50-704">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-704">Assembly</span></span></td>
<td><span data-ttu-id="84c50-705">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-705">10001</span></span></td>
<td><span data-ttu-id="84c50-706">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-706">Electricity</span></span></td>
<td><span data-ttu-id="84c50-707">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-707">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-708">713.75</span><span class="sxs-lookup"><span data-stu-id="84c50-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-709">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-710">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-710">CC003</span></span></td>
<td><span data-ttu-id="84c50-711">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-711">Assembly</span></span></td>
<td><span data-ttu-id="84c50-712">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-712">10001</span></span></td>
<td><span data-ttu-id="84c50-713">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-713">Electricity</span></span></td>
<td><span data-ttu-id="84c50-714">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-714">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="84c50-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-716">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-717">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-717">CC003</span></span></td>
<td><span data-ttu-id="84c50-718">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-718">Packaging</span></span></td>
<td><span data-ttu-id="84c50-719">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-719">10001</span></span></td>
<td><span data-ttu-id="84c50-720">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-720">Electricity</span></span></td>
<td><span data-ttu-id="84c50-721">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-721">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-722">286.25</span><span class="sxs-lookup"><span data-stu-id="84c50-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-723">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-724">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-724">CC003</span></span></td>
<td><span data-ttu-id="84c50-725">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-725">Packaging</span></span></td>
<td><span data-ttu-id="84c50-726">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-726">10001</span></span></td>
<td><span data-ttu-id="84c50-727">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-727">Electricity</span></span></td>
<td><span data-ttu-id="84c50-728">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-728">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="84c50-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-730">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-731">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-732">Product 1</span></span></td>
<td><span data-ttu-id="84c50-733">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-733">10001</span></span></td>
<td><span data-ttu-id="84c50-734">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-734">Electricity</span></span></td>
<td><span data-ttu-id="84c50-735">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-735">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-736">776.36</span><span class="sxs-lookup"><span data-stu-id="84c50-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-737">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-738">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-739">Product 1</span></span></td>
<td><span data-ttu-id="84c50-740">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-740">10001</span></span></td>
<td><span data-ttu-id="84c50-741">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-741">Electricity</span></span></td>
<td><span data-ttu-id="84c50-742">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-742">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="84c50-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-744">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-745">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-746">Product 1</span></span></td>
<td><span data-ttu-id="84c50-747">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-747">10001</span></span></td>
<td><span data-ttu-id="84c50-748">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-748">Electricity</span></span></td>
<td><span data-ttu-id="84c50-749">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-749">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-750">223.64</span><span class="sxs-lookup"><span data-stu-id="84c50-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-751">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="84c50-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-752">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-753">Product 1</span></span></td>
<td><span data-ttu-id="84c50-754">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-754">10001</span></span></td>
<td><span data-ttu-id="84c50-755">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-755">Electricity</span></span></td>
<td><span data-ttu-id="84c50-756">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-756">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="84c50-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="84c50-758">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="84c50-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="84c50-759">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="84c50-760">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-760">Cost element</span></span></th>
<th><span data-ttu-id="84c50-761">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="84c50-761">Cost behavior</span></span></th>
<th><span data-ttu-id="84c50-762">Belopp</span><span class="sxs-lookup"><span data-stu-id="84c50-762">Amount</span></span></th>
<th><span data-ttu-id="84c50-763">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="84c50-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="84c50-764">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-764">CC001</span></span></td>
<td><span data-ttu-id="84c50-765">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-765">HR</span></span></td>
<td><span data-ttu-id="84c50-766">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-766">10001</span></span></td>
<td><span data-ttu-id="84c50-767">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-767">Electricity</span></span></td>
<td><span data-ttu-id="84c50-768">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-768">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="84c50-769">-500.00</span></span></td>
<td><span data-ttu-id="84c50-770">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-771">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-771">CC002</span></span></td>
<td><span data-ttu-id="84c50-772">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-772">Finance</span></span></td>
<td><span data-ttu-id="84c50-773">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-773">10001</span></span></td>
<td><span data-ttu-id="84c50-774">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-774">Electricity</span></span></td>
<td><span data-ttu-id="84c50-775">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-775">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-776">175.00</span><span class="sxs-lookup"><span data-stu-id="84c50-776">175.00</span></span></td>
<td><span data-ttu-id="84c50-777">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-778">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-778">CC003</span></span></td>
<td><span data-ttu-id="84c50-779">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-779">Assembly</span></span></td>
<td><span data-ttu-id="84c50-780">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-780">10001</span></span></td>
<td><span data-ttu-id="84c50-781">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-781">Electricity</span></span></td>
<td><span data-ttu-id="84c50-782">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-782">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-783">275.00</span><span class="sxs-lookup"><span data-stu-id="84c50-783">275.00</span></span></td>
<td><span data-ttu-id="84c50-784">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-785">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-785">CC004</span></span></td>
<td><span data-ttu-id="84c50-786">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-786">Packaging</span></span></td>
<td><span data-ttu-id="84c50-787">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-787">10001</span></span></td>
<td><span data-ttu-id="84c50-788">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-788">Electricity</span></span></td>
<td><span data-ttu-id="84c50-789">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-789">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-790">50,00</span><span class="sxs-lookup"><span data-stu-id="84c50-790">50,00</span></span></td>
<td><span data-ttu-id="84c50-791">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-792">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-792">CC001</span></span></td>
<td><span data-ttu-id="84c50-793">Personal</span><span class="sxs-lookup"><span data-stu-id="84c50-793">HR</span></span></td>
<td><span data-ttu-id="84c50-794">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-794">10001</span></span></td>
<td><span data-ttu-id="84c50-795">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-795">Electricity</span></span></td>
<td><span data-ttu-id="84c50-796">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-796">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-797">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="84c50-797">-1,245.71</span></span></td>
<td><span data-ttu-id="84c50-798">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-799">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-799">CC002</span></span></td>
<td><span data-ttu-id="84c50-800">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-800">Finance</span></span></td>
<td><span data-ttu-id="84c50-801">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-801">10001</span></span></td>
<td><span data-ttu-id="84c50-802">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-802">Electricity</span></span></td>
<td><span data-ttu-id="84c50-803">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-803">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-804">436.00</span><span class="sxs-lookup"><span data-stu-id="84c50-804">436.00</span></span></td>
<td><span data-ttu-id="84c50-805">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-806">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-806">CC003</span></span></td>
<td><span data-ttu-id="84c50-807">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-807">Assembly</span></span></td>
<td><span data-ttu-id="84c50-808">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-808">10001</span></span></td>
<td><span data-ttu-id="84c50-809">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-809">Electricity</span></span></td>
<td><span data-ttu-id="84c50-810">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-810">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-811">685.14</span><span class="sxs-lookup"><span data-stu-id="84c50-811">685.14</span></span></td>
<td><span data-ttu-id="84c50-812">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-813">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-813">CC004</span></span></td>
<td><span data-ttu-id="84c50-814">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-814">Packaging</span></span></td>
<td><span data-ttu-id="84c50-815">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-815">10001</span></span></td>
<td><span data-ttu-id="84c50-816">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-816">Electricity</span></span></td>
<td><span data-ttu-id="84c50-817">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-817">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-818">124.57</span><span class="sxs-lookup"><span data-stu-id="84c50-818">124.57</span></span></td>
<td><span data-ttu-id="84c50-819">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-820">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-820">CC002</span></span></td>
<td><span data-ttu-id="84c50-821">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-821">Finance</span></span></td>
<td><span data-ttu-id="84c50-822">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-822">10001</span></span></td>
<td><span data-ttu-id="84c50-823">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-823">Electricity</span></span></td>
<td><span data-ttu-id="84c50-824">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-824">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="84c50-825">-675.00</span></span></td>
<td><span data-ttu-id="84c50-826">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-827">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-827">CC003</span></span></td>
<td><span data-ttu-id="84c50-828">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-828">Assembly</span></span></td>
<td><span data-ttu-id="84c50-829">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-829">10001</span></span></td>
<td><span data-ttu-id="84c50-830">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-830">Electricity</span></span></td>
<td><span data-ttu-id="84c50-831">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-831">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-832">438.75</span><span class="sxs-lookup"><span data-stu-id="84c50-832">438.75</span></span></td>
<td><span data-ttu-id="84c50-833">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-834">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-834">CC004</span></span></td>
<td><span data-ttu-id="84c50-835">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-835">Packaging</span></span></td>
<td><span data-ttu-id="84c50-836">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-836">10001</span></span></td>
<td><span data-ttu-id="84c50-837">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-837">Electricity</span></span></td>
<td><span data-ttu-id="84c50-838">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-838">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-839">236.25</span><span class="sxs-lookup"><span data-stu-id="84c50-839">236.25</span></span></td>
<td><span data-ttu-id="84c50-840">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-841">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-841">CC002</span></span></td>
<td><span data-ttu-id="84c50-842">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="84c50-842">Finance</span></span></td>
<td><span data-ttu-id="84c50-843">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-843">10001</span></span></td>
<td><span data-ttu-id="84c50-844">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-844">Electricity</span></span></td>
<td><span data-ttu-id="84c50-845">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-845">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-846">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="84c50-846">-8,150.29</span></span></td>
<td><span data-ttu-id="84c50-847">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-848">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-848">CC003</span></span></td>
<td><span data-ttu-id="84c50-849">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-849">Assembly</span></span></td>
<td><span data-ttu-id="84c50-850">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-850">10001</span></span></td>
<td><span data-ttu-id="84c50-851">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-851">Electricity</span></span></td>
<td><span data-ttu-id="84c50-852">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-852">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="84c50-853">5,297.69</span></span></td>
<td><span data-ttu-id="84c50-854">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-855">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-855">CC004</span></span></td>
<td><span data-ttu-id="84c50-856">Paketering</span><span class="sxs-lookup"><span data-stu-id="84c50-856">Packaging</span></span></td>
<td><span data-ttu-id="84c50-857">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-857">10001</span></span></td>
<td><span data-ttu-id="84c50-858">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-858">Electricity</span></span></td>
<td><span data-ttu-id="84c50-859">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-859">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="84c50-860">2,852.60</span></span></td>
<td><span data-ttu-id="84c50-861">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-862">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-862">CC003</span></span></td>
<td><span data-ttu-id="84c50-863">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-863">Assembly</span></span></td>
<td><span data-ttu-id="84c50-864">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-864">10001</span></span></td>
<td><span data-ttu-id="84c50-865">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-865">Electricity</span></span></td>
<td><span data-ttu-id="84c50-866">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-866">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="84c50-867">-713.75</span></span></td>
<td><span data-ttu-id="84c50-868">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-869">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-870">Product 1</span></span></td>
<td><span data-ttu-id="84c50-871">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-871">10001</span></span></td>
<td><span data-ttu-id="84c50-872">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-872">Electricity</span></span></td>
<td><span data-ttu-id="84c50-873">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-873">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-874">535.31</span><span class="sxs-lookup"><span data-stu-id="84c50-874">535.31</span></span></td>
<td><span data-ttu-id="84c50-875">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-876">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-877">Product 2</span></span></td>
<td><span data-ttu-id="84c50-878">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-878">10001</span></span></td>
<td><span data-ttu-id="84c50-879">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-879">Electricity</span></span></td>
<td><span data-ttu-id="84c50-880">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-880">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-881">178.44</span><span class="sxs-lookup"><span data-stu-id="84c50-881">178.44</span></span></td>
<td><span data-ttu-id="84c50-882">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-883">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-883">CC003</span></span></td>
<td><span data-ttu-id="84c50-884">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-884">Assembly</span></span></td>
<td><span data-ttu-id="84c50-885">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-885">10001</span></span></td>
<td><span data-ttu-id="84c50-886">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-886">Electricity</span></span></td>
<td><span data-ttu-id="84c50-887">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-887">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-888">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="84c50-888">-5,982.83</span></span></td>
<td><span data-ttu-id="84c50-889">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-890">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-891">Product 1</span></span></td>
<td><span data-ttu-id="84c50-892">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-892">10001</span></span></td>
<td><span data-ttu-id="84c50-893">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-893">Electricity</span></span></td>
<td><span data-ttu-id="84c50-894">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-894">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="84c50-895">4,487.12</span></span></td>
<td><span data-ttu-id="84c50-896">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-897">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-898">Product 2</span></span></td>
<td><span data-ttu-id="84c50-899">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-899">10001</span></span></td>
<td><span data-ttu-id="84c50-900">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-900">Electricity</span></span></td>
<td><span data-ttu-id="84c50-901">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-901">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="84c50-902">1,495.71</span></span></td>
<td><span data-ttu-id="84c50-903">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-904">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-904">CC003</span></span></td>
<td><span data-ttu-id="84c50-905">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-905">Assembly</span></span></td>
<td><span data-ttu-id="84c50-906">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-906">10001</span></span></td>
<td><span data-ttu-id="84c50-907">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-907">Electricity</span></span></td>
<td><span data-ttu-id="84c50-908">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-908">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="84c50-909">-286.25</span></span></td>
<td><span data-ttu-id="84c50-910">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-911">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-912">Product 1</span></span></td>
<td><span data-ttu-id="84c50-913">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-913">10001</span></span></td>
<td><span data-ttu-id="84c50-914">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-914">Electricity</span></span></td>
<td><span data-ttu-id="84c50-915">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-915">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-916">241.05</span><span class="sxs-lookup"><span data-stu-id="84c50-916">241.05</span></span></td>
<td><span data-ttu-id="84c50-917">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-918">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-919">Product 2</span></span></td>
<td><span data-ttu-id="84c50-920">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-920">10001</span></span></td>
<td><span data-ttu-id="84c50-921">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-921">Electricity</span></span></td>
<td><span data-ttu-id="84c50-922">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-922">Fixed cost</span></span></td>
<td><span data-ttu-id="84c50-923">45.20</span><span class="sxs-lookup"><span data-stu-id="84c50-923">45.20</span></span></td>
<td><span data-ttu-id="84c50-924">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-925">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-925">CC003</span></span></td>
<td><span data-ttu-id="84c50-926">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="84c50-926">Assembly</span></span></td>
<td><span data-ttu-id="84c50-927">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-927">10001</span></span></td>
<td><span data-ttu-id="84c50-928">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-928">Electricity</span></span></td>
<td><span data-ttu-id="84c50-929">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-929">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-930">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="84c50-930">-2,977.17</span></span></td>
<td><span data-ttu-id="84c50-931">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-932">Prod 1</span></span></td>
<td><span data-ttu-id="84c50-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="84c50-933">Product 1</span></span></td>
<td><span data-ttu-id="84c50-934">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-934">10001</span></span></td>
<td><span data-ttu-id="84c50-935">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-935">Electricity</span></span></td>
<td><span data-ttu-id="84c50-936">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-936">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="84c50-937">2,507.09</span></span></td>
<td><span data-ttu-id="84c50-938">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="84c50-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-939">Prod 2</span></span></td>
<td><span data-ttu-id="84c50-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="84c50-940">Product 2</span></span></td>
<td><span data-ttu-id="84c50-941">10001</span><span class="sxs-lookup"><span data-stu-id="84c50-941">10001</span></span></td>
<td><span data-ttu-id="84c50-942">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-942">Electricity</span></span></td>
<td><span data-ttu-id="84c50-943">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-943">Variable cost</span></span></td>
<td><span data-ttu-id="84c50-944">470.08</span><span class="sxs-lookup"><span data-stu-id="84c50-944">470.08</span></span></td>
<td><span data-ttu-id="84c50-945">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="84c50-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="84c50-946">Slutsats</span><span class="sxs-lookup"><span data-stu-id="84c50-946">Conclusion</span></span>
<span data-ttu-id="84c50-947">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="84c50-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="84c50-948">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="84c50-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="84c50-949">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="84c50-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="84c50-950">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="84c50-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="84c50-951">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="84c50-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="84c50-952">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="84c50-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="84c50-953">Totalt</span><span class="sxs-lookup"><span data-stu-id="84c50-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="84c50-954">CC099</span><span class="sxs-lookup"><span data-stu-id="84c50-954">CC099</span></span></th>
<th><span data-ttu-id="84c50-955">CC001</span><span class="sxs-lookup"><span data-stu-id="84c50-955">CC001</span></span></th>
<th><span data-ttu-id="84c50-956">CC002</span><span class="sxs-lookup"><span data-stu-id="84c50-956">CC002</span></span></th>
<th><span data-ttu-id="84c50-957">CC003</span><span class="sxs-lookup"><span data-stu-id="84c50-957">CC003</span></span></th>
<th><span data-ttu-id="84c50-958">CC004</span><span class="sxs-lookup"><span data-stu-id="84c50-958">CC004</span></span></th>
<th><span data-ttu-id="84c50-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="84c50-959">Proj 1</span></span></th>
<th><span data-ttu-id="84c50-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="84c50-960">Proj 2</span></span></th>
<th><span data-ttu-id="84c50-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="84c50-961">Prod 1</span></span></th>
<th><span data-ttu-id="84c50-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="84c50-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="84c50-963">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="84c50-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="84c50-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="84c50-973">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="84c50-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-974">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="84c50-975">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-976">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-977">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-978">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-979">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-980">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="84c50-981">776.36</span><span class="sxs-lookup"><span data-stu-id="84c50-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-982">223.64</span><span class="sxs-lookup"><span data-stu-id="84c50-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="84c50-984">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="84c50-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-985">000</span><span class="sxs-lookup"><span data-stu-id="84c50-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-986">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-987">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-988">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-989">0,00</span><span class="sxs-lookup"><span data-stu-id="84c50-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-990">30,00</span><span class="sxs-lookup"><span data-stu-id="84c50-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-991">10,00</span><span class="sxs-lookup"><span data-stu-id="84c50-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="84c50-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="84c50-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="84c50-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="84c50-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="84c50-995">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="84c50-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="84c50-996">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="84c50-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="84c50-997">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="84c50-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="84c50-998">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="84c50-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="84c50-999">Mer information finns i Policy för kostnadssummering.</span><span class="sxs-lookup"><span data-stu-id="84c50-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="84c50-1000">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="84c50-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




