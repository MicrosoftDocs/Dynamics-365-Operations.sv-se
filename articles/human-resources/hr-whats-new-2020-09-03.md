---
title: Nyheter och ändringar i Dynamics 365 Human Resources (03 september 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 3 september 2020.
author: Darinkramer
manager: tfehr
ms.date: 9/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ddffff18e1d6d16bd5a5f7e7021f9a34651307fa
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527470"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (3 september 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3504. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

Mer information om kommande funktioner i Human Resources finns i [Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Mer information om uppdateringsprocessen för Human Resources finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>I den här versionen

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nya standardrutnät för ekonomiska dimensioner och dialogmönster i Human Resources (469495)

Det nya mönstret för ekonomiska dimensioner är nu tillgängligt i följande områden:

- Positionsåtgärder (formulär: **HcmPositionActionDetail**)
- Löneuppbetalningskoder (formulär: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>Poster visas inte i företagets tjänstledighet om ledighet och förbättringar av frånvarokalendern inte aktiveras (484406)

Den här versionen åtgärdar ett problem där poster i företagets tjänstledighet inte visas i kalendern. Det här problemet uppstår bara när alternativet för funktionshantering **ledighet och förbättringar av frånvarokalendern inte aktiveras** inte är aktiverade.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problem med BenefitPlanEmployeeEntity (467597)

Den här utgåvan korrigerar ett problem med entiteten **BenefitsPlanEmployee**. När du importerar medarbetares registreringar **Omfattningskod** och **Plantypkod** ställs nu in korrekt. Det här problemet medförde att medarbetar förmånsplaner visas felaktigt i formuläret **förmånsplan för arbetare** och i formuläret **öppen anmälan** i Självbetjäning för medarbetare.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Elektronisk fil 1094-C utdata saknas i XML (435190)

Den här ändringen åtgärdar ett problem med utdatafilen 1094-C som saknar ett tecken som behövs för att skicka till IRS.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Register för variabel kompensation för medarbetare mappad till formulär för fast kompensation (476117)

Den här ändringen justerar fälten för fasta kompensationer med formuläret för fast kompensation. Variabla kompensations fält är nu bara tillgängliga i formuläret för variabel kompensation.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Lämna begäran som är tillåtna före registrering om tjänstledighetstypen har ett negativt minsta saldo (469917)

Den här ändringen tillåter inte att du anger tjänstledighetsbegäran innan de registreras i planen, även om registreringen har ett negativt minsta saldo. Du kan bara ange eller skicka förfrågningar när planen är aktiv.

### <a name="document-templates-dont-download-457279"></a>Dokumentmallar hämtas inte (457279)

Med den här ändringen kan du nu hämta alla dokumentmallar. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Data visas som kolumnrubriker i stället för rader för fältet lönesats i rapporten kompensationsplan (476077)

Analysrapporten visar nu korrekt information för **lönesatsen**.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns i:

- [Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 1-planen
- [Human Resources i Teams](https://go.microsoft.com/fwlink/?linkid=2127841) i Human Resources-dokumentation

### <a name="human-resources-app-in-teams-preview-features"></a>Förhandsfunktioner för Human Resources-app i Teams
 
-  **Meddelanden**: skicka och granskare av tidsförfrågningar kommer att meddelas i modulen Human Resources-app i Teams. Godkännare kan godkänna eller neka förfrågningar om ledighet. Avsändare kommer att meddelas om begäran har godkänts eller avslagits. Mer information finns i:
   - [Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen
   - [Aktivera meddelanden för Human Resources-appar i Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) i Human Resources-dokumentation
   - [Aktivera eller inaktivera Teams-meddelanden för enskilda användare](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) i Human Resources
   - [Team meddelanden](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) i Human Resources-dokumentation
   - [Visa gruppens tjänstledighetskalender](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) i Human Resources dokumentation
 
- **Ledighetskalender för chef**: chefer kommer att kunna se godkänd och väntande ledighet för sina underställda i en kalendervy. Den här vyn gör det enklare att förstå när gruppmedlemmarna är borta från arbetet. Mer information finns i:
   - [Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 2-planen
   - [Visa gruppens tjänstledighetskalender](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) i Human Resources dokumentation

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Konfigurationsalternativ för placering av lista över arbetsartiklar tilldelade till mig (477004)

Det finns nu ett nytt alternativ för att placera **Arbetsuppgifter som tilldelats till mig** i den högra kolumnen på instrumentpanelen. Med den här ändringen visas alla arbetsobjekt och att göra-listor i samma område. Aktivera den här funktionen genom att aktivera **Förhandsversion - Förbättringar av arbetsflödesupplevelse** i funktionshantering. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md).

Den här funktionen främjar också de arbetsflödesalternativ som visas i formuläret personalåtgärder. Arbetsflödesalternativen visas även ovanför åtgärdens snabbflik för snabbåtkomst. Mer information finns i: 

- [Arbetsflöde för organisation och personalhantering](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) i Dynamics 365 2020 utgivningsvåg 2-planen

![Arbetsuppgifter som tilldelats till mig](./media/hr-workflow-work-items-assigned-to-me.png)

![Snabbåtkomst till arbetsflödesartiklar](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Kommer snart

### <a name="checklist-entities-included-in-common-data-service"></a>Entiteter för checklista inkluderade i Common Data Service

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Common Data Service.

### <a name="benefits-management-reason-codes"></a>Orsakskoder för hantering av förmåner

Orsakskoder för förmånshantering kommer snart att kombineras med befintliga orsakskoder i Human Resources. Om du skapade orsakskoder i en förmånshantering som är över 15 tecken stora måste du ändra namnet på orsakskoden i formuläret för förmåner i förmånshanteringens formulär **orsakskoder** till 15 tecken eller mindre. När du har uppdaterat namnet visas orsakskoden under formuläret befintlig orsakskod i personalhantering. Den här ändringen kommer att vara tillgänglig i framtiden och påverkar inte befintliga funktioner.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]