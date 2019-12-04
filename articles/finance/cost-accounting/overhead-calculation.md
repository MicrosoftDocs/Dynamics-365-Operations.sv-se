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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770814"
---
# <a name="overhead-calculation"></a><span data-ttu-id="1230f-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="1230f-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1230f-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="1230f-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="1230f-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="1230f-105">Term definition</span></span>
---------------

<span data-ttu-id="1230f-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="1230f-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="1230f-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="1230f-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="1230f-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="1230f-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="1230f-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="1230f-109">Rent</span></span>
-   <span data-ttu-id="1230f-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-110">Electricity</span></span>
-   <span data-ttu-id="1230f-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="1230f-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="1230f-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="1230f-112">Overhead calculation overview</span></span>
<span data-ttu-id="1230f-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="1230f-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="1230f-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="1230f-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="1230f-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="1230f-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="1230f-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="1230f-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="1230f-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="1230f-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="1230f-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="1230f-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="1230f-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="1230f-119">Version type</span></span>
-   <span data-ttu-id="1230f-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="1230f-120">Date and time</span></span>
-   <span data-ttu-id="1230f-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="1230f-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="1230f-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="1230f-122">Fiscal year</span></span>
-   <span data-ttu-id="1230f-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="1230f-123">Fiscal period</span></span>

<span data-ttu-id="1230f-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="1230f-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="1230f-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="1230f-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="1230f-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="1230f-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="1230f-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="1230f-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="1230f-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="1230f-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="1230f-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="1230f-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="1230f-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="1230f-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="1230f-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="1230f-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="1230f-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="1230f-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="1230f-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="1230f-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="1230f-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="1230f-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="1230f-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="1230f-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="1230f-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="1230f-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="1230f-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="1230f-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="1230f-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="1230f-140">Main account</span></span></th>
<th><span data-ttu-id="1230f-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="1230f-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="1230f-143">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-143">CC099</span></span></td>
<td><span data-ttu-id="1230f-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-144">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-145">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-145">10001</span></span></td>
<td><span data-ttu-id="1230f-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-146">Electricity</span></span></td>
<td><span data-ttu-id="1230f-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="1230f-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="1230f-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="1230f-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="1230f-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="1230f-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="1230f-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="1230f-151">Define the cost behavior rule</span></span>

<span data-ttu-id="1230f-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="1230f-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="1230f-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="1230f-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="1230f-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1230f-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="1230f-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="1230f-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="1230f-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="1230f-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="1230f-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="1230f-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="1230f-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="1230f-159">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-160">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-160">Journal</span></span></th>
<th><span data-ttu-id="1230f-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1230f-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1230f-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1230f-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1230f-163">version</span><span class="sxs-lookup"><span data-stu-id="1230f-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-164">00001</span><span class="sxs-lookup"><span data-stu-id="1230f-164">00001</span></span></td>
<td><span data-ttu-id="1230f-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="1230f-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="1230f-166">Fiscal</span></span></td>
<td><span data-ttu-id="1230f-167">2017</span><span class="sxs-lookup"><span data-stu-id="1230f-167">2017</span></span></td>
<td><span data-ttu-id="1230f-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-168">Period 1</span></span></td>
<td><span data-ttu-id="1230f-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1230f-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1230f-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-173">Cost element</span></span></th>
<th><span data-ttu-id="1230f-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-174">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="1230f-177">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-177">CC099</span></span></td>
<td><span data-ttu-id="1230f-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-178">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-179">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-179">10001</span></span></td>
<td><span data-ttu-id="1230f-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-180">Electricity</span></span></td>
<td><span data-ttu-id="1230f-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1230f-181">Unclassified</span></span></td>
<td><span data-ttu-id="1230f-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1230f-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1230f-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-185">Cost element</span></span></th>
<th><span data-ttu-id="1230f-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-186">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-187">Amount</span></span></th>
<th><span data-ttu-id="1230f-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-189">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-189">CC099</span></span></td>
<td><span data-ttu-id="1230f-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-190">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-191">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-191">10001</span></span></td>
<td><span data-ttu-id="1230f-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-192">Electricity</span></span></td>
<td><span data-ttu-id="1230f-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1230f-193">Unclassified</span></span></td>
<td><span data-ttu-id="1230f-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-194">10,000.00</span></span></td>
<td><span data-ttu-id="1230f-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-196">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-196">CC099</span></span></td>
<td><span data-ttu-id="1230f-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-197">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-198">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-198">10001</span></span></td>
<td><span data-ttu-id="1230f-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-199">Electricity</span></span></td>
<td><span data-ttu-id="1230f-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1230f-200">Unclassified</span></span></td>
<td><span data-ttu-id="1230f-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-201">-10,000.00</span></span></td>
<td><span data-ttu-id="1230f-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-203">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-203">CC099</span></span></td>
<td><span data-ttu-id="1230f-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-204">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-205">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-205">10001</span></span></td>
<td><span data-ttu-id="1230f-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-206">Electricity</span></span></td>
<td><span data-ttu-id="1230f-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-207">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-208">1,000.00</span></span></td>
<td><span data-ttu-id="1230f-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-210">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-210">CC099</span></span></td>
<td><span data-ttu-id="1230f-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-211">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-212">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-212">10001</span></span></td>
<td><span data-ttu-id="1230f-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-213">Electricity</span></span></td>
<td><span data-ttu-id="1230f-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-214">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="1230f-215">9,000.00</span></span></td>
<td><span data-ttu-id="1230f-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1230f-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="1230f-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="1230f-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="1230f-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1230f-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="1230f-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1230f-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="1230f-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="1230f-221">Define the cost distribution rule</span></span>

