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
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544065"
---
# <a name="overhead-calculation"></a><span data-ttu-id="18e78-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="18e78-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18e78-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="18e78-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="18e78-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="18e78-105">Term definition</span></span>
---------------

<span data-ttu-id="18e78-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="18e78-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="18e78-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="18e78-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="18e78-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="18e78-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="18e78-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="18e78-109">Rent</span></span>
-   <span data-ttu-id="18e78-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-110">Electricity</span></span>
-   <span data-ttu-id="18e78-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="18e78-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="18e78-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="18e78-112">Overhead calculation overview</span></span>
<span data-ttu-id="18e78-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="18e78-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="18e78-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="18e78-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="18e78-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="18e78-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="18e78-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="18e78-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="18e78-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="18e78-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="18e78-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="18e78-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="18e78-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="18e78-119">Version type</span></span>
-   <span data-ttu-id="18e78-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="18e78-120">Date and time</span></span>
-   <span data-ttu-id="18e78-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="18e78-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="18e78-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="18e78-122">Fiscal year</span></span>
-   <span data-ttu-id="18e78-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="18e78-123">Fiscal period</span></span>

<span data-ttu-id="18e78-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="18e78-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="18e78-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="18e78-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="18e78-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="18e78-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="18e78-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="18e78-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="18e78-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="18e78-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="18e78-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="18e78-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="18e78-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="18e78-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="18e78-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="18e78-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="18e78-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="18e78-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="18e78-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="18e78-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="18e78-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="18e78-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="18e78-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="18e78-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="18e78-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="18e78-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="18e78-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="18e78-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="18e78-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="18e78-140">Main account</span></span></th>
<th><span data-ttu-id="18e78-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="18e78-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="18e78-143">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-143">CC099</span></span></td>
<td><span data-ttu-id="18e78-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-144">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-145">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-145">10001</span></span></td>
<td><span data-ttu-id="18e78-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-146">Electricity</span></span></td>
<td><span data-ttu-id="18e78-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="18e78-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="18e78-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="18e78-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="18e78-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="18e78-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="18e78-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="18e78-151">Define the cost behavior rule</span></span>

<span data-ttu-id="18e78-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="18e78-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="18e78-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="18e78-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="18e78-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="18e78-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="18e78-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="18e78-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="18e78-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="18e78-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="18e78-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="18e78-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="18e78-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="18e78-159">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-160">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-160">Journal</span></span></th>
<th><span data-ttu-id="18e78-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="18e78-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="18e78-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="18e78-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="18e78-163">version</span><span class="sxs-lookup"><span data-stu-id="18e78-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-164">00001</span><span class="sxs-lookup"><span data-stu-id="18e78-164">00001</span></span></td>
<td><span data-ttu-id="18e78-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="18e78-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="18e78-166">Fiscal</span></span></td>
<td><span data-ttu-id="18e78-167">2017</span><span class="sxs-lookup"><span data-stu-id="18e78-167">2017</span></span></td>
<td><span data-ttu-id="18e78-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-168">Period 1</span></span></td>
<td><span data-ttu-id="18e78-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="18e78-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="18e78-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-173">Cost element</span></span></th>
<th><span data-ttu-id="18e78-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-174">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="18e78-177">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-177">CC099</span></span></td>
<td><span data-ttu-id="18e78-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-178">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-179">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-179">10001</span></span></td>
<td><span data-ttu-id="18e78-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-180">Electricity</span></span></td>
<td><span data-ttu-id="18e78-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="18e78-181">Unclassified</span></span></td>
<td><span data-ttu-id="18e78-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="18e78-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="18e78-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-185">Cost element</span></span></th>
<th><span data-ttu-id="18e78-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-186">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-187">Amount</span></span></th>
<th><span data-ttu-id="18e78-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-189">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-189">CC099</span></span></td>
<td><span data-ttu-id="18e78-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-190">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-191">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-191">10001</span></span></td>
<td><span data-ttu-id="18e78-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-192">Electricity</span></span></td>
<td><span data-ttu-id="18e78-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="18e78-193">Unclassified</span></span></td>
<td><span data-ttu-id="18e78-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-194">10,000.00</span></span></td>
<td><span data-ttu-id="18e78-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-196">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-196">CC099</span></span></td>
<td><span data-ttu-id="18e78-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-197">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-198">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-198">10001</span></span></td>
<td><span data-ttu-id="18e78-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-199">Electricity</span></span></td>
<td><span data-ttu-id="18e78-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="18e78-200">Unclassified</span></span></td>
<td><span data-ttu-id="18e78-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-201">-10,000.00</span></span></td>
<td><span data-ttu-id="18e78-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-203">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-203">CC099</span></span></td>
<td><span data-ttu-id="18e78-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-204">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-205">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-205">10001</span></span></td>
<td><span data-ttu-id="18e78-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-206">Electricity</span></span></td>
<td><span data-ttu-id="18e78-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-207">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-208">1,000.00</span></span></td>
<td><span data-ttu-id="18e78-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-210">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-210">CC099</span></span></td>
<td><span data-ttu-id="18e78-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-211">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-212">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-212">10001</span></span></td>
<td><span data-ttu-id="18e78-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-213">Electricity</span></span></td>
<td><span data-ttu-id="18e78-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-214">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="18e78-215">9,000.00</span></span></td>
<td><span data-ttu-id="18e78-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="18e78-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="18e78-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="18e78-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="18e78-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="18e78-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="18e78-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="18e78-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="18e78-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="18e78-221">Define the cost distribution rule</span></span>

