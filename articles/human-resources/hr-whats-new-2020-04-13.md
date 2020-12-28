---
title: Vad är nytt och ändrat i Dynamics 365 Human Resources (13 april 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 13 april 2020.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a7ea8348cfe1c66d6d0cfa39b46c8e69111fe185
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528531"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="21bdc-103">Vad är nytt och ändrat i Dynamics 365 Human Resources (13 april 2020)</span><span class="sxs-lookup"><span data-stu-id="21bdc-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="21bdc-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="21bdc-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="21bdc-105">Ändringarna tillämpas på versionsnummer 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="21bdc-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="21bdc-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="21bdc-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="21bdc-107">Ny produktionsfrisläppningstakt</span><span class="sxs-lookup"><span data-stu-id="21bdc-107">New production release cadence</span></span>

<span data-ttu-id="21bdc-108">Med denna veckas frisläppning kommer frisläppningstakten för personal att flyttas från en uppdatering varje vecka till en uppdatering varannan vecka.</span><span class="sxs-lookup"><span data-stu-id="21bdc-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="21bdc-109">För att säkerställa att du har en säker driftsättningsmetod och upprätthåller höga normer för stabilitet och tillförlitlighet i tjänsten, är processen för att distribuera tjänstuppdateringar till alla regioner en två veckors lansering.</span><span class="sxs-lookup"><span data-stu-id="21bdc-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="21bdc-110">Ytterligare tester och bildskärmar är på plats för att kontrollera att distributionen lyckades vid varje steg av processen.</span><span class="sxs-lookup"><span data-stu-id="21bdc-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="21bdc-111">Mer information om frisläppningstakt finns i [Uppdatera process](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="21bdc-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="21bdc-112">Fält för avrundningsprecision går inte att redigera efter att ha angett en avrundningstyp (435616)</span><span class="sxs-lookup"><span data-stu-id="21bdc-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="21bdc-113">Med den här ändringen är fältet **avrundningsprecision** nu tillgängligt när du har uppdaterat fältet **avrundningstyp**.</span><span class="sxs-lookup"><span data-stu-id="21bdc-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="21bdc-114">Det går inte att redigera lämna slutdatum för anmälan när tjänstledighetsplanen inte har periodiseringstransaktioner (413628)</span><span class="sxs-lookup"><span data-stu-id="21bdc-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="21bdc-115">Du kan nu redigera slutdatum för anmälan utan att ta emot felet "Fältet för datumbasen för periodiseringen måste fyllas i."</span><span class="sxs-lookup"><span data-stu-id="21bdc-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a><span data-ttu-id="21bdc-116">Arbetsenheten synkroniseras inte till Common Data Service (430834)</span><span class="sxs-lookup"><span data-stu-id="21bdc-116">Employment entity doesn't sync to Common Data Service (430834)</span></span>

<span data-ttu-id="21bdc-117">Den här ändringen åtgärdar ett problem där anställningsdata inte synkroniseras till Common Data Service efter tillägg av ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="21bdc-117">This change corrects an issue where the employment data wasn't syncing to Common Data Service after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="21bdc-118">Ta bort flera överordnade för entiteten tidsintervall för arbetskalender (431775)</span><span class="sxs-lookup"><span data-stu-id="21bdc-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="21bdc-119">Denna ändring tar bort flera överordnade för entiteten **Tidsintervall till arbetskalendern**.</span><span class="sxs-lookup"><span data-stu-id="21bdc-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="21bdc-120">Filtret med CAST-funktionen fungerar inte på OData anropar entiteten befattningstilldelning för arbetare (431699)</span><span class="sxs-lookup"><span data-stu-id="21bdc-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="21bdc-121">I den här uppdateringen ingår en ändring som tillåter filtrering med funktionen CAST i OData för entiteten **Befattningstilldelning för arbetare**.</span><span class="sxs-lookup"><span data-stu-id="21bdc-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="21bdc-122">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="21bdc-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="21bdc-123">Lämna uppehåll</span><span class="sxs-lookup"><span data-stu-id="21bdc-123">Leave suspension</span></span>

<span data-ttu-id="21bdc-124">Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="21bdc-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="21bdc-125">Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna.</span><span class="sxs-lookup"><span data-stu-id="21bdc-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="21bdc-126">Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo.</span><span class="sxs-lookup"><span data-stu-id="21bdc-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="21bdc-127">Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="21bdc-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="21bdc-128">Överför regler</span><span class="sxs-lookup"><span data-stu-id="21bdc-128">Carry forward rules</span></span>

<span data-ttu-id="21bdc-129">Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs.</span><span class="sxs-lookup"><span data-stu-id="21bdc-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="21bdc-130">Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="21bdc-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="21bdc-131">Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="21bdc-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="21bdc-132">Kända problem</span><span class="sxs-lookup"><span data-stu-id="21bdc-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="21bdc-133">Entiteten anställningsinformation</span><span class="sxs-lookup"><span data-stu-id="21bdc-133">Employment Details entity</span></span>

<span data-ttu-id="21bdc-134">Entiteten **anställningsinformation** har uppdaterats med följande fält:</span><span class="sxs-lookup"><span data-stu-id="21bdc-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="21bdc-135">**PayFrequency**</span><span class="sxs-lookup"><span data-stu-id="21bdc-135">**PayFrequency**</span></span>
- <span data-ttu-id="21bdc-136">**Anställningskategori-ID**</span><span class="sxs-lookup"><span data-stu-id="21bdc-136">**Employment Category ID**</span></span>
- <span data-ttu-id="21bdc-137">**Anställningstyp**</span><span class="sxs-lookup"><span data-stu-id="21bdc-137">**Employment Type**</span></span>
- <span data-ttu-id="21bdc-138">**EmploymentType-ID**</span><span class="sxs-lookup"><span data-stu-id="21bdc-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="21bdc-139">**Status för anställningsförmån**</span><span class="sxs-lookup"><span data-stu-id="21bdc-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="21bdc-140">Inställningsdata för dessa fält är beroende av att hanteringen av förmåner aktiveras på arbetsytan för **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="21bdc-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="21bdc-141">Fyll inte i eller uppdatera fälten i entiteten **anställningsinformation** eftersom det resulterar i fel under importen.</span><span class="sxs-lookup"><span data-stu-id="21bdc-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="21bdc-142">SharePoint förhandsgranskning fungerar inte i vissa miljöer</span><span class="sxs-lookup"><span data-stu-id="21bdc-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="21bdc-143">Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:</span><span class="sxs-lookup"><span data-stu-id="21bdc-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="21bdc-144">Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten.</span><span class="sxs-lookup"><span data-stu-id="21bdc-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="21bdc-145">Du kan visa den här informationen på sidan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="21bdc-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="21bdc-146">Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData.</span><span class="sxs-lookup"><span data-stu-id="21bdc-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="21bdc-147">Standard är att e-postadressen inte finns i Excel-designen.</span><span class="sxs-lookup"><span data-stu-id="21bdc-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="21bdc-148">Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera.</span><span class="sxs-lookup"><span data-stu-id="21bdc-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="21bdc-149">När du är klar med dessa steg kan du uppdatera administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="21bdc-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="21bdc-150">När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="21bdc-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="21bdc-151">Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.</span><span class="sxs-lookup"><span data-stu-id="21bdc-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="21bdc-152">Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="21bdc-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="21bdc-153">Se även</span><span class="sxs-lookup"><span data-stu-id="21bdc-153">See also</span></span>

[<span data-ttu-id="21bdc-154">Nyheter och ändringar i Human Resources</span><span class="sxs-lookup"><span data-stu-id="21bdc-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="21bdc-155">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="21bdc-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="21bdc-156">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="21bdc-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="21bdc-157">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="21bdc-157">Manage features</span></span>](hr-admin-manage-features.md)