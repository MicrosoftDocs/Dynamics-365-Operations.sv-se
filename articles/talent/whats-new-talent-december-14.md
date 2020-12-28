---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (14 december 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9887d22a513e820c35c51b6c702e2d9d34ab1214
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529766"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-december-14-2018"></a><span data-ttu-id="a90b9-103">Nyheter och ändringar i Dynamics 365 Talent - Core HR (14 december 2018)</span><span class="sxs-lookup"><span data-stu-id="a90b9-103">What's new or changed in Dynamics 365 Talent - Core HR (December 14, 2018)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a90b9-104">**Skapa 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="a90b9-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="a90b9-105">Det här ämnet beskriver nya eller ändrade funktioner i Core HR.</span><span class="sxs-lookup"><span data-stu-id="a90b9-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="a90b9-106">Ändringar</span><span class="sxs-lookup"><span data-stu-id="a90b9-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="a90b9-107">US - ACA (Affordable Care Act) stöder för skatt år 2018 1095-B- och 1095-C-formulär</span><span class="sxs-lookup"><span data-stu-id="a90b9-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="a90b9-108">Varje år måste Applicable Large Employers (ALE) tillhandahålla varje heltidsanställd med 1095-C.</span><span class="sxs-lookup"><span data-stu-id="a90b9-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="a90b9-109">Dessutom, om arbetsgivaren ger självförsäkringstäckning måste även tillhandahålla 1095-C (om de är en ALE) och en 1095-B (om det är en liten arbetsgivare) till alla medarbetare på heltid eller deltid, som täcks av en av deras erbjudna hälsoplaner.</span><span class="sxs-lookup"><span data-stu-id="a90b9-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="a90b9-110">Den här funktionen ger formulär som kan skrivas för både 1095-C och 1095-B.</span><span class="sxs-lookup"><span data-stu-id="a90b9-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="a90b9-111">Under import ignoreras fältet SubmittedByPersonId på HcmPerfJournalEntity</span><span class="sxs-lookup"><span data-stu-id="a90b9-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="a90b9-112">När du importerar/exporterar prestationsjournalposter ignoreras fältet **Skickas av**.</span><span class="sxs-lookup"><span data-stu-id="a90b9-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="a90b9-113">Med denna skillnad kommer värdet **importerad/exporterad** återspegla värdet i registret under exporten, när du importerar kommer systemet att uppdateras med värdet i importfilen.</span><span class="sxs-lookup"><span data-stu-id="a90b9-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="a90b9-114">Fliken Analys på arbetsytan ”tjänstledighet och frånvaro” visar felet ”OpenConnectionError” för icke-systemadministratörsroller</span><span class="sxs-lookup"><span data-stu-id="a90b9-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="a90b9-115">Med denna uppdatering kommer inga fel att utfärdas när du öppnar fliken **analys** i arbetsytan **Tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="a90b9-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="a90b9-116">Självservice för anställda, den nedrullningen befattningshierarkin från panel misslyckas med att hämta överordnad nod</span><span class="sxs-lookup"><span data-stu-id="a90b9-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="a90b9-117">En ändring har gjorts för att korrigera felet ”hämtning av den överordnade noden misslyckades” när befattningshierarkin har anpassats så att den visas på en befintlig arbetsyta och en befattning väljs i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="a90b9-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="a90b9-118">Måste vara systemadministratör för att se fliken Lön på sidan Befattning</span><span class="sxs-lookup"><span data-stu-id="a90b9-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="a90b9-119">En ändring har gjorts för att inkludera rätt element i den befintliga behörigheten: ”Underhåll lönearbetare och befattningsdetaljer”.</span><span class="sxs-lookup"><span data-stu-id="a90b9-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="a90b9-120">Med den här ändringen har löneadministratören som standard åtkomst till fälten Lön på sidan Befattning.</span><span class="sxs-lookup"><span data-stu-id="a90b9-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="a90b9-121">Fel när du skickar resultatöversyn för granskning till chef och %Reviews.PerfPeriod% platshållare används i sändningsinstruktioner</span><span class="sxs-lookup"><span data-stu-id="a90b9-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="a90b9-122">En ändring har gjorts som rättar felet ”null-referens” när du använder %Reviews.PerfPeriod% platshållare i sändningsinstruktionerna.</span><span class="sxs-lookup"><span data-stu-id="a90b9-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="a90b9-123">Personalens Power BI-rapport visar fel när datum för tjänsteålder för arbetaren är en skottdag</span><span class="sxs-lookup"><span data-stu-id="a90b9-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="a90b9-124">Med den här ändringen stöds nu skottdagar i Power BI.</span><span class="sxs-lookup"><span data-stu-id="a90b9-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="a90b9-125">Integration mellan Core HR och Attract</span><span class="sxs-lookup"><span data-stu-id="a90b9-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="a90b9-126">En ändring har gjorts för att uppdatera integrationen mellan Core HR och Attract som är relaterad till kandidater att anställa.</span><span class="sxs-lookup"><span data-stu-id="a90b9-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="a90b9-127">För att kandidater att anställa ska visas i arbetsytan **personalhantering** kommer följande Common Data Service-enheter användas:</span><span class="sxs-lookup"><span data-stu-id="a90b9-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following Common Data Service entities are used:</span></span>

<span data-ttu-id="a90b9-128">Jobbansökan</span><span class="sxs-lookup"><span data-stu-id="a90b9-128">Job Application</span></span>
- <span data-ttu-id="a90b9-129">Statusorsak måste anges för Erbjudandet godkänt</span><span class="sxs-lookup"><span data-stu-id="a90b9-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="a90b9-130">Ger kandidat och ledigt jobb</span><span class="sxs-lookup"><span data-stu-id="a90b9-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="a90b9-131">Kandidat</span><span class="sxs-lookup"><span data-stu-id="a90b9-131">Candidate</span></span>
-   <span data-ttu-id="a90b9-132">Ger information om kandidat</span><span class="sxs-lookup"><span data-stu-id="a90b9-132">Provides Candidate information</span></span>

<span data-ttu-id="a90b9-133">Ledigt jobb</span><span class="sxs-lookup"><span data-stu-id="a90b9-133">Job Opening</span></span>
-   <span data-ttu-id="a90b9-134">Ger ID för ledigt jobb och deltagare i ledigt jobb</span><span class="sxs-lookup"><span data-stu-id="a90b9-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="a90b9-135">Deltagare i ledigt jobb</span><span class="sxs-lookup"><span data-stu-id="a90b9-135">Job Opening Participants</span></span>
-   <span data-ttu-id="a90b9-136">Ger anställande chef</span><span class="sxs-lookup"><span data-stu-id="a90b9-136">Provides Hiring Manager</span></span>

<span data-ttu-id="a90b9-137">När en kandidat läggs till personalhantering kan kandidaten nu också avfärdas med ett nytt alternativ som är tillgängligt på kandidatkortet.</span><span class="sxs-lookup"><span data-stu-id="a90b9-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a90b9-138">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="a90b9-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="a90b9-139">Tjänstledighet och frånvaro: framtida tjänstledighet och prognostisering lämnar saldon</span><span class="sxs-lookup"><span data-stu-id="a90b9-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="a90b9-140">Med de ändringar som görs för att möjliggöra för anställda att uppskatta ledig tid och begära framtida ledighetsansökningar utan att påverka deras nuvarande ledighetssaldon, ändrar också hur ledighetssaldon ändras.</span><span class="sxs-lookup"><span data-stu-id="a90b9-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="a90b9-141">Saldot som visas för tillfället är hur lång ledighet som är tillgänglig för begäranden, inklusive periodiseringar via idag och alla godkända tjänstledighetsansökningar till slutet av tiden.</span><span class="sxs-lookup"><span data-stu-id="a90b9-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="a90b9-142">När möjligheten att ställa en prognos frisläpps, visar saldot ändringar för att det aktuella saldot för ledighet inklusive periodiseringar via idag och ansökningar via idag.</span><span class="sxs-lookup"><span data-stu-id="a90b9-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="a90b9-143">Medarbetare och chefer ser dessa uppdaterade saldon i medarbetares och chefers självbetjäning på kortet **ledighet** och i fönstret **ledighetssaldon**.</span><span class="sxs-lookup"><span data-stu-id="a90b9-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="a90b9-144">Personalchefer kommer att se alla dessa uppdaterade saldon på arbetsytan **Personer** och i medarbetarens fönster **Tilldelade tjänstledighetsplaner**.</span><span class="sxs-lookup"><span data-stu-id="a90b9-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="a90b9-145">Kända problem</span><span class="sxs-lookup"><span data-stu-id="a90b9-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance"></a><span data-ttu-id="a90b9-146">Mappningsfel i integrationen med Finance</span><span class="sxs-lookup"><span data-stu-id="a90b9-146">Mapping errors in the integration with Finance</span></span>

<span data-ttu-id="a90b9-147">Följande problem har identifierats i den aktuella mallen för integrering av Talent med Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="a90b9-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 Finance.</span></span> <span data-ttu-id="a90b9-148">En ny mall kommer snart att publiceras och kommer att gälla alla nya integrationsprojekt som har skapats.</span><span class="sxs-lookup"><span data-stu-id="a90b9-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="a90b9-149">För befintliga integrationsprojekt uppdateras uppgiftsmappningarna.</span><span class="sxs-lookup"><span data-stu-id="a90b9-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="a90b9-150">Se följande tabell för uppdaterade mappningar.</span><span class="sxs-lookup"><span data-stu-id="a90b9-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="a90b9-151">Jobbbefattningarna till överordnad jobbuppgiftstilldelning för befattningar integrerar inte data.</span><span class="sxs-lookup"><span data-stu-id="a90b9-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="a90b9-152">Detta är ett problem som för närvarande undersöks.</span><span class="sxs-lookup"><span data-stu-id="a90b9-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="a90b9-153">Det finns ingen lösning för den aktuella mappningen.</span><span class="sxs-lookup"><span data-stu-id="a90b9-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="a90b9-154">Avdelningar för driftenhetsuppgift måste ha följande mappningar uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="a90b9-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="a90b9-155">Befintligt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-155">Existing source field</span></span>          | <span data-ttu-id="a90b9-156">Nytt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="a90b9-157">cdm_description (beskrivning)</span><span class="sxs-lookup"><span data-stu-id="a90b9-157">cdm_description (Description)</span></span>  | <span data-ttu-id="a90b9-158">cdm_name (namn)</span><span class="sxs-lookup"><span data-stu-id="a90b9-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="a90b9-159">En ytterligare mappning måste också läggas till.</span><span class="sxs-lookup"><span data-stu-id="a90b9-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="a90b9-160">Välj det senaste fältet **Ingen** för att lägga till följande mappning.</span><span class="sxs-lookup"><span data-stu-id="a90b9-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="a90b9-161">Källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-161">Source field</span></span>                   | <span data-ttu-id="a90b9-162">Målfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="a90b9-163">cdm_description (beskrivning)</span><span class="sxs-lookup"><span data-stu-id="a90b9-163">cdm_description (Description)</span></span>  | <span data-ttu-id="a90b9-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="a90b9-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="a90b9-165">Uppdaterade mappningar ska se ut som följande bilden.</span><span class="sxs-lookup"><span data-stu-id="a90b9-165">The updated mappings should look like the following image.</span></span>

![Avdelningar till driftenhetsuppgift](./media/DepartmentMapping.png)


<span data-ttu-id="a90b9-167">Jobb till jobbdetaljuppgift måste ha följande mappningar uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="a90b9-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="a90b9-168">Befintligt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-168">Existing source field</span></span>          | <span data-ttu-id="a90b9-169">Nytt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="a90b9-170">cdm_name (namn)</span><span class="sxs-lookup"><span data-stu-id="a90b9-170">cdm_name (Name)</span></span>                | <span data-ttu-id="a90b9-171">cdm_description (beskrivning)</span><span class="sxs-lookup"><span data-stu-id="a90b9-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="a90b9-172">cdm_name (beskrivning)</span><span class="sxs-lookup"><span data-stu-id="a90b9-172">cdm_name (Description)</span></span>         | <span data-ttu-id="a90b9-173">cdm_jobdescription (jobbeskrivning)</span><span class="sxs-lookup"><span data-stu-id="a90b9-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="a90b9-174">Uppdaterade mappningar ska se ut som bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="a90b9-174">The updated mappings should look like the image below.</span></span>

![Jobb till jobbdetaljuppgift](./media/JobMapping.png)

<span data-ttu-id="a90b9-176">Arbetare till arbetsuppgift måste ha följande mappningar uppdaterade.</span><span class="sxs-lookup"><span data-stu-id="a90b9-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="a90b9-177">Befintligt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-177">Existing source field</span></span>                 | <span data-ttu-id="a90b9-178">Nytt källfält</span><span class="sxs-lookup"><span data-stu-id="a90b9-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="a90b9-179">cdm_emailaddress1 (e-postadress 1)</span><span class="sxs-lookup"><span data-stu-id="a90b9-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="a90b9-180">cdm_primaryemailaddress (primär e-postadress)</span><span class="sxs-lookup"><span data-stu-id="a90b9-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="a90b9-181">cdm_telephone1 (telefon 1)</span><span class="sxs-lookup"><span data-stu-id="a90b9-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="a90b9-182">cdm_primarytelephone (primär telefon)</span><span class="sxs-lookup"><span data-stu-id="a90b9-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="a90b9-183">Transformering av fältet Kön behöver också uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a90b9-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="a90b9-184">Välj mapptypen **fn** (funktion) för kön och uppdatera följande värdemappningar.</span><span class="sxs-lookup"><span data-stu-id="a90b9-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="a90b9-185">Common Data Service, värde</span><span class="sxs-lookup"><span data-stu-id="a90b9-185">Common Data Service value</span></span>                   | <span data-ttu-id="a90b9-186">Finance and Operations, värde</span><span class="sxs-lookup"><span data-stu-id="a90b9-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="a90b9-187">75440000</span><span class="sxs-lookup"><span data-stu-id="a90b9-187">75440000</span></span>                    | <span data-ttu-id="a90b9-188">Man</span><span class="sxs-lookup"><span data-stu-id="a90b9-188">Male</span></span>                                             |
| <span data-ttu-id="a90b9-189">75440001</span><span class="sxs-lookup"><span data-stu-id="a90b9-189">75440001</span></span>                    | <span data-ttu-id="a90b9-190">Kvinna</span><span class="sxs-lookup"><span data-stu-id="a90b9-190">Female</span></span>                                           |
| <span data-ttu-id="a90b9-191">75440002</span><span class="sxs-lookup"><span data-stu-id="a90b9-191">75440002</span></span>                    | <span data-ttu-id="a90b9-192">None</span><span class="sxs-lookup"><span data-stu-id="a90b9-192">None</span></span>                                             | 
| <span data-ttu-id="a90b9-193">75440003</span><span class="sxs-lookup"><span data-stu-id="a90b9-193">75440003</span></span>                    | <span data-ttu-id="a90b9-194">Icke-specifikt</span><span class="sxs-lookup"><span data-stu-id="a90b9-194">NonSpecific</span></span>                                      |

<span data-ttu-id="a90b9-195">Uppdaterade mappningar ska se ut som följande bilderna.</span><span class="sxs-lookup"><span data-stu-id="a90b9-195">The updated mappings should look like the following images.</span></span>

![Arbetare till arbetaruppgift.](./media/WorkerMapping.png)

![Transformering av fältet Kön](./media/WorkerTransform.png)