<span data-ttu-id="18e78-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="18e78-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="18e78-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="18e78-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="18e78-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="18e78-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="18e78-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="18e78-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="18e78-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="18e78-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="18e78-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="18e78-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-228">Cost object</span></span></th>
<th><span data-ttu-id="18e78-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="18e78-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-230">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-230">CC001</span></span></td>
<td><span data-ttu-id="18e78-231">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-231">HR</span></span></td>
<td><span data-ttu-id="18e78-232">1 000</span><span class="sxs-lookup"><span data-stu-id="18e78-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-233">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-233">CC002</span></span></td>
<td><span data-ttu-id="18e78-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-234">Finance</span></span></td>
<td><span data-ttu-id="18e78-235">6,000</span><span class="sxs-lookup"><span data-stu-id="18e78-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-236">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-236">CC003</span></span></td>
<td><span data-ttu-id="18e78-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-237">Assembly</span></span></td>
<td><span data-ttu-id="18e78-238">0</span><span class="sxs-lookup"><span data-stu-id="18e78-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="18e78-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-240">Cost object</span></span></th>
<th><span data-ttu-id="18e78-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-241">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-242">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-244">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-244">CC001</span></span></td>
<td><span data-ttu-id="18e78-245">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-245">HR</span></span></td>
<td><span data-ttu-id="18e78-246">1 000</span><span class="sxs-lookup"><span data-stu-id="18e78-246">1,000</span></span></td>
<td><span data-ttu-id="18e78-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="18e78-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="18e78-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-249">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-249">CC002</span></span></td>
<td><span data-ttu-id="18e78-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-250">Finance</span></span></td>
<td><span data-ttu-id="18e78-251">6,000</span><span class="sxs-lookup"><span data-stu-id="18e78-251">6,000</span></span></td>
<td><span data-ttu-id="18e78-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="18e78-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="18e78-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-254">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-254">CC003</span></span></td>
<td><span data-ttu-id="18e78-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-255">Assembly</span></span></td>
<td><span data-ttu-id="18e78-256">0</span><span class="sxs-lookup"><span data-stu-id="18e78-256">0</span></span></td>
<td><span data-ttu-id="18e78-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="18e78-258">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="18e78-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="18e78-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="18e78-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-261">Cost object</span></span></th>
<th><span data-ttu-id="18e78-262">Formel</span><span class="sxs-lookup"><span data-stu-id="18e78-262">Formula</span></span></th>
<th><span data-ttu-id="18e78-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-263">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-264">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-266">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-266">CC001</span></span></td>
<td><span data-ttu-id="18e78-267">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-267">HR</span></span></td>
<td><span data-ttu-id="18e78-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="18e78-269">1</span><span class="sxs-lookup"><span data-stu-id="18e78-269">1</span></span></td>
<td><span data-ttu-id="18e78-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="18e78-271">500.00</span><span class="sxs-lookup"><span data-stu-id="18e78-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-272">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-272">CC002</span></span></td>
<td><span data-ttu-id="18e78-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-273">Finance</span></span></td>
<td><span data-ttu-id="18e78-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="18e78-275">1</span><span class="sxs-lookup"><span data-stu-id="18e78-275">1</span></span></td>
<td><span data-ttu-id="18e78-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="18e78-277">500.00</span><span class="sxs-lookup"><span data-stu-id="18e78-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-278">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-278">CC003</span></span></td>
<td><span data-ttu-id="18e78-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-279">Assembly</span></span></td>
<td><span data-ttu-id="18e78-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="18e78-281">0</span><span class="sxs-lookup"><span data-stu-id="18e78-281">0</span></span></td>
<td><span data-ttu-id="18e78-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="18e78-283">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="18e78-284">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-285">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-285">Journal</span></span></th>
<th><span data-ttu-id="18e78-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="18e78-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="18e78-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="18e78-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="18e78-288">version</span><span class="sxs-lookup"><span data-stu-id="18e78-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-289">00002</span><span class="sxs-lookup"><span data-stu-id="18e78-289">00002</span></span></td>
<td><span data-ttu-id="18e78-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="18e78-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="18e78-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="18e78-291">Fiscal</span></span></td>
<td><span data-ttu-id="18e78-292">2017</span><span class="sxs-lookup"><span data-stu-id="18e78-292">2017</span></span></td>
<td><span data-ttu-id="18e78-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-293">Period 1</span></span></td>
<td><span data-ttu-id="18e78-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="18e78-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="18e78-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-298">Cost element</span></span></th>
<th><span data-ttu-id="18e78-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-299">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-302">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-302">CC099</span></span></td>
<td><span data-ttu-id="18e78-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-303">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-304">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-304">10001</span></span></td>
<td><span data-ttu-id="18e78-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-305">Electricity</span></span></td>
<td><span data-ttu-id="18e78-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-306">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-309">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-309">CC099</span></span></td>
<td><span data-ttu-id="18e78-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-310">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-311">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-311">10001</span></span></td>
<td><span data-ttu-id="18e78-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-312">Electricity</span></span></td>
<td><span data-ttu-id="18e78-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-313">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="18e78-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="18e78-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="18e78-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-317">Cost element</span></span></th>
<th><span data-ttu-id="18e78-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-318">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-319">Amount</span></span></th>
<th><span data-ttu-id="18e78-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-321">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-321">CC099</span></span></td>
<td><span data-ttu-id="18e78-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-322">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-323">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-323">10001</span></span></td>
<td><span data-ttu-id="18e78-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-324">Electricity</span></span></td>
<td><span data-ttu-id="18e78-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-325">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-326">-1,000.00</span></span></td>
<td><span data-ttu-id="18e78-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-328">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-328">CC001</span></span></td>
<td><span data-ttu-id="18e78-329">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-329">HR</span></span></td>
<td><span data-ttu-id="18e78-330">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-330">10001</span></span></td>
<td><span data-ttu-id="18e78-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-331">Electricity</span></span></td>
<td><span data-ttu-id="18e78-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-332">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-333">500.00</span><span class="sxs-lookup"><span data-stu-id="18e78-333">500.00</span></span></td>
<td><span data-ttu-id="18e78-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-335">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-335">CC002</span></span></td>
<td><span data-ttu-id="18e78-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-336">Finance</span></span></td>
<td><span data-ttu-id="18e78-337">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-337">10001</span></span></td>
<td><span data-ttu-id="18e78-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-338">Electricity</span></span></td>
<td><span data-ttu-id="18e78-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-339">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-340">500.00</span><span class="sxs-lookup"><span data-stu-id="18e78-340">500.00</span></span></td>
<td><span data-ttu-id="18e78-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-342">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-342">CC099</span></span></td>
<td><span data-ttu-id="18e78-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="18e78-343">Default cost center</span></span></td>
<td><span data-ttu-id="18e78-344">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-344">10001</span></span></td>
<td><span data-ttu-id="18e78-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-345">Electricity</span></span></td>
<td><span data-ttu-id="18e78-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-346">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="18e78-347">-9,000.00</span></span></td>
<td><span data-ttu-id="18e78-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-349">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-349">CC001</span></span></td>
<td><span data-ttu-id="18e78-350">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-350">HR</span></span></td>
<td><span data-ttu-id="18e78-351">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-351">10001</span></span></td>
<td><span data-ttu-id="18e78-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-352">Electricity</span></span></td>
<td><span data-ttu-id="18e78-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-353">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="18e78-354">1,285.71</span></span></td>
<td><span data-ttu-id="18e78-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-356">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-356">CC002</span></span></td>
<td><span data-ttu-id="18e78-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-357">Finance</span></span></td>
<td><span data-ttu-id="18e78-358">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-358">10001</span></span></td>
<td><span data-ttu-id="18e78-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-359">Electricity</span></span></td>
<td><span data-ttu-id="18e78-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-360">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="18e78-361">7,714.29</span></span></td>
<td><span data-ttu-id="18e78-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="18e78-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="18e78-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="18e78-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="18e78-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="18e78-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="18e78-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-367">Define the overhead rate</span></span>

