---
title: Nyheter och ändringar i Dynamics 365 Human Resources 26 september 2020
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 26 september 2020.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f78201585101e2848eded69e03d5eb4c22d7e9a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066775"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources 26 september 2020

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Dynamics 365 Human Resources. Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3589-hf.3.

### <a name="new-features"></a>Nya funktioner

Följande funktion är i allmänhet tillgänglig i den här versionen:

- **Nu finns plattformsuppdatering 10.0.13**: Mer information om uppdateringen finns i [Plattformsuppdateringar för version 10.0.13 av appar för ekonomi och drift (oktober 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Det kan finnas uppdateringar till den här artikeln för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
| --- | --- | --- |
| 469495 | Uppdatera standardrutnät och dialogruta för ekonomiska dimensioner | Standardrutnätet för ekonomiska dimensioner och dialogruta ärr uppdaterade i Personal. |
| 474887 | Arbetsuppgiften för ledighetsansökan öppnar fel länk i ett manuellt beslut | När en arbetsflödeskonfiguration innehåller ett manuellt beslut, öppnar jag fellänken genom att navigera till ledighetsansökan från **arbetsuppgifter som har tilldelats till mig**, med antingen ett tomt formulär eller en ledighetsansökan som har skapats av aktuell användare i stället för den som har tilldelats dem för det manuella beslutet. |
| 474962 | Entiteten parametrar för tjänstledighet och frånvaro har fält med oklara etiketter | Etiketterna för entiteten parametrar för tjänstledighet och frånvaro uppdateras så att de blir tydligare. |
| 481401 | Periodiseringsbehandling hänger sig vid utgångsdatum för periodisering efter periodisering startdatum och i slutet av månaden | Periodiseringsbehandling uppdateras till att inte ha en försening när datumet för periodiseringen är efter periodiseringens startdatum och i slutet av månaden. |
| 447167 | Utgångna postlister inkluderar inaktiva arbetare | Fliken **utgående poster** i **personalhantering** inkluderar inaktiva arbetare. Nu ingår bara aktiva arbetare. |
| 486840 | Fel tjänstledighetsansökan öppnas från **arbetsuppgifter som tilldelats mig** | Om du väljer en tjänstledighetsansökan från **arbetsuppgifter som har tilldelats till mig** öppnas den senaste tjänstledighetsansökan som tilldelats den aktuella användaren. |
| 506868 | Dataverse **Rubrik**-fältet har inte angetts för entiteten **Jobbefattning** | Fältet **Rubrik** i entiteterna **Jobb** och **Jobbefattning** visas som ej specificerade. Fältet **Rubrik** visas nu. |
| 430359 | Kan inte komma åt checklisteuppgifter för avregistrering med chef och medarbetarroller tilldelade | Arbetare med ett framtida uppsägningsdatum kunde inte komma åt sina rapportuppgifter om de bara hade rollen medarbetare eller chef. Nu kan användare med endast en medarbetare eller chefsroll komma åt avregistreringsuppgifter med ett framtida uppsägningsdatum. |
| 458102 | Ny medarbetare visas inte på entiteten **Information om arbetarlön** när den skapas | Nya medarbetare tas med i entiteten information om arbetarlön utan att du behöver öppna löneinformationen för medarbetaren innan du exporterar enheten. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Personal-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Personal-app i Teams](./hr-admin-teams-leave-app.md)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Förbättrade arbetsflödesförfrågningar och godkännanden | [Arbetsflöden för organisation och personalhantering](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Kommer snart

Följande nya funktion är schemalagd för framtida versioner:

- [Anpassade länkar i självbetjäning för chef](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2019 utgivningscykel 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Ytterligare resurser

[Nyheter eller ändringar i Personal](hr-admin-whats-new.md)
[Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Uppdatera process](hr-admin-setup-update-process.md)
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
