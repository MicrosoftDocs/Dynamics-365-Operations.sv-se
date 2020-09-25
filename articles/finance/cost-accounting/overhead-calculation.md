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
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cc6ad48ef80aa01739129b59cc1133d0a1930f24
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759482"
---
# <a name="overhead-calculation"></a><span data-ttu-id="31b64-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="31b64-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31b64-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="31b64-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="31b64-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="31b64-105">Term definition</span></span>
---------------

<span data-ttu-id="31b64-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="31b64-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="31b64-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="31b64-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="31b64-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="31b64-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="31b64-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="31b64-109">Rent</span></span>
-   <span data-ttu-id="31b64-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-110">Electricity</span></span>
-   <span data-ttu-id="31b64-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="31b64-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="31b64-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="31b64-112">Overhead calculation overview</span></span>
<span data-ttu-id="31b64-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="31b64-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="31b64-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="31b64-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="31b64-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="31b64-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="31b64-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="31b64-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="31b64-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="31b64-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="31b64-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="31b64-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="31b64-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="31b64-119">Version type</span></span>
-   <span data-ttu-id="31b64-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="31b64-120">Date and time</span></span>
-   <span data-ttu-id="31b64-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="31b64-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="31b64-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="31b64-122">Fiscal year</span></span>
-   <span data-ttu-id="31b64-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="31b64-123">Fiscal period</span></span>

<span data-ttu-id="31b64-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="31b64-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="31b64-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="31b64-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="31b64-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="31b64-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="31b64-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="31b64-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="31b64-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="31b64-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="31b64-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="31b64-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="31b64-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="31b64-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="31b64-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="31b64-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="31b64-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="31b64-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="31b64-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="31b64-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="31b64-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="31b64-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="31b64-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="31b64-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="31b64-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="31b64-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="31b64-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="31b64-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="31b64-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="31b64-140">Main account</span></span></th>
<th><span data-ttu-id="31b64-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="31b64-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="31b64-143">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-143">CC099</span></span></td>
<td><span data-ttu-id="31b64-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-144">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-145">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-145">10001</span></span></td>
<td><span data-ttu-id="31b64-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-146">Electricity</span></span></td>
<td><span data-ttu-id="31b64-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="31b64-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="31b64-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="31b64-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="31b64-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="31b64-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="31b64-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="31b64-151">Define the cost behavior rule</span></span>

<span data-ttu-id="31b64-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="31b64-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="31b64-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="31b64-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="31b64-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="31b64-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="31b64-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="31b64-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="31b64-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="31b64-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="31b64-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="31b64-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="31b64-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="31b64-159">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-160">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-160">Journal</span></span></th>
<th><span data-ttu-id="31b64-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="31b64-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="31b64-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="31b64-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="31b64-163">version</span><span class="sxs-lookup"><span data-stu-id="31b64-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-164">00001</span><span class="sxs-lookup"><span data-stu-id="31b64-164">00001</span></span></td>
<td><span data-ttu-id="31b64-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="31b64-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="31b64-166">Fiscal</span></span></td>
<td><span data-ttu-id="31b64-167">2017</span><span class="sxs-lookup"><span data-stu-id="31b64-167">2017</span></span></td>
<td><span data-ttu-id="31b64-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-168">Period 1</span></span></td>
<td><span data-ttu-id="31b64-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="31b64-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="31b64-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-173">Cost element</span></span></th>
<th><span data-ttu-id="31b64-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-174">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="31b64-177">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-177">CC099</span></span></td>
<td><span data-ttu-id="31b64-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-178">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-179">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-179">10001</span></span></td>
<td><span data-ttu-id="31b64-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-180">Electricity</span></span></td>
<td><span data-ttu-id="31b64-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="31b64-181">Unclassified</span></span></td>
<td><span data-ttu-id="31b64-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="31b64-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="31b64-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-185">Cost element</span></span></th>
<th><span data-ttu-id="31b64-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-186">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-187">Amount</span></span></th>
<th><span data-ttu-id="31b64-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-189">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-189">CC099</span></span></td>
<td><span data-ttu-id="31b64-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-190">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-191">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-191">10001</span></span></td>
<td><span data-ttu-id="31b64-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-192">Electricity</span></span></td>
<td><span data-ttu-id="31b64-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="31b64-193">Unclassified</span></span></td>
<td><span data-ttu-id="31b64-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-194">10,000.00</span></span></td>
<td><span data-ttu-id="31b64-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-196">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-196">CC099</span></span></td>
<td><span data-ttu-id="31b64-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-197">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-198">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-198">10001</span></span></td>
<td><span data-ttu-id="31b64-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-199">Electricity</span></span></td>
<td><span data-ttu-id="31b64-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="31b64-200">Unclassified</span></span></td>
<td><span data-ttu-id="31b64-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-201">-10,000.00</span></span></td>
<td><span data-ttu-id="31b64-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-203">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-203">CC099</span></span></td>
<td><span data-ttu-id="31b64-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-204">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-205">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-205">10001</span></span></td>
<td><span data-ttu-id="31b64-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-206">Electricity</span></span></td>
<td><span data-ttu-id="31b64-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-207">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-208">1,000.00</span></span></td>
<td><span data-ttu-id="31b64-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-210">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-210">CC099</span></span></td>
<td><span data-ttu-id="31b64-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-211">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-212">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-212">10001</span></span></td>
<td><span data-ttu-id="31b64-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-213">Electricity</span></span></td>
<td><span data-ttu-id="31b64-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-214">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="31b64-215">9,000.00</span></span></td>
<td><span data-ttu-id="31b64-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="31b64-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="31b64-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="31b64-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="31b64-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="31b64-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="31b64-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="31b64-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="31b64-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="31b64-221">Define the cost distribution rule</span></span>

