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
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841499"
---
# <a name="overhead-calculation"></a><span data-ttu-id="1f2ab-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="1f2ab-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f2ab-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="1f2ab-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="1f2ab-105">Term definition</span></span>
---------------

<span data-ttu-id="1f2ab-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="1f2ab-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="1f2ab-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="1f2ab-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="1f2ab-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="1f2ab-109">Rent</span></span>
-   <span data-ttu-id="1f2ab-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-110">Electricity</span></span>
-   <span data-ttu-id="1f2ab-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="1f2ab-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="1f2ab-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="1f2ab-112">Overhead calculation overview</span></span>
<span data-ttu-id="1f2ab-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="1f2ab-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="1f2ab-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="1f2ab-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="1f2ab-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="1f2ab-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="1f2ab-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="1f2ab-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-119">Version type</span></span>
-   <span data-ttu-id="1f2ab-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="1f2ab-120">Date and time</span></span>
-   <span data-ttu-id="1f2ab-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="1f2ab-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="1f2ab-122">Fiscal year</span></span>
-   <span data-ttu-id="1f2ab-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="1f2ab-123">Fiscal period</span></span>

<span data-ttu-id="1f2ab-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="1f2ab-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="1f2ab-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="1f2ab-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="1f2ab-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="1f2ab-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="1f2ab-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="1f2ab-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="1f2ab-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="1f2ab-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="1f2ab-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="1f2ab-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="1f2ab-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="1f2ab-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="1f2ab-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="1f2ab-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="1f2ab-140">Main account</span></span></th>
<th><span data-ttu-id="1f2ab-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="1f2ab-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-143">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-143">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-144">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-145">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-145">10001</span></span></td>
<td><span data-ttu-id="1f2ab-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-146">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="1f2ab-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="1f2ab-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="1f2ab-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="1f2ab-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="1f2ab-151">Define the cost behavior rule</span></span>

<span data-ttu-id="1f2ab-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="1f2ab-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="1f2ab-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="1f2ab-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="1f2ab-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="1f2ab-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="1f2ab-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="1f2ab-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="1f2ab-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="1f2ab-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="1f2ab-159">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-160">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-160">Journal</span></span></th>
<th><span data-ttu-id="1f2ab-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1f2ab-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1f2ab-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1f2ab-163">version</span><span class="sxs-lookup"><span data-stu-id="1f2ab-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-164">00001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-164">00001</span></span></td>
<td><span data-ttu-id="1f2ab-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="1f2ab-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-166">Fiscal</span></span></td>
<td><span data-ttu-id="1f2ab-167">2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-167">2017</span></span></td>
<td><span data-ttu-id="1f2ab-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-168">Period 1</span></span></td>
<td><span data-ttu-id="1f2ab-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1f2ab-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-173">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-174">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-177">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-177">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-178">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-179">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-179">10001</span></span></td>
<td><span data-ttu-id="1f2ab-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-180">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1f2ab-181">Unclassified</span></span></td>
<td><span data-ttu-id="1f2ab-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1f2ab-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-185">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-186">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-187">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-189">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-189">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-190">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-191">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-191">10001</span></span></td>
<td><span data-ttu-id="1f2ab-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-192">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1f2ab-193">Unclassified</span></span></td>
<td><span data-ttu-id="1f2ab-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-194">10,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-196">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-196">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-197">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-198">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-198">10001</span></span></td>
<td><span data-ttu-id="1f2ab-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-199">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1f2ab-200">Unclassified</span></span></td>
<td><span data-ttu-id="1f2ab-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-201">-10,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-203">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-203">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-204">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-205">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-205">10001</span></span></td>
<td><span data-ttu-id="1f2ab-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-206">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-207">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-208">1,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-210">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-210">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-211">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-212">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-212">10001</span></span></td>
<td><span data-ttu-id="1f2ab-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-213">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-214">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-215">9,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="1f2ab-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="1f2ab-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="1f2ab-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="1f2ab-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="1f2ab-221">Define the cost distribution rule</span></span>

