---
title: "Power BI-innehåll om kompensationer och förmåner"
description: "Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för kompensationer och förmåner. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
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
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f403416921d2eede9d0071a13af09e1103f91692
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="compensation-and-benefits-power-bi-content"></a>Power BI-innehåll om kompensationer och förmåner

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver Finance and Operations - Power BI-innehåll för kompensationer och förmåner. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
--------------------------

Du kan hitta innehållspaketet för kompensationer och förmåner i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Finance and Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Finance and Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                     | Innehåll                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analys av kompensationer och förmåner | Timlön och avlönade anställda i företag, genomsnittlig timlön, genomsnittliga lön, anställda efter anställningstyp och planregistrering |
| Anställningsförmåner          | Anmälan till medarbetare efter valt förmån                                                                                               |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Finance and Operations-data används för att fylla i rapporter i innehållspaketet för kompensationer och förmåner. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                            | Innehåll                                                                                                   | Relationer med andra entiteter                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Personal\_Motkalender         | Kalenderförskjutningar till uppdela rapporter                                                                          | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workorce\_WorkerTrend Workforce\_TerminatedWorker                                                                                                                                                                                                                     |
| Personal\_företag                | Företag att filtrera rapporter efter                                                                             | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Personal\_Kompensation           | Lönesatsen och frekvens över tiden                                                                           | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Personal\_AktuellKompensation    | Lönesatsen och frekvens per aktuellt datum                                                              | Workforce\_Company Workforce\_Compensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Personalen\_AktuellBefattning        | Befattningar per innevarande datum, heltidslön (FTE) öppna positioner och öppna till fulla befattningar | Personal\_jobbpersonal\_befattning                                                                                                                                                                                                                                                                                               |
| Personal\_AktuellArbetare          | Arbetare per aktuellt datum, ålder och antal anställda                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position Workforce\_WorkerBenefit                                            |
| Personal\_dag                   | Dagar, veckor, månader och år.                                                                             | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                     |
| Personal\_Demografi           | Födelsedatum, kön, etniskt ursprung och civilstånd                                                   | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_anställning             | Startdatum, slutdatum och övergångsdatum                                                                  | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_GeograpiskPlats     | Stad, region, postnummer och delstat eller region                                                           | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_jobb                    | Funktion, typ och rubrik                                                                                  | Personal\_AktuellBefattning Personal\_AktuellArbetare                                                                                                                                                                                                                                                                              |
| Personal\_FöregåendeBefattningTilldelning | Orsak för tilldelningen, startdatum, slutdatum och jobb                                                           | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Personal\_Resultat            | Värdering, beskrivning och bedömningsmodellen                                                                      | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_Befattning               | Avdelning, FTE, befattning, befattningstyp och titel                                                        | Personal\_AktuellBefattning Personal\_AktuellArbetare                                                                                                                                                                                                                                                                              |
| Personal\_BefattningTrend          | Positioner över tid, FTE och jobb                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Personal\_RapporterTillArbetareNamn    | Förnamn, efternamn och fullständiga namn                                                                       | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_kompetens                  | Färdighet, färdighetstyp och värdering                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Personal\_AvslutadArbetare       | Avslutade arbetare, uppsägningsdatum, titel, befattning och jobb                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position Workforce\_WorkerBenefit |
| Personal\_ArbetareFörmån          | Giltighetsdatum, förmånsalternativ, förmånsplanen och förmånstyp                                             | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_ArbetareNamn             | Förnamn, efternamn och fullständiga namn                                                                       | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_ArbetareTitel            | Titel och tjänsteålder                                                                                   | Personal\_AktuellArbetare Personal\_AvslutadArbetare Personal\_ArbetareTrend                                                                                                                                                                                                                                                       |
| Personal\_ArbetareTrend             | Arbetare över tid, antal anställda, företag och befattning                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_WorkerBenefit                     |

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen CompensationandBenefits.pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





