---
title: Projektkontrakt
description: "Den här artikeln beskriver och ger exempel på projektkontrakten som kan skapa för olika typer av projekt och finansieringskällor och hur du hanterar avtal och fakturaprojektkunder i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 0d7d3b64b0d6a662246074b12e3a3fe105dfae47
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2017

---

# <a name="project-contracts"></a><span data-ttu-id="a72f4-103">Projektkontrakt</span><span class="sxs-lookup"><span data-stu-id="a72f4-103">Project contracts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a72f4-104">Den här artikeln beskriver och ger exempel på projektkontrakten som kan skapa för olika typer av projekt och finansieringskällor och hur du hanterar avtal och fakturaprojektkunder i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="a72f4-104">This article describes and provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

<span data-ttu-id="a72f4-105">Typen av projektet som du skapar för ett projektavtal bestämmer vilken metod som används för att faktura projektkunderna.</span><span class="sxs-lookup"><span data-stu-id="a72f4-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="a72f4-106">Du kan ändra ett projektavtal och det relaterade projektet, men du kan inte ändra projekttypen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="a72f4-107">Genom att använda ett projektkontrakt kan du fakturera ett eller flera projekt samtidigt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="a72f4-108">Projektkontraktet hjälper dig också att garantera att en enhetlig faktureringsprocedur används för varje delprojekt i en projektstruktur.</span><span class="sxs-lookup"><span data-stu-id="a72f4-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="a72f4-109">Varje projekt som ska faktureras måste kopplas till ett projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="a72f4-110">Inställningar för ett projektkontrakt gäller för alla projekt och delprojekt som är kopplade till det projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="a72f4-111">Ett projektkontrakt kan ange en eller flera källor till finansieringen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="a72f4-112">Därför kan du dela faktureringen mellan flera finansiärer, ställa in finansieringsgränser så att inte finansieringskällor faktureras mer än ett angivet belopp och konfigurera finansieringsregler för debitering av omkostnader.</span><span class="sxs-lookup"><span data-stu-id="a72f4-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="a72f4-113">Finansiering av projektkontrakt</span><span class="sxs-lookup"><span data-stu-id="a72f4-113">Funding for project contracts</span></span>
<span data-ttu-id="a72f4-114">Vissa projektkontrakt anger att flera parter delar ansvaret för att finansiera projektkostnaderna.</span><span class="sxs-lookup"><span data-stu-id="a72f4-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="a72f4-115">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="a72f4-115">Here are some examples:</span></span>