<span data-ttu-id="1f2ab-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="1f2ab-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="1f2ab-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="1f2ab-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="1f2ab-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="1f2ab-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-228">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="1f2ab-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-230">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-230">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-231">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-231">HR</span></span></td>
<td><span data-ttu-id="1f2ab-232">1 000</span><span class="sxs-lookup"><span data-stu-id="1f2ab-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-233">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-233">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-234">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-235">6,000</span><span class="sxs-lookup"><span data-stu-id="1f2ab-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-236">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-236">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-237">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-238">0</span><span class="sxs-lookup"><span data-stu-id="1f2ab-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-240">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-241">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-242">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-244">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-244">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-245">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-245">HR</span></span></td>
<td><span data-ttu-id="1f2ab-246">1 000</span><span class="sxs-lookup"><span data-stu-id="1f2ab-246">1,000</span></span></td>
<td><span data-ttu-id="1f2ab-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-249">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-249">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-250">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-251">6,000</span><span class="sxs-lookup"><span data-stu-id="1f2ab-251">6,000</span></span></td>
<td><span data-ttu-id="1f2ab-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1f2ab-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-254">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-254">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-255">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-256">0</span><span class="sxs-lookup"><span data-stu-id="1f2ab-256">0</span></span></td>
<td><span data-ttu-id="1f2ab-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-258">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="1f2ab-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-261">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-262">Formel</span><span class="sxs-lookup"><span data-stu-id="1f2ab-262">Formula</span></span></th>
<th><span data-ttu-id="1f2ab-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-263">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-264">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-266">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-266">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-267">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-267">HR</span></span></td>
<td><span data-ttu-id="1f2ab-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1f2ab-269">1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-269">1</span></span></td>
<td><span data-ttu-id="1f2ab-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-271">500.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-272">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-272">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-273">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1f2ab-275">1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-275">1</span></span></td>
<td><span data-ttu-id="1f2ab-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-277">500.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-278">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-278">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-279">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1f2ab-281">0</span><span class="sxs-lookup"><span data-stu-id="1f2ab-281">0</span></span></td>
<td><span data-ttu-id="1f2ab-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-283">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1f2ab-284">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-285">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-285">Journal</span></span></th>
<th><span data-ttu-id="1f2ab-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1f2ab-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1f2ab-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1f2ab-288">version</span><span class="sxs-lookup"><span data-stu-id="1f2ab-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-289">00002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-289">00002</span></span></td>
<td><span data-ttu-id="1f2ab-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="1f2ab-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-291">Fiscal</span></span></td>
<td><span data-ttu-id="1f2ab-292">2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-292">2017</span></span></td>
<td><span data-ttu-id="1f2ab-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-293">Period 1</span></span></td>
<td><span data-ttu-id="1f2ab-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1f2ab-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-298">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-299">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-302">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-302">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-303">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-304">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-304">10001</span></span></td>
<td><span data-ttu-id="1f2ab-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-305">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-306">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-309">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-309">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-310">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-311">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-311">10001</span></span></td>
<td><span data-ttu-id="1f2ab-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-312">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-313">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1f2ab-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-317">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-318">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-319">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-321">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-321">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-322">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-323">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-323">10001</span></span></td>
<td><span data-ttu-id="1f2ab-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-324">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-325">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-326">-1,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-328">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-328">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-329">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-329">HR</span></span></td>
<td><span data-ttu-id="1f2ab-330">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-330">10001</span></span></td>
<td><span data-ttu-id="1f2ab-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-331">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-332">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-333">500.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-333">500.00</span></span></td>
<td><span data-ttu-id="1f2ab-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-335">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-335">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-336">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-337">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-337">10001</span></span></td>
<td><span data-ttu-id="1f2ab-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-338">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-339">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-340">500.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-340">500.00</span></span></td>
<td><span data-ttu-id="1f2ab-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-342">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-342">CC099</span></span></td>
<td><span data-ttu-id="1f2ab-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-343">Default cost center</span></span></td>
<td><span data-ttu-id="1f2ab-344">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-344">10001</span></span></td>
<td><span data-ttu-id="1f2ab-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-345">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-346">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-347">-9,000.00</span></span></td>
<td><span data-ttu-id="1f2ab-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-349">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-349">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-350">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-350">HR</span></span></td>
<td><span data-ttu-id="1f2ab-351">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-351">10001</span></span></td>
<td><span data-ttu-id="1f2ab-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-352">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-353">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-354">1,285.71</span></span></td>
<td><span data-ttu-id="1f2ab-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-356">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-356">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-357">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-358">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-358">10001</span></span></td>
<td><span data-ttu-id="1f2ab-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-359">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-360">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1f2ab-361">7,714.29</span></span></td>
<td><span data-ttu-id="1f2ab-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="1f2ab-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="1f2ab-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="1f2ab-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="1f2ab-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-367">Define the overhead rate</span></span>

