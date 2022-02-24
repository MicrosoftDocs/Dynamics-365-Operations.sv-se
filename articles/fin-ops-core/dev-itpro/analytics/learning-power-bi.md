---
title: Lär dig Power BI-innehåll
description: Det här avsnittet beskriver Learning Power BI-innehållet.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 46b7a442470d1fe78ebc5c9d5a0c6e155c0d9918
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685259"
---
# <a name="learning-power-bi-content"></a>Lär dig Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **Learning** Microsoft Power BI-innehållet.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

Rapporter som ingår i **Learning** Power BI-innehållet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                | Innehåll |
|-----------------------|----------|
| Översikt - Learning     | Sammanfattning av andra rapporter |
| Kursanalys       | Registrering efter plats, deltagare efter status, kurser efter typ per företag, samt kursnärvaro efter jobb |
| Registreringsanalys | Registreringslista |
| Kurstyper          | Kurstyper per kompetens |
| Instruktörsanalys   | Kurskvot för instruktörer, antal instruktörer, kurser efter instruktör, kurser per lärare och kursagenda per instruktör |
| Erbjudna kurser       | Lista över kurser |
| Kursdesign        | Kursagenda |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapporterna i **Learning** Power BI-innehållet. Denna tabell visar enheterna som innehållet baserades på.

| Enhet           | Innehåll                                                         | Relationer med andra entiteter |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Kalenderförskjutning  | Kalenderförskjutningar till uppdela rapporter                                | Kursagenda, kursdeltagare |
| Företag          | Företag att filtrera rapporter efter                                   | Kursagenda, kursdeltagare |
| Kurs           | Kursen, beskrivning, lärares namn, plats, rum och status | Kursagenda, kursdeltagare, kurskompetens |
| Kursagenda    | Agenda, kurs och start- och sluttider                          | Företaget, kalenderförskjutning, datum, kurs |
| Kursdeltagare | Namn, status, jobb och registreringsdatum                         | Företag, kalenderförskjutning, datum, kurs, demografi, anställning, kurs, medarbetarens namn, medarbetares titel, jobb, befattning |
| Kursfärdighet     | Färdighet, färdighetstyp och nivå                                     | Kurs |
| Datum             | Dagar, veckor, månader och år.                                   | Kursagenda, kursdeltagare |
| Demografi     | Födelsedatum, kön, etniskt ursprung och civilstånd         | Kursagenda, kursdeltagare |
| Anställning       | Startdatum, slutdatum och övergångsdatum                        | Kursagenda, kursdeltagare |
| Jobb              | Funktion, typ och rubrik                                        | Kursagenda, kursdeltagare |
| Befattning         | Befattning, titel och heltidsanställning (FTE)                  | Kursagenda, kursdeltagare |
| Namn på medarbetare    | Förnamn, efternamn och fullständiga namn                             | Kursdeltagare |
| Medarbetartitel   | Titel och tjänsteålder                                         | Kursdeltagare |
