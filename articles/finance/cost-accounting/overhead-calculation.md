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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179980"
---
# <a name="overhead-calculation"></a><span data-ttu-id="d6d84-103">Beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="d6d84-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6d84-104">Det här avsnittet beskriver de vanliga processerna för beräkning och allokering av indirekta kostnader.</span><span class="sxs-lookup"><span data-stu-id="d6d84-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="d6d84-105">Termdefinition</span><span class="sxs-lookup"><span data-stu-id="d6d84-105">Term definition</span></span>
---------------

<span data-ttu-id="d6d84-106">Indirekta kostnader är sådana kostnader som uppkommer för att kunna driva ett företag, men som inte är direkt hänförliga till en viss affärsverksamhet, produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="d6d84-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="d6d84-107">Indirekta kostnader har viktiga funktioner för generering av vinstdrivande aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="d6d84-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="d6d84-108">Här följer några exempel på indirekta kostnader:</span><span class="sxs-lookup"><span data-stu-id="d6d84-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="d6d84-109">Hyra</span><span class="sxs-lookup"><span data-stu-id="d6d84-109">Rent</span></span>
-   <span data-ttu-id="d6d84-110">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-110">Electricity</span></span>
-   <span data-ttu-id="d6d84-111">Administrativa löner</span><span class="sxs-lookup"><span data-stu-id="d6d84-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="d6d84-112">Översikt över beräkning av indirekta kostnader</span><span class="sxs-lookup"><span data-stu-id="d6d84-112">Overhead calculation overview</span></span>
<span data-ttu-id="d6d84-113">Beräkning av indirekta kostnader kör kostnadsredovisningspolicyerna i korrekt ordning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="d6d84-114">Du kan köra beräkningar av indirekta kostnader flera gånger för samma räkenskapsperiod om kostnadsredovisningspolicyerna har ändrats eller om specifika fel har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="d6d84-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="d6d84-115">Varje körning av beräkning av indirekta kostnader lagras och får ett unikt versions-ID som gör att du kan jämföra beräkningarna i olika versioner.</span><span class="sxs-lookup"><span data-stu-id="d6d84-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="d6d84-116">Kostnadstransaktioner som beräkningen av indirekta kostnader genererar får ett redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="d6d84-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="d6d84-117">Det här redovisningsdatumet matchar slutdatumet för den räkenskapsperiod som används i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="d6d84-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="d6d84-118">Det unika versions-ID:t består av följande element:</span><span class="sxs-lookup"><span data-stu-id="d6d84-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="d6d84-119">Versionstyp</span><span class="sxs-lookup"><span data-stu-id="d6d84-119">Version type</span></span>
-   <span data-ttu-id="d6d84-120">Datum och tid</span><span class="sxs-lookup"><span data-stu-id="d6d84-120">Date and time</span></span>
-   <span data-ttu-id="d6d84-121">Huvudbok för kostnadsredovisning</span><span class="sxs-lookup"><span data-stu-id="d6d84-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="d6d84-122">Räkenskapsår</span><span class="sxs-lookup"><span data-stu-id="d6d84-122">Fiscal year</span></span>
-   <span data-ttu-id="d6d84-123">Räkenskapsperiod</span><span class="sxs-lookup"><span data-stu-id="d6d84-123">Fiscal period</span></span>