-   <span data-ttu-id="a72f4-116">En stort kund med flera avdelningar begär att finansiering för ett projekt delas per avdelning.</span><span class="sxs-lookup"><span data-stu-id="a72f4-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="a72f4-117">Ditt företag delar kostnaderna för ett stort projekt med en extern organisation.</span><span class="sxs-lookup"><span data-stu-id="a72f4-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="a72f4-118">Ett vägprojekt samfinansieras av två kommuner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="a72f4-119">Ett broprojekt finansieras med statsbidrag och av ett privat företag.</span><span class="sxs-lookup"><span data-stu-id="a72f4-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="a72f4-120">I Finance and Operations kan du dela faktureringen för en enstaka transaktion eller ett helt projekt mellan flera kunder, anslag eller organisationer.</span><span class="sxs-lookup"><span data-stu-id="a72f4-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="a72f4-121">I projekt med flera finansiärer kallas alla parter som bidrar till finansieringen av ett avancerat finansieringsprojekt för finansieringskällor.</span><span class="sxs-lookup"><span data-stu-id="a72f4-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="a72f4-122">När kund, organisation eller ett anslag definieras som en finansieringskälla kan den tilldelas till en eller flera finansieringsregler.</span><span class="sxs-lookup"><span data-stu-id="a72f4-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="a72f4-123">Finansieringsregler innehåller villkoren som bestämmer hur debiteringar fördelas till de olika finansieringskällorna för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="a72f4-124">Eftersom artiklar i lager, till exempel sådana som anges på inköpsrekvisitioner och inköpsorder inte kan delas, kan kostnadsbeloppet inte delas mellan flera finansieringskällor vid distribution.</span><span class="sxs-lookup"><span data-stu-id="a72f4-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="a72f4-125">Därför blir finansieringskällvärdet 0 (noll) tills lagerutleveransen bokförs.</span><span class="sxs-lookup"><span data-stu-id="a72f4-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="a72f4-126">När lagerutleveransen bokförs fördelas kostnadsbeloppet enligt kontofördelningsreglerna för projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="a72f4-127">Nedan följer några steg du kan ta för att göra det enklare att dela faktureringen mellan flera finansieringskällor:</span><span class="sxs-lookup"><span data-stu-id="a72f4-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="a72f4-128">Ange att alla transaktioner som anges för ett projekt använder samma försäljningsvaluta som projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="a72f4-129">Ställ in finansieringsgränser, så att en finansieringskälla inte faktureras mer än ett angivet belopp mot ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="a72f4-130">Konfigurera finansieringsregler och finansieringsgränser för varje anställd, artikel, kategori, kategorigrupp och transaktionstyp (eller för alla transaktionstyper).</span><span class="sxs-lookup"><span data-stu-id="a72f4-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="a72f4-131">Välj valfria start- och slutdatum för att definiera perioden då varje finansieringsregel är giltig.</span><span class="sxs-lookup"><span data-stu-id="a72f4-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="a72f4-132">Ange procentsatsen att varje finansieringskälla ansvarar för.</span><span class="sxs-lookup"><span data-stu-id="a72f4-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="a72f4-133">Ange vilken finansieringskälla som är ansvarig för avrundningsdifferenser som orsakas av finansieringsallokeringsberäkningar.</span><span class="sxs-lookup"><span data-stu-id="a72f4-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="a72f4-134">Ställ upp regler som avgör hur projektkostnader faktureras till externa kunder och debiteras interna organisationer.</span><span class="sxs-lookup"><span data-stu-id="a72f4-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="a72f4-135">Registrera transaktioner på ett spärrat finansieringskonto tills ytterligare finansieringen erhålls eller tills du väljer att ta kostnaderna internt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="a72f4-136">Avgör vilken momsgrupp som associeras med en transaktion genom att söka igenom projektet efter en momsgrupptilldelning.</span><span class="sxs-lookup"><span data-stu-id="a72f4-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="a72f4-137">Om ingen momsgrupptilldelning har gjorts på projektnivån genomsöks projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="a72f4-138">Exempel: Flera finansieringskällor (enkel)</span><span class="sxs-lookup"><span data-stu-id="a72f4-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="a72f4-139">I följande tabell finns scenarier för hantering av finansieringsallokering mellan flera finansieringskällor.</span><span class="sxs-lookup"><span data-stu-id="a72f4-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="a72f4-140">Dessa scenarier baseras på följande antaganden:</span><span class="sxs-lookup"><span data-stu-id="a72f4-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="a72f4-141">Prioriteringsinställningar tas med i beräkningen av allokering av medel innan andra finansieringsregelvillkor tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a72f4-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="a72f4-142">Inget datumintervall har angetts för att definiera perioden D när finansieringsregeln är giltig.</span><span class="sxs-lookup"><span data-stu-id="a72f4-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a72f4-143"><strong>Scenario</strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="a72f4-144"><strong>Finansieringskälla </strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="a72f4-145"><strong>Allokeringsprocent </strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="a72f4-146"><strong>Allokeringsprioritet </strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a72f4-147">Du vill fördela kostnader till en finansieringskälla tills dess medel har utnyttjats, fördela kostnader till en andra finansieringskälla tills dess medel har utnyttjats och slutligen fördela återstående kostnader till tredje finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-148">Finansieringskälla 1</span><span class="sxs-lookup"><span data-stu-id="a72f4-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="a72f4-149">Finansieringskälla 2</span><span class="sxs-lookup"><span data-stu-id="a72f4-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="a72f4-150">Finansieringskälla 3</span><span class="sxs-lookup"><span data-stu-id="a72f4-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-151">100 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-151">100%</span></span></li>
<li><span data-ttu-id="a72f4-152">100 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-152">100%</span></span></li>
<li><span data-ttu-id="a72f4-153">100 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-154">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-154">1</span></span></li>
<li><span data-ttu-id="a72f4-155">2</span><span class="sxs-lookup"><span data-stu-id="a72f4-155">2</span></span></li>
<li><span data-ttu-id="a72f4-156">3</span><span class="sxs-lookup"><span data-stu-id="a72f4-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a72f4-157">Du vill fördela 75 procent av kostnaderna till en finansieringskälla och 25 procent till en andra finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="a72f4-158">När någon av finansieringskällorna har utnyttjats betalar du återstående kostnader från en tredje finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-159">Finansieringskälla 1</span><span class="sxs-lookup"><span data-stu-id="a72f4-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="a72f4-160">Finansieringskälla 2</span><span class="sxs-lookup"><span data-stu-id="a72f4-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="a72f4-161">Finansieringskälla 3</span><span class="sxs-lookup"><span data-stu-id="a72f4-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-162">75 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-162">75%</span></span></li>
<li><span data-ttu-id="a72f4-163">25 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-163">25%</span></span></li>
<li><span data-ttu-id="a72f4-164">100 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-165">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-165">1</span></span></li>
<li><span data-ttu-id="a72f4-166">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-166">1</span></span></li>
<li><span data-ttu-id="a72f4-167">2</span><span class="sxs-lookup"><span data-stu-id="a72f4-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a72f4-168">Du vill fördela 75 procent av kostnaderna till en finansieringskälla och 25 procent till en andra finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="a72f4-169">När någon av finansieringskällorna har utnyttjats delar du återstående kostnader mellan en tredje och en fjärde finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-170">Finansieringskälla 1</span><span class="sxs-lookup"><span data-stu-id="a72f4-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="a72f4-171">Finansieringskälla 2</span><span class="sxs-lookup"><span data-stu-id="a72f4-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="a72f4-172">Finansieringskälla 3</span><span class="sxs-lookup"><span data-stu-id="a72f4-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="a72f4-173">Finansieringskälla 4</span><span class="sxs-lookup"><span data-stu-id="a72f4-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-174">75 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-174">75%</span></span></li>
<li><span data-ttu-id="a72f4-175">25 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-175">25%</span></span></li>
<li><span data-ttu-id="a72f4-176">50 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-176">50%</span></span></li>
<li><span data-ttu-id="a72f4-177">50 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-178">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-178">1</span></span></li>
<li><span data-ttu-id="a72f4-179">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-179">1</span></span></li>
<li><span data-ttu-id="a72f4-180">2</span><span class="sxs-lookup"><span data-stu-id="a72f4-180">2</span></span></li>
<li><span data-ttu-id="a72f4-181">2</span><span class="sxs-lookup"><span data-stu-id="a72f4-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a72f4-182">Du vill fördela de första 25 procenten av kostnaderna till en finansieringskälla och resten till en andra finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-183">Finansieringskälla 1</span><span class="sxs-lookup"><span data-stu-id="a72f4-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="a72f4-184">Finansieringskälla 2</span><span class="sxs-lookup"><span data-stu-id="a72f4-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-185">25 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-185">25%</span></span></li>
<li><span data-ttu-id="a72f4-186">100 %</span><span class="sxs-lookup"><span data-stu-id="a72f4-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="a72f4-187">1</span><span class="sxs-lookup"><span data-stu-id="a72f4-187">1</span></span></li>
<li><span data-ttu-id="a72f4-188">2</span><span class="sxs-lookup"><span data-stu-id="a72f4-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="a72f4-189">Exempel: Flera finansieringskällor (komplex)</span><span class="sxs-lookup"><span data-stu-id="a72f4-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="a72f4-190">Du har tre finansieringskällor som du vill använda i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="a72f4-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="a72f4-191">Använd finansieringskälla 2 och 3 lika tills finansieringskälla 2 har utnyttjats.</span><span class="sxs-lookup"><span data-stu-id="a72f4-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="a72f4-192">Fortsätt att använda finansieringskälla 3 tills har utnyttjats.</span><span class="sxs-lookup"><span data-stu-id="a72f4-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="a72f4-193">Använd finansieringskälla 1 när finansieringskälla 3 har utnyttjats.</span><span class="sxs-lookup"><span data-stu-id="a72f4-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="a72f4-194">Om du vill uppnå målet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="a72f4-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="a72f4-195">Ställ in finansieringsgränser för finansieringskälla 2 och 3 med deras respektive belopp.</span><span class="sxs-lookup"><span data-stu-id="a72f4-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="a72f4-196">Skapa följande finansieringsregler:</span><span class="sxs-lookup"><span data-stu-id="a72f4-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="a72f4-197">Regel 1 (prioritet 1): Fördela 50 procent av transaktionerna till finansieringskälla 2 och 50 procent till finansieringskälla 3.</span><span class="sxs-lookup"><span data-stu-id="a72f4-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="a72f4-198">Regel 2 (prioritet 2): Fördela 100 procent av transaktionerna till finansieringskälla 3.</span><span class="sxs-lookup"><span data-stu-id="a72f4-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="a72f4-199">Regel 3 (prioritet 3): Fördela 100 procent av transaktionerna till finansieringskälla 1.</span><span class="sxs-lookup"><span data-stu-id="a72f4-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="a72f4-200">Det här fungerar eftersom transaktioner kontrolleras mot regler och gränser som fastställer om några av dem gäller för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="a72f4-201">Om inga specifika regler eller gränser gäller för transaktionen gäller regeln Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="a72f4-202">Regeln Alla transaktioner matchar alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="a72f4-203">Om en regel som matchar en transaktion används procentandelen som har allokerats i regeln först, men endast efter att matchningarna kontrolleras mot gränserna som har ställts in.</span><span class="sxs-lookup"><span data-stu-id="a72f4-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="a72f4-204">Om en gräns har uppfyllts och en finansieringskällas medel har utnyttjats, ignoreras finansieringsregeln som är kopplad till finansieringsgränsen och programmet söker efter nästa regel som gäller.</span><span class="sxs-lookup"><span data-stu-id="a72f4-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="a72f4-205">I vissa fall kan bara en del av en transaktion fördelas under en regel.</span><span class="sxs-lookup"><span data-stu-id="a72f4-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="a72f4-206">Detta kan inträffa eftersom en gräns uppnås när transaktionen fördelas.</span><span class="sxs-lookup"><span data-stu-id="a72f4-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="a72f4-207">I det här fallet allokeras bara ett visst belopp enligt den regeln, till exempel 50 procent till varje finansieringskälla.</span><span class="sxs-lookup"><span data-stu-id="a72f4-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="a72f4-208">Detta är fallet i regel 1 som beskrevs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="a72f4-209">Resten fördelas enligt nästa regel i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="a72f4-210">Följande tabell undersöker det här scenariot noggrannare.</span><span class="sxs-lookup"><span data-stu-id="a72f4-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a72f4-211"><strong>Fokus </strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="a72f4-212"><strong>Detaljer</strong></span><span class="sxs-lookup"><span data-stu-id="a72f4-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a72f4-213">Finansieringsregler</span><span class="sxs-lookup"><span data-stu-id="a72f4-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-214">Regel 1 (prioritet 1): Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="a72f4-215">Fördela finansieringskälla 2 till 50 % och finansieringskälla 3 till 50 %.</span><span class="sxs-lookup"><span data-stu-id="a72f4-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="a72f4-216">Regel 2 (prioritet 2): Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="a72f4-217">Fördela finansieringskälla 3 till 100 %.</span><span class="sxs-lookup"><span data-stu-id="a72f4-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="a72f4-218">Regel 3 (prioritet 2): Alla transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="a72f4-219">Fördela finansieringskälla 1 till 100 %.</span><span class="sxs-lookup"><span data-stu-id="a72f4-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a72f4-220">Finansieringsgränser</span><span class="sxs-lookup"><span data-stu-id="a72f4-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-221">Gräns för finansieringskälla 1 = 10 000,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="a72f4-222">Gräns för finansieringskälla 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="a72f4-223">Gräns för finansieringskälla 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a72f4-224">Transaktion 1</span><span class="sxs-lookup"><span data-stu-id="a72f4-224">Transaction 1</span></span></td>
<td><span data-ttu-id="a72f4-225"><strong>Transaktionsbelopp:</strong> 100,00,<strong>Finansiering:</strong> Transaktionen betalas endast enligt regel 1, eftersom transaktionen är fullständigt betalad efter att regel 1 tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a72f4-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="a72f4-226">Transaktionen finansieras lika mellan finansieringskälla 2 och 3.</span><span class="sxs-lookup"><span data-stu-id="a72f4-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="a72f4-227">Finansieringskälla 2: 50,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="a72f4-228">Finansieringskälla 3: 50,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a72f4-229">Transaktion 2</span><span class="sxs-lookup"><span data-stu-id="a72f4-229">Transaction 2</span></span></td>
<td><span data-ttu-id="a72f4-230"><strong>Transaktionsbelopp:</strong> 5 000,00<strong>Finansiering:</strong> Transaktionen finansieras enligt alla tre reglerna.<strong>Regel 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="a72f4-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.<strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="a72f4-231">Finansieringskälla 2: 450,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-231">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="a72f4-232">Finansieringskälla 3: 450,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-232">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="a72f4-233">
<strong>Regel 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="a72f4-233">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="a72f4-234">Finansieringskälla 3: 250,00 (= 750,00 - 50,00 - 450,00)</span><span class="sxs-lookup"><span data-stu-id="a72f4-234">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="a72f4-235">
<strong>Regel 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="a72f4-235">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="a72f4-236">Finansieringskälla 1: 3 850,00 (= 5 000,00 - 450,00 - 450,00 - 250,00)</span><span class="sxs-lookup"><span data-stu-id="a72f4-236">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a72f4-237">Total finansiering som distribueras för varje finansieringskälla</span><span class="sxs-lookup"><span data-stu-id="a72f4-237">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="a72f4-238">Finansieringskälla 1: 3 850,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-238">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="a72f4-239">Finansieringskälla 2: 500,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-239">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="a72f4-240">Finansieringskälla 3: 750,00</span><span class="sxs-lookup"><span data-stu-id="a72f4-240">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="a72f4-241">Faktureringsregler</span><span class="sxs-lookup"><span data-stu-id="a72f4-241">Billing rules</span></span>
<span data-ttu-id="a72f4-242">När du förhandling om ett projektkontrakt med en kund, kan du definiera hur och när du kan fakturera kunden för arbete på ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-242">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="a72f4-243">När du har ställt in projektkontraktet och projektet kan du ställa in faktureringsregler för projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-243">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="a72f4-244">Faktureringsreglerna baseras på projektvillkoren som anges i projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-244">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="a72f4-245">Vilka faktureringsregler som du kan skapa beror på villkoren i projektkontraktet och typen av projekt, till exempel Tid och material eller Fastpris, som du associerar med faktureringsregeln.</span><span class="sxs-lookup"><span data-stu-id="a72f4-245">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="a72f4-246">Du kan skapa mer än en faktureringsregel för ett projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-246">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="a72f4-247">Du kan också tilldela en faktureringsregel till projekt, som associeras med samma projektkontrakt, och du har liknande faktureringstermer.</span><span class="sxs-lookup"><span data-stu-id="a72f4-247">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="a72f4-248">Du kan ställa in följande faktureringsregler:</span><span class="sxs-lookup"><span data-stu-id="a72f4-248">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="a72f4-249">**Leveransenhet** – Fakturera en kund när du slutför en leveransenhet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-249">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="a72f4-250">Du definierar enheter för leverans i kontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-250">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="a72f4-251">**Förlopp** – Fakturera en kund när du slutför en viss procentadel av projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-251">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="a72f4-252">Du kan ställa in en faktureringsregel automatiskt att beräkna den uppsagda procent av arbete, eller så kan du manuellt vill beräkna hur många procent av arbete som är avslutat och beloppet för att fakturera kunden.</span><span class="sxs-lookup"><span data-stu-id="a72f4-252">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="a72f4-253">**Milstolpe** – Fakturera en kund för hela beloppet för en projektmilstolpe när den uppnås.</span><span class="sxs-lookup"><span data-stu-id="a72f4-253">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="a72f4-254">**Avgift** – Fakturera en kund för dina tjänster plus en hanteringsavgift, vanligtvis en procentandel av kostnaden för tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="a72f4-254">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="a72f4-255">**Tid och material** – Fakturera en kund värdet av tid och material som användes i ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-255">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="a72f4-256">För alla typer av faktureringsregler kan du ange en kvarhållandeprocentsats som dras av från kundfakturor tills ett projekt når en avtalad fas.</span><span class="sxs-lookup"><span data-stu-id="a72f4-256">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="a72f4-257">Betalningskvarhållandeprocentsatsen anges i projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-257">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="a72f4-258">Beloppet beräknas på och dras av från det totala värdet av raderna i en kundfaktura.</span><span class="sxs-lookup"><span data-stu-id="a72f4-258">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="a72f4-259">För faktureringsreglerna **Tid och material** och **Förlopp** kan du tilldela debiterbara kategorier.</span><span class="sxs-lookup"><span data-stu-id="a72f4-259">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="a72f4-260">Debiterbara kategorier visar vilka transaktioner som ska inkluderas i kundfakturor.</span><span class="sxs-lookup"><span data-stu-id="a72f4-260">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="a72f4-261">När du är redo att fakturera kunden är beloppet på fakturan för projektet beräknat baserat på faktureringsreglerna och ett projektfakturaförslag genereras.</span><span class="sxs-lookup"><span data-stu-id="a72f4-261">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="a72f4-262">Följande avsnitt innehåller exempel som visar hur du ställer in och hanterar faktureringsregler för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a72f4-262">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="a72f4-263">Exempel: Skapa en faktureringsregel som baseras på antalet levererade enheter</span><span class="sxs-lookup"><span data-stu-id="a72f4-263">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="a72f4-264">Din organisation avtalar att tillhandahålla totalt fem utbildningssessioner till en kunds medarbetare till en kostnad på 10 000 per utbildningssession.</span><span class="sxs-lookup"><span data-stu-id="a72f4-264">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="a72f4-265">Du fakturerar kunden efter varje utbildningssession.</span><span class="sxs-lookup"><span data-stu-id="a72f4-265">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="a72f4-266">När du ställer in faktureringsreglerna för kontraktet använder du följande värden:</span><span class="sxs-lookup"><span data-stu-id="a72f4-266">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="a72f4-267">Enheten för leverans är en träningsession.</span><span class="sxs-lookup"><span data-stu-id="a72f4-267">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="a72f4-268">Enhetspriset är 10,000 per träningsession.</span><span class="sxs-lookup"><span data-stu-id="a72f4-268">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="a72f4-269">Totalt antal enheter är fem träningssessioner.</span><span class="sxs-lookup"><span data-stu-id="a72f4-269">The total number of units is five training sessions.</span></span>