<span data-ttu-id="18e78-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="18e78-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="18e78-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-370">Cost object</span></span></th>
<th><span data-ttu-id="18e78-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="18e78-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-372">Proj 1</span></span></td>
<td><span data-ttu-id="18e78-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-373">Project 1</span></span></td>
<td><span data-ttu-id="18e78-374">3</span><span class="sxs-lookup"><span data-stu-id="18e78-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-375">Proj 2</span></span></td>
<td><span data-ttu-id="18e78-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-376">Project 2</span></span></td>
<td><span data-ttu-id="18e78-377">1</span><span class="sxs-lookup"><span data-stu-id="18e78-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="18e78-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-379">Cost object</span></span></th>
<th><span data-ttu-id="18e78-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-380">Cost element</span></span></th>
<th><span data-ttu-id="18e78-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-381">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="18e78-382">Units</span></span></th>
<th><span data-ttu-id="18e78-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="18e78-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-384">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-384">CC001</span></span></td>
<td><span data-ttu-id="18e78-385">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-385">HR</span></span></td>
<td><span data-ttu-id="18e78-386">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-386">10001</span></span></td>
<td><span data-ttu-id="18e78-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-387">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-388">1</span><span class="sxs-lookup"><span data-stu-id="18e78-388">1</span></span></td>
<td><span data-ttu-id="18e78-389">10</span><span class="sxs-lookup"><span data-stu-id="18e78-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="18e78-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-391">Cost object</span></span></th>
<th><span data-ttu-id="18e78-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-392">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-393">Cost element</span></span></th>
<th><span data-ttu-id="18e78-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-394">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-396">Proj 1</span></span></td>
<td><span data-ttu-id="18e78-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-397">Project 1</span></span></td>
<td><span data-ttu-id="18e78-398">3</span><span class="sxs-lookup"><span data-stu-id="18e78-398">3</span></span></td>
<td><span data-ttu-id="18e78-399">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-399">10001</span></span></td>
<td><span data-ttu-id="18e78-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="18e78-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="18e78-401">30,00</span><span class="sxs-lookup"><span data-stu-id="18e78-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-402">Proj 2</span></span></td>
<td><span data-ttu-id="18e78-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-403">Project 2</span></span></td>
<td><span data-ttu-id="18e78-404">1</span><span class="sxs-lookup"><span data-stu-id="18e78-404">1</span></span></td>
<td><span data-ttu-id="18e78-405">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-405">10001</span></span></td>
<td><span data-ttu-id="18e78-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="18e78-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="18e78-407">10,00</span><span class="sxs-lookup"><span data-stu-id="18e78-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="18e78-408">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-409">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-409">Journal</span></span></th>
<th><span data-ttu-id="18e78-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="18e78-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="18e78-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="18e78-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="18e78-412">version</span><span class="sxs-lookup"><span data-stu-id="18e78-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-413">00003</span><span class="sxs-lookup"><span data-stu-id="18e78-413">00003</span></span></td>
<td><span data-ttu-id="18e78-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="18e78-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="18e78-415">Fiscal</span></span></td>
<td><span data-ttu-id="18e78-416">2017</span><span class="sxs-lookup"><span data-stu-id="18e78-416">2017</span></span></td>
<td><span data-ttu-id="18e78-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-417">Period 1</span></span></td>
<td><span data-ttu-id="18e78-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="18e78-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="18e78-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-421">Cost object</span></span></th>
<th><span data-ttu-id="18e78-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-424">Proj 1</span></span></td>
<td><span data-ttu-id="18e78-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="18e78-426">3,00</span><span class="sxs-lookup"><span data-stu-id="18e78-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-428">Proj 2</span></span></td>
<td><span data-ttu-id="18e78-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="18e78-430">1,00</span><span class="sxs-lookup"><span data-stu-id="18e78-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="18e78-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="18e78-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-433">Cost element</span></span></th>
<th><span data-ttu-id="18e78-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-434">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-435">Amount</span></span></th>
<th><span data-ttu-id="18e78-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="18e78-437">CC0001</span></span></td>
<td><span data-ttu-id="18e78-438">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-438">HR</span></span></td>
<td><span data-ttu-id="18e78-439">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-439">10001</span></span></td>
<td><span data-ttu-id="18e78-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-440">Electricity</span></span></td>
<td><span data-ttu-id="18e78-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-441">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="18e78-442">-30.00</span></span></td>
<td><span data-ttu-id="18e78-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-444">Proj 1</span></span></td>
<td><span data-ttu-id="18e78-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="18e78-446">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-446">10001</span></span></td>
<td><span data-ttu-id="18e78-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-447">Electricity</span></span></td>
<td><span data-ttu-id="18e78-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-448">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-449">30,00</span><span class="sxs-lookup"><span data-stu-id="18e78-449">30.00</span></span></td>
<td><span data-ttu-id="18e78-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-451">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-451">CC001</span></span></td>
<td><span data-ttu-id="18e78-452">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-452">HR</span></span></td>
<td><span data-ttu-id="18e78-453">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-453">10001</span></span></td>
<td><span data-ttu-id="18e78-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-454">Electricity</span></span></td>
<td><span data-ttu-id="18e78-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-455">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="18e78-456">-10.00</span></span></td>
<td><span data-ttu-id="18e78-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-458">Proj 2</span></span></td>
<td><span data-ttu-id="18e78-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="18e78-460">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-460">10001</span></span></td>
<td><span data-ttu-id="18e78-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-461">Electricity</span></span></td>
<td><span data-ttu-id="18e78-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-462">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-463">10,00</span><span class="sxs-lookup"><span data-stu-id="18e78-463">10.00</span></span></td>
<td><span data-ttu-id="18e78-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="18e78-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="18e78-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="18e78-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="18e78-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="18e78-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="18e78-468">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="18e78-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="18e78-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="18e78-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="18e78-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="18e78-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="18e78-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="18e78-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="18e78-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="18e78-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="18e78-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="18e78-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="18e78-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="18e78-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="18e78-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="18e78-475">Define the cost allocation</span></span>

