---
title: Nyheter och ändringar i Dynamics 365 Human Resources 22 juni 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 22 juni 2021.
author: marcelbf
ms.date: 06/22/2021
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
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae444b4d208804364333bd3d6e4704500da85470
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303572"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 22 juni 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4258.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Informera användare av arbetare utan anställningsfunktionen – När avancerad åtkomst är inaktiv och funktionen **Visa alla medarbetare utan anställning** är inaktiverad i funktionshantering visas en banner för arbetarna utan anställningsformulär. Bannern uppmanar användaren att aktivera funktionen **Visa alla medarbetare utan anställning**. | Inte aktuellt| [Arbetare utan anställning](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Stöd för anpassade fält i behörighetsregler för förmånshantering | [Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Konfigurera berättiganderegler](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Granskning av periodiseringstransaktion för tjänstledighet | Inte aktuellt | [Granskning av periodiseringstransaktion för tjänstledighet](hr-leave-and-absence-accrue.md#preview-leave-accrual-transaction-auditing)|
| Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro | [Förbättringar av arbetsflödesupplevelse för tjänstledighet och frånvaro](https://go.microsoft.com/fwlink/?linkid=2147528) | [Begära ledig tid](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan uppdatera det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem |  beskrivning |
| --- | --- | --- |
| 583052 | Användare som tar emot återrapportering kan redigera feedback som mottagits | När en medarbetare som får återrapportering från en resultatjournal väljer **Lägg till extern länk**, kan formuläret redigeras så att medarbetaren kan redigera den resultatfeedback som de har fått. |
| 522281 | Om du väljer antalet medarbetare i kompensationsstrukturen som är nöjda i Kompensationshantering leder det till felaktiga resultat| När du går ner i kompensationsplanerna från kompensationsarbetsytan visas nu korrekt antal medarbetare. |
| 580683 | Användare som tilldelats medarbetar- och chefsroller kan inte bifoga anteckningar eller uppdatera en resultatjournal | Användare som tilldelats medarbetar- och chefsroller kan inte bifoga anteckningar eller uppdatera en resultatjournal. Användaren får då felmeddelandet "Det går inte att skapa en post i Prestandajournalposten (HcmPerfJournal). Policy för säkerhetsbehörighet nekas. |
| 583077 | Födelsedatum för en medarbetare i kalendern för tjänstledighets- och frånvaroföretaget visar fel datum | Användare kommer att kunna visa korrekt födelsedatum för medarbetarna i tjänstledighets- och frånvaroföretagets kalender. |
| 586996 | Visningsfunktionen för flera företag gör att saldon blir tomma när åtkomsten begränsas till ett enskilt företag | Användare kan visa medarbetarens framtida tjänstledighetssaldon korrekt när vyn Tjänstledighet för flera företag aktiveras. |
| 581014 | Om du aktiverar tjänstledighets- och frånvarovyn mellan företag orsakar det ett fel när du visar framtida saldon | Felen har åtgärdats när användarna visar framtida tjänstledighetssaldon med vyn Tjänstledighet för flera företag aktiverad. |
| 509404 | Analys av avdelningspersonal tar inte hänsyn till medarbetarnas förflyttningar mellan avdelningarna. | När en medarbetare flyttar från en avdelning till en annan återspeglar informationen i personalstyrkan inte den gamla avdelning där medarbetaren växlas om befattningsdetaljerna upphör att gälla under innevarande år. |
| 584851 | Förmånskreditprorationsregel "Ingen" ger aldrig kredit |Flexkreditregel "Ingen" resulterade i att medarbetare fick noll kredit för förmånsperioden, oavsett när de anställdes. Detta har fastställts så att en medarbetare ska få fullständig flexkredit om de anställs innan förmånsperioden börjar och ingen om de anställs efter perioden börjar. |
| 584897 | Om du vill duplicera funktionen "Använd grundläggande externa funktioner" leder det till ett fel | När användaren försöker att duplicera funktionen "Använd grundläggande externa funktioner" får han eller hon felmeddelandet", "Det gick inte att hitta objekt med identifieraren UserDefinedAppHostDialogView." |
| 575692 | Det går inte att periodisera tjänstledighet och frånvaro för väntande medarbetare | Periodisering av tjänstledighet och frånvaro kan köras på framtida anställningar när **strömlinjeformad medarbetarpost** är aktiverad. |
| 580110 | Om du lägger till ett företag i löneintegreringen återställs integrationen så att alla enheter används även om alternativet är inställt på att inte uppdatera projektet | Om en kund har tagit bort enheter eller ändrat dataprojektet för löneintegrering och har ställt in alternativet för att förhindra en automatisk uppdatering av projektet, ignorerar och uppdaterar projektet om ett nytt företag läggs till i integrationen.  |
| 584518 |Problemet med att registrera förmåner vid bearbetning av prestanda | Denna rapport behandlar prestandaproblem i processen för anmälan av äldre förmåner. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Kommer snart

| Funktion | Information |
| --- | --- |
| Plattformsuppdatering 10.0.19 (43) | Plattformsuppdatering 10.0.19 planeras i och med nästa serviceversion den 28 juni 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.19 av Finance and Operations-appar (juni 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Växling av visningsperiod för service | Med den här funktionen kan du använda olika datum vid beräkning av serviceåren som visas i formuläret **Strömlinjeformad medarbetarpost** och i formuläret **Personer**.  Denna kommer att vara tillgänglig i Personal-parametrar. |
|  Aktivera frånvarochefen för hantering av tjänstledighet | [Aktivera frånvarochefen för hantering av tjänstledighet](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Bestämd bilagor för specifika tjänstledighetstyper | Med den här funktionen kan administratörer lägga till fullmaktsbilagor när tjänstledighetsansökningar för specifika tjänstledighetstyper skickas. |
|  Konfigurera ledighetsenheter per tjänstledighetstyp | Med denna funktion kan administratörer konfigurera tjänstledighetsenheter (timmar eller dagar) för varje tjänstledighetstyp.  |
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
