---
title: Nyheter och ändringar i Dynamics 365 Talent (26 mars 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
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
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 17eae6c2aa2a1305b1d6f403c595c022f71da48f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529100"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-26-2019"></a><span data-ttu-id="2f232-103">Nyheter och ändringar i Dynamics 365 Talent (26 mars 2019)</span><span class="sxs-lookup"><span data-stu-id="2f232-103">What's new or changed in Dynamics 365 Talent (March 26, 2019)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2f232-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="2f232-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="2f232-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="2f232-105">Changes in Attract</span></span>

### <a name="enhancements-to-interview-scheduling"></a><span data-ttu-id="2f232-106">Förbättringar av tidsplanering av intervjuer</span><span class="sxs-lookup"><span data-stu-id="2f232-106">Enhancements to interview scheduling</span></span>
<span data-ttu-id="2f232-107">Följande förbättringar finns vid tidsplanering av intervjun.</span><span class="sxs-lookup"><span data-stu-id="2f232-107">The following enhancements are available in interview scheduling.</span></span>

- <span data-ttu-id="2f232-108">Rekryterare och anställande chefer kan nu manuellt utlösa en påminnelse för en intervjuare om att skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="2f232-108">Recruiters or hiring managers can now manually trigger a reminder for an interviewer to submit their feedback.</span></span> <span data-ttu-id="2f232-109">Associerade e-postmallen för påminnelsen kan också konfigureras.</span><span class="sxs-lookup"><span data-stu-id="2f232-109">The associated email template for the reminder is configurable as well.</span></span>
- <span data-ttu-id="2f232-110">Medan sammanfattningen av intervjun med kandidaten delas kan intervjuplaneraren välja att dölja namnen på intervjuarna och också välja att dölja rader från vyn för intervjusammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="2f232-110">While sharing the interview summary with the candidate, the interview scheduler can choose to hide the names of the interviewers and also choose to hide rows from the interview summary view.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="2f232-111">Ändringar i Onboard</span><span class="sxs-lookup"><span data-stu-id="2f232-111">Changes in Onboard</span></span>

### <a name="embedded-images-in-activities"></a><span data-ttu-id="2f232-112">Inbäddade bilder i aktiviteter</span><span class="sxs-lookup"><span data-stu-id="2f232-112">Embedded images in activities</span></span>
<span data-ttu-id="2f232-113">Du kan nu bädda in bilder direkt i aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="2f232-113">You can now embed images directly into activities.</span></span> <span data-ttu-id="2f232-114">Förutom att kopiera och klistra in bilder från webben kan du överföra bilder från det lokala filsystemet.</span><span class="sxs-lookup"><span data-stu-id="2f232-114">In addition to being able to copy and paste images from the web, you can upload images from your local file system.</span></span> <span data-ttu-id="2f232-115">Storleken på aktiviteten är begränsad till 1 MB.</span><span class="sxs-lookup"><span data-stu-id="2f232-115">The size of the activity is limited to 1 MB.</span></span> <span data-ttu-id="2f232-116">Om bilden är för stor, ändra storlek och försök överföra igen.</span><span class="sxs-lookup"><span data-stu-id="2f232-116">If the image is too large, resize and try to upload again.</span></span>

<span data-ttu-id="2f232-117">[![Mappning](./media/embedimages.png)](./media/embedimages.png)</span><span class="sxs-lookup"><span data-stu-id="2f232-117">[![Mapping](./media/embedimages.png)](./media/embedimages.png)</span></span>

<span data-ttu-id="2f232-118">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="2f232-118">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="2f232-119">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="2f232-119">Changes in Core HR</span></span>
<span data-ttu-id="2f232-120">**Skapa 8.1.2210**</span><span class="sxs-lookup"><span data-stu-id="2f232-120">**Build 8.1.2210**</span></span>

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a><span data-ttu-id="2f232-121">Anpassat fältstöd är tillgängligt för utvalda entiteter i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2f232-121">Custom field support available for select entities in Common Data Service</span></span> 

<span data-ttu-id="2f232-122">Följande Common Data Service-entiteter stöder nu kundfälten som skapats i Talent:</span><span class="sxs-lookup"><span data-stu-id="2f232-122">The following Common Data Service entities now support customer fields created in Talent:</span></span>

- <span data-ttu-id="2f232-123">Arbetare</span><span class="sxs-lookup"><span data-stu-id="2f232-123">Worker</span></span>
- <span data-ttu-id="2f232-124">Etniskt ursprung</span><span class="sxs-lookup"><span data-stu-id="2f232-124">Ethnic origin</span></span>
- <span data-ttu-id="2f232-125">Veteranstatus</span><span class="sxs-lookup"><span data-stu-id="2f232-125">Veteran status</span></span>
- <span data-ttu-id="2f232-126">Språkkod</span><span class="sxs-lookup"><span data-stu-id="2f232-126">Language code</span></span>
- <span data-ttu-id="2f232-127">Befattning</span><span class="sxs-lookup"><span data-stu-id="2f232-127">Job</span></span>
- <span data-ttu-id="2f232-128">Jobbtyp</span><span class="sxs-lookup"><span data-stu-id="2f232-128">Job type</span></span>
- <span data-ttu-id="2f232-129">Jobbfunktion</span><span class="sxs-lookup"><span data-stu-id="2f232-129">Job function</span></span>
- <span data-ttu-id="2f232-130">Befattning</span><span class="sxs-lookup"><span data-stu-id="2f232-130">Position</span></span>
- <span data-ttu-id="2f232-131">Befattningstyp</span><span class="sxs-lookup"><span data-stu-id="2f232-131">Position type</span></span>
 
### <a name="employment-history-not-displayed-chronologically"></a><span data-ttu-id="2f232-132">Anställningshistorik visas inte kronologiskt</span><span class="sxs-lookup"><span data-stu-id="2f232-132">Employment history not displayed chronologically</span></span>
<span data-ttu-id="2f232-133">Förutom denna ändring visar nu anställningshistoriksidan medarbetarposter i kronologisk ordning, oberoende av företaget.</span><span class="sxs-lookup"><span data-stu-id="2f232-133">With this change, the employment history page now displays employment records chronologically, independent of company.</span></span> <span data-ttu-id="2f232-134">Du kan också använda sorteringsalternativ för att sortera efter företag.</span><span class="sxs-lookup"><span data-stu-id="2f232-134">You can also use sorting options to sort by company.</span></span>

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a><span data-ttu-id="2f232-135">Planer för fast kompensation visas inte vid begränsning av användare av företag i säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2f232-135">Fixed compensation plans don't appear when restricting user by company in security.</span></span>
<span data-ttu-id="2f232-136">I den här versionen visas nu fasta kompensationsplaner vid begränsning av användare av företag i säkerhet.</span><span class="sxs-lookup"><span data-stu-id="2f232-136">In this release, fixed compensation plans now appear when restricting users by company in security.</span></span> <span data-ttu-id="2f232-137">Alla säkerhetsinställningar kommer att hedras och fasta planer kommer att visas för de företag som användaren har behörigheter att få åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="2f232-137">All security settings will be honored, and fixed plans will appear for those companies the user has permissions to access.</span></span> 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a><span data-ttu-id="2f232-138">Kan inte ta bort jobbposter med Öppna i Excel-alternativ i Talent</span><span class="sxs-lookup"><span data-stu-id="2f232-138">Can't delete Job records using Open in Excel option in Talent</span></span>
<span data-ttu-id="2f232-139">Med den här versionen kan du nu ta bort jobbposter med alternativet **öppna i Excel** i Talent.</span><span class="sxs-lookup"><span data-stu-id="2f232-139">With this release, you can now remove job records by using the **Open in Excel** option in Talent.</span></span>

### <a name="upgrade-to-common-data-service"></a><span data-ttu-id="2f232-140">Uppgradera till Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2f232-140">Upgrade to Common Data Service</span></span>
<span data-ttu-id="2f232-141">Tidsgränser för uppgradering till Common Data Service för appar närmar sig snabbt.</span><span class="sxs-lookup"><span data-stu-id="2f232-141">Deadlines to upgrade to Common Data Service are quickly approaching.</span></span> <span data-ttu-id="2f232-142">Logga in på Power Apps-administrationscenter för att avgöra om databasen måste uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="2f232-142">Sign in to the Power Apps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="2f232-143">Mer information om deadlines och nödvändiga instruktioner för uppgradering finns i [uppgradera till Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="2f232-143">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="in-preview"></a><span data-ttu-id="2f232-144">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="2f232-144">In preview</span></span>

<span data-ttu-id="2f232-145">För information om hur du aktiverar funktioner för förhandsgranskning finns i [Få åtkomst till förhandsfunktioner i Microsoft Dynamics 365 Talent](./access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="2f232-145">For information about enabling preview features, see [Access preview features in Microsoft Dynamics 365 Talent](./access-preview-feature.md).</span></span>

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a><span data-ttu-id="2f232-146">Tillåt att orsakskoder anges på tjänstledighetstyper</span><span class="sxs-lookup"><span data-stu-id="2f232-146">Allow reason codes to be specified on leave types</span></span>
<span data-ttu-id="2f232-147">Organisationer kanske behöver ytterligare information relaterad till ledighetsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="2f232-147">Organizations might need additional information related to time off requests.</span></span> <span data-ttu-id="2f232-148">Om du vill ha den här informationen måste medarbetare inkludera en orsakskod på deras ledighetsbegäran.</span><span class="sxs-lookup"><span data-stu-id="2f232-148">To get this information, employees need to include a reason code on their time off requests.</span></span> <span data-ttu-id="2f232-149">Med den här versionen kan du kan nu ange orsakskoder som är associerade med en viss ledighetstyp och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.</span><span class="sxs-lookup"><span data-stu-id="2f232-149">With this release, you can now specify the reason codes associated with a given leave type and enable employees to select a reason code on their time off requests.</span></span>

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a><span data-ttu-id="2f232-150">Konfigurera orsakskoder för att köras när du skickar tjänstledighetstyper för vissa ledighetstyper</span><span class="sxs-lookup"><span data-stu-id="2f232-150">Configure reason codes to be required when submitting time off for certain leave types</span></span>
<span data-ttu-id="2f232-151">Organisationer kan kräva att orsakskoder anges för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar.</span><span class="sxs-lookup"><span data-stu-id="2f232-151">Organizations might require reason codes to be set on specific leave types when employees submit time off.</span></span> <span data-ttu-id="2f232-152">Detta kan krävas utifrån lagstadgat krav i deras land/region eller en företagspolicy.</span><span class="sxs-lookup"><span data-stu-id="2f232-152">This may be required based on a regulatory requirement in their country/region or a company policy.</span></span> <span data-ttu-id="2f232-153">Den här versionen ger möjlighet för personalavdelningen att ange vilka tjänstledighetstyper som kräver en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="2f232-153">This release provides the ability for HR to specify which leave types require a reason code.</span></span> <span data-ttu-id="2f232-154">Detta kommer att aktiveras när medarbetare skickar begäranden där ledighet kräver en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="2f232-154">This will be enforced when employees submit time off requests where the leave requires a reason code.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="2f232-155">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="2f232-155">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="2f232-156">Avancerad kompensationssäkerhet (fasta och rörliga)</span><span class="sxs-lookup"><span data-stu-id="2f232-156">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="2f232-157">I många organisationer kan kompensations- och förmånsansvariga endast ha tillgång till vissa kompensationsposter.</span><span class="sxs-lookup"><span data-stu-id="2f232-157">In many organizations, compensation and benefits managers might only have access to certain compensation records.</span></span> <span data-ttu-id="2f232-158">Posterna kan vara för chefer eller nationella medarbetare.</span><span class="sxs-lookup"><span data-stu-id="2f232-158">These could be for executives or regional employees.</span></span> <span data-ttu-id="2f232-159">Med den här ändringen kan personalavdelningen hantera och underhålla kompensationsplaner för olika medarbetargrupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f232-159">With this change, HR can manage and maintain the compensation plans for different employee groups in the organization.</span></span> <span data-ttu-id="2f232-160">Du ska tilldela säkerhetsroller till fasta och variabla planer som bestämmer åtkomsten till planer och medarbetardata relaterade till planerna, till exempel lön eller bonusposter.</span><span class="sxs-lookup"><span data-stu-id="2f232-160">You can assign security roles to fixed and variable plans that determine access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="2f232-161">Endast roller med åtkomst kan bearbeta kompensation för dessa anställda.</span><span class="sxs-lookup"><span data-stu-id="2f232-161">Only the roles granted with access can process compensation for these employees.</span></span>

###  <a name="email-support-for-alerts"></a><span data-ttu-id="2f232-162">E-support för notifieringar</span><span class="sxs-lookup"><span data-stu-id="2f232-162">Email support for alerts</span></span>
<span data-ttu-id="2f232-163">Med plattformsuppdatering 25 för Finance and Operations kan användare skapa notifieringsregler som automatiskt skickar ut e-postmeddelanden till kontakter när de utlöses av en händelse.</span><span class="sxs-lookup"><span data-stu-id="2f232-163">With Platform update 25 for Finance and Operations, users can create alert rules that automatically dispatch email notifications to contacts when triggered by an event.</span></span> 

### <a name="duplicate-employee-checks-user-interface-changes"></a><span data-ttu-id="2f232-164">Dubblettkontroll av medarbetare: användargränssnittsändringar</span><span class="sxs-lookup"><span data-stu-id="2f232-164">Duplicate employee checks: User interface changes</span></span>
<span data-ttu-id="2f232-165">Med denna ändring detekteras dubbletter när du anger namnfält och status visar antalet dubbletter som hittades.</span><span class="sxs-lookup"><span data-stu-id="2f232-165">With this change, duplicates are detected as you enter name fields, and a status displays the number of duplicates found.</span></span> <span data-ttu-id="2f232-166">Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna.</span><span class="sxs-lookup"><span data-stu-id="2f232-166">You can select the provided link to open a new page to evaluate whether to use the detected match.</span></span> <span data-ttu-id="2f232-167">Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.</span><span class="sxs-lookup"><span data-stu-id="2f232-167">To avoid interrupting data entry, the duplicates form doesn't open automatically.</span></span>
