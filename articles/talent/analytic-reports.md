---
title: Använda analysrapporter i Microsoft Dynamics 365 Talent - Attract
description: Det här ämnet beskriver analysrapporterna för insikter om anställningsprocessen i Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 5a4d160e8c90725d5ea129a76fd48da1c5af7900
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551528"
---
# <a name="use-analytic-reports-in-microsoft-dynamics-365-talent---attract"></a>Använda analysrapporter i Microsoft Dynamics 365 Talent - Attract

Analytiska rapporter i Microsoft Dynamics 365 Talent: Attract ger en OOTB-lösning (färdigkonfigurerade) för anställning av processinsikter. Tillgängliga funktioner omfattar:

- **Jobbanalys:** Klicka på **Analys** inom ett jobb för mätvärden på jobbets sökande.
- **Analysnav:** Klicka  **Analys** på analys när du vill navigera till vänster om aggregerade mått över jobb.
- **Användarspecifik säkerhet** – Åtkomst till rapporter styrs av Attract [roll](security-attract.md) och jobbdeltagarnas roll.
- **Korsfiltrering:** Klicka på visuella objekt i en rapport om du vill visa andra mått som filtrerats efter valda data.

>[!NOTE] 
>- Den här funktionen är för närvarande i [förhandsgranskning](access-preview-feature.md). För att kunna prova måste du ha [**Tillägget för omfattande anställning**](attract-comprehensive-hiring.md).
>- Alla allmänna förhandsgranskningsrapporter visas på engelska.
>- Uppdatera rapporter var 3:e timme. Den senaste uppdaterings tiden (i den lokala tidszonen) finns högst upp i rapporten. Uppdateringstiden är en ungefärlig och varierar beroende på data volym och resursbelastning i din region.

## <a name="job-analytics"></a>Jobbanalyser

Jobbanalysrapporter ger en ögonblicksbild av anställningsprocessen för ett jobb.  Nyckelmått är:

- Aktiva sökande efter etapp
- Sökandes källa
- Typ av sökande (intern eller extern)

## <a name="analytics-hub"></a>Analysnav

Analysnav rapporterar sammansatta data över jobb för att visa trender anställningsprocessen. Attract inkluderar två OOTB-rapporter: Sammanfattning av försäljningsförlopp och trattanalys.

### <a name="pipeline-summary"></a>Sammanfattning av pipeline

Rapporten sammanfattning av försäljningsförlopp sammanställer data för lediga jobb. Nyckelmått är:

- Sökande över alla jobb efter fas
- Sökandes källa
- Lediga jobb efter tjänsteåldernivå

### <a name="funnel-analysis"></a>Trattanalys

I rapporten för trattanalys sammanställs data för jobb som har stängts som fyllda. Nyckelmått är:

- Tid att hyra
- Konverteringsmått (vid hovring)
- Frekvens för godkännande av erbjudande

Obs! för den mest exakta tiden för rapportering av tid det tar för att anställa rekommenderar vi att du använder [erbjudandehantering](offer-setup.md), en funktion som är en del av tillägget för omfattande anställning.

>[!TIP] 
>Försök att hovra över visuella bilder om du vill ha mer information. Om du till exempel hovrar över **aktiva sökande** visas visuella, genomsnittsdagarna i stadiet. Analys av den här informationen kan ge insikter som är kritiska för att minska tiden för anställare och ge rekryterare möjlighet att fokusera på olika sätt att minska den tid som ägnas åt varje etapp.

## <a name="user-specific-security"></a>Användarspecifik säkerhet

Attract-rapporter är tillgängliga för rollerna admin, läs alla, rekryterare och Anställande chef [roller](security-attract.md). Ej tilldelade användare har inte tillgång till någon av analysrapportsidorna (Jobbanalys och Analysnav).

Jobbanalys-rapporter visar data för det valda jobbet. Analysnav rapporterar sammanslagna data över alla jobb som en användare kan visa. Användare som kan visa både mina jobb och alla jobb på jobbsidan har samma vyer tillgängliga i analysnavet.

## <a name="cross-filter"></a>Korsfilter

En av de fantastiska funktionerna i Power BI är hur alla visuella element på en rapportsida är sammankopplade. Om du markerar en datapunkt på något av de visuella elementen, är alla andra visuella element på sidan som innehåller data ändringar baserade på den markeringen. Läs mer och se ett exempel på [hur visuella element korsfiltrerar varandra i en Power BI-rapport.](https://docs.microsoft.com/power-bi/consumer/end-user-interactions)

## <a name="export-to-excel"></a>Exportera till Excel

Om du vill visa rapportdata i Excel kan du klicka på alternativmenyn (tre punkter) på en bild och välja **Exportera underliggande data**. Exporterade data exporteras som filtrerade och respekterar användarbehörigheterna för att Attract. Mer information finns i [exportera data från visualiseringar](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)
