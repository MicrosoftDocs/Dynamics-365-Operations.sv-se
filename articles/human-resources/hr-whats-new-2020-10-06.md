---
title: Nyheter och ändringar i Dynamics 365 Human Resources (6 oktober 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 6 oktober 2020.
author: jcart1106
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ac64218e48d2713b91af1541f94083aef3f815a2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062989"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (6 oktober 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Det här ämnet beskriver nya, ändrade, kommer snart funktioner i Dynamics 365 Human Resources. Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2020 utgivningscykel 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.3636.

### <a name="new-features"></a>Nya funktioner

Följande funktion är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Ytterligare inblick i tjänstledighetskalendrar | [Ge ytterligare inblick i tjänstledighetskalendervy](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Visa team- och företagskalender](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

>[!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Det kan finnas uppdateringar till det här avsnittet för att inkludera felkorrigeringar som gjorde det i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Utleverans | beskrivning |
| --- | --- | --- |
| 448806 | **Standard identifieringstyp** exporterar som **RecId** i HCM-parametrar | Denna ändring i entiteten Personal-parametrar lägger till ytterligare en kolumn som visar **standard identifieringstypen**. |
| 492923 | Uppgiftsregistreringar sparas inte i Lifecycle Services (LCS) | Uppgiftsregistreringar kan n u sparas i LCS. |
| 429950 | Fast kompensation upphör inte korrekt när positionen ändras | När en arbetares position ändras på sidan **Överför arbetare** ställdes datumet för slutkompensation in på en dag före positionens slut. Slutdatum för kompensation är nu samma som positionens slutdatum. |
| 467214 | **Analys av fast lön** visas endast om **Namn på lönesatskonvertering** anges till **Årlig** | Lönesats för fast lön med ett annat namn än **årligt** visades inte i kompensationsanalysen. Med den här uppdateringen använder nu kompensationsanalys alla lönesatskonverteringar. När du kör rapporterna med hjälp av **Varje timme** eller **Lön** använder lönesatskonvertering en annan period än varje timme i filtret **Lön**. Endast lönesatser med en period av **Varje timme** inkluderas i filtret **Varje timme**. |
| 482464 | När du tittar i vyn **Granskningar** ändrar inte vyn **Detaljer** till rutnätsvy efter att du har använt ett filter | När du har använt ett filter visas rutnätet som förväntat. |
| 483184 | Personal genererar inte periodiseringar när du väljer **nivåbas** som **justerat startdatum** i posten **Anmälan om tjänstledighet** |**Justerat startdatum** fylls i och används när tjänstledighetsperiodiseringar genereras.  |
| 509731 | Ledighetsansökan för framtida uppsagda medarbetare orsakar problem om de ansöker om ledighet efter uppsägningsdatum | Ledighetsansökningar kan nu skickas för medarbetare med ett framtida uppsägningsdatum så länge som begäran infaller före uppsägningsdatumet. |
| 510716 | Kompensationsanalys inkluderar både manliga och kvinnliga medarbetare för **genomsnittlig timlön för män** | I kompensationsanalys inkluderar **genomsnittlig timlön för män** i **kompensationens demografiska analys** genomsnittlig lön för kvinnor. Nu omfattar det bara män. |
| 511348 | Förmånerna självbetjäning ska bara visa förmånsplaner som är giltiga från och med i slutet av förmånsperioden | Utgångna förmånsplaner visas för medarbetare på sidan **förmånsanmälan**. Denna korrigeringsfil tar bort dessa planer. |
| 512706 | Ange följande fält som skrivskyddade:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | Knapparna **Lägg till** och **Ta bort** för dimensionsinformation aktiveras felaktigt när åtgärden slutfördes. Den här uppdateringen till sidan **Befattningsåtgärd** gör att fälten inte kan redigeras när åtgärden har slutförts. |

## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar eller inaktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
| --- | --- | --- |
| Personal-app i Microsoft Teams | [Tjänstledighet för medarbetare och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Personal-app i Teams](./hr-admin-teams-leave-app.md)<br>[Hantera begäranden om ledighet i Teams](hr-teams-leave-app.md) |
| Förbättrade arbetsflödesförfrågningar och godkännanden | [Arbetsflöden för organisation och personalhantering](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Virtuella enheter i Dataverse för Personal | [Expandera Dynamics 365 Human Resources grundläggande data i Dataverse](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Konfigurera Dataverse virtuella enheter](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Kommer snart

Följande nya funktioner är schemalagda för framtida versioner:

- **Entiteter för checklista inkluderade i Dataverse**: Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.

- **Orsakskoder för hantering av förmåner**: Orsakskoder för förmånshantering kommer snart att kombineras med befintliga orsakskoder i Personal. Om du skapade orsakskoder i en förmånshantering som är över 15 tecken stora måste du ändra namnet på orsakskoden i formuläret för förmåner i förmånshanteringens formulär **orsakskoder** till 15 tecken eller mindre. När du har uppdaterat namnet visas orsakskoden under formuläret befintlig orsakskod i personalhantering. Den här ändringen kommer att vara tillgänglig i framtiden och påverkar inte befintliga funktioner.

- **Anpassade länkar i självbetjäning för chef**: för att stödja chefer utökas funktionerna i självbetjäning för chef. Funktionerna läggs till för att lägga till anpassade länkar på fliken **Mitt team**. Den här funktionen liknar funktionen anpassade länkar på **Min informationsfliken** i självbetjäning för medarbetare. Mer information finns i [Anpassade länkar i självbetjäning för chef](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2019 utgivningscykel 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Ytterligare resurser

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2020 utgivningsvåg 2](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]