---
title: Organisera arbetsstyrkan med hjälp av avdelningar, jobb och befattningar
description: Avdelningar, jobb och befattningar är organisationselement som underhålls i Personal. Det här avsnittet beskriver begreppsmässig information om dessa element.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e1dace0dc6477e259d1004440c4cda8060bf90e3
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130239"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a><span data-ttu-id="1e0d0-104">Organisera personalen efter avdelningar, jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="1e0d0-104">Organize your workforce by using departments, jobs, and positions</span></span>

<span data-ttu-id="1e0d0-105">Avdelningar, jobb och befattningar är organisationselement som underhålls i Personal.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-105">Departments, jobs, and positions are organizational elements that are maintained within Human resources.</span></span> <span data-ttu-id="1e0d0-106">Det här avsnittet beskriver begreppsmässig information om dessa element.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-106">This article describes conceptual information about these elements.</span></span> 

<span data-ttu-id="1e0d0-107">Följande exempel används för att illustrera koncepten som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-107">The following example is used to illustrate the concepts described in this article.</span></span>

|<span data-ttu-id="1e0d0-108">**Avdelning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-108">**Department**</span></span>|<span data-ttu-id="1e0d0-109">**Befattning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-109">**Position**</span></span>|<span data-ttu-id="1e0d0-110">**Jobb**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-110">**Job**</span></span>|
|---|---|---|
|<span data-ttu-id="1e0d0-111">**Försäljning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-111">**Sales**</span></span>|<span data-ttu-id="1e0d0-112">Försäljningschef (öst)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-112">Sales manager (East)</span></span>|<span data-ttu-id="1e0d0-113">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-113">Sales manager</span></span>|
|<span data-ttu-id="1e0d0-114">**Försäljning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-114">**Sales**</span></span>|<span data-ttu-id="1e0d0-115">Försäljningschef (väst)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-115">Sales manager (West)</span></span>|<span data-ttu-id="1e0d0-116">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-116">Sales manager</span></span>|
|<span data-ttu-id="1e0d0-117">**Försäljning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-117">**Sales**</span></span>|<span data-ttu-id="1e0d0-118">Försäljningschef (central)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-118">Sales manager (Central)</span></span>|<span data-ttu-id="1e0d0-119">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-119">Sales manager</span></span>|
|<span data-ttu-id="1e0d0-120">**Redovisning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-120">**Accounting**</span></span>|<span data-ttu-id="1e0d0-121">Redovisningsansvarig</span><span class="sxs-lookup"><span data-stu-id="1e0d0-121">Accounting supervisor</span></span>|<span data-ttu-id="1e0d0-122">Redovisningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-122">Accounting manager</span></span>|
|<span data-ttu-id="1e0d0-123">**Redovisning**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-123">**Accounting**</span></span>|<span data-ttu-id="1e0d0-124">Redovisning-A</span><span class="sxs-lookup"><span data-stu-id="1e0d0-124">Accounting-A</span></span>|<span data-ttu-id="1e0d0-125">Redovisare</span><span class="sxs-lookup"><span data-stu-id="1e0d0-125">Accountant</span></span>|
|<span data-ttu-id="1e0d0-126">**Personal**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-126">**Human resources**</span></span>|<span data-ttu-id="1e0d0-127">Anställande chef (öst)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-127">HR manager (East)</span></span>|<span data-ttu-id="1e0d0-128">Anställande chef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-128">HR manager</span></span>|
|<span data-ttu-id="1e0d0-129">**Personal**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-129">**Human resources**</span></span>|<span data-ttu-id="1e0d0-130">Anställande chef (väst)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-130">HR manager (West)</span></span>|<span data-ttu-id="1e0d0-131">Anställande chef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-131">HR manager</span></span>|
|<span data-ttu-id="1e0d0-132">**Personal**</span><span class="sxs-lookup"><span data-stu-id="1e0d0-132">**Human resources**</span></span>|<span data-ttu-id="1e0d0-133">Anställande chef (central)</span><span class="sxs-lookup"><span data-stu-id="1e0d0-133">HR manager (Central)</span></span>|<span data-ttu-id="1e0d0-134">Anställande chef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-134">HR manager</span></span>|


 <a name="departments"></a><span data-ttu-id="1e0d0-135">Avdelningar</span><span class="sxs-lookup"><span data-stu-id="1e0d0-135">Departments</span></span>
