---
title: Vad är nytt och ändrat i Dynamics 365 Human Resources (13 april 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 13 april 2020.
author: andreabichsel
ms.date: 04/13/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 93873707703ce7148c353735ce1abce795796a5e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892019"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Vad är nytt och ändrat i Dynamics 365 Human Resources (13 april 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3136. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="new-production-release-cadence"></a>Ny produktionsfrisläppningstakt

Med denna veckas frisläppning kommer frisläppningstakten för personal att flyttas från en uppdatering varje vecka till en uppdatering varannan vecka. För att säkerställa att du har en säker driftsättningsmetod och upprätthåller höga normer för stabilitet och tillförlitlighet i tjänsten, är processen för att distribuera tjänstuppdateringar till alla regioner en två veckors lansering. Ytterligare tester och bildskärmar är på plats för att kontrollera att distributionen lyckades vid varje steg av processen. Mer information om frisläppningstakt finns i [Uppdatera process](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>Fält för avrundningsprecision går inte att redigera efter att ha angett en avrundningstyp (435616)

Med den här ändringen är fältet **avrundningsprecision** nu tillgängligt när du har uppdaterat fältet **avrundningstyp**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Det går inte att redigera lämna slutdatum för anmälan när tjänstledighetsplanen inte har periodiseringstransaktioner (413628)

Du kan nu redigera slutdatum för anmälan utan att ta emot felet "Fältet för datumbasen för periodiseringen måste fyllas i."

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>Arbetsenheten synkroniseras inte till Dataverse (430834)

Den här ändringen åtgärdar ett problem där anställningsdata inte synkroniseras till Dataverse efter tillägg av ekonomiska dimensioner. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Ta bort flera överordnade för entiteten tidsintervall för arbetskalender (431775)

Denna ändring tar bort flera överordnade för entiteten **Tidsintervall till arbetskalendern**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>Filtret med CAST-funktionen fungerar inte på OData anropar entiteten befattningstilldelning för arbetare (431699)

I den här uppdateringen ingår en ändring som tillåter filtrering med funktionen CAST i OData för entiteten **Befattningstilldelning för arbetare**.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="leave-suspension"></a>Lämna uppehåll

Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Överför regler

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Kända problem

## <a name="employment-details-entity"></a>Entiteten anställningsinformation

Entiteten **anställningsinformation** har uppdaterats med följande fält:

- **PayFrequency**
- **Anställningskategori-ID**
- **Anställningstyp**
- **EmploymentType-ID**
- **Status för anställningsförmån**

Inställningsdata för dessa fält är beroende av att hanteringen av förmåner aktiveras på arbetsytan för **funktionshantering**. Fyll inte i eller uppdatera fälten i entiteten **anställningsinformation** eftersom det resulterar i fel under importen.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint förhandsgranskning fungerar inte i vissa miljöer

Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:

1. Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten. Du kan visa den här informationen på sidan **Användare**. Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData. Standard är att e-postadressen inte finns i Excel-designen. Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera. När du är klar med dessa steg kan du uppdatera administratörskontot.

2. När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.

3. Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.

4. Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]