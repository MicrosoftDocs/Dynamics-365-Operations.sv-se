---
title: Nyheter och ändringar i Dynamics 365 Human Resources 2 december 2020
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 2 december 2020.
author: marcelbf
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 36d82efa182bff12442d51908d634cbddbd13fa9
ms.sourcegitcommit: fc852ae4939089a294d00fdf9cad8d6372ffb012
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "5080048"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources 2 december 2020

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3788.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Chefer som kan skicka rekryteringsbegäranden för befattningar | [Chefer kan skicka en rekryteringsbegäran för öppna befattningar](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Lägg till en rekryteringsbegäran](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Förbättrad kandidatprofil i personalhantering | [Förbättrad kandidatprofil i personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Lägga till eller redigera en kandidatprofil](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Aktivera förenklad integration med rekryteringsleverantörer | [Aktivera förenklad integration med rekryteringsleverantörer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrytera jobbkandidater](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |
| Anpassade länkar i självbetjäning för chef | [Anpassade länkar i självbetjäning för chef](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Anpassade länkar i självbetjäning för chef](https://aka.ms/MSSCustomLinks) |


### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans | beskrivning |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult ska inkludera datetime som användes i bearbetningen. | BenefitEligibity bearbetningsresultat innehåller nu datetimestamp för senaste bearbetning, som saknades tidigare. |
| 526903 | Förmånsregistrering misslyckas för planer med beroenden när **automatiskt utvalda tilldelningar** aktiveras i **Delade personalparametrar**. | Åtgärdade problemet där förmånsregistrering misslyckas för beroende när alternativet **Automatiskt utvalda tilldelningar** aktiverades för standardtilldelningar. |
| 521922 | Parametern **Visa frånvaro utan detalj** visar information om ledighetsförfrågningar i teamets frånvarokalender. | Tjänstledighetstyp, tjänstledighetstypens färg och dag visas i teamets frånvarokalender när **Visa frånvaro utan detalj** var inställd på **Ja** i **Tjänstledighet- och frånvaroparametrar**. Det här har åtgärdats och nu visas inte tjänstledighetstypen och standarfärgen för tjänstledighet (mörkblå) används för alla tjänstledighetstyper i teamets frånvarokalender. |
| 527316 | Titeländringar för jobb-, befattnings- och arbetstagarmeddelanden synkroniseras inte. | En titelrelation har tidigare lagts till i jobb-, befattnings- och arbetstagarentiteter. Synkroniseringen för den här relationen fungerar för synkroniseringen från personal till Dataverse, men fungerade inte för meddelanden från Dataverse. Detta har åtgärdats. |
| 512275 | Ta bort färgalternativen från **Tjänstledighets- och frånvaroparametrarna**. | Nu när färgerna har definierats på tjänstledighetstypen behövs inte längre färgalternativen i **tjänstledighets- och frånvaroparametrar**, så de tas bort. |
| 437112 | Vilseledande felmeddelandetext under medarbetarens befattningstilldelning. | Ett felmeddelande har uppdaterats vid anställning av en arbetare och ett försök att tilldela arbetaren till en befattning som inte är aktiv. Uppdaterat meddelande **Den angivna befattningen är inte aktiv från och med anställningens startdatum. Kontrollera befattningens varaktighet.** |
| 527816 | Prestandaproblem med sidan **Ledighet**. | Prestanda har förbättrats på sidan **Ledighet**. |
| 523158 | BenefitPeriodMigrationUpgrade och BenefitPlanMigrationUpgrade körs inte. | Åtgärdade problem med jobb för förmånsmigrering relaterade till **period** och **plan** utförs inte korrekt. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Personal-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Personal-app i Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Förbättrade arbetsflödesförfrågningar och godkännanden | [Arbetsflöden för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integration med LinkedIn Talent Hub | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
|Företagsövergripande vy av tjänstledighet för chefer | [Företagsövergripande vy av medarbetares tjänstledighet för chefer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurera parametrar för ledighet och frånvaro](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Ge ytterligare inblick i tjänstledighetssaldon| [Ge ytterligare inblick i tjänstledighetssaldon](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Hantera tjänstledighet för medarbetare](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Chefer som kan skicka rekryteringsbegäranden för befattningar | [Chefer kan skicka en rekryteringsbegäran för öppna befattningar](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Lägg till en rekryteringsbegäran](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Förbättrad kandidatprofil i personalhantering | [Förbättrad kandidatprofil i personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Lägga till eller redigera en kandidatprofil](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Aktivera förenklad integration med rekryteringsleverantörer | [Aktivera förenklad integration med rekryteringsleverantörer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrytera jobbkandidater](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2020 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)