------------

<span data-ttu-id="1e0d0-136">En avdelning är en driftenhet som representerar en kategori eller ett funktionellt område i organisationen, som är ansvarig för ett visst område i organisationen, till exempel försäljning eller redovisning.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-136">A department is an operating unit that represents a category or functional area of an organization that is responsible for a specific area of the organization, such as sales or accounting.</span></span> <span data-ttu-id="1e0d0-137">En avdelning används för att skapa rapporter om funktionella områden och kan ha vinst- och förlustansvar.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-137">A department is used to report on functional areas and may have profit and loss responsibility.</span></span> <span data-ttu-id="1e0d0-138">En avdelning kan omfatta en grupp kostnadsställen.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-138">Also, a department might include a group of cost centers.</span></span> <span data-ttu-id="1e0d0-139">Försäljning, redovisning och personal är exempel på avdelningar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-139">Sales, accounting, and human resources are some examples of departments in an organization.</span></span>

## <a name="jobs-and-positions"></a><span data-ttu-id="1e0d0-140"> Jobb och befattningar</span><span class="sxs-lookup"><span data-stu-id="1e0d0-140">Jobs and positions</span></span>
<span data-ttu-id="1e0d0-141">Ett jobb är en samling uppgifter och ansvarsområden som krävs av en person, som utför ett jobb.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-141">A job is a collection of tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="1e0d0-142">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-142">A position is an individual instance of a job.</span></span> <span data-ttu-id="1e0d0-143">Ansvarsområden, jobbuppgifter, jobbfunktioner, information om färdigheter, intyg och utbildning som är obligatoriska för ett jobb, är också obligatoriska för befattningar som är kopplade till ett jobb.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-143">Areas of responsibility, job tasks, job functions, skills, education information, and certificates that are required for a job are also required for positions that are associated with a job.</span></span>
### <a name="job-tasks"></a><span data-ttu-id="1e0d0-144">Jobbuppgifter</span><span class="sxs-lookup"><span data-stu-id="1e0d0-144">Job tasks</span></span>

<span data-ttu-id="1e0d0-145">Du kan skapa jobbuppgifter som beskriver grundläggande uppgifter, som en anställd i en befattning för det jobbet måste utföra.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-145">You can create job tasks that describe the basic tasks that a worker in a position for that job must complete.</span></span> <span data-ttu-id="1e0d0-146">Samma jobbuppgift kan läggas till flera jobb och befattningar eftersom dessa jobb ärver jobbuppgifterna.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-146">The same job task can be added to multiple jobs, and positions for those jobs will inherit those job tasks.</span></span> <span data-ttu-id="1e0d0-147">Exempel på jobbuppgifter finns i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-147">Examples of job tasks are listed in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1e0d0-148">Jobb</span><span class="sxs-lookup"><span data-stu-id="1e0d0-148">Job</span></span></th>
<th><span data-ttu-id="1e0d0-149">Jobbuppgift</span><span class="sxs-lookup"><span data-stu-id="1e0d0-149">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1e0d0-150">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-150">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="1e0d0-151"><span class="input">Perf-granskning</span> – Granska varje säljares jobbprestanda.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-151"><span class="input">Perf-review</span> – Review each salesperson’s job performance.</span></span></li>
<li><span data-ttu-id="1e0d0-152"><span class="input">Abs-granskning</span> – Godkänna eller avvisa varje säljares frånvaroförfrågningar eller registreringar.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-152"><span class="input">Abs-review</span> – Approve or reject each salesperson’s absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1e0d0-153">Redovisare</span><span class="sxs-lookup"><span data-stu-id="1e0d0-153">Accountant</span></span></td>
<td><span data-ttu-id="1e0d0-154"><span class="input">FIN-rapport</span> – Aktuella veckovisa ekonomiska rapporter till ekonomichef.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-154"><span class="input">FIN-Report</span> – Present weekly financial reports to chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a><span data-ttu-id="1e0d0-155">Jobbfunktioner</span><span class="sxs-lookup"><span data-stu-id="1e0d0-155">Job functions</span></span>

