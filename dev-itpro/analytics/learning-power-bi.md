---
title: "Learning Power BI-innehåll"
description: "Det här avsnittet beskriver Learning Power BI-innehållet. Det förklarar hur du öppnar rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: JCart
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a3f28d21a7e73d3ad462c5cc37198dd2b6f5f8af
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="learning-power-bi-content"></a>Learning Power BI-innehåll

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver Microsoft Power BI-innehållet för **utbildning (Learning)**. Det förklarar hur du öppnar innehållspaketet, och beskriver den datamodell och de enheter som användes för att skapa paketet.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll

Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (uppdatering i juli 2017), så hittar du Power BI-innehållet **Learning** i det gemensamma tillgångsbiblioteket i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

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

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehåll. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen .pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

