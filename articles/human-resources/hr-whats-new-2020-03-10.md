---
title: Nyheter och ändringar i Dynamics 365 Human Resources (10 mars 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
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
ms.author: dkrame
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7c1a9f10a434343e4c9c8a42ec5c0b7a1a18ad36
ms.sourcegitcommit: 437170338c49b61bba58f822f8494095ea1308c2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2020
ms.locfileid: "3124026"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (10 mars 2020)

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.2985. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Det går inte att komma åt GAP-analysrapporten (394460)

Den här rapporten stöds inte i Dynamics 365 Human Resources. Menyalternativet för utskrift av SSRS-rapporten tas bort.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Felaktigt meddelande vid åtkomst till sidan komma igång (417950)

Med den här ändringen döljs detta menyalternativ om du inte har åtkomst till formuläret.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Strömlinjeformat underhåll av uppgifter för medarbetare (380538)

I formuläret underhåll av arbetsuppgift visas alla uppgifter för en medarbetare över registrering, offboard, övergångar och affärsprocesser. Du kan nu ta bort, tilldela om eller uppdatera status för uppgiften.

Exempel: Benjamin Martin är en förmånsadministratörer. Under medarbetarens avregistrering skapas uppgifter för Benjamin för att granska den nya medarbetarens val av förmån. Benjamin har tidigare uppgifter som han slutfört och framtida uppgifter som han behöver för att kunna slutföra. Benjamin bestämmer sig för att lämna företaget, så sina uppgifter måste antingen återtilldelas eller tas bort. Formuläret aktivitetsunderhåll (i åtgärdsfönstret i formuläret **arbetare**) gör att alla Benjamin uppgifter kan tilldelas till en annan arbetare eller tas bort.  

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
| Ny enhet för **Rubrik** | <ul><li>**Rubrik** tillagd</li></ul> Den nya entiteten **Rubrik** är inkluderad i Common Data Service men refereras inte från entiteterna **Jobbposition** eller **Jobb** för tillfället. |

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

## <a name="in-preview"></a>I förhandsgranskning

Följande förhandsgranskningsfunktioner är tillgängliga den 3 februari 2020:

- **Förhandsgranskningsfunktioner för tjänstledighet och frånvaro** - För mer information, se [Förhandsgranskningsfunktioner för tjänstledighet och frånvaro](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Förhandsgranskningsfunktioner för förmånshantering** - För mer information, inklusive kända problem, se [Översikt över förmånshantering](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Kommer snart

### <a name="platform-update-33"></a>Plattform update 33

- Full sida appar (förhandsgranskning) – den här förhandsgranskningsfunktionen som kräver att du aktiverar funktionen Sparade vyer gör att Power Apps och appar från tredje part läggs till som fulla sidupplevelser via instrumentpanelen.

- Sparade vyer (förhandsgranskning) – med hjälp av den här funktionen kan du spara vyer, vilket är en avsevärd förbättring av under systemet för anpassning. Med den här funktionen kan användare ha flera namngivna uppsättningar av anpassningar per sida. Du kan även publicera vyer i säkerhetsroller.

- Optimerad "är en av" filtreringsupplevelser – den här funktionen möjliggör optimerad "är en av" filtreringsupplevelser som gör det enklare att ange flera filtervärden, har en enklare mekanism för att ta bort enskilda eller alla filtervärden och har en mer kompakt och intuitiv visualisering av filtervärden.

- Rekommenderade fält – användarna ofta måste lägga till fält i ett rutnät eller på en sida. Det kan vara svårt med så många tillgängliga fält. I stället för att behöva söka igenom en stor lista, aktiverar den här funktionen systemet för en uppsättning rekommenderade fält baserat på vad andra användare ofta lägger till i liknande scenarier.

- Tröga standardåtgärder i rutnät – med den här funktionen kan du se till att standardåtgärden i ett rutnät länkas till en viss kolumn i ett rutnät, oavsett om den kolumnen flyttas eller döljs.