<span data-ttu-id="1230f-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="1230f-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="1230f-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="1230f-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="1230f-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="1230f-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="1230f-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1230f-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="1230f-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="1230f-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="1230f-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1230f-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-228">Cost object</span></span></th>
<th><span data-ttu-id="1230f-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="1230f-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-230">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-230">CC001</span></span></td>
<td><span data-ttu-id="1230f-231">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-231">HR</span></span></td>
<td><span data-ttu-id="1230f-232">1 000</span><span class="sxs-lookup"><span data-stu-id="1230f-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-233">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-233">CC002</span></span></td>
<td><span data-ttu-id="1230f-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-234">Finance</span></span></td>
<td><span data-ttu-id="1230f-235">6,000</span><span class="sxs-lookup"><span data-stu-id="1230f-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-236">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-236">CC003</span></span></td>
<td><span data-ttu-id="1230f-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-237">Assembly</span></span></td>
<td><span data-ttu-id="1230f-238">0</span><span class="sxs-lookup"><span data-stu-id="1230f-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="1230f-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-240">Cost object</span></span></th>
<th><span data-ttu-id="1230f-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-241">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-242">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-244">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-244">CC001</span></span></td>
<td><span data-ttu-id="1230f-245">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-245">HR</span></span></td>
<td><span data-ttu-id="1230f-246">1 000</span><span class="sxs-lookup"><span data-stu-id="1230f-246">1,000</span></span></td>
<td><span data-ttu-id="1230f-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1230f-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1230f-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-249">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-249">CC002</span></span></td>
<td><span data-ttu-id="1230f-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-250">Finance</span></span></td>
<td><span data-ttu-id="1230f-251">6,000</span><span class="sxs-lookup"><span data-stu-id="1230f-251">6,000</span></span></td>
<td><span data-ttu-id="1230f-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1230f-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1230f-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-254">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-254">CC003</span></span></td>
<td><span data-ttu-id="1230f-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-255">Assembly</span></span></td>
<td><span data-ttu-id="1230f-256">0</span><span class="sxs-lookup"><span data-stu-id="1230f-256">0</span></span></td>
<td><span data-ttu-id="1230f-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1230f-258">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="1230f-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="1230f-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="1230f-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-261">Cost object</span></span></th>
<th><span data-ttu-id="1230f-262">Formel</span><span class="sxs-lookup"><span data-stu-id="1230f-262">Formula</span></span></th>
<th><span data-ttu-id="1230f-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-263">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-264">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-266">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-266">CC001</span></span></td>
<td><span data-ttu-id="1230f-267">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-267">HR</span></span></td>
<td><span data-ttu-id="1230f-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1230f-269">1</span><span class="sxs-lookup"><span data-stu-id="1230f-269">1</span></span></td>
<td><span data-ttu-id="1230f-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1230f-271">500.00</span><span class="sxs-lookup"><span data-stu-id="1230f-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-272">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-272">CC002</span></span></td>
<td><span data-ttu-id="1230f-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-273">Finance</span></span></td>
<td><span data-ttu-id="1230f-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1230f-275">1</span><span class="sxs-lookup"><span data-stu-id="1230f-275">1</span></span></td>
<td><span data-ttu-id="1230f-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1230f-277">500.00</span><span class="sxs-lookup"><span data-stu-id="1230f-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-278">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-278">CC003</span></span></td>
<td><span data-ttu-id="1230f-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-279">Assembly</span></span></td>
<td><span data-ttu-id="1230f-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1230f-281">0</span><span class="sxs-lookup"><span data-stu-id="1230f-281">0</span></span></td>
<td><span data-ttu-id="1230f-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1230f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1230f-284">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-285">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-285">Journal</span></span></th>
<th><span data-ttu-id="1230f-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1230f-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1230f-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1230f-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1230f-288">version</span><span class="sxs-lookup"><span data-stu-id="1230f-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-289">00002</span><span class="sxs-lookup"><span data-stu-id="1230f-289">00002</span></span></td>
<td><span data-ttu-id="1230f-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="1230f-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="1230f-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="1230f-291">Fiscal</span></span></td>
<td><span data-ttu-id="1230f-292">2017</span><span class="sxs-lookup"><span data-stu-id="1230f-292">2017</span></span></td>
<td><span data-ttu-id="1230f-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-293">Period 1</span></span></td>
<td><span data-ttu-id="1230f-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1230f-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1230f-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-298">Cost element</span></span></th>
<th><span data-ttu-id="1230f-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-299">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-302">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-302">CC099</span></span></td>
<td><span data-ttu-id="1230f-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-303">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-304">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-304">10001</span></span></td>
<td><span data-ttu-id="1230f-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-305">Electricity</span></span></td>
<td><span data-ttu-id="1230f-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-306">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-309">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-309">CC099</span></span></td>
<td><span data-ttu-id="1230f-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-310">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-311">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-311">10001</span></span></td>
<td><span data-ttu-id="1230f-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-312">Electricity</span></span></td>
<td><span data-ttu-id="1230f-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-313">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="1230f-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1230f-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1230f-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-317">Cost element</span></span></th>
<th><span data-ttu-id="1230f-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-318">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-319">Amount</span></span></th>
<th><span data-ttu-id="1230f-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-321">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-321">CC099</span></span></td>
<td><span data-ttu-id="1230f-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-322">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-323">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-323">10001</span></span></td>
<td><span data-ttu-id="1230f-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-324">Electricity</span></span></td>
<td><span data-ttu-id="1230f-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-325">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-326">-1,000.00</span></span></td>
<td><span data-ttu-id="1230f-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-328">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-328">CC001</span></span></td>
<td><span data-ttu-id="1230f-329">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-329">HR</span></span></td>
<td><span data-ttu-id="1230f-330">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-330">10001</span></span></td>
<td><span data-ttu-id="1230f-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-331">Electricity</span></span></td>
<td><span data-ttu-id="1230f-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-332">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-333">500.00</span><span class="sxs-lookup"><span data-stu-id="1230f-333">500.00</span></span></td>
<td><span data-ttu-id="1230f-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-335">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-335">CC002</span></span></td>
<td><span data-ttu-id="1230f-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-336">Finance</span></span></td>
<td><span data-ttu-id="1230f-337">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-337">10001</span></span></td>
<td><span data-ttu-id="1230f-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-338">Electricity</span></span></td>
<td><span data-ttu-id="1230f-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-339">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-340">500.00</span><span class="sxs-lookup"><span data-stu-id="1230f-340">500.00</span></span></td>
<td><span data-ttu-id="1230f-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-342">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-342">CC099</span></span></td>
<td><span data-ttu-id="1230f-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1230f-343">Default cost center</span></span></td>
<td><span data-ttu-id="1230f-344">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-344">10001</span></span></td>
<td><span data-ttu-id="1230f-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-345">Electricity</span></span></td>
<td><span data-ttu-id="1230f-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-346">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="1230f-347">-9,000.00</span></span></td>
<td><span data-ttu-id="1230f-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-349">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-349">CC001</span></span></td>
<td><span data-ttu-id="1230f-350">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-350">HR</span></span></td>
<td><span data-ttu-id="1230f-351">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-351">10001</span></span></td>
<td><span data-ttu-id="1230f-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-352">Electricity</span></span></td>
<td><span data-ttu-id="1230f-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-353">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1230f-354">1,285.71</span></span></td>
<td><span data-ttu-id="1230f-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-356">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-356">CC002</span></span></td>
<td><span data-ttu-id="1230f-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-357">Finance</span></span></td>
<td><span data-ttu-id="1230f-358">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-358">10001</span></span></td>
<td><span data-ttu-id="1230f-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-359">Electricity</span></span></td>
<td><span data-ttu-id="1230f-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-360">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1230f-361">7,714.29</span></span></td>
<td><span data-ttu-id="1230f-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1230f-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="1230f-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="1230f-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="1230f-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="1230f-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="1230f-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-367">Define the overhead rate</span></span>

