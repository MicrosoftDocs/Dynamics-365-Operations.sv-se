---
title: Organisationsutbildning Power BI-innehåll
description: Den här artikeln beskriver Ekonomi och drift – Power BI-innehåll för organisationsutbildning.
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
- "263874"
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.openlocfilehash: 7b8f6c1b32876af3a6992ff73c6898ce5307c5a2
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206768"
---
# <a name="organizational-training-power-bi-content"></a>Organisationsutbildning Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver Ekonomi och drift – Power BI-innehåll för organisationsutbildning.

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport          | Innehåll                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Kursanalys | Registrering per plats, deltagare i kursen efter status och registreringslista |
| Kurstyper    | Kurstyper per kompetens                                                       |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Programdata används för att fylla i rapporter i innehållspaketet för organisationsutbildning. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                    | Innehåll                                                         | Relationer med andra entiteter |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Training\_CalendarOffset  | Kalenderförskjutningar till uppdela rapporter                                | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Company         | Företag att filtrera rapporter efter                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Course          | Kursen, beskrivning, lärares namn, plats, rum och status | Training\_CourseAgenda, Training\_CourseAttendees, Training\_CourseSkill |
| Training\_CourseAgenda    | Agenda, kurs och start- och sluttider                          | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Course |
| Training\_CourseAttendees | Namn, status, jobb och registreringsdatum                         | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Demographics, Training\_Employment, Training\_Course, Training\_WorkerName, Training\_WorkerTitle, Training\_Job, Training\_Position |
| Training\_CourseSkill     | Färdighet, färdighetstyp och nivå                                     | Training\_Course |
| Training\_Date            | Dagar, veckor, månader och år.                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Demographics    | Födelsedatum, kön, etniskt ursprung och civilstånd         | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Employment      | Startdatum, slutdatum och övergångsdatum                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Job             | Funktion, typ och rubrik                                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Position        | Befattning, titel och heltidsanställning (FTE)                  | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_WorkerName      | Förnamn, efternamn och fullständiga namn                             | Training\_CourseAttendees |
| Training\_WorkerTitle     | Titel och tjänsteålder                                         | Training\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
