---
title: Nyheter och ändringar i Dynamics 365 Human Resources 3 maj 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 3 maj 2021.
author: marcelbf
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df8bd0277e4f27c23ba25c886d12f589913e5d46
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066236"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 3 maj 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4140.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Lägg till infofält när livscykelhändelser skapas. | - | När du skapar en livscykelhändelse visas ett meddelande i informationsfältet som anger vilken typ av livslängdshändelse som skapats.

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  Beskrivning |
| --- | --- | --- |
| 559312 |  Nivå visas inte när en fast kompensationsplan skapas för en medarbetare. |  När det finns ett tidszonfel mellan användarens tidszon och företagets tidszon kan kompensationsnivån på jobbet inte läsas. Frågan har uppdaterats för hämtning baserat på UTC-tid. |
| 573676  | Det går inte att lägga till en ny period i formuläret **Förmånsplan**. | Uppdaterade formuläret så att knappen **Ny** aktiveras under fliken **Period** i **Förmånsplaner**. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro | [Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2147528) | [Begära ledig tid](hr-employee-self-service-request-time-off.md)|
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md)|
| Granskning av periodiseringstransaktion för tjänstledighet | - | [Granskning av periodiseringstransaktion för tjänstledighet](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Plattformsuppdatering 10.0.18 (42) | Plattformsuppdatering 10.0.18 planeras i och med nästa serviceversion den 17 maj 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.18 av program för Ekonomi och drift (maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Stöd för anpassade fält i behörighetsregler för förmånshantering  | [Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

