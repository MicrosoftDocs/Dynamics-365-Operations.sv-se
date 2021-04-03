---
title: Nyheter och ändringar i Dynamics 365 Human Resources (16 september 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 16 september 2020.
author: jcart1106
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14a4c08b0d223bc7fd8044354f5976388af9176b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467467"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a><span data-ttu-id="5be70-103">Nyheter och ändringar i Dynamics 365 Human Resources (16 september 2020)</span><span class="sxs-lookup"><span data-stu-id="5be70-103">What's new or changed in Dynamics 365 Human Resources (September 16, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5be70-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5be70-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5be70-105">Ändringarna tillämpas på versionsnummer 8.1.3557.</span><span class="sxs-lookup"><span data-stu-id="5be70-105">Changes apply to build number 8.1.3557.</span></span> <span data-ttu-id="5be70-106">Siffror inom parenteser bredvid vissa funktioner refererar till supportnummer i Lifecycle Services (LCS) för referens.</span><span class="sxs-lookup"><span data-stu-id="5be70-106">The numbers in parentheses next to some features refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="included-in-this-release"></a><span data-ttu-id="5be70-107">Ingår i den här versionen</span><span class="sxs-lookup"><span data-stu-id="5be70-107">Included in this release</span></span>

-  [<span data-ttu-id="5be70-108">Sparade vyer – allmän tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="5be70-108">Saved views - general availability</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br><span data-ttu-id="5be70-109">- För mer information, se [Sparade vyer](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views).</span><span class="sxs-lookup"><span data-stu-id="5be70-109">- For more information, see [Saved views](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views).</span></span> 

- <span data-ttu-id="5be70-110">Formuläret **Positionsåtgärder** har uppdaterade dimensionsrutnät och ny dialog (469495).</span><span class="sxs-lookup"><span data-stu-id="5be70-110">The **Position actions** form has an updated dimensions grid and new dialogue (469495).</span></span>

- <span data-ttu-id="5be70-111">Om du ställer in **begränsa åtkomsten till arbetsuppgifter** till Ja i **Avancerad åtkomst** i **Delade parametrar för Personal** visas nu bara de aktuella arbetarna (393384).</span><span class="sxs-lookup"><span data-stu-id="5be70-111">If you set **Restrict access to worker information** to yes in **Advanced access** in **Human Resources Shared parameters**, benefits forms now show only the appropriate workers (393384).</span></span>

- <span data-ttu-id="5be70-112">Nya alternativ för att skapa kalendrar i entiteten **WorkCalendar** (477055):</span><span class="sxs-lookup"><span data-stu-id="5be70-112">New calendar generation options in the **WorkCalendar** entity (477055):</span></span><br><span data-ttu-id="5be70-113">- Standard sluttid</span><span class="sxs-lookup"><span data-stu-id="5be70-113">- Default ending time</span></span><br><span data-ttu-id="5be70-114">- Standard starttid</span><span class="sxs-lookup"><span data-stu-id="5be70-114">-    Default starting time</span></span><br><span data-ttu-id="5be70-115">- Är fredag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-115">-  Is Friday working day</span></span><br><span data-ttu-id="5be70-116">- Är måndag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-116">-  Is Monday working day</span></span><br><span data-ttu-id="5be70-117">- Är lördag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-117">-  Is Saturday working day</span></span><br><span data-ttu-id="5be70-118">- Är söndag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-118">- Is Sunday working day</span></span><br><span data-ttu-id="5be70-119">- Är torsdag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-119">- Is Thursday working day</span></span><br><span data-ttu-id="5be70-120">- Är tisdag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-120">- Is Tuesday working day</span></span><br><span data-ttu-id="5be70-121">- Är onsdag arbetsdag</span><span class="sxs-lookup"><span data-stu-id="5be70-121">- Is Wednesday working day</span></span><br><span data-ttu-id="5be70-122">- Helgdags-ID i arbetskalender</span><span class="sxs-lookup"><span data-stu-id="5be70-122">- Work calendar holiday ID</span></span>

- <span data-ttu-id="5be70-123">Entiteten **LeaveBankTransactionV1** omfattar nu orsakskoden (477823).</span><span class="sxs-lookup"><span data-stu-id="5be70-123">The **LeaveBankTransactionV1** entity now includes the reason code (477823).</span></span>

- <span data-ttu-id="5be70-124">Du kan nu spara uppgiftsregistreringar (492923).</span><span class="sxs-lookup"><span data-stu-id="5be70-124">You can now save task recordings (492923).</span></span>

- <span data-ttu-id="5be70-125">Nu har data publicerats från **HCMWorkerContactEntity** (427620).</span><span class="sxs-lookup"><span data-stu-id="5be70-125">Data is now published successfully from **HCMWorkerContactEntity** (427620).</span></span>

- <span data-ttu-id="5be70-126">Snabbfliken **Kompensation** visas nu för leverantörens arbetartyp ange formuläret **Arbetarens åtgärder** (482494).</span><span class="sxs-lookup"><span data-stu-id="5be70-126">The **Compensation** fast tab now displays for the contractor worker type in the **Worker actions** form (482494).</span></span>

- <span data-ttu-id="5be70-127">Fälten **Nivå** och **Plan** är nu obligatoriska om du anger en **Fast kompensation**.</span><span class="sxs-lookup"><span data-stu-id="5be70-127">The **Level** and **Plan** fields are now mandatory if you set **Fixed compensation**.</span></span> <span data-ttu-id="5be70-128">Ett felmeddelande visas om du lämnar dessa fält tomma (482497).</span><span class="sxs-lookup"><span data-stu-id="5be70-128">An error message displays if you leave these fields blank (482497).</span></span>

- <span data-ttu-id="5be70-129">Fältet **Plantyp** i **Förmåner** är nu en nedrullningsbar lista (488768).</span><span class="sxs-lookup"><span data-stu-id="5be70-129">The **Plan type** field in **Benefits** is now a dropdown list (488768).</span></span>

- <span data-ttu-id="5be70-130">Systemadministratörer får nu ett meddelande om att ett anpassat fält tas bort från Personal (481408).</span><span class="sxs-lookup"><span data-stu-id="5be70-130">System administrators now receive a notification if a custom field is deleted from Human Resources (481408).</span></span>

- <span data-ttu-id="5be70-131">Under medarbetarens uppsägningsprocess beter sig Personal som förväntat och ändrar inte det valda företaget efter att ha låst sig (479877).</span><span class="sxs-lookup"><span data-stu-id="5be70-131">During the terminate employee process, Human Resources behaves as expected and doesn't change the selected company after appearing to lock (479877).</span></span> 

- <span data-ttu-id="5be70-132">Chefer kan inte längre lägga till en nummerkolumn genom anpassning (485317).</span><span class="sxs-lookup"><span data-stu-id="5be70-132">Managers can no longer add a number column through personalization (485317).</span></span>

- <span data-ttu-id="5be70-133">Chefer kan inte längre ta bort dataområdes filtret från identifieringsnummer som upphör att gälla (485321).</span><span class="sxs-lookup"><span data-stu-id="5be70-133">Managers can no longer remove the data range filter from identification numbers expiring (485321).</span></span>

- <span data-ttu-id="5be70-134">När fältet **Rapporteras till** är tomt, visas befattningsdetaljer fortfarande när du hovrar över befattningen (433328).</span><span class="sxs-lookup"><span data-stu-id="5be70-134">When the **Reports to** field is empty, position details still display when hovering over the position (433328).</span></span>

- <span data-ttu-id="5be70-135">Medarbetarna kan nu visa information om förmånsplaner i Employee Self Service (481676).</span><span class="sxs-lookup"><span data-stu-id="5be70-135">Employees can now view benefit plan information in Employee self service (481676).</span></span>

- <span data-ttu-id="5be70-136">Medarbetarna kan nu se alla registrerade kurser (429048).</span><span class="sxs-lookup"><span data-stu-id="5be70-136">Employees can now see all registered courses (429048).</span></span>

- <span data-ttu-id="5be70-137">Du kan nu begränsa visningsalternativen för sidan **Professionella certifikat**.</span><span class="sxs-lookup"><span data-stu-id="5be70-137">You can now restrict viewing options for the **Professional certificates** page.</span></span> <span data-ttu-id="5be70-138">Du kan begränsa visningsalternativen till den aktuella juridiska personen efter arbetsstatus och efter typ av arbetare (451501).</span><span class="sxs-lookup"><span data-stu-id="5be70-138">You can restrict viewing options to the current legal entity, by worker status, and by worker type (451501).</span></span> 


## <a name="in-preview"></a><span data-ttu-id="5be70-139">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="5be70-139">In Preview</span></span>

### <a name="human-resources-app-in-teams"></a><span data-ttu-id="5be70-140">Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="5be70-140">Human Resources app in Teams</span></span>

<span data-ttu-id="5be70-141">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5be70-141">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="5be70-142">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="5be70-142">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="5be70-143">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="5be70-143">For more information, see:</span></span>

- <span data-ttu-id="5be70-144">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 1-planen</span><span class="sxs-lookup"><span data-stu-id="5be70-144">[Employee leave and absence experience in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- <span data-ttu-id="5be70-145">[Personal i Teams](https://go.microsoft.com/fwlink/?linkid=2127841) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="5be70-145">[Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841) in Human Resources documentation</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="5be70-146">Förhandsfunktioner för Personal-app i Teams</span><span class="sxs-lookup"><span data-stu-id="5be70-146">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="5be70-147">**Meddelanden**: skicka och granskare av tidsförfrågningar kommer att meddelas i modulen Personal-app i Teams.</span><span class="sxs-lookup"><span data-stu-id="5be70-147">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="5be70-148">Godkännare kan godkänna eller neka förfrågningar om ledighet.</span><span class="sxs-lookup"><span data-stu-id="5be70-148">Approvers can approve or deny time-off requests.</span></span> <span data-ttu-id="5be70-149">Avsändare kommer att meddelas om begäran har godkänts eller avslagits.</span><span class="sxs-lookup"><span data-stu-id="5be70-149">Submitters will be notified if the request was approved or denied.</span></span> <span data-ttu-id="5be70-150">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="5be70-150">For more information, see:</span></span>
   - <span data-ttu-id="5be70-151">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="5be70-151">[Employee leave and absence experience in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="5be70-152">[Aktivera meddelanden för Personal-appar i Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="5be70-152">[Enable notifications for the Human Resources app in Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) in Human Resources documentation</span></span>
   - <span data-ttu-id="5be70-153">[Aktivera eller inaktivera Teams-meddelanden för enskilda användare](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) i Personal</span><span class="sxs-lookup"><span data-stu-id="5be70-153">[Turn Teams notifications on or off for individual users](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) in Human Resources documentation</span></span>
   - <span data-ttu-id="5be70-154">[Team meddelanden](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) i Personal-dokumentation</span><span class="sxs-lookup"><span data-stu-id="5be70-154">[Teams notifications](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) in Human Resources documentation</span></span>
   - <span data-ttu-id="5be70-155">[Visa gruppens tjänstledighetskalender](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) i Personal dokumentation</span><span class="sxs-lookup"><span data-stu-id="5be70-155">[View your team's leave calendar](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) in Human Resources documentation</span></span>
 
- <span data-ttu-id="5be70-156">**Ledighetskalender för chef**: chefer kommer att kunna se godkänd och väntande ledighet för sina underställda i en kalendervy.</span><span class="sxs-lookup"><span data-stu-id="5be70-156">**Manager time-off calendar**: Managers can see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="5be70-157">Den här vyn gör det enklare att förstå när gruppmedlemmarna är borta från arbetet.</span><span class="sxs-lookup"><span data-stu-id="5be70-157">This view provides an easy understanding of when their team members are away from work.</span></span> <span data-ttu-id="5be70-158">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="5be70-158">For more information, see:</span></span>
   - <span data-ttu-id="5be70-159">[Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="5be70-159">[Employee leave and absence experience in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 2 plan</span></span>
   - <span data-ttu-id="5be70-160">[Visa gruppens tjänstledighetskalender](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) i Personal dokumentation</span><span class="sxs-lookup"><span data-stu-id="5be70-160">[View your team's leave calendar](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) in Human Resources documentation</span></span>

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a><span data-ttu-id="5be70-161">Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig (477004)</span><span class="sxs-lookup"><span data-stu-id="5be70-161">Configuration option to position Work items assigned to me list (477004)</span></span>

<span data-ttu-id="5be70-162">Det finns nu ett nytt alternativ för att placera **Arbetsuppgifter som tilldelats till mig** i den högra kolumnen på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="5be70-162">A new option is now available to position the **Work items assigned to me** list in the right-hand column of the dashboard.</span></span> <span data-ttu-id="5be70-163">Med den här ändringen visas alla arbetsobjekt och att göra-listor i samma område.</span><span class="sxs-lookup"><span data-stu-id="5be70-163">With this change, all work items and to do lists display in the same area.</span></span> <span data-ttu-id="5be70-164">Aktivera den här funktionen genom att aktivera **Förhandsversion – Förbättringar av arbetsflödesupplevelse** i funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="5be70-164">Enable this functionality by turning on **Preview - Workflow experience enhancements** in Feature management.</span></span> <span data-ttu-id="5be70-165">Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="5be70-165">For more information about turning on preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

<span data-ttu-id="5be70-166">Den här funktionen främjar också de arbetsflödesalternativ som visas i formuläret personalåtgärder.</span><span class="sxs-lookup"><span data-stu-id="5be70-166">This feature also promotes the workflow options that appear in the personnel actions forms.</span></span> <span data-ttu-id="5be70-167">Arbetsflödesalternativen visas även ovanför åtgärdens snabbflik för snabbåtkomst.</span><span class="sxs-lookup"><span data-stu-id="5be70-167">Workflow options also appear above the action fast tab for quick access.</span></span> <span data-ttu-id="5be70-168">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="5be70-168">For more information, see:</span></span> 

- <span data-ttu-id="5be70-169">[Arbetsflöde för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) i Dynamics 365 2020 utgivningsvåg 2-planen</span><span class="sxs-lookup"><span data-stu-id="5be70-169">[Organization and personnel management workflow experience enhancements](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) in the Dynamics 365 2020 release wave 2 plan</span></span>

![Arbetsuppgifter som tilldelats till mig](./media/hr-workflow-work-items-assigned-to-me.png)

![Snabbåtkomst till arbetsflödesartiklar](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a><span data-ttu-id="5be70-172">Kalender för ledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="5be70-172">Leave and absence calendar</span></span>

<span data-ttu-id="5be70-173">Den här versionen innehåller ytterligare kalenderalternativ för tjänstledighets- och frånvarokalendrar.</span><span class="sxs-lookup"><span data-stu-id="5be70-173">This release includes additional calendar options for leave and absence calendars.</span></span> <span data-ttu-id="5be70-174">Mer information finns i [Visa team- och företagskalendrar](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).</span><span class="sxs-lookup"><span data-stu-id="5be70-174">For more information, see [View team and company calendars](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="5be70-175">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="5be70-175">Coming Soon</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="5be70-176">Entiteter för checklista inkluderade i Dataverse</span><span class="sxs-lookup"><span data-stu-id="5be70-176">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="5be70-177">Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5be70-177">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

### <a name="benefits-management-reason-codes"></a><span data-ttu-id="5be70-178">Orsakskoder för hantering av förmåner</span><span class="sxs-lookup"><span data-stu-id="5be70-178">Benefits management reason codes</span></span>

<span data-ttu-id="5be70-179">Orsakskoder för förmånshantering kommer snart att kombineras med befintliga orsakskoder i Personal.</span><span class="sxs-lookup"><span data-stu-id="5be70-179">Benefits management reason codes will soon be combined with existing reason codes in Human Resources.</span></span> <span data-ttu-id="5be70-180">Om du skapade orsakskoder i en förmånshantering som är över 15 tecken stora måste du ändra namnet på orsakskoden i formuläret för förmåner i förmånshanteringens formulär **orsakskoder** till 15 tecken eller mindre.</span><span class="sxs-lookup"><span data-stu-id="5be70-180">If you created reason codes in Benefits management that are over 15 characters, you must change the name of the reason code in the Benefits management **Reason codes** form to be 15 characters or less.</span></span> <span data-ttu-id="5be70-181">När du har uppdaterat namnet visas orsakskoden under formuläret befintlig orsakskod i personalhantering.</span><span class="sxs-lookup"><span data-stu-id="5be70-181">After you update the name, the reason code will appear under the existing reason code form in Personnel management.</span></span> <span data-ttu-id="5be70-182">Den här ändringen kommer att vara tillgänglig i framtiden och påverkar inte befintliga funktioner.</span><span class="sxs-lookup"><span data-stu-id="5be70-182">This change will be available in the future and won't affect existing functionality.</span></span>

## <a name="see-also"></a><span data-ttu-id="5be70-183">Se även</span><span class="sxs-lookup"><span data-stu-id="5be70-183">See also</span></span>

[<span data-ttu-id="5be70-184">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="5be70-184">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="5be70-185">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="5be70-185">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="5be70-186">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="5be70-186">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="5be70-187">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="5be70-187">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]