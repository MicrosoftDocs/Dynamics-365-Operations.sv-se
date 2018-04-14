---
title: "Learning Power BI-innehåll"
description: "Det här avsnittet beskriver Learning Power BI-innehållet."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: e5a78812aabaa5c835fe23787a9cbb57d1a7770e
ms.contentlocale: sv-se
ms.lasthandoff: 12/19/2017

---

# <a name="learning-power-bi-content"></a>Learning Power BI-innehåll

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehållet för **utbildning (Learning)**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

De rapporter som ingår i Power BI-innehållspaketet **Learning** har både diagram och tabeller som innehåller ytterligare information. Följande register beskriver rapporterna.

| Rapport                | Innehåll |
|-----------------------|----------|
| Översikt - Learning     | Sammanfattning av andra rapporter |
| Kursanalys       | Registrering efter plats, deltagare efter status, kurser efter typ per företag, samt kursnärvaro efter jobb |
| Registreringsanalys | Registreringslista |
| Kurstyper          | Kurstyper per kompetens |
| Instruktörsanalys   | Kurskvot för instruktörer, antal instruktörer, kurser efter instruktör, kurser per lärare och kursagenda per instruktör |
| Erbjudna kurser       | Lista över kurser |
| Kursdesign        | Kursagenda |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapporterna i Power-Bi-innehållet för **Learning**. Denna tabell visar enheterna som innehållet baserades på.

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