<span data-ttu-id="1e0d0-156">Jobbfunktioner används på jobbuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-156">Job functions are like job tasks.</span></span> <span data-ttu-id="1e0d0-157">En jobbfunktion beskriver en eller flera uppgifter eller ansvarsområden som tilldelats ett jobb.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-157">A job function describes one or more tasks, duties or responsibilities that are assigned to a job.</span></span> <span data-ttu-id="1e0d0-158">Jobbfunktioner kan tilldelas jobb och användas för att ställa in och implementera berättiganderegler för kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-158">Job functions can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="1e0d0-159">Exempel på jobbfunktioner finns i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-159">Examples of job functions are listed in the following table.</span></span>

| <span data-ttu-id="1e0d0-160">Jobb</span><span class="sxs-lookup"><span data-stu-id="1e0d0-160">Job</span></span>           | <span data-ttu-id="1e0d0-161">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="1e0d0-161">Job function</span></span>                                                |
|---------------|-------------------------------------------------------------|
| <span data-ttu-id="1e0d0-162">Försäljningschef</span><span class="sxs-lookup"><span data-stu-id="1e0d0-162">Sales manager</span></span> | <span data-ttu-id="1e0d0-163">Mng-personer – Hantera människor som rapporterar till dig.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-163">Mng-people – Manage people who report to you.</span></span>               |
| <span data-ttu-id="1e0d0-164">Redovisare</span><span class="sxs-lookup"><span data-stu-id="1e0d0-164">Accountant</span></span>    | <span data-ttu-id="1e0d0-165">FIN-granskning – Underhåll av ekonomiska data för en grupp konton.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-165">FIN-Review – Maintain financial data for a set of accounts.</span></span> |

### <a name="job-types"></a><span data-ttu-id="1e0d0-166">Jobbtyper</span><span class="sxs-lookup"><span data-stu-id="1e0d0-166">Job types</span></span>

<span data-ttu-id="1e0d0-167">Använd jobbtyper för att klassificera liknande jobb i kategorier.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-167">Use job types to classify similar jobs into categories.</span></span> <span data-ttu-id="1e0d0-168">Jobbtyåer, liksom jobbfunktioner, kan tilldelas jobb och användas för att ställa in och implementera berättiganderegler för kompensationsplaner.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-168">Job types, just like job functions, can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="1e0d0-169">Exempel på jobbtyper anges i följande lista.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-169">Some examples of job types are included in the following list:</span></span>
-   <span data-ttu-id="1e0d0-170">Heltid</span><span class="sxs-lookup"><span data-stu-id="1e0d0-170">Full-time</span></span>
-   <span data-ttu-id="1e0d0-171">Deltid</span><span class="sxs-lookup"><span data-stu-id="1e0d0-171">Part-time</span></span>
-   <span data-ttu-id="1e0d0-172">Lön</span><span class="sxs-lookup"><span data-stu-id="1e0d0-172">Salary</span></span>
-   <span data-ttu-id="1e0d0-173">Timlön</span><span class="sxs-lookup"><span data-stu-id="1e0d0-173">Hourly pay</span></span>

### <a name="areas-of-responsibility"></a><span data-ttu-id="1e0d0-174">Ansvarsområden</span><span class="sxs-lookup"><span data-stu-id="1e0d0-174">Areas of responsibility</span></span>

<span data-ttu-id="1e0d0-175">Använd ansvarsområden för att indikera arbetets roller, processer och produkter som en befattning för det jobbet skulle vara ansvarig för.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-175">Use areas of responsibility to indicate the work roles, processes, and products that a worker in a position for that job would be responsible for.</span></span> <span data-ttu-id="1e0d0-176">Ett exempel på ett ansvarsområde för ett jobb som kallas "revisor" kan vara "Ekonomisk rapporteringen för produkt A”.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-176">An example of an area of responsibility for a job titled “Accountant” might be “Financial reporting for Product A”.</span></span>

