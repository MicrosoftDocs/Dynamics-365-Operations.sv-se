---
title: Nyheter och ändringar i Dynamics 365 Human Resources 8 mars 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 8 mars 2021.
author: marcelbf
ms.date: 03/08/2021
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
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 133cfffadabade8f7770b4853e14b769c5b961370546e3104d6db26bc0c6331a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719078"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 08 mars 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4017.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Företagsövergripande vy av tjänstledighet för chefer | [Företagsövergripande vy av medarbetares tjänstledighet för chefer](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurera parametrar för ledighet och frånvaro](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 486611 | Tjänstledighet visas i tjänstledighetskalendern när **Inaktivera tjänstledighet i alla kalendrar** är aktiverat | Om **Inaktivera tjänstledighet i alla kalendrar** är aktiverad ska du inte längre visa information när funktionen tjänstledighet och frånvarokalender har aktiverats.|
| 508972 | Tjänstledighets- och frånvaro banktransaktionsenhet som saknar validering av anmälan | När du använder banktransaktionsenheten Tjänstledighet och frånvaro kan medarbetare som inte har anmälts till en plan inte längre importeras. |
| 554854 | Uppdatering av kalender i fel för anställningsenhet om standardvärdet juridisk person i användaralternativen är olika | Om anställningsenheten används för att uppdatera kalendern för en medarbetare får inte längre ett felmeddelande om standardenheten för juridisk person i användaralternativen skiljer sig åt. |
| 558347 | "Det går inte att skapa en post i formulärkonfigurationer (FormRunConfiguration)" visas när startsidan läses in. | Anpassningar orsakar felet "Det går inte att skapa en post i formulärkonfigurationer (FormRunConfiguration)" visas när startsidan läses in. |
| 557327 | Arbetsyta för förmånshantering: Lucka visas ovanför rutnätet. | Problem med fast användarupplevelse där en oavsiktlig lucka visas i registerrutnätets gränser i förmånsarbetsytan. |
| 557334 | Arbetsyta för förmånshantering: Listrutan för valet **Period** bör endast visas på fliken **Sammanfattning** | Listrutan för val av förmån **Period** visas endast när fliken **Sammanfattning** är aktiv i arbetsytan Förmåner och inte i avsnitten **Processresultat** och **Länkar**. |
| 557336 | Arbetsyta för förmånshantering: texten **Öppen registrering med utcheckade planer** trunkeras i panelvyn | Ändrad text i panelvyn till **Utcheckade planer... öppen registrering** för att undvika trunkering av nödvändigt sammanhang. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Hindra medarbetare från att redigera affärskontaktinformation | [Hindra medarbetare från att redigera affärskontaktinformation](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Begränsa redigering av personlig information](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]