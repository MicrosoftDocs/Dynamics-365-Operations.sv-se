---
title: Nyheter och ändringar i Dynamics 365 Human Resources (23 juli 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 23 juli 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/23/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5e10d6d1dedfc251a1a00110b50c9096314d75b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127531"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="a00fe-103">Nyheter och ändringar i Dynamics 365 Human Resources (23 juli 2020)</span><span class="sxs-lookup"><span data-stu-id="a00fe-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a00fe-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a00fe-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a00fe-105">Ändringarna tillämpas på versionsnummer 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="a00fe-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="a00fe-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="a00fe-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="a00fe-107">Att ta bort ekonomiska dimensioner för en position fungerar inte som förväntat (445476)</span><span class="sxs-lookup"><span data-stu-id="a00fe-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="a00fe-108">Om du tar bort dimensioner från en befattning tas nu samma positioner bort från Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a00fe-108">Removing dimensions from a position now removes those same positions from Dataverse.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="a00fe-109">Positioner som inte är i hierarkin visa inaktiva positioner (397257)</span><span class="sxs-lookup"><span data-stu-id="a00fe-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="a00fe-110">Positioner som är inaktiva (har en förfallen varaktighet), visas inte längre i positionshierarkin som **positioner som inte finns i hierarkin**.</span><span class="sxs-lookup"><span data-stu-id="a00fe-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="a00fe-111">Valideringen sker mellan LeaveEnrollmentEntity och HcmWorkerEntity i import av datahanteringsramverk (DMF) orsakar långsam databelastning (442324)</span><span class="sxs-lookup"><span data-stu-id="a00fe-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="a00fe-112">Ändringar i den här versionen ökar prestanda för **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="a00fe-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="a00fe-113">Det går inte att personanpassa i organisationsadministrationen (447490)</span><span class="sxs-lookup"><span data-stu-id="a00fe-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="a00fe-114">Med den här ändringen kan du nu anpassa länkarna i **organisationsadministrationen**.</span><span class="sxs-lookup"><span data-stu-id="a00fe-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a00fe-115">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="a00fe-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="a00fe-116">Obligatoriska fält</span><span class="sxs-lookup"><span data-stu-id="a00fe-116">Mandatory fields</span></span> 

<span data-ttu-id="a00fe-117">Du kan nu göra fält obligatoriska genom att använda anpassningsfunktioner för personal.</span><span class="sxs-lookup"><span data-stu-id="a00fe-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="a00fe-118">Den här funktionen kräver **sparade vyer**.</span><span class="sxs-lookup"><span data-stu-id="a00fe-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="a00fe-119">Personalapp i Teams</span><span class="sxs-lookup"><span data-stu-id="a00fe-119">Human Resources application in Teams</span></span>

<span data-ttu-id="a00fe-120">Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a00fe-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a00fe-121">De kan samverka med en bot för att skapa tjänstledighetsansökan.</span><span class="sxs-lookup"><span data-stu-id="a00fe-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a00fe-122">Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="a00fe-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="a00fe-123">DMF-enheter (Data Management Framework) för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="a00fe-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="a00fe-124">Entiteter för hantering av förmåner släpps.</span><span class="sxs-lookup"><span data-stu-id="a00fe-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="a00fe-125">DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner.</span><span class="sxs-lookup"><span data-stu-id="a00fe-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="a00fe-126">En mall för hantering av förmåner kan användas för att flytta data.</span><span class="sxs-lookup"><span data-stu-id="a00fe-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="a00fe-127">Mallen exporterar och importerar data sekventiellt för att respektera databeroenden.</span><span class="sxs-lookup"><span data-stu-id="a00fe-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="a00fe-128">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="a00fe-128">Buy and sell leave</span></span> 

<span data-ttu-id="a00fe-129">Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="a00fe-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="a00fe-130">Den här processen hanteras ofta manuellt.</span><span class="sxs-lookup"><span data-stu-id="a00fe-130">This process is often managed manually.</span></span> <span data-ttu-id="a00fe-131">Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen.</span><span class="sxs-lookup"><span data-stu-id="a00fe-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="a00fe-132">Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag.</span><span class="sxs-lookup"><span data-stu-id="a00fe-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="a00fe-133">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="a00fe-133">For more information, see:</span></span>

- [<span data-ttu-id="a00fe-134">Hantera principer för köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="a00fe-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="a00fe-135">Köpa och sälja tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="a00fe-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="a00fe-136">Lämna periodisering för ett enskilt företag eller en plan</span><span class="sxs-lookup"><span data-stu-id="a00fe-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="a00fe-137">Kunder kan bearbeta periodiseringar för ett enskilt företag eller en enskild plan för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="a00fe-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="a00fe-138">Denna möjlighet ger klarhet i den periodiserade processen för kunder med olika tjänstledighetsår eller principer för periodisering av tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="a00fe-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="a00fe-139">Mer information finns i [tjänstledighet per företag eller per tjänstledighetsplan](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="a00fe-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="a00fe-140">Lägg till bifogade filer i ledighetsansökningar</span><span class="sxs-lookup"><span data-stu-id="a00fe-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="a00fe-141">Möjligheten att lägga till bilagor till godkända ansökan om tjänstledighet är viktigt i den aktuella COVID-19 miljön.</span><span class="sxs-lookup"><span data-stu-id="a00fe-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="a00fe-142">Medarbetarna kan nu lägga till dessa bilagor.</span><span class="sxs-lookup"><span data-stu-id="a00fe-142">Employees can now add these attachments.</span></span> <span data-ttu-id="a00fe-143">De har också mer inblick i hur uppdateringar görs för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="a00fe-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="a00fe-144">Mer information finns i [lägga till en bilaga till en befintlig begäran](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="a00fe-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="a00fe-145">Lägg till orsakskod för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="a00fe-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="a00fe-146">Orsakskoder har lagts till den periodiserade avstängningen.</span><span class="sxs-lookup"><span data-stu-id="a00fe-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a00fe-147">Överför regler</span><span class="sxs-lookup"><span data-stu-id="a00fe-147">Carry forward rules</span></span> 

<span data-ttu-id="a00fe-148">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="a00fe-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a00fe-149">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="a00fe-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a00fe-150">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a00fe-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="a00fe-151">Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper</span><span class="sxs-lookup"><span data-stu-id="a00fe-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="a00fe-152">Du kan skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="a00fe-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a00fe-153">Obetald tjänstledighet kan vara en typ, men behöver inte vara det.</span><span class="sxs-lookup"><span data-stu-id="a00fe-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a00fe-154">Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="a00fe-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="a00fe-155">DMF-enhet tillgänglig för periodiserade avstängningar</span><span class="sxs-lookup"><span data-stu-id="a00fe-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="a00fe-156">Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.</span><span class="sxs-lookup"><span data-stu-id="a00fe-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a00fe-157">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="a00fe-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="a00fe-158">Entiteter för checklista inkluderade i Dataverse</span><span class="sxs-lookup"><span data-stu-id="a00fe-158">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="a00fe-159">Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a00fe-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="a00fe-160">Plattformsändringar</span><span class="sxs-lookup"><span data-stu-id="a00fe-160">Platform changes</span></span>

<span data-ttu-id="a00fe-161">Plattformsuppdatering 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="a00fe-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="a00fe-162">Se även</span><span class="sxs-lookup"><span data-stu-id="a00fe-162">See also</span></span>

[<span data-ttu-id="a00fe-163">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="a00fe-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a00fe-164">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="a00fe-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a00fe-165">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="a00fe-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a00fe-166">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="a00fe-166">Manage features</span></span>](hr-admin-manage-features.md)
