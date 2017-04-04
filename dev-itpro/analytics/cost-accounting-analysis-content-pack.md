---
title: "Kostnadsredovisningsanalys Power BI-innehåll"
description: "Det här avsnittet beskrivs vad som ska ingå i analysen kostnadsredovisning Power BI-innehåll. Det förklaras hur du öppnar Power BI-rapporter och ger information om personer som användes för att skapa innehåll och datamodellen."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>Kostnadsredovisningsanalys Power BI-innehåll

Det här avsnittet beskrivs vad som ska ingå i analysen kostnadsredovisning Power BI-innehåll. Det förklaras hur du öppnar Power BI-rapporter och ger information om personer som användes för att skapa innehåll och datamodellen.

<a name="overview"></a>Översikt
--------

Den **Kostnadsredovisningsanalys** Microsoft Power BI innehållet riktar sig till domänkontrollanter kostnad eller någon som är ansvarig för att utföra kostnadskontroll inom en organisation. Den innehåller viktiga mätvärden som kostnad, omfattningen och kostnadstariff genom verklig kostnad och budgeterad kstn kostnaden för flexibel budget. Den använder transaktionsdata från kostnadsredovisningen operationer i Microsoft Dynamics 365 och visar totala kostnader för hela organisationen i en rapporteringsvaluta. Chefer kan filtrera data genom att kostnadsbärare för kostnadskontroll av organisationsenheter, även om organisationen kan ha flera juridiska personer. Eftersom de **Kostnadsredovisningsanalys** Power BI innehållet markeras avvikelser mellan de faktiska och budgeterade kostnader chefer kan meddelas om positiva och negativa trender för deras operativa enheter. Chefer kan gå ner kostnaden elementet hierarkier eller enskilda kostnadselement att få detaljerad information om hur kostnadsavvikelser har inträffat och vidta effektiva åtgärder. Den **Kostnadsredovisningsanalys** Power BI innehåll ska analysera kostnad revisorer hur kostnadsflödet går via en kostnadsbärare för hela organisationen. Mer information om kostnadsredovisning finns [hemsida kostnadsredovisning](/dynamics365/operations/financials/cost-accounting/cost-accounting-home-page.md). Genom att definiera åtkomst på resursnivå i kostnadsredovisningen, och att man kombinerar den med säkerhet på radnivå i Power BI, beviljar du alla objektägare kostnad åtkomst till den **Kostnadsredovisningsanalys** Power BI-innehåll. Alla data i de visuella effekterna sedan filtreras baserat på åtkomstnivån som kontrolleras i kostnadsredovisning. Mer information om säkerhet åtkomst och säkerhet på användarnivå Se [ange säkerhetsinställningar för kostnadsredovisning innehåll för Power BI](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Power BI-innehåll
Du kan hitta den **Kostnadsredovisningsanalys** Power BI innehållet i biblioteket delade resurser i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållet och anslutas för operationer i Dynamics 365 finns [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md). **Anmärkning:** KB4011327 ** ** är en förutsättning för den **Kostnadsredovisningsanalys** Power BI-innehåll.  När du loggar in till Lifecycle Services kan komma åt den här KB: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehåll
Innehållet omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualized som, brickor, t.ex. Följande tabell ger en översikt över de visuella effekterna i den **Kostnadsredovisningsanalys** Power BI-innehåll.

| Rapportsida                      | Diagram                                                                                                                         | Panel                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Kostnadskontroll efter räkenskapsperiod    | Den verkliga kostnaden och budgeterad kostnad av kostnaden elementet hierarkinivå                                                                   | Faktisk kostnad kontra budgeterad kostnad                    |
|                                  | Avvikelse från budget enligt hierarkinivå kostnad element                                                                               | Kontra faktisk kostnad tariff kostnadstabell för Budget          |
|                                  | 10 högsta avvikelse från Budget i procent av kostnaden element                                                                          | Omfattningen av faktiska storlek jämfört med Budget          |
| Kostnadskontroll per år till datum     | Den verkliga kostnaden och budgeterad kostnad per kalenderår Period                                                                           | Faktisk kostnad kontra budgeterad kostnad                    |
|                                  | Avvikelse från budget per kalenderår Period                                                                                       | Kontra faktisk kostnad tariff kostnadstabell för Budget          |
|                                  | 10 högsta avvikelse från Budget i procent av kostnaden element                                                                          | Omfattningen av faktiska storlek jämfört med Budget          |
| Kostnadstariff efter räkenskapsår         | Faktisk kostnadstariff genom kostnad-funktion                                                                                             | Kontra faktisk kostnad tariff kostnadstabell för Budget          |
|                                  | Faktisk kostnadstariff, Budget Kostnadsavvikelse hastighet, procent och Budget kostnadstariff som kostnaden elementet hierarkinivå-budgeterad kostnad | Omfattningen av faktiska storlek jämfört med Budget          |
|                                  | Avvikelse från budget enligt hierarkinivå kostnad element                                                                               |                                               |
|                                  | 10 högsta avvikelse från Budget i procent av kostnaden element                                                                          |                                               |
| Flexibel budget per räkenskapsperiod | Faktisk kostnad, budgeterad kostnad och flexibel Budgetkostnad som kostnad elementet hierarkinivå                                             | Omfattningen av faktiska storlek jämfört med Budget          |
|                                  | Avvikelse från budget och flexibel budget varians efter kostnad elementet hierarkinivå                                                  | Faktisk kostnad kontra flexibla budgeterad kstn           |
|                                  | Faktisk kostnad, budgeterad kostnad och flexibla kostnader för kostnad beteende och elementet hierarkinivå                                  | Faktisk hastighet jämfört med flexibel budget kostnad kostnadstariff |
| Kostnadsredovisning per räkenskapsperiod  | Faktisk kostnad efter kostnad hierarkinivå elementet och dimensionsmedlemsnamn objekt                                             |                                               |
|                                  | Faktisk kostnad efter kostnad objektet dimensionsmedlemsnamn och kostnaden elementet dimensionsmedlemsnamn                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer som används för att fylla rapportsidorna i den **Kostnadsredovisningsanalys** Power BI-innehåll. Informationen visas som sammansatta mått som mellanlagras i arkivet entitet som är en Microsoft SQL-databas som är optimerad för analys. Mer information finns i [översikt Power BI integration med entiteten arkivet](power-bi-integration-entity-store.md). Följande viktiga aggregerade mätningar används som bas för innehållet.

| Enhet                  | Nyckelmätpunkt aggregerade | Datakälla för Dynamics 365 för operationer | Fält     | beskrivning                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Transaktioner för kostnadsredovisning | SUM(Amount)               | CAMDATAAggregatedCostEntry                  | Belopp    | Beloppet i valutan redovisningen kostnadsredovisning |
| Statistikposter     | SUM(MAGNITUDE)            | CAMDATAAggregatedStatisctialEntry           | Storlek |                                               |

Följande tabell visar hur viktiga aggregerade mått som används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått                                       | Hur åtgärden ska beräknas.                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Faktisk kostnad                                   | BERÄKNA ('transaktioner för kostnadsredovisning'\[åtgärd\], "Transaktionen versioner"\[ISSOURCEVERSIONBUDGET\_värdet\] = 0)            |
| Budgeterad kostnad                                   | BERÄKNA ('transaktioner för kostnadsredovisning'\[åtgärd\], "Transaktionen versioner"\[ISSOURCEVERSIONBUDGET\_värdet\] = 1)            |
| Avvikelse från budget-kostnad                          | \[Budgeterad kostnad\] - \[verklig kostnad\]                                                                                      |
| Avvikelseprocent budget                    | IF (\[budgeterad kstn\] = 0, blank(), \[data\] / \[budgeterad kstn\])                                                |
| Verklig storlek                              | BERÄKNA ('Statistiska transaktioner'\[FullMagnitude\], "Transaktionen versioner"\[ISSOURCEVERSIONBUDGET\_värdet\] = 0)          |
| Omfattningen av budget                              | BERÄKNA (\[FullMagnitude\], "Transaktionen versioner"\[ISSOURCEVERSIONBUDGET\_värdet\] = 1)                               |
| Statistiska data                   | \[Omfattningen av budgeten\] - \[faktiska storlek\]                                                                            |
| Avvikelseprocent statistiska budget        | Om (\[Budget storleken\] = 0, blank(), \[statistiska data\] / \[Budget storleken\])                          |
| Faktisk kostnadstariff                              | IF (\[faktiska storlek\] = 0, BLANK(), \[verklig kostnad\] / \[faktiska storlek\])                                          |
| Budgetkostnadstariff                              | IF (\[Budget storleken\] = 0, BLANK(), \[budgeterad kstn\] / \[Budget storleken\])                                          |
| Budgeterad tariff avvikelse                     | \[Kostnad för budget\] - \[Faktisk kostnadstariff\]                                                                            |
| Budgeterad avvikelse i procent          | IF (\[budgeterad kstn\] = 0 returneras blank(), \[Budget Kostnadsavvikelse hastighet\] / \[Budget kostnadstariffen\])                                 |
| Budgeterad fast kostnad                             | BERÄKNA (\[budgeterad kstn\]"Kostnadsredovisning poster",\[COSTBEHAVIOR\] = 1)                                              |
| Variabel budgeterad kstn                          | BERÄKNA (\[budgeterad kstn\]"Kostnadsredovisning poster",\[COSTBEHAVIOR\] = 2)                                              |
| Flexibel budget för fast kostnad                    | \[Budgeterad fast kostnad\]                                                                                                  |
| Flexibel budget variabel kostnad                 | IF (\[Budget storleken\] = 0, BLANK(), (\[variabel budgeterad kstn\] / \[Budget storleken\]) \*\[verklig storlek\])       |
| Kostnaden för flexibel budget                          | \[Fast kostnad för flexibel budget\] + \[variabel flexibla budgeterad kstn\]                                                     |
| Avvikelse för flexibel budget                      | \[Flexibla budgeterad kstn\] - \[verklig kostnad\]                                                                             |
| Avvikelseprocent flexibel budget           | IF (\[flexibla budgeterad kstn\] = 0, BLANK(), \[avvikelse flexibel budget\] / \[flexibla budgeterad kstn\])                     |
| Flexibla budgetkostnader tariff                     | IF (\[verklig storlek\] = 0, BLANK(), \[flexibla budgeterad kstn\] / \[faktiska storlek\])                                 |
| Flexibla budgetkostnader tariff avvikelse            | \[Flexibel budget kostnadstariffen\] - \[Faktisk kostnadstariff\]                                                                   |
| Flexibel budget kostnad avvikelse i procent | IF (\[kostnadstariffen för flexibel budget\] = 0, BLANK(), \[flexibel budget Kostnadsavvikelse kurs\] / \[kostnadstariffen för flexibel budget\]) |

Skära totala måtten för att uppnå förbättrad säkerhetsadministration och ger en bättre förståelse för analytiska används följande viktiga dimensionerna som filter.

| Enhet                             | Exempel på attribut                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Huvudböcker för kostnadsredovisning            | Huvudbok för kostnadsredovisning                                                                                               |
| Kostnadsstyrenheter                 | Namn på kostnadsstyrenhet                                                                                               |
| Dimensioner för kostnadselement            | Kostnad element dimension namn, kostnad elementet dimensionsmedlemsnamn, kostnad elementbeskrivning dimension medlem          |
| Kostnadsobjektdimensioner             | Dimensionsnamnet kostnadsbärare, kostnad objektet dimensionsmedlemsnamn kostnad objektbeskrivning dimension medlem              |
| Statistikdimensioner             | Statistiska dimensionsnamnet statistiska dimensionsmedlemsnamn, beskrivning av statistiska dimension medlem              |
| Dimensionshierarkier kostnadsbärare  | Kostnad objektnamn dimension hierarki, kostnadskontroll dimension hierarki objektnivån kostnad objektet dimensionshierarkiträdet    |
| Dimensionshierarkier kostnad element | Kostnad elementnamn dimension hierarki, kostnadskontroll elementet dimension hierarkinivån, kostnad elementet dimensionshierarkiträdet |
| Statistiska dimensionshierarkier  | Statistiska hierarki dimensionsnamnet, statistiska dimension hierarkinivå hierarkiträdet statistiska dimension    |
| Transaktionsversioner               | Versionsnamn                                                                                                         |
| Räkenskapskalendrar                   | Kalender, kalender, beskrivning                                                                                       |
| Räkenskapsår                       | Kalenderår                                                                                                        |
| Räkenskapsperioder                     | Kalenderår för perioden                                                                                                 |

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)
-   [Ställa in säkerhet för kostnadsredovisning innehåll för Power BI](setup-security-cost-accounting-content-pack.md)


