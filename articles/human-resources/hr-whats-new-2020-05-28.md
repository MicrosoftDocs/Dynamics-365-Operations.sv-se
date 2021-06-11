---
title: Nyheter och ändringar i Dynamics 365 Human Resources (28 maj 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 28 maj 2020.
author: andreabichsel
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d5396e24f036e670ce276911cd3582442a98da7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054342"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="6754d-103">Nyheter och ändringar i Dynamics 365 Human Resources (28 maj 2020)</span><span class="sxs-lookup"><span data-stu-id="6754d-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6754d-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6754d-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="6754d-105">Ändringarna tillämpas på versionsnummer 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="6754d-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="6754d-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="6754d-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="6754d-107">LeaveRequest-entitet fungerar inte när du aktiverar flera typer per tjänstledighetsplan (447498)</span><span class="sxs-lookup"><span data-stu-id="6754d-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="6754d-108">Med den här ändringen är **LeaveEnrollmentV2Entity** nu tillgänglig för att korrigera det fel som uppstår när du aktiverar flera tjänstledighetstyper.</span><span class="sxs-lookup"><span data-stu-id="6754d-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="6754d-109">Funktionen för minskning av batch-konkurrens (förhandsgranskning) (446619)</span><span class="sxs-lookup"><span data-stu-id="6754d-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="6754d-110">När du aktiverar den här funktionen kan du förvänta dig en minskning av blockeringen på batch-ramverkstabeller när du väljer uppgifter och slutför jobb.</span><span class="sxs-lookup"><span data-stu-id="6754d-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="6754d-111">UpdateConflict medan du sparar arbetare förhindrar redigering av en post i personer (427915)</span><span class="sxs-lookup"><span data-stu-id="6754d-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="6754d-112">Den här ändringen korrigerar ett fel när en ny arbetare läggs till, uppdatering av adressinformation och ändring av språkinställningar görs.</span><span class="sxs-lookup"><span data-stu-id="6754d-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="6754d-113">I det unika scenariot visas ett fel som anger att posten inte kunde uppdateras.</span><span class="sxs-lookup"><span data-stu-id="6754d-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="6754d-114">Det går inte att lägga till en bilaga till en godkänd tjänstledighetsansökan som ska skickas in på nytt (425407)</span><span class="sxs-lookup"><span data-stu-id="6754d-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="6754d-115">Denna ändring tillåter nu bilagor till godkända tjänstledighetsansökningar.</span><span class="sxs-lookup"><span data-stu-id="6754d-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="6754d-116">Användaren kan ange kompensation för en medarbetare i ett annat formulär för juridisk person (409529)</span><span class="sxs-lookup"><span data-stu-id="6754d-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="6754d-117">Denna ändring inaktiverar kompensationsalternativ för att förhindra oavsiktlig registrering av kompensationsposter för fel juridisk person.</span><span class="sxs-lookup"><span data-stu-id="6754d-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="6754d-118">Fel när du överför en medarbetare och datumet för tilldelningsarbetarposition är före positionen varaktighet (429402)</span><span class="sxs-lookup"><span data-stu-id="6754d-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="6754d-119">Felmeddelanden vid överföring av en medarbetare i det här scenariot har uppdaterats för att bättre beskriva de ändringar som är nödvändiga för att rätta till problemet.</span><span class="sxs-lookup"><span data-stu-id="6754d-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="6754d-120">Bilagefunktioner i registrering av självbetjäningen för medarbetarens förmåner</span><span class="sxs-lookup"><span data-stu-id="6754d-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="6754d-121">Nu kan du lägga till bilagor under förmånsregistreringsprocessen för varje plan som medarbetaren registrerar sig i.</span><span class="sxs-lookup"><span data-stu-id="6754d-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="6754d-122">Du kan sedan visa bilagorna i formuläret **Förmåner som arbetaren är anmäld till**.</span><span class="sxs-lookup"><span data-stu-id="6754d-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="6754d-123">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="6754d-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="6754d-124">Personalapp i Teams</span><span class="sxs-lookup"><span data-stu-id="6754d-124">Human Resources application in Teams</span></span>

<span data-ttu-id="6754d-125">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6754d-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="6754d-126">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="6754d-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="6754d-127">Mer information finns [i personalapp i Teams](./hr-admin-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="6754d-127">For more information, see [Human Resources app in Teams](./hr-admin-teams-leave-app.md).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="6754d-128">Lämna uppehåll</span><span class="sxs-lookup"><span data-stu-id="6754d-128">Leave suspension</span></span>

<span data-ttu-id="6754d-129">Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="6754d-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="6754d-130">Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna.</span><span class="sxs-lookup"><span data-stu-id="6754d-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="6754d-131">Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo.</span><span class="sxs-lookup"><span data-stu-id="6754d-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="6754d-132">Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="6754d-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="6754d-133">Uppdatera användarupplevelsen att anger att periodiseringen är pausad (429550)</span><span class="sxs-lookup"><span data-stu-id="6754d-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="6754d-134">Användarupplevelsen anger nu att periodiseringen har avbrutits för en plan.</span><span class="sxs-lookup"><span data-stu-id="6754d-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="6754d-135">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="6754d-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="6754d-136">Databasloggning (i förhandsgranskning i juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="6754d-137">Med funktionen för databasloggning kan du bestämma vilka register och fält som ska övervakas.</span><span class="sxs-lookup"><span data-stu-id="6754d-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="6754d-138">Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen.</span><span class="sxs-lookup"><span data-stu-id="6754d-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="6754d-139">Begärankapacitet kan visa dessa ändringar med tiden.</span><span class="sxs-lookup"><span data-stu-id="6754d-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="6754d-140">Köpa och sälja tjänstledighet (i förhandsversion 1 juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="6754d-141">Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="6754d-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="6754d-142">Den här processen hanteras ofta manuellt.</span><span class="sxs-lookup"><span data-stu-id="6754d-142">This process is often managed manually.</span></span> <span data-ttu-id="6754d-143">Med hjälp av den här funktionen kan du på ett mer automatiserat sätt hantera policyer och förfrågningar för personalavdelningen och ta bort misstag samtidigt som du effektiviserar hanteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6754d-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="6754d-144">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="6754d-144">For more information, see:</span></span>

- [<span data-ttu-id="6754d-145">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="6754d-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="6754d-146">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="6754d-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="6754d-147">DMF-enheter (Data Management Framework) för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="6754d-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="6754d-148">Entiteter för hantering av förmåner släpps.</span><span class="sxs-lookup"><span data-stu-id="6754d-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="6754d-149">DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="6754d-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="6754d-150">En mall för hantering av förmåner kan också användas för att flytta data.</span><span class="sxs-lookup"><span data-stu-id="6754d-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="6754d-151">Mallen exporterar och importerar data på ett sekventiellt sätt för att respektera databeroenden.</span><span class="sxs-lookup"><span data-stu-id="6754d-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="6754d-152">Lägg till orsakskod för periodiserade avstängningar (1 juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="6754d-153">Orsakskoder har lagts till den periodiserade avstängningen.</span><span class="sxs-lookup"><span data-stu-id="6754d-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="6754d-154">Överför regler (1 juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="6754d-155">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="6754d-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="6754d-156">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="6754d-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="6754d-157">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="6754d-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="6754d-158">Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper (1 juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="6754d-159">I den här versionen kan HR skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="6754d-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="6754d-160">Obetald tjänstledighet kan vara en typ, men behöver inte vara det.</span><span class="sxs-lookup"><span data-stu-id="6754d-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="6754d-161">Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="6754d-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="6754d-162">DMF-enhet tillgänglig för periodiserade avstängningar (1 juni)</span><span class="sxs-lookup"><span data-stu-id="6754d-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="6754d-163">Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.</span><span class="sxs-lookup"><span data-stu-id="6754d-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="6754d-164">Se även</span><span class="sxs-lookup"><span data-stu-id="6754d-164">See also</span></span>

[<span data-ttu-id="6754d-165">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="6754d-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="6754d-166">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="6754d-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="6754d-167">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="6754d-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="6754d-168">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="6754d-168">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]