---
title: Uppdatera process
description: Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar för app- och plattformsändringar.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4069e369b1a9f15372d1e29e3809198b90b12c7e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791543"
---
# <a name="update-process"></a><span data-ttu-id="1e303-103">Uppdatera process</span><span class="sxs-lookup"><span data-stu-id="1e303-103">Update process</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1e303-104">Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="1e303-104">Microsoft Dynamics 365 Human Resources is a true software as a service (SaaS) that provides continuous, touchless service updates.</span></span> <span data-ttu-id="1e303-105">Uppdateringarna innehåller både program- och plattformsändringar som ofta ger viktiga förbättringar av tjänsten, inklusive regler för uppdatering av regler.</span><span class="sxs-lookup"><span data-stu-id="1e303-105">These updates contain both application and platform changes that often provide critical improvements to the service, including regulatory updates.</span></span>

## <a name="update-policy"></a><span data-ttu-id="1e303-106">Uppdatera policy</span><span class="sxs-lookup"><span data-stu-id="1e303-106">Update policy</span></span>

<span data-ttu-id="1e303-107">Uppdateringar släpps regelbundet för alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="1e303-107">Updates are released on a regular cadence to all environments.</span></span> <span data-ttu-id="1e303-108">Personal stöds enligt [Microsoft livscykelpolicy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av support.</span><span class="sxs-lookup"><span data-stu-id="1e303-108">Human Resources is supported according to the [Microsoft Lifecycle policy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), which provides consistent and predictable guidelines for the availability of support.</span></span>

## <a name="release-cadence"></a><span data-ttu-id="1e303-109">Frisläpp miljö</span><span class="sxs-lookup"><span data-stu-id="1e303-109">Release cadence</span></span> 

<span data-ttu-id="1e303-110">Personaluppdateringar tillämpas automatiskt på alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="1e303-110">Human Resources updates are applied to all environments automatically.</span></span> <span data-ttu-id="1e303-111">I personal finns två typer av utgåvor:</span><span class="sxs-lookup"><span data-stu-id="1e303-111">Human Resources provides two types of releases:</span></span>

- <span data-ttu-id="1e303-112">**Tjänstuppdateringar**: uppdateringar sker varannan vecka som innehåller felkorrigeringar och nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="1e303-112">**Service updates**: Updates occur every two weeks that include bug fixes and new features.</span></span> <span data-ttu-id="1e303-113">Tjänstuppdateringar inkluderar även tillämpliga plattformsuppdateringar när de släpps.</span><span class="sxs-lookup"><span data-stu-id="1e303-113">Service updates also include applicable Platform updates when they release.</span></span> <span data-ttu-id="1e303-114">För att få en uppfattning om hur plattformsuppdateringar frisläpps, se [Tabell 3: frisläppning av plattformsuppdateringar](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span><span class="sxs-lookup"><span data-stu-id="1e303-114">To get an idea of when Platform updates are released, see [Table 3: Platform releases](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases).</span></span> <span data-ttu-id="1e303-115">Uppdateringar varannan vecka har en stegvis global introduktion över regioner.</span><span class="sxs-lookup"><span data-stu-id="1e303-115">Biweekly updates have a staged global rollout across regions.</span></span> <span data-ttu-id="1e303-116">Mer information om uppdateringar varannan vecka finns i [Nyheter eller ändringar i Dynamics 365 Human Resources](hr-admin-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="1e303-116">For more information about biweekly updates, see [What's new or changed in Dynamics 365 Human Resources](hr-admin-whats-new.md).</span></span>

    <span data-ttu-id="1e303-117">Alla datacenter som stöds uppdateras varannan vecka, om inget annat anges.</span><span class="sxs-lookup"><span data-stu-id="1e303-117">All supported data centers update every two weeks, unless otherwise noted.</span></span> <span data-ttu-id="1e303-118">Regionerna USA, Australien, Europa, Storbritannien, Asien och Kanada ingår i uppdateringar varannan vecka.</span><span class="sxs-lookup"><span data-stu-id="1e303-118">US, Australia, Europe, UK, Asia, and Canada regions are included in biweekly updates.</span></span> 

- <span data-ttu-id="1e303-119">**Uppdateringar av Dataverse-lösning**: dessa uppdateringar sker var sjätte vecka, efter behov.</span><span class="sxs-lookup"><span data-stu-id="1e303-119">**Dataverse solution updates**: These updates occur approximately every six weeks, as needed.</span></span> <span data-ttu-id="1e303-120">De innehåller nya entiteter och ändringar i befintliga entiteter i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1e303-120">They include new entities and changes to existing entities in Dataverse.</span></span> <span data-ttu-id="1e303-121">Dessa uppdateringar frisläpps på samma områden som uppdateringar varannan vecka och de tar ungefär sex veckor att replikera genom alla datacenter.</span><span class="sxs-lookup"><span data-stu-id="1e303-121">These updates release to the same regions as the biweekly updates, and they take about six weeks to replicate through all data centers.</span></span> <span data-ttu-id="1e303-122">Uppdateringar av lösningen kan eventuellt justeras med tjänstuppdateringar varannan vecka.</span><span class="sxs-lookup"><span data-stu-id="1e303-122">Solution updates may or may not align with biweekly service updates.</span></span>

> [!NOTE]
> <span data-ttu-id="1e303-123">Lösningsuppdateringar är tillgängliga på alla datacenter när de har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="1e303-123">Solution updates are available on all data centers once they're released.</span></span> <span data-ttu-id="1e303-124">Om du inte vill vänta på att uppdateringarna ska replikeras automatiskt kan du installera dessa uppdateringar manuellt på alla miljöer i datacentret.</span><span class="sxs-lookup"><span data-stu-id="1e303-124">If you don't want to wait for the updates to replicate automatically, you can manually apply these updates on any environment in any data center.</span></span>

<span data-ttu-id="1e303-125">Vid behov innehåller personal även följande typer av korrigeringar:</span><span class="sxs-lookup"><span data-stu-id="1e303-125">When needed, Human Resources also provides the following types of fixes:</span></span>

- <span data-ttu-id="1e303-126">**Ändring (snabbkorrigering)**: felkorrigeringar som kan uppstå med eller utanför en tjänstuppdateringsversion varannan vecka</span><span class="sxs-lookup"><span data-stu-id="1e303-126">**Revision (hotfix)**: Bug fixes that can occur either with or apart from a biweekly service update release</span></span>

- <span data-ttu-id="1e303-127">**Nödkorrigering**: förebyggande och återaktiva snabbkorrigeringar som är fristående, kan inkludera enbart konfigurations- eller kodändringar för att lösa problem med aktiva webbplatsen och kan komma från en uppdatering varannan vecka av tjänstuppdateringar</span><span class="sxs-lookup"><span data-stu-id="1e303-127">**Emergency fix**: Proactive and reactive hotfixes that are standalone in nature, can include configuration-only or code changes to resolve live site issues, and can occur apart from a biweekly service update release</span></span>

<span data-ttu-id="1e303-128">Versioner granskas, testas och valideras i en intern miljö.</span><span class="sxs-lookup"><span data-stu-id="1e303-128">Releases are reviewed, tested, and validated on an internal environment.</span></span> <span data-ttu-id="1e303-129">När versioner har signerats distribueras de till produktion.</span><span class="sxs-lookup"><span data-stu-id="1e303-129">After builds are signed off, they're then deployed to production.</span></span>

## <a name="release-cadence-exceptions-in-2021"></a><span data-ttu-id="1e303-130">Frisläppningstakt undantag i 2021</span><span class="sxs-lookup"><span data-stu-id="1e303-130">Release cadence exceptions in 2021</span></span>

<span data-ttu-id="1e303-131">För att kunna redovisa helgdagar är publicering av version för november och december 2021 följande:</span><span class="sxs-lookup"><span data-stu-id="1e303-131">To account for holidays, the release schedule for November and December 2021 is as follows:</span></span>

- <span data-ttu-id="1e303-132">November version: 1 november – 14 november</span><span class="sxs-lookup"><span data-stu-id="1e303-132">November release: November 1 - November 14</span></span>
- <span data-ttu-id="1e303-133">December version: 29 november – 12 december</span><span class="sxs-lookup"><span data-stu-id="1e303-133">December release: November 29 - December 12</span></span>
 
<span data-ttu-id="1e303-134">Frisläppningstakten på två veckor kommer att återupptas som vanligt den 10 januari, 2022.</span><span class="sxs-lookup"><span data-stu-id="1e303-134">The two-week release cadence will resume as usual on January 10, 2022.</span></span>

## <a name="communications"></a><span data-ttu-id="1e303-135">Kommunikationer</span><span class="sxs-lookup"><span data-stu-id="1e303-135">Communications</span></span>

<span data-ttu-id="1e303-136">Du kan ta reda på vad som finns i arbetet för personal och vad vi har publicerat på följande platser:</span><span class="sxs-lookup"><span data-stu-id="1e303-136">You can find out what's in the works for Human Resources and what we've released in the following locations:</span></span>

- [<span data-ttu-id="1e303-137">Dynamics 365 Human Resources översikt</span><span class="sxs-lookup"><span data-stu-id="1e303-137">Dynamics 365 Human Resources roadmap</span></span>](https://dynamics.microsoft.com/roadmap/human-resources/)

- [<span data-ttu-id="1e303-138">Utgivningsplaner för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1e303-138">Dynamics 365 Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans/)

- [<span data-ttu-id="1e303-139">Nyheter och ändringar i Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="1e303-139">What's new or changed in Dynamics 365 Human Resources</span></span>](hr-admin-whats-new.md)

- <span data-ttu-id="1e303-140">[Problemsökning i Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (endast för plattformsspecifika programfel)</span><span class="sxs-lookup"><span data-stu-id="1e303-140">[Issue search in Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (for Platform-related bugs only)</span></span>

- [<span data-ttu-id="1e303-141">Personalblogg</span><span class="sxs-lookup"><span data-stu-id="1e303-141">Human Resources blog</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [<span data-ttu-id="1e303-142">Personal Yammer-community</span><span class="sxs-lookup"><span data-stu-id="1e303-142">Human Resources Yammer community</span></span>](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a><span data-ttu-id="1e303-143">Förhandsgranskningsfunktioner i en miljö med begränsat läge</span><span class="sxs-lookup"><span data-stu-id="1e303-143">Preview features in a sandbox environment</span></span>

<span data-ttu-id="1e303-144">Du kan validera förhandsgranskningsfunktionerna i en miljö med begränsat läge innan du gör dem i produktionsmiljön.</span><span class="sxs-lookup"><span data-stu-id="1e303-144">You can validate preview features in a sandbox environment before enabling them in your production environment.</span></span> <span data-ttu-id="1e303-145">Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="1e303-145">For more information about enabling features, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

<span data-ttu-id="1e303-146">Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar.</span><span class="sxs-lookup"><span data-stu-id="1e303-146">All new features remain in preview for at least 30 days, and typically 30-60 days.</span></span> <span data-ttu-id="1e303-147">Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden.</span><span class="sxs-lookup"><span data-stu-id="1e303-147">Major features are generally available in October and April of each year following the preview period.</span></span> <span data-ttu-id="1e303-148">Så snart du ser nya funktioner på arbetsytan Funktionshantering kan du aktivera dem.</span><span class="sxs-lookup"><span data-stu-id="1e303-148">As soon as you see new capabilities in the Feature management workspace, you can turn them on.</span></span> <span data-ttu-id="1e303-149">Vissa funktioner kan vara aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="1e303-149">Some features may be on by default.</span></span>

<span data-ttu-id="1e303-150">I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan funktionshantering).</span><span class="sxs-lookup"><span data-stu-id="1e303-150">At times, an integral feature will be on by default and can't be turned off (for example, the Feature management workspace).</span></span>

<span data-ttu-id="1e303-151">När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="1e303-151">Once a feature is generally available, it may be turned on or off in production environments.</span></span> <span data-ttu-id="1e303-152">Arbetsytan funktionshantering anger när en förhandsgranskningsfunktion blir obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="1e303-152">The Feature management workspace indicates when a preview feature will become mandatory.</span></span> <span data-ttu-id="1e303-153">Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna.</span><span class="sxs-lookup"><span data-stu-id="1e303-153">This date is usually on October 1 or April 1 to align with the semiannual release plans.</span></span> <span data-ttu-id="1e303-154">De kan inte inaktivera obligatoriska funktioner.</span><span class="sxs-lookup"><span data-stu-id="1e303-154">You can't turn off mandatory features.</span></span> <span data-ttu-id="1e303-155">Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="1e303-155">Until it becomes mandatory, you can turn a feature on and off in all environments.</span></span>

<span data-ttu-id="1e303-156">Vi rekommenderar starkt förhandsgranskningsfunktionerna i en miljö med begränsat läge eller en testmiljö.</span><span class="sxs-lookup"><span data-stu-id="1e303-156">We highly recommend previewing features in a sandbox or trial environment.</span></span> <span data-ttu-id="1e303-157">Det är bäst att skapa en kopia av den aktuella produktionsmiljön eller databasen i en miljö med begränsat läge så att du kan få den fullständiga upplevelsen av de nya funktionerna med dina data.</span><span class="sxs-lookup"><span data-stu-id="1e303-157">It's best to create a copy of your current production environment or database into a sandbox environment so you can get the complete experience of the new features with your data.</span></span>

<span data-ttu-id="1e303-158">Mer information om hur du etablerar en miljö med begränsat läge finns i [etablera ett personalprojekt](hr-admin-setup-provision.md).</span><span class="sxs-lookup"><span data-stu-id="1e303-158">For more information about provisioning a sandbox environment, see [Provision a Human Resources project](hr-admin-setup-provision.md).</span></span> <span data-ttu-id="1e303-159">Mer information om hur du tar bort finns i [Ta bort en instans](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span><span class="sxs-lookup"><span data-stu-id="1e303-159">To remove a test environment, see [Remove an instance](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment).</span></span> 

## <a name="report-bugs"></a><span data-ttu-id="1e303-160">Rapportera buggar</span><span class="sxs-lookup"><span data-stu-id="1e303-160">Report bugs</span></span>

<span data-ttu-id="1e303-161">När du testar förhandsgranskningsfunktioner eller försöker med nya funktioner kanske du hittar objekt som inte fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="1e303-161">While testing preview features or trying new capabilities, you might find items that don't work as expected.</span></span> <span data-ttu-id="1e303-162">Rapportera eventuella fel till [Microsoft Dynamics 365-stödet](https://dynamics.microsoft.com/support/).</span><span class="sxs-lookup"><span data-stu-id="1e303-162">Please report any bugs through [Microsoft Dynamics 365 support](https://dynamics.microsoft.com/support/).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e303-163">Se även</span><span class="sxs-lookup"><span data-stu-id="1e303-163">See also</span></span>

[<span data-ttu-id="1e303-164">Utgivningsplaner för Dynamics 365 och Power Platform</span><span class="sxs-lookup"><span data-stu-id="1e303-164">Dynamics 365 and Power Platform Release Plans</span></span>](https://docs.microsoft.com/dynamics365/release-plans)</br>
[<span data-ttu-id="1e303-165">Nyheter och ändringar i Dynamics 365 Personal</span><span class="sxs-lookup"><span data-stu-id="1e303-165">What's new or changed in Dynamics 365 Human Resource</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="1e303-166">Livscykelpolicy för programmet</span><span class="sxs-lookup"><span data-stu-id="1e303-166">Software lifecycle policy</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
