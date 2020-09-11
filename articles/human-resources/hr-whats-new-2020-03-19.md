---
title: Nyheter och ändringar i Dynamics 365 Human Resources (19 mars 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 19 mars 2020.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
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
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f0b961de23a76947440f6616176874dc6a86cc4c
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712530"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (19 mars 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3014. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Miljögränser för personal är nu baserade på uppdaterad licensiering (394595)

Gränsen för antalet miljöer per projekt i Lifecycle Services (LCS) har ändrats. Den föregående gränsen var två miljöer. Gränsen för antalet produktionsmiljöer och miljöer med begränsat läge som du kan skapa för personal i LCS baseras nu på uppdaterad licens. Du kan nu skapa så många miljöer som behövs per LCS-projekt, beroende på antalet köpta licenser. Den nya licensen uppdaterades den 1 februari 2020, vilket innebär att kunderna kan köpa ytterligare miljöer. Mer information om licensieringskrav för ytterligare miljöer finns i [Dynamics 365 licensieringsguide](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Ange visning mellan företag av kompensationsdata för medarbetare och chefer (403904)

Aktivera denna funktion i arbetsytan **Funktionshantering**. Mer information finns i [Aktivera eller inaktivera funktioner](hr-admin-manage-features.md#enable-or-disable-preview-features).

När du aktiverar den här funktionen kan chefer visa direkt och utökad rapportkompensation utan att behöva logga in på anställande företaget. En fullständig kompensationshistorik är tillgänglig från alla inloggade företag som chefen har åtkomst till. Mer information finns i [Ställ in självservice för medarbetare och chef – översikt](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Aktivera funktioner för kopplad utskrift av globala adressböcker (427189)

Du kan nu slå samman poster i en adressbok genom att markera dubblettposterna och välja **Sammanfoga** på sidan **global adressbok**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>Det går inte att justera lämnar saldot för en plan utan periodiseringar som skapades med funktionen för typ av flera tjänstledighet på (419635)

Du kan nu justera saldon för tjänstledighetsplaner som har skapats med funktionen **flera tjänstledighetstyper** som är aktiverade i funktionshantering.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Primärt positionsfält i WorkerPositionAssignmentEntity när en medarbetare slutat (420774)

För medarbetare med en avslutad anställning visas den primära befattning som var aktiv vid uppsägningen i enheten. För integrationer skapas inte längre en dubblettpost för medarbetarens befattningstilldelning. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>Common Data Service-lösningen finns nu med följande ändringar:

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
| Ny enhet för **Rubrik** | <ul><li>**Rubrik** tillagd</li></ul>Den nya entiteten **Rubrik** är inkluderad i Common Data Service men refereras inte från entiteterna **Jobbposition** eller **Jobb** för tillfället. |

> [!NOTE]
> Ekonomiska dimensioner för både befattningar och sysselsättning ger en enkelriktad integration för uppdateringar Personal till Common Data Service. Uppdateringar av ekonomiska dimensioner synkroniseras från Common Data Service till personal.

Under de närmaste veckorna kommer dessa enhetsändringar att vara tillgängliga i alla miljöer. Så här installerar du den senaste Common Data Service-lösningen för personal manuellt:

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

### <a name="platform-update-33"></a>Plattform update 33

- Full sida appar (förhandsgranskning) – den här förhandsgranskningsfunktionen som kräver att du aktiverar funktionen Sparade vyer gör att Power Apps och appar från tredje part läggs till som fulla sidupplevelser via instrumentpanelen.

- Sparade vyer (förhandsgranskning) – med hjälp av den här funktionen kan du spara vyer, vilket är en avsevärd förbättring av under systemet för anpassning. Med den här funktionen kan användare ha flera namngivna uppsättningar av anpassningar per sida. Du kan även publicera vyer i säkerhetsroller.

- Optimerad "är en av" filtreringsupplevelser – den här funktionen möjliggör optimerad "är en av" filtreringsupplevelser som gör det enklare att ange flera filtervärden, har en enklare mekanism för att ta bort enskilda eller alla filtervärden och har en mer kompakt och intuitiv visualisering av filtervärden.

- Rekommenderade fält – användarna ofta måste lägga till fält i ett rutnät eller på en sida. Det kan vara svårt med så många tillgängliga fält. I stället för att behöva söka igenom en stor lista, aktiverar den här funktionen systemet för en uppsättning rekommenderade fält baserat på vad andra användare ofta lägger till i liknande scenarier.

- Tröga standardåtgärder i rutnät – med den här funktionen kan du se till att standardåtgärden i ett rutnät länkas till en viss kolumn i ett rutnät, oavsett om den kolumnen flyttas eller döljs.

## <a name="new-production-release-cadence"></a>Ny produktionsfrisläppningstakt

Från och med april kommer frisläppningstakten för personal att flyttas från en uppdatering varje vecka till en uppdatering varannan vecka. Detta säkerställer justeringen med säker driftsättningsmetod och upprätthåller höga normer för stabilitet och pålitlighet i tjänsten. Vi lägger till ytterligare tester och bildskärmar på platsen för att kontrollera att distributionen lyckades vid varje steg av processen. Mer information om frisläppningstakt finns i [Uppdatera process](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner är tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** - För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** - För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)