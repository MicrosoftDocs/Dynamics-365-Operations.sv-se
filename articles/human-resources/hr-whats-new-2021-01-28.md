---
title: Nyheter och ändringar i Dynamics 365 Human Resources 28 januari 2021
description: Detta ämne beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för den 28 januari 2021.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d59e242421b1b86c32f9009ae6ae17e0f161a2e2
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689310"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 28 januari 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3906.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Integrera orsakskoder för förmåner i arbetsytan för **Personalhantering** | -- | [Ställ in orsakskoder](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.


| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 539456 | I kalendern visas tjänstledighetstypen i hovrad text när parametern **Visa endast frånvaro utan detaljer** är aktiverad. | När alternativet **Visa endast frånvaro utan detaljer** har aktiverats visas datumet för begäran hovrat. |
| 528907 | Om medarbetare beviljas åtkomst till en juridisk person i medarbetarroller leder detta till att chefer inte kan se en saldoaktivitet för medarbetare i området **Mitt team** i självbetjäningen för medarbetare. |Om du ställer in det här alternativet kan chefer fortsätta att se aktiviteten för tjänstledighetssaldo. |
| 526280 | Behörighetsfel för HcmWorkerEntity, HcmEmployeeEntity och HcmContractorEntity. | Användare med en icke-systemadministratörsroll kunde inte exportera de entiteter som listats på grund av ett behörighetsfel i fältet NationalityCountryRegion. Användarna behöver även fortsättningsvis följande behörigheter för att exportera denna information: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain samt HCMContractorEntityView. |
| 542147 | Fälten för **Bankkontonummer** och **Organisationsnummer** är obligatoriska när du lägger till bankkonto via självbetjäningen för medarbetare. | Vi har åtgärdat felet där medarbetarna var tvungna att ange fälten **Bankkontonummer** och **Organisationsnummer** vid inmatning av bankkontoinformation. Dessa fält är inte längre obligatoriska när du sparar ny bankkontoinformation. |
| 543641 | Postnummer fylls inte i för elektronisk rapportering. | Åtgärdade en bugg där postnummer inte fylldes i i sjukförsäkringsrapport för täckningskoder L till Q. |
| 545402 | Lägg till flödesändring för filen UserRouing.js om du vill ta bort 404-fel. | Användaren bör inte längre se 404-fel i konsolen. |

## <a name="in-preview"></a>I förhandsgranskning   

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Personal-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Personal-app i Teams](./hr-admin-teams-leave-app.md)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Företagsövergripande vy av tjänstledighet för chefer | [Företagsövergripande vy av medarbetares tjänstledighet för chefer](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurera parametrar för ledighet och frånvaro](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| E-postbekräftelse för förmånsanmälningar | Denna funktion erbjuder alternativet att skicka ett e-postmeddelande till medarbetarna när dessa checkar ut från förmånsanmälan i medarbetarnas självbetjäning. Denna funktion blir tillgänglig den 1 februari. Mer information finns i [Konfigurera parametrar för förmånshantering per företag](hr-benefits-setup-parameters-per-company.md). |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Terminologiuppdateringar för Microsoft Dataverse

Från och med november 2020 har Common Data Service bytt namn till [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Se det [officiella beskedet](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) i Power Apps-bloggen för mer information. Tillsammans med denna namnändringen har viss terminologi i Dataverse uppdaterats. Till exempel heter *enhet* numera *tabell* och *fält* heter numera *kolumn*. Mer information finns i [terminologiuppdateringar](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

I denna version har terminologin som är relaterad till Dynamics 365 Human Resources-integreringen med Dataverse uppdaterats i hela programmet för att återspegla dessa ändringar. Formuläret **Common Data Service-integrering** heter exempelvis numera **Microsoft Dataverse-integrering**.

Mer information om Dynamics 365 Human Resources-integreringen med Microsoft Dataverse finns i [Konfigurera Microsoft Dataverse-integrering](./hr-admin-integration-common-data-service.md) och [Konfigurera virtuella Microsoft Dataverse-register](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]