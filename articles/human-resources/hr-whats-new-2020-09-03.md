---
title: Nyheter och ändringar i Dynamics 365 Human Resources (03 september 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 3 september 2020.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10978d8843e7bce2800d62b63e58152569be9631
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891779"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a><span data-ttu-id="a9890-103">Nyheter och ändringar i Dynamics 365 Human Resources (3 september 2020)</span><span class="sxs-lookup"><span data-stu-id="a9890-103">What's new or changed in Dynamics 365 Human Resources (September 3, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9890-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9890-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a9890-105">Ändringarna tillämpas på versionsnummer 8.1.3504.</span><span class="sxs-lookup"><span data-stu-id="a9890-105">Changes apply to build number 8.1.3504.</span></span> <span data-ttu-id="a9890-106">Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.</span><span class="sxs-lookup"><span data-stu-id="a9890-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

<span data-ttu-id="a9890-107">Mer information om kommande funktioner i Personal finns i [Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).</span><span class="sxs-lookup"><span data-stu-id="a9890-107">For more information about upcoming features in Human Resources, see [Overview of Dynamics 365 Human Resources 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).</span></span> <span data-ttu-id="a9890-108">Mer information om uppdateringsprocessen för Personal finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="a9890-108">For more information about the update process for Human Resources, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="in-this-release"></a><span data-ttu-id="a9890-109">I den här versionen</span><span class="sxs-lookup"><span data-stu-id="a9890-109">In this release</span></span>

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a><span data-ttu-id="a9890-110">Nya standardrutnät för ekonomiska dimensioner och dialogmönster i Personal (469495)</span><span class="sxs-lookup"><span data-stu-id="a9890-110">New default financial dimensions grid and dialog pattern throughout Human Resources (469495)</span></span>

<span data-ttu-id="a9890-111">Det nya mönstret för ekonomiska dimensioner är nu tillgängligt i följande områden:</span><span class="sxs-lookup"><span data-stu-id="a9890-111">The new pattern for financial dimensions is now available in the following areas:</span></span>

- <span data-ttu-id="a9890-112">Positionsåtgärder (formulär: **HcmPositionActionDetail**)</span><span class="sxs-lookup"><span data-stu-id="a9890-112">Position actions  (Form: **HcmPositionActionDetail**)</span></span>
- <span data-ttu-id="a9890-113">Löneuppbetalningskoder (formulär: **PayrollEarningCode**)</span><span class="sxs-lookup"><span data-stu-id="a9890-113">Payroll earning codes  (Form: **PayrollEarningCode**)</span></span>

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a><span data-ttu-id="a9890-114">Poster visas inte i företagets tjänstledighet om ledighet och förbättringar av frånvarokalendern inte aktiveras (484406)</span><span class="sxs-lookup"><span data-stu-id="a9890-114">Entries don't appear in company leave calendar if Leave and absence calendar enhancements aren't enabled (484406)</span></span>

<span data-ttu-id="a9890-115">Den här versionen åtgärdar ett problem där poster i företagets tjänstledighet inte visas i kalendern.</span><span class="sxs-lookup"><span data-stu-id="a9890-115">This release corrects an issue where leave entries aren't displayed in the company leave calendar.</span></span> <span data-ttu-id="a9890-116">Det här problemet uppstår bara när alternativet för funktionshantering **ledighet och förbättringar av frånvarokalendern inte aktiveras** inte är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="a9890-116">This issue only occurs when the Feature management option **Leave and absence calendar enhancements** isn't enabled.</span></span>

### <a name="benefitplanemployeeentity-issue-467597"></a><span data-ttu-id="a9890-117">Problem med BenefitPlanEmployeeEntity (467597)</span><span class="sxs-lookup"><span data-stu-id="a9890-117">BenefitPlanEmployeeEntity issue (467597)</span></span>

<span data-ttu-id="a9890-118">Den här utgåvan korrigerar ett problem med entiteten **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="a9890-118">This release corrects an issue with the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="a9890-119">När du importerar medarbetares registreringar **Omfattningskod** och **Plantypkod** ställs nu in korrekt.</span><span class="sxs-lookup"><span data-stu-id="a9890-119">When importing worker enrollments, the **Coverage code** and the **Plan type code** are now set correctly.</span></span> <span data-ttu-id="a9890-120">Det här problemet medförde att medarbetar förmånsplaner visas felaktigt i formuläret **förmånsplan för arbetare** och i formuläret **öppen anmälan** i Självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="a9890-120">This issue caused employee benefit plans to display incorrectly in the **Worker benefits plan** and **Open enrollment** forms in Employee self service.</span></span>

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a><span data-ttu-id="a9890-121">Elektronisk fil 1094-C utdata saknas i XML (435190)</span><span class="sxs-lookup"><span data-stu-id="a9890-121">Electronic file 1094-C output missing letter in XML (435190)</span></span>

<span data-ttu-id="a9890-122">Den här ändringen åtgärdar ett problem med utdatafilen 1094-C som saknar ett tecken som behövs för att skicka till IRS.</span><span class="sxs-lookup"><span data-stu-id="a9890-122">This change corrects an issue with the 1094-C output file missing a character needed when submitting to the IRS.</span></span>

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a><span data-ttu-id="a9890-123">Register för variabel kompensation för medarbetare mappad till formulär för fast kompensation (476117)</span><span class="sxs-lookup"><span data-stu-id="a9890-123">Employee variable compensation table mapped to fixed compensation form (476117)</span></span>

<span data-ttu-id="a9890-124">Den här ändringen justerar fälten för fasta kompensationer med formuläret för fast kompensation.</span><span class="sxs-lookup"><span data-stu-id="a9890-124">This change aligns the fixed compensation fields with the fixed compensation form.</span></span> <span data-ttu-id="a9890-125">Variabla kompensations fält är nu bara tillgängliga i formuläret för variabel kompensation.</span><span class="sxs-lookup"><span data-stu-id="a9890-125">Variable compensation fields are now only available with the variable compensation form.</span></span>

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a><span data-ttu-id="a9890-126">Lämna begäran som är tillåtna före registrering om tjänstledighetstypen har ett negativt minsta saldo (469917)</span><span class="sxs-lookup"><span data-stu-id="a9890-126">Leave requests allowed before enrollment if that leave type has a negative minimum balance (469917)</span></span>

<span data-ttu-id="a9890-127">Den här ändringen tillåter inte att du anger tjänstledighetsbegäran innan de registreras i planen, även om registreringen har ett negativt minsta saldo.</span><span class="sxs-lookup"><span data-stu-id="a9890-127">This change prohibits entering leave requests before being enrolled in the plan, even if the enrollment has a negative minimum balance.</span></span> <span data-ttu-id="a9890-128">Du kan bara ange eller skicka förfrågningar när planen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="a9890-128">You can only enter or submit requests when the plan is active.</span></span>

### <a name="document-templates-dont-download-457279"></a><span data-ttu-id="a9890-129">Dokumentmallar hämtas inte (457279)</span><span class="sxs-lookup"><span data-stu-id="a9890-129">Document templates don't download (457279)</span></span>

<span data-ttu-id="a9890-130">Med den här ändringen kan du nu hämta alla dokumentmallar.</span><span class="sxs-lookup"><span data-stu-id="a9890-130">With this change, you can now download all document templates.</span></span> 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a><span data-ttu-id="a9890-131">Data visas som kolumnrubriker i stället för rader för fältet lönesats i rapporten kompensationsplan (476077)</span><span class="sxs-lookup"><span data-stu-id="a9890-131">Data displays as column headers instead of rows for the Pay rate field in the compensation plan report (476077)</span></span>

<span data-ttu-id="a9890-132">Analysrapporten visar nu korrekt information för **lönesatsen**.</span><span class="sxs-lookup"><span data-stu-id="a9890-132">The analytics report now displays the correct information for **Pay rate**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a9890-133">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="a9890-133">In preview</span></span>

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="a9890-134">Personalapp i Teams</span><span class="sxs-lookup"><span data-stu-id="a9890-134">Human Resources application in Teams</span></span>

<span data-ttu-id="a9890-135">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a9890-135">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a9890-136">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="a9890-136">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a9890-137">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a9890-137">For more information, see:</span></span>

- <span data-ttu-id="a9890-138">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 1-planen</span><span class="sxs-lookup"><span data-stu-id="a9890-138">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- <span data-ttu-id="a9890-139">[Personal i Teams](./hr-admin-teams-leave-app.md) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="a9890-139">[Human Resources app in Teams](./hr-admin-teams-leave-app.md) in Human Resources documentation</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="a9890-140">Förhandsfunktioner för Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="a9890-140">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="a9890-141">**Meddelanden**: skicka och granskare av tidsförfrågningar kommer att meddelas i modulen Personal-app i Teams.</span><span class="sxs-lookup"><span data-stu-id="a9890-141">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="a9890-142">Godkännare kan godkänna eller neka förfrågningar om ledighet.</span><span class="sxs-lookup"><span data-stu-id="a9890-142">Approvers will be able to approve or deny time-off requests.</span></span> <span data-ttu-id="a9890-143">Avsändare kommer att meddelas om begäran har godkänts eller avslagits.</span><span class="sxs-lookup"><span data-stu-id="a9890-143">Submitters will be notified if the request was approved or denied.</span></span> <span data-ttu-id="a9890-144">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a9890-144">For more information, see:</span></span>
   - <span data-ttu-id="a9890-145">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="a9890-145">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="a9890-146">[Aktivera meddelanden för Personal-appar i Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="a9890-146">[Enable notifications for the Human Resources app in Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) in Human Resources documentation</span></span>
   - <span data-ttu-id="a9890-147">[Aktivera eller inaktivera Teams-meddelanden för enskilda användare](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) i Personal</span><span class="sxs-lookup"><span data-stu-id="a9890-147">[Turn Teams notifications on or off for individual users](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) in Human Resources documentation</span></span>
   - <span data-ttu-id="a9890-148">[Team meddelanden](./hr-teams-leave-app.md#respond-to-teams-notifications) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="a9890-148">[Teams notifications](./hr-teams-leave-app.md#respond-to-teams-notifications) in Human Resources documentation</span></span>
   - <span data-ttu-id="a9890-149">[Visa gruppens tjänstledighetskalender](./hr-teams-leave-app.md#view-your-teams-leave-calendar) i Personal dokumentation</span><span class="sxs-lookup"><span data-stu-id="a9890-149">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>
 
- <span data-ttu-id="a9890-150">**Ledighetskalender för chef**: chefer kommer att kunna se godkänd och väntande ledighet för sina underställda i en kalendervy.</span><span class="sxs-lookup"><span data-stu-id="a9890-150">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="a9890-151">Den här vyn gör det enklare att förstå när gruppmedlemmarna är borta från arbetet.</span><span class="sxs-lookup"><span data-stu-id="a9890-151">This view provides an easy understanding of when their team members are away from work.</span></span> <span data-ttu-id="a9890-152">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a9890-152">For more information, see:</span></span>
   - <span data-ttu-id="a9890-153">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="a9890-153">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="a9890-154">[Visa gruppens tjänstledighetskalender](./hr-teams-leave-app.md#view-your-teams-leave-calendar) i Personal dokumentation</span><span class="sxs-lookup"><span data-stu-id="a9890-154">[View your team's leave calendar](./hr-teams-leave-app.md#view-your-teams-leave-calendar) in Human Resources documentation</span></span>

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a><span data-ttu-id="a9890-155">Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig (477004)</span><span class="sxs-lookup"><span data-stu-id="a9890-155">Configuration option to position Work items assigned to me list (477004)</span></span>

<span data-ttu-id="a9890-156">Det finns nu ett nytt alternativ för att placera **Arbetsuppgifter som tilldelats till mig** i den högra kolumnen på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="a9890-156">A new option is now available to position the **Work items assigned to me** list in the right-hand column of the dashboard.</span></span> <span data-ttu-id="a9890-157">Med den här ändringen visas alla arbetsobjekt och att göra-listor i samma område.</span><span class="sxs-lookup"><span data-stu-id="a9890-157">With this change, all work items and to do lists display in the same area.</span></span> <span data-ttu-id="a9890-158">Aktivera den här funktionen genom att aktivera **Förhandsversion – Förbättringar av arbetsflödesupplevelse** i funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="a9890-158">Enable this functionality by turning on **Preview - Workflow experience enhancements** in Feature management.</span></span> <span data-ttu-id="a9890-159">Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="a9890-159">For more information about turning on preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

<span data-ttu-id="a9890-160">Den här funktionen främjar också de arbetsflödesalternativ som visas i formuläret personalåtgärder.</span><span class="sxs-lookup"><span data-stu-id="a9890-160">This feature also promotes the workflow options that appear in the personnel actions forms.</span></span> <span data-ttu-id="a9890-161">Arbetsflödesalternativen visas även ovanför åtgärdens snabbflik för snabbåtkomst.</span><span class="sxs-lookup"><span data-stu-id="a9890-161">Workflow options also appear above the action fast tab for quick access.</span></span> <span data-ttu-id="a9890-162">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a9890-162">For more information, see:</span></span> 

- <span data-ttu-id="a9890-163">[Arbetsflöde för organisation och personalhantering](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="a9890-163">[Organization and personnel management workflow experience enhancements](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) in the Dynamics 365 2020 release wave 2 plan</span></span>

![Arbetsuppgifter som tilldelats till mig](./media/hr-workflow-work-items-assigned-to-me.png)

![Snabbåtkomst till arbetsflödesartiklar](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a><span data-ttu-id="a9890-166">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="a9890-166">Coming Soon</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="a9890-167">Entiteter för checklista inkluderade i Dataverse</span><span class="sxs-lookup"><span data-stu-id="a9890-167">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="a9890-168">Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9890-168">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

### <a name="benefits-management-reason-codes"></a><span data-ttu-id="a9890-169">Orsakskoder för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="a9890-169">Benefits management reason codes</span></span>

<span data-ttu-id="a9890-170">Orsakskoder för förmånshantering kommer snart att kombineras med befintliga orsakskoder i Personal.</span><span class="sxs-lookup"><span data-stu-id="a9890-170">Benefits management reason codes will soon be combined with existing reason codes in Human Resources.</span></span> <span data-ttu-id="a9890-171">Om du skapade orsakskoder i en förmånshantering som är över 15 tecken stora måste du ändra namnet på orsakskoden i formuläret för förmåner i förmånshanteringens formulär **orsakskoder** till 15 tecken eller mindre.</span><span class="sxs-lookup"><span data-stu-id="a9890-171">If you created reason codes in Benefits management that are over 15 characters, you must change the name of the reason code in the Benefits management **Reason codes** form to be 15 characters or less.</span></span> <span data-ttu-id="a9890-172">När du har uppdaterat namnet visas orsakskoden under formuläret befintlig orsakskod i personalhantering.</span><span class="sxs-lookup"><span data-stu-id="a9890-172">After you update the name, the reason code will appear under the existing reason code form in Personnel management.</span></span> <span data-ttu-id="a9890-173">Den här ändringen kommer att vara tillgänglig i framtiden och påverkar inte befintliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="a9890-173">This change will be available in the future and won't affect existing functionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9890-174">Se även</span><span class="sxs-lookup"><span data-stu-id="a9890-174">See also</span></span>

[<span data-ttu-id="a9890-175">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="a9890-175">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a9890-176">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="a9890-176">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a9890-177">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="a9890-177">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a9890-178">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="a9890-178">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