<span data-ttu-id="31b64-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="31b64-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="31b64-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="31b64-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="31b64-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="31b64-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="31b64-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="31b64-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="31b64-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="31b64-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="31b64-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="31b64-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-228">Cost object</span></span></th>
<th><span data-ttu-id="31b64-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="31b64-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-230">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-230">CC001</span></span></td>
<td><span data-ttu-id="31b64-231">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-231">HR</span></span></td>
<td><span data-ttu-id="31b64-232">1 000</span><span class="sxs-lookup"><span data-stu-id="31b64-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-233">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-233">CC002</span></span></td>
<td><span data-ttu-id="31b64-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-234">Finance</span></span></td>
<td><span data-ttu-id="31b64-235">6,000</span><span class="sxs-lookup"><span data-stu-id="31b64-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-236">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-236">CC003</span></span></td>
<td><span data-ttu-id="31b64-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-237">Assembly</span></span></td>
<td><span data-ttu-id="31b64-238">0</span><span class="sxs-lookup"><span data-stu-id="31b64-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="31b64-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-240">Cost object</span></span></th>
<th><span data-ttu-id="31b64-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-241">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-242">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-244">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-244">CC001</span></span></td>
<td><span data-ttu-id="31b64-245">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-245">HR</span></span></td>
<td><span data-ttu-id="31b64-246">1 000</span><span class="sxs-lookup"><span data-stu-id="31b64-246">1,000</span></span></td>
<td><span data-ttu-id="31b64-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="31b64-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="31b64-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-249">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-249">CC002</span></span></td>
<td><span data-ttu-id="31b64-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-250">Finance</span></span></td>
<td><span data-ttu-id="31b64-251">6,000</span><span class="sxs-lookup"><span data-stu-id="31b64-251">6,000</span></span></td>
<td><span data-ttu-id="31b64-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="31b64-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="31b64-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-254">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-254">CC003</span></span></td>
<td><span data-ttu-id="31b64-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-255">Assembly</span></span></td>
<td><span data-ttu-id="31b64-256">0</span><span class="sxs-lookup"><span data-stu-id="31b64-256">0</span></span></td>
<td><span data-ttu-id="31b64-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="31b64-258">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="31b64-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="31b64-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="31b64-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-261">Cost object</span></span></th>
<th><span data-ttu-id="31b64-262">Formel</span><span class="sxs-lookup"><span data-stu-id="31b64-262">Formula</span></span></th>
<th><span data-ttu-id="31b64-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-263">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-264">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-266">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-266">CC001</span></span></td>
<td><span data-ttu-id="31b64-267">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-267">HR</span></span></td>
<td><span data-ttu-id="31b64-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="31b64-269">1</span><span class="sxs-lookup"><span data-stu-id="31b64-269">1</span></span></td>
<td><span data-ttu-id="31b64-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="31b64-271">500.00</span><span class="sxs-lookup"><span data-stu-id="31b64-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-272">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-272">CC002</span></span></td>
<td><span data-ttu-id="31b64-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-273">Finance</span></span></td>
<td><span data-ttu-id="31b64-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="31b64-275">1</span><span class="sxs-lookup"><span data-stu-id="31b64-275">1</span></span></td>
<td><span data-ttu-id="31b64-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="31b64-277">500.00</span><span class="sxs-lookup"><span data-stu-id="31b64-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-278">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-278">CC003</span></span></td>
<td><span data-ttu-id="31b64-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-279">Assembly</span></span></td>
<td><span data-ttu-id="31b64-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="31b64-281">0</span><span class="sxs-lookup"><span data-stu-id="31b64-281">0</span></span></td>
<td><span data-ttu-id="31b64-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="31b64-283">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="31b64-284">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-285">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-285">Journal</span></span></th>
<th><span data-ttu-id="31b64-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="31b64-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="31b64-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="31b64-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="31b64-288">version</span><span class="sxs-lookup"><span data-stu-id="31b64-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-289">00002</span><span class="sxs-lookup"><span data-stu-id="31b64-289">00002</span></span></td>
<td><span data-ttu-id="31b64-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="31b64-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="31b64-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="31b64-291">Fiscal</span></span></td>
<td><span data-ttu-id="31b64-292">2017</span><span class="sxs-lookup"><span data-stu-id="31b64-292">2017</span></span></td>
<td><span data-ttu-id="31b64-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-293">Period 1</span></span></td>
<td><span data-ttu-id="31b64-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="31b64-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="31b64-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-298">Cost element</span></span></th>
<th><span data-ttu-id="31b64-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-299">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-302">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-302">CC099</span></span></td>
<td><span data-ttu-id="31b64-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-303">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-304">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-304">10001</span></span></td>
<td><span data-ttu-id="31b64-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-305">Electricity</span></span></td>
<td><span data-ttu-id="31b64-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-306">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-309">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-309">CC099</span></span></td>
<td><span data-ttu-id="31b64-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-310">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-311">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-311">10001</span></span></td>
<td><span data-ttu-id="31b64-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-312">Electricity</span></span></td>
<td><span data-ttu-id="31b64-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-313">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="31b64-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="31b64-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="31b64-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-317">Cost element</span></span></th>
<th><span data-ttu-id="31b64-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-318">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-319">Amount</span></span></th>
<th><span data-ttu-id="31b64-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-321">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-321">CC099</span></span></td>
<td><span data-ttu-id="31b64-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-322">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-323">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-323">10001</span></span></td>
<td><span data-ttu-id="31b64-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-324">Electricity</span></span></td>
<td><span data-ttu-id="31b64-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-325">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-326">-1,000.00</span></span></td>
<td><span data-ttu-id="31b64-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-328">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-328">CC001</span></span></td>
<td><span data-ttu-id="31b64-329">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-329">HR</span></span></td>
<td><span data-ttu-id="31b64-330">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-330">10001</span></span></td>
<td><span data-ttu-id="31b64-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-331">Electricity</span></span></td>
<td><span data-ttu-id="31b64-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-332">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-333">500.00</span><span class="sxs-lookup"><span data-stu-id="31b64-333">500.00</span></span></td>
<td><span data-ttu-id="31b64-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-335">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-335">CC002</span></span></td>
<td><span data-ttu-id="31b64-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-336">Finance</span></span></td>
<td><span data-ttu-id="31b64-337">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-337">10001</span></span></td>
<td><span data-ttu-id="31b64-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-338">Electricity</span></span></td>
<td><span data-ttu-id="31b64-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-339">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-340">500.00</span><span class="sxs-lookup"><span data-stu-id="31b64-340">500.00</span></span></td>
<td><span data-ttu-id="31b64-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-342">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-342">CC099</span></span></td>
<td><span data-ttu-id="31b64-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="31b64-343">Default cost center</span></span></td>
<td><span data-ttu-id="31b64-344">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-344">10001</span></span></td>
<td><span data-ttu-id="31b64-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-345">Electricity</span></span></td>
<td><span data-ttu-id="31b64-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-346">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="31b64-347">-9,000.00</span></span></td>
<td><span data-ttu-id="31b64-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-349">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-349">CC001</span></span></td>
<td><span data-ttu-id="31b64-350">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-350">HR</span></span></td>
<td><span data-ttu-id="31b64-351">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-351">10001</span></span></td>
<td><span data-ttu-id="31b64-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-352">Electricity</span></span></td>
<td><span data-ttu-id="31b64-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-353">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="31b64-354">1,285.71</span></span></td>
<td><span data-ttu-id="31b64-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-356">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-356">CC002</span></span></td>
<td><span data-ttu-id="31b64-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-357">Finance</span></span></td>
<td><span data-ttu-id="31b64-358">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-358">10001</span></span></td>
<td><span data-ttu-id="31b64-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-359">Electricity</span></span></td>
<td><span data-ttu-id="31b64-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-360">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="31b64-361">7,714.29</span></span></td>
<td><span data-ttu-id="31b64-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="31b64-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="31b64-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="31b64-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="31b64-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="31b64-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="31b64-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-367">Define the overhead rate</span></span>

