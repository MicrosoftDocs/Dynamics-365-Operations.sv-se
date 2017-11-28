---
title: "Power BI-innehåll för medarbetares kompetenser och utveckling"
description: "Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för medarbetares kompetenser och utveckling. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b2b3d96a64a552d1f0e0144dcbd809964fdf63c4
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="employee-competencies-and-development-power-bi-content"></a>Power BI-innehåll för medarbetares kompetenser och utveckling

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för medarbetares kompetenser och utveckling. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
--------------------------

Du kan hitta innehållspaketet för medarbetares kompetenser och utveckling i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Finance and Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Finance and Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                            | Innehåll                                               |
|-----------------------------------|--------------------------------------------------------|
| Analys av kompetenser och utveckling | Teammedlemmens färdighetstyper och teammedlemmens färdighet efter typ |
| Kompetensprofil                     | Kompetensprofil för vald medarbetare.                |
| Kompetensanalys                    | Kompetens efter typ och värdering                              |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Finance and Operations-data används för att fylla i rapporter i innehållspaketet för medarbetares kompetenser och utveckling. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                            | Innehåll                                                                                                   | Relationer med andra entiteter                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Personal\_Motkalender         | Kalenderförskjutningar till uppdela rapporter                                                                          |                                                                                                                                                                                                                                                                                                         |
| Personal\_företag                | Företag att filtrera rapporter efter                                                                             |                                                                                                                                                                                                                                                                                                         |
| Personal\_Kompensation           | Lönesatsen och frekvens över tiden                                                                           |                                                                                                                                                                                                                                                                                                         |
| Personal\_AktuellKompensation    | Lönesatsen och frekvens per aktuellt datum                                                              | Workforce\_Company Workforce\_CurrentCompensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                            |
| Personalen\_AktuellBefattning        | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Personal\_jobbpersonal\_befattning                                                                                                                                                                                                                                                                      |
| Personal\_AktuellArbetare          | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_PersonSkill Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position                     |
| Personal\_dag                   | Dagar, veckor, månader och år.                                                                             |                                                                                                                                                                                                                                                                                                         |
| Personal\_Demografi           | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   |                                                                                                                                                                                                                                                                                                         |
| Personal\_anställning             | Startdatum, slutdatum och övergångsdatum                                                                  |                                                                                                                                                                                                                                                                                                         |
| Personal\_GeograpiskPlats     | Stad, region, postnummer och delstat eller region                                                           |                                                                                                                                                                                                                                                                                                         |
| Personal\_jobb                    | Funktion, typ och rubrik                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Workforce\_JobPreferredSkill      | Prioritet, värdering, kompetens och kompetensnivå                                                                 | Workforce\_Skill Workforce\_Job                                                                                                                                                                                                                                                                         |
| Personal\_FöregåendeBefattningTilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Workforce\_ClaendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Personal\_Resultat            | Värdering, beskrivning och bedömningsmodellen                                                                      |                                                                                                                                                                                                                                                                                                         |
| Personal\_PersonKompetens            | Nivå, nivådatum och kompetens                                                                               | Personal\_kompetens                                                                                                                                                                                                                                                                                        |
| Personal\_PersonKompetensAnalys    | Certifierad, nivå, nivådatum och kompetens                                                                    | Workforce\_WorkerName Workforce\_Skill                                                                                                                                                                                                                                                                  |
| Personal\_Befattning               | Avdelning, FTE, befattning, befattningstyp och titel                                                        |                                                                                                                                                                                                                                                                                                         |
| Personal\_BefattningTrend          | Positioner över tid, FTE och jobb                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Personal\_RapporterTillArbetareNamn    | Förnamn, efternamn och fullständiga namn                                                                       |                                                                                                                                                                                                                                                                                                         |
| Personal\_kompetens                  | Färdighet, färdighetstyp och värdering                                                                              |                                                                                                                                                                                                                                                                                                         |
| Personal\_AvslutadArbetare       | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position |
| Personal\_ArbetareNamn             | Förnamn, efternamn och fullständiga namn                                                                       |                                                                                                                                                                                                                                                                                                         |
| Personal\_ArbetareTitel            | Titel och tjänsteålder                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Personal\_ArbetareTrend             | Arbetare över tid, antal anställda, företag och befattning                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job                     |

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen CompetenciesandDevelopment.pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