<span data-ttu-id="a72f4-270">När du har slutfört en utbildningssession kan du skapa en faktura på 10 000 för den första enheten som levererades och skicka fakturan till kunden.</span><span class="sxs-lookup"><span data-stu-id="a72f4-270">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="a72f4-271">Exempel: Skapa en faktureringsregel som baseras på en viss procent av projektslutförande (manuell beräkning)</span><span class="sxs-lookup"><span data-stu-id="a72f4-271">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="a72f4-272">Din organisation, ett datakonsultföretag, ingår ett avtal med en kund om att utveckla en del av en produkt som kunden utvecklar.</span><span class="sxs-lookup"><span data-stu-id="a72f4-272">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="a72f4-273">Organisationen förbinder sig att leverera programvarukoden över en period på sex månader.</span><span class="sxs-lookup"><span data-stu-id="a72f4-273">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="a72f4-274">Kunden förbinder sig att betala din organisation totalt 100 000 för arbetet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-274">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="a72f4-275">Du skapar en faktureringsregel för att fakturera kunden baserat på en procentsats färdigt arbete i projektet enligt avtalet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-275">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="a72f4-276">I slutet av den första månaden träffar du kunden för att bestämma hur många procent av arbetet som har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a72f4-276">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="a72f4-277">Vid granskning av projektet beslutar du och kunden att projektet är slutfört till 15 procent.</span><span class="sxs-lookup"><span data-stu-id="a72f4-277">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="a72f4-278">Du skapar en faktura på 15 000 (15 procent av 100 000) och skickar den till kunden.</span><span class="sxs-lookup"><span data-stu-id="a72f4-278">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="a72f4-279">Exempel: Skapa en faktureringsregel som baseras på en viss procentandel av projektslutförande (automatisk beräkning)</span><span class="sxs-lookup"><span data-stu-id="a72f4-279">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="a72f4-280">Din organisation, en programutvecklingsfirma, går med på att sammanställa ett lönelisteredovisningspaket till en kund för 30 000.</span><span class="sxs-lookup"><span data-stu-id="a72f4-280">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="a72f4-281">Kunden förbinder sig att betala din organisation baserat på procentandelen slutfört arbete.</span><span class="sxs-lookup"><span data-stu-id="a72f4-281">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="a72f4-282">Du beräknar att projektkostnaderna är 20 000.</span><span class="sxs-lookup"><span data-stu-id="a72f4-282">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="a72f4-283">Projektkontraktet anger arbetskategorierna som används i faktureringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-283">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="a72f4-284">Du ställer in faktureringsregler som automatiskt beräknar fakturabelopp för procent av arbete, som utförs för varje kategori.</span><span class="sxs-lookup"><span data-stu-id="a72f4-284">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="a72f4-285">Du ställer in en budget för varje kategori:</span><span class="sxs-lookup"><span data-stu-id="a72f4-285">You set up a budget for each category:</span></span>