<a name="positions"></a><span data-ttu-id="1e0d0-177">Befattningar</span><span class="sxs-lookup"><span data-stu-id="1e0d0-177">Positions</span></span>
----------

<span data-ttu-id="1e0d0-178">Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-178">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="1e0d0-179">En befattning är ett exempel på ett enskilt jobb.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-179">A position is an individual instance of a job.</span></span> <span data-ttu-id="1e0d0-180">Befattningen "Försäljningschef (öst)" är exempelvis bara en de befattningar som associeras med jobbet "Försäljningschef."</span><span class="sxs-lookup"><span data-stu-id="1e0d0-180">For example, the position, “Sales manager (East),” is just one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="1e0d0-181">Befattningar som finns på en avdelning och tilldelas arbetare.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-181">Positions exist in a department and are assigned to workers.</span></span>
### <a name="position-creation-and-maintenance"></a><span data-ttu-id="1e0d0-182">Befattningskapelse och underhåll</span><span class="sxs-lookup"><span data-stu-id="1e0d0-182">Position creation and maintenance</span></span>

-   <span data-ttu-id="1e0d0-183">Du kan visa en historik över befattningsrelaterade systemändringar på en lättillgänglig listsida.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-183">You can view a history of position-related system changes in an easy-to-access list page.</span></span>
-   <span data-ttu-id="1e0d0-184">Du kan skapa orsakskoder som användarna kan välja när de skapar och ändrar befattningar.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-184">You can create reason codes that your users can select when they create or modify positions.</span></span>
-   <span data-ttu-id="1e0d0-185">Du kan skapa typer av personalåtgärder och tilldela en nummerserie för personalåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-185">You can create personnel action types and assign a number sequence to personnel actions.</span></span>
-   <span data-ttu-id="1e0d0-186">Du kan ställa in arbetsflöden, så att befattningtillägg och ändringar kan kräva godkännande.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-186">You can set up workflow so that position additions and changes can require approval.</span></span>

### <a name="position-duration"></a><span data-ttu-id="1e0d0-187">Befattningstidslängd</span><span class="sxs-lookup"><span data-stu-id="1e0d0-187">Position duration</span></span>

<span data-ttu-id="1e0d0-188">Varje befattning har en tidslängd som befattningen ska gälla.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-188">Every position has a length of time that the position is effective.</span></span> <span data-ttu-id="1e0d0-189">Den tidslängden kallas för varaktighet.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-189">This length of time is referred to as duration.</span></span> <span data-ttu-id="1e0d0-190">Du kan till exempel ha sommarbefattningar med varaktighet 1 maj 2015 till 31 augusti 2015.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-190">For example, summer positions might have duration of May 1, 2015 until August 31, 2015.</span></span>

### <a name="worker-assignments"></a><span data-ttu-id="1e0d0-191">Tilldelningar för arbetare</span><span class="sxs-lookup"><span data-stu-id="1e0d0-191">Worker assignments</span></span>

<span data-ttu-id="1e0d0-192">När du tilldelar en anställd till en befattning, fyller du den befattningen.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-192">When you assign a worker to a position, you fill that position.</span></span> <span data-ttu-id="1e0d0-193">Du kan tilldela flera anställda till befattningar, men bara en anställd kan tilldelas en befattning samtidigt.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-193">You can assign workers to multiple positions, but only one worker can be assigned to a position at the same time.</span></span>

### <a name="reporting-relationships"></a><span data-ttu-id="1e0d0-194">Relationer till överordnad</span><span class="sxs-lookup"><span data-stu-id="1e0d0-194">Reporting relationships</span></span>

