---
title: "Power BI-innehåll för rekrytering"
description: "Det här avsnittet beskriver Dynamics 365 for Operations - Power BI-innehåll för rekrytering Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
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

# <a name="recruiting-power-bi-content"></a>Power BI-innehåll för rekrytering

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver Dynamics 365 for Operations - Power BI-innehåll för rekrytering Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
--------------------------

Du kan hitta innehållspaketet för rekrytering i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Rapporter som ingår i innehållspaketet
När du har anslutit innehållspaketet till dina Dynamics 365 for Operations-data kommer rapporterna att visa din organisations data. Om du aldrig har använt Microsoft Power BI tidigare kan du lära dig mer om det på sidan [Guidad utbildning för Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Rapporter som ingår i innehållspaketet har både diagram och tabeller med ytterligare information. Följande register beskriver rapporterna.

| Rapport                       | Innehåll                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analys av sökande           | Sökande efter jobb, sökandekällor, sökande efter plats och antal sökande           |
| Sökandestatus             | Sökande efter typ och status och sökandestatus                                                    |
| Demografi för sökande       | Sökande efter ålder och kön, samt sökande efter utbildningsnivå och status                             |
| Rekryteringsanalys          | Nettoanställningskvot, genomsnittligt antal dagar för att anställa, andelen dåliga anställningar och kostnader för rekrytering                    |
| Rekryteringsprojekt – analys | Antal rekryteringsprojekt, lediga jobb per rekryteringsprojekt och sökande per rekryteringsprojekt |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 for Operations-data används för att fylla i rapporter i innehållspaketet för rekrytering. Följande tabell visar enheterna som innehållspaketet baserades på.

| Enhet                          | Innehåll                                                         | Relationer med andra entiteter                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rekrytering\_Sökande           | Sökande, anställda sökande, nettoanställningskvot och kostnader          | Recruiting\_ApplicantName Recruiting\_Company Recruiting\_CalendarOffset Recuriting\_Date Recruiting\_GeographicLocation Recruiting\_Demographics Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject                                |
| Recruiting\_ApplicantName       | Sökandes förnamn, efternamn och fullständiga namn                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_CalendarOffset      | Kalenderförskjutningar till uppdela rapporter                                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Company             | Företag att filtrera rapporter efter                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Date                | Dagar, veckor, månader och år.                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Demographics        | Födelsedatum, kön, etniskt ursprung och civilstånd         | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_EmployedApplicant   | Sökande, prestanda, startdatum och typ av sökande           | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_ApplicantName Recruiting\_Employment Recruiting\_Performance Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject          |
| Recruiting\_Employment          | Startdatum, slutdatum och övergångsdatum                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_GeographicLocation  | Stad, region, postnummer och delstat eller region                 | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Job                 | Funktion, typ och rubrik                                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Media               | Sökandes källa                                             | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Performance         | Värdering, beskrivning och bedömningsmodellen                            | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_RecruitmentProject  | Projektbeskrivning, projektstatus och lediga jobb                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_TerminatedApplicant | Uppsagda sökande, orsak, prestanda och uppsägningsdatum | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_Performance Recruiting\_Demographics Recruiting\_Employment Recruiting\_Media Recruiting\_RecruitmentProject Recruiting\_ApplicantName |

Dessa enheter används för att skapa beräknade mått. Beräknade åtgärder används sedan för att beräkna huvudindikatorerna för prestanda (KPI) samt de rapporter som används i innehållspaketet. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra filen Recruiting.pbix från LCS. Filen är den standarddatamodell som använts för att skapa innehållspaketet. När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