-   <span data-ttu-id="a72f4-286">**Utveckling** – kostnad på 15 000 och intäkter på 20 000</span><span class="sxs-lookup"><span data-stu-id="a72f4-286">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="a72f4-287">**Installation** – kostnad på 5 000 och intäkter på 10 000</span><span class="sxs-lookup"><span data-stu-id="a72f4-287">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="a72f4-288">När du skapar en kundfaktura för första gången, är fakturabeloppet automatiskt beräknat baserat på följande information:</span><span class="sxs-lookup"><span data-stu-id="a72f4-288">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="a72f4-289">Efter en månad skickar arbetaren en tidrapport för projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-289">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="a72f4-290">Kostnaden för arbetarens timmar är 5 000 för utveckling och 1 000 för installation.</span><span class="sxs-lookup"><span data-stu-id="a72f4-290">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="a72f4-291">Utvecklingsarbetet är 33 procent klart (faktisk kostnad 5 000/budgeterad kostnad 15 000) och installationsarbetet är 20 procent klart (faktisk kostnad 1 000/budgeterad kostnad 5 000).</span><span class="sxs-lookup"><span data-stu-id="a72f4-291">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="a72f4-292">Fakturabeloppet på 8 667 beräknas automatiskt (33 procent av 20 000 + 20 procent av 10 000).</span><span class="sxs-lookup"><span data-stu-id="a72f4-292">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="a72f4-293">Du skapar en faktura på 8 667 och skickar den till kunden.</span><span class="sxs-lookup"><span data-stu-id="a72f4-293">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="a72f4-294">Exempel: Skapa en faktureringsregel som baseras på överenskomna milstolpar</span><span class="sxs-lookup"><span data-stu-id="a72f4-294">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="a72f4-295">Din organisation, en management-konsultfirma, genomför marknadsundersökningar för en konsumentprodukt som kunden planerar att sälja.</span><span class="sxs-lookup"><span data-stu-id="a72f4-295">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="a72f4-296">Kunden förbinder sig att använda dina tjänster för en period på tre månader som startar i mars, och förbinder sig att betala din organisation 50 000.</span><span class="sxs-lookup"><span data-stu-id="a72f4-296">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="a72f4-297">Projektet har tre milstolpar:</span><span class="sxs-lookup"><span data-stu-id="a72f4-297">The project has three milestones:</span></span>