<span data-ttu-id="31b64-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="31b64-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="31b64-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-370">Cost object</span></span></th>
<th><span data-ttu-id="31b64-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="31b64-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-372">Proj 1</span></span></td>
<td><span data-ttu-id="31b64-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-373">Project 1</span></span></td>
<td><span data-ttu-id="31b64-374">3</span><span class="sxs-lookup"><span data-stu-id="31b64-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-375">Proj 2</span></span></td>
<td><span data-ttu-id="31b64-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-376">Project 2</span></span></td>
<td><span data-ttu-id="31b64-377">1</span><span class="sxs-lookup"><span data-stu-id="31b64-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="31b64-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-379">Cost object</span></span></th>
<th><span data-ttu-id="31b64-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-380">Cost element</span></span></th>
<th><span data-ttu-id="31b64-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-381">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="31b64-382">Units</span></span></th>
<th><span data-ttu-id="31b64-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="31b64-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-384">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-384">CC001</span></span></td>
<td><span data-ttu-id="31b64-385">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-385">HR</span></span></td>
<td><span data-ttu-id="31b64-386">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-386">10001</span></span></td>
<td><span data-ttu-id="31b64-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-387">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-388">1</span><span class="sxs-lookup"><span data-stu-id="31b64-388">1</span></span></td>
<td><span data-ttu-id="31b64-389">10</span><span class="sxs-lookup"><span data-stu-id="31b64-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="31b64-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-391">Cost object</span></span></th>
<th><span data-ttu-id="31b64-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-392">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-393">Cost element</span></span></th>
<th><span data-ttu-id="31b64-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-394">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-396">Proj 1</span></span></td>
<td><span data-ttu-id="31b64-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-397">Project 1</span></span></td>
<td><span data-ttu-id="31b64-398">3</span><span class="sxs-lookup"><span data-stu-id="31b64-398">3</span></span></td>
<td><span data-ttu-id="31b64-399">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-399">10001</span></span></td>
<td><span data-ttu-id="31b64-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="31b64-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="31b64-401">30,00</span><span class="sxs-lookup"><span data-stu-id="31b64-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-402">Proj 2</span></span></td>
<td><span data-ttu-id="31b64-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-403">Project 2</span></span></td>
<td><span data-ttu-id="31b64-404">1</span><span class="sxs-lookup"><span data-stu-id="31b64-404">1</span></span></td>
<td><span data-ttu-id="31b64-405">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-405">10001</span></span></td>
<td><span data-ttu-id="31b64-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="31b64-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="31b64-407">10,00</span><span class="sxs-lookup"><span data-stu-id="31b64-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="31b64-408">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-409">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-409">Journal</span></span></th>
<th><span data-ttu-id="31b64-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="31b64-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="31b64-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="31b64-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="31b64-412">version</span><span class="sxs-lookup"><span data-stu-id="31b64-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-413">00003</span><span class="sxs-lookup"><span data-stu-id="31b64-413">00003</span></span></td>
<td><span data-ttu-id="31b64-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="31b64-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="31b64-415">Fiscal</span></span></td>
<td><span data-ttu-id="31b64-416">2017</span><span class="sxs-lookup"><span data-stu-id="31b64-416">2017</span></span></td>
<td><span data-ttu-id="31b64-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-417">Period 1</span></span></td>
<td><span data-ttu-id="31b64-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="31b64-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="31b64-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-421">Cost object</span></span></th>
<th><span data-ttu-id="31b64-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-424">Proj 1</span></span></td>
<td><span data-ttu-id="31b64-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="31b64-426">3,00</span><span class="sxs-lookup"><span data-stu-id="31b64-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-428">Proj 2</span></span></td>
<td><span data-ttu-id="31b64-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="31b64-430">1,00</span><span class="sxs-lookup"><span data-stu-id="31b64-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="31b64-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="31b64-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-433">Cost element</span></span></th>
<th><span data-ttu-id="31b64-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-434">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-435">Amount</span></span></th>
<th><span data-ttu-id="31b64-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="31b64-437">CC0001</span></span></td>
<td><span data-ttu-id="31b64-438">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-438">HR</span></span></td>
<td><span data-ttu-id="31b64-439">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-439">10001</span></span></td>
<td><span data-ttu-id="31b64-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-440">Electricity</span></span></td>
<td><span data-ttu-id="31b64-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-441">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="31b64-442">-30.00</span></span></td>
<td><span data-ttu-id="31b64-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-444">Proj 1</span></span></td>
<td><span data-ttu-id="31b64-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="31b64-446">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-446">10001</span></span></td>
<td><span data-ttu-id="31b64-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-447">Electricity</span></span></td>
<td><span data-ttu-id="31b64-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-448">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-449">30,00</span><span class="sxs-lookup"><span data-stu-id="31b64-449">30.00</span></span></td>
<td><span data-ttu-id="31b64-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-451">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-451">CC001</span></span></td>
<td><span data-ttu-id="31b64-452">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-452">HR</span></span></td>
<td><span data-ttu-id="31b64-453">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-453">10001</span></span></td>
<td><span data-ttu-id="31b64-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-454">Electricity</span></span></td>
<td><span data-ttu-id="31b64-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-455">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="31b64-456">-10.00</span></span></td>
<td><span data-ttu-id="31b64-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-458">Proj 2</span></span></td>
<td><span data-ttu-id="31b64-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="31b64-460">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-460">10001</span></span></td>
<td><span data-ttu-id="31b64-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-461">Electricity</span></span></td>
<td><span data-ttu-id="31b64-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-462">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-463">10,00</span><span class="sxs-lookup"><span data-stu-id="31b64-463">10.00</span></span></td>
<td><span data-ttu-id="31b64-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="31b64-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="31b64-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="31b64-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="31b64-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="31b64-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="31b64-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="31b64-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="31b64-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="31b64-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="31b64-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="31b64-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="31b64-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="31b64-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="31b64-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="31b64-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="31b64-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="31b64-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="31b64-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="31b64-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="31b64-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="31b64-475">Define the cost allocation</span></span>

