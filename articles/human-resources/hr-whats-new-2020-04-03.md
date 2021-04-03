---
title: Vad är nytt och ändrat i Dynamics 365 Human Resources (3 april 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 3 april 2020.
author: andreabichsel
manager: tfehr
ms.date: 04/03/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 715de76e9920bcb6cca7cabf053f649d27094149
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465376"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Vad är nytt och ändrat i Dynamics 365 Human Resources (3 april 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3111. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>Funktioner som generellt är tillgängliga i veckan för 6 april

- **Funktioner för tjänstledighet och frånvaro** – För mer information, se [Översikt av tjänstledighet och frånvaro](hr-leave-and-absence-overview.md).

- **Funktioner för förmånshantering** – För mer information, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Miljögränser för personal är nu baserade på uppdaterad licensiering (394595)

Gränsen för antalet miljöer per projekt i LCS har ändrats. Den föregående gränsen var två miljöer. Gränsen för antalet produktionsmiljöer och miljöer med begränsat läge som du kan skapa för personal i LCS baseras nu på uppdaterad licens. Du kan nu skapa så många miljöer som behövs per LCS-projekt, beroende på antalet köpta licenser. Den nya licensen uppdaterades den 1 februari 2020, vilket innebär att kunderna kan köpa ytterligare miljöer. Mer information om licensieringskrav för ytterligare miljöer finns i [Dynamics 365 licensieringsguide](https://dynamics.microsoft.com/pricing/#HumanResources).
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>Fel vid försök att ta bort en enkät (428603)

Genom uppdateringen för den här veckan korrigeras problemet att följande fel visas vid försök att ta bort en enkät:

Ett obalanserad X++ TTSBEGIN/TTSCOMMIT par har upptäckts.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>Prestandajournal och säkerhetsproblem för professionella certifikat (428499)

Denna ändring begränsar visningen av både prestandajournaler och professionella certifikat baserat på de företag som de har tillgång till. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>Förkortningen för Quebec och Manitoba (387510)

Startdata har uppdaterats för att återspegla korrekt förkortning för Manitoba och Quebec.

## <a name="new-entities-available-in-data-management-framework"></a>Nya entiteter finns i datahanteringsramverk

Följande entiteter är nu tillgängliga. Om dessa entiteter inte visas i listan entiteter använder du alternativet **uppdatera entiteter** i **Ramverksparametrar > Enhetsinställningar > Uppdatera enhetslistan**.

 - Transaktion för tjänstledighets- och frånvarobank V2
 - Anmälan om tjänstledighet och frånvaro V2
 - Plannivå för tjänstledighet och frånvaro V2
 - Plan för tjänstledighet och frånvaro V2

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>Dataverse-lösningen finns nu med följande ändringar:

| beskrivning | Växel |
| --- | --- |
| **Jobb/befattning** enhetsändringar | <ul><li>**Kompensationsregion** tillagd</li>|
| Entiteten **Dimension för jobbposition** har lagts till | <ul><li>**Ekonomiska dimensioner** tillagd</li>
| **Arbetare** enhetsändringar | <ul><li>**Namnordning** tillagd</li><li>**Arbetar hemifrån** tillagd</li><li>**Språk** tillagt</li><li>**Datum för tjänsteålder** tillagt</li><li>**Jubileumsdatum** tillagt</li><li>**Ursprungligt anställningsdatum** tillagt</li></ul> |
| **Anställning** enhetsändringar | <ul><li>**Ekonomiska dimensioner** tillagd</li><li>**Uppsägningsorsak** tillagd</li><li>**Uppsägningsdatum** ändrade namn från **Övergångsdatum**</li><li>**Provanställningsdatum** tillagt</li></ul> |
| **Arbetaradress** enhetsändringar | <ul><li>**Gatuadress** tillagd</li><li>**Adressrad 1**, **Adressrad 2** och **Adressrad 3** markerad som inaktuell</li></ul> |
| Inställningsenheter för ny variabelkompensation | <ul><li>**Typ av variabel kompensationsplan**</li><li>**Variabel kompensationsplan**</li><li>**Överlåtelseregler**</li><li>**Variabel kompensationsplannivå**</li></ul> |
| Ny enhet för **Arbetarkalender anställning** | <ul><li>**Enheten arbetskalender** tillagd</li></ul> |
| Ny enhet för **lönepositionsuppgift** | <ul><li>**Lönepositionsuppgift** tillagd</li></ul> |
| Ny enhet för **Rubrik** | <ul><li>**Rubrik** tillagd</li></ul>Den nya entiteten **Rubrik** är inkluderad i Dataverse men refereras inte från entiteterna **Jobbposition** eller **Jobb** för tillfället. |

> [!NOTE]
> Ekonomiska dimensioner för både befattningar och sysselsättning ger en enkelriktad integration för uppdateringar Personal till Dataverse. Uppdateringar av ekonomiska dimensioner synkroniseras från Dataverse till personal.

Under de närmaste veckorna kommer dessa enhetsändringar att vara tillgängliga i alla miljöer. Så här installerar du den senaste Dataverse-lösningen för personal manuellt:

1.  Gå till [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).

2.  Välj **Miljö**.

3.  Leta upp den miljö som du vill uppgradera. Miljön bör motsvara **Miljönamn** i avsnittet **Dataverse-information** i formuläret **Om** i Personal.

4.  Välj miljö om du vill visa information om miljön.

5.  I åtgärdsfältet längst upp, välj **Hantera lösningar**. Ett nytt webbläsarfönster öppnas och navigera till **Dynamics 365 administrationscenter** inom ramen för din miljö.

6.  I listan **Lösningar** välj **Dynamics 365 Human Resources Förankra**.

7.  Välj **uppgradering** om du vill använda den senaste lösningen.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="leave-suspension"></a>Lämna uppehåll

Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Överför regler

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="coming-soon"></a>Kommer snart

## <a name="new-production-release-cadence"></a>Ny produktionsfrisläppningstakt

Från och med april kommer frisläppningstakten för personal att flyttas från en uppdatering varje vecka till en uppdatering varannan vecka. För att säkerställa att du har en säker driftsättningsmetod och upprätthåller höga normer för stabilitet och tillförlitlighet i tjänsten, är processen för att distribuera tjänstuppdateringar till alla regioner en två veckors lansering. Ytterligare tester och bildskärmar är på plats för att kontrollera att distributionen lyckades vid varje steg av processen. Mer information om frisläppningstakt finns i [Uppdatera process](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Kända problem

## <a name="employment-detail-entity"></a>Entiteten anställningsinformation

Enheten **anställningsinformation** har uppdaterats med följande fält: **PayFrequency**, **Anställningskategori-ID**, **Anställningstyp**, **EmploymentType ID** och **Status för anställningsförmån**. Inställningsdata för dessa fält är beroende av att hanteringen av förmåner aktiveras i funktionshantering. Dessa fält bör inte fyllas i eller uppdateras i entiteten **anställningsinformation** eftersom det resulterar i fel under importen.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint förhandsgranskning fungerar inte i vissa miljöer

Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:

1. Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten. Du kan visa den här informationen på sidan **Användare**. Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData. Standard är att e-postadressen inte finns i Excel-designen. Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera. När du är klar med dessa steg kan du uppdatera administratörskontot.

2. När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.

3. Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.

4. Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]