<span data-ttu-id="1230f-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="1230f-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1230f-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-370">Cost object</span></span></th>
<th><span data-ttu-id="1230f-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="1230f-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-372">Proj 1</span></span></td>
<td><span data-ttu-id="1230f-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-373">Project 1</span></span></td>
<td><span data-ttu-id="1230f-374">3</span><span class="sxs-lookup"><span data-stu-id="1230f-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-375">Proj 2</span></span></td>
<td><span data-ttu-id="1230f-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-376">Project 2</span></span></td>
<td><span data-ttu-id="1230f-377">1</span><span class="sxs-lookup"><span data-stu-id="1230f-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="1230f-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-379">Cost object</span></span></th>
<th><span data-ttu-id="1230f-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-380">Cost element</span></span></th>
<th><span data-ttu-id="1230f-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-381">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="1230f-382">Units</span></span></th>
<th><span data-ttu-id="1230f-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="1230f-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-384">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-384">CC001</span></span></td>
<td><span data-ttu-id="1230f-385">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-385">HR</span></span></td>
<td><span data-ttu-id="1230f-386">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-386">10001</span></span></td>
<td><span data-ttu-id="1230f-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-387">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-388">1</span><span class="sxs-lookup"><span data-stu-id="1230f-388">1</span></span></td>
<td><span data-ttu-id="1230f-389">10</span><span class="sxs-lookup"><span data-stu-id="1230f-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1230f-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-391">Cost object</span></span></th>
<th><span data-ttu-id="1230f-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-392">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-393">Cost element</span></span></th>
<th><span data-ttu-id="1230f-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-394">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-396">Proj 1</span></span></td>
<td><span data-ttu-id="1230f-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-397">Project 1</span></span></td>
<td><span data-ttu-id="1230f-398">3</span><span class="sxs-lookup"><span data-stu-id="1230f-398">3</span></span></td>
<td><span data-ttu-id="1230f-399">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-399">10001</span></span></td>
<td><span data-ttu-id="1230f-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1230f-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1230f-401">30,00</span><span class="sxs-lookup"><span data-stu-id="1230f-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-402">Proj 2</span></span></td>
<td><span data-ttu-id="1230f-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-403">Project 2</span></span></td>
<td><span data-ttu-id="1230f-404">1</span><span class="sxs-lookup"><span data-stu-id="1230f-404">1</span></span></td>
<td><span data-ttu-id="1230f-405">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-405">10001</span></span></td>
<td><span data-ttu-id="1230f-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1230f-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1230f-407">10,00</span><span class="sxs-lookup"><span data-stu-id="1230f-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1230f-408">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-409">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-409">Journal</span></span></th>
<th><span data-ttu-id="1230f-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1230f-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1230f-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1230f-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1230f-412">version</span><span class="sxs-lookup"><span data-stu-id="1230f-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-413">00003</span><span class="sxs-lookup"><span data-stu-id="1230f-413">00003</span></span></td>
<td><span data-ttu-id="1230f-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="1230f-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="1230f-415">Fiscal</span></span></td>
<td><span data-ttu-id="1230f-416">2017</span><span class="sxs-lookup"><span data-stu-id="1230f-416">2017</span></span></td>
<td><span data-ttu-id="1230f-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-417">Period 1</span></span></td>
<td><span data-ttu-id="1230f-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="1230f-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="1230f-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-421">Cost object</span></span></th>
<th><span data-ttu-id="1230f-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-424">Proj 1</span></span></td>
<td><span data-ttu-id="1230f-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1230f-426">3,00</span><span class="sxs-lookup"><span data-stu-id="1230f-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-428">Proj 2</span></span></td>
<td><span data-ttu-id="1230f-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1230f-430">1,00</span><span class="sxs-lookup"><span data-stu-id="1230f-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1230f-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1230f-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-433">Cost element</span></span></th>
<th><span data-ttu-id="1230f-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-434">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-435">Amount</span></span></th>
<th><span data-ttu-id="1230f-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="1230f-437">CC0001</span></span></td>
<td><span data-ttu-id="1230f-438">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-438">HR</span></span></td>
<td><span data-ttu-id="1230f-439">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-439">10001</span></span></td>
<td><span data-ttu-id="1230f-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-440">Electricity</span></span></td>
<td><span data-ttu-id="1230f-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-441">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="1230f-442">-30.00</span></span></td>
<td><span data-ttu-id="1230f-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-444">Proj 1</span></span></td>
<td><span data-ttu-id="1230f-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1230f-446">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-446">10001</span></span></td>
<td><span data-ttu-id="1230f-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-447">Electricity</span></span></td>
<td><span data-ttu-id="1230f-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-448">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-449">30,00</span><span class="sxs-lookup"><span data-stu-id="1230f-449">30.00</span></span></td>
<td><span data-ttu-id="1230f-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-451">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-451">CC001</span></span></td>
<td><span data-ttu-id="1230f-452">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-452">HR</span></span></td>
<td><span data-ttu-id="1230f-453">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-453">10001</span></span></td>
<td><span data-ttu-id="1230f-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-454">Electricity</span></span></td>
<td><span data-ttu-id="1230f-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-455">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="1230f-456">-10.00</span></span></td>
<td><span data-ttu-id="1230f-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-458">Proj 2</span></span></td>
<td><span data-ttu-id="1230f-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1230f-460">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-460">10001</span></span></td>
<td><span data-ttu-id="1230f-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-461">Electricity</span></span></td>
<td><span data-ttu-id="1230f-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-462">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-463">10,00</span><span class="sxs-lookup"><span data-stu-id="1230f-463">10.00</span></span></td>
<td><span data-ttu-id="1230f-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="1230f-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="1230f-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="1230f-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="1230f-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1230f-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="1230f-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="1230f-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="1230f-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="1230f-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="1230f-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="1230f-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="1230f-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1230f-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="1230f-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="1230f-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="1230f-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="1230f-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="1230f-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="1230f-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="1230f-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="1230f-475">Define the cost allocation</span></span>