-   <span data-ttu-id="a72f4-298">Milstolpe 1: Samla in konsumentdata – 31 mars</span><span class="sxs-lookup"><span data-stu-id="a72f4-298">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="a72f4-299">Milstolpe 2: Analysera konsumentdata – 30 april</span><span class="sxs-lookup"><span data-stu-id="a72f4-299">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="a72f4-300">Milstolpe 3: Framlägga ett produktgenomförbarhetsförslag – 31 mars</span><span class="sxs-lookup"><span data-stu-id="a72f4-300">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="a72f4-301">Kunden förbinder sig att betala din organisation 10 000 för den första milstolpen och 20 000 för den andra och 20 000 för den tredje milstolpen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-301">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="a72f4-302">När du ställer in projektkontrakt går du med på att fakturera kunden baserat på den slutförda milstolpen.</span><span class="sxs-lookup"><span data-stu-id="a72f4-302">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="a72f4-303">Inställningen av faktureringsregler inkluderar följande steg:</span><span class="sxs-lookup"><span data-stu-id="a72f4-303">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="a72f4-304">Definiera projektmilstolparna.</span><span class="sxs-lookup"><span data-stu-id="a72f4-304">Define the project milestones.</span></span>
-   <span data-ttu-id="a72f4-305">Definiera beloppet att fakturera kunden vid slutförande av varje milstolpe.</span><span class="sxs-lookup"><span data-stu-id="a72f4-305">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="a72f4-306">När den första milstolpen är klar de 31 mars, markerar du milstolpen som slutförd och skapar sedan en faktura med beloppet 10 000 som skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="a72f4-306">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="a72f4-307">Du kan inte skapa en faktura för en milstolpe förrän du har markerat milstolpen som slutförd.</span><span class="sxs-lookup"><span data-stu-id="a72f4-307">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="a72f4-308">Exempel: Skapa en faktureringsregel baserad på tjänster plus en förvaltningsavgift</span><span class="sxs-lookup"><span data-stu-id="a72f4-308">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="a72f4-309">Din organisation, en management-konsultfirma, går med på att utföra marknadsundersökningar för att utvärdera genomförbarheten av en produkt som kunden, ett butiksföretag, utvecklar.</span><span class="sxs-lookup"><span data-stu-id="a72f4-309">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="a72f4-310">Avtalets villkor anger att du tillhandahåller tjänster från de tre bästa managementkonsulterna som genomför undersökningen baserat på tid och material.</span><span class="sxs-lookup"><span data-stu-id="a72f4-310">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="a72f4-311">Kunden går med på att betala 100 per timme plus en ytterligare administrationsavgift på 10 procent för konsulttimmar som debiteras projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-311">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="a72f4-312">När du ställer in projektkontraktet skapar du en faktureringsregel som lägger till en 10 procents administrationsavgift för konsulttimmar som debiteras projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-312">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="a72f4-313">När du skapar en faktura för kunden, kommer kunden att faktureras en 10 procent administrationsavgift plus kostnaden för konsulttimmarna.</span><span class="sxs-lookup"><span data-stu-id="a72f4-313">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="a72f4-314">Om till exempel de tre konsulterna arbetade totalt 200 timmar på projektet skapas en faktura med beloppet 22 000 med följande beräkning:</span><span class="sxs-lookup"><span data-stu-id="a72f4-314">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="a72f4-315">200 timmar, 100 per timme = 20 000</span><span class="sxs-lookup"><span data-stu-id="a72f4-315">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="a72f4-316">10 procent hanteringsavgift = 2 000</span><span class="sxs-lookup"><span data-stu-id="a72f4-316">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="a72f4-317">Totalt fakturabelopp = 22 000</span><span class="sxs-lookup"><span data-stu-id="a72f4-317">Total invoice amount = 22,000</span></span>

