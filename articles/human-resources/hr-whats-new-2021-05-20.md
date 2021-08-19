---
title: Nyheter och ändringar i Dynamics 365 Human Resources 20 maj 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 20 maj 2021.
author: marcelbf
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4519e90e19d0652f855999d1a73ca64777b53b53465d6065987afc1cf2494187
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731947"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 20 maj 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4189.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Plattformsuppdatering 10.0.18 (42) | -- | [Plattformsuppdateringar för version 10.0.18 av Finance and Operations-appar (maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| Appen Human Resources för nu Microsoft Teams har stöd för halvdagsdefinitioner och funktioner för uppdelade dagar | -- | [Hantera begäranden om ledighet i Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  beskrivning |
| --- | --- | --- |
| 583776 | Massanmälningar av medarbetare till tjänstledighetsplaner orsakar ett dupliceringsfel | Denna information har åtgärdats med den senaste versionen och registreringar av massanställningsplan ska bearbetas. |
| 582263 | Det går inte att köra bearbetning av livscykelhändelsen för alla arbetare samtidigt | När fältet **Arbetare** lämnas tomt för bearbetning av livscykeln bearbetas alla arbetare. |
| 558383 | Primär mottagare som inte markerats som 100 % om standarddesigner inte har valts | Felet har åtgärdats så att användaren bara behöver välja primär mottagarväxling.|
| 509404 | Analys av avdelningspersonal tar inte hänsyn till medarbetarnas förflyttningar mellan avdelningarna |Analyserna har uppdaterats så att de inkluderar överföringar av medarbetare mellan avdelningarna.|
| 579420 | Låsa kolumner i rutnätsfunktionen ska ännu inte vara tillgänglig | Funktionen **Fryskolumnerna i rutnät** som inte är tillgängliga i Personal, listas som tillgängliga i Funktionshantering. Funktionen har tagits bort från listan över funktioner som ska aktiveras. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Stöd för anpassade fält i behörighetsregler för förmånshantering | [Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Konfigurera berättiganderegler](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro | [Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2147528) | [Begära ledig tid](hr-employee-self-service-request-time-off.md)|
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md)|
| Granskning av periodiseringstransaktion för tjänstledighet | - | [Granskning av periodiseringstransaktion för tjänstledighet](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
|  Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