<span data-ttu-id="1f2ab-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="1f2ab-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-370">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="1f2ab-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-372">Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-373">Project 1</span></span></td>
<td><span data-ttu-id="1f2ab-374">3</span><span class="sxs-lookup"><span data-stu-id="1f2ab-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-375">Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-376">Project 2</span></span></td>
<td><span data-ttu-id="1f2ab-377">1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-379">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-380">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-381">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-382">Units</span></span></th>
<th><span data-ttu-id="1f2ab-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="1f2ab-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-384">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-384">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-385">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-385">HR</span></span></td>
<td><span data-ttu-id="1f2ab-386">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-386">10001</span></span></td>
<td><span data-ttu-id="1f2ab-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-387">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-388">1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-388">1</span></span></td>
<td><span data-ttu-id="1f2ab-389">10</span><span class="sxs-lookup"><span data-stu-id="1f2ab-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-391">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-392">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-393">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-394">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-396">Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-397">Project 1</span></span></td>
<td><span data-ttu-id="1f2ab-398">3</span><span class="sxs-lookup"><span data-stu-id="1f2ab-398">3</span></span></td>
<td><span data-ttu-id="1f2ab-399">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-399">10001</span></span></td>
<td><span data-ttu-id="1f2ab-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1f2ab-401">30,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-402">Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-403">Project 2</span></span></td>
<td><span data-ttu-id="1f2ab-404">1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-404">1</span></span></td>
<td><span data-ttu-id="1f2ab-405">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-405">10001</span></span></td>
<td><span data-ttu-id="1f2ab-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1f2ab-407">10,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1f2ab-408">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-409">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-409">Journal</span></span></th>
<th><span data-ttu-id="1f2ab-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1f2ab-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1f2ab-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1f2ab-412">version</span><span class="sxs-lookup"><span data-stu-id="1f2ab-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-413">00003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-413">00003</span></span></td>
<td><span data-ttu-id="1f2ab-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="1f2ab-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-415">Fiscal</span></span></td>
<td><span data-ttu-id="1f2ab-416">2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-416">2017</span></span></td>
<td><span data-ttu-id="1f2ab-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-417">Period 1</span></span></td>
<td><span data-ttu-id="1f2ab-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="1f2ab-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-421">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-424">Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-426">3,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-428">Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-430">1,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1f2ab-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-433">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-434">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-435">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-437">CC0001</span></span></td>
<td><span data-ttu-id="1f2ab-438">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-438">HR</span></span></td>
<td><span data-ttu-id="1f2ab-439">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-439">10001</span></span></td>
<td><span data-ttu-id="1f2ab-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-440">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-441">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-442">-30.00</span></span></td>
<td><span data-ttu-id="1f2ab-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-444">Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1f2ab-446">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-446">10001</span></span></td>
<td><span data-ttu-id="1f2ab-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-447">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-448">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-449">30,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-449">30.00</span></span></td>
<td><span data-ttu-id="1f2ab-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-451">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-451">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-452">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-452">HR</span></span></td>
<td><span data-ttu-id="1f2ab-453">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-453">10001</span></span></td>
<td><span data-ttu-id="1f2ab-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-454">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-455">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-456">-10.00</span></span></td>
<td><span data-ttu-id="1f2ab-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-458">Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1f2ab-460">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-460">10001</span></span></td>
<td><span data-ttu-id="1f2ab-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-461">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-462">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-463">10,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-463">10.00</span></span></td>
<td><span data-ttu-id="1f2ab-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="1f2ab-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="1f2ab-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="1f2ab-468">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="1f2ab-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="1f2ab-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="1f2ab-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="1f2ab-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="1f2ab-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="1f2ab-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="1f2ab-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-475">Define the cost allocation</span></span>

