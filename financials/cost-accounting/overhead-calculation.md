---
title: "Beräkning av indirekta kostnader"
description: "Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 1eb5560ba795ab6df61b5af889049810dd00d79e
ms.contentlocale: sv-se
ms.lasthandoff: 06/29/2017


---

# <a name="overhead-calculation"></a><span data-ttu-id="5ced1-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="5ced1-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5ced1-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="5ced1-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="5ced1-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="5ced1-105">Term definition</span></span>
---------------

<span data-ttu-id="5ced1-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="5ced1-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="5ced1-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="5ced1-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="5ced1-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="5ced1-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="5ced1-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="5ced1-109">Rent</span></span>
-   <span data-ttu-id="5ced1-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-110">Electricity</span></span>
-   <span data-ttu-id="5ced1-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="5ced1-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="5ced1-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="5ced1-112">Overhead calculation overview</span></span>
<span data-ttu-id="5ced1-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="5ced1-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="5ced1-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="5ced1-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="5ced1-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="5ced1-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="5ced1-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="5ced1-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="5ced1-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="5ced1-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="5ced1-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="5ced1-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="5ced1-119">Version type</span></span>
-   <span data-ttu-id="5ced1-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="5ced1-120">Date and time</span></span>
-   <span data-ttu-id="5ced1-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="5ced1-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="5ced1-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="5ced1-122">Fiscal year</span></span>
-   <span data-ttu-id="5ced1-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="5ced1-123">Fiscal period</span></span>

<span data-ttu-id="5ced1-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="5ced1-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="5ced1-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="5ced1-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="5ced1-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="5ced1-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="5ced1-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="5ced1-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="5ced1-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="5ced1-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="5ced1-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="5ced1-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="5ced1-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="5ced1-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="5ced1-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="5ced1-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="5ced1-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="5ced1-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="5ced1-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="5ced1-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="5ced1-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="5ced1-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="5ced1-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="5ced1-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="5ced1-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="5ced1-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="5ced1-140">Main account</span></span></th>
<th><span data-ttu-id="5ced1-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="5ced1-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="5ced1-143">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-143">CC099</span></span></td>
<td><span data-ttu-id="5ced1-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-144">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-145">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-145">10001</span></span></td>
<td><span data-ttu-id="5ced1-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-146">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="5ced1-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="5ced1-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="5ced1-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="5ced1-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="5ced1-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="5ced1-151">Define the cost behavior rule</span></span>

<span data-ttu-id="5ced1-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="5ced1-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="5ced1-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="5ced1-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="5ced1-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="5ced1-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="5ced1-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="5ced1-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="5ced1-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="5ced1-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="5ced1-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="5ced1-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="5ced1-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="5ced1-159">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-160">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-160">Journal</span></span></th>
<th><span data-ttu-id="5ced1-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="5ced1-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5ced1-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="5ced1-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5ced1-163">version</span><span class="sxs-lookup"><span data-stu-id="5ced1-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-164">00001</span><span class="sxs-lookup"><span data-stu-id="5ced1-164">00001</span></span></td>
<td><span data-ttu-id="5ced1-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="5ced1-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="5ced1-166">Fiscal</span></span></td>
<td><span data-ttu-id="5ced1-167">2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-167">2017</span></span></td>
<td><span data-ttu-id="5ced1-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-168">Period 1</span></span></td>
<td><span data-ttu-id="5ced1-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5ced1-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="5ced1-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-173">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-174">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="5ced1-177">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-177">CC099</span></span></td>
<td><span data-ttu-id="5ced1-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-178">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-179">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-179">10001</span></span></td>
<td><span data-ttu-id="5ced1-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-180">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="5ced1-181">Unclassified</span></span></td>
<td><span data-ttu-id="5ced1-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5ced1-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="5ced1-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-185">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-186">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-187">Amount</span></span></th>
<th><span data-ttu-id="5ced1-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-189">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-189">CC099</span></span></td>
<td><span data-ttu-id="5ced1-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-190">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-191">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-191">10001</span></span></td>
<td><span data-ttu-id="5ced1-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-192">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="5ced1-193">Unclassified</span></span></td>
<td><span data-ttu-id="5ced1-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-194">10,000.00</span></span></td>
<td><span data-ttu-id="5ced1-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-196">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-196">CC099</span></span></td>
<td><span data-ttu-id="5ced1-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-197">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-198">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-198">10001</span></span></td>
<td><span data-ttu-id="5ced1-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-199">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="5ced1-200">Unclassified</span></span></td>
<td><span data-ttu-id="5ced1-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-201">-10,000.00</span></span></td>
<td><span data-ttu-id="5ced1-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-203">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-203">CC099</span></span></td>
<td><span data-ttu-id="5ced1-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-204">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-205">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-205">10001</span></span></td>
<td><span data-ttu-id="5ced1-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-206">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-207">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-208">1,000.00</span></span></td>
<td><span data-ttu-id="5ced1-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-210">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-210">CC099</span></span></td>
<td><span data-ttu-id="5ced1-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-211">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-212">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-212">10001</span></span></td>
<td><span data-ttu-id="5ced1-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-213">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-214">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-215">9,000.00</span></span></td>
<td><span data-ttu-id="5ced1-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-217">Detaljerad information om kostnadsbeteende finns i Kostnadsbeteendepolicy.</span><span class="sxs-lookup"><span data-stu-id="5ced1-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="5ced1-218">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="5ced1-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="5ced1-219">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="5ced1-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="5ced1-220">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="5ced1-221">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="5ced1-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="5ced1-222">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="5ced1-222">Define the cost distribution rule</span></span>