<span data-ttu-id="31b64-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="31b64-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="31b64-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="31b64-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="31b64-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-479">Cost object</span></span></th>
<th><span data-ttu-id="31b64-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="31b64-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-481">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-481">CC002</span></span></td>
<td><span data-ttu-id="31b64-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-482">Finance</span></span></td>
<td><span data-ttu-id="31b64-483">35</span><span class="sxs-lookup"><span data-stu-id="31b64-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-484">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-484">CC003</span></span></td>
<td><span data-ttu-id="31b64-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-485">Assembly</span></span></td>
<td><span data-ttu-id="31b64-486">55</span><span class="sxs-lookup"><span data-stu-id="31b64-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-487">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-487">CC004</span></span></td>
<td><span data-ttu-id="31b64-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-488">Packaging</span></span></td>
<td><span data-ttu-id="31b64-489">10</span><span class="sxs-lookup"><span data-stu-id="31b64-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="31b64-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="31b64-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-492">Cost object</span></span></th>
<th><span data-ttu-id="31b64-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="31b64-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-494">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-494">CC003</span></span></td>
<td><span data-ttu-id="31b64-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-495">Assembly</span></span></td>
<td><span data-ttu-id="31b64-496">65</span><span class="sxs-lookup"><span data-stu-id="31b64-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-497">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-497">CC004</span></span></td>
<td><span data-ttu-id="31b64-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-498">Packaging</span></span></td>
<td><span data-ttu-id="31b64-499">35</span><span class="sxs-lookup"><span data-stu-id="31b64-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="31b64-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="31b64-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-502">Cost object</span></span></th>
<th><span data-ttu-id="31b64-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="31b64-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-504">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-505">Product 1</span></span></td>
<td><span data-ttu-id="31b64-506">60</span><span class="sxs-lookup"><span data-stu-id="31b64-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-507">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-508">Product 2</span></span></td>
<td><span data-ttu-id="31b64-509">20</span><span class="sxs-lookup"><span data-stu-id="31b64-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="31b64-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="31b64-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="31b64-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-512">Cost object</span></span></th>
<th><span data-ttu-id="31b64-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="31b64-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-514">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-515">Product 1</span></span></td>
<td><span data-ttu-id="31b64-516">80</span><span class="sxs-lookup"><span data-stu-id="31b64-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-517">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-518">Product 2</span></span></td>
<td><span data-ttu-id="31b64-519">15</span><span class="sxs-lookup"><span data-stu-id="31b64-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="31b64-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="31b64-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="31b64-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="31b64-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="31b64-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="31b64-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-523">Cost object</span></span></th>
<th><span data-ttu-id="31b64-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-524">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-525">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-526">Amount</span></span></th>
<th><span data-ttu-id="31b64-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-528">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-528">CC002</span></span></td>
<td><span data-ttu-id="31b64-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-529">Finance</span></span></td>
<td><span data-ttu-id="31b64-530">35</span><span class="sxs-lookup"><span data-stu-id="31b64-530">35</span></span></td>
<td><span data-ttu-id="31b64-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="31b64-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="31b64-532">175.00</span><span class="sxs-lookup"><span data-stu-id="31b64-532">175.00</span></span></td>
<td><span data-ttu-id="31b64-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-534">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-534">CC003</span></span></td>
<td><span data-ttu-id="31b64-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-535">Assembly</span></span></td>
<td><span data-ttu-id="31b64-536">55</span><span class="sxs-lookup"><span data-stu-id="31b64-536">55</span></span></td>
<td><span data-ttu-id="31b64-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="31b64-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="31b64-538">275.00</span><span class="sxs-lookup"><span data-stu-id="31b64-538">275.00</span></span></td>
<td><span data-ttu-id="31b64-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-540">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-540">CC004</span></span></td>
<td><span data-ttu-id="31b64-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-541">Packaging</span></span></td>
<td><span data-ttu-id="31b64-542">10</span><span class="sxs-lookup"><span data-stu-id="31b64-542">10</span></span></td>
<td><span data-ttu-id="31b64-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="31b64-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="31b64-544">50,00</span><span class="sxs-lookup"><span data-stu-id="31b64-544">50.00</span></span></td>
<td><span data-ttu-id="31b64-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-546">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-546">CC002</span></span></td>
<td><span data-ttu-id="31b64-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-547">Finance</span></span></td>
<td><span data-ttu-id="31b64-548">35</span><span class="sxs-lookup"><span data-stu-id="31b64-548">35</span></span></td>
<td><span data-ttu-id="31b64-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="31b64-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="31b64-550">436.00</span><span class="sxs-lookup"><span data-stu-id="31b64-550">436.00</span></span></td>
<td><span data-ttu-id="31b64-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-552">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-552">CC003</span></span></td>
<td><span data-ttu-id="31b64-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-553">Assembly</span></span></td>
<td><span data-ttu-id="31b64-554">55</span><span class="sxs-lookup"><span data-stu-id="31b64-554">55</span></span></td>
<td><span data-ttu-id="31b64-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="31b64-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="31b64-556">685.14</span><span class="sxs-lookup"><span data-stu-id="31b64-556">685.14</span></span></td>
<td><span data-ttu-id="31b64-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-558">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-558">CC004</span></span></td>
<td><span data-ttu-id="31b64-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-559">Packaging</span></span></td>
<td><span data-ttu-id="31b64-560">10</span><span class="sxs-lookup"><span data-stu-id="31b64-560">10</span></span></td>
<td><span data-ttu-id="31b64-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="31b64-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="31b64-562">124.57</span><span class="sxs-lookup"><span data-stu-id="31b64-562">124.57</span></span></td>
<td><span data-ttu-id="31b64-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="31b64-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-565">Cost object</span></span></th>
<th><span data-ttu-id="31b64-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-566">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-567">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-568">Amount</span></span></th>
<th><span data-ttu-id="31b64-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-570">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-570">CC003</span></span></td>
<td><span data-ttu-id="31b64-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-571">Assembly</span></span></td>
<td><span data-ttu-id="31b64-572">65</span><span class="sxs-lookup"><span data-stu-id="31b64-572">65</span></span></td>
<td><span data-ttu-id="31b64-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="31b64-574">438.75</span><span class="sxs-lookup"><span data-stu-id="31b64-574">438.75</span></span></td>
<td><span data-ttu-id="31b64-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-576">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-576">CC004</span></span></td>
<td><span data-ttu-id="31b64-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-577">Packaging</span></span></td>
<td><span data-ttu-id="31b64-578">35</span><span class="sxs-lookup"><span data-stu-id="31b64-578">35</span></span></td>
<td><span data-ttu-id="31b64-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="31b64-580">236.25</span><span class="sxs-lookup"><span data-stu-id="31b64-580">236.25</span></span></td>
<td><span data-ttu-id="31b64-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-582">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-582">CC003</span></span></td>
<td><span data-ttu-id="31b64-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-583">Assembly</span></span></td>
<td><span data-ttu-id="31b64-584">65</span><span class="sxs-lookup"><span data-stu-id="31b64-584">65</span></span></td>
<td><span data-ttu-id="31b64-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="31b64-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="31b64-586">5,297.69</span></span></td>
<td><span data-ttu-id="31b64-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-588">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-588">CC004</span></span></td>
<td><span data-ttu-id="31b64-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-589">Packaging</span></span></td>
<td><span data-ttu-id="31b64-590">35</span><span class="sxs-lookup"><span data-stu-id="31b64-590">35</span></span></td>
<td><span data-ttu-id="31b64-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="31b64-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="31b64-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="31b64-592">2,852.60</span></span></td>
<td><span data-ttu-id="31b64-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="31b64-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-595">Cost object</span></span></th>
<th><span data-ttu-id="31b64-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-596">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-597">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-598">Amount</span></span></th>
<th><span data-ttu-id="31b64-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-600">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-601">Product 1</span></span></td>
<td><span data-ttu-id="31b64-602">60</span><span class="sxs-lookup"><span data-stu-id="31b64-602">60</span></span></td>
<td><span data-ttu-id="31b64-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="31b64-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="31b64-604">535.31</span><span class="sxs-lookup"><span data-stu-id="31b64-604">535.31</span></span></td>
<td><span data-ttu-id="31b64-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-606">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-607">Product 2</span></span></td>
<td><span data-ttu-id="31b64-608">20</span><span class="sxs-lookup"><span data-stu-id="31b64-608">20</span></span></td>
<td><span data-ttu-id="31b64-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="31b64-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="31b64-610">178.44</span><span class="sxs-lookup"><span data-stu-id="31b64-610">178.44</span></span></td>
<td><span data-ttu-id="31b64-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-612">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-613">Product 1</span></span></td>
<td><span data-ttu-id="31b64-614">60</span><span class="sxs-lookup"><span data-stu-id="31b64-614">60</span></span></td>
<td><span data-ttu-id="31b64-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="31b64-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="31b64-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="31b64-616">4,487.12</span></span></td>
<td><span data-ttu-id="31b64-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-618">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-619">Product 2</span></span></td>
<td><span data-ttu-id="31b64-620">20</span><span class="sxs-lookup"><span data-stu-id="31b64-620">20</span></span></td>
<td><span data-ttu-id="31b64-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="31b64-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="31b64-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="31b64-622">1,495.71</span></span></td>
<td><span data-ttu-id="31b64-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="31b64-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="31b64-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-625">Cost object</span></span></th>
<th><span data-ttu-id="31b64-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="31b64-626">Magnitude</span></span></th>
<th><span data-ttu-id="31b64-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="31b64-627">Allocation factor</span></span></th>
<th><span data-ttu-id="31b64-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-628">Amount</span></span></th>
<th><span data-ttu-id="31b64-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-630">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-631">Product 1</span></span></td>
<td><span data-ttu-id="31b64-632">80</span><span class="sxs-lookup"><span data-stu-id="31b64-632">80</span></span></td>
<td><span data-ttu-id="31b64-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="31b64-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="31b64-634">241.05</span><span class="sxs-lookup"><span data-stu-id="31b64-634">241.05</span></span></td>
<td><span data-ttu-id="31b64-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-636">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-637">Product 2</span></span></td>
<td><span data-ttu-id="31b64-638">15</span><span class="sxs-lookup"><span data-stu-id="31b64-638">15</span></span></td>
<td><span data-ttu-id="31b64-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="31b64-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="31b64-640">45.20</span><span class="sxs-lookup"><span data-stu-id="31b64-640">45.20</span></span></td>
<td><span data-ttu-id="31b64-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-642">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-643">Product 1</span></span></td>
<td><span data-ttu-id="31b64-644">80</span><span class="sxs-lookup"><span data-stu-id="31b64-644">80</span></span></td>
<td><span data-ttu-id="31b64-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="31b64-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="31b64-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="31b64-646">2,507.09</span></span></td>
<td><span data-ttu-id="31b64-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-648">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-649">Product 2</span></span></td>
<td><span data-ttu-id="31b64-650">15</span><span class="sxs-lookup"><span data-stu-id="31b64-650">15</span></span></td>
<td><span data-ttu-id="31b64-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="31b64-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="31b64-652">470.08</span><span class="sxs-lookup"><span data-stu-id="31b64-652">470.08</span></span></td>
<td><span data-ttu-id="31b64-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="31b64-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="31b64-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-655">Journal</span><span class="sxs-lookup"><span data-stu-id="31b64-655">Journal</span></span></th>
<th><span data-ttu-id="31b64-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="31b64-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="31b64-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="31b64-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="31b64-658">version</span><span class="sxs-lookup"><span data-stu-id="31b64-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-659">00004</span><span class="sxs-lookup"><span data-stu-id="31b64-659">00004</span></span></td>
<td><span data-ttu-id="31b64-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="31b64-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="31b64-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="31b64-661">Fiscal</span></span></td>
<td><span data-ttu-id="31b64-662">2017</span><span class="sxs-lookup"><span data-stu-id="31b64-662">2017</span></span></td>
<td><span data-ttu-id="31b64-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-663">Period 1</span></span></td>
<td><span data-ttu-id="31b64-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="31b64-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="31b64-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="31b64-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="31b64-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-668">Cost element</span></span></th>
<th><span data-ttu-id="31b64-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-669">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-672">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-672">CC001</span></span></td>
<td><span data-ttu-id="31b64-673">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-673">HR</span></span></td>
<td><span data-ttu-id="31b64-674">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-674">10001</span></span></td>
<td><span data-ttu-id="31b64-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-675">Electricity</span></span></td>
<td><span data-ttu-id="31b64-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-676">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-677">500.00</span><span class="sxs-lookup"><span data-stu-id="31b64-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-679">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-679">CC001</span></span></td>
<td><span data-ttu-id="31b64-680">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-680">HR</span></span></td>
<td><span data-ttu-id="31b64-681">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-681">10001</span></span></td>
<td><span data-ttu-id="31b64-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-682">Electricity</span></span></td>
<td><span data-ttu-id="31b64-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-683">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="31b64-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-686">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-686">CC002</span></span></td>
<td><span data-ttu-id="31b64-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-687">Finance</span></span></td>
<td><span data-ttu-id="31b64-688">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-688">10001</span></span></td>
<td><span data-ttu-id="31b64-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-689">Electricity</span></span></td>
<td><span data-ttu-id="31b64-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-690">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-691">675.00</span><span class="sxs-lookup"><span data-stu-id="31b64-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-693">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-693">CC002</span></span></td>
<td><span data-ttu-id="31b64-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-694">Finance</span></span></td>
<td><span data-ttu-id="31b64-695">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-695">10001</span></span></td>
<td><span data-ttu-id="31b64-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-696">Electricity</span></span></td>
<td><span data-ttu-id="31b64-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-697">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="31b64-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-700">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-700">CC003</span></span></td>
<td><span data-ttu-id="31b64-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-701">Assembly</span></span></td>
<td><span data-ttu-id="31b64-702">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-702">10001</span></span></td>
<td><span data-ttu-id="31b64-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-703">Electricity</span></span></td>
<td><span data-ttu-id="31b64-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-704">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-705">713.75</span><span class="sxs-lookup"><span data-stu-id="31b64-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-707">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-707">CC003</span></span></td>
<td><span data-ttu-id="31b64-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-708">Assembly</span></span></td>
<td><span data-ttu-id="31b64-709">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-709">10001</span></span></td>
<td><span data-ttu-id="31b64-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-710">Electricity</span></span></td>
<td><span data-ttu-id="31b64-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-711">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="31b64-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-714">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-714">CC003</span></span></td>
<td><span data-ttu-id="31b64-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-715">Packaging</span></span></td>
<td><span data-ttu-id="31b64-716">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-716">10001</span></span></td>
<td><span data-ttu-id="31b64-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-717">Electricity</span></span></td>
<td><span data-ttu-id="31b64-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-718">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-719">286.25</span><span class="sxs-lookup"><span data-stu-id="31b64-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-721">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-721">CC003</span></span></td>
<td><span data-ttu-id="31b64-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-722">Packaging</span></span></td>
<td><span data-ttu-id="31b64-723">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-723">10001</span></span></td>
<td><span data-ttu-id="31b64-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-724">Electricity</span></span></td>
<td><span data-ttu-id="31b64-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-725">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="31b64-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-728">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-729">Product 1</span></span></td>
<td><span data-ttu-id="31b64-730">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-730">10001</span></span></td>
<td><span data-ttu-id="31b64-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-731">Electricity</span></span></td>
<td><span data-ttu-id="31b64-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-732">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-733">776.36</span><span class="sxs-lookup"><span data-stu-id="31b64-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-735">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-736">Product 1</span></span></td>
<td><span data-ttu-id="31b64-737">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-737">10001</span></span></td>
<td><span data-ttu-id="31b64-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-738">Electricity</span></span></td>
<td><span data-ttu-id="31b64-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-739">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="31b64-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-742">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-743">Product 1</span></span></td>
<td><span data-ttu-id="31b64-744">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-744">10001</span></span></td>
<td><span data-ttu-id="31b64-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-745">Electricity</span></span></td>
<td><span data-ttu-id="31b64-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-746">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-747">223.64</span><span class="sxs-lookup"><span data-stu-id="31b64-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="31b64-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-749">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-750">Product 1</span></span></td>
<td><span data-ttu-id="31b64-751">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-751">10001</span></span></td>
<td><span data-ttu-id="31b64-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-752">Electricity</span></span></td>
<td><span data-ttu-id="31b64-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-753">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="31b64-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="31b64-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="31b64-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="31b64-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="31b64-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-757">Cost element</span></span></th>
<th><span data-ttu-id="31b64-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="31b64-758">Cost behavior</span></span></th>
<th><span data-ttu-id="31b64-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="31b64-759">Amount</span></span></th>
<th><span data-ttu-id="31b64-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="31b64-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="31b64-761">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-761">CC001</span></span></td>
<td><span data-ttu-id="31b64-762">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-762">HR</span></span></td>
<td><span data-ttu-id="31b64-763">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-763">10001</span></span></td>
<td><span data-ttu-id="31b64-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-764">Electricity</span></span></td>
<td><span data-ttu-id="31b64-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-765">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="31b64-766">-500.00</span></span></td>
<td><span data-ttu-id="31b64-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-768">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-768">CC002</span></span></td>
<td><span data-ttu-id="31b64-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-769">Finance</span></span></td>
<td><span data-ttu-id="31b64-770">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-770">10001</span></span></td>
<td><span data-ttu-id="31b64-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-771">Electricity</span></span></td>
<td><span data-ttu-id="31b64-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-772">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-773">175.00</span><span class="sxs-lookup"><span data-stu-id="31b64-773">175.00</span></span></td>
<td><span data-ttu-id="31b64-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-775">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-775">CC003</span></span></td>
<td><span data-ttu-id="31b64-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-776">Assembly</span></span></td>
<td><span data-ttu-id="31b64-777">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-777">10001</span></span></td>
<td><span data-ttu-id="31b64-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-778">Electricity</span></span></td>
<td><span data-ttu-id="31b64-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-779">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-780">275.00</span><span class="sxs-lookup"><span data-stu-id="31b64-780">275.00</span></span></td>
<td><span data-ttu-id="31b64-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-782">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-782">CC004</span></span></td>
<td><span data-ttu-id="31b64-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-783">Packaging</span></span></td>
<td><span data-ttu-id="31b64-784">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-784">10001</span></span></td>
<td><span data-ttu-id="31b64-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-785">Electricity</span></span></td>
<td><span data-ttu-id="31b64-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-786">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-787">50,00</span><span class="sxs-lookup"><span data-stu-id="31b64-787">50,00</span></span></td>
<td><span data-ttu-id="31b64-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-789">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-789">CC001</span></span></td>
<td><span data-ttu-id="31b64-790">Personal</span><span class="sxs-lookup"><span data-stu-id="31b64-790">HR</span></span></td>
<td><span data-ttu-id="31b64-791">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-791">10001</span></span></td>
<td><span data-ttu-id="31b64-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-792">Electricity</span></span></td>
<td><span data-ttu-id="31b64-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-793">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="31b64-794">-1,245.71</span></span></td>
<td><span data-ttu-id="31b64-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-796">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-796">CC002</span></span></td>
<td><span data-ttu-id="31b64-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-797">Finance</span></span></td>
<td><span data-ttu-id="31b64-798">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-798">10001</span></span></td>
<td><span data-ttu-id="31b64-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-799">Electricity</span></span></td>
<td><span data-ttu-id="31b64-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-800">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-801">436.00</span><span class="sxs-lookup"><span data-stu-id="31b64-801">436.00</span></span></td>
<td><span data-ttu-id="31b64-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-803">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-803">CC003</span></span></td>
<td><span data-ttu-id="31b64-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-804">Assembly</span></span></td>
<td><span data-ttu-id="31b64-805">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-805">10001</span></span></td>
<td><span data-ttu-id="31b64-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-806">Electricity</span></span></td>
<td><span data-ttu-id="31b64-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-807">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-808">685.14</span><span class="sxs-lookup"><span data-stu-id="31b64-808">685.14</span></span></td>
<td><span data-ttu-id="31b64-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-810">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-810">CC004</span></span></td>
<td><span data-ttu-id="31b64-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-811">Packaging</span></span></td>
<td><span data-ttu-id="31b64-812">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-812">10001</span></span></td>
<td><span data-ttu-id="31b64-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-813">Electricity</span></span></td>
<td><span data-ttu-id="31b64-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-814">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-815">124.57</span><span class="sxs-lookup"><span data-stu-id="31b64-815">124.57</span></span></td>
<td><span data-ttu-id="31b64-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-817">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-817">CC002</span></span></td>
<td><span data-ttu-id="31b64-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-818">Finance</span></span></td>
<td><span data-ttu-id="31b64-819">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-819">10001</span></span></td>
<td><span data-ttu-id="31b64-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-820">Electricity</span></span></td>
<td><span data-ttu-id="31b64-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-821">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="31b64-822">-675.00</span></span></td>
<td><span data-ttu-id="31b64-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-824">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-824">CC003</span></span></td>
<td><span data-ttu-id="31b64-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-825">Assembly</span></span></td>
<td><span data-ttu-id="31b64-826">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-826">10001</span></span></td>
<td><span data-ttu-id="31b64-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-827">Electricity</span></span></td>
<td><span data-ttu-id="31b64-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-828">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-829">438.75</span><span class="sxs-lookup"><span data-stu-id="31b64-829">438.75</span></span></td>
<td><span data-ttu-id="31b64-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-831">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-831">CC004</span></span></td>
<td><span data-ttu-id="31b64-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-832">Packaging</span></span></td>
<td><span data-ttu-id="31b64-833">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-833">10001</span></span></td>
<td><span data-ttu-id="31b64-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-834">Electricity</span></span></td>
<td><span data-ttu-id="31b64-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-835">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-836">236.25</span><span class="sxs-lookup"><span data-stu-id="31b64-836">236.25</span></span></td>
<td><span data-ttu-id="31b64-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-838">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-838">CC002</span></span></td>
<td><span data-ttu-id="31b64-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="31b64-839">Finance</span></span></td>
<td><span data-ttu-id="31b64-840">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-840">10001</span></span></td>
<td><span data-ttu-id="31b64-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-841">Electricity</span></span></td>
<td><span data-ttu-id="31b64-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-842">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="31b64-843">-8,150.29</span></span></td>
<td><span data-ttu-id="31b64-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-845">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-845">CC003</span></span></td>
<td><span data-ttu-id="31b64-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-846">Assembly</span></span></td>
<td><span data-ttu-id="31b64-847">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-847">10001</span></span></td>
<td><span data-ttu-id="31b64-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-848">Electricity</span></span></td>
<td><span data-ttu-id="31b64-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-849">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="31b64-850">5,297.69</span></span></td>
<td><span data-ttu-id="31b64-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-852">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-852">CC004</span></span></td>
<td><span data-ttu-id="31b64-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="31b64-853">Packaging</span></span></td>
<td><span data-ttu-id="31b64-854">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-854">10001</span></span></td>
<td><span data-ttu-id="31b64-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-855">Electricity</span></span></td>
<td><span data-ttu-id="31b64-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-856">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="31b64-857">2,852.60</span></span></td>
<td><span data-ttu-id="31b64-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-859">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-859">CC003</span></span></td>
<td><span data-ttu-id="31b64-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-860">Assembly</span></span></td>
<td><span data-ttu-id="31b64-861">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-861">10001</span></span></td>
<td><span data-ttu-id="31b64-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-862">Electricity</span></span></td>
<td><span data-ttu-id="31b64-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-863">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="31b64-864">-713.75</span></span></td>
<td><span data-ttu-id="31b64-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-866">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-867">Product 1</span></span></td>
<td><span data-ttu-id="31b64-868">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-868">10001</span></span></td>
<td><span data-ttu-id="31b64-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-869">Electricity</span></span></td>
<td><span data-ttu-id="31b64-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-870">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-871">535.31</span><span class="sxs-lookup"><span data-stu-id="31b64-871">535.31</span></span></td>
<td><span data-ttu-id="31b64-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-873">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-874">Product 2</span></span></td>
<td><span data-ttu-id="31b64-875">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-875">10001</span></span></td>
<td><span data-ttu-id="31b64-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-876">Electricity</span></span></td>
<td><span data-ttu-id="31b64-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-877">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-878">178.44</span><span class="sxs-lookup"><span data-stu-id="31b64-878">178.44</span></span></td>
<td><span data-ttu-id="31b64-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-880">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-880">CC003</span></span></td>
<td><span data-ttu-id="31b64-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-881">Assembly</span></span></td>
<td><span data-ttu-id="31b64-882">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-882">10001</span></span></td>
<td><span data-ttu-id="31b64-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-883">Electricity</span></span></td>
<td><span data-ttu-id="31b64-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-884">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="31b64-885">-5,982.83</span></span></td>
<td><span data-ttu-id="31b64-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-887">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-888">Product 1</span></span></td>
<td><span data-ttu-id="31b64-889">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-889">10001</span></span></td>
<td><span data-ttu-id="31b64-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-890">Electricity</span></span></td>
<td><span data-ttu-id="31b64-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-891">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="31b64-892">4,487.12</span></span></td>
<td><span data-ttu-id="31b64-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-894">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-895">Product 2</span></span></td>
<td><span data-ttu-id="31b64-896">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-896">10001</span></span></td>
<td><span data-ttu-id="31b64-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-897">Electricity</span></span></td>
<td><span data-ttu-id="31b64-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-898">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="31b64-899">1,495.71</span></span></td>
<td><span data-ttu-id="31b64-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-901">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-901">CC003</span></span></td>
<td><span data-ttu-id="31b64-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-902">Assembly</span></span></td>
<td><span data-ttu-id="31b64-903">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-903">10001</span></span></td>
<td><span data-ttu-id="31b64-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-904">Electricity</span></span></td>
<td><span data-ttu-id="31b64-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-905">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="31b64-906">-286.25</span></span></td>
<td><span data-ttu-id="31b64-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-908">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-909">Product 1</span></span></td>
<td><span data-ttu-id="31b64-910">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-910">10001</span></span></td>
<td><span data-ttu-id="31b64-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-911">Electricity</span></span></td>
<td><span data-ttu-id="31b64-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-912">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-913">241.05</span><span class="sxs-lookup"><span data-stu-id="31b64-913">241.05</span></span></td>
<td><span data-ttu-id="31b64-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-915">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-916">Product 2</span></span></td>
<td><span data-ttu-id="31b64-917">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-917">10001</span></span></td>
<td><span data-ttu-id="31b64-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-918">Electricity</span></span></td>
<td><span data-ttu-id="31b64-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-919">Fixed cost</span></span></td>
<td><span data-ttu-id="31b64-920">45.20</span><span class="sxs-lookup"><span data-stu-id="31b64-920">45.20</span></span></td>
<td><span data-ttu-id="31b64-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-922">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-922">CC003</span></span></td>
<td><span data-ttu-id="31b64-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="31b64-923">Assembly</span></span></td>
<td><span data-ttu-id="31b64-924">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-924">10001</span></span></td>
<td><span data-ttu-id="31b64-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-925">Electricity</span></span></td>
<td><span data-ttu-id="31b64-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-926">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="31b64-927">-2,977.17</span></span></td>
<td><span data-ttu-id="31b64-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-929">Prod 1</span></span></td>
<td><span data-ttu-id="31b64-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="31b64-930">Product 1</span></span></td>
<td><span data-ttu-id="31b64-931">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-931">10001</span></span></td>
<td><span data-ttu-id="31b64-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-932">Electricity</span></span></td>
<td><span data-ttu-id="31b64-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-933">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="31b64-934">2,507.09</span></span></td>
<td><span data-ttu-id="31b64-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="31b64-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-936">Prod 2</span></span></td>
<td><span data-ttu-id="31b64-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="31b64-937">Product 2</span></span></td>
<td><span data-ttu-id="31b64-938">10001</span><span class="sxs-lookup"><span data-stu-id="31b64-938">10001</span></span></td>
<td><span data-ttu-id="31b64-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-939">Electricity</span></span></td>
<td><span data-ttu-id="31b64-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-940">Variable cost</span></span></td>
<td><span data-ttu-id="31b64-941">470.08</span><span class="sxs-lookup"><span data-stu-id="31b64-941">470.08</span></span></td>
<td><span data-ttu-id="31b64-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="31b64-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="31b64-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="31b64-943">Conclusion</span></span>
<span data-ttu-id="31b64-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="31b64-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="31b64-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="31b64-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="31b64-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="31b64-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="31b64-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="31b64-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="31b64-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="31b64-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="31b64-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="31b64-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="31b64-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="31b64-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="31b64-951">CC099</span><span class="sxs-lookup"><span data-stu-id="31b64-951">CC099</span></span></th>
<th><span data-ttu-id="31b64-952">CC001</span><span class="sxs-lookup"><span data-stu-id="31b64-952">CC001</span></span></th>
<th><span data-ttu-id="31b64-953">CC002</span><span class="sxs-lookup"><span data-stu-id="31b64-953">CC002</span></span></th>
<th><span data-ttu-id="31b64-954">CC003</span><span class="sxs-lookup"><span data-stu-id="31b64-954">CC003</span></span></th>
<th><span data-ttu-id="31b64-955">CC004</span><span class="sxs-lookup"><span data-stu-id="31b64-955">CC004</span></span></th>
<th><span data-ttu-id="31b64-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="31b64-956">Proj 1</span></span></th>
<th><span data-ttu-id="31b64-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="31b64-957">Proj 2</span></span></th>
<th><span data-ttu-id="31b64-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="31b64-958">Prod 1</span></span></th>
<th><span data-ttu-id="31b64-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="31b64-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="31b64-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="31b64-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="31b64-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="31b64-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="31b64-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-971">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="31b64-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-973">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-974">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-975">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-976">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-977">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="31b64-978">776.36</span><span class="sxs-lookup"><span data-stu-id="31b64-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-979">223.64</span><span class="sxs-lookup"><span data-stu-id="31b64-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="31b64-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="31b64-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-982">000</span><span class="sxs-lookup"><span data-stu-id="31b64-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-983">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-984">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-985">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-986">0,00</span><span class="sxs-lookup"><span data-stu-id="31b64-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-987">30,00</span><span class="sxs-lookup"><span data-stu-id="31b64-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-988">10,00</span><span class="sxs-lookup"><span data-stu-id="31b64-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="31b64-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="31b64-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="31b64-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="31b64-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="31b64-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="31b64-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="31b64-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="31b64-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="31b64-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="31b64-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="31b64-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="31b64-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="31b64-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="31b64-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