<span data-ttu-id="a72f4-318">Om avgifter är momspliktiga för en kund och du väljer en momsgrupp i projektkontraktet, anges momsgruppen automatiskt i en faktureringsregel för avgifter.</span><span class="sxs-lookup"><span data-stu-id="a72f4-318">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="a72f4-319">Exempel: Skapa en faktureringsregel för tids- och materialvärde</span><span class="sxs-lookup"><span data-stu-id="a72f4-319">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="a72f4-320">Din organisation, ett datakonsultföretag, avtalar att tillhandahålla fem tekniska konsulter att arbeta på ett programvaruutvecklingsprojekt för en kund under nästa halvår.</span><span class="sxs-lookup"><span data-stu-id="a72f4-320">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="a72f4-321">Kunden förbinder sig att betala 150 för varje konsulttimme plus kostnaden för kontorsmaterial.</span><span class="sxs-lookup"><span data-stu-id="a72f4-321">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="a72f4-322">Din organisation skickar en faktura till kunden i slutet av varje månad.</span><span class="sxs-lookup"><span data-stu-id="a72f4-322">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="a72f4-323">När du ställer in projektkontraktet går du med på att fakturera kunden varje månad för tid och material i projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-323">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="a72f4-324">Du skapar en faktureringsregel som omfattar följande information:</span><span class="sxs-lookup"><span data-stu-id="a72f4-324">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="a72f4-325">Kontraktsperioden är sex månader.</span><span class="sxs-lookup"><span data-stu-id="a72f4-325">The contract period is six months.</span></span>
-   <span data-ttu-id="a72f4-326">Konsulttiden beräknas till ett värde av 150 per timme.</span><span class="sxs-lookup"><span data-stu-id="a72f4-326">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="a72f4-327">Kontorsvaror faktureras till självkostnad och totalkostnaden för projektet får inte överstiga 10 000.</span><span class="sxs-lookup"><span data-stu-id="a72f4-327">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="a72f4-328">Du skapar en kundfaktura i slutet av varje månad under projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-328">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="a72f4-329">Under den första månaden registrerades totalt 800 timmar av konsulterna i projektet.</span><span class="sxs-lookup"><span data-stu-id="a72f4-329">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="a72f4-330">Kostnaden för kontorsmaterial som debiteras projektet är 2 000.</span><span class="sxs-lookup"><span data-stu-id="a72f4-330">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="a72f4-331">I slutet av månaden skapar du en faktura på 122 000 (800 timmar för 150 per timme plus 2 000 för kontorsmaterial).</span><span class="sxs-lookup"><span data-stu-id="a72f4-331">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>




