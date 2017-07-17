---
title: "Power BI-innehåll för organisationsutbildning"
description: "Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för organisationsutbildning. Det förklarar hur du öppnar innehållspaketet, och beskriver datamodellen och de enheter som användes för att skapa paketet."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 26499bf5423bc3711d110bd7e548eda238162b7a
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Power BI-innehåll för organisationsutbildning
<a id="organizational-training-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för organisationsutbildning. Det förklarar hur du öppnar innehållspaketet, och beskriver datamodellen och de enheter som användes för att skapa paketet.

Åtkomst till innehållspaketet
<a id="accessing-the-content-pack" class="xliff"></a>
--------------------------

Du kan hitta innehållspaketet för organisationsutbildning i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Finance and Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

## Rapporter som ingår i innehållspaketet
<a id="reports-that-are-included-in-the-content-pack" class="xliff"></a>
När du har anslutit innehållspaketet till dina Finance and Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport          | Innehåll                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Kursanalys | Registrering per plats, deltagare i kursen efter status och registreringslista |
| Kurstyper    | Kurstyper per kompetens                                                       |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## Förstå datamodellen och enheterna
<a id="understanding-the-data-model-and-entities" class="xliff"></a>
Finance and Operations -data används för att fylla i rapporter i innehållspaketet för organisationsutbildning. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                    | Innehåll                                                         | Relationer med andra entiteter                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Training\_CalendarOffset  | Kalenderförskjutningar till uppdela rapporter                                | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Company         | Företag att filtrera rapporter efter                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Course          | Kursen, beskrivning, lärares namn, plats, rum och status | Training\_CourseAgenda Training\_CourseAttendees Training\_CourseSkill                                                                                                                             |
| Training\_CourseAgenda    | Agenda, kurs och start- och sluttider                          | Training\_Company Training\_CalendarOffset Training\_Date Training\_Course                                                                                                                         |
| Training\_CourseAttendees | Namn, status, jobb och registreringsdatum                         | Training\_Company Training\_CalendarOffset Training\_Date Training\_Demographics Training\_Employment Training\_Course Training\_WorkerName Training\_WorkerTitle Training\_Job Training\_Position |
| Training\_CourseSkill     | Färdighet, färdighetstyp och nivå                                     | Training\_Course                                                                                                                                                                                   |
| Training\_Date            | Dagar, veckor, månader och år.                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Demographics    | Födelsedatum, kön, etniskt ursprung och civilstånd         | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Employment      | Startdatum, slutdatum och övergångsdatum                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Job             | Funktion, typ och rubrik                                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Position        | Befattning, titel och heltidsanställning (FTE)                  | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_WorkerName      | Förnamn, efternamn och fullständiga namn                             | Training\_CourseAttendees                                                                                                                                                                          |
| Training\_WorkerTitle     | Titel och tjänsteålder                                         | Training\_CourseAttendees                                                                                                                                                                          |

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen Training.pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

## Ytterligare resurser
<a id="additional-resources" class="xliff"></a>
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





