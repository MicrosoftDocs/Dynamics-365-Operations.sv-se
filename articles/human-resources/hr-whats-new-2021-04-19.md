---
title: Vad är nytt eller har ändrats i Dynamics 365 Human Resources (19 april 2021)
description: Detta ämne beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources per den 19 juli 2021.
author: marcelbf
ms.date: 04/19/2021
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
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadad34be31f6522654bc3af47a4f71695dcc5fea7f0b3e760ff26d79d88eb4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722521"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Vad är nytt eller har ändrats i Dynamics 365 Human Resources (19 april 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4113.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Plattformsuppdatering 10.0.17 (41) | -- | [Plattformsuppdateringar för version 10.0.17 av Finance and Operations-appar (april 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Stöd för anpassade fält i formulär för förmånshantering | [Stöd för anpassade fält i förmånshantering](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Hantering av förmåner – översikt](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 552164 | **Sparad vy** i **Självbetjäning för medarbetare > Öppna kurser** fungerar inte för kurser som innehåller en agenda | Om en sparad vy används på öppna kurser (ESS) och en av kurserna har en kopplad agenda, visar vyn inte längre flera rader för den kursen. |
| 560614 | **Förmåner > Alternativ för livshändelser** visar avvikelser i verktygstipsdokumentationen och kodbeteendet. | Uppdaterade knappbeskrivningar i **Alternativ för livshändelse** för att visa korrekt beteende. |
| 560616 | **Förmåner > Alternativ för livshändelser** kan redigeras i förmånsplanen för medarbetare, men ändringarna påverkas inte. | Uppdaterat beteende för alternativ för livshändelse växlar till aktivera eller inaktivera - baserat på beroende alternativ - per verktygstipsdokumentation. |
| 565054 | Det gick inte att visa listinnehåll för **Medarbetare utan anställning** när **Avancerad åtkomst** är aktiverat. | Denna version löser problemet med att endast systemadministratörer kan visa innehållet i listan **Medarbetare utan anställning** när **Avancerad åtkomst** är aktiverat. Eftersom denna korrigering är en säkerhetsändring måste du välja den i funktionshanteringen. När funktionen väl är aktiverad kommer de roller som har åtkomst till formuläret att se innehållet, även om avancerad åtkomst är aktiverad. Mer information finns i [Medarbetare utan anställning](hr-personnel-workers-without-employment.md). |
| 570586 | Tjänstledighetsvalidering misslyckas när anställningen slutar före den senaste transaktionen för medarbetaren i alla tjänstledighetsplaner. | När en anställning är slut misslyckas inte valideringen av ledighetsförfrågningar baserat på medarbetarens tjänstledighetstransaktioner.|
| 570783 | Att aktivera och inaktivera tjänstledighet mellan företag i gemensamma parametrar för Personal ändrar det som medarbetare som är anställda i ett enskilt företag ser i tjänstledighetsansökningar. | Medarbetare som är anställda i ett enskilt företag ser inga ändringar i begäran om ledighet om parametern är aktiverad eller inaktiverad. |
| 572343 | Obligatorisk orsakskod visas inte när funktionen för företagsövergripande tjänstledighet aktiveras. | Orsakskoden visas nu som förväntat när funktionen företagsövergripande tjänstledighet har aktiverats. |
| 573676 | Kan inte lägga till **Period** i **Förmånshantering > Länkar > Förmånsplaner**. | Korrigerade buggar där **Period** inte kunde läggas till eller uppdateras i befintligt formulär för **Förmånsplan**. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro | [Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2147528) | [Begära ledig tid](hr-employee-self-service-request-time-off.md)|
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |
| Plattformsuppdatering 10.0.18 (42) | Plattformsuppdatering 10.0.18 planeras i och med nästa serviceversion den 17 maj 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.18 av Finance and Operations-appar (maj 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Stöd för anpassade fält i behörighetsregler för förmånshantering  | [Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