<span data-ttu-id="18e78-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="18e78-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="18e78-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="18e78-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="18e78-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-479">Cost object</span></span></th>
<th><span data-ttu-id="18e78-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="18e78-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-481">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-481">CC002</span></span></td>
<td><span data-ttu-id="18e78-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-482">Finance</span></span></td>
<td><span data-ttu-id="18e78-483">35</span><span class="sxs-lookup"><span data-stu-id="18e78-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-484">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-484">CC003</span></span></td>
<td><span data-ttu-id="18e78-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-485">Assembly</span></span></td>
<td><span data-ttu-id="18e78-486">55</span><span class="sxs-lookup"><span data-stu-id="18e78-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-487">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-487">CC004</span></span></td>
<td><span data-ttu-id="18e78-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-488">Packaging</span></span></td>
<td><span data-ttu-id="18e78-489">10</span><span class="sxs-lookup"><span data-stu-id="18e78-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="18e78-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="18e78-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-492">Cost object</span></span></th>
<th><span data-ttu-id="18e78-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="18e78-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-494">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-494">CC003</span></span></td>
<td><span data-ttu-id="18e78-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-495">Assembly</span></span></td>
<td><span data-ttu-id="18e78-496">65</span><span class="sxs-lookup"><span data-stu-id="18e78-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-497">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-497">CC004</span></span></td>
<td><span data-ttu-id="18e78-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-498">Packaging</span></span></td>
<td><span data-ttu-id="18e78-499">35</span><span class="sxs-lookup"><span data-stu-id="18e78-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="18e78-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="18e78-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-502">Cost object</span></span></th>
<th><span data-ttu-id="18e78-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="18e78-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-504">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-505">Product 1</span></span></td>
<td><span data-ttu-id="18e78-506">60</span><span class="sxs-lookup"><span data-stu-id="18e78-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-507">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-508">Product 2</span></span></td>
<td><span data-ttu-id="18e78-509">20</span><span class="sxs-lookup"><span data-stu-id="18e78-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="18e78-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="18e78-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="18e78-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-512">Cost object</span></span></th>
<th><span data-ttu-id="18e78-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="18e78-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-514">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-515">Product 1</span></span></td>
<td><span data-ttu-id="18e78-516">80</span><span class="sxs-lookup"><span data-stu-id="18e78-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-517">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-518">Product 2</span></span></td>
<td><span data-ttu-id="18e78-519">15</span><span class="sxs-lookup"><span data-stu-id="18e78-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="18e78-520">I Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="18e78-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="18e78-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="18e78-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="18e78-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="18e78-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-523">Cost object</span></span></th>
<th><span data-ttu-id="18e78-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-524">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-525">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-526">Amount</span></span></th>
<th><span data-ttu-id="18e78-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-528">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-528">CC002</span></span></td>
<td><span data-ttu-id="18e78-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-529">Finance</span></span></td>
<td><span data-ttu-id="18e78-530">35</span><span class="sxs-lookup"><span data-stu-id="18e78-530">35</span></span></td>
<td><span data-ttu-id="18e78-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="18e78-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="18e78-532">175.00</span><span class="sxs-lookup"><span data-stu-id="18e78-532">175.00</span></span></td>
<td><span data-ttu-id="18e78-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-534">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-534">CC003</span></span></td>
<td><span data-ttu-id="18e78-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-535">Assembly</span></span></td>
<td><span data-ttu-id="18e78-536">55</span><span class="sxs-lookup"><span data-stu-id="18e78-536">55</span></span></td>
<td><span data-ttu-id="18e78-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="18e78-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="18e78-538">275.00</span><span class="sxs-lookup"><span data-stu-id="18e78-538">275.00</span></span></td>
<td><span data-ttu-id="18e78-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-540">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-540">CC004</span></span></td>
<td><span data-ttu-id="18e78-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-541">Packaging</span></span></td>
<td><span data-ttu-id="18e78-542">10</span><span class="sxs-lookup"><span data-stu-id="18e78-542">10</span></span></td>
<td><span data-ttu-id="18e78-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="18e78-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="18e78-544">50,00</span><span class="sxs-lookup"><span data-stu-id="18e78-544">50.00</span></span></td>
<td><span data-ttu-id="18e78-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-546">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-546">CC002</span></span></td>
<td><span data-ttu-id="18e78-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-547">Finance</span></span></td>
<td><span data-ttu-id="18e78-548">35</span><span class="sxs-lookup"><span data-stu-id="18e78-548">35</span></span></td>
<td><span data-ttu-id="18e78-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="18e78-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="18e78-550">436.00</span><span class="sxs-lookup"><span data-stu-id="18e78-550">436.00</span></span></td>
<td><span data-ttu-id="18e78-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-552">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-552">CC003</span></span></td>
<td><span data-ttu-id="18e78-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-553">Assembly</span></span></td>
<td><span data-ttu-id="18e78-554">55</span><span class="sxs-lookup"><span data-stu-id="18e78-554">55</span></span></td>
<td><span data-ttu-id="18e78-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="18e78-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="18e78-556">685.14</span><span class="sxs-lookup"><span data-stu-id="18e78-556">685.14</span></span></td>
<td><span data-ttu-id="18e78-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-558">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-558">CC004</span></span></td>
<td><span data-ttu-id="18e78-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-559">Packaging</span></span></td>
<td><span data-ttu-id="18e78-560">10</span><span class="sxs-lookup"><span data-stu-id="18e78-560">10</span></span></td>
<td><span data-ttu-id="18e78-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="18e78-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="18e78-562">124.57</span><span class="sxs-lookup"><span data-stu-id="18e78-562">124.57</span></span></td>
<td><span data-ttu-id="18e78-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="18e78-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-565">Cost object</span></span></th>
<th><span data-ttu-id="18e78-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-566">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-567">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-568">Amount</span></span></th>
<th><span data-ttu-id="18e78-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-570">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-570">CC003</span></span></td>
<td><span data-ttu-id="18e78-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-571">Assembly</span></span></td>
<td><span data-ttu-id="18e78-572">65</span><span class="sxs-lookup"><span data-stu-id="18e78-572">65</span></span></td>
<td><span data-ttu-id="18e78-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="18e78-574">438.75</span><span class="sxs-lookup"><span data-stu-id="18e78-574">438.75</span></span></td>
<td><span data-ttu-id="18e78-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-576">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-576">CC004</span></span></td>
<td><span data-ttu-id="18e78-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-577">Packaging</span></span></td>
<td><span data-ttu-id="18e78-578">35</span><span class="sxs-lookup"><span data-stu-id="18e78-578">35</span></span></td>
<td><span data-ttu-id="18e78-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="18e78-580">236.25</span><span class="sxs-lookup"><span data-stu-id="18e78-580">236.25</span></span></td>
<td><span data-ttu-id="18e78-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-582">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-582">CC003</span></span></td>
<td><span data-ttu-id="18e78-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-583">Assembly</span></span></td>
<td><span data-ttu-id="18e78-584">65</span><span class="sxs-lookup"><span data-stu-id="18e78-584">65</span></span></td>
<td><span data-ttu-id="18e78-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="18e78-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="18e78-586">5,297.69</span></span></td>
<td><span data-ttu-id="18e78-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-588">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-588">CC004</span></span></td>
<td><span data-ttu-id="18e78-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-589">Packaging</span></span></td>
<td><span data-ttu-id="18e78-590">35</span><span class="sxs-lookup"><span data-stu-id="18e78-590">35</span></span></td>
<td><span data-ttu-id="18e78-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="18e78-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="18e78-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="18e78-592">2,852.60</span></span></td>
<td><span data-ttu-id="18e78-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="18e78-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-595">Cost object</span></span></th>
<th><span data-ttu-id="18e78-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-596">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-597">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-598">Amount</span></span></th>
<th><span data-ttu-id="18e78-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-600">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-601">Product 1</span></span></td>
<td><span data-ttu-id="18e78-602">60</span><span class="sxs-lookup"><span data-stu-id="18e78-602">60</span></span></td>
<td><span data-ttu-id="18e78-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="18e78-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="18e78-604">535.31</span><span class="sxs-lookup"><span data-stu-id="18e78-604">535.31</span></span></td>
<td><span data-ttu-id="18e78-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-606">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-607">Product 2</span></span></td>
<td><span data-ttu-id="18e78-608">20</span><span class="sxs-lookup"><span data-stu-id="18e78-608">20</span></span></td>
<td><span data-ttu-id="18e78-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="18e78-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="18e78-610">178.44</span><span class="sxs-lookup"><span data-stu-id="18e78-610">178.44</span></span></td>
<td><span data-ttu-id="18e78-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-612">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-613">Product 1</span></span></td>
<td><span data-ttu-id="18e78-614">60</span><span class="sxs-lookup"><span data-stu-id="18e78-614">60</span></span></td>
<td><span data-ttu-id="18e78-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="18e78-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="18e78-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="18e78-616">4,487.12</span></span></td>
<td><span data-ttu-id="18e78-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-618">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-619">Product 2</span></span></td>
<td><span data-ttu-id="18e78-620">20</span><span class="sxs-lookup"><span data-stu-id="18e78-620">20</span></span></td>
<td><span data-ttu-id="18e78-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="18e78-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="18e78-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="18e78-622">1,495.71</span></span></td>
<td><span data-ttu-id="18e78-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="18e78-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="18e78-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-625">Cost object</span></span></th>
<th><span data-ttu-id="18e78-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="18e78-626">Magnitude</span></span></th>
<th><span data-ttu-id="18e78-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="18e78-627">Allocation factor</span></span></th>
<th><span data-ttu-id="18e78-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-628">Amount</span></span></th>
<th><span data-ttu-id="18e78-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-630">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-631">Product 1</span></span></td>
<td><span data-ttu-id="18e78-632">80</span><span class="sxs-lookup"><span data-stu-id="18e78-632">80</span></span></td>
<td><span data-ttu-id="18e78-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="18e78-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="18e78-634">241.05</span><span class="sxs-lookup"><span data-stu-id="18e78-634">241.05</span></span></td>
<td><span data-ttu-id="18e78-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-636">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-637">Product 2</span></span></td>
<td><span data-ttu-id="18e78-638">15</span><span class="sxs-lookup"><span data-stu-id="18e78-638">15</span></span></td>
<td><span data-ttu-id="18e78-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="18e78-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="18e78-640">45.20</span><span class="sxs-lookup"><span data-stu-id="18e78-640">45.20</span></span></td>
<td><span data-ttu-id="18e78-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-642">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-643">Product 1</span></span></td>
<td><span data-ttu-id="18e78-644">80</span><span class="sxs-lookup"><span data-stu-id="18e78-644">80</span></span></td>
<td><span data-ttu-id="18e78-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="18e78-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="18e78-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="18e78-646">2,507.09</span></span></td>
<td><span data-ttu-id="18e78-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-648">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-649">Product 2</span></span></td>
<td><span data-ttu-id="18e78-650">15</span><span class="sxs-lookup"><span data-stu-id="18e78-650">15</span></span></td>
<td><span data-ttu-id="18e78-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="18e78-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="18e78-652">470.08</span><span class="sxs-lookup"><span data-stu-id="18e78-652">470.08</span></span></td>
<td><span data-ttu-id="18e78-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="18e78-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="18e78-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-655">Journal</span><span class="sxs-lookup"><span data-stu-id="18e78-655">Journal</span></span></th>
<th><span data-ttu-id="18e78-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="18e78-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="18e78-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="18e78-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="18e78-658">version</span><span class="sxs-lookup"><span data-stu-id="18e78-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-659">00004</span><span class="sxs-lookup"><span data-stu-id="18e78-659">00004</span></span></td>
<td><span data-ttu-id="18e78-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="18e78-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="18e78-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="18e78-661">Fiscal</span></span></td>
<td><span data-ttu-id="18e78-662">2017</span><span class="sxs-lookup"><span data-stu-id="18e78-662">2017</span></span></td>
<td><span data-ttu-id="18e78-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-663">Period 1</span></span></td>
<td><span data-ttu-id="18e78-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="18e78-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="18e78-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="18e78-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18e78-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-668">Cost element</span></span></th>
<th><span data-ttu-id="18e78-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-669">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-672">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-672">CC001</span></span></td>
<td><span data-ttu-id="18e78-673">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-673">HR</span></span></td>
<td><span data-ttu-id="18e78-674">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-674">10001</span></span></td>
<td><span data-ttu-id="18e78-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-675">Electricity</span></span></td>
<td><span data-ttu-id="18e78-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-676">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-677">500.00</span><span class="sxs-lookup"><span data-stu-id="18e78-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-679">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-679">CC001</span></span></td>
<td><span data-ttu-id="18e78-680">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-680">HR</span></span></td>
<td><span data-ttu-id="18e78-681">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-681">10001</span></span></td>
<td><span data-ttu-id="18e78-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-682">Electricity</span></span></td>
<td><span data-ttu-id="18e78-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-683">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="18e78-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-686">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-686">CC002</span></span></td>
<td><span data-ttu-id="18e78-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-687">Finance</span></span></td>
<td><span data-ttu-id="18e78-688">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-688">10001</span></span></td>
<td><span data-ttu-id="18e78-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-689">Electricity</span></span></td>
<td><span data-ttu-id="18e78-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-690">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-691">675.00</span><span class="sxs-lookup"><span data-stu-id="18e78-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-693">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-693">CC002</span></span></td>
<td><span data-ttu-id="18e78-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-694">Finance</span></span></td>
<td><span data-ttu-id="18e78-695">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-695">10001</span></span></td>
<td><span data-ttu-id="18e78-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-696">Electricity</span></span></td>
<td><span data-ttu-id="18e78-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-697">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="18e78-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-700">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-700">CC003</span></span></td>
<td><span data-ttu-id="18e78-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-701">Assembly</span></span></td>
<td><span data-ttu-id="18e78-702">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-702">10001</span></span></td>
<td><span data-ttu-id="18e78-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-703">Electricity</span></span></td>
<td><span data-ttu-id="18e78-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-704">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-705">713.75</span><span class="sxs-lookup"><span data-stu-id="18e78-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-707">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-707">CC003</span></span></td>
<td><span data-ttu-id="18e78-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-708">Assembly</span></span></td>
<td><span data-ttu-id="18e78-709">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-709">10001</span></span></td>
<td><span data-ttu-id="18e78-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-710">Electricity</span></span></td>
<td><span data-ttu-id="18e78-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-711">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="18e78-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-714">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-714">CC003</span></span></td>
<td><span data-ttu-id="18e78-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-715">Packaging</span></span></td>
<td><span data-ttu-id="18e78-716">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-716">10001</span></span></td>
<td><span data-ttu-id="18e78-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-717">Electricity</span></span></td>
<td><span data-ttu-id="18e78-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-718">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-719">286.25</span><span class="sxs-lookup"><span data-stu-id="18e78-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-721">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-721">CC003</span></span></td>
<td><span data-ttu-id="18e78-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-722">Packaging</span></span></td>
<td><span data-ttu-id="18e78-723">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-723">10001</span></span></td>
<td><span data-ttu-id="18e78-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-724">Electricity</span></span></td>
<td><span data-ttu-id="18e78-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-725">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="18e78-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-728">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-729">Product 1</span></span></td>
<td><span data-ttu-id="18e78-730">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-730">10001</span></span></td>
<td><span data-ttu-id="18e78-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-731">Electricity</span></span></td>
<td><span data-ttu-id="18e78-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-732">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-733">776.36</span><span class="sxs-lookup"><span data-stu-id="18e78-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-735">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-736">Product 1</span></span></td>
<td><span data-ttu-id="18e78-737">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-737">10001</span></span></td>
<td><span data-ttu-id="18e78-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-738">Electricity</span></span></td>
<td><span data-ttu-id="18e78-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-739">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="18e78-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-742">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-743">Product 1</span></span></td>
<td><span data-ttu-id="18e78-744">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-744">10001</span></span></td>
<td><span data-ttu-id="18e78-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-745">Electricity</span></span></td>
<td><span data-ttu-id="18e78-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-746">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-747">223.64</span><span class="sxs-lookup"><span data-stu-id="18e78-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="18e78-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-749">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-750">Product 1</span></span></td>
<td><span data-ttu-id="18e78-751">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-751">10001</span></span></td>
<td><span data-ttu-id="18e78-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-752">Electricity</span></span></td>
<td><span data-ttu-id="18e78-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-753">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="18e78-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="18e78-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="18e78-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="18e78-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="18e78-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-757">Cost element</span></span></th>
<th><span data-ttu-id="18e78-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="18e78-758">Cost behavior</span></span></th>
<th><span data-ttu-id="18e78-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="18e78-759">Amount</span></span></th>
<th><span data-ttu-id="18e78-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="18e78-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18e78-761">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-761">CC001</span></span></td>
<td><span data-ttu-id="18e78-762">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-762">HR</span></span></td>
<td><span data-ttu-id="18e78-763">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-763">10001</span></span></td>
<td><span data-ttu-id="18e78-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-764">Electricity</span></span></td>
<td><span data-ttu-id="18e78-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-765">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="18e78-766">-500.00</span></span></td>
<td><span data-ttu-id="18e78-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-768">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-768">CC002</span></span></td>
<td><span data-ttu-id="18e78-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-769">Finance</span></span></td>
<td><span data-ttu-id="18e78-770">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-770">10001</span></span></td>
<td><span data-ttu-id="18e78-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-771">Electricity</span></span></td>
<td><span data-ttu-id="18e78-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-772">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-773">175.00</span><span class="sxs-lookup"><span data-stu-id="18e78-773">175.00</span></span></td>
<td><span data-ttu-id="18e78-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-775">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-775">CC003</span></span></td>
<td><span data-ttu-id="18e78-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-776">Assembly</span></span></td>
<td><span data-ttu-id="18e78-777">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-777">10001</span></span></td>
<td><span data-ttu-id="18e78-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-778">Electricity</span></span></td>
<td><span data-ttu-id="18e78-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-779">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-780">275.00</span><span class="sxs-lookup"><span data-stu-id="18e78-780">275.00</span></span></td>
<td><span data-ttu-id="18e78-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-782">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-782">CC004</span></span></td>
<td><span data-ttu-id="18e78-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-783">Packaging</span></span></td>
<td><span data-ttu-id="18e78-784">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-784">10001</span></span></td>
<td><span data-ttu-id="18e78-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-785">Electricity</span></span></td>
<td><span data-ttu-id="18e78-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-786">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-787">50,00</span><span class="sxs-lookup"><span data-stu-id="18e78-787">50,00</span></span></td>
<td><span data-ttu-id="18e78-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-789">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-789">CC001</span></span></td>
<td><span data-ttu-id="18e78-790">Personal</span><span class="sxs-lookup"><span data-stu-id="18e78-790">HR</span></span></td>
<td><span data-ttu-id="18e78-791">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-791">10001</span></span></td>
<td><span data-ttu-id="18e78-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-792">Electricity</span></span></td>
<td><span data-ttu-id="18e78-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-793">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="18e78-794">-1,245.71</span></span></td>
<td><span data-ttu-id="18e78-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-796">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-796">CC002</span></span></td>
<td><span data-ttu-id="18e78-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-797">Finance</span></span></td>
<td><span data-ttu-id="18e78-798">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-798">10001</span></span></td>
<td><span data-ttu-id="18e78-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-799">Electricity</span></span></td>
<td><span data-ttu-id="18e78-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-800">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-801">436.00</span><span class="sxs-lookup"><span data-stu-id="18e78-801">436.00</span></span></td>
<td><span data-ttu-id="18e78-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-803">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-803">CC003</span></span></td>
<td><span data-ttu-id="18e78-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-804">Assembly</span></span></td>
<td><span data-ttu-id="18e78-805">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-805">10001</span></span></td>
<td><span data-ttu-id="18e78-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-806">Electricity</span></span></td>
<td><span data-ttu-id="18e78-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-807">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-808">685.14</span><span class="sxs-lookup"><span data-stu-id="18e78-808">685.14</span></span></td>
<td><span data-ttu-id="18e78-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-810">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-810">CC004</span></span></td>
<td><span data-ttu-id="18e78-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-811">Packaging</span></span></td>
<td><span data-ttu-id="18e78-812">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-812">10001</span></span></td>
<td><span data-ttu-id="18e78-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-813">Electricity</span></span></td>
<td><span data-ttu-id="18e78-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-814">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-815">124.57</span><span class="sxs-lookup"><span data-stu-id="18e78-815">124.57</span></span></td>
<td><span data-ttu-id="18e78-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-817">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-817">CC002</span></span></td>
<td><span data-ttu-id="18e78-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-818">Finance</span></span></td>
<td><span data-ttu-id="18e78-819">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-819">10001</span></span></td>
<td><span data-ttu-id="18e78-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-820">Electricity</span></span></td>
<td><span data-ttu-id="18e78-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-821">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="18e78-822">-675.00</span></span></td>
<td><span data-ttu-id="18e78-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-824">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-824">CC003</span></span></td>
<td><span data-ttu-id="18e78-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-825">Assembly</span></span></td>
<td><span data-ttu-id="18e78-826">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-826">10001</span></span></td>
<td><span data-ttu-id="18e78-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-827">Electricity</span></span></td>
<td><span data-ttu-id="18e78-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-828">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-829">438.75</span><span class="sxs-lookup"><span data-stu-id="18e78-829">438.75</span></span></td>
<td><span data-ttu-id="18e78-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-831">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-831">CC004</span></span></td>
<td><span data-ttu-id="18e78-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-832">Packaging</span></span></td>
<td><span data-ttu-id="18e78-833">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-833">10001</span></span></td>
<td><span data-ttu-id="18e78-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-834">Electricity</span></span></td>
<td><span data-ttu-id="18e78-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-835">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-836">236.25</span><span class="sxs-lookup"><span data-stu-id="18e78-836">236.25</span></span></td>
<td><span data-ttu-id="18e78-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-838">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-838">CC002</span></span></td>
<td><span data-ttu-id="18e78-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="18e78-839">Finance</span></span></td>
<td><span data-ttu-id="18e78-840">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-840">10001</span></span></td>
<td><span data-ttu-id="18e78-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-841">Electricity</span></span></td>
<td><span data-ttu-id="18e78-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-842">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="18e78-843">-8,150.29</span></span></td>
<td><span data-ttu-id="18e78-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-845">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-845">CC003</span></span></td>
<td><span data-ttu-id="18e78-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-846">Assembly</span></span></td>
<td><span data-ttu-id="18e78-847">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-847">10001</span></span></td>
<td><span data-ttu-id="18e78-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-848">Electricity</span></span></td>
<td><span data-ttu-id="18e78-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-849">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="18e78-850">5,297.69</span></span></td>
<td><span data-ttu-id="18e78-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-852">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-852">CC004</span></span></td>
<td><span data-ttu-id="18e78-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="18e78-853">Packaging</span></span></td>
<td><span data-ttu-id="18e78-854">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-854">10001</span></span></td>
<td><span data-ttu-id="18e78-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-855">Electricity</span></span></td>
<td><span data-ttu-id="18e78-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-856">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="18e78-857">2,852.60</span></span></td>
<td><span data-ttu-id="18e78-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-859">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-859">CC003</span></span></td>
<td><span data-ttu-id="18e78-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-860">Assembly</span></span></td>
<td><span data-ttu-id="18e78-861">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-861">10001</span></span></td>
<td><span data-ttu-id="18e78-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-862">Electricity</span></span></td>
<td><span data-ttu-id="18e78-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-863">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="18e78-864">-713.75</span></span></td>
<td><span data-ttu-id="18e78-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-866">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-867">Product 1</span></span></td>
<td><span data-ttu-id="18e78-868">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-868">10001</span></span></td>
<td><span data-ttu-id="18e78-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-869">Electricity</span></span></td>
<td><span data-ttu-id="18e78-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-870">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-871">535.31</span><span class="sxs-lookup"><span data-stu-id="18e78-871">535.31</span></span></td>
<td><span data-ttu-id="18e78-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-873">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-874">Product 2</span></span></td>
<td><span data-ttu-id="18e78-875">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-875">10001</span></span></td>
<td><span data-ttu-id="18e78-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-876">Electricity</span></span></td>
<td><span data-ttu-id="18e78-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-877">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-878">178.44</span><span class="sxs-lookup"><span data-stu-id="18e78-878">178.44</span></span></td>
<td><span data-ttu-id="18e78-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-880">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-880">CC003</span></span></td>
<td><span data-ttu-id="18e78-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-881">Assembly</span></span></td>
<td><span data-ttu-id="18e78-882">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-882">10001</span></span></td>
<td><span data-ttu-id="18e78-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-883">Electricity</span></span></td>
<td><span data-ttu-id="18e78-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-884">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="18e78-885">-5,982.83</span></span></td>
<td><span data-ttu-id="18e78-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-887">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-888">Product 1</span></span></td>
<td><span data-ttu-id="18e78-889">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-889">10001</span></span></td>
<td><span data-ttu-id="18e78-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-890">Electricity</span></span></td>
<td><span data-ttu-id="18e78-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-891">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="18e78-892">4,487.12</span></span></td>
<td><span data-ttu-id="18e78-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-894">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-895">Product 2</span></span></td>
<td><span data-ttu-id="18e78-896">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-896">10001</span></span></td>
<td><span data-ttu-id="18e78-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-897">Electricity</span></span></td>
<td><span data-ttu-id="18e78-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-898">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="18e78-899">1,495.71</span></span></td>
<td><span data-ttu-id="18e78-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-901">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-901">CC003</span></span></td>
<td><span data-ttu-id="18e78-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-902">Assembly</span></span></td>
<td><span data-ttu-id="18e78-903">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-903">10001</span></span></td>
<td><span data-ttu-id="18e78-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-904">Electricity</span></span></td>
<td><span data-ttu-id="18e78-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-905">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="18e78-906">-286.25</span></span></td>
<td><span data-ttu-id="18e78-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-908">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-909">Product 1</span></span></td>
<td><span data-ttu-id="18e78-910">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-910">10001</span></span></td>
<td><span data-ttu-id="18e78-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-911">Electricity</span></span></td>
<td><span data-ttu-id="18e78-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-912">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-913">241.05</span><span class="sxs-lookup"><span data-stu-id="18e78-913">241.05</span></span></td>
<td><span data-ttu-id="18e78-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-915">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-916">Product 2</span></span></td>
<td><span data-ttu-id="18e78-917">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-917">10001</span></span></td>
<td><span data-ttu-id="18e78-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-918">Electricity</span></span></td>
<td><span data-ttu-id="18e78-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-919">Fixed cost</span></span></td>
<td><span data-ttu-id="18e78-920">45.20</span><span class="sxs-lookup"><span data-stu-id="18e78-920">45.20</span></span></td>
<td><span data-ttu-id="18e78-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-922">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-922">CC003</span></span></td>
<td><span data-ttu-id="18e78-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="18e78-923">Assembly</span></span></td>
<td><span data-ttu-id="18e78-924">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-924">10001</span></span></td>
<td><span data-ttu-id="18e78-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-925">Electricity</span></span></td>
<td><span data-ttu-id="18e78-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-926">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="18e78-927">-2,977.17</span></span></td>
<td><span data-ttu-id="18e78-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-929">Prod 1</span></span></td>
<td><span data-ttu-id="18e78-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="18e78-930">Product 1</span></span></td>
<td><span data-ttu-id="18e78-931">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-931">10001</span></span></td>
<td><span data-ttu-id="18e78-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-932">Electricity</span></span></td>
<td><span data-ttu-id="18e78-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-933">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="18e78-934">2,507.09</span></span></td>
<td><span data-ttu-id="18e78-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18e78-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-936">Prod 2</span></span></td>
<td><span data-ttu-id="18e78-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="18e78-937">Product 2</span></span></td>
<td><span data-ttu-id="18e78-938">10001</span><span class="sxs-lookup"><span data-stu-id="18e78-938">10001</span></span></td>
<td><span data-ttu-id="18e78-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-939">Electricity</span></span></td>
<td><span data-ttu-id="18e78-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-940">Variable cost</span></span></td>
<td><span data-ttu-id="18e78-941">470.08</span><span class="sxs-lookup"><span data-stu-id="18e78-941">470.08</span></span></td>
<td><span data-ttu-id="18e78-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="18e78-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="18e78-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="18e78-943">Conclusion</span></span>
<span data-ttu-id="18e78-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="18e78-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="18e78-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="18e78-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="18e78-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="18e78-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="18e78-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="18e78-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="18e78-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="18e78-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="18e78-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="18e78-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="18e78-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="18e78-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="18e78-951">CC099</span><span class="sxs-lookup"><span data-stu-id="18e78-951">CC099</span></span></th>
<th><span data-ttu-id="18e78-952">CC001</span><span class="sxs-lookup"><span data-stu-id="18e78-952">CC001</span></span></th>
<th><span data-ttu-id="18e78-953">CC002</span><span class="sxs-lookup"><span data-stu-id="18e78-953">CC002</span></span></th>
<th><span data-ttu-id="18e78-954">CC003</span><span class="sxs-lookup"><span data-stu-id="18e78-954">CC003</span></span></th>
<th><span data-ttu-id="18e78-955">CC004</span><span class="sxs-lookup"><span data-stu-id="18e78-955">CC004</span></span></th>
<th><span data-ttu-id="18e78-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="18e78-956">Proj 1</span></span></th>
<th><span data-ttu-id="18e78-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="18e78-957">Proj 2</span></span></th>
<th><span data-ttu-id="18e78-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="18e78-958">Prod 1</span></span></th>
<th><span data-ttu-id="18e78-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="18e78-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="18e78-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="18e78-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="18e78-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="18e78-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="18e78-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-971">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="18e78-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-973">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-974">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-975">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-976">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-977">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="18e78-978">776.36</span><span class="sxs-lookup"><span data-stu-id="18e78-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-979">223.64</span><span class="sxs-lookup"><span data-stu-id="18e78-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="18e78-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="18e78-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-982">000</span><span class="sxs-lookup"><span data-stu-id="18e78-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-983">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-984">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-985">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-986">0,00</span><span class="sxs-lookup"><span data-stu-id="18e78-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-987">30,00</span><span class="sxs-lookup"><span data-stu-id="18e78-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-988">10,00</span><span class="sxs-lookup"><span data-stu-id="18e78-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="18e78-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="18e78-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="18e78-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="18e78-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="18e78-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="18e78-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="18e78-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="18e78-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="18e78-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="18e78-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="18e78-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="18e78-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="18e78-996">Mer information finns i [Samlade kostnader](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="18e78-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



