---
title: Nyheter och ändringar i Dynamics 365 Human Resources 6 september 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 6 september 2021.
author: marcelbf
ms.date: 09/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 03f832a6a3a099c472b781f7e2258ac575127101
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070013"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 6 september 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4443.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | I denna version uppdaterar vi vyn för arbetsyta för frånvaroansvarig. Mer information finns i [konfigurera roll för frånvaroansvarig](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Konfigurera kopplingsbehov per tjänstledighetstyp | [Konfigurera kopplingsbehov per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Konfigurera ledighetsenheter per tjänstledighetstyp | [Konfigurera ledighetsenheter per tjänstledighetstyp](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Konfigurera typer av tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
|---|---|---|
| 610128 | Fel i publiceringsdata vid användning av HcmDiscussionOverallCommentEntity | När data publiceras från en Excel-arbetsbok till enheten HcmDiscussionOverralCommentEntity inträffar följande fel: "Det går inte att lokalisera datakällsposten av typen HcmTopicOverrall." |
| 589073 | EEO-1 räknas som "Ej specifik" och tomma värden för fältet **Kön** som värdet "Kvinna". | Om **Man** inte har angetts för fältet **Kön**, rapporten EEO-1 genererar standardvärdet **Kvinna**. |
| 589617 | Saldon för lediga kort, Tillgänglig för inköp och Tillgänglig för försäljning visas inte när användarrollerna begränsas till en specifik juridisk person. | Om användaren (medarbetarrollen) är begränsad till en specifik juridisk person visas saldon inte korrekt på kortet **Ledighetssaldon** och i fälten **Tillgänglig att köpa** och **Tillgänglig att sälja**. |
| 604310 | Fliken Frånvaroansvarig bör vara dold när användaren inte har tilldelats en frånvarohierarki. | För en viss juridisk person, fliken **Frånvaroansvarig** ska döljas i självbetjäningsportalen om inte företagsparametern är aktiverad och minst en frånvarohierarki är kopplad till användaren. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar och inaktiverar funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md) |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Klar att betalas](/dynamics365/human-resources/hr-compensation-payroll) |
| Anpassade fält i Berättigande |[Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Använda anpassade fält i bearbetning av berättigande](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funktion | Information |
|---|---|
| Plattformsuppdatering 10.0.21 (45) | Lansering av plattformsuppdatering 10.0.21 planeras i och med nästa serviceversion den 4 oktober 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.21 av appar för ekonomi och drift (oktober 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Förmånsutdrag | Förmånsutdrag för att visa en medarbetares aktuella förmånsförmån. Mer information finns i [Förmånsutdrag](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) i dokumentet utgivningscykel. |

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

