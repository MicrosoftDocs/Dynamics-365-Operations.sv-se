---
title: Power BI-innehåll för kompensationer och förmåner.
description: Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för kompensationer och förmåner.
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
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 48c968dfacd951d571f91fdcd809454f96f27a02
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848457"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Power BI-innehåll för kompensationer och förmåner.

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för kompensationer och förmåner. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Finance and Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                     | Innehåll                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analys av kompensationer och förmåner | Timlön och avlönade anställda i företag, genomsnittlig timlön, genomsnittliga lön, anställda efter anställningstyp och planregistrering |
| Anställningsförmåner          | Anmälan till medarbetare efter valt förmån                                                                                               |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Finance and Operations-data används för att fylla i rapporter i innehållspaketet för kompensationer och förmåner. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                            | Innehåll                                                                                                   | Relationer med andra entiteter |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Personal\_Motkalender         | Kalenderförskjutningar till uppdela rapporter                                                                          | Personal\_PastPositionAssignment, Personal\_PositionTrend, Personal\_WorkerTrend, Personal\_TerminatedWorker |
| Personal\_företag                | Företag att filtrera rapporter efter                                                                             | Personal\_CurrentCompensation, Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_Kompensation           | Lönesatsen och frekvens över tiden                                                                           | Personal\_CurrentCompensation, Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_AktuellKompensation    | Lönesatsen och frekvens per aktuellt datum                                                              | Personal\_Företag, Personal\_Kompensation, Personal\_Demografi, Personal\_Jobb, Personal\_Befattning |
| Personalen\_AktuellBefattning        | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Personal\_Jobb, Personal\_Befattning |
| Personal\_AktuellArbetare          | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Personal\_Företag, Personal\_Kompensation, Personal\_GeographicLocation, Personal\_Resultat, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Jobb, Personal\_Anställning, Personal\_Befattning, Personal\_WorkerBenefit |
| Personal\_dag                   | Dagar, veckor, månader och år.                                                                             | Personal\_PastPositionAssignment, Personal\_PositionTrend, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_Demografi           | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_anställning             | Startdatum, slutdatum och övergångsdatum                                                                  | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_GeograpiskPlats     | Stad, region, postnummer och delstat eller region                                                           | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_jobb                    | Funktion, typ och rubrik                                                                                  | Personal\_CurrentPosition, Personal\_CurrentWorker |
| Personal\_FöregåendeBefattningTilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Personal\_CalendarOffset, Personal\_Datum, Personal\_Jobb, Personal\_Befattning |
| Personal\_Resultat            | Värdering, beskrivning och bedömningsmodellen                                                                      | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_Befattning               | Avdelning, FTE, befattning, befattningstyp och titel                                                        | Personal\_CurrentPosition, Personal\_CurrentWorker |
| Personal\_BefattningTrend          | Positioner över tid, FTE och jobb                                                                          | Personal\_CalendarOffset, Personal\_Datum, Personal\_Jobb, Personal\_Befattning |
| Personal\_RapporterTillArbetareNamn    | Förnamn, efternamn och fullständiga namn                                                                       | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_kompetens                  | Färdighet, färdighetstyp och värdering                                                                              | |
| Personal\_AvslutadArbetare       | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                                             | Personal\_Företag, Personal\_Kompensation, Personal\_GeographicLocation, Personal\_Resultat, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_CalendarOffset, Personal\_Datum, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Anställning, Personal\_Jobb, Personal\_Befattning, Personal\_WorkerBenefit |
| Personal\_ArbetareFörmån          | Giltighetsdatum, förmånsalternativ, förmånsplanen och förmånstyp                                             | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_ArbetareNamn             | Förnamn, efternamn och fullständiga namn                                                                       | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_ArbetareTitel            | Titel och tjänsteålder                                                                                   | Personal\_CurrentWorker, Personal\_TerminatedWorker, Personal\_WorkerTrend |
| Personal\_WorkerTrend            | Arbetare över tid, antal anställda, företag och befattning                                                        | Personal\_Företag, Personal\_Kompensation, Personal\_GeographicLocation, Personal\_Resultat, Personal\_WorkerName, Personal\_ReportsToWorkerName, Personal\_CalendarOffset, Personal\_Datum, Personal\_WorkerTitle, Personal\_Demografi, Personal\_Anställning, Personal\_Jobb, Personal\_WorkerBenefit |
