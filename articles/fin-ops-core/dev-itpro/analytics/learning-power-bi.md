---
title: Lär dig Power BI-innehåll
description: Den här artikeln beskriver Learning Power BI-innehållet.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a7aca9e47ed26dcb4ef7f4b9aee72987e2d8fdd2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273972"
---
# <a name="learning-power-bi-content"></a>Lär dig Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver **Learning** Microsoft Power BI-innehållet.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

Rapporter som ingår i **Learning** Power BI-innehållet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                | Innehåll |
|-----------------------|----------|
| Översikt – Learning     | Sammanfattning av andra rapporter |
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
