---
title: Nyheter och ändringar i Dynamics 365 Human Resources (24 mars 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 24 mars 2020.
author: andreabichsel
ms.date: 03/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3607e09935928a079a3f7e60cde1017e69875dea
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694778"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-24-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (24 mars 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3073. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Miljögränser för personal är nu baserade på uppdaterad licensiering (394595)

Gränsen för antalet miljöer per projekt i Lifecycle Services (LCS) har ändrats. Den föregående gränsen var två miljöer. Gränsen för antalet produktionsmiljöer och miljöer med begränsat läge som du kan skapa för personal i LCS baseras nu på uppdaterad licens. Du kan nu skapa så många miljöer som behövs per LCS-projekt, beroende på antalet köpta licenser. Den nya licensen uppdaterades den 1 februari 2020, vilket innebär att kunderna kan köpa ytterligare miljöer. Mer information om licensieringskrav för ytterligare miljöer finns i [Dynamics 365 licensieringsguide](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="platform-changes"></a>Plattformsändringar

- Full sida appar (förhandsgranskning) – den här förhandsgranskningsfunktionen som kräver att du aktiverar funktionen Sparade vyer gör att Power Apps och appar från tredje part läggs till som fulla sidupplevelser via instrumentpanelen.

- Sparade vyer (förhandsgranskning) – med hjälp av den här funktionen kan du spara vyer, vilket är en avsevärd förbättring av under systemet för anpassning. Med den här funktionen kan användare ha flera namngivna uppsättningar av anpassningar per sida. Du kan även publicera vyer i säkerhetsroller.

- Optimerad "är en av" filtreringsupplevelser – den här funktionen möjliggör optimerad "är en av" filtreringsupplevelser som gör det enklare att ange flera filtervärden, har en enklare mekanism för att ta bort enskilda eller alla filtervärden och har en mer kompakt och intuitiv visualisering av filtervärden.

- Rekommenderade fält – användarna ofta måste lägga till fält i ett rutnät eller på en sida. Det kan vara svårt med så många tillgängliga fält. I stället för att behöva söka igenom en stor lista, aktiverar den här funktionen systemet för en uppsättning rekommenderade fält baserat på vad andra användare ofta lägger till i liknande scenarier.

- Tröga standardåtgärder i rutnät – med den här funktionen kan du se till att standardåtgärden i ett rutnät länkas till en viss kolumn i ett rutnät, oavsett om den kolumnen flyttas eller döljs.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-multiple-leave-type-feature-on-419635"></a>Det går inte att justera lämnar saldot för en plan utan periodiseringar som skapades med funktionen för typ av flera tjänstledighet på (419635)

Med den här ändringen kan du justera saldon för tjänstledighetsplaner som har skapats med funktionen flera tjänstledighetstyper (förhandsgranskning) som är aktiverade i funktionshantering.

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner blir tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** – För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** – För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

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

3.  Leta upp den miljö som du vill uppgradera. Miljön bör motsvara **Miljönamn** i avsnittet **Common Data Service-information** i formuläret **Om** i Personal.

4.  Välj miljö om du vill visa information om miljön.

5.  I åtgärdsfältet längst upp, välj **Hantera lösningar**. Ett nytt webbläsarfönster öppnas och navigera till **Dynamics 365 administrationscenter** inom ramen för din miljö.

6.  I listan **Lösningar** välj **Dynamics 365 Human Resources Förankra**.

7.  Välj **uppgradering** om du vill använda den senaste lösningen.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint förhandsgranskning fungerar inte i vissa miljöer

Om förhandsgranska dokument för dokument som lagras i SharePoint inte fungerar gör du så här:

1. Kontrollera att administratörens användarkonto har ett e-postmeddelande kopplat till användarposten. Du kan visa den här informationen på sidan **Användare**. Om e-post inte har konfigurerats måste du lägga till e-postadressen och providern med Excel-tillägget OData. Standard är att e-postadressen inte finns i Excel-designen. Du måste redigera Excel-designen, lägga till alla fält, använda och uppdatera. När du är klar med dessa steg kan du uppdatera administratörskontot.

2. När administratörskontot har ett associerat e-postkonto loggar du in på personal med administratörsbehörighet.

3. Få åtkomst till en bilaga i SharePoint för att starta förhandsgranskningen av dokument.

4. Logga in med ett annat användarkonto som har tillgång till bilagor och kontrollera att förhandsgranskningen fungerar som förväntat.

## <a name="coming-soon"></a>Kommer snart

## <a name="new-production-release-cadence"></a>Ny produktionsfrisläppningstakt

Från och med april kommer frisläppningstakten för personal att flyttas från en uppdatering varje vecka till en uppdatering varannan vecka. För att säkerställa att du har en säker driftsättningsmetod och upprätthåller höga normer för stabilitet och tillförlitlighet i tjänsten, är processen för att distribuera tjänstuppdateringar till alla regioner en två veckors lansering. Ytterligare tester och bildskärmar är på plats för att kontrollera att distributionen lyckades vid varje steg av processen. Mer information om frisläppningstakt finns i [Uppdatera process](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Kända problem

## <a name="employment-detail-entity"></a>Entiteten anställningsinformation

Enheten **anställningsinformation** har uppdaterats med följande fält: **PayFrequency**, **Anställningskategori-ID**, **Anställningstyp**, **EmploymentType ID** och **Status för anställningsförmån**. Inställningsdata för dessa fält är beroende av att hanteringen av förmåner aktiveras i funktionshantering. Dessa fält bör inte fyllas i eller uppdateras i entiteten **anställningsinformation** eftersom det resulterar i fel under importen.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]