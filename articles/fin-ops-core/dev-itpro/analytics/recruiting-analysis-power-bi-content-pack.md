---
title: Rekrytering Power BI-innehåll
description: Den här artikeln beskriver rekrytering Power BI-innehållet.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom:
- "263934"
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.form: HcmRecruitmentWorkspace
ms.openlocfilehash: 3bce9b165623ed415a0902d3f369a5deef56e8b6
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205805"
---
# <a name="recruiting-power-bi-content"></a>Rekrytering Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver **rekrytering** Microsoft Power BI-innehållet. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
**Rekrytering** Power BI-innehåll visas på arbetsytan **Rekryteringshantering**.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Rapporter och modeller i arbetsytan Rekryteringshantering
Arbetsytan **Rekryteringshantering** innehåller fliken **Analys**. Denna flik innehåller det inbäddade Power BI-innehållet för rekrytering. Innehållet består av en översiktsflik och ytterligare flikar som innehåller information. Följande register beskriver rapporterna på varje flik.

| Rapport               | Innehåll |
|----------------------|----------|
| Rekryteringsöversikt | Sammanfattning av andra rapporter |
| Analys av sökande   | Totalt antal sökande, sökande efter jobb, sökandekällor, kvinnliga till manliga sökande och sökande efter plats |
| Sökandestatus     | Sökande efter typ och status och sökandestatus |
| Rekryteringsanalys  | Nettoanställningskvot, genomsnittligt antal dagar för att anställa, andelen dåliga rekryteringar, rekryteringskostnader, antal rekryteringsprojekt anställning av sökande och sökande gentemot öppningar per rekryteringsprojekt |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Följande tabell visar enheterna som **Rekrytering** Power BI baserades på.

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
