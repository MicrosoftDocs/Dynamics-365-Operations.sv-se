---
title: Nyheter och ändringar i Dynamics 365 Human Resources 22 oktober 2020
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources.
author: jcart1106
manager: tfehr
ms.date: 10/22/2020
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
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 513fc3b35f0b6a7f5d9703d2b5eb4109289a189a
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529992"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources 22 oktober 2020

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources. Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3680.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Plattformsuppdatering 10.0.14(38) | -- | [Plattformsuppdateringar för version 10.0.14 av Finance and Operations-appar (2020 november)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14) |
| Arbetsflöden för organisation och personalhantering | [Arbetsflöden för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer| Utleverans  | beskrivning|
| --- | --- | --- |
| 437922 | Import av FMLA timmar med DMF-entiteten resulterar i ett skrivskyddat fel. | Om du använder enheten FMLA timmar för att importera timmar som är kopplade till ett FMLA-ärende misslyckades. Vi har lagt till logik för att se till att de importerade timmarna inte överskrider det antal timmar som återstår för ärendet. |
| 512019 | Felaktigt belopp för **senaste överföring**. | På sidan **Ledighet** visas ett felaktigt **Från och med** till den första dagen i nästa budgetperiod visas ett felaktigt belopp för **senaste överföring** för typ **Årlig ledighet**. Nu visas rätt belopp. |
| 458639 | Entiteten **Arbetarkontakter** stöder inte ändringsspårningsläge. | Vi uppdaterade entiteten **Arbetarkontakter** så att du kan använda den för att ta med dina egna databas (BYOD) scenarier.|
| 505347 | Utbildningsansvariga kan skicka en begäran om att lämna en medarbetare när den strömlinjeformade funktionen för arbetare aktiverades. | Andra roller än personal assistenten och personalchef får inte skicka ansökningar om ledighet för medarbetare. |
| 513490 | Loggning av fördelarhantering: lägg till loggning för planer utan täckningsalternativ. | Vi aktiverade loggningsresultat för **Planera utan täckningsalternativ**. Nu visas de i tabellen **Processresultat** och de sorteras korrekt så att de visas överst. |
| 517021 | Det går inte att välja flera planer med samma **plantyp** kod om **plantypen** kan anmäla sig till en per typ. | Vi har ändrat begränsningarna för urvalsplaner där endast en registrering tillåts. Begränsningarna är nu på **plantypskoden** nivå i stället för **plantyp**. Den här ändringen gör det möjligt att planera som HSA och FSA, som är både samma typ, men du kan ge dem en separat **plantypskod**. På så sätt kan du välja båda för samma registreringsperiod. |
| 444791 | Kan inte se ersättning i självbetjäning för medarbetare när **begränsad åtkomst** är aktiverat i kompensationsplanen. | I kort självbetjäning för medarbetare **Kompensation**, det aktuella ersättningsbeloppet och ökningsprocenten som visas "0" om den anställde var inskriven i en plan med **Begränsa åtkomsten** aktiverat och tilldelats specifika roller. Vi har löst problemet så att medarbetaren och chefen alltid kan se kompensationsdetaljer för sig själva och deras direkt rapporter. |
| 457542 | Uppdatera kursinformation när kursen stängs uppdaterar inte också samma information för medarbetaren som tog kursen. | Medarbetarens information uppdateras nu på rätt sätt när du ändrar kursinformation när en kurs stängs och sedan öppnas igen. |
| 515342 | Det går inte att infoga data via **CDSLeaveRequestDetailEntity**. Företaget hittas inte eller finns inte. | Du kan nu använda **CDSLeaveRequestDetailEntity** till infoga data. |
| 514743 | Fel i formuläret **E-postparameter** vid användning av Microsoft Exchange. | Meddelandet "Det gick inte att läsa in filer eller sammansättning..." visas på sidan **E-postparametrar** när e-postleverantören ställts in på **Växel**. Denna korrigering tillåter också **E-postparametrar** läses in och sparas som förväntat. |


## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Human Resources-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources-app i Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Förbättrade arbetsflödesförfrågningar och godkännanden | [Arbetsflöden för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Virtuella enheter i Common Data Service för Human Resources | [Expandera Dynamics 365 Human Resources grundläggande data i Common Data Service](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Konfigurera Common Data Service virtuella enheter](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integration med LinkedIn Talent Hub | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integration med LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Anpassade länkar i självbetjäning för chef | [Anpassade länkar i självbetjäning för chef](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Anpassade länkar i självbetjäning för chef](https://aka.ms/MSSCustomLinks) |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2020 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)