<span data-ttu-id="1230f-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="1230f-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="1230f-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="1230f-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1230f-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-479">Cost object</span></span></th>
<th><span data-ttu-id="1230f-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="1230f-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-481">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-481">CC002</span></span></td>
<td><span data-ttu-id="1230f-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-482">Finance</span></span></td>
<td><span data-ttu-id="1230f-483">35</span><span class="sxs-lookup"><span data-stu-id="1230f-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-484">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-484">CC003</span></span></td>
<td><span data-ttu-id="1230f-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-485">Assembly</span></span></td>
<td><span data-ttu-id="1230f-486">55</span><span class="sxs-lookup"><span data-stu-id="1230f-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-487">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-487">CC004</span></span></td>
<td><span data-ttu-id="1230f-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-488">Packaging</span></span></td>
<td><span data-ttu-id="1230f-489">10</span><span class="sxs-lookup"><span data-stu-id="1230f-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="1230f-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1230f-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-492">Cost object</span></span></th>
<th><span data-ttu-id="1230f-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="1230f-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-494">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-494">CC003</span></span></td>
<td><span data-ttu-id="1230f-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-495">Assembly</span></span></td>
<td><span data-ttu-id="1230f-496">65</span><span class="sxs-lookup"><span data-stu-id="1230f-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-497">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-497">CC004</span></span></td>
<td><span data-ttu-id="1230f-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-498">Packaging</span></span></td>
<td><span data-ttu-id="1230f-499">35</span><span class="sxs-lookup"><span data-stu-id="1230f-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="1230f-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1230f-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-502">Cost object</span></span></th>
<th><span data-ttu-id="1230f-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="1230f-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-504">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-505">Product 1</span></span></td>
<td><span data-ttu-id="1230f-506">60</span><span class="sxs-lookup"><span data-stu-id="1230f-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-507">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-508">Product 2</span></span></td>
<td><span data-ttu-id="1230f-509">20</span><span class="sxs-lookup"><span data-stu-id="1230f-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1230f-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="1230f-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1230f-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-512">Cost object</span></span></th>
<th><span data-ttu-id="1230f-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="1230f-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-514">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-515">Product 1</span></span></td>
<td><span data-ttu-id="1230f-516">80</span><span class="sxs-lookup"><span data-stu-id="1230f-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-517">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-518">Product 2</span></span></td>
<td><span data-ttu-id="1230f-519">15</span><span class="sxs-lookup"><span data-stu-id="1230f-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1230f-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="1230f-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="1230f-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="1230f-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="1230f-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1230f-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-523">Cost object</span></span></th>
<th><span data-ttu-id="1230f-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-524">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-525">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-526">Amount</span></span></th>
<th><span data-ttu-id="1230f-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-528">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-528">CC002</span></span></td>
<td><span data-ttu-id="1230f-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-529">Finance</span></span></td>
<td><span data-ttu-id="1230f-530">35</span><span class="sxs-lookup"><span data-stu-id="1230f-530">35</span></span></td>
<td><span data-ttu-id="1230f-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1230f-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1230f-532">175.00</span><span class="sxs-lookup"><span data-stu-id="1230f-532">175.00</span></span></td>
<td><span data-ttu-id="1230f-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-534">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-534">CC003</span></span></td>
<td><span data-ttu-id="1230f-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-535">Assembly</span></span></td>
<td><span data-ttu-id="1230f-536">55</span><span class="sxs-lookup"><span data-stu-id="1230f-536">55</span></span></td>
<td><span data-ttu-id="1230f-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1230f-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1230f-538">275.00</span><span class="sxs-lookup"><span data-stu-id="1230f-538">275.00</span></span></td>
<td><span data-ttu-id="1230f-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-540">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-540">CC004</span></span></td>
<td><span data-ttu-id="1230f-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-541">Packaging</span></span></td>
<td><span data-ttu-id="1230f-542">10</span><span class="sxs-lookup"><span data-stu-id="1230f-542">10</span></span></td>
<td><span data-ttu-id="1230f-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1230f-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1230f-544">50,00</span><span class="sxs-lookup"><span data-stu-id="1230f-544">50.00</span></span></td>
<td><span data-ttu-id="1230f-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-546">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-546">CC002</span></span></td>
<td><span data-ttu-id="1230f-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-547">Finance</span></span></td>
<td><span data-ttu-id="1230f-548">35</span><span class="sxs-lookup"><span data-stu-id="1230f-548">35</span></span></td>
<td><span data-ttu-id="1230f-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1230f-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1230f-550">436.00</span><span class="sxs-lookup"><span data-stu-id="1230f-550">436.00</span></span></td>
<td><span data-ttu-id="1230f-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-552">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-552">CC003</span></span></td>
<td><span data-ttu-id="1230f-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-553">Assembly</span></span></td>
<td><span data-ttu-id="1230f-554">55</span><span class="sxs-lookup"><span data-stu-id="1230f-554">55</span></span></td>
<td><span data-ttu-id="1230f-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1230f-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1230f-556">685.14</span><span class="sxs-lookup"><span data-stu-id="1230f-556">685.14</span></span></td>
<td><span data-ttu-id="1230f-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-558">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-558">CC004</span></span></td>
<td><span data-ttu-id="1230f-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-559">Packaging</span></span></td>
<td><span data-ttu-id="1230f-560">10</span><span class="sxs-lookup"><span data-stu-id="1230f-560">10</span></span></td>
<td><span data-ttu-id="1230f-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1230f-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1230f-562">124.57</span><span class="sxs-lookup"><span data-stu-id="1230f-562">124.57</span></span></td>
<td><span data-ttu-id="1230f-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1230f-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-565">Cost object</span></span></th>
<th><span data-ttu-id="1230f-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-566">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-567">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-568">Amount</span></span></th>
<th><span data-ttu-id="1230f-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-570">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-570">CC003</span></span></td>
<td><span data-ttu-id="1230f-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-571">Assembly</span></span></td>
<td><span data-ttu-id="1230f-572">65</span><span class="sxs-lookup"><span data-stu-id="1230f-572">65</span></span></td>
<td><span data-ttu-id="1230f-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1230f-574">438.75</span><span class="sxs-lookup"><span data-stu-id="1230f-574">438.75</span></span></td>
<td><span data-ttu-id="1230f-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-576">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-576">CC004</span></span></td>
<td><span data-ttu-id="1230f-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-577">Packaging</span></span></td>
<td><span data-ttu-id="1230f-578">35</span><span class="sxs-lookup"><span data-stu-id="1230f-578">35</span></span></td>
<td><span data-ttu-id="1230f-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1230f-580">236.25</span><span class="sxs-lookup"><span data-stu-id="1230f-580">236.25</span></span></td>
<td><span data-ttu-id="1230f-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-582">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-582">CC003</span></span></td>
<td><span data-ttu-id="1230f-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-583">Assembly</span></span></td>
<td><span data-ttu-id="1230f-584">65</span><span class="sxs-lookup"><span data-stu-id="1230f-584">65</span></span></td>
<td><span data-ttu-id="1230f-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1230f-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1230f-586">5,297.69</span></span></td>
<td><span data-ttu-id="1230f-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-588">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-588">CC004</span></span></td>
<td><span data-ttu-id="1230f-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-589">Packaging</span></span></td>
<td><span data-ttu-id="1230f-590">35</span><span class="sxs-lookup"><span data-stu-id="1230f-590">35</span></span></td>
<td><span data-ttu-id="1230f-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1230f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1230f-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1230f-592">2,852.60</span></span></td>
<td><span data-ttu-id="1230f-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1230f-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-595">Cost object</span></span></th>
<th><span data-ttu-id="1230f-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-596">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-597">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-598">Amount</span></span></th>
<th><span data-ttu-id="1230f-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-600">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-601">Product 1</span></span></td>
<td><span data-ttu-id="1230f-602">60</span><span class="sxs-lookup"><span data-stu-id="1230f-602">60</span></span></td>
<td><span data-ttu-id="1230f-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1230f-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1230f-604">535.31</span><span class="sxs-lookup"><span data-stu-id="1230f-604">535.31</span></span></td>
<td><span data-ttu-id="1230f-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-606">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-607">Product 2</span></span></td>
<td><span data-ttu-id="1230f-608">20</span><span class="sxs-lookup"><span data-stu-id="1230f-608">20</span></span></td>
<td><span data-ttu-id="1230f-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1230f-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1230f-610">178.44</span><span class="sxs-lookup"><span data-stu-id="1230f-610">178.44</span></span></td>
<td><span data-ttu-id="1230f-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-612">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-613">Product 1</span></span></td>
<td><span data-ttu-id="1230f-614">60</span><span class="sxs-lookup"><span data-stu-id="1230f-614">60</span></span></td>
<td><span data-ttu-id="1230f-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1230f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1230f-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1230f-616">4,487.12</span></span></td>
<td><span data-ttu-id="1230f-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-618">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-619">Product 2</span></span></td>
<td><span data-ttu-id="1230f-620">20</span><span class="sxs-lookup"><span data-stu-id="1230f-620">20</span></span></td>
<td><span data-ttu-id="1230f-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1230f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1230f-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1230f-622">1,495.71</span></span></td>
<td><span data-ttu-id="1230f-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1230f-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1230f-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-625">Cost object</span></span></th>
<th><span data-ttu-id="1230f-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="1230f-626">Magnitude</span></span></th>
<th><span data-ttu-id="1230f-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1230f-627">Allocation factor</span></span></th>
<th><span data-ttu-id="1230f-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-628">Amount</span></span></th>
<th><span data-ttu-id="1230f-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-630">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-631">Product 1</span></span></td>
<td><span data-ttu-id="1230f-632">80</span><span class="sxs-lookup"><span data-stu-id="1230f-632">80</span></span></td>
<td><span data-ttu-id="1230f-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1230f-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1230f-634">241.05</span><span class="sxs-lookup"><span data-stu-id="1230f-634">241.05</span></span></td>
<td><span data-ttu-id="1230f-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-636">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-637">Product 2</span></span></td>
<td><span data-ttu-id="1230f-638">15</span><span class="sxs-lookup"><span data-stu-id="1230f-638">15</span></span></td>
<td><span data-ttu-id="1230f-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1230f-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1230f-640">45.20</span><span class="sxs-lookup"><span data-stu-id="1230f-640">45.20</span></span></td>
<td><span data-ttu-id="1230f-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-642">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-643">Product 1</span></span></td>
<td><span data-ttu-id="1230f-644">80</span><span class="sxs-lookup"><span data-stu-id="1230f-644">80</span></span></td>
<td><span data-ttu-id="1230f-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1230f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1230f-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1230f-646">2,507.09</span></span></td>
<td><span data-ttu-id="1230f-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-648">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-649">Product 2</span></span></td>
<td><span data-ttu-id="1230f-650">15</span><span class="sxs-lookup"><span data-stu-id="1230f-650">15</span></span></td>
<td><span data-ttu-id="1230f-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1230f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1230f-652">470.08</span><span class="sxs-lookup"><span data-stu-id="1230f-652">470.08</span></span></td>
<td><span data-ttu-id="1230f-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1230f-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1230f-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-655">Journal</span><span class="sxs-lookup"><span data-stu-id="1230f-655">Journal</span></span></th>
<th><span data-ttu-id="1230f-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1230f-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1230f-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1230f-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1230f-658">version</span><span class="sxs-lookup"><span data-stu-id="1230f-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-659">00004</span><span class="sxs-lookup"><span data-stu-id="1230f-659">00004</span></span></td>
<td><span data-ttu-id="1230f-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="1230f-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="1230f-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="1230f-661">Fiscal</span></span></td>
<td><span data-ttu-id="1230f-662">2017</span><span class="sxs-lookup"><span data-stu-id="1230f-662">2017</span></span></td>
<td><span data-ttu-id="1230f-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-663">Period 1</span></span></td>
<td><span data-ttu-id="1230f-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1230f-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="1230f-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="1230f-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1230f-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-668">Cost element</span></span></th>
<th><span data-ttu-id="1230f-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-669">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-672">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-672">CC001</span></span></td>
<td><span data-ttu-id="1230f-673">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-673">HR</span></span></td>
<td><span data-ttu-id="1230f-674">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-674">10001</span></span></td>
<td><span data-ttu-id="1230f-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-675">Electricity</span></span></td>
<td><span data-ttu-id="1230f-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-676">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-677">500.00</span><span class="sxs-lookup"><span data-stu-id="1230f-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-679">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-679">CC001</span></span></td>
<td><span data-ttu-id="1230f-680">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-680">HR</span></span></td>
<td><span data-ttu-id="1230f-681">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-681">10001</span></span></td>
<td><span data-ttu-id="1230f-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-682">Electricity</span></span></td>
<td><span data-ttu-id="1230f-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-683">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="1230f-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-686">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-686">CC002</span></span></td>
<td><span data-ttu-id="1230f-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-687">Finance</span></span></td>
<td><span data-ttu-id="1230f-688">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-688">10001</span></span></td>
<td><span data-ttu-id="1230f-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-689">Electricity</span></span></td>
<td><span data-ttu-id="1230f-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-690">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-691">675.00</span><span class="sxs-lookup"><span data-stu-id="1230f-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-693">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-693">CC002</span></span></td>
<td><span data-ttu-id="1230f-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-694">Finance</span></span></td>
<td><span data-ttu-id="1230f-695">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-695">10001</span></span></td>
<td><span data-ttu-id="1230f-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-696">Electricity</span></span></td>
<td><span data-ttu-id="1230f-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-697">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="1230f-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-700">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-700">CC003</span></span></td>
<td><span data-ttu-id="1230f-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-701">Assembly</span></span></td>
<td><span data-ttu-id="1230f-702">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-702">10001</span></span></td>
<td><span data-ttu-id="1230f-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-703">Electricity</span></span></td>
<td><span data-ttu-id="1230f-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-704">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-705">713.75</span><span class="sxs-lookup"><span data-stu-id="1230f-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-707">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-707">CC003</span></span></td>
<td><span data-ttu-id="1230f-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-708">Assembly</span></span></td>
<td><span data-ttu-id="1230f-709">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-709">10001</span></span></td>
<td><span data-ttu-id="1230f-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-710">Electricity</span></span></td>
<td><span data-ttu-id="1230f-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-711">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="1230f-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-714">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-714">CC003</span></span></td>
<td><span data-ttu-id="1230f-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-715">Packaging</span></span></td>
<td><span data-ttu-id="1230f-716">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-716">10001</span></span></td>
<td><span data-ttu-id="1230f-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-717">Electricity</span></span></td>
<td><span data-ttu-id="1230f-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-718">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-719">286.25</span><span class="sxs-lookup"><span data-stu-id="1230f-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-721">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-721">CC003</span></span></td>
<td><span data-ttu-id="1230f-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-722">Packaging</span></span></td>
<td><span data-ttu-id="1230f-723">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-723">10001</span></span></td>
<td><span data-ttu-id="1230f-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-724">Electricity</span></span></td>
<td><span data-ttu-id="1230f-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-725">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="1230f-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-728">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-729">Product 1</span></span></td>
<td><span data-ttu-id="1230f-730">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-730">10001</span></span></td>
<td><span data-ttu-id="1230f-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-731">Electricity</span></span></td>
<td><span data-ttu-id="1230f-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-732">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-733">776.36</span><span class="sxs-lookup"><span data-stu-id="1230f-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-735">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-736">Product 1</span></span></td>
<td><span data-ttu-id="1230f-737">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-737">10001</span></span></td>
<td><span data-ttu-id="1230f-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-738">Electricity</span></span></td>
<td><span data-ttu-id="1230f-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-739">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1230f-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-742">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-743">Product 1</span></span></td>
<td><span data-ttu-id="1230f-744">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-744">10001</span></span></td>
<td><span data-ttu-id="1230f-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-745">Electricity</span></span></td>
<td><span data-ttu-id="1230f-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-746">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-747">223.64</span><span class="sxs-lookup"><span data-stu-id="1230f-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="1230f-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-749">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-750">Product 1</span></span></td>
<td><span data-ttu-id="1230f-751">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-751">10001</span></span></td>
<td><span data-ttu-id="1230f-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-752">Electricity</span></span></td>
<td><span data-ttu-id="1230f-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-753">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1230f-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1230f-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1230f-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1230f-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1230f-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-757">Cost element</span></span></th>
<th><span data-ttu-id="1230f-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1230f-758">Cost behavior</span></span></th>
<th><span data-ttu-id="1230f-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="1230f-759">Amount</span></span></th>
<th><span data-ttu-id="1230f-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1230f-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1230f-761">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-761">CC001</span></span></td>
<td><span data-ttu-id="1230f-762">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-762">HR</span></span></td>
<td><span data-ttu-id="1230f-763">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-763">10001</span></span></td>
<td><span data-ttu-id="1230f-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-764">Electricity</span></span></td>
<td><span data-ttu-id="1230f-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-765">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="1230f-766">-500.00</span></span></td>
<td><span data-ttu-id="1230f-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-768">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-768">CC002</span></span></td>
<td><span data-ttu-id="1230f-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-769">Finance</span></span></td>
<td><span data-ttu-id="1230f-770">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-770">10001</span></span></td>
<td><span data-ttu-id="1230f-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-771">Electricity</span></span></td>
<td><span data-ttu-id="1230f-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-772">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-773">175.00</span><span class="sxs-lookup"><span data-stu-id="1230f-773">175.00</span></span></td>
<td><span data-ttu-id="1230f-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-775">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-775">CC003</span></span></td>
<td><span data-ttu-id="1230f-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-776">Assembly</span></span></td>
<td><span data-ttu-id="1230f-777">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-777">10001</span></span></td>
<td><span data-ttu-id="1230f-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-778">Electricity</span></span></td>
<td><span data-ttu-id="1230f-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-779">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-780">275.00</span><span class="sxs-lookup"><span data-stu-id="1230f-780">275.00</span></span></td>
<td><span data-ttu-id="1230f-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-782">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-782">CC004</span></span></td>
<td><span data-ttu-id="1230f-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-783">Packaging</span></span></td>
<td><span data-ttu-id="1230f-784">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-784">10001</span></span></td>
<td><span data-ttu-id="1230f-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-785">Electricity</span></span></td>
<td><span data-ttu-id="1230f-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-786">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-787">50,00</span><span class="sxs-lookup"><span data-stu-id="1230f-787">50,00</span></span></td>
<td><span data-ttu-id="1230f-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-789">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-789">CC001</span></span></td>
<td><span data-ttu-id="1230f-790">Personal</span><span class="sxs-lookup"><span data-stu-id="1230f-790">HR</span></span></td>
<td><span data-ttu-id="1230f-791">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-791">10001</span></span></td>
<td><span data-ttu-id="1230f-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-792">Electricity</span></span></td>
<td><span data-ttu-id="1230f-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-793">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="1230f-794">-1,245.71</span></span></td>
<td><span data-ttu-id="1230f-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-796">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-796">CC002</span></span></td>
<td><span data-ttu-id="1230f-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-797">Finance</span></span></td>
<td><span data-ttu-id="1230f-798">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-798">10001</span></span></td>
<td><span data-ttu-id="1230f-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-799">Electricity</span></span></td>
<td><span data-ttu-id="1230f-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-800">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-801">436.00</span><span class="sxs-lookup"><span data-stu-id="1230f-801">436.00</span></span></td>
<td><span data-ttu-id="1230f-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-803">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-803">CC003</span></span></td>
<td><span data-ttu-id="1230f-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-804">Assembly</span></span></td>
<td><span data-ttu-id="1230f-805">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-805">10001</span></span></td>
<td><span data-ttu-id="1230f-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-806">Electricity</span></span></td>
<td><span data-ttu-id="1230f-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-807">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-808">685.14</span><span class="sxs-lookup"><span data-stu-id="1230f-808">685.14</span></span></td>
<td><span data-ttu-id="1230f-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-810">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-810">CC004</span></span></td>
<td><span data-ttu-id="1230f-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-811">Packaging</span></span></td>
<td><span data-ttu-id="1230f-812">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-812">10001</span></span></td>
<td><span data-ttu-id="1230f-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-813">Electricity</span></span></td>
<td><span data-ttu-id="1230f-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-814">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-815">124.57</span><span class="sxs-lookup"><span data-stu-id="1230f-815">124.57</span></span></td>
<td><span data-ttu-id="1230f-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-817">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-817">CC002</span></span></td>
<td><span data-ttu-id="1230f-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-818">Finance</span></span></td>
<td><span data-ttu-id="1230f-819">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-819">10001</span></span></td>
<td><span data-ttu-id="1230f-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-820">Electricity</span></span></td>
<td><span data-ttu-id="1230f-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-821">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="1230f-822">-675.00</span></span></td>
<td><span data-ttu-id="1230f-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-824">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-824">CC003</span></span></td>
<td><span data-ttu-id="1230f-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-825">Assembly</span></span></td>
<td><span data-ttu-id="1230f-826">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-826">10001</span></span></td>
<td><span data-ttu-id="1230f-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-827">Electricity</span></span></td>
<td><span data-ttu-id="1230f-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-828">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-829">438.75</span><span class="sxs-lookup"><span data-stu-id="1230f-829">438.75</span></span></td>
<td><span data-ttu-id="1230f-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-831">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-831">CC004</span></span></td>
<td><span data-ttu-id="1230f-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-832">Packaging</span></span></td>
<td><span data-ttu-id="1230f-833">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-833">10001</span></span></td>
<td><span data-ttu-id="1230f-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-834">Electricity</span></span></td>
<td><span data-ttu-id="1230f-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-835">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-836">236.25</span><span class="sxs-lookup"><span data-stu-id="1230f-836">236.25</span></span></td>
<td><span data-ttu-id="1230f-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-838">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-838">CC002</span></span></td>
<td><span data-ttu-id="1230f-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1230f-839">Finance</span></span></td>
<td><span data-ttu-id="1230f-840">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-840">10001</span></span></td>
<td><span data-ttu-id="1230f-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-841">Electricity</span></span></td>
<td><span data-ttu-id="1230f-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-842">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="1230f-843">-8,150.29</span></span></td>
<td><span data-ttu-id="1230f-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-845">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-845">CC003</span></span></td>
<td><span data-ttu-id="1230f-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-846">Assembly</span></span></td>
<td><span data-ttu-id="1230f-847">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-847">10001</span></span></td>
<td><span data-ttu-id="1230f-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-848">Electricity</span></span></td>
<td><span data-ttu-id="1230f-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-849">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1230f-850">5,297.69</span></span></td>
<td><span data-ttu-id="1230f-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-852">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-852">CC004</span></span></td>
<td><span data-ttu-id="1230f-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="1230f-853">Packaging</span></span></td>
<td><span data-ttu-id="1230f-854">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-854">10001</span></span></td>
<td><span data-ttu-id="1230f-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-855">Electricity</span></span></td>
<td><span data-ttu-id="1230f-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-856">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1230f-857">2,852.60</span></span></td>
<td><span data-ttu-id="1230f-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-859">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-859">CC003</span></span></td>
<td><span data-ttu-id="1230f-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-860">Assembly</span></span></td>
<td><span data-ttu-id="1230f-861">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-861">10001</span></span></td>
<td><span data-ttu-id="1230f-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-862">Electricity</span></span></td>
<td><span data-ttu-id="1230f-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-863">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="1230f-864">-713.75</span></span></td>
<td><span data-ttu-id="1230f-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-866">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-867">Product 1</span></span></td>
<td><span data-ttu-id="1230f-868">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-868">10001</span></span></td>
<td><span data-ttu-id="1230f-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-869">Electricity</span></span></td>
<td><span data-ttu-id="1230f-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-870">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-871">535.31</span><span class="sxs-lookup"><span data-stu-id="1230f-871">535.31</span></span></td>
<td><span data-ttu-id="1230f-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-873">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-874">Product 2</span></span></td>
<td><span data-ttu-id="1230f-875">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-875">10001</span></span></td>
<td><span data-ttu-id="1230f-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-876">Electricity</span></span></td>
<td><span data-ttu-id="1230f-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-877">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-878">178.44</span><span class="sxs-lookup"><span data-stu-id="1230f-878">178.44</span></span></td>
<td><span data-ttu-id="1230f-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-880">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-880">CC003</span></span></td>
<td><span data-ttu-id="1230f-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-881">Assembly</span></span></td>
<td><span data-ttu-id="1230f-882">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-882">10001</span></span></td>
<td><span data-ttu-id="1230f-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-883">Electricity</span></span></td>
<td><span data-ttu-id="1230f-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-884">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="1230f-885">-5,982.83</span></span></td>
<td><span data-ttu-id="1230f-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-887">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-888">Product 1</span></span></td>
<td><span data-ttu-id="1230f-889">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-889">10001</span></span></td>
<td><span data-ttu-id="1230f-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-890">Electricity</span></span></td>
<td><span data-ttu-id="1230f-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-891">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1230f-892">4,487.12</span></span></td>
<td><span data-ttu-id="1230f-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-894">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-895">Product 2</span></span></td>
<td><span data-ttu-id="1230f-896">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-896">10001</span></span></td>
<td><span data-ttu-id="1230f-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-897">Electricity</span></span></td>
<td><span data-ttu-id="1230f-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-898">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1230f-899">1,495.71</span></span></td>
<td><span data-ttu-id="1230f-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-901">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-901">CC003</span></span></td>
<td><span data-ttu-id="1230f-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-902">Assembly</span></span></td>
<td><span data-ttu-id="1230f-903">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-903">10001</span></span></td>
<td><span data-ttu-id="1230f-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-904">Electricity</span></span></td>
<td><span data-ttu-id="1230f-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-905">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="1230f-906">-286.25</span></span></td>
<td><span data-ttu-id="1230f-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-908">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-909">Product 1</span></span></td>
<td><span data-ttu-id="1230f-910">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-910">10001</span></span></td>
<td><span data-ttu-id="1230f-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-911">Electricity</span></span></td>
<td><span data-ttu-id="1230f-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-912">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-913">241.05</span><span class="sxs-lookup"><span data-stu-id="1230f-913">241.05</span></span></td>
<td><span data-ttu-id="1230f-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-915">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-916">Product 2</span></span></td>
<td><span data-ttu-id="1230f-917">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-917">10001</span></span></td>
<td><span data-ttu-id="1230f-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-918">Electricity</span></span></td>
<td><span data-ttu-id="1230f-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-919">Fixed cost</span></span></td>
<td><span data-ttu-id="1230f-920">45.20</span><span class="sxs-lookup"><span data-stu-id="1230f-920">45.20</span></span></td>
<td><span data-ttu-id="1230f-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-922">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-922">CC003</span></span></td>
<td><span data-ttu-id="1230f-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1230f-923">Assembly</span></span></td>
<td><span data-ttu-id="1230f-924">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-924">10001</span></span></td>
<td><span data-ttu-id="1230f-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-925">Electricity</span></span></td>
<td><span data-ttu-id="1230f-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-926">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="1230f-927">-2,977.17</span></span></td>
<td><span data-ttu-id="1230f-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-929">Prod 1</span></span></td>
<td><span data-ttu-id="1230f-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1230f-930">Product 1</span></span></td>
<td><span data-ttu-id="1230f-931">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-931">10001</span></span></td>
<td><span data-ttu-id="1230f-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-932">Electricity</span></span></td>
<td><span data-ttu-id="1230f-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-933">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1230f-934">2,507.09</span></span></td>
<td><span data-ttu-id="1230f-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1230f-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-936">Prod 2</span></span></td>
<td><span data-ttu-id="1230f-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1230f-937">Product 2</span></span></td>
<td><span data-ttu-id="1230f-938">10001</span><span class="sxs-lookup"><span data-stu-id="1230f-938">10001</span></span></td>
<td><span data-ttu-id="1230f-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-939">Electricity</span></span></td>
<td><span data-ttu-id="1230f-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-940">Variable cost</span></span></td>
<td><span data-ttu-id="1230f-941">470.08</span><span class="sxs-lookup"><span data-stu-id="1230f-941">470.08</span></span></td>
<td><span data-ttu-id="1230f-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1230f-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="1230f-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="1230f-943">Conclusion</span></span>
<span data-ttu-id="1230f-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="1230f-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="1230f-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="1230f-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="1230f-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1230f-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="1230f-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1230f-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="1230f-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1230f-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="1230f-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1230f-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="1230f-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="1230f-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="1230f-951">CC099</span><span class="sxs-lookup"><span data-stu-id="1230f-951">CC099</span></span></th>
<th><span data-ttu-id="1230f-952">CC001</span><span class="sxs-lookup"><span data-stu-id="1230f-952">CC001</span></span></th>
<th><span data-ttu-id="1230f-953">CC002</span><span class="sxs-lookup"><span data-stu-id="1230f-953">CC002</span></span></th>
<th><span data-ttu-id="1230f-954">CC003</span><span class="sxs-lookup"><span data-stu-id="1230f-954">CC003</span></span></th>
<th><span data-ttu-id="1230f-955">CC004</span><span class="sxs-lookup"><span data-stu-id="1230f-955">CC004</span></span></th>
<th><span data-ttu-id="1230f-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1230f-956">Proj 1</span></span></th>
<th><span data-ttu-id="1230f-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1230f-957">Proj 2</span></span></th>
<th><span data-ttu-id="1230f-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1230f-958">Prod 1</span></span></th>
<th><span data-ttu-id="1230f-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1230f-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="1230f-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1230f-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1230f-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="1230f-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1230f-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-971">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="1230f-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-973">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-974">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-975">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-976">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-977">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1230f-978">776.36</span><span class="sxs-lookup"><span data-stu-id="1230f-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-979">223.64</span><span class="sxs-lookup"><span data-stu-id="1230f-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="1230f-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1230f-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-982">000</span><span class="sxs-lookup"><span data-stu-id="1230f-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-983">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-984">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-985">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-986">0,00</span><span class="sxs-lookup"><span data-stu-id="1230f-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-987">30,00</span><span class="sxs-lookup"><span data-stu-id="1230f-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-988">10,00</span><span class="sxs-lookup"><span data-stu-id="1230f-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1230f-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1230f-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1230f-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1230f-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1230f-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="1230f-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="1230f-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1230f-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="1230f-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1230f-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="1230f-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1230f-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="1230f-996">Mer information finns i [Policy för samlade kostnader och omkostnadsberäkning](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="1230f-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