<span data-ttu-id="5ced1-223">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="5ced1-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="5ced1-224">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="5ced1-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="5ced1-225">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="5ced1-226">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="5ced1-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="5ced1-227">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="5ced1-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="5ced1-228">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-229">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-229">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="5ced1-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-231">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-231">CC001</span></span></td>
<td><span data-ttu-id="5ced1-232">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-232">HR</span></span></td>
<td><span data-ttu-id="5ced1-233">1 000</span><span class="sxs-lookup"><span data-stu-id="5ced1-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-234">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-234">CC002</span></span></td>
<td><span data-ttu-id="5ced1-235">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-235">Finance</span></span></td>
<td><span data-ttu-id="5ced1-236">6,000</span><span class="sxs-lookup"><span data-stu-id="5ced1-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-237">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-237">CC003</span></span></td>
<td><span data-ttu-id="5ced1-238">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-238">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-239">0</span><span class="sxs-lookup"><span data-stu-id="5ced1-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-240">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="5ced1-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-241">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-241">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-242">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-242">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-243">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-243">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-244">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-245">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-245">CC001</span></span></td>
<td><span data-ttu-id="5ced1-246">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-246">HR</span></span></td>
<td><span data-ttu-id="5ced1-247">1 000</span><span class="sxs-lookup"><span data-stu-id="5ced1-247">1,000</span></span></td>
<td><span data-ttu-id="5ced1-248">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5ced1-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5ced1-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-250">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-250">CC002</span></span></td>
<td><span data-ttu-id="5ced1-251">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-251">Finance</span></span></td>
<td><span data-ttu-id="5ced1-252">6,000</span><span class="sxs-lookup"><span data-stu-id="5ced1-252">6,000</span></span></td>
<td><span data-ttu-id="5ced1-253">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5ced1-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5ced1-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-255">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-255">CC003</span></span></td>
<td><span data-ttu-id="5ced1-256">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-256">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-257">0</span><span class="sxs-lookup"><span data-stu-id="5ced1-257">0</span></span></td>
<td><span data-ttu-id="5ced1-258">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5ced1-259">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-260">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="5ced1-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="5ced1-261">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="5ced1-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-262">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-262">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-263">Formel</span><span class="sxs-lookup"><span data-stu-id="5ced1-263">Formula</span></span></th>
<th><span data-ttu-id="5ced1-264">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-264">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-265">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-265">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-266">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-267">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-267">CC001</span></span></td>
<td><span data-ttu-id="5ced1-268">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-268">HR</span></span></td>
<td><span data-ttu-id="5ced1-269">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5ced1-270">1</span><span class="sxs-lookup"><span data-stu-id="5ced1-270">1</span></span></td>
<td><span data-ttu-id="5ced1-271">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5ced1-272">500.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-273">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-273">CC002</span></span></td>
<td><span data-ttu-id="5ced1-274">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-274">Finance</span></span></td>
<td><span data-ttu-id="5ced1-275">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5ced1-276">1</span><span class="sxs-lookup"><span data-stu-id="5ced1-276">1</span></span></td>
<td><span data-ttu-id="5ced1-277">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5ced1-278">500.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-279">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-279">CC003</span></span></td>
<td><span data-ttu-id="5ced1-280">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-280">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5ced1-282">0</span><span class="sxs-lookup"><span data-stu-id="5ced1-282">0</span></span></td>
<td><span data-ttu-id="5ced1-283">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5ced1-284">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5ced1-285">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-286">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-286">Journal</span></span></th>
<th><span data-ttu-id="5ced1-287">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="5ced1-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5ced1-288">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="5ced1-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5ced1-289">version</span><span class="sxs-lookup"><span data-stu-id="5ced1-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-290">00002</span><span class="sxs-lookup"><span data-stu-id="5ced1-290">00002</span></span></td>
<td><span data-ttu-id="5ced1-291">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="5ced1-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="5ced1-292">Skatt</span><span class="sxs-lookup"><span data-stu-id="5ced1-292">Fiscal</span></span></td>
<td><span data-ttu-id="5ced1-293">2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-293">2017</span></span></td>
<td><span data-ttu-id="5ced1-294">Period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-294">Period 1</span></span></td>
<td><span data-ttu-id="5ced1-295">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5ced1-296">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="5ced1-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-297">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-298">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-299">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-299">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-300">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-300">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-301">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-302">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-303">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-303">CC099</span></span></td>
<td><span data-ttu-id="5ced1-304">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-304">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-305">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-305">10001</span></span></td>
<td><span data-ttu-id="5ced1-306">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-306">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-307">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-307">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-308">1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-309">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-310">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-310">CC099</span></span></td>
<td><span data-ttu-id="5ced1-311">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-311">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-312">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-312">10001</span></span></td>
<td><span data-ttu-id="5ced1-313">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-313">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-314">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-314">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5ced1-316">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="5ced1-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-317">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-318">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-318">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-319">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-319">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-320">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-320">Amount</span></span></th>
<th><span data-ttu-id="5ced1-321">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-322">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-322">CC099</span></span></td>
<td><span data-ttu-id="5ced1-323">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-323">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-324">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-324">10001</span></span></td>
<td><span data-ttu-id="5ced1-325">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-325">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-326">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-326">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-327">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-327">-1,000.00</span></span></td>
<td><span data-ttu-id="5ced1-328">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-329">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-329">CC001</span></span></td>
<td><span data-ttu-id="5ced1-330">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-330">HR</span></span></td>
<td><span data-ttu-id="5ced1-331">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-331">10001</span></span></td>
<td><span data-ttu-id="5ced1-332">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-332">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-333">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-333">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-334">500.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-334">500.00</span></span></td>
<td><span data-ttu-id="5ced1-335">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-336">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-336">CC002</span></span></td>
<td><span data-ttu-id="5ced1-337">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-337">Finance</span></span></td>
<td><span data-ttu-id="5ced1-338">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-338">10001</span></span></td>
<td><span data-ttu-id="5ced1-339">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-339">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-340">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-340">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-341">500.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-341">500.00</span></span></td>
<td><span data-ttu-id="5ced1-342">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-343">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-343">CC099</span></span></td>
<td><span data-ttu-id="5ced1-344">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="5ced1-344">Default cost center</span></span></td>
<td><span data-ttu-id="5ced1-345">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-345">10001</span></span></td>
<td><span data-ttu-id="5ced1-346">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-346">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-347">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-347">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-348">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-348">-9,000.00</span></span></td>
<td><span data-ttu-id="5ced1-349">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-350">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-350">CC001</span></span></td>
<td><span data-ttu-id="5ced1-351">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-351">HR</span></span></td>
<td><span data-ttu-id="5ced1-352">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-352">10001</span></span></td>
<td><span data-ttu-id="5ced1-353">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-353">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-354">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-354">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5ced1-355">1,285.71</span></span></td>
<td><span data-ttu-id="5ced1-356">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-357">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-357">CC002</span></span></td>
<td><span data-ttu-id="5ced1-358">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-358">Finance</span></span></td>
<td><span data-ttu-id="5ced1-359">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-359">10001</span></span></td>
<td><span data-ttu-id="5ced1-360">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-360">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-361">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-361">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5ced1-362">7,714.29</span></span></td>
<td><span data-ttu-id="5ced1-363">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-364">För detaljerad information om kostnadsfördelning och allokeringsunderlag, se Kostnadsfördelningspolicy och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="5ced1-365">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="5ced1-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="5ced1-366">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="5ced1-367">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="5ced1-368">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="5ced1-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="5ced1-369">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-369">Define the overhead rate</span></span>

