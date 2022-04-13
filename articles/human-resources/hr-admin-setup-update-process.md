---
title: Uppdatera process
description: Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar för app- och plattformsändringar.
author: twheeloc
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9552e518855711781c905514cae1cc25d33718c6
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533583"
---
# <a name="update-process"></a>Uppdatera process

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Microsoft Dynamics 365 Human Resources är en äkta programvara som en tjänst (SaaS) som tillhandahåller kontinuerliga, beröringsfria tjänstuppdateringar. Uppdateringarna innehåller både program- och plattformsändringar som ofta ger viktiga förbättringar av tjänsten, inklusive regler för uppdatering av regler.

## <a name="update-policy"></a>Uppdatera policy

Uppdateringar släpps regelbundet för alla miljöer. Personal stöds enligt [Microsoft livscykelpolicy](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av support.

## <a name="release-cadence"></a>Frisläpp miljö 

Personaluppdateringar tillämpas automatiskt på alla miljöer. I personal finns två typer av utgåvor:

- **Tjänstuppdateringar**: uppdateringar sker varannan vecka som innehåller felkorrigeringar och nya funktioner. Tjänstuppdateringar inkluderar även tillämpliga plattformsuppdateringar när de släpps. För att få en uppfattning om hur plattformsuppdateringar frisläpps, se [Tabell 3: frisläppning av plattformsuppdateringar](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases). Uppdateringar varannan vecka har en stegvis global introduktion över regioner. Mer information om uppdateringar varannan vecka finns i [Nyheter eller ändringar i Dynamics 365 Human Resources](hr-admin-whats-new.md).

    Alla datacenter som stöds uppdateras varannan vecka, om inget annat anges. Regionerna USA, Australien, Europa, Storbritannien, Asien och Kanada ingår i uppdateringar varannan vecka. 

- **Uppdateringar av Dataverse-lösning**: dessa uppdateringar sker var sjätte vecka, efter behov. De innehåller nya entiteter och ändringar i befintliga entiteter i Dataverse. Dessa uppdateringar frisläpps på samma områden som uppdateringar varannan vecka och de tar ungefär sex veckor att replikera genom alla datacenter. Uppdateringar av lösningen kan eventuellt justeras med tjänstuppdateringar varannan vecka.

> [!NOTE]
> Lösningsuppdateringar är tillgängliga på alla datacenter när de har frisläppts. Om du inte vill vänta på att uppdateringarna ska replikeras automatiskt kan du installera dessa uppdateringar manuellt på alla miljöer i datacentret.

Vid behov innehåller personal även följande typer av korrigeringar:

- **Ändring (snabbkorrigering)**: felkorrigeringar som kan uppstå med eller utanför en tjänstuppdateringsversion varannan vecka

- **Nödkorrigering**: förebyggande och återaktiva snabbkorrigeringar som är fristående, kan inkludera enbart konfigurations- eller kodändringar för att lösa problem med aktiva webbplatsen och kan komma från en uppdatering varannan vecka av tjänstuppdateringar

Versioner granskas, testas och valideras i en intern miljö. När versioner har signerats distribueras de till produktion.

## <a name="release-cadence-exceptions-in-2021"></a>Frisläppningstakt undantag i 2021

För att kunna redovisa helgdagar är publicering av version för november och december 2021 följande:

- November version: 1 november – 14 november
- December version: 29 november – 12 december
 
Frisläppningstakten på två veckor kommer att återupptas som vanligt den 10 januari, 2022.

## <a name="communications"></a>Kommunikationer

Du kan ta reda på vad som finns i arbetet för personal och vad vi har publicerat på följande platser:

- [Dynamics 365 Human Resources översikt](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Utgivningsplaner för Dynamics 365](/dynamics365/release-plans/)

- [Nyheter och ändringar i Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Problemsökning i Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (endast för plattformsspecifika programfel)

- [Personalblogg](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Personal Yammer-community](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Förhandsgranskningsfunktioner i en miljö med begränsat läge

Du kan validera förhandsgranskningsfunktionerna i en miljö med begränsat läge innan du gör dem i produktionsmiljön. Mer information om hur du aktiverar funktioner finns i [Översikt över funktionshantering](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan Funktionshantering kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.

I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan funktionshantering).

När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan funktionshantering anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

Vi rekommenderar starkt förhandsgranskningsfunktionerna i en miljö med begränsat läge eller en testmiljö. Det är bäst att skapa en kopia av den aktuella produktionsmiljön eller databasen i en miljö med begränsat läge så att du kan få den fullständiga upplevelsen av de nya funktionerna med dina data.

Mer information om hur du etablerar en miljö med begränsat läge finns i [etablera ett personalprojekt](hr-admin-setup-provision.md). Mer information om hur du tar bort finns i [Ta bort en instans](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Rapportera buggar

När du testar förhandsgranskningsfunktioner eller försöker med nya funktioner kanske du hittar objekt som inte fungerar som förväntat. Rapportera eventuella fel till [Microsoft Dynamics 365-stödet](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Se även

[Utgivningsplaner för Dynamics 365 och Power Platform](/dynamics365/release-plans)</br>
[Nyheter och ändringar i Dynamics 365 Personal](hr-admin-whats-new.md)</br>
[Livscykelpolicy för programmet](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
