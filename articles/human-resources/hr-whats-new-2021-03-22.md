---
title: Nyheter och ändringar i Dynamics 365 Human Resources 22 mars 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 22 mars 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 609b70fb2dfa3f3b2a1746392984108d7ac195c4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019284"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 22 mars 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4049.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Alternativ för att tvinga annullering och återställning av låsta batchjobb (560976) | NA | [Återställ låsta batchjobb](./hr-admin-troubleshooting-batch-execution.md) |
| Mindre UX-uppdateringar för att skapa ny förmånsplan (419941) | NA | [Skapa en förmånsplan](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans |  beskrivning |
| --- | --- | --- |
| 554239 | Prestandaförbättringar för enheter som är relaterade till tabellen **BusinessProcessTaskAssignment** | Förbättra prestanda för enheter som är relaterade till tabellen **BusinessProcessTaskAssignment** genom att lägga till föreslagna index i tabellen. |
| 566061 | Ta bort reservkod för V2-entitet från nattsynkronisering | Ta bort V2-reservkoden för Dataverse nattsynkronisering. Reserv behövs inte längre och förhindrar att filtrerad synkronisering fungerar som förväntat. Ändringen ökar konsekventa Dataverse datasynkronisering. |
| 538024 | Arbetsförmånsplaner > Ta bort utcheckning - fel vid kontroll | Fast fel vid borttagning av utcheckning av förmånsplan i formuläret Arbetsförmåner. |
| 557965 | Arbetsyta för **Förmåner**: länken **Aktiva livshändelser** ska alltid vara synlig i avsnittet **Länkar** | Korrigerat problem där länken **Aktiva livshändelser** var synlig för avsnittet **Länkar** men som gav ett när du försöker navigera om funktionen **(förhandsversion) Arbetsyta för förmånshantering** inte är aktiverad. Mer information om hur du aktiverar arbetsytan finns i [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md). |
| 556672 | Det går inte att behandla intäkter för en uppsagd anställd när **Strömlinjeformad medarbetarinmatning** är aktiverat i funktionshanteringen | Alternativet att samla ledighet och frånvaroplaner har lagts till **Flera alternativ** under **Arbetshistorik** för medarbetare när **Strömlinjeformad medarbetarinmatning** har aktiverats i funktionshantering. |
| 562656 | Menyalternativet **SysRecordChangeLogValidTimeState** ska inkluderas i en säkerhetsbehörighet och ett filnamnstillägg för säkerhetsprogrambehörighet **SystemExternalBasicMaintain** | Icke-systemadministratörsroller saknade knappen **Visa ändringar** i formulären för datumhanterare. |
| 505989 | Bearbetning av livstidshändelser: Ändring av berättigande som inte bearbetats på rätt sätt till det datum som använts | Fast fråga där ändringen av berättigandebearbetningen var beroende av startdatumet för befattningen och inte bara den aktuella befattningen. |
| 562286 | Säga upp arbetare skickar flera uppdateringar till Dataverse | När en arbetare avslutas skickas mer än en uppdateringsåtgärd till  Dataverse, vilket leder till två uppdateringsmeddelanden för samma ändring. Det kan leda till flera utlösare om Power Automate-flöde har konfigurerats för att utlösa från åtgärden. |
| 527340 | Felet "Orepresentable DateTime" visas när tjänstledighet och frånvaroanmälningar öppnas | När du väljer tjänstledighet och frånvaroanmälning visas inte längre felet. |
| 561663 | Öka väntetiden för kluster provisionering | Förbättra infrastrukturkapaciteten och få överensstämmelse med uppdateringar av kluster provision. |
| 486129 | Det går inte att redigera anpassade fält i **Befattningar > Hantera ändringar** | Korrigerade ett problem där anpassade fält inte kunde redigeras på fliken **Hantera ändringar** för **Befattningar**. |

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