<span data-ttu-id="1f2ab-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="1f2ab-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="1f2ab-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-479">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="1f2ab-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-481">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-481">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-482">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-483">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-484">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-484">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-485">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-486">55</span><span class="sxs-lookup"><span data-stu-id="1f2ab-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-487">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-487">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-488">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-489">10</span><span class="sxs-lookup"><span data-stu-id="1f2ab-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="1f2ab-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-492">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="1f2ab-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-494">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-494">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-495">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-496">65</span><span class="sxs-lookup"><span data-stu-id="1f2ab-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-497">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-497">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-498">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-499">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="1f2ab-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-502">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-504">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-505">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-506">60</span><span class="sxs-lookup"><span data-stu-id="1f2ab-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-507">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-508">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-509">20</span><span class="sxs-lookup"><span data-stu-id="1f2ab-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="1f2ab-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-512">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-514">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-515">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-516">80</span><span class="sxs-lookup"><span data-stu-id="1f2ab-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-517">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-518">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-519">15</span><span class="sxs-lookup"><span data-stu-id="1f2ab-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1f2ab-520">I Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="1f2ab-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="1f2ab-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-523">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-524">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-525">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-526">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-528">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-528">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-529">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-530">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-530">35</span></span></td>
<td><span data-ttu-id="1f2ab-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1f2ab-532">175.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-532">175.00</span></span></td>
<td><span data-ttu-id="1f2ab-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-534">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-534">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-535">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-536">55</span><span class="sxs-lookup"><span data-stu-id="1f2ab-536">55</span></span></td>
<td><span data-ttu-id="1f2ab-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1f2ab-538">275.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-538">275.00</span></span></td>
<td><span data-ttu-id="1f2ab-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-540">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-540">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-541">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-542">10</span><span class="sxs-lookup"><span data-stu-id="1f2ab-542">10</span></span></td>
<td><span data-ttu-id="1f2ab-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1f2ab-544">50,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-544">50.00</span></span></td>
<td><span data-ttu-id="1f2ab-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-546">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-546">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-547">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-548">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-548">35</span></span></td>
<td><span data-ttu-id="1f2ab-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1f2ab-550">436.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-550">436.00</span></span></td>
<td><span data-ttu-id="1f2ab-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-552">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-552">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-553">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-554">55</span><span class="sxs-lookup"><span data-stu-id="1f2ab-554">55</span></span></td>
<td><span data-ttu-id="1f2ab-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1f2ab-556">685.14</span><span class="sxs-lookup"><span data-stu-id="1f2ab-556">685.14</span></span></td>
<td><span data-ttu-id="1f2ab-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-558">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-558">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-559">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-560">10</span><span class="sxs-lookup"><span data-stu-id="1f2ab-560">10</span></span></td>
<td><span data-ttu-id="1f2ab-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1f2ab-562">124.57</span><span class="sxs-lookup"><span data-stu-id="1f2ab-562">124.57</span></span></td>
<td><span data-ttu-id="1f2ab-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-565">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-566">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-567">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-568">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-570">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-570">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-571">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-572">65</span><span class="sxs-lookup"><span data-stu-id="1f2ab-572">65</span></span></td>
<td><span data-ttu-id="1f2ab-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1f2ab-574">438.75</span><span class="sxs-lookup"><span data-stu-id="1f2ab-574">438.75</span></span></td>
<td><span data-ttu-id="1f2ab-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-576">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-576">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-577">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-578">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-578">35</span></span></td>
<td><span data-ttu-id="1f2ab-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1f2ab-580">236.25</span><span class="sxs-lookup"><span data-stu-id="1f2ab-580">236.25</span></span></td>
<td><span data-ttu-id="1f2ab-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-582">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-582">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-583">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-584">65</span><span class="sxs-lookup"><span data-stu-id="1f2ab-584">65</span></span></td>
<td><span data-ttu-id="1f2ab-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1f2ab-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1f2ab-586">5,297.69</span></span></td>
<td><span data-ttu-id="1f2ab-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-588">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-588">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-589">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-590">35</span><span class="sxs-lookup"><span data-stu-id="1f2ab-590">35</span></span></td>
<td><span data-ttu-id="1f2ab-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1f2ab-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1f2ab-592">2,852.60</span></span></td>
<td><span data-ttu-id="1f2ab-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-595">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-596">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-597">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-598">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-600">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-601">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-602">60</span><span class="sxs-lookup"><span data-stu-id="1f2ab-602">60</span></span></td>
<td><span data-ttu-id="1f2ab-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1f2ab-604">535.31</span><span class="sxs-lookup"><span data-stu-id="1f2ab-604">535.31</span></span></td>
<td><span data-ttu-id="1f2ab-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-606">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-607">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-608">20</span><span class="sxs-lookup"><span data-stu-id="1f2ab-608">20</span></span></td>
<td><span data-ttu-id="1f2ab-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1f2ab-610">178.44</span><span class="sxs-lookup"><span data-stu-id="1f2ab-610">178.44</span></span></td>
<td><span data-ttu-id="1f2ab-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-612">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-613">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-614">60</span><span class="sxs-lookup"><span data-stu-id="1f2ab-614">60</span></span></td>
<td><span data-ttu-id="1f2ab-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1f2ab-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1f2ab-616">4,487.12</span></span></td>
<td><span data-ttu-id="1f2ab-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-618">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-619">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-620">20</span><span class="sxs-lookup"><span data-stu-id="1f2ab-620">20</span></span></td>
<td><span data-ttu-id="1f2ab-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1f2ab-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-622">1,495.71</span></span></td>
<td><span data-ttu-id="1f2ab-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1f2ab-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-625">Cost object</span></span></th>
<th><span data-ttu-id="1f2ab-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="1f2ab-626">Magnitude</span></span></th>
<th><span data-ttu-id="1f2ab-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="1f2ab-627">Allocation factor</span></span></th>
<th><span data-ttu-id="1f2ab-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-628">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-630">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-631">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-632">80</span><span class="sxs-lookup"><span data-stu-id="1f2ab-632">80</span></span></td>
<td><span data-ttu-id="1f2ab-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1f2ab-634">241.05</span><span class="sxs-lookup"><span data-stu-id="1f2ab-634">241.05</span></span></td>
<td><span data-ttu-id="1f2ab-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-636">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-637">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-638">15</span><span class="sxs-lookup"><span data-stu-id="1f2ab-638">15</span></span></td>
<td><span data-ttu-id="1f2ab-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1f2ab-640">45.20</span><span class="sxs-lookup"><span data-stu-id="1f2ab-640">45.20</span></span></td>
<td><span data-ttu-id="1f2ab-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-642">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-643">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-644">80</span><span class="sxs-lookup"><span data-stu-id="1f2ab-644">80</span></span></td>
<td><span data-ttu-id="1f2ab-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1f2ab-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1f2ab-646">2,507.09</span></span></td>
<td><span data-ttu-id="1f2ab-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-648">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-649">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-650">15</span><span class="sxs-lookup"><span data-stu-id="1f2ab-650">15</span></span></td>
<td><span data-ttu-id="1f2ab-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1f2ab-652">470.08</span><span class="sxs-lookup"><span data-stu-id="1f2ab-652">470.08</span></span></td>
<td><span data-ttu-id="1f2ab-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1f2ab-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="1f2ab-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-655">Journal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-655">Journal</span></span></th>
<th><span data-ttu-id="1f2ab-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1f2ab-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="1f2ab-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1f2ab-658">version</span><span class="sxs-lookup"><span data-stu-id="1f2ab-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-659">00004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-659">00004</span></span></td>
<td><span data-ttu-id="1f2ab-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="1f2ab-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-661">Fiscal</span></span></td>
<td><span data-ttu-id="1f2ab-662">2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-662">2017</span></span></td>
<td><span data-ttu-id="1f2ab-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-663">Period 1</span></span></td>
<td><span data-ttu-id="1f2ab-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="1f2ab-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="1f2ab-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1f2ab-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-668">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-669">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-672">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-672">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-673">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-673">HR</span></span></td>
<td><span data-ttu-id="1f2ab-674">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-674">10001</span></span></td>
<td><span data-ttu-id="1f2ab-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-675">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-676">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-677">500.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-679">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-679">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-680">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-680">HR</span></span></td>
<td><span data-ttu-id="1f2ab-681">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-681">10001</span></span></td>
<td><span data-ttu-id="1f2ab-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-682">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-683">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-686">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-686">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-687">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-688">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-688">10001</span></span></td>
<td><span data-ttu-id="1f2ab-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-689">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-690">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-691">675.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-693">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-693">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-694">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-695">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-695">10001</span></span></td>
<td><span data-ttu-id="1f2ab-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-696">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-697">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="1f2ab-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-700">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-700">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-701">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-702">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-702">10001</span></span></td>
<td><span data-ttu-id="1f2ab-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-703">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-704">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-705">713.75</span><span class="sxs-lookup"><span data-stu-id="1f2ab-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-707">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-707">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-708">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-709">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-709">10001</span></span></td>
<td><span data-ttu-id="1f2ab-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-710">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-711">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="1f2ab-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-714">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-714">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-715">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-716">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-716">10001</span></span></td>
<td><span data-ttu-id="1f2ab-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-717">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-718">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-719">286.25</span><span class="sxs-lookup"><span data-stu-id="1f2ab-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-721">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-721">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-722">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-723">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-723">10001</span></span></td>
<td><span data-ttu-id="1f2ab-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-724">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-725">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="1f2ab-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-728">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-729">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-730">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-730">10001</span></span></td>
<td><span data-ttu-id="1f2ab-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-731">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-732">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-733">776.36</span><span class="sxs-lookup"><span data-stu-id="1f2ab-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-735">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-736">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-737">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-737">10001</span></span></td>
<td><span data-ttu-id="1f2ab-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-738">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-739">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1f2ab-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-742">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-743">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-744">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-744">10001</span></span></td>
<td><span data-ttu-id="1f2ab-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-745">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-746">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-747">223.64</span><span class="sxs-lookup"><span data-stu-id="1f2ab-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="1f2ab-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-749">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-750">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-751">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-751">10001</span></span></td>
<td><span data-ttu-id="1f2ab-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-752">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-753">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1f2ab-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1f2ab-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="1f2ab-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1f2ab-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1f2ab-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-757">Cost element</span></span></th>
<th><span data-ttu-id="1f2ab-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="1f2ab-758">Cost behavior</span></span></th>
<th><span data-ttu-id="1f2ab-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="1f2ab-759">Amount</span></span></th>
<th><span data-ttu-id="1f2ab-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="1f2ab-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1f2ab-761">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-761">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-762">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-762">HR</span></span></td>
<td><span data-ttu-id="1f2ab-763">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-763">10001</span></span></td>
<td><span data-ttu-id="1f2ab-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-764">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-765">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-766">-500.00</span></span></td>
<td><span data-ttu-id="1f2ab-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-768">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-768">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-769">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-770">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-770">10001</span></span></td>
<td><span data-ttu-id="1f2ab-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-771">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-772">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-773">175.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-773">175.00</span></span></td>
<td><span data-ttu-id="1f2ab-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-775">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-775">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-776">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-777">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-777">10001</span></span></td>
<td><span data-ttu-id="1f2ab-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-778">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-779">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-780">275.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-780">275.00</span></span></td>
<td><span data-ttu-id="1f2ab-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-782">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-782">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-783">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-784">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-784">10001</span></span></td>
<td><span data-ttu-id="1f2ab-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-785">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-786">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-787">50,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-787">50,00</span></span></td>
<td><span data-ttu-id="1f2ab-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-789">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-789">CC001</span></span></td>
<td><span data-ttu-id="1f2ab-790">Personal</span><span class="sxs-lookup"><span data-stu-id="1f2ab-790">HR</span></span></td>
<td><span data-ttu-id="1f2ab-791">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-791">10001</span></span></td>
<td><span data-ttu-id="1f2ab-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-792">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-793">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-794">-1,245.71</span></span></td>
<td><span data-ttu-id="1f2ab-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-796">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-796">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-797">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-798">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-798">10001</span></span></td>
<td><span data-ttu-id="1f2ab-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-799">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-800">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-801">436.00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-801">436.00</span></span></td>
<td><span data-ttu-id="1f2ab-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-803">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-803">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-804">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-805">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-805">10001</span></span></td>
<td><span data-ttu-id="1f2ab-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-806">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-807">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-808">685.14</span><span class="sxs-lookup"><span data-stu-id="1f2ab-808">685.14</span></span></td>
<td><span data-ttu-id="1f2ab-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-810">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-810">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-811">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-812">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-812">10001</span></span></td>
<td><span data-ttu-id="1f2ab-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-813">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-814">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-815">124.57</span><span class="sxs-lookup"><span data-stu-id="1f2ab-815">124.57</span></span></td>
<td><span data-ttu-id="1f2ab-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-817">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-817">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-818">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-819">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-819">10001</span></span></td>
<td><span data-ttu-id="1f2ab-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-820">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-821">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-822">-675.00</span></span></td>
<td><span data-ttu-id="1f2ab-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-824">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-824">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-825">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-826">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-826">10001</span></span></td>
<td><span data-ttu-id="1f2ab-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-827">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-828">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-829">438.75</span><span class="sxs-lookup"><span data-stu-id="1f2ab-829">438.75</span></span></td>
<td><span data-ttu-id="1f2ab-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-831">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-831">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-832">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-833">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-833">10001</span></span></td>
<td><span data-ttu-id="1f2ab-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-834">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-835">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-836">236.25</span><span class="sxs-lookup"><span data-stu-id="1f2ab-836">236.25</span></span></td>
<td><span data-ttu-id="1f2ab-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-838">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-838">CC002</span></span></td>
<td><span data-ttu-id="1f2ab-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-839">Finance</span></span></td>
<td><span data-ttu-id="1f2ab-840">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-840">10001</span></span></td>
<td><span data-ttu-id="1f2ab-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-841">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-842">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="1f2ab-843">-8,150.29</span></span></td>
<td><span data-ttu-id="1f2ab-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-845">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-845">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-846">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-847">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-847">10001</span></span></td>
<td><span data-ttu-id="1f2ab-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-848">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-849">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1f2ab-850">5,297.69</span></span></td>
<td><span data-ttu-id="1f2ab-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-852">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-852">CC004</span></span></td>
<td><span data-ttu-id="1f2ab-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="1f2ab-853">Packaging</span></span></td>
<td><span data-ttu-id="1f2ab-854">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-854">10001</span></span></td>
<td><span data-ttu-id="1f2ab-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-855">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-856">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1f2ab-857">2,852.60</span></span></td>
<td><span data-ttu-id="1f2ab-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-859">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-859">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-860">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-861">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-861">10001</span></span></td>
<td><span data-ttu-id="1f2ab-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-862">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-863">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="1f2ab-864">-713.75</span></span></td>
<td><span data-ttu-id="1f2ab-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-866">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-867">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-868">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-868">10001</span></span></td>
<td><span data-ttu-id="1f2ab-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-869">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-870">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-871">535.31</span><span class="sxs-lookup"><span data-stu-id="1f2ab-871">535.31</span></span></td>
<td><span data-ttu-id="1f2ab-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-873">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-874">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-875">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-875">10001</span></span></td>
<td><span data-ttu-id="1f2ab-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-876">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-877">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-878">178.44</span><span class="sxs-lookup"><span data-stu-id="1f2ab-878">178.44</span></span></td>
<td><span data-ttu-id="1f2ab-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-880">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-880">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-881">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-882">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-882">10001</span></span></td>
<td><span data-ttu-id="1f2ab-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-883">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-884">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="1f2ab-885">-5,982.83</span></span></td>
<td><span data-ttu-id="1f2ab-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-887">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-888">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-889">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-889">10001</span></span></td>
<td><span data-ttu-id="1f2ab-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-890">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-891">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1f2ab-892">4,487.12</span></span></td>
<td><span data-ttu-id="1f2ab-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-894">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-895">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-896">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-896">10001</span></span></td>
<td><span data-ttu-id="1f2ab-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-897">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-898">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1f2ab-899">1,495.71</span></span></td>
<td><span data-ttu-id="1f2ab-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-901">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-901">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-902">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-903">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-903">10001</span></span></td>
<td><span data-ttu-id="1f2ab-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-904">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-905">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="1f2ab-906">-286.25</span></span></td>
<td><span data-ttu-id="1f2ab-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-908">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-909">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-910">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-910">10001</span></span></td>
<td><span data-ttu-id="1f2ab-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-911">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-912">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-913">241.05</span><span class="sxs-lookup"><span data-stu-id="1f2ab-913">241.05</span></span></td>
<td><span data-ttu-id="1f2ab-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-915">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-916">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-917">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-917">10001</span></span></td>
<td><span data-ttu-id="1f2ab-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-918">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-919">Fixed cost</span></span></td>
<td><span data-ttu-id="1f2ab-920">45.20</span><span class="sxs-lookup"><span data-stu-id="1f2ab-920">45.20</span></span></td>
<td><span data-ttu-id="1f2ab-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-922">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-922">CC003</span></span></td>
<td><span data-ttu-id="1f2ab-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="1f2ab-923">Assembly</span></span></td>
<td><span data-ttu-id="1f2ab-924">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-924">10001</span></span></td>
<td><span data-ttu-id="1f2ab-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-925">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-926">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="1f2ab-927">-2,977.17</span></span></td>
<td><span data-ttu-id="1f2ab-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-929">Prod 1</span></span></td>
<td><span data-ttu-id="1f2ab-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-930">Product 1</span></span></td>
<td><span data-ttu-id="1f2ab-931">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-931">10001</span></span></td>
<td><span data-ttu-id="1f2ab-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-932">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-933">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1f2ab-934">2,507.09</span></span></td>
<td><span data-ttu-id="1f2ab-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1f2ab-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-936">Prod 2</span></span></td>
<td><span data-ttu-id="1f2ab-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-937">Product 2</span></span></td>
<td><span data-ttu-id="1f2ab-938">10001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-938">10001</span></span></td>
<td><span data-ttu-id="1f2ab-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-939">Electricity</span></span></td>
<td><span data-ttu-id="1f2ab-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-940">Variable cost</span></span></td>
<td><span data-ttu-id="1f2ab-941">470.08</span><span class="sxs-lookup"><span data-stu-id="1f2ab-941">470.08</span></span></td>
<td><span data-ttu-id="1f2ab-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="1f2ab-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="1f2ab-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="1f2ab-943">Conclusion</span></span>
<span data-ttu-id="1f2ab-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="1f2ab-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="1f2ab-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="1f2ab-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="1f2ab-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="1f2ab-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="1f2ab-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="1f2ab-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="1f2ab-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="1f2ab-951">CC099</span><span class="sxs-lookup"><span data-stu-id="1f2ab-951">CC099</span></span></th>
<th><span data-ttu-id="1f2ab-952">CC001</span><span class="sxs-lookup"><span data-stu-id="1f2ab-952">CC001</span></span></th>
<th><span data-ttu-id="1f2ab-953">CC002</span><span class="sxs-lookup"><span data-stu-id="1f2ab-953">CC002</span></span></th>
<th><span data-ttu-id="1f2ab-954">CC003</span><span class="sxs-lookup"><span data-stu-id="1f2ab-954">CC003</span></span></th>
<th><span data-ttu-id="1f2ab-955">CC004</span><span class="sxs-lookup"><span data-stu-id="1f2ab-955">CC004</span></span></th>
<th><span data-ttu-id="1f2ab-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-956">Proj 1</span></span></th>
<th><span data-ttu-id="1f2ab-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-957">Proj 2</span></span></th>
<th><span data-ttu-id="1f2ab-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1f2ab-958">Prod 1</span></span></th>
<th><span data-ttu-id="1f2ab-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1f2ab-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="1f2ab-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="1f2ab-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="1f2ab-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="1f2ab-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-971">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="1f2ab-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-973">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-974">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-975">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-976">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-977">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-978">776.36</span><span class="sxs-lookup"><span data-stu-id="1f2ab-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-979">223.64</span><span class="sxs-lookup"><span data-stu-id="1f2ab-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="1f2ab-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="1f2ab-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-982">000</span><span class="sxs-lookup"><span data-stu-id="1f2ab-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-983">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-984">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-985">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-986">0,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-987">30,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-988">10,00</span><span class="sxs-lookup"><span data-stu-id="1f2ab-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1f2ab-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1f2ab-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1f2ab-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1f2ab-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1f2ab-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="1f2ab-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="1f2ab-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="1f2ab-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1f2ab-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="1f2ab-996">Mer information finns i [Samlade kostnader](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="1f2ab-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



