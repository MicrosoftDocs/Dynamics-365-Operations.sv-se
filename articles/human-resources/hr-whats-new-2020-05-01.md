---
title: Nyheter och ändringar i Dynamics 365 Human Resources (1 maj 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 1 maj 2020.
author: andreabichsel
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1c97d0e332cb81391ec3095fcb5d4d42a0d6bff
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891995"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a><span data-ttu-id="50506-103">Nyheter och ändringar i Dynamics 365 Human Resources (1 maj 2020)</span><span class="sxs-lookup"><span data-stu-id="50506-103">What's new or changed in Dynamics 365 Human Resources (May 1, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="50506-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="50506-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="50506-105">Ändringarna tillämpas på versionsnummer 8.1.3196.</span><span class="sxs-lookup"><span data-stu-id="50506-105">Changes apply to build number 8.1.3196.</span></span> <span data-ttu-id="50506-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="50506-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a><span data-ttu-id="50506-107">Nya prestationshanteringsenheter finns i datahanteringsramverk (DMF)</span><span class="sxs-lookup"><span data-stu-id="50506-107">New Performance Management entities available in Data Management Framework (DMF)</span></span>

<span data-ttu-id="50506-108">Följande entiteter är nu tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="50506-108">The following entities are now available.</span></span> <span data-ttu-id="50506-109">Om dessa entiteter inte visas i listan entiteter använder du alternativet **uppdatera entiteter** i **Ramverksparametrar > Enhetsinställningar > Uppdatera enhetslistan**.</span><span class="sxs-lookup"><span data-stu-id="50506-109">If you don't see these entities listed in the entities list, use the **Refresh entities** option in **Framework Parameters > Entity settings > Refresh entity list**.</span></span>

- <span data-ttu-id="50506-110">**Diskussionskompetens**</span><span class="sxs-lookup"><span data-stu-id="50506-110">**Discussion Competency**</span></span>
- <span data-ttu-id="50506-111">**Diskussionsmål**</span><span class="sxs-lookup"><span data-stu-id="50506-111">**Discussion Goals**</span></span>
- <span data-ttu-id="50506-112">**Diskussionsmätning**</span><span class="sxs-lookup"><span data-stu-id="50506-112">**Discussion Measurement**</span></span>
- <span data-ttu-id="50506-113">**Diskussionsämne**</span><span class="sxs-lookup"><span data-stu-id="50506-113">**Discussion Topic**</span></span>
- <span data-ttu-id="50506-114">**Prestationsjournal**</span><span class="sxs-lookup"><span data-stu-id="50506-114">**Performance Journal**</span></span>
- <span data-ttu-id="50506-115">**Mått**</span><span class="sxs-lookup"><span data-stu-id="50506-115">**Measurement**</span></span>
- <span data-ttu-id="50506-116">**Målmätning**</span><span class="sxs-lookup"><span data-stu-id="50506-116">**Goal Measurement**</span></span>

<span data-ttu-id="50506-117">Dessutom har **Totalpoäng** och **Genomsnittspoäng** lagts till i **Diskussions**-enheten.</span><span class="sxs-lookup"><span data-stu-id="50506-117">In addition, **Total score** and **Average score** were added to the **Discussion** entity.</span></span>

## <a name="increase-length-of-leave-request-comments-275641"></a><span data-ttu-id="50506-118">Öka längden på tjänstledighetskommentarer (275641)</span><span class="sxs-lookup"><span data-stu-id="50506-118">Increase length of leave request comments (275641)</span></span>

<span data-ttu-id="50506-119">Kommentarer om tjänstledighet får nu fler än 100 tecken.</span><span class="sxs-lookup"><span data-stu-id="50506-119">Comments on leave requests now allow more than 100 characters.</span></span>

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a><span data-ttu-id="50506-120">Slutgiltiga kommentarer till recensioner visas inte när chefen eller medarbetaren är inloggad i ett annat företag (431688)</span><span class="sxs-lookup"><span data-stu-id="50506-120">Final comments on reviews don't appear when the manager or employee is signed into a different company (431688)</span></span>

<span data-ttu-id="50506-121">Alla kommentarer visas nu när granskningarna visas.</span><span class="sxs-lookup"><span data-stu-id="50506-121">All comments will now appear when viewing reviews.</span></span>

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a><span data-ttu-id="50506-122">Användardefinierade länkar stöds inte i nytt arbetarformulär (390374)</span><span class="sxs-lookup"><span data-stu-id="50506-122">User-defined links aren't supported on new Worker form (390374)</span></span>

<span data-ttu-id="50506-123">Användardefinierade länkar är nu aktiverade i formuläret för strömlinjeformad **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="50506-123">User-defined links are now enabled on the streamlined **Worker** form.</span></span>

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a><span data-ttu-id="50506-124">HcmRatingLevelEntity orsakar OData API-krasch (439476)</span><span class="sxs-lookup"><span data-stu-id="50506-124">HcmRatingLevelEntity causes OData API crash (439476)</span></span>

<span data-ttu-id="50506-125">Den här ändringen korrigerar API-kraschen.</span><span class="sxs-lookup"><span data-stu-id="50506-125">This change corrects the API crash.</span></span> <span data-ttu-id="50506-126">Ett dubblettnamn orsakade det här felet.</span><span class="sxs-lookup"><span data-stu-id="50506-126">A duplicate name cased this error.</span></span>

## <a name="in-preview"></a><span data-ttu-id="50506-127">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="50506-127">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="50506-128">Lämna uppehåll</span><span class="sxs-lookup"><span data-stu-id="50506-128">Leave suspension</span></span>

<span data-ttu-id="50506-129">Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="50506-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="50506-130">Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna.</span><span class="sxs-lookup"><span data-stu-id="50506-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="50506-131">Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo.</span><span class="sxs-lookup"><span data-stu-id="50506-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="50506-132">Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="50506-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="50506-133">Uppdatera användarupplevelsen att anger att periodiseringen är pausad (429550)</span><span class="sxs-lookup"><span data-stu-id="50506-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="50506-134">Användarupplevelsen anger nu att periodiseringen har avbrutits för en plan.</span><span class="sxs-lookup"><span data-stu-id="50506-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="50506-135">Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper (272447)</span><span class="sxs-lookup"><span data-stu-id="50506-135">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="50506-136">I den här versionen kan HR skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet.</span><span class="sxs-lookup"><span data-stu-id="50506-136">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="50506-137">Obetald tjänstledighet kan vara en typ, men behöver inte vara det.</span><span class="sxs-lookup"><span data-stu-id="50506-137">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="50506-138">Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.</span><span class="sxs-lookup"><span data-stu-id="50506-138">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="50506-139">DMF-enhet tillgänglig för periodiserade avstängningar (429549)</span><span class="sxs-lookup"><span data-stu-id="50506-139">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="50506-140">Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.</span><span class="sxs-lookup"><span data-stu-id="50506-140">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="50506-141">Lägg till orsakskod för periodiserade avstängningar (429547)</span><span class="sxs-lookup"><span data-stu-id="50506-141">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="50506-142">Orsakskoder har lagts till den periodiserade avstängningen.</span><span class="sxs-lookup"><span data-stu-id="50506-142">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="50506-143">Påbörja övergång från Personal-parametrar till tjänstledighets- och frånvaroparametrar</span><span class="sxs-lookup"><span data-stu-id="50506-143">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="50506-144">Den här versionen börjar kombinera Personal-parametrar med parametrar för tjänstledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="50506-144">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="50506-145">Överför regler</span><span class="sxs-lookup"><span data-stu-id="50506-145">Carry forward rules</span></span>

<span data-ttu-id="50506-146">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="50506-146">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="50506-147">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="50506-147">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="50506-148">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="50506-148">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="50506-149">Kända problem</span><span class="sxs-lookup"><span data-stu-id="50506-149">Known issues</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="50506-150">SharePoint förhandsgranskning fungerar inte i vissa miljöer</span><span class="sxs-lookup"><span data-stu-id="50506-150">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="50506-151">Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:</span><span class="sxs-lookup"><span data-stu-id="50506-151">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="50506-152">Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten.</span><span class="sxs-lookup"><span data-stu-id="50506-152">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="50506-153">Du kan visa den här informationen på sidan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="50506-153">You can view this information in the **User** page.</span></span> <span data-ttu-id="50506-154">Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData.</span><span class="sxs-lookup"><span data-stu-id="50506-154">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="50506-155">Standard är att e-postadressen inte finns i Excel-designen.</span><span class="sxs-lookup"><span data-stu-id="50506-155">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="50506-156">Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera.</span><span class="sxs-lookup"><span data-stu-id="50506-156">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="50506-157">När du är klar med dessa steg kan du uppdatera administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="50506-157">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="50506-158">När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="50506-158">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="50506-159">Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.</span><span class="sxs-lookup"><span data-stu-id="50506-159">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="50506-160">Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="50506-160">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="50506-161">Se även</span><span class="sxs-lookup"><span data-stu-id="50506-161">See also</span></span>

[<span data-ttu-id="50506-162">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="50506-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="50506-163">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="50506-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="50506-164">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="50506-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="50506-165">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="50506-165">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]