<span data-ttu-id="d6d84-124">Beräkningen av indirekta kostnader körs oberoende av versionen.</span><span class="sxs-lookup"><span data-stu-id="d6d84-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="d6d84-125">Du kan därför beräkna budgetversionen innan den faktiska versionen.</span><span class="sxs-lookup"><span data-stu-id="d6d84-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="d6d84-126">Beräkningen av indirekta kostnader består av fyra steg som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="d6d84-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="d6d84-127">I varje steg skapas en journalrubrik med journalposter.</span><span class="sxs-lookup"><span data-stu-id="d6d84-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="d6d84-128">Den här journalrubriken behåller indata för varje beräkningssteg.</span><span class="sxs-lookup"><span data-stu-id="d6d84-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="d6d84-129">Policyer och regler tillämpas på varje journalrad och kostnadstransaktioner skapas som utleverans.</span><span class="sxs-lookup"><span data-stu-id="d6d84-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="d6d84-130">Därför måste du alltid ha fullständig spårning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="d6d84-131">[![Beräkning av indirekta kostnader](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="d6d84-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="d6d84-132">Beräkna och fördela den indirekta elkostnaden</span><span class="sxs-lookup"><span data-stu-id="d6d84-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="d6d84-133">I affärsredovisning är vissa kostnader som till exempel el, registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="d6d84-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="d6d84-134">Därför ges inte detaljerad ledarskapsinblick för kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="d6d84-135">I kostnadsredovisning måste kostnader flöda genom organisationsenheterna för att ge rätt ledarskapsinsikt för alla organisationsenheter och nivåer.</span><span class="sxs-lookup"><span data-stu-id="d6d84-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="d6d84-136">Detta flöde måste baseras på en korrekt bild av förbrukningen eller en rimlig bedömning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="d6d84-137">I redovisning kan en elkostnad bokföras enligt tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="d6d84-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-138">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-139">Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="d6d84-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-140">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="d6d84-140">Main account</span></span></th>
<th><span data-ttu-id="d6d84-141">Belopp i redovisningsvalutan</span><span class="sxs-lookup"><span data-stu-id="d6d84-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-142">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="d6d84-143">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-143">CC099</span></span></td>
<td><span data-ttu-id="d6d84-144">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-144">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-145">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-145">10001</span></span></td>
<td><span data-ttu-id="d6d84-146">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-146">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-147">10 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="d6d84-148">Steg 1: Bearbeta beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="d6d84-149">Som standard när kostnadstransaktioner importeras från källdata, får de klassificeringen **Oklassificerade** i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="d6d84-150">Genom att använda policyregler för kostnadsbeteende klassificerar du kostnadstransaktioner som **fast kostnad** eller **variabel kostnad**.</span><span class="sxs-lookup"><span data-stu-id="d6d84-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="d6d84-151">Definiera kostnadsbeteenderegeln</span><span class="sxs-lookup"><span data-stu-id="d6d84-151">Define the cost behavior rule</span></span>

<span data-ttu-id="d6d84-152">I vissa fall är en del av kostnaden en fast avgift och återstående kostnad baseras på förbrukning.</span><span class="sxs-lookup"><span data-stu-id="d6d84-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="d6d84-153">Elräkningar matchar ofta denna definition.</span><span class="sxs-lookup"><span data-stu-id="d6d84-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="d6d84-154">När du betalar en fast avgift betalar du för förbrukning per kilowattimme (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d6d84-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="d6d84-155">Om avgiften t.ex. är en fast kostnad på 1 000,00 definieras kostnadsbeteenderegeln enligt följande:</span><span class="sxs-lookup"><span data-stu-id="d6d84-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="d6d84-156">Fast belopp 1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="d6d84-157">0 &lt;= 1 000,00 = fast</span><span class="sxs-lookup"><span data-stu-id="d6d84-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="d6d84-158">1 000,01 &lt; N = variabel</span><span class="sxs-lookup"><span data-stu-id="d6d84-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="d6d84-159">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-160">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-160">Journal</span></span></th>
<th><span data-ttu-id="d6d84-161">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="d6d84-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6d84-162">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="d6d84-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6d84-163">version</span><span class="sxs-lookup"><span data-stu-id="d6d84-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-164">00001</span><span class="sxs-lookup"><span data-stu-id="d6d84-164">00001</span></span></td>
<td><span data-ttu-id="d6d84-165">Journal för beräkning av kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="d6d84-166">Skatt</span><span class="sxs-lookup"><span data-stu-id="d6d84-166">Fiscal</span></span></td>
<td><span data-ttu-id="d6d84-167">2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-167">2017</span></span></td>
<td><span data-ttu-id="d6d84-168">Period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-168">Period 1</span></span></td>
<td><span data-ttu-id="d6d84-169">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6d84-170">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="d6d84-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-171">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-172">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-173">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-173">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-174">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-174">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-175">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-176">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="d6d84-177">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-177">CC099</span></span></td>
<td><span data-ttu-id="d6d84-178">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-178">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-179">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-179">10001</span></span></td>
<td><span data-ttu-id="d6d84-180">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-180">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-181">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="d6d84-181">Unclassified</span></span></td>
<td><span data-ttu-id="d6d84-182">10 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6d84-183">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="d6d84-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-184">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-185">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-185">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-186">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-186">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-187">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-187">Amount</span></span></th>
<th><span data-ttu-id="d6d84-188">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-189">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-189">CC099</span></span></td>
<td><span data-ttu-id="d6d84-190">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-190">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-191">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-191">10001</span></span></td>
<td><span data-ttu-id="d6d84-192">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-192">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-193">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="d6d84-193">Unclassified</span></span></td>
<td><span data-ttu-id="d6d84-194">10 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-194">10,000.00</span></span></td>
<td><span data-ttu-id="d6d84-195">3 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-196">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-196">CC099</span></span></td>
<td><span data-ttu-id="d6d84-197">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-197">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-198">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-198">10001</span></span></td>
<td><span data-ttu-id="d6d84-199">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-199">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-200">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="d6d84-200">Unclassified</span></span></td>
<td><span data-ttu-id="d6d84-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-201">-10,000.00</span></span></td>
<td><span data-ttu-id="d6d84-202">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-203">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-203">CC099</span></span></td>
<td><span data-ttu-id="d6d84-204">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-204">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-205">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-205">10001</span></span></td>
<td><span data-ttu-id="d6d84-206">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-206">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-207">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-207">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-208">1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-208">1,000.00</span></span></td>
<td><span data-ttu-id="d6d84-209">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-210">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-210">CC099</span></span></td>
<td><span data-ttu-id="d6d84-211">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-211">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-212">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-212">10001</span></span></td>
<td><span data-ttu-id="d6d84-213">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-213">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-214">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-214">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-215">9,000.00</span></span></td>
<td><span data-ttu-id="d6d84-216">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-217">För mer information, se [Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="d6d84-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="d6d84-218">Steg 2: Bearbeta beräkning av kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="d6d84-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="d6d84-219">Kostnadsfördelning används för att distribuera kostnad från ett kostnadsobjekt till ett eller flera andra kostnadsobjekt genom att tillämpa ett relevant allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="d6d84-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="d6d84-220">Kostnadsfördelning och kostnadsallokering skiljer sig genom att kostnadsfördelning alltid inträffar i nivån för det primära kostnadselementet i den ursprungliga kostnaden.</span><span class="sxs-lookup"><span data-stu-id="d6d84-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="d6d84-221">Definiera kostnadsfördelningsregeln</span><span class="sxs-lookup"><span data-stu-id="d6d84-221">Define the cost distribution rule</span></span>

<span data-ttu-id="d6d84-222">I affärsredovisning är elkostnader ofta registrerade som en klumpsumma.</span><span class="sxs-lookup"><span data-stu-id="d6d84-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="d6d84-223">I kostnadsredovisning är inte denna metod tillräckligt detaljerad.</span><span class="sxs-lookup"><span data-stu-id="d6d84-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="d6d84-224">Variabelkostnaden ska fördelas på det enskilda kostnadsobjektet på ett rättvist sätt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="d6d84-225">Den mest logiska allokeringsbasen är elförbrukning (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d6d84-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="d6d84-226">En statistikdimensionsmedlem som heter Elektricitet skapas och elförbrukningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="d6d84-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="d6d84-227">Som standard blir alla statistikdimensionsmedlemmar tillgängliga som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="d6d84-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-228">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-228">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="d6d84-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-230">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-230">CC001</span></span></td>
<td><span data-ttu-id="d6d84-231">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-231">HR</span></span></td>
<td><span data-ttu-id="d6d84-232">1 000</span><span class="sxs-lookup"><span data-stu-id="d6d84-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-233">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-233">CC002</span></span></td>
<td><span data-ttu-id="d6d84-234">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-234">Finance</span></span></td>
<td><span data-ttu-id="d6d84-235">6,000</span><span class="sxs-lookup"><span data-stu-id="d6d84-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-236">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-236">CC003</span></span></td>
<td><span data-ttu-id="d6d84-237">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-237">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-238">0</span><span class="sxs-lookup"><span data-stu-id="d6d84-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-239">I följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="d6d84-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-240">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-240">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-241">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-241">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-242">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-242">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-243">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-244">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-244">CC001</span></span></td>
<td><span data-ttu-id="d6d84-245">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-245">HR</span></span></td>
<td><span data-ttu-id="d6d84-246">1 000</span><span class="sxs-lookup"><span data-stu-id="d6d84-246">1,000</span></span></td>
<td><span data-ttu-id="d6d84-247">(1 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6d84-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d6d84-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-249">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-249">CC002</span></span></td>
<td><span data-ttu-id="d6d84-250">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-250">Finance</span></span></td>
<td><span data-ttu-id="d6d84-251">6,000</span><span class="sxs-lookup"><span data-stu-id="d6d84-251">6,000</span></span></td>
<td><span data-ttu-id="d6d84-252">(6 000 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6d84-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d6d84-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-254">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-254">CC003</span></span></td>
<td><span data-ttu-id="d6d84-255">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-255">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-256">0</span><span class="sxs-lookup"><span data-stu-id="d6d84-256">0</span></span></td>
<td><span data-ttu-id="d6d84-257">(0 ÷ 7 000) × 9 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6d84-258">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-259">Den fasta kostnaden ska fördelas jämnt på de enskilda kostnadsbärarna som har förbrukat el.</span><span class="sxs-lookup"><span data-stu-id="d6d84-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="d6d84-260">Du kan uppnå detta med statistikdimensionsmedlemmen i ett formelallokeringsunderlag: (Elektricitet &gt;0,00). Följande tabell visas resultatet när elförbrukningen används som ett allokeringsunderlag för rörliga kostnader.</span><span class="sxs-lookup"><span data-stu-id="d6d84-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-261">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-261">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-262">Formel</span><span class="sxs-lookup"><span data-stu-id="d6d84-262">Formula</span></span></th>
<th><span data-ttu-id="d6d84-263">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-263">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-264">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-264">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-265">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-266">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-266">CC001</span></span></td>
<td><span data-ttu-id="d6d84-267">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-267">HR</span></span></td>
<td><span data-ttu-id="d6d84-268">(1 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6d84-269">1</span><span class="sxs-lookup"><span data-stu-id="d6d84-269">1</span></span></td>
<td><span data-ttu-id="d6d84-270">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6d84-271">500.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-272">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-272">CC002</span></span></td>
<td><span data-ttu-id="d6d84-273">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-273">Finance</span></span></td>
<td><span data-ttu-id="d6d84-274">(6 000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6d84-275">1</span><span class="sxs-lookup"><span data-stu-id="d6d84-275">1</span></span></td>
<td><span data-ttu-id="d6d84-276">(1 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6d84-277">500.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-278">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-278">CC003</span></span></td>
<td><span data-ttu-id="d6d84-279">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-279">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6d84-281">0</span><span class="sxs-lookup"><span data-stu-id="d6d84-281">0</span></span></td>
<td><span data-ttu-id="d6d84-282">(0 ÷ 2) × 1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6d84-283">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d6d84-284">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-285">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-285">Journal</span></span></th>
<th><span data-ttu-id="d6d84-286">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="d6d84-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6d84-287">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="d6d84-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6d84-288">version</span><span class="sxs-lookup"><span data-stu-id="d6d84-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-289">00002</span><span class="sxs-lookup"><span data-stu-id="d6d84-289">00002</span></span></td>
<td><span data-ttu-id="d6d84-290">Beräkningsjournal för kostnadsfördelning</span><span class="sxs-lookup"><span data-stu-id="d6d84-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="d6d84-291">Skatt</span><span class="sxs-lookup"><span data-stu-id="d6d84-291">Fiscal</span></span></td>
<td><span data-ttu-id="d6d84-292">2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-292">2017</span></span></td>
<td><span data-ttu-id="d6d84-293">Period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-293">Period 1</span></span></td>
<td><span data-ttu-id="d6d84-294">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6d84-295">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="d6d84-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-296">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-297">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-298">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-298">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-299">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-299">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-300">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-301">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-302">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-302">CC099</span></span></td>
<td><span data-ttu-id="d6d84-303">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-303">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-304">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-304">10001</span></span></td>
<td><span data-ttu-id="d6d84-305">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-305">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-306">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-306">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-307">1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-308">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-309">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-309">CC099</span></span></td>
<td><span data-ttu-id="d6d84-310">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-310">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-311">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-311">10001</span></span></td>
<td><span data-ttu-id="d6d84-312">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-312">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-313">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-313">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6d84-315">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="d6d84-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-316">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-317">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-317">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-318">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-318">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-319">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-319">Amount</span></span></th>
<th><span data-ttu-id="d6d84-320">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-321">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-321">CC099</span></span></td>
<td><span data-ttu-id="d6d84-322">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-322">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-323">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-323">10001</span></span></td>
<td><span data-ttu-id="d6d84-324">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-324">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-325">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-325">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-326">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-326">-1,000.00</span></span></td>
<td><span data-ttu-id="d6d84-327">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-328">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-328">CC001</span></span></td>
<td><span data-ttu-id="d6d84-329">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-329">HR</span></span></td>
<td><span data-ttu-id="d6d84-330">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-330">10001</span></span></td>
<td><span data-ttu-id="d6d84-331">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-331">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-332">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-332">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-333">500.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-333">500.00</span></span></td>
<td><span data-ttu-id="d6d84-334">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-335">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-335">CC002</span></span></td>
<td><span data-ttu-id="d6d84-336">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-336">Finance</span></span></td>
<td><span data-ttu-id="d6d84-337">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-337">10001</span></span></td>
<td><span data-ttu-id="d6d84-338">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-338">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-339">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-339">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-340">500.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-340">500.00</span></span></td>
<td><span data-ttu-id="d6d84-341">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-342">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-342">CC099</span></span></td>
<td><span data-ttu-id="d6d84-343">Standardkostnadscenter</span><span class="sxs-lookup"><span data-stu-id="d6d84-343">Default cost center</span></span></td>
<td><span data-ttu-id="d6d84-344">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-344">10001</span></span></td>
<td><span data-ttu-id="d6d84-345">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-345">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-346">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-346">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-347">-9 000,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-347">-9,000.00</span></span></td>
<td><span data-ttu-id="d6d84-348">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-349">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-349">CC001</span></span></td>
<td><span data-ttu-id="d6d84-350">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-350">HR</span></span></td>
<td><span data-ttu-id="d6d84-351">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-351">10001</span></span></td>
<td><span data-ttu-id="d6d84-352">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-352">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-353">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-353">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d6d84-354">1,285.71</span></span></td>
<td><span data-ttu-id="d6d84-355">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-356">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-356">CC002</span></span></td>
<td><span data-ttu-id="d6d84-357">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-357">Finance</span></span></td>
<td><span data-ttu-id="d6d84-358">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-358">10001</span></span></td>
<td><span data-ttu-id="d6d84-359">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-359">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-360">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-360">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d6d84-361">7,714.29</span></span></td>
<td><span data-ttu-id="d6d84-362">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-363">För mer information, se [Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="d6d84-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="d6d84-364">Steg 3: Bearbeta beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="d6d84-365">Den indirekta kostnaden används för att debitera en eller flera specifika kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="d6d84-366">Avgiften baseras på en förutbestämd kostnadstarriff och storleken från det tilldelade fördelningsunderlaget.</span><span class="sxs-lookup"><span data-stu-id="d6d84-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="d6d84-367">Definiera en indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-367">Define the overhead rate</span></span>

<span data-ttu-id="d6d84-368">Kostnadsobjekt CC001 HR bidrar till en uppsättning interna projekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="d6d84-369">En statistikdimensionsmedlem som heter HR skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="d6d84-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-370">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-370">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-371">Timmar</span><span class="sxs-lookup"><span data-stu-id="d6d84-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-372">Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-373">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-373">Project 1</span></span></td>
<td><span data-ttu-id="d6d84-374">3</span><span class="sxs-lookup"><span data-stu-id="d6d84-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-375">Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-376">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-376">Project 2</span></span></td>
<td><span data-ttu-id="d6d84-377">1</span><span class="sxs-lookup"><span data-stu-id="d6d84-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-378">En förutbestämd kostnadstarriff för kostnadsprojektets bidrag har definierats.</span><span class="sxs-lookup"><span data-stu-id="d6d84-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-379">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-379">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-380">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-380">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-381">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-381">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-382">Enheter</span><span class="sxs-lookup"><span data-stu-id="d6d84-382">Units</span></span></th>
<th><span data-ttu-id="d6d84-383">Kurs</span><span class="sxs-lookup"><span data-stu-id="d6d84-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-384">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-384">CC001</span></span></td>
<td><span data-ttu-id="d6d84-385">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-385">HR</span></span></td>
<td><span data-ttu-id="d6d84-386">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-386">10001</span></span></td>
<td><span data-ttu-id="d6d84-387">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-387">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-388">1</span><span class="sxs-lookup"><span data-stu-id="d6d84-388">1</span></span></td>
<td><span data-ttu-id="d6d84-389">10</span><span class="sxs-lookup"><span data-stu-id="d6d84-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-390">Följande tabell visar resultatet när HR-projekt används som allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="d6d84-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-391">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-391">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-392">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-392">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-393">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-393">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-394">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-394">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-395">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-396">Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-397">Projekt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-397">Project 1</span></span></td>
<td><span data-ttu-id="d6d84-398">3</span><span class="sxs-lookup"><span data-stu-id="d6d84-398">3</span></span></td>
<td><span data-ttu-id="d6d84-399">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-399">10001</span></span></td>
<td><span data-ttu-id="d6d84-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d6d84-401">30,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-402">Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-403">Projekt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-403">Project 2</span></span></td>
<td><span data-ttu-id="d6d84-404">1</span><span class="sxs-lookup"><span data-stu-id="d6d84-404">1</span></span></td>
<td><span data-ttu-id="d6d84-405">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-405">10001</span></span></td>
<td><span data-ttu-id="d6d84-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d6d84-407">10,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d6d84-408">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-409">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-409">Journal</span></span></th>
<th><span data-ttu-id="d6d84-410">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="d6d84-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6d84-411">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="d6d84-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6d84-412">version</span><span class="sxs-lookup"><span data-stu-id="d6d84-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-413">00003</span><span class="sxs-lookup"><span data-stu-id="d6d84-413">00003</span></span></td>
<td><span data-ttu-id="d6d84-414">Journal för beräkning av indirekt kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="d6d84-415">Skatt</span><span class="sxs-lookup"><span data-stu-id="d6d84-415">Fiscal</span></span></td>
<td><span data-ttu-id="d6d84-416">2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-416">2017</span></span></td>
<td><span data-ttu-id="d6d84-417">Period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-417">Period 1</span></span></td>
<td><span data-ttu-id="d6d84-418">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="d6d84-419">Journalposter för beräkning av indirekt kostnad (Journalposter för beräkning av indirekt kostnad)</span><span class="sxs-lookup"><span data-stu-id="d6d84-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-420">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-421">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-421">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-422">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-423">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-424">Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-425">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-426">3,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-427">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-428">Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-429">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-430">1,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6d84-431">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="d6d84-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-432">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-433">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-433">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-434">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-434">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-435">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-435">Amount</span></span></th>
<th><span data-ttu-id="d6d84-436">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="d6d84-437">CC0001</span></span></td>
<td><span data-ttu-id="d6d84-438">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-438">HR</span></span></td>
<td><span data-ttu-id="d6d84-439">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-439">10001</span></span></td>
<td><span data-ttu-id="d6d84-440">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-440">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-441">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-441">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-442">-30.00</span></span></td>
<td><span data-ttu-id="d6d84-443">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-444">Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-445">Internt proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d6d84-446">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-446">10001</span></span></td>
<td><span data-ttu-id="d6d84-447">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-447">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-448">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-448">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-449">30,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-449">30.00</span></span></td>
<td><span data-ttu-id="d6d84-450">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-451">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-451">CC001</span></span></td>
<td><span data-ttu-id="d6d84-452">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-452">HR</span></span></td>
<td><span data-ttu-id="d6d84-453">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-453">10001</span></span></td>
<td><span data-ttu-id="d6d84-454">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-454">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-455">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-455">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-456">-10.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-456">-10.00</span></span></td>
<td><span data-ttu-id="d6d84-457">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-458">Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-459">Internt proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d6d84-460">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-460">10001</span></span></td>
<td><span data-ttu-id="d6d84-461">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-461">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-462">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-462">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-463">10,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-463">10.00</span></span></td>
<td><span data-ttu-id="d6d84-464">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-465">För mer information, se [Utföra beräkning av indirekta kostnader](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="d6d84-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="d6d84-466">Steg 4: Bearbeta beräkning av kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="d6d84-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="d6d84-467">Allokering används för att allkokera saldot på ett kostnadsobjekt till andra kostnadsobjekt genom att använda ett allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="d6d84-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="d6d84-468">Finance stöder ömsesidig allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="d6d84-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="d6d84-469">I den inbördes allokeringsmetoden identifieras de ömsesidiga tjänsterna som de extra kostnadobjekten utbyter fullständigt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="d6d84-470">Systemet avgör automatiskt den korrekta ordnigen för att utföra allokeringar i.</span><span class="sxs-lookup"><span data-stu-id="d6d84-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="d6d84-471">Saldot på ett kostnadsobjekt allkoeras genom ett enda allokeringsunderlag.</span><span class="sxs-lookup"><span data-stu-id="d6d84-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="d6d84-472">Allokeringar över kostnadsobjektdimensioner och deras respektive medlemmar stöds.</span><span class="sxs-lookup"><span data-stu-id="d6d84-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="d6d84-473">Allokeringsordern styrs av kostnadskontrollenheten.</span><span class="sxs-lookup"><span data-stu-id="d6d84-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="d6d84-474">[![Ömsesidig metod](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="d6d84-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="d6d84-475">Definiera kostnadsallokering</span><span class="sxs-lookup"><span data-stu-id="d6d84-475">Define the cost allocation</span></span>

<span data-ttu-id="d6d84-476">Här följer ett enkelt exempel som förklarar hur du kan spåra kostnadsflödet.</span><span class="sxs-lookup"><span data-stu-id="d6d84-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="d6d84-477">Kostnadsobjekt CC001 HR bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="d6d84-478">En statistikdimensionsmedlem som heter HR-tjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="d6d84-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-479">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-479">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-480">HR-tjänster</span><span class="sxs-lookup"><span data-stu-id="d6d84-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-481">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-481">CC002</span></span></td>
<td><span data-ttu-id="d6d84-482">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-482">Finance</span></span></td>
<td><span data-ttu-id="d6d84-483">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-484">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-484">CC003</span></span></td>
<td><span data-ttu-id="d6d84-485">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-485">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-486">55</span><span class="sxs-lookup"><span data-stu-id="d6d84-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-487">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-487">CC004</span></span></td>
<td><span data-ttu-id="d6d84-488">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-488">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-489">10</span><span class="sxs-lookup"><span data-stu-id="d6d84-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-490">Kostnadsobjekt CC002 Finans bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="d6d84-491">En statistikdimensionsmedlem som heter Finanstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="d6d84-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-492">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-492">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-493">Finanstjänster</span><span class="sxs-lookup"><span data-stu-id="d6d84-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-494">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-494">CC003</span></span></td>
<td><span data-ttu-id="d6d84-495">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-495">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-496">65</span><span class="sxs-lookup"><span data-stu-id="d6d84-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-497">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-497">CC004</span></span></td>
<td><span data-ttu-id="d6d84-498">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-498">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-499">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-500">Kostnadsobjekt CC003 Sammansättning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="d6d84-501">En statistikdimensionsmedlem som heter Sammansättningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="d6d84-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-502">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-502">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-503">Sammansättningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="d6d84-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-504">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-505">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-505">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-506">60</span><span class="sxs-lookup"><span data-stu-id="d6d84-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-507">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-508">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-508">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-509">20</span><span class="sxs-lookup"><span data-stu-id="d6d84-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-510">Kostnadsobjekt CC004 Förpackning bidrar till flera kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="d6d84-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="d6d84-511">En statistikdimensionsmedlem som heter Förpackningstjänster skapas för att mäta förbrukad storlek.</span><span class="sxs-lookup"><span data-stu-id="d6d84-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-512">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-512">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-513">Förpackningstjänster (timmar)</span><span class="sxs-lookup"><span data-stu-id="d6d84-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-514">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-515">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-515">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-516">80</span><span class="sxs-lookup"><span data-stu-id="d6d84-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-517">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-518">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-518">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-519">15</span><span class="sxs-lookup"><span data-stu-id="d6d84-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d6d84-520">Statistikmått som t.ex. produktionstimmar som en produkt förbrukar härledas ur källinformationen.</span><span class="sxs-lookup"><span data-stu-id="d6d84-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="d6d84-521">Mer information finns i [Providermallar för statistisk mätning](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="d6d84-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="d6d84-522">Följande tabell visar resultatet när HR-tjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="d6d84-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-523">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-523">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-524">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-524">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-525">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-525">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-526">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-526">Amount</span></span></th>
<th><span data-ttu-id="d6d84-527">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-528">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-528">CC002</span></span></td>
<td><span data-ttu-id="d6d84-529">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-529">Finance</span></span></td>
<td><span data-ttu-id="d6d84-530">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-530">35</span></span></td>
<td><span data-ttu-id="d6d84-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6d84-532">175.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-532">175.00</span></span></td>
<td><span data-ttu-id="d6d84-533">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-534">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-534">CC003</span></span></td>
<td><span data-ttu-id="d6d84-535">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-535">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-536">55</span><span class="sxs-lookup"><span data-stu-id="d6d84-536">55</span></span></td>
<td><span data-ttu-id="d6d84-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6d84-538">275.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-538">275.00</span></span></td>
<td><span data-ttu-id="d6d84-539">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-540">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-540">CC004</span></span></td>
<td><span data-ttu-id="d6d84-541">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-541">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-542">10</span><span class="sxs-lookup"><span data-stu-id="d6d84-542">10</span></span></td>
<td><span data-ttu-id="d6d84-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6d84-544">50,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-544">50.00</span></span></td>
<td><span data-ttu-id="d6d84-545">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-546">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-546">CC002</span></span></td>
<td><span data-ttu-id="d6d84-547">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-547">Finance</span></span></td>
<td><span data-ttu-id="d6d84-548">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-548">35</span></span></td>
<td><span data-ttu-id="d6d84-549">(35 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="d6d84-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6d84-550">436.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-550">436.00</span></span></td>
<td><span data-ttu-id="d6d84-551">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-552">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-552">CC003</span></span></td>
<td><span data-ttu-id="d6d84-553">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-553">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-554">55</span><span class="sxs-lookup"><span data-stu-id="d6d84-554">55</span></span></td>
<td><span data-ttu-id="d6d84-555">(55 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="d6d84-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6d84-556">685.14</span><span class="sxs-lookup"><span data-stu-id="d6d84-556">685.14</span></span></td>
<td><span data-ttu-id="d6d84-557">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-558">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-558">CC004</span></span></td>
<td><span data-ttu-id="d6d84-559">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-559">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-560">10</span><span class="sxs-lookup"><span data-stu-id="d6d84-560">10</span></span></td>
<td><span data-ttu-id="d6d84-561">(10 ÷ 100) × 1 245,71</span><span class="sxs-lookup"><span data-stu-id="d6d84-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6d84-562">124.57</span><span class="sxs-lookup"><span data-stu-id="d6d84-562">124.57</span></span></td>
<td><span data-ttu-id="d6d84-563">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-564">Följande tabell visar resultatet när Finanstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="d6d84-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-565">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-565">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-566">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-566">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-567">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-567">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-568">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-568">Amount</span></span></th>
<th><span data-ttu-id="d6d84-569">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-570">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-570">CC003</span></span></td>
<td><span data-ttu-id="d6d84-571">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-571">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-572">65</span><span class="sxs-lookup"><span data-stu-id="d6d84-572">65</span></span></td>
<td><span data-ttu-id="d6d84-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d6d84-574">438.75</span><span class="sxs-lookup"><span data-stu-id="d6d84-574">438.75</span></span></td>
<td><span data-ttu-id="d6d84-575">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-576">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-576">CC004</span></span></td>
<td><span data-ttu-id="d6d84-577">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-577">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-578">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-578">35</span></span></td>
<td><span data-ttu-id="d6d84-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d6d84-580">236.25</span><span class="sxs-lookup"><span data-stu-id="d6d84-580">236.25</span></span></td>
<td><span data-ttu-id="d6d84-581">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-582">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-582">CC003</span></span></td>
<td><span data-ttu-id="d6d84-583">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-583">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-584">65</span><span class="sxs-lookup"><span data-stu-id="d6d84-584">65</span></span></td>
<td><span data-ttu-id="d6d84-585">(65 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d6d84-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d6d84-586">5,297.69</span></span></td>
<td><span data-ttu-id="d6d84-587">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-588">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-588">CC004</span></span></td>
<td><span data-ttu-id="d6d84-589">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-589">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-590">35</span><span class="sxs-lookup"><span data-stu-id="d6d84-590">35</span></span></td>
<td><span data-ttu-id="d6d84-591">(35 ÷ 100) × (7 714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d6d84-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d6d84-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d6d84-592">2,852.60</span></span></td>
<td><span data-ttu-id="d6d84-593">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-594">Följande tabell visar resultatet när Sammansättningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="d6d84-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-595">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-595">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-596">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-596">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-597">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-597">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-598">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-598">Amount</span></span></th>
<th><span data-ttu-id="d6d84-599">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-600">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-601">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-601">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-602">60</span><span class="sxs-lookup"><span data-stu-id="d6d84-602">60</span></span></td>
<td><span data-ttu-id="d6d84-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d6d84-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d6d84-604">535.31</span><span class="sxs-lookup"><span data-stu-id="d6d84-604">535.31</span></span></td>
<td><span data-ttu-id="d6d84-605">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-606">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-607">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-607">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-608">20</span><span class="sxs-lookup"><span data-stu-id="d6d84-608">20</span></span></td>
<td><span data-ttu-id="d6d84-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d6d84-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d6d84-610">178.44</span><span class="sxs-lookup"><span data-stu-id="d6d84-610">178.44</span></span></td>
<td><span data-ttu-id="d6d84-611">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-612">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-613">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-613">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-614">60</span><span class="sxs-lookup"><span data-stu-id="d6d84-614">60</span></span></td>
<td><span data-ttu-id="d6d84-615">(60 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d6d84-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d6d84-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d6d84-616">4,487.12</span></span></td>
<td><span data-ttu-id="d6d84-617">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-618">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-619">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-619">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-620">20</span><span class="sxs-lookup"><span data-stu-id="d6d84-620">20</span></span></td>
<td><span data-ttu-id="d6d84-621">(20 ÷ 80) × (5 297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d6d84-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d6d84-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d6d84-622">1,495.71</span></span></td>
<td><span data-ttu-id="d6d84-623">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6d84-624">Följande tabell visar resultatet när Förpackningstjänster för privatpersoner används som ett allokeringsunderlag för totalkostnad (fast kostnad och variabel kostnad).</span><span class="sxs-lookup"><span data-stu-id="d6d84-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-625">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-625">Cost object</span></span></th>
<th><span data-ttu-id="d6d84-626">Storlek</span><span class="sxs-lookup"><span data-stu-id="d6d84-626">Magnitude</span></span></th>
<th><span data-ttu-id="d6d84-627">Allokeringsfaktor</span><span class="sxs-lookup"><span data-stu-id="d6d84-627">Allocation factor</span></span></th>
<th><span data-ttu-id="d6d84-628">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-628">Amount</span></span></th>
<th><span data-ttu-id="d6d84-629">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-630">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-631">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-631">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-632">80</span><span class="sxs-lookup"><span data-stu-id="d6d84-632">80</span></span></td>
<td><span data-ttu-id="d6d84-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d6d84-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d6d84-634">241.05</span><span class="sxs-lookup"><span data-stu-id="d6d84-634">241.05</span></span></td>
<td><span data-ttu-id="d6d84-635">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-636">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-637">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-637">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-638">15</span><span class="sxs-lookup"><span data-stu-id="d6d84-638">15</span></span></td>
<td><span data-ttu-id="d6d84-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d6d84-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d6d84-640">45.20</span><span class="sxs-lookup"><span data-stu-id="d6d84-640">45.20</span></span></td>
<td><span data-ttu-id="d6d84-641">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-642">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-643">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-643">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-644">80</span><span class="sxs-lookup"><span data-stu-id="d6d84-644">80</span></span></td>
<td><span data-ttu-id="d6d84-645">(80 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d6d84-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d6d84-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d6d84-646">2,507.09</span></span></td>
<td><span data-ttu-id="d6d84-647">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-648">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-649">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-649">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-650">15</span><span class="sxs-lookup"><span data-stu-id="d6d84-650">15</span></span></td>
<td><span data-ttu-id="d6d84-651">(15 ÷ 95) × (2 852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d6d84-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d6d84-652">470.08</span><span class="sxs-lookup"><span data-stu-id="d6d84-652">470.08</span></span></td>
<td><span data-ttu-id="d6d84-653">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6d84-654">Journalposter (Journalposter för kostnadsobjektsaldo)</span><span class="sxs-lookup"><span data-stu-id="d6d84-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-655">Journal</span><span class="sxs-lookup"><span data-stu-id="d6d84-655">Journal</span></span></th>
<th><span data-ttu-id="d6d84-656">Journaltyp</span><span class="sxs-lookup"><span data-stu-id="d6d84-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6d84-657">Räkenskapskalenderperiod</span><span class="sxs-lookup"><span data-stu-id="d6d84-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6d84-658">version</span><span class="sxs-lookup"><span data-stu-id="d6d84-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-659">00004</span><span class="sxs-lookup"><span data-stu-id="d6d84-659">00004</span></span></td>
<td><span data-ttu-id="d6d84-660">Kostnadsallokeringsjournal</span><span class="sxs-lookup"><span data-stu-id="d6d84-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="d6d84-661">Skatt</span><span class="sxs-lookup"><span data-stu-id="d6d84-661">Fiscal</span></span></td>
<td><span data-ttu-id="d6d84-662">2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-662">2017</span></span></td>
<td><span data-ttu-id="d6d84-663">Period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-663">Period 1</span></span></td>
<td><span data-ttu-id="d6d84-664">Beräkning av indirekta kostnader/2017-02-01 23:51:00/redovisning/2017/period 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="d6d84-665">Journalrader</span><span class="sxs-lookup"><span data-stu-id="d6d84-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6d84-666">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-667">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-668">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-668">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-669">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-669">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-670">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-671">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-672">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-672">CC001</span></span></td>
<td><span data-ttu-id="d6d84-673">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-673">HR</span></span></td>
<td><span data-ttu-id="d6d84-674">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-674">10001</span></span></td>
<td><span data-ttu-id="d6d84-675">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-675">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-676">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-676">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-677">500.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-678">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-679">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-679">CC001</span></span></td>
<td><span data-ttu-id="d6d84-680">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-680">HR</span></span></td>
<td><span data-ttu-id="d6d84-681">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-681">10001</span></span></td>
<td><span data-ttu-id="d6d84-682">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-682">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-683">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-683">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="d6d84-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-685">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-686">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-686">CC002</span></span></td>
<td><span data-ttu-id="d6d84-687">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-687">Finance</span></span></td>
<td><span data-ttu-id="d6d84-688">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-688">10001</span></span></td>
<td><span data-ttu-id="d6d84-689">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-689">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-690">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-690">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-691">675.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-692">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-693">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-693">CC002</span></span></td>
<td><span data-ttu-id="d6d84-694">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-694">Finance</span></span></td>
<td><span data-ttu-id="d6d84-695">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-695">10001</span></span></td>
<td><span data-ttu-id="d6d84-696">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-696">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-697">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-697">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="d6d84-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-699">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-700">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-700">CC003</span></span></td>
<td><span data-ttu-id="d6d84-701">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-701">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-702">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-702">10001</span></span></td>
<td><span data-ttu-id="d6d84-703">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-703">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-704">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-704">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-705">713.75</span><span class="sxs-lookup"><span data-stu-id="d6d84-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-706">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-707">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-707">CC003</span></span></td>
<td><span data-ttu-id="d6d84-708">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-708">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-709">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-709">10001</span></span></td>
<td><span data-ttu-id="d6d84-710">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-710">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-711">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-711">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="d6d84-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-713">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-714">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-714">CC003</span></span></td>
<td><span data-ttu-id="d6d84-715">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-715">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-716">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-716">10001</span></span></td>
<td><span data-ttu-id="d6d84-717">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-717">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-718">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-718">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-719">286.25</span><span class="sxs-lookup"><span data-stu-id="d6d84-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-720">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-721">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-721">CC003</span></span></td>
<td><span data-ttu-id="d6d84-722">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-722">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-723">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-723">10001</span></span></td>
<td><span data-ttu-id="d6d84-724">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-724">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-725">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-725">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="d6d84-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-727">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-728">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-729">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-729">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-730">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-730">10001</span></span></td>
<td><span data-ttu-id="d6d84-731">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-731">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-732">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-732">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-733">776.36</span><span class="sxs-lookup"><span data-stu-id="d6d84-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-734">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-735">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-736">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-736">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-737">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-737">10001</span></span></td>
<td><span data-ttu-id="d6d84-738">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-738">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-739">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-739">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d6d84-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-741">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-742">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-743">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-743">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-744">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-744">10001</span></span></td>
<td><span data-ttu-id="d6d84-745">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-745">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-746">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-746">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-747">223.64</span><span class="sxs-lookup"><span data-stu-id="d6d84-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-748">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6d84-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-749">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-750">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-750">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-751">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-751">10001</span></span></td>
<td><span data-ttu-id="d6d84-752">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-752">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-753">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-753">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d6d84-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6d84-755">Kostnadsposter</span><span class="sxs-lookup"><span data-stu-id="d6d84-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6d84-756">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6d84-757">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-757">Cost element</span></span></th>
<th><span data-ttu-id="d6d84-758">Kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="d6d84-758">Cost behavior</span></span></th>
<th><span data-ttu-id="d6d84-759">Belopp</span><span class="sxs-lookup"><span data-stu-id="d6d84-759">Amount</span></span></th>
<th><span data-ttu-id="d6d84-760">Räkenskapsdatum</span><span class="sxs-lookup"><span data-stu-id="d6d84-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6d84-761">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-761">CC001</span></span></td>
<td><span data-ttu-id="d6d84-762">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-762">HR</span></span></td>
<td><span data-ttu-id="d6d84-763">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-763">10001</span></span></td>
<td><span data-ttu-id="d6d84-764">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-764">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-765">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-765">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-766">-500.00</span></span></td>
<td><span data-ttu-id="d6d84-767">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-768">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-768">CC002</span></span></td>
<td><span data-ttu-id="d6d84-769">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-769">Finance</span></span></td>
<td><span data-ttu-id="d6d84-770">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-770">10001</span></span></td>
<td><span data-ttu-id="d6d84-771">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-771">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-772">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-772">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-773">175.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-773">175.00</span></span></td>
<td><span data-ttu-id="d6d84-774">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-775">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-775">CC003</span></span></td>
<td><span data-ttu-id="d6d84-776">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-776">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-777">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-777">10001</span></span></td>
<td><span data-ttu-id="d6d84-778">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-778">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-779">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-779">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-780">275.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-780">275.00</span></span></td>
<td><span data-ttu-id="d6d84-781">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-782">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-782">CC004</span></span></td>
<td><span data-ttu-id="d6d84-783">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-783">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-784">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-784">10001</span></span></td>
<td><span data-ttu-id="d6d84-785">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-785">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-786">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-786">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-787">50,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-787">50,00</span></span></td>
<td><span data-ttu-id="d6d84-788">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-789">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-789">CC001</span></span></td>
<td><span data-ttu-id="d6d84-790">Personal</span><span class="sxs-lookup"><span data-stu-id="d6d84-790">HR</span></span></td>
<td><span data-ttu-id="d6d84-791">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-791">10001</span></span></td>
<td><span data-ttu-id="d6d84-792">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-792">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-793">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-793">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-794">-1 245,71</span><span class="sxs-lookup"><span data-stu-id="d6d84-794">-1,245.71</span></span></td>
<td><span data-ttu-id="d6d84-795">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-796">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-796">CC002</span></span></td>
<td><span data-ttu-id="d6d84-797">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-797">Finance</span></span></td>
<td><span data-ttu-id="d6d84-798">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-798">10001</span></span></td>
<td><span data-ttu-id="d6d84-799">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-799">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-800">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-800">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-801">436.00</span><span class="sxs-lookup"><span data-stu-id="d6d84-801">436.00</span></span></td>
<td><span data-ttu-id="d6d84-802">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-803">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-803">CC003</span></span></td>
<td><span data-ttu-id="d6d84-804">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-804">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-805">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-805">10001</span></span></td>
<td><span data-ttu-id="d6d84-806">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-806">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-807">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-807">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-808">685.14</span><span class="sxs-lookup"><span data-stu-id="d6d84-808">685.14</span></span></td>
<td><span data-ttu-id="d6d84-809">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-810">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-810">CC004</span></span></td>
<td><span data-ttu-id="d6d84-811">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-811">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-812">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-812">10001</span></span></td>
<td><span data-ttu-id="d6d84-813">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-813">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-814">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-814">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-815">124.57</span><span class="sxs-lookup"><span data-stu-id="d6d84-815">124.57</span></span></td>
<td><span data-ttu-id="d6d84-816">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-817">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-817">CC002</span></span></td>
<td><span data-ttu-id="d6d84-818">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-818">Finance</span></span></td>
<td><span data-ttu-id="d6d84-819">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-819">10001</span></span></td>
<td><span data-ttu-id="d6d84-820">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-820">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-821">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-821">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-822">-675.00</span></span></td>
<td><span data-ttu-id="d6d84-823">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-824">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-824">CC003</span></span></td>
<td><span data-ttu-id="d6d84-825">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-825">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-826">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-826">10001</span></span></td>
<td><span data-ttu-id="d6d84-827">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-827">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-828">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-828">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-829">438.75</span><span class="sxs-lookup"><span data-stu-id="d6d84-829">438.75</span></span></td>
<td><span data-ttu-id="d6d84-830">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-831">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-831">CC004</span></span></td>
<td><span data-ttu-id="d6d84-832">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-832">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-833">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-833">10001</span></span></td>
<td><span data-ttu-id="d6d84-834">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-834">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-835">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-835">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-836">236.25</span><span class="sxs-lookup"><span data-stu-id="d6d84-836">236.25</span></span></td>
<td><span data-ttu-id="d6d84-837">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-838">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-838">CC002</span></span></td>
<td><span data-ttu-id="d6d84-839">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="d6d84-839">Finance</span></span></td>
<td><span data-ttu-id="d6d84-840">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-840">10001</span></span></td>
<td><span data-ttu-id="d6d84-841">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-841">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-842">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-842">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-843">-8 150,29</span><span class="sxs-lookup"><span data-stu-id="d6d84-843">-8,150.29</span></span></td>
<td><span data-ttu-id="d6d84-844">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-845">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-845">CC003</span></span></td>
<td><span data-ttu-id="d6d84-846">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-846">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-847">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-847">10001</span></span></td>
<td><span data-ttu-id="d6d84-848">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-848">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-849">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-849">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d6d84-850">5,297.69</span></span></td>
<td><span data-ttu-id="d6d84-851">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-852">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-852">CC004</span></span></td>
<td><span data-ttu-id="d6d84-853">Paketering</span><span class="sxs-lookup"><span data-stu-id="d6d84-853">Packaging</span></span></td>
<td><span data-ttu-id="d6d84-854">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-854">10001</span></span></td>
<td><span data-ttu-id="d6d84-855">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-855">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-856">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-856">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d6d84-857">2,852.60</span></span></td>
<td><span data-ttu-id="d6d84-858">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-859">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-859">CC003</span></span></td>
<td><span data-ttu-id="d6d84-860">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-860">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-861">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-861">10001</span></span></td>
<td><span data-ttu-id="d6d84-862">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-862">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-863">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-863">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="d6d84-864">-713.75</span></span></td>
<td><span data-ttu-id="d6d84-865">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-866">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-867">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-867">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-868">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-868">10001</span></span></td>
<td><span data-ttu-id="d6d84-869">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-869">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-870">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-870">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-871">535.31</span><span class="sxs-lookup"><span data-stu-id="d6d84-871">535.31</span></span></td>
<td><span data-ttu-id="d6d84-872">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-873">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-874">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-874">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-875">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-875">10001</span></span></td>
<td><span data-ttu-id="d6d84-876">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-876">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-877">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-877">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-878">178.44</span><span class="sxs-lookup"><span data-stu-id="d6d84-878">178.44</span></span></td>
<td><span data-ttu-id="d6d84-879">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-880">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-880">CC003</span></span></td>
<td><span data-ttu-id="d6d84-881">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-881">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-882">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-882">10001</span></span></td>
<td><span data-ttu-id="d6d84-883">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-883">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-884">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-884">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-885">-5 982,83</span><span class="sxs-lookup"><span data-stu-id="d6d84-885">-5,982.83</span></span></td>
<td><span data-ttu-id="d6d84-886">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-887">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-888">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-888">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-889">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-889">10001</span></span></td>
<td><span data-ttu-id="d6d84-890">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-890">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-891">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-891">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d6d84-892">4,487.12</span></span></td>
<td><span data-ttu-id="d6d84-893">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-894">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-895">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-895">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-896">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-896">10001</span></span></td>
<td><span data-ttu-id="d6d84-897">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-897">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-898">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-898">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d6d84-899">1,495.71</span></span></td>
<td><span data-ttu-id="d6d84-900">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-901">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-901">CC003</span></span></td>
<td><span data-ttu-id="d6d84-902">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-902">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-903">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-903">10001</span></span></td>
<td><span data-ttu-id="d6d84-904">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-904">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-905">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-905">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="d6d84-906">-286.25</span></span></td>
<td><span data-ttu-id="d6d84-907">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-908">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-909">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-909">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-910">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-910">10001</span></span></td>
<td><span data-ttu-id="d6d84-911">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-911">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-912">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-912">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-913">241.05</span><span class="sxs-lookup"><span data-stu-id="d6d84-913">241.05</span></span></td>
<td><span data-ttu-id="d6d84-914">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-915">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-916">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-916">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-917">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-917">10001</span></span></td>
<td><span data-ttu-id="d6d84-918">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-918">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-919">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-919">Fixed cost</span></span></td>
<td><span data-ttu-id="d6d84-920">45.20</span><span class="sxs-lookup"><span data-stu-id="d6d84-920">45.20</span></span></td>
<td><span data-ttu-id="d6d84-921">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-922">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-922">CC003</span></span></td>
<td><span data-ttu-id="d6d84-923">Sammansättning</span><span class="sxs-lookup"><span data-stu-id="d6d84-923">Assembly</span></span></td>
<td><span data-ttu-id="d6d84-924">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-924">10001</span></span></td>
<td><span data-ttu-id="d6d84-925">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-925">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-926">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-926">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-927">-2 977,17</span><span class="sxs-lookup"><span data-stu-id="d6d84-927">-2,977.17</span></span></td>
<td><span data-ttu-id="d6d84-928">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-929">Prod 1</span></span></td>
<td><span data-ttu-id="d6d84-930">Produkt 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-930">Product 1</span></span></td>
<td><span data-ttu-id="d6d84-931">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-931">10001</span></span></td>
<td><span data-ttu-id="d6d84-932">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-932">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-933">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-933">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d6d84-934">2,507.09</span></span></td>
<td><span data-ttu-id="d6d84-935">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6d84-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-936">Prod 2</span></span></td>
<td><span data-ttu-id="d6d84-937">Produkt 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-937">Product 2</span></span></td>
<td><span data-ttu-id="d6d84-938">10001</span><span class="sxs-lookup"><span data-stu-id="d6d84-938">10001</span></span></td>
<td><span data-ttu-id="d6d84-939">Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-939">Electricity</span></span></td>
<td><span data-ttu-id="d6d84-940">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-940">Variable cost</span></span></td>
<td><span data-ttu-id="d6d84-941">470.08</span><span class="sxs-lookup"><span data-stu-id="d6d84-941">470.08</span></span></td>
<td><span data-ttu-id="d6d84-942">31 januari 2017</span><span class="sxs-lookup"><span data-stu-id="d6d84-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="d6d84-943">Slutsats</span><span class="sxs-lookup"><span data-stu-id="d6d84-943">Conclusion</span></span>
<span data-ttu-id="d6d84-944">I Affärsredovisning bokförs en kostnad på 10 000,00 för Electricitet på ett dummykostnadscenter-ID.</span><span class="sxs-lookup"><span data-stu-id="d6d84-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="d6d84-945">Därför vet kostnadsrevisorer att kostnaden måste allkoeras.</span><span class="sxs-lookup"><span data-stu-id="d6d84-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="d6d84-946">I kostnadsredovisning flödar kostnaderna över organisationsenheter och nivåer, baserat på de policyer och regler som tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d6d84-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="d6d84-947">Varje kostnad har kopplats till ett allokeringsunderlag som ger den bästa bedömningen för allkoeringen av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="d6d84-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="d6d84-948">Kostnadselement</span><span class="sxs-lookup"><span data-stu-id="d6d84-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="d6d84-949">Kostnadsobjekt</span><span class="sxs-lookup"><span data-stu-id="d6d84-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="d6d84-950">Totalt</span><span class="sxs-lookup"><span data-stu-id="d6d84-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d6d84-951">CC099</span><span class="sxs-lookup"><span data-stu-id="d6d84-951">CC099</span></span></th>
<th><span data-ttu-id="d6d84-952">CC001</span><span class="sxs-lookup"><span data-stu-id="d6d84-952">CC001</span></span></th>
<th><span data-ttu-id="d6d84-953">CC002</span><span class="sxs-lookup"><span data-stu-id="d6d84-953">CC002</span></span></th>
<th><span data-ttu-id="d6d84-954">CC003</span><span class="sxs-lookup"><span data-stu-id="d6d84-954">CC003</span></span></th>
<th><span data-ttu-id="d6d84-955">CC004</span><span class="sxs-lookup"><span data-stu-id="d6d84-955">CC004</span></span></th>
<th><span data-ttu-id="d6d84-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-956">Proj 1</span></span></th>
<th><span data-ttu-id="d6d84-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-957">Proj 2</span></span></th>
<th><span data-ttu-id="d6d84-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6d84-958">Prod 1</span></span></th>
<th><span data-ttu-id="d6d84-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6d84-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="d6d84-960">10001 Elektricitet</span><span class="sxs-lookup"><span data-stu-id="d6d84-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="d6d84-970">Oklassificerade</span><span class="sxs-lookup"><span data-stu-id="d6d84-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-971">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="d6d84-972">Fast kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-973">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-974">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-975">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-976">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-977">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-978">776.36</span><span class="sxs-lookup"><span data-stu-id="d6d84-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-979">223.64</span><span class="sxs-lookup"><span data-stu-id="d6d84-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="d6d84-981">Variabel kostnad</span><span class="sxs-lookup"><span data-stu-id="d6d84-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-982">000</span><span class="sxs-lookup"><span data-stu-id="d6d84-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-983">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-984">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-985">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-986">0,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-987">30,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-988">10,00</span><span class="sxs-lookup"><span data-stu-id="d6d84-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d6d84-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d6d84-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6d84-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6d84-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d6d84-992">Det här avsnittet visar hur ett primärt kostnadselement 10001 Elektricitet flödar genom kostnadsobjekten.</span><span class="sxs-lookup"><span data-stu-id="d6d84-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="d6d84-993">Därför tilldelas denna indirekta kostnad till den lägsta nivån i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d6d84-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="d6d84-994">Med andra ord bär kostnadsobjekten på den lägsta nivån kostnaden.</span><span class="sxs-lookup"><span data-stu-id="d6d84-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="d6d84-995">Om du behöver ett visuellt flöde mellan kostnadsobjekten, kan du använda policyregler för kostnadssummeringen för att visualisera flödet av kostnaden.</span><span class="sxs-lookup"><span data-stu-id="d6d84-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="d6d84-996">Mer information finns i [Samlade kostnader](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="d6d84-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



