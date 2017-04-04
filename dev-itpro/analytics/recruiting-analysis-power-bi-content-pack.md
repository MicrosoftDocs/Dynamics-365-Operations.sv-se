---
title: "Rekrytering Power BI-innehåll"
description: "Det här avsnittet beskrivs Dynamics 365 för verksamhet – rekrytering Power BI-innehåll. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om personer som användes för att skapa innehåll pack och datamodellen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Rekrytering Power BI-innehåll

Det här avsnittet beskrivs Dynamics 365 för verksamhet – rekrytering Power BI-innehåll. Det förklaras hur du öppnar rapporter som ingår i paketet innehåll och ger information om personer som användes för att skapa innehåll pack och datamodellen.

<a name="accessing-the-content-pack"></a>Åtkomst till content pack
--------------------------

Du hittar rekrytering innehållet i biblioteket delade resurser i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehåll pack och ansluta den till din Microsoft Dynamics 365 för operationer finns [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i paketet innehåll
När du anslutit innehåll pack för operationer i Dynamics 365, visa rapporterna organisationens data. Om du aldrig har använt Microsoft Power BI innan du mer information om det i den [Power BI interaktiv utbildning sidan](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i paketet innehåll har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                       | Innehåll                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analys av sökande           | Sökande efter jobb, sökande källor, sökande efter lagerställe och antalet sökande           |
| Sökandestatus             | Sökande efter typ och status och Sökandestatus                                                    |
| Sökande befolkning       | Sökande efter ålder- och könsvärden och sökande efter utbildningsnivå och status                             |
| Rekrytering-analys          | NET hyra kvoten, genomsnittligt antal dagar för att anställa andelen dålig hires och kostnader för rekrytering                    |
| Analys av projekt för rekrytering | Antal rekryteringsprojekt inledningsfraser per rekryteringsprojekt och sökande per rekryteringsprojekt |

Du kan filtrera de diagram och en sammanfattning av dessa rapporter och Fäst diagram och rubriker på instrumentpanelen. Mer information om hur du filtret och PIN-kod i Power BI finns [skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer används för att fylla i rapporterna i rekrytering innehållet. Följande tabell visar enheterna att innehåll pack baserades på.

| Enhet                          | Innehåll                                                         | Relationer med andra entiteter                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rekrytering\_sökande           | Sökande, anställda sökande, net hyra kvoten och kostnader          | Rekrytering\_ApplicantName rekrytering\_Company rekrytering\_CalendarOffset Recuriting\_datum rekrytering\_GeographicLocation rekrytering\_befolkning rekrytering\_jobbet rekrytering\_Media rekrytering\_RecruitmentProject                                |
| Rekrytering\_ApplicantName       | Sökande förnamn, efternamn och fullständigt namn                   | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_CalendarOffset      | Förskjuter kalender till BITS-rapporter                                | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_företag             | Filtrera rapporter efter företag                                   | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_dag                | Dagar, veckor, månader och år                                   | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_befolkning        | Datum för civilstånd, etniskt ursprung, kön och födelsedatum         | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_EmployedApplicant   | Sökande, prestanda, startdatum och typ av sökande           | Rekrytering\_Company rekrytering\_CalendarOffset rekrytering\_datum rekrytering\_GeographicLocation rekrytering\_ApplicantName rekrytering\_anställning rekrytering\_prestanda rekrytering\_jobbet rekrytering\_Media rekrytering\_RecruitmentProject          |
| Rekrytering\_anställning          | Startdatum, slutdatum och övergångsdatum                        | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_GeographicLocation  | Stad, region, postnummer kod och region                 | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_jobb                 | Funktionen, typ och rubrik                                        | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_Media               | Källa för sökande                                             | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_prestanda         | Klassificering, beskrivning och bedömningsmodellen                            | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_RecruitmentProject  | Projektbeskrivning, projektstatus och öppningar                | Rekrytering\_sökande rekrytering\_rekrytering av EmployedApplicant\_TerminatedApplicant                                                                                                                                                               |
| Rekrytering\_TerminatedApplicant | Avslutade sökande, orsak, prestanda och uppsägningsdatum | Rekrytering\_Company rekrytering\_CalendarOffset rekrytering\_datum rekrytering\_GeographicLocation rekrytering\_prestanda rekrytering\_befolkning rekrytering\_anställning rekrytering\_Media rekrytering\_rekrytering RecruitmentProject\_ApplicantName |

Dessa poster används för att skapa beräknade mått. Dessa beräknas sedan används för att beräkna prestationsindikatorer (KPI: er) och rapporter som används i det aktuella innehållet. Du kan hämta och ändra filen Recruiting.pbix från LCS om du vill inkludera ytterligare beräkningar på instrumentpanelen och rapporter. Detta är standard datamodellen som användes för att skapa innehåll pack. Du kan skapa en organisations innehållet och instrumentpanel som innehåller den information som du har lagt till när du har gjort ändringar.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



