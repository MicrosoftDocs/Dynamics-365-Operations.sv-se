---
title: "Medarbetarens kompetenser och utveckling Power BI-innehåll"
description: "Det här avsnittet beskrivs Dynamics 365 för verksamhet – medarbetaren kompetenser och utveckling Power BI-innehåll. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om personer som användes för att skapa innehåll pack och datamodellen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1fd6f978b6a871f9f7d3d5e91ab3e0aac789ae88
ms.lasthandoff: 03/31/2017


---

# <a name="employee-competencies-and-development-power-bi-content"></a>Medarbetarens kompetenser och utveckling Power BI-innehåll

Det här avsnittet beskrivs Dynamics 365 för verksamhet – medarbetaren kompetenser och utveckling Power BI-innehåll. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om personer som användes för att skapa innehåll pack och datamodellen.

<a name="accessing-the-content-pack"></a>Åtkomst till content pack
--------------------------

Du hittar medarbetarens kompetenser och utveckling innehåll pack i biblioteket delade resurser i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehåll pack och ansluta den till din Microsoft Dynamics 365 för operationer finns [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i paketet innehåll
När du anslutit innehåll pack för operationer i Dynamics 365, visa rapporterna organisationens data. Om du aldrig har använt Microsoft Power BI innan du mer information om det i den [Power BI interaktiv utbildning sidan](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i paketet innehåll har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                            | Innehåll                                               |
|-----------------------------------|--------------------------------------------------------|
| Kunskap och utveckling | Team medlem färdighetstyper och team medlem färdighet efter typ |
| Kompetensprofil                     | Färdighetsprofil för vald medarbetare                |
| Färdighetsanalys                    | Färdighet efter typ och värdering                              |

Du kan filtrera de diagram och en sammanfattning av dessa rapporter och Fäst diagram och rubriker på instrumentpanelen. Mer information om hur du filtret och PIN-kod i Power BI finns [skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer används för att fylla i rapporterna i medarbetarens kompetenser och utveckling av innehållet. Följande tabell visar enheterna att innehåll pack baserades på.

| Enhet                            | Innehåll                                                                                                   | Relationer med andra entiteter                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Personalen\_CalendarOffset         | Förskjuter kalender till BITS-rapporter                                                                          |                                                                                                                                                                                                                                                                                                         |
| Personalen\_företag                | Filtrera rapporter efter företag                                                                             |                                                                                                                                                                                                                                                                                                         |
| Personalen\_kompensation           | Lönesatsen och ofta över tiden                                                                           |                                                                                                                                                                                                                                                                                                         |
| Personalen\_CurrentCompensation    | Lönesatsen och frekvens per aktuellt datum                                                              | Personalen\_Company personalen\_CurrentCompensation personal\_befolkning personalen\_jobbet personalen\_Position                                                                                                                                                                                            |
| Personalen\_CurrentPosition        | Befattningar per innevarande datum, motsvarande heltid (motsvarande HELTID) öppna positioner och öppna till fylls positioner | Personalen\_jobbet personalen\_placering                                                                                                                                                                                                                                                                      |
| Personalen\_CurrentWorker          | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Personalen\_företagets personal\_kompensation personalen\_GeographicLocation personal\_prestanda personalen\_PersonSkill personal\_personalen WorkerName\_ReportsToWorkerName personal\_WorkerTitle personal\_befolkning personalen\_jobbet personalen\_anställning personalen\_Position                     |
| Personalen\_dag                   | Dagar, veckor, månader och år                                                                             |                                                                                                                                                                                                                                                                                                         |
| Personalen\_befolkning           | Datum för civilstånd, etniskt ursprung, kön och födelsedatum                                                   |                                                                                                                                                                                                                                                                                                         |
| Personalen\_anställning             | Startdatum, slutdatum och övergångsdatum                                                                  |                                                                                                                                                                                                                                                                                                         |
| Personalen\_GeographicLocation     | Stad, region, postnummer kod och region                                                           |                                                                                                                                                                                                                                                                                                         |
| Personalen\_jobb                    | Funktionen, typ och rubrik                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Personalen\_JobPreferredSkill      | Prioritet, klassificering, kunskaper och kompetens                                                                 | Personalen\_kompetens personalen\_jobb                                                                                                                                                                                                                                                                         |
| Personalen\_PastPositionAssignment | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Personalen\_ClaendarOffset personal\_datum personalen\_jobbet personalen\_placering                                                                                                                                                                                                                            |
| Personalen\_prestanda            | Klassificering, beskrivning och bedömningsmodellen                                                                      |                                                                                                                                                                                                                                                                                                         |
| Personalen\_PersonSkill            | Nivå, kompetens och Nivådatum                                                                               | Personalen\_kompetens                                                                                                                                                                                                                                                                                        |
| Personalen\_PersonSkillAnalysis    | Certifierad, nivå och nivåerna datum och färdighet                                                                    | Personalen\_WorkerName personal\_kompetens                                                                                                                                                                                                                                                                  |
| Personalen\_placering               | Avdelning, FTE, Befattningstyp, befattning och titel                                                        |                                                                                                                                                                                                                                                                                                         |
| Personalen\_PositionTrend          | Positioner i förhållande till tid, motsvarande HELTID och jobb                                                                          | Personalen\_CalendarOffset personal\_datum personalen\_jobbet personalen\_placering                                                                                                                                                                                                                            |
| Personalen\_ReportsToWorkerName    | Förnamn, efternamn och fullständigt namn                                                                       |                                                                                                                                                                                                                                                                                                         |
| Personalen\_kompetens                  | Färdighet, färdighetstyp och klassificering                                                                              |                                                                                                                                                                                                                                                                                                         |
| Personalen\_TerminatedWorker       | Avslutade arbetare uppsägningsdatum, namn, befattning och jobb                                             | Personalen\_företag personalen\_kompensation personalen\_GeographicLocation personal\_prestanda personalen\_WorkerName personal\_ReportsToWorkerName personal\_CalendarOffset takt\_datum personalen\_WorkerTitle personal\_befolkning personalen\_anställning personalen\_jobbet personalen\_Position |
| Personalen\_WorkerName             | Förnamn, efternamn och fullständigt namn                                                                       |                                                                                                                                                                                                                                                                                                         |
| Personalen\_WorkerTitle            | Rubrik och tjänsteålder                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Workorce\_WorkerTrend             | Arbetare över tid, antal anställda, företag och befattning                                                        | Personalen\_företagets personal\_kompensation personalen\_GeographicLocation personal\_prestanda personalen\_WorkerName personal\_ReportsToWorkerName personal\_CalendarOffset takt\_datum personalen\_WorkerTitle personal\_befolkning personalen\_anställning personalen\_jobb                     |

Dessa poster används för att skapa beräknade mått i datamodellen. Dessa beräknas sedan används för att beräkna prestationsindikatorer (KPI: er) och rapporter som används i det aktuella innehållet. Du kan hämta och ändra filen CompetenciesandDevelopment.pbix från LCS om du vill inkludera ytterligare beräkningar på instrumentpanelen och rapporter. Detta är standard datamodellen som användes för att skapa innehåll pack. Du kan skapa en organisations innehållet och instrumentpanel som innehåller den information som du har lagt till när du har gjort ändringar.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



