---
title: Nyheter och ändringar i Dynamics 365 Human Resources (25 februari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 25 februari 2020.
author: andreabichsel
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d9ff9b524a5812bd309fc33d6aa4ba4a92d687b
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051195"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="68d41-103">Nyheter och ändringar i Dynamics 365 Human Resources (25 februari 2020)</span><span class="sxs-lookup"><span data-stu-id="68d41-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="68d41-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68d41-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="68d41-105">Ändringarna tillämpas på versionsnummer 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="68d41-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="68d41-106">Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.</span><span class="sxs-lookup"><span data-stu-id="68d41-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="68d41-107">Aktivera hantering av ärendehantering och DMF-entiteten (Data Management Framework) (414754)</span><span class="sxs-lookup"><span data-stu-id="68d41-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="68d41-108">Den här förhandsgranskningsfunktionen möjliggör ytterligare navigering till ärenden som hanteras av ärendet.</span><span class="sxs-lookup"><span data-stu-id="68d41-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="68d41-109">Du kan aktivera den här förhandsgranskningsfunktionen i arbetsytan **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="68d41-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="68d41-110">Dessa menyalternativ visas på arbetsytan **Regelefterlevnad** för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="68d41-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="68d41-111">Med den här ändringen kan Personal komma åt:</span><span class="sxs-lookup"><span data-stu-id="68d41-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="68d41-112">Alla ärenden</span><span class="sxs-lookup"><span data-stu-id="68d41-112">All cases</span></span>
- <span data-ttu-id="68d41-113">Mina ärenden</span><span class="sxs-lookup"><span data-stu-id="68d41-113">My cases</span></span>
- <span data-ttu-id="68d41-114">Mina öppna ärenden</span><span class="sxs-lookup"><span data-stu-id="68d41-114">My open cases</span></span>
- <span data-ttu-id="68d41-115">Mina förfallna ärenden</span><span class="sxs-lookup"><span data-stu-id="68d41-115">My overdue cases</span></span>
- <span data-ttu-id="68d41-116">Ärenden tilldelade till mig genom arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="68d41-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="68d41-117">Tillsammans med dessa nya vyer i ärenden finns även DMF-entiteten **Ärendedetalj**.</span><span class="sxs-lookup"><span data-stu-id="68d41-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="68d41-118">Aktivera relationsdefinitioner i globala adressboken (414762)</span><span class="sxs-lookup"><span data-stu-id="68d41-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="68d41-119">Relationerna är nu aktiverade i den globala adressboken.</span><span class="sxs-lookup"><span data-stu-id="68d41-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="68d41-120">Innan den här veckans frisläppning visas faktarutan, **Relationer** alla systemdefinierade relationer.</span><span class="sxs-lookup"><span data-stu-id="68d41-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="68d41-121">Nu kan du definiera dessa relationer på sidan för den globala adressboken.</span><span class="sxs-lookup"><span data-stu-id="68d41-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="68d41-122">En befattning kan tas bort när aktiva kompensationsposter finns för positionen (414568)</span><span class="sxs-lookup"><span data-stu-id="68d41-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="68d41-123">Med den här ändringen visas en varning när du försöker ta bort en position och arbetaren har en aktiv kompensationspost för samma position.</span><span class="sxs-lookup"><span data-stu-id="68d41-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="68d41-124">När detta inträffar måste du uppdatera medarbetarens fasta kompensationspost innan du tar bort positionen.</span><span class="sxs-lookup"><span data-stu-id="68d41-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="68d41-125">Arbetsflödet för prestandagranskning infogar ibland godkännandena från personer som inte ingår i processen (414171)</span><span class="sxs-lookup"><span data-stu-id="68d41-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="68d41-126">Den här ändringen åtgärdar ett problem där ytterligare godkännande deltagare läggs till i prestandagranskningen.</span><span class="sxs-lookup"><span data-stu-id="68d41-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="68d41-127">Tilldelning av arbetarposition skapas inte i Dataverse när den väljs i dialogrutan Ny arbetare (413479)</span><span class="sxs-lookup"><span data-stu-id="68d41-127">Worker position assignment not created in Dataverse when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="68d41-128">Den här ändringen åtgärdar ett problem vid anställning av en ny arbetare och tilldelar den nya anställningen till en position via dialogrutan **Ny arbetare**.</span><span class="sxs-lookup"><span data-stu-id="68d41-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="68d41-129">Nu återspeglas befattningstilldelning reflekteras i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="68d41-129">Now the position assignment is reflected in Dataverse.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="68d41-130">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="68d41-130">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="68d41-131">Uppdaterad Dataverse-lösning</span><span class="sxs-lookup"><span data-stu-id="68d41-131">Updated Dataverse solution</span></span>

<span data-ttu-id="68d41-132">En ny Dataverse-lösning kommer snart att vara tillgänglig med följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="68d41-132">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="68d41-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="68d41-133">Description</span></span> | <span data-ttu-id="68d41-134">Växel</span><span class="sxs-lookup"><span data-stu-id="68d41-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="68d41-135">**Jobb/befattning** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="68d41-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="68d41-136">**Kompensationsregion** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-136">**Compensation region** added</span></span></br><span data-ttu-id="68d41-137">**Ekonomiska dimensioner** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="68d41-138">**Arbetare** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="68d41-138">**Worker** entity changes</span></span> | <span data-ttu-id="68d41-139">**Namnordning** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-139">**Name sequence** added</span></span></br><span data-ttu-id="68d41-140">**Arbetar hemifrån** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-140">**Works from home** added</span></span></br><span data-ttu-id="68d41-141">**Språk** tillagt</span><span class="sxs-lookup"><span data-stu-id="68d41-141">**Language** added</span></span></br><span data-ttu-id="68d41-142">**Datum för tjänsteålder** tillagt</span><span class="sxs-lookup"><span data-stu-id="68d41-142">**Seniority date** added</span></span></br><span data-ttu-id="68d41-143">**Jubileumsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="68d41-143">**Anniversary date** added</span></span></br><span data-ttu-id="68d41-144">**Ursprungligt anställningsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="68d41-144">**Original hire date** added</span></span> |
| <span data-ttu-id="68d41-145">**Anställning** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="68d41-145">**Employment** entity changes</span></span> | <span data-ttu-id="68d41-146">**Ekonomiska dimensioner** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-146">**Financial dimensions** added</span></span></br><span data-ttu-id="68d41-147">**Uppsägningsorsak** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-147">**Termination reason** added</span></span></br><span data-ttu-id="68d41-148">**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</span><span class="sxs-lookup"><span data-stu-id="68d41-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="68d41-149">**Provanställningsdatum** tillagt</span><span class="sxs-lookup"><span data-stu-id="68d41-149">**Probation date** added</span></span> |
| <span data-ttu-id="68d41-150">**Arbetaradress** enhetsändringar</span><span class="sxs-lookup"><span data-stu-id="68d41-150">**Worker address** entity changes</span></span> | <span data-ttu-id="68d41-151">**Gatuadress** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-151">**Street address** added</span></span></br><span data-ttu-id="68d41-152">**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell</span><span class="sxs-lookup"><span data-stu-id="68d41-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="68d41-153">Inställningsenheter för ny variabelkompensation</span><span class="sxs-lookup"><span data-stu-id="68d41-153">New variable compensation setup entities</span></span> | <span data-ttu-id="68d41-154">**Typ av variabel kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="68d41-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="68d41-155">**Variabel kompensationsplan**</span><span class="sxs-lookup"><span data-stu-id="68d41-155">**Compensation variable plan**</span></span></br><span data-ttu-id="68d41-156">**Överlåtelseregler**</span><span class="sxs-lookup"><span data-stu-id="68d41-156">**Vesting rules**</span></span></br><span data-ttu-id="68d41-157">**Variabel kompensationsplannivå**</span><span class="sxs-lookup"><span data-stu-id="68d41-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="68d41-158">Ny enhet för **Arbetarkalender anställning**</span><span class="sxs-lookup"><span data-stu-id="68d41-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="68d41-159">**Enheten arbetskalender** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="68d41-160">Ny enhet för **lönepositionsuppgift**</span><span class="sxs-lookup"><span data-stu-id="68d41-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="68d41-161">**Lönepositionsuppgift** tillagd</span><span class="sxs-lookup"><span data-stu-id="68d41-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="68d41-162">Ny enhet för **Rubrik**</span><span class="sxs-lookup"><span data-stu-id="68d41-162">New **Title** entity</span></span> | <span data-ttu-id="68d41-163">**Rubrik** tillagd.</span><span class="sxs-lookup"><span data-stu-id="68d41-163">**Title** added.</span></span> <span data-ttu-id="68d41-164">Den nya entiteten **Rubrik** kommer att inkluderas i synkroniseringsprocessen mellan personal och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="68d41-164">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="68d41-165">Den kommer då inte från **Jobbefattning** eller **Jobb** enheter.</span><span class="sxs-lookup"><span data-stu-id="68d41-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="68d41-166">Under de närmaste veckorna kommer dessa enhetsändringar att vara tillgängliga i alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="68d41-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="68d41-167">Så här installerar du den senaste Dataverse-lösningen för personal manuellt:</span><span class="sxs-lookup"><span data-stu-id="68d41-167">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="68d41-168">Gå till [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="68d41-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="68d41-169">Välj **Miljö**.</span><span class="sxs-lookup"><span data-stu-id="68d41-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="68d41-170">Leta upp den miljö som du vill uppgradera.</span><span class="sxs-lookup"><span data-stu-id="68d41-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="68d41-171">Detta bör motsvara **Miljönamn** i avsnittet **Common Data Service-information** i formuläret **Om** i Personal.</span><span class="sxs-lookup"><span data-stu-id="68d41-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="68d41-172">Välj miljö om du vill visa information om miljön.</span><span class="sxs-lookup"><span data-stu-id="68d41-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="68d41-173">I åtgärdsfältet längst upp, välj **Hantera lösningar**.</span><span class="sxs-lookup"><span data-stu-id="68d41-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="68d41-174">Ett nytt webbläsarfönster öppnas och navigera till **Dynamics 365 administrationscenter** inom ramen för din miljö.</span><span class="sxs-lookup"><span data-stu-id="68d41-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="68d41-175">I listan **Lösningar** välj **Dynamics 365 Human Resources Förankra**.</span><span class="sxs-lookup"><span data-stu-id="68d41-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="68d41-176">Välj **uppgradering** om du vill använda den senaste lösningen.</span><span class="sxs-lookup"><span data-stu-id="68d41-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="68d41-177">I förhandsgranskning</span><span class="sxs-lookup"><span data-stu-id="68d41-177">In preview</span></span>

<span data-ttu-id="68d41-178">Följande förhandsgranskningsfunktioner blir tillgängliga den 3 februari 2020:</span><span class="sxs-lookup"><span data-stu-id="68d41-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="68d41-179">**Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** – För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="68d41-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="68d41-180">**Förhandsgranskningsfunktioner för förmånshantering** – För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="68d41-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68d41-181">Se även</span><span class="sxs-lookup"><span data-stu-id="68d41-181">See also</span></span>

[<span data-ttu-id="68d41-182">Nyheter och ändringar i Personal</span><span class="sxs-lookup"><span data-stu-id="68d41-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="68d41-183">Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2</span><span class="sxs-lookup"><span data-stu-id="68d41-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="68d41-184">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="68d41-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="68d41-185">Hantera funktioner</span><span class="sxs-lookup"><span data-stu-id="68d41-185">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]