<span data-ttu-id="1e0d0-195">Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-195">Positions are important elements of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="1e0d0-196">I formuläret Befattning kan du ange var en befattning som rapporterar till.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-196">In the Position form, you can specify the position that a position reports to.</span></span> <span data-ttu-id="1e0d0-197">När du tilldelar en anställd till en befattning som rapporterar till en annan befattning, skapar du en rapporteringrelation mellan arbetarna som tilldelas de två befattningarna.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-197">When you assign a worker to a position that reports to another position, you create a reporting relationship between the workers who are assigned to the two positions.</span></span> <span data-ttu-id="1e0d0-198">Till exempel rapporterar befattningen ”revisor-A” till befattning ”Redovisningschef".</span><span class="sxs-lookup"><span data-stu-id="1e0d0-198">For example, position “Accountant-A” reports to position “Accounting Supervisor”.</span></span> <span data-ttu-id="1e0d0-199">Kim Akers tilldelas befattningen ”Redovisningschef" och Sanjay Patel tilldelas befattningen "revisor-A”.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-199">Kim Akers is assigned to position “Accounting Supervisor” and Sanjay Patel is assigned to position “Accountant-A”.</span></span> <span data-ttu-id="1e0d0-200">Det innebär att Sanjay Patel rapporterar till Kim Akers.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-200">This means that Sanjay Patel reports to Kim Akers.</span></span> 

<span data-ttu-id="1e0d0-201">Om din organisation använder en matrishierarki eller en annan anpassad hierarki, kan du ställa in befattninghierarkityper, och sedan lägga till rapporteringrelationer till befattningar för varje hierarkityp som du ställer in.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-201">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span> <span data-ttu-id="1e0d0-202">Exempelvis är Lori Penor chef på Adventure Works och tilldelas befattningen "Chef".</span><span class="sxs-lookup"><span data-stu-id="1e0d0-202">For example, Lori Penor is a general manager at Adventure Works and is assigned to the “General Manager” position.</span></span> <span data-ttu-id="1e0d0-203">Lori hanterar utvecklingen av en produkt som används för att rena gränssnittskomponenter.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-203">Lori manages the development of a product that is used to clean widgets.</span></span> <span data-ttu-id="1e0d0-204">Lori kräver att en revisor hjälper henne med finanserna för att utveckla produkten.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-204">Lori requires an accountant to help her with the finances for developing the product.</span></span> <span data-ttu-id="1e0d0-205">Därför hon har rekryterat Sanjay Patel för att vara hennes revisor.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-205">Therefore, she has recruited Sanjay Patel to be her accountant.</span></span> <span data-ttu-id="1e0d0-206">Sanjay rapporterar direkt till Kim Akers, men arbetar också med Lori Penor i dennes arbete som är relaterat till finanserna för att utveckla gränssnittskomponentrengöringsmedlet.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-206">Sanjay reports directly to Kim Akers, but also works with Lori Penor on his work related to the finances for developing the widget cleaner.</span></span> 

<span data-ttu-id="1e0d0-207">För det tidigare exemplet ska du utföra följande uppgifter om du vill ange arbetsrelationen mellan Sanjay Patel och Lori Penor:</span><span class="sxs-lookup"><span data-stu-id="1e0d0-207">For the previous example, you would complete the following tasks to set up the working relationship between Sanjay Patel and Lori Penor:</span></span>
1.  <span data-ttu-id="1e0d0-208">Skapa en anpassad befattningshierarkityp kallad Gränssnittskomponent” för att skapa en hierarki som inkluderar befattningar som ansvarar för arbete med gränssnittskomponentrengöringsmedelprodukten.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-208">Create a custom position hierarchy type called “Widget” to create a hierarchy that includes positions responsible for working on the widget cleaner product.</span></span>
2.  <span data-ttu-id="1e0d0-209">Tilldela rbefattningen Chef att vara den befattning där befattningen Revisor-A rapporterar till i gränssnittskomponenthierarkin.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-209">Assign the General Manager position to be the position that the Accountant-A position reports to in the Widget hierarchy.</span></span>

