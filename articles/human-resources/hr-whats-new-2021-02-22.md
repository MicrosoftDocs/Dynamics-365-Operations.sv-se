---
title: Nyheter och ändringar i Dynamics 365 Human Resources 22 februari 2021
description: Detta ämne beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för den 22 februari 2021.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 53e9c42f718665165be97e5022a9e767b0436e59
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802225"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 22 februari 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3988.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Dynamics 365 Human Resources-app för Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources-app i Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 529994 | Ändring av **Känd som** i formuläret **Arbetare** utlöser ingen Dataverse-uppdatering | Åtgärdat ett problem där Dataverse inte uppdateras när fältet **Känd som** uppdateras i formuläret **Arbetare**. |
| 532651 | Kompensationsanalys PBI-rapporten använder inte valutakonvertering när mått beräknas för alla företag | Åtgärdat ett problem där Kompensationsanalys PBI-rapporten inte stämmer vid valutakonverteringar. |
| 552226 | Bearbetningen av livshändelse stänger och öppnar planer på nytt flera gånger för händelse av enstaka livshändelse  | Åtgärdat ett problem där en medarbetare finns i flera juridiska personer och en livstidshändelse inträffar genererar en livstidshändelsepost för varje juridisk person som medarbetaren finns i. När du bearbetar livshändelser måste den juridiska personen som ska bearbetas vara vald. Bearbetningslogiken begränsar dock inte sig själv till den här juridiska personen. I stället bearbetar den för alla juridiska personer och stänger och öppnar planerna igen i den valda juridiska personen. Den här åtgärden är en händelse som används för att bearbeta flera gånger inom samma juridiska person, vilket leder till att varje plan stängs/öppnas på nytt som påverkas av händelsen. |
| 518064 | Endast en beroende person väljs i de berättigade planerna när fler än en markeras som standarddesigner | Har åtgärdat en fråga där flera standarddesigner inte markeras automatiskt i de berättigade planerna. Du kan nu även ange att en person i första hand ska föra in en personlig kontakt. Den primära målberättigade listan visas som 100 % i de berättigade planerna när det finns flera aktuella. |
| 552365 | Ta med din egen databas (BYOD) exportjobb misslyckas efter att du har uppgraderat till uppdatering av plattform 40 | Korrigerat ett problem där BYOD-exporter misslyckas efter uppdatering av plattform 40 används i miljön. |
| 547123 | Begränsa antalet uppgifter som frågor finns i att göra-lista på instrumentpanelen | Antalet uppgifter som visas i att göra-listan är nu begränsat till 15 för att korrigera ett prestandaproblem som orsakas av för många uppgifter som försöker läsas in. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Företagsövergripande vy av tjänstledighet för chefer | [Företagsövergripande vy av medarbetares tjänstledighet för chefer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurera parametrar för ledighet och frånvaro](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Hindra medarbetare från att redigera affärskontaktinformation | [Hindra medarbetare från att redigera affärskontaktinformation](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Begränsa redigering av personlig information](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminologiuppdateringar för Microsoft Dataverse

Från och med november 2020 har Common Data Service bytt namn till [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Se det [officiella beskedet](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) i Power Apps-bloggen för mer information. Med denna namnändringen har viss terminologi i Dataverse uppdaterats. Till exempel heter *enhet* numera *tabell* och *fält* heter numera *kolumn*. Mer information finns i [terminologiuppdateringar](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

I denna version har terminologin som är relaterad till Dynamics 365 Human Resources-integreringen med Dataverse uppdaterats i hela programmet för att återspegla dessa ändringar. Formuläret **Common Data Service-integrering** heter exempelvis numera **Microsoft Dataverse-integrering**.

Mer information om Dynamics 365 Human Resources-integreringen med Microsoft Dataverse finns i [Konfigurera Microsoft Dataverse-integrering](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) och [Konfigurera virtuella Microsoft Dataverse-register](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="updates-to-service-deployment"></a>Uppdateringar av tjänstedistributionen

Från och med den 22 februari 2021-versionen justerar vi vår uppdatering av den nationella tjänsten. Justeringarna kommer att innebära att den ordning som globala regioner får uppdateringar av personaltjänsten är tillgängliga i, och ändringar i väntetiden mellan uppdateringsfaserna. Dessa ändringar får oss att gå bättre i linje med säker driftsättningsmetod (SDP) för att förbättra prestandan, kvaliteten och stöd.

Vi fortsätter att följa den två veckor långa distributionstakten. Kunderna kanske emellertid ser att uppdateringar vanligtvis tillämpas i deras Personal-miljöer på en annan dag i tvåveckorsperioden än i tidigare versioner.

Mer information om uppdateringsprocessen för tjänsten finns i [uppdateringsprocessen](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-setup-update-process).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
