---
title: Nyheter och ändringar i Dynamics 365 Human Resources (18 februari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 18 februari 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e087095807f587536f2dad7e65fbc8beaa88878e
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128075"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="3be5c-103">Nyheter och ändringar i Dynamics 365 Human Resources (18 februari 2020)</span><span class="sxs-lookup"><span data-stu-id="3be5c-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3be5c-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3be5c-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="3be5c-105">Ändringarna tillämpas på versionsnummer 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="3be5c-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="3be5c-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="3be5c-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="3be5c-107">Plattform update 32</span><span class="sxs-lookup"><span data-stu-id="3be5c-107">Platform update 32</span></span> 

<span data-ttu-id="3be5c-108">Plattformsuppdateringen 32 finns nu tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3be5c-108">Platform update 32 is now available.</span></span> <span data-ttu-id="3be5c-109">Mer information finns i [Nyheter och ändringar i plattformsuppdatering 32 för Finance and Operations-appar (februari 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="3be5c-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="3be5c-110">Sökvärden sparas vid ändring av visningsalternativ i förenklat medarbetarformulär (383833)</span><span class="sxs-lookup"><span data-stu-id="3be5c-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="3be5c-111">Det nya formuläret **arbetare** kommer nu ihåg sökvärden när du ändrar visningsalternativen och tillämpar ändringar.</span><span class="sxs-lookup"><span data-stu-id="3be5c-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="3be5c-112">Sammanfattningspaneler för kompensationshantering i förhandsgranskningsfunktionen omdirigera till felformulär (401861)</span><span class="sxs-lookup"><span data-stu-id="3be5c-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="3be5c-113">Fasta och variabla kompensationshanteringspaneler visar nu korrekta poster i formuläret **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="3be5c-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="3be5c-114">Gäller endast förhandsgranskningsfunktionen för formulär för förenklad medarbetare.</span><span class="sxs-lookup"><span data-stu-id="3be5c-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="3be5c-115">Du kan aktivera den här förhandsgranskningsfunktionen i **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="3be5c-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="3be5c-116">Mer information finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="3be5c-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="3be5c-117">Tomt statusfält för vissa poster för ledighetsansökan i Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="3be5c-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="3be5c-118">Den här ändringen åtgärdar ett problem i Dataverse när fältet **status** i en ledighetsansökan anges till **granskning**.</span><span class="sxs-lookup"><span data-stu-id="3be5c-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="3be5c-119">Dataverse visar nu statusen.</span><span class="sxs-lookup"><span data-stu-id="3be5c-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="3be5c-120">Analys av kompetensluckor är endast möjlig för tilldelat jobb (411390)</span><span class="sxs-lookup"><span data-stu-id="3be5c-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="3be5c-121">Du kan nu utföra en analys av kompetensluckor på alla jobb som definierats i personal.</span><span class="sxs-lookup"><span data-stu-id="3be5c-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="3be5c-122">Systemvalutan synkroniseras inte från Dataverse till personal i nya miljöer (418011)</span><span class="sxs-lookup"><span data-stu-id="3be5c-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="3be5c-123">Systemvalutan i Dataverse kan nu synkronisera med personal.</span><span class="sxs-lookup"><span data-stu-id="3be5c-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="3be5c-124">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="3be5c-124">In preview</span></span>

- [<span data-ttu-id="3be5c-125">Funktioner för förhandsgranskning av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="3be5c-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="3be5c-126">Förhandsgranskningsfunktion för förmånshantering</span><span class="sxs-lookup"><span data-stu-id="3be5c-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="3be5c-127">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="3be5c-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="3be5c-128">Uppdaterad Dataverse-lösning</span><span class="sxs-lookup"><span data-stu-id="3be5c-128">Updated Dataverse solution</span></span>

<span data-ttu-id="3be5c-129">En ny Dataverse-lösning kommer snart att vara tillgänglig med följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="3be5c-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="3be5c-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3be5c-130">Description</span></span> | <span data-ttu-id="3be5c-131">Växel</span><span class="sxs-lookup"><span data-stu-id="3be5c-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="3be5c-132">**Jobb/befattning** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="3be5c-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="3be5c-133">**Kompensationsregion** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-133">**Compensation region** added</span></span></br><span data-ttu-id="3be5c-134">**Ekonomiska dimensioner** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="3be5c-135">**Arbetare** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="3be5c-135">**Worker** entity changes</span></span> | <span data-ttu-id="3be5c-136">**Namnordning** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-136">**Name sequence** added</span></span></br><span data-ttu-id="3be5c-137">**Arbetar hemifrån** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-137">**Works from home** added</span></span></br><span data-ttu-id="3be5c-138">**Språk** tillagt</span><span class="sxs-lookup"><span data-stu-id="3be5c-138">**Language** added</span></span></br><span data-ttu-id="3be5c-139">**Datum för tjänsteålder** tillagt</span><span class="sxs-lookup"><span data-stu-id="3be5c-139">**Seniority date** added</span></span></br><span data-ttu-id="3be5c-140">**Jubileumsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="3be5c-140">**Anniversary date** added</span></span></br><span data-ttu-id="3be5c-141">**Ursprungligt anställningsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="3be5c-141">**Original hire date** added</span></span> |
| <span data-ttu-id="3be5c-142">**Anställning** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="3be5c-142">**Employment** entity changes</span></span> | <span data-ttu-id="3be5c-143">**Ekonomiska dimensioner** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-143">**Financial dimensions** added</span></span></br><span data-ttu-id="3be5c-144">**Uppsägningsorsak** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-144">**Termination reason** added</span></span></br><span data-ttu-id="3be5c-145">**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</span><span class="sxs-lookup"><span data-stu-id="3be5c-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="3be5c-146">**Provanställningsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="3be5c-146">**Probation date** added</span></span> |
| <span data-ttu-id="3be5c-147">**Arbetaradress** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="3be5c-147">**Worker address** entity changes</span></span> | <span data-ttu-id="3be5c-148">**Gatuadress** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-148">**Street address** added</span></span></br><span data-ttu-id="3be5c-149">**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell</span><span class="sxs-lookup"><span data-stu-id="3be5c-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="3be5c-150">Inställningsenheter för ny variabelkompensation</span><span class="sxs-lookup"><span data-stu-id="3be5c-150">New variable compensation setup entities</span></span> | <span data-ttu-id="3be5c-151">**Typ av variabel kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="3be5c-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="3be5c-152">**Variabel kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="3be5c-152">**Compensation variable plan**</span></span></br><span data-ttu-id="3be5c-153">**Överlåtelseregler**</span><span class="sxs-lookup"><span data-stu-id="3be5c-153">**Vesting rules**</span></span></br><span data-ttu-id="3be5c-154">**Variabel kompensationsplannivå**</span><span class="sxs-lookup"><span data-stu-id="3be5c-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="3be5c-155">Ny enhet för **Arbetarkalender anställning**</span><span class="sxs-lookup"><span data-stu-id="3be5c-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="3be5c-156">**Enheten arbetskalender** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="3be5c-157">Ny enhet för **lönepositionsuppgift**</span><span class="sxs-lookup"><span data-stu-id="3be5c-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="3be5c-158">**Lönepositionsuppgift** tillagd</span><span class="sxs-lookup"><span data-stu-id="3be5c-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="3be5c-159">Ny enhet för **Rubrik**</span><span class="sxs-lookup"><span data-stu-id="3be5c-159">New **Title** entity</span></span> | <span data-ttu-id="3be5c-160">**Rubrik** tillagd.</span><span class="sxs-lookup"><span data-stu-id="3be5c-160">**Title** added.</span></span> <span data-ttu-id="3be5c-161">Den nya entiteten **Rubrik** kommer att inkluderas i synkroniseringsprocessen mellan personal och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3be5c-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="3be5c-162">Den kommer då inte från **Jobbefattning** eller **Jobb** enheter.</span><span class="sxs-lookup"><span data-stu-id="3be5c-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3be5c-163">Se även</span><span class="sxs-lookup"><span data-stu-id="3be5c-163">See also</span></span>

[<span data-ttu-id="3be5c-164">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="3be5c-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="3be5c-165">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="3be5c-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="3be5c-166">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="3be5c-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="3be5c-167">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="3be5c-167">Manage features</span></span>](hr-admin-manage-features.md)