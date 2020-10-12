---
title: Nyheter och ändringar i Dynamics 365 Human Resources (16 september 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 16 september 2020.
author: jcart1106
manager: tfehr
ms.date: 09/16/2020
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
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad8513477c7f9243fa3ee5d99569c048ffada97d
ms.sourcegitcommit: 7537aa8ef619eea6c48467a3ca86e3372415f8a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "3823732"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (16 september 2020)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3557. Siffror inom parenteser bredvid vissa funktioner refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="included-in-this-release"></a>Ingår i den här versionen

-  [Sparade vyer – allmän tillgänglighet](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- För mer information, se [Sparade vyer](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views). 

- Formuläret **Positionsåtgärder** har uppdaterade dimensionsrutnät och ny dialog (469495).

- Om du ställer in **begränsa åtkomsten till arbetsuppgifter** till Ja i **Avancerad åtkomst** i **Delade parametrar för Human Resources** visas nu bara de aktuella arbetarna (393384).

- Nya alternativ för att skapa kalendrar i entiteten **WorkCalendar** (477055):<br>- Standard sluttid<br>- Standard starttid<br>- Är fredag arbetsdag<br>- Är måndag arbetsdag<br>- Är lördag arbetsdag<br>- Är söndag arbetsdag<br>- Är torsdag arbetsdag<br>- Är tisdag arbetsdag<br>- Är onsdag arbetsdag<br>- Helgdags-ID i arbetskalender

- Entiteten **LeaveBankTransactionV1** omfattar nu orsakskoden (477823).

- Du kan nu spara uppgiftsregistreringar (492923).

- Nu har data publicerats från **HCMWorkerContactEntity** (427620).

- Snabbfliken **Kompensation** visas nu för leverantörens arbetartyp ange formuläret **Arbetarens åtgärder** (482494).

- Fälten **Nivå** och **Plan** är nu obligatoriska om du anger en **Fast kompensation**. Ett felmeddelande visas om du lämnar dessa fält tomma (482497).

- Fältet **Plantyp** i **Förmåner** är nu en nedrullningsbar lista (488768).

- Systemadministratörer får nu ett meddelande om att ett anpassat fält tas bort från Human Resources (481408).

- Under medarbetarens uppsägningsprocess beter sig Human Resources som förväntat och ändrar inte det valda företaget efter att ha låst sig (479877). 

- Chefer kan inte längre lägga till en nummerkolumn genom anpassning (485317).

- Chefer kan inte längre ta bort dataområdes filtret från identifieringsnummer som upphör att gälla (485321).

- När fältet **Rapporteras till** är tomt, visas befattningsdetaljer fortfarande när du hovrar över befattningen (433328).

- Medarbetarna kan nu visa information om förmånsplaner i Employee Self Service (481676).

- Medarbetarna kan nu se alla registrerade kurser (429048).

- Du kan nu begränsa visningsalternativen för sidan **Professionella certifikat**. Du kan begränsa visningsalternativen till den aktuella juridiska personen efter arbetsstatus och efter typ av arbetare (451501). 


## <a name="in-preview"></a>I förhandsgranskning

### <a name="human-resources-app-in-teams"></a>Human Resources-app i Teams

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

### <a name="leave-and-absence-calendar"></a>Kalender för ledighet och frånvaro

Den här versionen innehåller ytterligare kalenderalternativ för tjänstledighets- och frånvarokalendrar. Mer information finns i [Visa team- och företagskalendrar](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).

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
