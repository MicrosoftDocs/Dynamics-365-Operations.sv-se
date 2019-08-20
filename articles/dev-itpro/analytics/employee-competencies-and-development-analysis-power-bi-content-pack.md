---
title: Medarbetares kompetenser och utveckling Power BI-innehåll
description: Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för medarbetares kompetenser och utveckling.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1b1a0c8f756601dc342ab44364ea362cf2698f3c
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849747"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Medarbetares kompetenser och utveckling Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för medarbetares kompetenser och utveckling. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Finance and Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                            | Innehåll                                               |
|-----------------------------------|--------------------------------------------------------|
| Analys av kompetenser och utveckling | Teammedlemmens färdighetstyper och teammedlemmens färdighet efter typ |
| Kompetensprofil                     | Kompetensprofil för vald medarbetare.                |
| Kompetensanalys                    | Kompetens efter typ och värdering                              |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Finance and Operations-data används för att fylla i rapporter i innehållspaketet för medarbetares kompetenser och utveckling. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                            | Innehåll                                                                                                   | Relationer med andra entiteter |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Personal\_Motkalender         | Kalenderförskjutningar till uppdela rapporter                                                                          | |
| Personal\_företag                | Företag att filtrera rapporter efter                                                                             | |
| Personal\_Kompensation           | Lönesatsen och frekvens över tiden                                                                           | |
| Personal\_AktuellKompensation    | Lönesatsen och frekvens per aktuellt datum                                                              | Personal\_Företag, Personal\_CurrentCompensation, Personal\_Demografi, Personal\_Jobb, Personal\_Befattning |
| Personalen\_AktuellBefattning        | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Personal\_jobbpersonal\_befattning |
| Personal\_AktuellArbetare          | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Personal\_Företagets personal\_Kompensation, Personal\_GeographicLocation, Personal\_Prestanda, Personal\_PersonSkill, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Jobb, Personal\_Anställning, Personal\_Position |
| Personal\_dag                   | Dagar, veckor, månader och år.                                                                             | |
| Personal\_Demografi           | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   | |
| Personal\_anställning             | Startdatum, slutdatum och övergångsdatum                                                                  | |
| Personal\_GeograpiskPlats     | Stad, region, postnummer och delstat eller region                                                           | |
| Personal\_jobb                    | Funktion, typ och rubrik                                                                                  | |
| Workforce\_JobPreferredSkill      | Prioritet, värdering, kompetens och kompetensnivå                                                                 | Personal\_Kompetens, Personal\_Jobb |
| Personal\_FöregåendeBefattningTilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Personal\_CalendarOffset, Personal\_Datum, Personal\_Jobb, Personal\_Befattning |
| Personal\_Resultat            | Värdering, beskrivning och bedömningsmodellen                                                                      | |
| Personal\_PersonKompetens            | Nivå, nivådatum och kompetens                                                                               | Personal\_kompetens |
| Personal\_PersonKompetensAnalys    | Certifierad, nivå, nivådatum och kompetens                                                                    | Personal\_WorkerName, Personal\_Kompetens |
| Personal\_Befattning               | Avdelning, FTE, befattning, befattningstyp och titel                                                        | |
| Personal\_BefattningTrend          | Positioner över tid, FTE och jobb                                                                          | Personal\_CalendarOffset, Personal\_Datum, Personal\_Jobb, Personal\_Befattning |
| Personal\_RapporterTillArbetareNamn    | Förnamn, efternamn och fullständiga namn                                                                       | |
| Personal\_kompetens                  | Färdighet, färdighetstyp och värdering                                                                              | |
| Personal\_AvslutadArbetare       | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                                             | Personal\_Företag, Personal\_Kompensation, Personal\_GeographicLocation, Personal\_Prestanda, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_CalendarOffset, Personal\_Datum, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Anställning, Personal\_Jobb, Personal\_Befattning |
| Personal\_ArbetareNamn             | Förnamn, efternamn och fullständiga namn                                                                       | |
| Personal\_ArbetareTitel            | Titel och tjänsteålder                                                                                   | |
| Personal\_ArbetareTrend             | Arbetare över tid, antal anställda, företag och befattning                                                        | Personal\_Företag, Personal\_Kompensation, Personal\_GeographicLocation, Personal\_Prestanda, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_CalendarOffset, Personal\_Datum, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Anställning, Personal\_Jobb |
