---
title: Nyheter och ändringar i Dynamics 365 Human Resources (10 mars 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 10 mars 2020.
author: andreabichsel
manager: tfehr
ms.date: 03/10/2020
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
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e57e224767a366b4cec3058a81e9be9ee1f5ba92
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463728"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (10 mars 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2985. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Det går inte att komma åt GAP-analysrapporten (394460)

Den här rapporten stöds inte i Dynamics 365 Human Resources. Menyalternativet för utskrift av SSRS-rapporten tas bort.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Felaktigt meddelande vid åtkomst till sidan komma igång (417950)

Med den här ändringen döljs detta menyalternativ om du inte har åtkomst till formuläret.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Strömlinjeformat underhåll av uppgifter för medarbetare (380538)

I formuläret underhåll av arbetsuppgift visas alla uppgifter för en medarbetare över registrering, offboard, övergångar och affärsprocesser. Du kan nu ta bort, tilldela om eller uppdatera status för uppgiften.

Exempel: Benjamin Martin är en förmånsadministratörer. Under medarbetarens avregistrering skapas uppgifter för Benjamin för att granska den nya medarbetarens val av förmån. Benjamin har tidigare uppgifter som han slutfört och framtida uppgifter som han behöver för att kunna slutföra. Benjamin bestämmer sig för att lämna företaget, så sina uppgifter måste antingen återtilldelas eller tas bort. Formuläret aktivitetsunderhåll (i åtgärdsfönstret i formuläret **arbetare**) gör att alla Benjamin uppgifter kan tilldelas till en annan arbetare eller tas bort.  

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
| Ny enhet för **Rubrik** | <ul><li>**Rubrik** tillagd</li></ul> Den nya entiteten **Rubrik** är inkluderad i Dataverse men refereras inte från entiteterna **Jobbposition** eller **Jobb** för tillfället. |

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

Följande förhandsgranskningsfunktioner är tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** – För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** – För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Kommer snart

### <a name="platform-update-33"></a>Plattform update 33

- Full sida appar (förhandsgranskning) – den här förhandsgranskningsfunktionen som kräver att du aktiverar funktionen Sparade vyer gör att Power Apps och appar från tredje part läggs till som fulla sidupplevelser via instrumentpanelen.

- Sparade vyer (förhandsgranskning) – med hjälp av den här funktionen kan du spara vyer, vilket är en avsevärd förbättring av under systemet för anpassning. Med den här funktionen kan användare ha flera namngivna uppsättningar av anpassningar per sida. Du kan även publicera vyer i säkerhetsroller.

- Optimerad "är en av" filtreringsupplevelser – den här funktionen möjliggör optimerad "är en av" filtreringsupplevelser som gör det enklare att ange flera filtervärden, har en enklare mekanism för att ta bort enskilda eller alla filtervärden och har en mer kompakt och intuitiv visualisering av filtervärden.

- Rekommenderade fält – användarna ofta måste lägga till fält i ett rutnät eller på en sida. Det kan vara svårt med så många tillgängliga fält. I stället för att behöva söka igenom en stor lista, aktiverar den här funktionen systemet för en uppsättning rekommenderade fält baserat på vad andra användare ofta lägger till i liknande scenarier.

- Tröga standardåtgärder i rutnät – med den här funktionen kan du se till att standardåtgärden i ett rutnät länkas till en viss kolumn i ett rutnät, oavsett om den kolumnen flyttas eller döljs.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]