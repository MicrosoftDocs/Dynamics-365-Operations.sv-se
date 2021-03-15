---
title: Nyheter och ändringar i Dynamics 365 Human Resources 21 januari 2021
description: Detta ämne beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för den 21 januari 2021.
author: marcelbf
manager: tfehr
ms.date: 01/21/2021
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
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: af847ed36187c0d0629ce4063d9c17cb0fa8cfcf
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060852"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 21 januari 2021

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3866.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Plattformsuppdatering 10.0.16(40) | -- | [Plattformsuppdateringar för version 10.0.16 av Finance and Operations-appar (februari 2021)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16) |
| Förbättrade arbetsflödesförfrågningar och godkännanden | [Arbetsflöden för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Efterlevnadsuppdateringar för sjukförsäkring för formulär 1095-C, formulär 1095-B och elektronisk rapportering i äldre förmåner | -- | -- | 
| Förmånshantering har nu stöd för efterlevnadsrapportering för sjukförsäkring för USA-baserade juridiska personer | -- | [Generera sjukförsäkringsrapporter i förmånshanteringen](hr-benefits-management-aca-reports.md) |
| Förmånshantering har nu nivåer för förmånssats, och dubbla nivåentiteter för förmånssats visas  | -- | -- |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 533079 | Navigeringsfelet "Formuläret anropades felaktigt" när vi försöker titta på avdrag. | Fast fel vid visning av förmånsavdrag med vyn **Från och med datum**. |
| 543641 | Postnummer fylls inte i för elektronisk rapportering.  | Åtgärdade en intern bugg för postnummer som inte visas i elektroniska sjukförsäkringsrapporter för förmånshantering när disponeringskod är M till Q. |
| 542815 | Med hjälp av den personliga kontaktskärmen i Självbetjäning för medarbetare kan medarbetare se andras personliga kontakter. | Åtgärdade fel där formuläret **Redigera** för medarbetarnas personliga kontakter inte begränsar frågan tillräckligt för att garantera att endast en enskild personlig kontakt hämtas, vilket gör det möjligt för en användare att använda kortkommandon för att visa andra personers kontakter. |
| 536157 | Det går inte att öppna sidan **Microsoft Dataverse-integrering** i Systemadministration på grund av anropet IsVirtualEntityPackageInsadministration(). | Problemet förhindrar att sidan **Microsoft Dataverse-integrering** läses in i Personal. |
| 533079 | Navigeringsfelet "Formuläret anropades felaktigt" när vi försöker titta på avdrag. | Åtgärdade fel som uppstår i formuläret **Avdrag** för förmånshanteringen när den visas **från och med datum**. |
| 537264 | Snabbfliken **Personlig information** saknas i kandidatposten. | Personlig information för kandidaten är nu tillgänglig på kandidatposten. |
| 537267 | **Yrkeserfarenhet** visas inte på interna kandidatposter. | Snabbfliken **Yrkeserfarenhet** visas nu på interna kandidatposter. Om kandidaten var intern ersattaes tidigare **Yrkeserfarenhet** av **Anställningshistorik**, det vill säga kandidatens anställningshistorik inom orgnaisationen. Båda är tillämpliga och måste visas för interna kandidater. |
| 537067 | **Tillåtet att kontakta arbetsgivare** visas inte. | Kontrollen **Tillåtelse att kontakta arbetsgivare** lades till i fönstret **Redigera yrkeserfarenhet** för en kandidatpost. |
| 525957 | **Kandidatstatusen** uppdateras inte för interna kandidater när överföringen är slutförd. | När en överföring är slutförd (knappen **Byt position** eller **Fortsätt** väljs på sidan **Överför medarbetare till ny befattningstilldelning**) måste **Status** på kandidatposten ändras till **Anställd**. |
| 537051 | Valutasymboler för indiska rupier och turkiska lira synkroniseras inte korrekt till Dataverse | Symboler för indiska rupier och turkiska lira synkroniseras nu korrekt till Dataverse. |
| 534846 | Rekryteringsregister måste aktiveras för Datahantering. | De nya registren som skapas för rekryteringsförfrågningar och kandidater aktiveras nu för Datahantering. Då aktiveras ändringsspårning för registren, så att OData-ändringsspårning aktiveras i de virtuella Dataverse-registren. |
| 533474 | Korrigera saknad referens till Microsoft.SqlServer.XEvent.wd. | Sammansättningsundantag för Microsoft.SqlServer.XEvent.dll spärrade virtuella Dataverse-register från att konfigureras i vissa miljöer. |
| 481122 | Arbetsytan **Personer** visar pensionerade befattningar. | Pensionerade befattningar visades som öppna befattningar i arbetsytan **Personer**. Pensionerade befattningar visas inte längre. | 
| 541978 | Lägg till primär e-postadress i entiteten BaseWorker. | Denna ändring lade till medarbetarens primära e-postadress i HcmWorkerBaseEntity. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Personal-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Personal-app i Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Integration med LinkedIn Talent Hub | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Företagsövergripande vy av tjänstledighet för chefer | [Företagsövergripande vy av medarbetares tjänstledighet för chefer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurera parametrar för ledighet och frånvaro](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Ge ytterligare inblick i tjänstledighetssaldon| [Ge ytterligare inblick i tjänstledighetssaldon](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Hantera tjänstledighet för medarbetare](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Chefer som kan skicka rekryteringsbegäranden för befattningar | [Chefer kan skicka en rekryteringsbegäran för öppna befattningar](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Lägg till en rekryteringsbegäran](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Förbättrad kandidatprofil i personalhantering | [Förbättrad kandidatprofil i personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Lägga till eller redigera en kandidatprofil](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Aktivera förenklad integration med rekryteringsleverantörer | [Aktivera förenklad integration med rekryteringsleverantörer](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrytera jobbkandidater](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Kommer snart
| Funktion | Information |
| --- | --- |
| E-postbekräftelse för förmånsanmälningar | Denna funktion erbjuder alternativet att skicka ett e-postmeddelande till medarbetarna när dessa checkar ut från förmånsanmälan i medarbetarnas självbetjäning. Mer information finns i [Konfigurera parametrar för förmånshantering per företag](hr-benefits-setup-parameters-per-company.md). |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminologiuppdateringar för Microsoft Dataverse

Från och med november 2020 har Common Data Service bytt namn till [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Se det [officiella beskedet](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) i Power Apps-bloggen för mer information. Tillsammans med denna namnändringen har viss terminologi i Dataverse uppdaterats. Till exempel heter *enhet* numera *tabell* och *fält* heter numera *kolumn*. Mer information finns i [terminologiuppdateringar](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

I denna version har terminologin som är relaterad till Dynamics 365 Human Resources-integreringen med Dataverse uppdaterats i hela programmet för att återspegla dessa ändringar. Formuläret **Common Data Service-integrering** heter exempelvis numera **Microsoft Dataverse-integrering**.

Mer information om Dynamics 365 Human Resources-integreringen med Microsoft Dataverse finns i [Konfigurera Microsoft Dataverse-integrering](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) och [Konfigurera virtuella Microsoft Dataverse-register](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2020 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]