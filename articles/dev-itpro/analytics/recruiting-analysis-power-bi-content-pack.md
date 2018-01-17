---
title: "Power BI-innehåll för rekrytering"
description: "Det här avsnittet beskriver Power BI-innehållet Rekrytering. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: HcmRecruitmentWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 0d6bc8584d202810ed14367d36d113d9b109ea7a
ms.contentlocale: sv-se
ms.lasthandoff: 12/19/2017

---

# <a name="recruiting-power-bi-content"></a>Power BI-innehåll för rekrytering

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehållet **Rekrytering**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehållet **Rekrytering** visas i arbetsytan **Rekryteringshantering**. 

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Rapporter och modeller i arbetsytan Rekryteringshantering
Arbetsytan **Rekryteringshantering** innehåller fliken **Analys**. Denna flik innehåller det inbäddade Power BI-innehållet för rekrytering. Innehållet består av en översiktsflik och ytterligare flikar som innehåller information. Följande register beskriver rapporterna på varje flik.

| Rapport               | Innehåll |
|----------------------|----------|
| Rekryteringsöversikt | Sammanfattning av andra rapporter |
| Analys av sökande   | Totalt antal sökande, sökande efter jobb, sökandekällor, kvinnliga till manliga sökande och sökande efter plats |
| Sökandestatus     | Sökande efter typ och status och sökandestatus |
| Rekryteringsanalys  | Nettoanställningskvot, genomsnittligt antal dagar för att anställa, andelen dåliga rekryteringar, rekryteringskostnader, antal rekryteringsprojekt anställning av sökande och sökande gentemot öppningar per rekryteringsprojekt |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Följande tabell visar enheterna som Power BI-innehållet **Rekrytering** baserades på.

| Enhet               | Innehåll                                                         | Relationer med andra entiteter |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Sökande            | Sökande, anställda sökande, nettoanställningskvot och kostnader          | Namn på sökande, företag, kalenderförskjutning, datum, geografisk placering, befolkning, jobb, media, rekryteringsprojekt |
| Namn på sökande       | Sökandes förnamn, efternamn och fullständiga namn                   | Sökande, anställd sökande, uppsagd sökande |
| Kalenderförskjutning      | Kalenderförskjutningar till uppdela rapporter                                | Sökande, anställd sökande, uppsagd sökande |
| Företag              | Företag att filtrera rapporter efter                                   | Sökande, anställd sökande, uppsagd sökande |
| Datum                 | Dagar, veckor, månader och år.                                   | Sökande, anställd sökande, uppsagd sökande |
| Demografi         | Födelsedatum, kön, etniskt ursprung och civilstånd         | Sökande, anställd sökande, uppsagd sökande |
| Anställd sökande   | Sökande, prestanda, startdatum och typ av sökande           | Företag, kalenderförskjutning, datum, geografisk placering, sökandens namn, anställning, resultat, jobb, media, rekryteringsprojekt |
| Anställning           | Startdatum, slutdatum och övergångsdatum                        | Sökande, anställd sökande, uppsagd sökande |
| Geografisk plats  | Stad, region, postnummer och delstat eller region                 | Sökande, anställd sökande, uppsagd sökande |
| Jobb                  | Funktion, typ och rubrik                                        | Sökande, anställd sökande, uppsagd sökande |
| Medier                | Sökandes källa                                             | Sökande, anställd sökande, uppsagd sökande |
| Resultat          | Värdering, beskrivning och bedömningsmodellen                            | Sökande, anställd sökande, uppsagd sökande |
| Rekryteringsprojekt  | Projektbeskrivning, projektstatus och lediga jobb                | Sökande, anställd sökande, uppsagd sökande |
| Uppsagd sökande | Uppsagda sökande, orsak, prestanda och uppsägningsdatum | Företag, kalenderförskjutning, datum, geografisk placering, resultat, befolkning, anställning, media, rekryteringsprojekt, sökandes namn |