<span data-ttu-id="1e0d0-210">Använd befattninghierarkin om du vill visa rapporteringstrukturen av befattningar.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-210">Use the position hierarchy to view the reporting structure of positions.</span></span> <span data-ttu-id="1e0d0-211">Om du har flera befattninghierarkier, kan du visa hierarkin för varje hierarki i befattninghierarkin.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-211">If you have multiple position hierarchies, you can view the hierarchy for each hierarchy type in the position hierarchy.</span></span> <span data-ttu-id="1e0d0-212">Du kan även söka efter en befattning efter befattnings-ID eller efter namnet på den arbetare som hör till befattningen.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-212">Also, you can search for a position by position ID or by the name of the worker who is assigned to the position.</span></span> <span data-ttu-id="1e0d0-213">Befattninghierarkin är en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-213">The position hierarchy is an organizational hierarchy.</span></span>

## <a name="date-effective-records"></a><span data-ttu-id="1e0d0-214">Poster för giltighetsdatum</span><span class="sxs-lookup"><span data-stu-id="1e0d0-214">Date effective records</span></span>
<span data-ttu-id="1e0d0-215">För alla poster kan du ange framtida ändringar i posten.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-215">For some records, you can specify future changes to the record.</span></span> <span data-ttu-id="1e0d0-216">Följande information är giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-216">The following information is date effective.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1e0d0-217">Poster</span><span class="sxs-lookup"><span data-stu-id="1e0d0-217">Records</span></span></th>
<th><span data-ttu-id="1e0d0-218">Anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="1e0d0-218">Date effective information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1e0d0-219">Jobb</span><span class="sxs-lookup"><span data-stu-id="1e0d0-219">Jobs</span></span></td>
<td><ul>
<li><span data-ttu-id="1e0d0-220">Detaljerad källinformation</span><span class="sxs-lookup"><span data-stu-id="1e0d0-220">Some detailed job information</span></span></li>
<li><span data-ttu-id="1e0d0-221">Jobbklassificeringsinformation</span><span class="sxs-lookup"><span data-stu-id="1e0d0-221">Job classification information</span></span></li>
<li><span data-ttu-id="1e0d0-222">Kompensationsinformation</span><span class="sxs-lookup"><span data-stu-id="1e0d0-222">Compensation information</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1e0d0-223">Befattningar</span><span class="sxs-lookup"><span data-stu-id="1e0d0-223">Positions</span></span></td>
<td><ul>
<li><span data-ttu-id="1e0d0-224">Detaljerad befattningsinformation</span><span class="sxs-lookup"><span data-stu-id="1e0d0-224">Some detailed position information</span></span></li>
<li><span data-ttu-id="1e0d0-225">Tilldelningar för arbetare</span><span class="sxs-lookup"><span data-stu-id="1e0d0-225">Worker assignments</span></span></li>
<li><span data-ttu-id="1e0d0-226">Befattningstidslängder</span><span class="sxs-lookup"><span data-stu-id="1e0d0-226">Position durations</span></span></li>
<li><span data-ttu-id="1e0d0-227">Befattningshierarkier</span><span class="sxs-lookup"><span data-stu-id="1e0d0-227">Position hierarchies</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1e0d0-228">Du kan ändra informationen som nämns i tabellen ovan för en befattning eller ett jobb och ange ett datum, när ändringarna till befattningen eller jobbet ska genomföras.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-228">You can modify the information mentioned in the previous table for a position or a job and specify a date when the modifications to the position or job should take effect.</span></span> <span data-ttu-id="1e0d0-229">Till exempel kan en befattning endast tilldelas till en anställd, men Sanjay Patel, som är tilldelad befattningen Revisor-A lämnar den om två veckor.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-229">For example, a position can only be assigned to one worker, but Sanjay Patel, who is assigned to the position Accountant-A, will be leaving in two weeks.</span></span> <span data-ttu-id="1e0d0-230">Joe Healy ska ersätta Sanjay Patel, när han lämnar.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-230">Joe Healy will replace Sanjay Patel when he leaves.</span></span> <span data-ttu-id="1e0d0-231">Även om Sanjay fortfarande tilldelas hans befattning, kan du tilldela Joe Healy till samma befattning så att tilldelningen är bara gäller efter Sanjays sista dag.</span><span class="sxs-lookup"><span data-stu-id="1e0d0-231">Even though Sanjay is still assigned to his position, you can assign Joe Healy to the same position so that the assignment is effective only after Sanjay’s last day.</span></span>





