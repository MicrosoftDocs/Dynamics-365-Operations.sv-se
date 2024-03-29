---
title: Vad är nytt eller har ändrats i Dynamics 365 Human Resources (5 april 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 5 april 2021.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9388b2f43762bedf07c89a7a565935d2043ee90c
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068014"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Vad är nytt eller har ändrats i Dynamics 365 Human Resources (5 april 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4074.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Hindra medarbetare från att redigera affärskontaktinformation | [Hindra medarbetare från att redigera affärskontaktinformation](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Begränsa redigering av personlig information](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  Beskrivning |
| --- | --- | --- |
| 550852 | Knappen **Godkännande** valideras inte med obligatoriska fält som ställts in i formuläret **Granska**. | När du anger ett fält som obligatoriskt i formuläret **Granska** och publicerar ändringarna för den ansvariges roll, validerar inte formuläret som förväntat. |
| 559564 | Historiska medarbetaråtgärder för ändring av fast kompensation leder till ett fel för uppsagda användare. | Medarbetaråtgärden för kompensation till en före detta medarbetare förorsakar ett fel. När en medarbetare lämnar företaget leder medarbetaråtgärden om befordran före uppsägning till ett fel. |
| 560074 | Listrutan för anställningskategori filtrerar inte **Medarbetarkategori** utan visar kategorier för medarbetare och leverantörer. | I formuläret **Medarbetare** ska listrutan **Anställningskategori** ange kategorier för antingen medarbetare eller leverantör baserat på medarbetartyp. |
| 567388 | En del av informationen för nyskapade medarbetare synkroniseras inte direkt med registret **cdm_worker** i Dataverse. | När du skapar en ny medarbetarpost synkroniseras den nya posten med registret **cdm_worker** i Dataverse, men alla egenskaper inkluderas inte i Dataverse-posten. |
| 563837 | Funktioner som inte är tillgängliga i Personal-visningen. | Flera funktioner som inte gäller för Personal-visning i Funktionshantering. Dessa funktioner tas nu bort från listan över funktioner som är tillgängliga för aktivering i Personal. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Färdigheter som en chef har angett för sina medarbetare kan godkännas automatiskt av ett arbetsflöde | Kommer snart. |
| Plattformsuppdatering 10.0.17 (41) | Plattformsuppdatering 10.0.17 planeras i och med nästa version den 19 april 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.17 av appar för ekonomi och drift (april 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
