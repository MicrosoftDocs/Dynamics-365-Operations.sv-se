---
title: Uppdatera process
description: Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar för app- och plattformsändringar.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 267682f4497bacf70f93840a948d0e525dfa4aa1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092211"
---
# <a name="update-process"></a><span data-ttu-id="8974a-103">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="8974a-103">Update process</span></span>

<span data-ttu-id="8974a-104">Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8974a-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="8974a-105">Uppdateringarna innehåller både program- och plattformsändringar som ofta ger viktiga förbättringar av tjänsten, inklusive regler för uppdatering av regler.</span><span class="sxs-lookup"><span data-stu-id="8974a-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="8974a-106">Uppdatera policy</span><span class="sxs-lookup"><span data-stu-id="8974a-106">Update policy</span></span>

<span data-ttu-id="8974a-107">Uppdateringar släpps regelbundet för alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="8974a-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="8974a-108">Personal stöds enligt [Microsoft livscykelpolicy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av support.</span><span class="sxs-lookup"><span data-stu-id="8974a-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="8974a-109">Frisläpp miljö</span><span class="sxs-lookup"><span data-stu-id="8974a-109">Release cadence</span></span>

<span data-ttu-id="8974a-110">Personaluppdateringar tillämpas automatiskt på alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="8974a-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="8974a-111">I personal finns två typer av utgåvor:</span><span class="sxs-lookup"><span data-stu-id="8974a-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="8974a-112">**Tjänstuppdateringar**: uppdateringar varje vecka som innehåller felkorrigeringar och nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="8974a-112">**Service updates**: Weekly updates that include bug fixes and new features.</span></span> <span data-ttu-id="8974a-113">Tjänstuppdateringar inkluderar även tillämpliga plattformsuppdateringar när de släpps.</span><span class="sxs-lookup"><span data-stu-id="8974a-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="8974a-114">För att få en uppfattning om hur plattformsuppdateringar frisläpps, se [Tabell 3: frisläppning av plattformsuppdateringar](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="8974a-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span></span> <span data-ttu-id="8974a-115">Veckovisa uppdateringar ges vanligtvis på onsdagar.</span><span class="sxs-lookup"><span data-stu-id="8974a-115">Weekly updates usually release on Wednesdays.</span></span> <span data-ttu-id="8974a-116">Mer information om veckovisa uppdateringar finns i [Nyheter eller ändringar i Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).</span><span class="sxs-lookup"><span data-stu-id="8974a-116">For more information about weekly updates, see [What's new or changed in Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).</span></span>

    <span data-ttu-id="8974a-117">Alla datacenter som stöds uppdateras varje vecka, om inget annat anges.</span><span class="sxs-lookup"><span data-stu-id="8974a-117">All supported data centers update weekly, unless otherwise noted.</span></span> <span data-ttu-id="8974a-118">Veckovisa uppdateringar börjar normalt på onsdag och slutförs på söndag.</span><span class="sxs-lookup"><span data-stu-id="8974a-118">Weekly updates typically begin on Wednesday and complete by Sunday.</span></span> <span data-ttu-id="8974a-119">Regionerna USA, Australien, Europa, Storbritannien, Asien och Kanada ingår i varje veckas uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8974a-119">US, Australia, Europe, UK, Asia, and Canada regions are included in weekly updates.</span></span> 

- <span data-ttu-id="8974a-120">**Uppdateringar av Common Data Service-lösning**: dessa uppdateringar sker var sjätte vecka, efter behov.</span><span class="sxs-lookup"><span data-stu-id="8974a-120">**Common Data Service solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="8974a-121">De innehåller nya entiteter och ändringar i befintliga entiteter i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8974a-121">They include new entities and changes to existing entities in Common Data Service.</span></span> <span data-ttu-id="8974a-122">Dessa uppdateringar frisläpps på samma områden som veckovisa uppdateringar och de tar ungefär sex veckor att replikera genom alla datacenter.</span><span class="sxs-lookup"><span data-stu-id="8974a-122">These updates release to the same regions as the weekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="8974a-123">Uppdateringar av lösningen kan eventuellt justeras med veckovisa tjänstuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="8974a-123">Solution updates may or may not align with weekly service updates.</span></span>

<span data-ttu-id="8974a-124">Följande tabell visar ett exempelschema:</span><span class="sxs-lookup"><span data-stu-id="8974a-124">The following table shows a sample schedule:</span></span>

| <span data-ttu-id="8974a-125">Vecka</span><span class="sxs-lookup"><span data-stu-id="8974a-125">Week</span></span> | <span data-ttu-id="8974a-126">Uppdateringstyp</span><span class="sxs-lookup"><span data-stu-id="8974a-126">Update type</span></span> |
| --- | --- |
| <span data-ttu-id="8974a-127">1</span><span class="sxs-lookup"><span data-stu-id="8974a-127">1</span></span> | <span data-ttu-id="8974a-128">Tjänstuppdatering (alla regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-128">Service update (all regions)</span></span> |
| <span data-ttu-id="8974a-129">2</span><span class="sxs-lookup"><span data-stu-id="8974a-129">2</span></span> | <span data-ttu-id="8974a-130">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 1 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-130">Service update (all regions) + Solution update (Week 1 regions)</span></span> |
| <span data-ttu-id="8974a-131">3</span><span class="sxs-lookup"><span data-stu-id="8974a-131">3</span></span> | <span data-ttu-id="8974a-132">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 2 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-132">Service update (all regions) + Solution update (Week 2 regions)</span></span> |
| <span data-ttu-id="8974a-133">4</span><span class="sxs-lookup"><span data-stu-id="8974a-133">4</span></span> | <span data-ttu-id="8974a-134">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 3 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-134">Service update (all regions) + Solution update (Week 3 regions)</span></span> |
| <span data-ttu-id="8974a-135">5</span><span class="sxs-lookup"><span data-stu-id="8974a-135">5</span></span> | <span data-ttu-id="8974a-136">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 4 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-136">Service update (all regions) + Solution update (Week 4 regions)</span></span> |
| <span data-ttu-id="8974a-137">6</span><span class="sxs-lookup"><span data-stu-id="8974a-137">6</span></span> | <span data-ttu-id="8974a-138">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 5 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-138">Service update (all regions) + Solution update (Week 5 regions)</span></span> |
| <span data-ttu-id="8974a-139">7</span><span class="sxs-lookup"><span data-stu-id="8974a-139">7</span></span> | <span data-ttu-id="8974a-140">Tjänstuppdatering (alla regioner) + uppdatering av lösningen (vecka 6 regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-140">Service update (all regions) + Solution update (Week 6 regions)</span></span> |
| <span data-ttu-id="8974a-141">8</span><span class="sxs-lookup"><span data-stu-id="8974a-141">8</span></span> | <span data-ttu-id="8974a-142">Tjänstuppdatering (alla regioner)</span><span class="sxs-lookup"><span data-stu-id="8974a-142">Service update (all regions)</span></span> |

> [!NOTE]
> <span data-ttu-id="8974a-143">Lösningsuppdateringar är tillgängliga på alla datacenter när de har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="8974a-143">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="8974a-144">Om du inte vill vänta på att uppdateringarna ska replikeras automatiskt kan du installera dessa uppdateringar manuellt på alla miljöer i datacentret.</span><span class="sxs-lookup"><span data-stu-id="8974a-144">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="8974a-145">Vid behov innehåller personal även följande typer av korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="8974a-145">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="8974a-146">**Ändring (snabbkorrigering)**: felkorrigeringar som kan uppstå med eller utanför en veckovis tjänstuppdateringsversion</span><span class="sxs-lookup"><span data-stu-id="8974a-146">**Revision (hotfix)**: bug fixes that can occur either with or apart from a weekly service update release</span></span>

- <span data-ttu-id="8974a-147">**Nödkorrigering**: förebyggande och återaktiva snabbkorrigeringar som är fristående, kan inkludera enbart konfigurations- eller kodändringar för att lösa problem med aktiva webbplatsen och kan komma från en veckovis uppdatering av tjänstuppdateringar</span><span class="sxs-lookup"><span data-stu-id="8974a-147">**Emergency fix**: proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a weekly service update release</span></span>

<span data-ttu-id="8974a-148">Versioner granskas, testas och valideras i en intern miljö.</span><span class="sxs-lookup"><span data-stu-id="8974a-148">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="8974a-149">När versioner har signerats distribueras de till produktion.</span><span class="sxs-lookup"><span data-stu-id="8974a-149">After builds are signed off, they're then deployed to production.</span></span>

## <a name="exceptions-in-2019"></a><span data-ttu-id="8974a-150">Undantag i 2019</span><span class="sxs-lookup"><span data-stu-id="8974a-150">Exceptions in 2019</span></span>

<span data-ttu-id="8974a-151">Följande datum utgör undantag från schemat för regelbunden publicering:</span><span class="sxs-lookup"><span data-stu-id="8974a-151">The following dates are exceptions to the regular release schedule:</span></span>

| <span data-ttu-id="8974a-152">Datum</span><span class="sxs-lookup"><span data-stu-id="8974a-152">Date</span></span> | <span data-ttu-id="8974a-153">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8974a-153">Description</span></span> |
| --- | --- |
| <span data-ttu-id="8974a-154">Vecka för 25 november</span><span class="sxs-lookup"><span data-stu-id="8974a-154">Week of November 25</span></span> | <span data-ttu-id="8974a-155">Inga uppdateringar</span><span class="sxs-lookup"><span data-stu-id="8974a-155">No updates</span></span> |
| <span data-ttu-id="8974a-156">Vecka för 16 december</span><span class="sxs-lookup"><span data-stu-id="8974a-156">Week of December 16</span></span> | <span data-ttu-id="8974a-157">Endast mindre uppdateringar</span><span class="sxs-lookup"><span data-stu-id="8974a-157">Minor updates only</span></span> |
| <span data-ttu-id="8974a-158">Vecka för 23 december</span><span class="sxs-lookup"><span data-stu-id="8974a-158">Week of December 23</span></span> | <span data-ttu-id="8974a-159">Inga uppdateringar</span><span class="sxs-lookup"><span data-stu-id="8974a-159">No updates</span></span> |
| <span data-ttu-id="8974a-160">Vecka för 30 december</span><span class="sxs-lookup"><span data-stu-id="8974a-160">Week of December 30</span></span> | <span data-ttu-id="8974a-161">Inga uppdateringar</span><span class="sxs-lookup"><span data-stu-id="8974a-161">No updates</span></span> |

## <a name="communications"></a><span data-ttu-id="8974a-162">Kommunikationer</span><span class="sxs-lookup"><span data-stu-id="8974a-162">Communications</span></span>

<span data-ttu-id="8974a-163">Du kan ta reda på vad som finns i arbetet för personal och vad vi har publicerat på följande platser:</span><span class="sxs-lookup"><span data-stu-id="8974a-163">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="8974a-164">Dynamics 365 Human Resources översikt</span><span class="sxs-lookup"><span data-stu-id="8974a-164">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/talent/)

- [<span data-ttu-id="8974a-165">Utgivningsplaner för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8974a-165">Dynamics 365 Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans/)

- [<span data-ttu-id="8974a-166">Nyheter och ändringar i Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="8974a-166">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="8974a-167">[Problemsökning i Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (endast för plattformsspecifika programfel)</span><span class="sxs-lookup"><span data-stu-id="8974a-167">[Issue search in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="8974a-168">Personalblogg</span><span class="sxs-lookup"><span data-stu-id="8974a-168">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="8974a-169">Personal Yammer-community</span><span class="sxs-lookup"><span data-stu-id="8974a-169">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="8974a-170">Förhandsgranskningsfunktioner i en miljö med begränsat läge</span><span class="sxs-lookup"><span data-stu-id="8974a-170">Preview features in a sandbox environment</span></span>

<span data-ttu-id="8974a-171">Du kan validera förhandsgranskningsfunktionerna i en miljö med begränsat läge innan du gör dem i produktionsmiljön.</span><span class="sxs-lookup"><span data-stu-id="8974a-171">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="8974a-172">Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="8974a-172">For more information about enabling features, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

<span data-ttu-id="8974a-173">Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar.</span><span class="sxs-lookup"><span data-stu-id="8974a-173">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="8974a-174">Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden.</span><span class="sxs-lookup"><span data-stu-id="8974a-174">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="8974a-175">Så snart du ser nya funktioner på arbetsytan Funktionshantering kan du aktivera dem.</span><span class="sxs-lookup"><span data-stu-id="8974a-175">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="8974a-176">Vissa funktioner kan vara aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="8974a-176">Some features may be on by default.</span></span>

<span data-ttu-id="8974a-177">I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan funktionshantering).</span><span class="sxs-lookup"><span data-stu-id="8974a-177">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="8974a-178">När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="8974a-178">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="8974a-179">Arbetsytan funktionshantering anger när en förhandsgranskningsfunktion blir obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="8974a-179">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="8974a-180">Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna.</span><span class="sxs-lookup"><span data-stu-id="8974a-180">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="8974a-181">De kan inte inaktivera obligatoriska funktioner.</span><span class="sxs-lookup"><span data-stu-id="8974a-181">You can't turn off mandatory features.</span></span> <span data-ttu-id="8974a-182">Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="8974a-182">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="8974a-183">Vi rekommenderar starkt förhandsgranskningsfunktionerna i en miljö med begränsat läge eller en testmiljö.</span><span class="sxs-lookup"><span data-stu-id="8974a-183">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="8974a-184">Det är bäst att skapa en kopia av den aktuella produktionsmiljön eller databasen i en miljö med begränsat läge så att du kan få den fullständiga upplevelsen av de nya funktionerna med dina data.</span><span class="sxs-lookup"><span data-stu-id="8974a-184">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="8974a-185">Mer information om hur du etablerar en miljö med begränsat läge finns i [etablera ett personalprojekt](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="8974a-185">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="8974a-186">Mer information om hur du tar bort finns i [Ta bort en instans](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="8974a-186">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="8974a-187">Rapportera buggar</span><span class="sxs-lookup"><span data-stu-id="8974a-187">Report bugs</span></span>

<span data-ttu-id="8974a-188">När du testar förhandsgranskningsfunktioner eller försöker med nya funktioner kanske du hittar objekt som inte fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="8974a-188">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="8974a-189">Rapportera eventuella fel till [Microsoft Dynamics 365-stödet](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="8974a-189">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="8974a-190">Se även</span><span class="sxs-lookup"><span data-stu-id="8974a-190">See also</span></span>

- [<span data-ttu-id="8974a-191">Utgivningsplaner för Dynamics 365 och Power Platform</span><span class="sxs-lookup"><span data-stu-id="8974a-191">Dynamics 365 and Power Platform Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans)
- [<span data-ttu-id="8974a-192">Nyheter och ändringar i Dynamics 365 Personal</span><span class="sxs-lookup"><span data-stu-id="8974a-192">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="8974a-193">Livscykelpolicy för programmet</span><span class="sxs-lookup"><span data-stu-id="8974a-193">Software lifecycle policy</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