<span data-ttu-id="5ced1-370">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="5ced1-371">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="5ced1-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-372">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-372">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-373">Timmar</span><span class="sxs-lookup"><span data-stu-id="5ced1-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-374">Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-375">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-375">Project 1</span></span></td>
<td><span data-ttu-id="5ced1-376">3</span><span class="sxs-lookup"><span data-stu-id="5ced1-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-377">Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-378">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-378">Project 2</span></span></td>
<td><span data-ttu-id="5ced1-379">1</span><span class="sxs-lookup"><span data-stu-id="5ced1-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-380">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="5ced1-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-381">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-381">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-382">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-382">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-383">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-383">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-384">Enheter</span><span class="sxs-lookup"><span data-stu-id="5ced1-384">Units</span></span></th>
<th><span data-ttu-id="5ced1-385">Kurs</span><span class="sxs-lookup"><span data-stu-id="5ced1-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-386">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-386">CC001</span></span></td>
<td><span data-ttu-id="5ced1-387">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-387">HR</span></span></td>
<td><span data-ttu-id="5ced1-388">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-388">10001</span></span></td>
<td><span data-ttu-id="5ced1-389">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-389">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-390">1</span><span class="sxs-lookup"><span data-stu-id="5ced1-390">1</span></span></td>
<td><span data-ttu-id="5ced1-391">10</span><span class="sxs-lookup"><span data-stu-id="5ced1-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-392">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-393">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-393">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-394">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-394">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-395">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-395">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-396">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-396">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-397">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-398">Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-399">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-399">Project 1</span></span></td>
<td><span data-ttu-id="5ced1-400">3</span><span class="sxs-lookup"><span data-stu-id="5ced1-400">3</span></span></td>
<td><span data-ttu-id="5ced1-401">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-401">10001</span></span></td>
<td><span data-ttu-id="5ced1-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5ced1-403">30,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-404">Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-405">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-405">Project 2</span></span></td>
<td><span data-ttu-id="5ced1-406">1</span><span class="sxs-lookup"><span data-stu-id="5ced1-406">1</span></span></td>
<td><span data-ttu-id="5ced1-407">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-407">10001</span></span></td>
<td><span data-ttu-id="5ced1-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5ced1-409">10,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5ced1-410">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-411">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-411">Journal</span></span></th>
<th><span data-ttu-id="5ced1-412">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="5ced1-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5ced1-413">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="5ced1-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5ced1-414">version</span><span class="sxs-lookup"><span data-stu-id="5ced1-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-415">00003</span><span class="sxs-lookup"><span data-stu-id="5ced1-415">00003</span></span></td>
<td><span data-ttu-id="5ced1-416">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="5ced1-417">Skatt</span><span class="sxs-lookup"><span data-stu-id="5ced1-417">Fiscal</span></span></td>
<td><span data-ttu-id="5ced1-418">2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-418">2017</span></span></td>
<td><span data-ttu-id="5ced1-419">Period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-419">Period 1</span></span></td>
<td><span data-ttu-id="5ced1-420">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="5ced1-421">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="5ced1-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-422">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-423">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-423">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-424">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-425">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-426">Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-427">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-428">3,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-429">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-430">Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-431">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-432">1,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5ced1-433">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="5ced1-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-434">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-435">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-435">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-436">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-436">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-437">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-437">Amount</span></span></th>
<th><span data-ttu-id="5ced1-438">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="5ced1-439">CC0001</span></span></td>
<td><span data-ttu-id="5ced1-440">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-440">HR</span></span></td>
<td><span data-ttu-id="5ced1-441">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-441">10001</span></span></td>
<td><span data-ttu-id="5ced1-442">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-442">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-443">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-443">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-444">-30.00</span></span></td>
<td><span data-ttu-id="5ced1-445">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-446">Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-447">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5ced1-448">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-448">10001</span></span></td>
<td><span data-ttu-id="5ced1-449">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-449">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-450">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-450">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-451">30,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-451">30.00</span></span></td>
<td><span data-ttu-id="5ced1-452">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-453">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-453">CC001</span></span></td>
<td><span data-ttu-id="5ced1-454">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-454">HR</span></span></td>
<td><span data-ttu-id="5ced1-455">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-455">10001</span></span></td>
<td><span data-ttu-id="5ced1-456">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-456">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-457">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-457">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-458">-10.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-458">-10.00</span></span></td>
<td><span data-ttu-id="5ced1-459">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-460">Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-461">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5ced1-462">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-462">10001</span></span></td>
<td><span data-ttu-id="5ced1-463">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-463">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-464">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-464">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-465">10,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-465">10.00</span></span></td>
<td><span data-ttu-id="5ced1-466">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-467">Detaljerad information om policy för indirekt kostnad finns i Policy för indirekt kostnad och Allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="5ced1-468">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="5ced1-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="5ced1-469">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="5ced1-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="5ced1-470">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="5ced1-471">Finance and Operations stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="5ced1-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="5ced1-472">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="5ced1-473">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="5ced1-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="5ced1-474">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="5ced1-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="5ced1-475">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="5ced1-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="5ced1-476">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="5ced1-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="5ced1-477">[![Ömsesidig metod](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="5ced1-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="5ced1-478">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="5ced1-478">Define the cost allocation</span></span>

<span data-ttu-id="5ced1-479">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="5ced1-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="5ced1-480">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="5ced1-481">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="5ced1-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-482">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-482">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-483">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="5ced1-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-484">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-484">CC002</span></span></td>
<td><span data-ttu-id="5ced1-485">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-485">Finance</span></span></td>
<td><span data-ttu-id="5ced1-486">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-487">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-487">CC003</span></span></td>
<td><span data-ttu-id="5ced1-488">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-488">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-489">55</span><span class="sxs-lookup"><span data-stu-id="5ced1-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-490">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-490">CC004</span></span></td>
<td><span data-ttu-id="5ced1-491">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-491">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-492">10</span><span class="sxs-lookup"><span data-stu-id="5ced1-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-493">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="5ced1-494">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="5ced1-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-495">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-495">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-496">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="5ced1-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-497">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-497">CC003</span></span></td>
<td><span data-ttu-id="5ced1-498">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-498">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-499">65</span><span class="sxs-lookup"><span data-stu-id="5ced1-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-500">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-500">CC004</span></span></td>
<td><span data-ttu-id="5ced1-501">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-501">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-502">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-503">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="5ced1-504">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="5ced1-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-505">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-505">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-506">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="5ced1-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-507">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-508">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-508">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-509">60</span><span class="sxs-lookup"><span data-stu-id="5ced1-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-510">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-511">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-511">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-512">20</span><span class="sxs-lookup"><span data-stu-id="5ced1-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-513">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5ced1-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="5ced1-514">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="5ced1-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-515">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-515">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-516">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="5ced1-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-517">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-518">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-518">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-519">80</span><span class="sxs-lookup"><span data-stu-id="5ced1-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-520">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-521">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-521">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-522">15</span><span class="sxs-lookup"><span data-stu-id="5ced1-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-523">**Obs:** i Finance and Operations kan statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="5ced1-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="5ced1-524">Mer detaljerad information om provider av statistiska mått finns i Providermallar för statistiska mätningar.</span><span class="sxs-lookup"><span data-stu-id="5ced1-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="5ced1-525">(Observera att det här avsnittet är inte klart, men kommer snart.) I följande tabell visas resultatet när HR-tjänsten används som ett allokeringsunderlag för totalkostnaden (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="5ced1-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-526">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-526">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-527">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-527">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-528">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-528">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-529">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-529">Amount</span></span></th>
<th><span data-ttu-id="5ced1-530">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-531">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-531">CC002</span></span></td>
<td><span data-ttu-id="5ced1-532">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-532">Finance</span></span></td>
<td><span data-ttu-id="5ced1-533">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-533">35</span></span></td>
<td><span data-ttu-id="5ced1-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5ced1-535">175.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-535">175.00</span></span></td>
<td><span data-ttu-id="5ced1-536">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-537">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-537">CC003</span></span></td>
<td><span data-ttu-id="5ced1-538">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-538">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-539">55</span><span class="sxs-lookup"><span data-stu-id="5ced1-539">55</span></span></td>
<td><span data-ttu-id="5ced1-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5ced1-541">275.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-541">275.00</span></span></td>
<td><span data-ttu-id="5ced1-542">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-543">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-543">CC004</span></span></td>
<td><span data-ttu-id="5ced1-544">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-544">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-545">10</span><span class="sxs-lookup"><span data-stu-id="5ced1-545">10</span></span></td>
<td><span data-ttu-id="5ced1-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5ced1-547">50,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-547">50.00</span></span></td>
<td><span data-ttu-id="5ced1-548">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-549">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-549">CC002</span></span></td>
<td><span data-ttu-id="5ced1-550">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-550">Finance</span></span></td>
<td><span data-ttu-id="5ced1-551">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-551">35</span></span></td>
<td><span data-ttu-id="5ced1-552">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5ced1-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5ced1-553">436.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-553">436.00</span></span></td>
<td><span data-ttu-id="5ced1-554">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-555">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-555">CC003</span></span></td>
<td><span data-ttu-id="5ced1-556">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-556">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-557">55</span><span class="sxs-lookup"><span data-stu-id="5ced1-557">55</span></span></td>
<td><span data-ttu-id="5ced1-558">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5ced1-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5ced1-559">685.14</span><span class="sxs-lookup"><span data-stu-id="5ced1-559">685.14</span></span></td>
<td><span data-ttu-id="5ced1-560">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-561">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-561">CC004</span></span></td>
<td><span data-ttu-id="5ced1-562">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-562">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-563">10</span><span class="sxs-lookup"><span data-stu-id="5ced1-563">10</span></span></td>
<td><span data-ttu-id="5ced1-564">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="5ced1-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5ced1-565">124.57</span><span class="sxs-lookup"><span data-stu-id="5ced1-565">124.57</span></span></td>
<td><span data-ttu-id="5ced1-566">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-567">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="5ced1-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-568">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-568">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-569">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-569">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-570">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-570">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-571">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-571">Amount</span></span></th>
<th><span data-ttu-id="5ced1-572">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-573">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-573">CC003</span></span></td>
<td><span data-ttu-id="5ced1-574">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-574">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-575">65</span><span class="sxs-lookup"><span data-stu-id="5ced1-575">65</span></span></td>
<td><span data-ttu-id="5ced1-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5ced1-577">438.75</span><span class="sxs-lookup"><span data-stu-id="5ced1-577">438.75</span></span></td>
<td><span data-ttu-id="5ced1-578">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-579">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-579">CC004</span></span></td>
<td><span data-ttu-id="5ced1-580">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-580">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-581">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-581">35</span></span></td>
<td><span data-ttu-id="5ced1-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5ced1-583">236.25</span><span class="sxs-lookup"><span data-stu-id="5ced1-583">236.25</span></span></td>
<td><span data-ttu-id="5ced1-584">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-585">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-585">CC003</span></span></td>
<td><span data-ttu-id="5ced1-586">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-586">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-587">65</span><span class="sxs-lookup"><span data-stu-id="5ced1-587">65</span></span></td>
<td><span data-ttu-id="5ced1-588">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5ced1-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5ced1-589">5,297.69</span></span></td>
<td><span data-ttu-id="5ced1-590">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-591">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-591">CC004</span></span></td>
<td><span data-ttu-id="5ced1-592">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-592">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-593">35</span><span class="sxs-lookup"><span data-stu-id="5ced1-593">35</span></span></td>
<td><span data-ttu-id="5ced1-594">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="5ced1-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5ced1-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5ced1-595">2,852.60</span></span></td>
<td><span data-ttu-id="5ced1-596">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-597">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="5ced1-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-598">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-598">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-599">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-599">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-600">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-600">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-601">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-601">Amount</span></span></th>
<th><span data-ttu-id="5ced1-602">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-603">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-604">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-604">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-605">60</span><span class="sxs-lookup"><span data-stu-id="5ced1-605">60</span></span></td>
<td><span data-ttu-id="5ced1-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5ced1-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5ced1-607">535.31</span><span class="sxs-lookup"><span data-stu-id="5ced1-607">535.31</span></span></td>
<td><span data-ttu-id="5ced1-608">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-609">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-610">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-610">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-611">20</span><span class="sxs-lookup"><span data-stu-id="5ced1-611">20</span></span></td>
<td><span data-ttu-id="5ced1-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="5ced1-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5ced1-613">178.44</span><span class="sxs-lookup"><span data-stu-id="5ced1-613">178.44</span></span></td>
<td><span data-ttu-id="5ced1-614">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-615">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-616">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-616">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-617">60</span><span class="sxs-lookup"><span data-stu-id="5ced1-617">60</span></span></td>
<td><span data-ttu-id="5ced1-618">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5ced1-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5ced1-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5ced1-619">4,487.12</span></span></td>
<td><span data-ttu-id="5ced1-620">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-621">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-622">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-622">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-623">20</span><span class="sxs-lookup"><span data-stu-id="5ced1-623">20</span></span></td>
<td><span data-ttu-id="5ced1-624">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="5ced1-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5ced1-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5ced1-625">1,495.71</span></span></td>
<td><span data-ttu-id="5ced1-626">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5ced1-627">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="5ced1-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-628">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-628">Cost object</span></span></th>
<th><span data-ttu-id="5ced1-629">Storlek</span><span class="sxs-lookup"><span data-stu-id="5ced1-629">Magnitude</span></span></th>
<th><span data-ttu-id="5ced1-630">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="5ced1-630">Allocation factor</span></span></th>
<th><span data-ttu-id="5ced1-631">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-631">Amount</span></span></th>
<th><span data-ttu-id="5ced1-632">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-633">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-634">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-634">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-635">80</span><span class="sxs-lookup"><span data-stu-id="5ced1-635">80</span></span></td>
<td><span data-ttu-id="5ced1-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5ced1-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5ced1-637">241.05</span><span class="sxs-lookup"><span data-stu-id="5ced1-637">241.05</span></span></td>
<td><span data-ttu-id="5ced1-638">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-639">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-640">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-640">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-641">15</span><span class="sxs-lookup"><span data-stu-id="5ced1-641">15</span></span></td>
<td><span data-ttu-id="5ced1-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="5ced1-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5ced1-643">45.20</span><span class="sxs-lookup"><span data-stu-id="5ced1-643">45.20</span></span></td>
<td><span data-ttu-id="5ced1-644">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-645">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-646">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-646">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-647">80</span><span class="sxs-lookup"><span data-stu-id="5ced1-647">80</span></span></td>
<td><span data-ttu-id="5ced1-648">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5ced1-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5ced1-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5ced1-649">2,507.09</span></span></td>
<td><span data-ttu-id="5ced1-650">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-651">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-652">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-652">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-653">15</span><span class="sxs-lookup"><span data-stu-id="5ced1-653">15</span></span></td>
<td><span data-ttu-id="5ced1-654">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="5ced1-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5ced1-655">470.08</span><span class="sxs-lookup"><span data-stu-id="5ced1-655">470.08</span></span></td>
<td><span data-ttu-id="5ced1-656">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5ced1-657">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="5ced1-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-658">Journal</span><span class="sxs-lookup"><span data-stu-id="5ced1-658">Journal</span></span></th>
<th><span data-ttu-id="5ced1-659">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="5ced1-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5ced1-660">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="5ced1-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5ced1-661">version</span><span class="sxs-lookup"><span data-stu-id="5ced1-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-662">00004</span><span class="sxs-lookup"><span data-stu-id="5ced1-662">00004</span></span></td>
<td><span data-ttu-id="5ced1-663">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="5ced1-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="5ced1-664">Skatt</span><span class="sxs-lookup"><span data-stu-id="5ced1-664">Fiscal</span></span></td>
<td><span data-ttu-id="5ced1-665">2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-665">2017</span></span></td>
<td><span data-ttu-id="5ced1-666">Period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-666">Period 1</span></span></td>
<td><span data-ttu-id="5ced1-667">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="5ced1-668">Journalrader</span><span class="sxs-lookup"><span data-stu-id="5ced1-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5ced1-669">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-670">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-671">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-671">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-672">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-672">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-673">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-674">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-675">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-675">CC001</span></span></td>
<td><span data-ttu-id="5ced1-676">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-676">HR</span></span></td>
<td><span data-ttu-id="5ced1-677">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-677">10001</span></span></td>
<td><span data-ttu-id="5ced1-678">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-678">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-679">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-679">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-680">500.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-681">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-682">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-682">CC001</span></span></td>
<td><span data-ttu-id="5ced1-683">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-683">HR</span></span></td>
<td><span data-ttu-id="5ced1-684">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-684">10001</span></span></td>
<td><span data-ttu-id="5ced1-685">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-685">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-686">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-686">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="5ced1-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-688">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-689">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-689">CC002</span></span></td>
<td><span data-ttu-id="5ced1-690">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-690">Finance</span></span></td>
<td><span data-ttu-id="5ced1-691">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-691">10001</span></span></td>
<td><span data-ttu-id="5ced1-692">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-692">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-693">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-693">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-694">675.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-695">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-696">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-696">CC002</span></span></td>
<td><span data-ttu-id="5ced1-697">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-697">Finance</span></span></td>
<td><span data-ttu-id="5ced1-698">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-698">10001</span></span></td>
<td><span data-ttu-id="5ced1-699">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-699">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-700">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-700">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="5ced1-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-702">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-703">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-703">CC003</span></span></td>
<td><span data-ttu-id="5ced1-704">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-704">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-705">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-705">10001</span></span></td>
<td><span data-ttu-id="5ced1-706">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-706">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-707">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-707">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-708">713.75</span><span class="sxs-lookup"><span data-stu-id="5ced1-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-709">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-710">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-710">CC003</span></span></td>
<td><span data-ttu-id="5ced1-711">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-711">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-712">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-712">10001</span></span></td>
<td><span data-ttu-id="5ced1-713">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-713">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-714">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-714">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="5ced1-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-716">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-717">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-717">CC003</span></span></td>
<td><span data-ttu-id="5ced1-718">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-718">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-719">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-719">10001</span></span></td>
<td><span data-ttu-id="5ced1-720">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-720">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-721">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-721">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-722">286.25</span><span class="sxs-lookup"><span data-stu-id="5ced1-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-723">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-724">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-724">CC003</span></span></td>
<td><span data-ttu-id="5ced1-725">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-725">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-726">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-726">10001</span></span></td>
<td><span data-ttu-id="5ced1-727">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-727">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-728">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-728">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="5ced1-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-730">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-731">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-732">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-732">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-733">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-733">10001</span></span></td>
<td><span data-ttu-id="5ced1-734">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-734">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-735">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-735">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-736">776.36</span><span class="sxs-lookup"><span data-stu-id="5ced1-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-737">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-738">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-739">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-739">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-740">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-740">10001</span></span></td>
<td><span data-ttu-id="5ced1-741">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-741">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-742">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-742">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5ced1-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-744">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-745">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-746">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-746">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-747">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-747">10001</span></span></td>
<td><span data-ttu-id="5ced1-748">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-748">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-749">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-749">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-750">223.64</span><span class="sxs-lookup"><span data-stu-id="5ced1-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-751">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="5ced1-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-752">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-753">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-753">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-754">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-754">10001</span></span></td>
<td><span data-ttu-id="5ced1-755">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-755">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-756">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-756">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5ced1-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5ced1-758">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="5ced1-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5ced1-759">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5ced1-760">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-760">Cost element</span></span></th>
<th><span data-ttu-id="5ced1-761">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="5ced1-761">Cost behavior</span></span></th>
<th><span data-ttu-id="5ced1-762">Belopp</span><span class="sxs-lookup"><span data-stu-id="5ced1-762">Amount</span></span></th>
<th><span data-ttu-id="5ced1-763">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="5ced1-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5ced1-764">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-764">CC001</span></span></td>
<td><span data-ttu-id="5ced1-765">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-765">HR</span></span></td>
<td><span data-ttu-id="5ced1-766">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-766">10001</span></span></td>
<td><span data-ttu-id="5ced1-767">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-767">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-768">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-768">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-769">-500.00</span></span></td>
<td><span data-ttu-id="5ced1-770">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-771">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-771">CC002</span></span></td>
<td><span data-ttu-id="5ced1-772">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-772">Finance</span></span></td>
<td><span data-ttu-id="5ced1-773">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-773">10001</span></span></td>
<td><span data-ttu-id="5ced1-774">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-774">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-775">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-775">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-776">175.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-776">175.00</span></span></td>
<td><span data-ttu-id="5ced1-777">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-778">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-778">CC003</span></span></td>
<td><span data-ttu-id="5ced1-779">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-779">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-780">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-780">10001</span></span></td>
<td><span data-ttu-id="5ced1-781">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-781">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-782">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-782">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-783">275.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-783">275.00</span></span></td>
<td><span data-ttu-id="5ced1-784">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-785">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-785">CC004</span></span></td>
<td><span data-ttu-id="5ced1-786">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-786">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-787">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-787">10001</span></span></td>
<td><span data-ttu-id="5ced1-788">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-788">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-789">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-789">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-790">50,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-790">50,00</span></span></td>
<td><span data-ttu-id="5ced1-791">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-792">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-792">CC001</span></span></td>
<td><span data-ttu-id="5ced1-793">Personal</span><span class="sxs-lookup"><span data-stu-id="5ced1-793">HR</span></span></td>
<td><span data-ttu-id="5ced1-794">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-794">10001</span></span></td>
<td><span data-ttu-id="5ced1-795">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-795">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-796">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-796">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-797">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="5ced1-797">-1,245.71</span></span></td>
<td><span data-ttu-id="5ced1-798">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-799">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-799">CC002</span></span></td>
<td><span data-ttu-id="5ced1-800">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-800">Finance</span></span></td>
<td><span data-ttu-id="5ced1-801">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-801">10001</span></span></td>
<td><span data-ttu-id="5ced1-802">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-802">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-803">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-803">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-804">436.00</span><span class="sxs-lookup"><span data-stu-id="5ced1-804">436.00</span></span></td>
<td><span data-ttu-id="5ced1-805">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-806">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-806">CC003</span></span></td>
<td><span data-ttu-id="5ced1-807">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-807">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-808">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-808">10001</span></span></td>
<td><span data-ttu-id="5ced1-809">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-809">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-810">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-810">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-811">685.14</span><span class="sxs-lookup"><span data-stu-id="5ced1-811">685.14</span></span></td>
<td><span data-ttu-id="5ced1-812">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-813">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-813">CC004</span></span></td>
<td><span data-ttu-id="5ced1-814">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-814">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-815">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-815">10001</span></span></td>
<td><span data-ttu-id="5ced1-816">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-816">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-817">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-817">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-818">124.57</span><span class="sxs-lookup"><span data-stu-id="5ced1-818">124.57</span></span></td>
<td><span data-ttu-id="5ced1-819">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-820">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-820">CC002</span></span></td>
<td><span data-ttu-id="5ced1-821">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-821">Finance</span></span></td>
<td><span data-ttu-id="5ced1-822">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-822">10001</span></span></td>
<td><span data-ttu-id="5ced1-823">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-823">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-824">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-824">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-825">-675.00</span></span></td>
<td><span data-ttu-id="5ced1-826">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-827">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-827">CC003</span></span></td>
<td><span data-ttu-id="5ced1-828">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-828">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-829">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-829">10001</span></span></td>
<td><span data-ttu-id="5ced1-830">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-830">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-831">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-831">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-832">438.75</span><span class="sxs-lookup"><span data-stu-id="5ced1-832">438.75</span></span></td>
<td><span data-ttu-id="5ced1-833">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-834">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-834">CC004</span></span></td>
<td><span data-ttu-id="5ced1-835">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-835">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-836">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-836">10001</span></span></td>
<td><span data-ttu-id="5ced1-837">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-837">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-838">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-838">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-839">236.25</span><span class="sxs-lookup"><span data-stu-id="5ced1-839">236.25</span></span></td>
<td><span data-ttu-id="5ced1-840">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-841">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-841">CC002</span></span></td>
<td><span data-ttu-id="5ced1-842">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="5ced1-842">Finance</span></span></td>
<td><span data-ttu-id="5ced1-843">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-843">10001</span></span></td>
<td><span data-ttu-id="5ced1-844">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-844">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-845">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-845">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-846">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="5ced1-846">-8,150.29</span></span></td>
<td><span data-ttu-id="5ced1-847">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-848">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-848">CC003</span></span></td>
<td><span data-ttu-id="5ced1-849">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-849">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-850">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-850">10001</span></span></td>
<td><span data-ttu-id="5ced1-851">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-851">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-852">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-852">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5ced1-853">5,297.69</span></span></td>
<td><span data-ttu-id="5ced1-854">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-855">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-855">CC004</span></span></td>
<td><span data-ttu-id="5ced1-856">Paketering</span><span class="sxs-lookup"><span data-stu-id="5ced1-856">Packaging</span></span></td>
<td><span data-ttu-id="5ced1-857">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-857">10001</span></span></td>
<td><span data-ttu-id="5ced1-858">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-858">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-859">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-859">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5ced1-860">2,852.60</span></span></td>
<td><span data-ttu-id="5ced1-861">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-862">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-862">CC003</span></span></td>
<td><span data-ttu-id="5ced1-863">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-863">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-864">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-864">10001</span></span></td>
<td><span data-ttu-id="5ced1-865">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-865">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-866">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-866">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="5ced1-867">-713.75</span></span></td>
<td><span data-ttu-id="5ced1-868">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-869">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-870">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-870">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-871">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-871">10001</span></span></td>
<td><span data-ttu-id="5ced1-872">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-872">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-873">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-873">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-874">535.31</span><span class="sxs-lookup"><span data-stu-id="5ced1-874">535.31</span></span></td>
<td><span data-ttu-id="5ced1-875">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-876">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-877">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-877">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-878">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-878">10001</span></span></td>
<td><span data-ttu-id="5ced1-879">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-879">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-880">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-880">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-881">178.44</span><span class="sxs-lookup"><span data-stu-id="5ced1-881">178.44</span></span></td>
<td><span data-ttu-id="5ced1-882">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-883">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-883">CC003</span></span></td>
<td><span data-ttu-id="5ced1-884">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-884">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-885">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-885">10001</span></span></td>
<td><span data-ttu-id="5ced1-886">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-886">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-887">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-887">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-888">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="5ced1-888">-5,982.83</span></span></td>
<td><span data-ttu-id="5ced1-889">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-890">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-891">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-891">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-892">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-892">10001</span></span></td>
<td><span data-ttu-id="5ced1-893">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-893">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-894">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-894">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5ced1-895">4,487.12</span></span></td>
<td><span data-ttu-id="5ced1-896">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-897">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-898">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-898">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-899">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-899">10001</span></span></td>
<td><span data-ttu-id="5ced1-900">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-900">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-901">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-901">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5ced1-902">1,495.71</span></span></td>
<td><span data-ttu-id="5ced1-903">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-904">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-904">CC003</span></span></td>
<td><span data-ttu-id="5ced1-905">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-905">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-906">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-906">10001</span></span></td>
<td><span data-ttu-id="5ced1-907">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-907">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-908">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-908">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="5ced1-909">-286.25</span></span></td>
<td><span data-ttu-id="5ced1-910">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-911">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-912">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-912">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-913">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-913">10001</span></span></td>
<td><span data-ttu-id="5ced1-914">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-914">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-915">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-915">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-916">241.05</span><span class="sxs-lookup"><span data-stu-id="5ced1-916">241.05</span></span></td>
<td><span data-ttu-id="5ced1-917">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-918">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-919">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-919">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-920">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-920">10001</span></span></td>
<td><span data-ttu-id="5ced1-921">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-921">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-922">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-922">Fixed cost</span></span></td>
<td><span data-ttu-id="5ced1-923">45.20</span><span class="sxs-lookup"><span data-stu-id="5ced1-923">45.20</span></span></td>
<td><span data-ttu-id="5ced1-924">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-925">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-925">CC003</span></span></td>
<td><span data-ttu-id="5ced1-926">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="5ced1-926">Assembly</span></span></td>
<td><span data-ttu-id="5ced1-927">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-927">10001</span></span></td>
<td><span data-ttu-id="5ced1-928">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-928">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-929">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-929">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-930">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="5ced1-930">-2,977.17</span></span></td>
<td><span data-ttu-id="5ced1-931">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-932">Prod 1</span></span></td>
<td><span data-ttu-id="5ced1-933">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-933">Product 1</span></span></td>
<td><span data-ttu-id="5ced1-934">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-934">10001</span></span></td>
<td><span data-ttu-id="5ced1-935">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-935">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-936">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-936">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5ced1-937">2,507.09</span></span></td>
<td><span data-ttu-id="5ced1-938">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5ced1-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-939">Prod 2</span></span></td>
<td><span data-ttu-id="5ced1-940">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-940">Product 2</span></span></td>
<td><span data-ttu-id="5ced1-941">10001</span><span class="sxs-lookup"><span data-stu-id="5ced1-941">10001</span></span></td>
<td><span data-ttu-id="5ced1-942">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-942">Electricity</span></span></td>
<td><span data-ttu-id="5ced1-943">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-943">Variable cost</span></span></td>
<td><span data-ttu-id="5ced1-944">470.08</span><span class="sxs-lookup"><span data-stu-id="5ced1-944">470.08</span></span></td>
<td><span data-ttu-id="5ced1-945">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="5ced1-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="5ced1-946">Slutsats</span><span class="sxs-lookup"><span data-stu-id="5ced1-946">Conclusion</span></span>
<span data-ttu-id="5ced1-947">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="5ced1-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="5ced1-948">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="5ced1-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="5ced1-949">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="5ced1-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="5ced1-950">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="5ced1-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="5ced1-951">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="5ced1-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="5ced1-952">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="5ced1-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="5ced1-953">Totalt</span><span class="sxs-lookup"><span data-stu-id="5ced1-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="5ced1-954">CC099</span><span class="sxs-lookup"><span data-stu-id="5ced1-954">CC099</span></span></th>
<th><span data-ttu-id="5ced1-955">CC001</span><span class="sxs-lookup"><span data-stu-id="5ced1-955">CC001</span></span></th>
<th><span data-ttu-id="5ced1-956">CC002</span><span class="sxs-lookup"><span data-stu-id="5ced1-956">CC002</span></span></th>
<th><span data-ttu-id="5ced1-957">CC003</span><span class="sxs-lookup"><span data-stu-id="5ced1-957">CC003</span></span></th>
<th><span data-ttu-id="5ced1-958">CC004</span><span class="sxs-lookup"><span data-stu-id="5ced1-958">CC004</span></span></th>
<th><span data-ttu-id="5ced1-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-959">Proj 1</span></span></th>
<th><span data-ttu-id="5ced1-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-960">Proj 2</span></span></th>
<th><span data-ttu-id="5ced1-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="5ced1-961">Prod 1</span></span></th>
<th><span data-ttu-id="5ced1-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="5ced1-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="5ced1-963">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="5ced1-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="5ced1-973">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="5ced1-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-974">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="5ced1-975">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-976">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-977">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-978">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-979">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-980">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-981">776.36</span><span class="sxs-lookup"><span data-stu-id="5ced1-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-982">223.64</span><span class="sxs-lookup"><span data-stu-id="5ced1-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="5ced1-984">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="5ced1-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-985">000</span><span class="sxs-lookup"><span data-stu-id="5ced1-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-986">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-987">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-988">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-989">0,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-990">30,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-991">10,00</span><span class="sxs-lookup"><span data-stu-id="5ced1-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5ced1-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5ced1-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5ced1-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="5ced1-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5ced1-995">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="5ced1-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="5ced1-996">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5ced1-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="5ced1-997">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="5ced1-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="5ced1-998">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="5ced1-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="5ced1-999">Mer information finns i Policy för kostnadssummering.</span><span class="sxs-lookup"><span data-stu-id="5ced1-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="5ced1-1000">(Observera att det här ämnet ännu inte är färdigt men kommer snart.)</span><span class="sxs-lookup"><span data-stu-id="5ced1-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




