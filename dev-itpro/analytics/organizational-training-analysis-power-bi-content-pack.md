---
title: "Företagets utbildning Power BI-innehåll"
description: "Det här avsnittet beskrivs Dynamics 365 för - organisationen utbildning Power BI-innehåll. Det förklarar hur du kommer åt det här innehållet och beskriver datamodellen och enheter som användes för att skapa innehåll pack."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Företagets utbildning Power BI-innehåll

Det här avsnittet beskrivs Dynamics 365 för - organisationen utbildning Power BI-innehåll. Det förklarar hur du kommer åt det här innehållet och beskriver datamodellen och enheter som användes för att skapa innehåll pack.

<a name="accessing-the-content-pack"></a>Åtkomst till content pack
--------------------------

Du hittar utbildning organisationens innehållet i biblioteket delade resurser i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehåll pack och ansluta den till din Microsoft Dynamics 365 för operationer finns [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i paketet innehåll
När du anslutit innehåll pack för operationer i Dynamics 365, visa rapporterna organisationens data. Om du aldrig har använt Microsoft Power BI innan du mer information om det i den [Power BI interaktiv utbildning sidan](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i paketet innehåll har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport          | Innehåll                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Kurs-analys | Registrering av plats, deltagare i kursen med status och Registreringslista |
| Kurstyper    | Kurstyper per kompetens                                                       |

Du kan filtrera de diagram och en sammanfattning av dessa rapporter och Fäst diagram och rubriker på instrumentpanelen. Mer information om hur du filtret och PIN-kod i Power BI finns [skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer används för att fylla i rapporterna i organisationens utbildning innehållet. Följande tabell visar enheterna att innehåll pack baserades på.

| Enhet                    | Innehåll                                                         | Relationer med andra entiteter                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utbildning\_CalendarOffset  | Förskjuter kalender till BITS-rapporter                                | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_företag         | Filtrera rapporter efter företag                                   | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_kurs          | Kursen, beskrivning, lärare namn, plats, plats och status | Utbildning\_utbildning av CourseAgenda\_CourseAttendees utbildning\_CourseSkill                                                                                                                             |
| Utbildning\_CourseAgenda    | Agenda kurs och start- och sluttider                          | Utbildning\_utbildning för företag\_CalendarOffset utbildning\_datum utbildning\_kurs                                                                                                                         |
| Utbildning\_CourseAttendees | Namn, status, jobb och registrering av datum                         | Utbildning\_utbildning för företag\_CalendarOffset utbildning\_datum utbildning\_befolkning utbildning\_anställning utbildning\_kurs utbildning\_utbildning av WorkerName\_WorkerTitle utbildning\_jobbet utbildning\_placering |
| Utbildning\_CourseSkill     | Färdigheten färdighetstyp och nivå                                     | Utbildning\_kurs                                                                                                                                                                                   |
| Utbildning\_dag            | Dagar, veckor, månader och år                                   | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_befolkning    | Datum för civilstånd, etniskt ursprung, kön och födelsedatum         | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_anställning      | Startdatum, slutdatum och övergångsdatum                        | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_jobb             | Funktionen, typ och rubrik                                        | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_placering        | Befattning, titel och motsvarande heltid (motsvarande HELTID)                  | Utbildning\_utbildning av CourseAgenda\_CourseAttendees                                                                                                                                                   |
| Utbildning\_WorkerName      | Förnamn, efternamn och fullständigt namn                             | Utbildning\_CourseAttendees                                                                                                                                                                          |
| Utbildning\_WorkerTitle     | Rubrik och tjänsteålder                                         | Utbildning\_CourseAttendees                                                                                                                                                                          |

Dessa poster används för att skapa beräknade mått i datamodellen. Dessa beräknas sedan används för att beräkna prestationsindikatorer (KPI: er) och rapporter som används i det aktuella innehållet. Du kan hämta och ändra filen Training.pbix från LCS om du vill inkludera ytterligare beräkningar på instrumentpanelen och rapporter. Detta är standard datamodellen som användes för att skapa innehåll pack. Du kan skapa en organisations innehållet och instrumentpanel som innehåller den information som du har lagt till när du har gjort ändringar.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



