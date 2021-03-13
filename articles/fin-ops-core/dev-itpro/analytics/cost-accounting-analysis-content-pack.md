---
title: Power BI-innehåll för kostnadsredovisningsanalys
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kostnadsredovisning.
author: AndersGirke
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c9a4741c1b09b8e68a9fe95d6f4effa328615d5
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093396"
---
# <a name="cost-accounting-analysis-power-bi-content"></a>Power BI-innehåll för kostnadsredovisningsanalys

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Power BI-innehållet för **kostnadsredovisning**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet **Kostnadsredovisningsanalys** är avsett för kostnadskontrollanter eller annan som med ansvar för att utföra kostnadskontroll inom en organisation. Det innehåller viktiga mätvärden såsom kostnad, omfattning och kostnadstariff efter verklig kostnad, budgeterad kostnad och kostnad för flexibel budget. Det använder transaktionsdata från modulen **kostnadsredovisning** och visar totala kostnader för hela organisationen i en rapporteringsvaluta. Chefer kan filtrera data efter kostnadsobjekt för kostnadskontroll av organisationsenheter, även om organisationen kan ha flera juridiska personer.

Eftersom innehållet **Kostnadsredovisningsanalys** markerar avvikelser mellan faktiska och budgeterade kostnader, kan chefer meddelas om positiva och negativa trender för deras operativa enheter. Chefer kan bläddra ner till kostnadselementhierarkierna eller enskilda kostnadselement. På så sätt kan kan chefer få detaljerad information om hur kostnadsavvikelser har inträffat och vidta effektiva åtgärder.

Innehållet **Kostnadsredovisningsanalys** låter kostnadsredovisare analysera kostnadsflödet genom kostnadsobjekt inom hela organisationen.

Mer information om kostnadsredovisning finns [Startsida för kostnadsredovisning](../../../finance/cost-accounting/cost-accounting-home-page.md).

Genom att definiera säkerhetsnivån för åtkomst inom kostnadsredovisningen och kombinera den med säkerheten på radnivå i Power BI, beviljar du alla ägare av kostnadsobjekt åtkomst till Power BI-innehållet för **Kostnadsredovisningsanalys**. Alla data i de visuella effekterna filtreras sedan baserat på den åtkomstnivå som kontrolleras i kostnadsredovisningen. Mer information om säkerhetsnivån för åtkomst och säkerhet på radnivå, se [Ange säkerhetsinställningar för kostnadsredovisningsanalyser i Power BI-innehåll](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
Du kan hitta Power BI-innehållet **Kostnadsredovisningsanalys** i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).

Hämta innehållet **Kostnadsredovisningsanalys** innehåll som avser versionen av Microsoft Dynamics 365 som du använder.

> [!NOTE]
> KB 4011327 är ett krav för detta Power BI-innehåll När du loggar in på LCS når KB på <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet
Innehållet omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualiseras som diagram, brickor och tabeller. Följande register ger en översikt över de visuella effekterna i Power BI-innehållet **Kostnadsredovisningsanalys**.

| Rapportsida                      | Diagram                                                                                                                         | Panel                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Kostnadskontroll efter räkenskapsperiod    | Faktisk kostnad och budgeterad kostnad efter hierarkinivå för kostnadselement                                                                   | Faktisk kostnad jämförd med budgeterad kostnad                    |
|                                  | Budgetavvikelse efter hierarkinivå för kostnadselement                                                                               | Faktisk kostnadstariff jämförd med budgettariff          |
|                                  | De 10 största budgetavvikelserna i procent efter kostnadselement                                                                          | Faktiskt storlek jämfört med budgetstorlek          |
| Kostnadskontroll per år fram tills nu     | Faktisk kostnad och budgeterad kostnad efter kalenderårsperiod                                                                           | Faktisk kostnad jämförd med budgeterad kostnad                    |
|                                  | Budgetavvikelse efter kalenderårsperiod                                                                                       | Faktisk kostnadstariff jämförd med budgettariff          |
|                                  | De 10 största budgetavvikelserna i procent efter kostnadselement                                                                          | Faktiskt storlek jämfört med budgetstorlek          |
| Kostnadstariff efter räkenskapsår         | Faktisk kostnadstariff efter kostnadsbeteende                                                                                             | Faktisk kostnadstariff jämförd med budgettariff          |
|                                  | Faktisk kostnadstariff, tariffavvikelse för budgetkostnad, tariffprocent för budgetkostnad samt budgetkostnadstariff efter hierarkinivå | Faktiskt storlek jämfört med budgetstorlek          |
|                                  | Budgetavvikelse efter hierarkinivå för kostnadselement                                                                               |                                               |
|                                  | De 10 största budgetavvikelserna i procent efter kostnadselement                                                                          |                                               |
| Flexibel budget efter räkenskapsperiod | Faktisk kostnad, budgeterad kostnad och flexibel budgetkostnad efter hierarkinivå för kostnadselement                                             | Faktiskt storlek jämfört med budgetstorlek          |
|                                  | Budgetavvikelse och flexibel budgetavvikelse efter hierarkinivå för kostnadselement                                                  | Faktisk kostnad jämförd med flexible budgetkostnad           |
|                                  | Faktisk kostnad, budgeterad kostnad och flexibel budgetkostnad efter kostnadsbeteende och hierarkinivå för kostnadselement                                  | Faktiskt kostnadstariff jämförd med tariff för flexibel budgetkostnad |
| Kostnadsutdrag efter räkenskapsperiod  | Faktisk kostnad efter hierarkinivå för kostnadselement samt medlemsnamn för kostnadsobjektdimension                                             |                                               |
|                                  | Faktisk kostnad efter medlemsnamn för kostnadsobjektdimension samt medlemsnamn för kostnadselemetdimension                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Följande data används för att fylla i rapportsidorna Power BI-innehållet **Kostnadsredovisningsanalys**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Följande sammanlagda huvudmått används till grund för innehållet:

| Enhet                  | Sammanlagda huvudmått | Datakälla för Dynamics 365      | Fält     | beskrivning                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| Poster för kostnadsredovisning | SUMMA(Belopp)               | CAMDATAAggregatedCostEntry        | Belopp    | Beloppet i redovisningsvalutan för kostnadsredovisning. |
| Statistikposter     | SUMMA(storlek)            | CAMDATAAggregatedStatisctialEntry | Storlek |                                                    |

Följande tabell visar hur viktiga sammanlagda mått används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått                                       | Hur åtgärden beräknas                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Faktisk kostnad                                   | BERÄKNA("Poster för kostnadsredovisning"\[Åtgärd\], "Transaktionsversioner"\[ISSOURCEVERSIONBUDGET\_VÄRDE\] = 0)            |
| Budgeterad kostnad                                   | BERÄKNA("Poster för kostnadsredovisning"\[Åtgärd\], "Transaktionsversioner"\[ISSOURCEVERSIONBUDGET\_VÄRDE\] = 1)            |
| Avvikelse i budgetkostnad                          | \[Budgeterad kostnad\] - \[Faktisk kostnad\]                                                                                      |
| Budgetavvikelseprocent                    | OM(\[Budgeterad kostnad\] = 0, blank(), \[Budgetavvikelse\] / \[Budgeterad kostnad\])                                                |
| Verklig storlek                              | BERÄKNA("Statistiska poster"\[FullMagnitude\], "Transaktionsversioner"\[ISSOURCEVERSIONBUDGET\_VÄRDE\] = 0)          |
| Budgetomfattning                              | BERÄKNA(\[FullMagnitude\], "Transaktionsversioner"\[ISSOURCEVERSIONBUDGET\_VÄRDE\] = 1)                               |
| Statistisk budgetavvikelse                   | \[Budgetstorlek\] - \[Faktisk storlek\]                                                                            |
| Statistisk budgetavvikelseprocent        | OM(\[Budgetstorlek\] = 0, blank(), \[Statistisk budgetavvikelse\] / \[Budgetstorlek\])                          |
| Faktisk kostnadstariff                              | OM(\[Faktisk storlek\] = 0, BLANK(), \[Faktisk kostnad\] / \[Faktisk storlek\])                                          |
| Budgetkostnadstariff                              | OM(\[Budgetstorlek\] = 0, BLANK(), \[Budgetkostnad\] / \[Budgetstorlek\])                                          |
| Avvikelse för budgetkostnadstariff                     | \[Budgetkostnadstariff\] - \[Faktisk kostnadstariff\]                                                                            |
| Avvikelseprocentsats för budgetkostnadstariff          | OM(\[Budgetkostnad\] = 0, blank(), \[Tariffavvikelse för budgetkostnad\] / \[Budgetkostnadstariff\])                                 |
| Fast budgetkostnad                             | BERÄKNA(\[Budgetkostnad\]"Kostnadsredovisningsposter",\[COSTBEHAVIOR\] = 1)                                              |
| Rörlig budgetkostnad                          | BERÄKNA(\[Budgetkostnad\]"Kostnadsredovisningsposter",\[COSTBEHAVIOR\] = 2)                                              |
| Fast, flexibel budgetkostnad                    | \[Fast budgetkostnad\]                                                                                                  |
| Rörlig, flexibel budgetkostnad                 | OM(\[Budgetstorlek\] = 0, BLANK(), (\[Variabel budgeterad kostnad\] / \[Budgetstorlek\]) \* \[Faktisk storlek\])       |
| Flexibel budgetkostnad                          | \[Fast kostnad för flexibel budget\] + \[Variabel flexibel budgetkostnad\]                                                     |
| Flexibel budgetavvikelse                      | \[Flexibel budgetkostnad\] - \[Faktisk kostnad\]                                                                             |
| Flexibel budgetavvikelseprocent           | OM(\[Flexibel budgetkostnad\] = 0, BLANK(), \[Flexibel budgetavvikelse\] / \[Flexibel budgetkostnad\])                     |
| Flexibel budgetkostnadstariff                     | OM(\[Faktisk storlek\] = 0, BLANK(), \[Flexibel budgetkostnad\] / \[Faktisk storlek\])                                 |
| Flexibel tariffavvikelse för budgetkostnad            | \[Flexibel budgetkostnadstariff\] - \[Faktisk kostnadstariff\]                                                                   |
| Flexibel avvikelseprocent för budgetkostnadstariff | OM(\[Flexibel budgetkostnadstariff\] = 0, BLANK(), \[Flexibel tariffavvikelse för budgetkostnad\] / \[Flexibel tariff för budgetkostnad\]) |

Följande huvuddimensioner används som filter för att dela upp de sammanlagda måtten i syfte att uppnå en förbättrad nivå och ge djupare analysinsikter.

| Enhet                             | Exempel på attribut                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Huvudböcker för kostnadsredovisning            | Huvudbok för kostnadsredovisning                                                                                               |
| Kostnadsstyrenheter                 | Namn på kostnadsstyrenhet                                                                                               |
| Dimensioner för kostnadselement            | Måttnamn för kostnadselement, Medlemsnamn för kostnadselementdimension, Medlemsbeskrivning för kostnadselementdimension          |
| Kostnadsobjektdimensioner             | Måttnamn för kostnadsobjekt, Medlemsnamn för kostnadsobjektsdimension, Medlemsbeskrivning för kostnadsobjektdimension              |
| Statistikdimensioner             | Statistiskt dimensionsnamn, Namn för statistisk dimensionsmedlem, Beskrivning av statistisk dimensionsmedlem              |
| Dimensionshierarkier för kostnadsobjekt  | Hierarkinamn för kostnadsobjektdimension, Hierarkinivå för kostnadsobjektdimension, Hierarkiträd för kostnadsobjektdimension    |
| Dimensionshierarkier för kostnadselement | Hierarkinamn för kostnadselementdimension, Hierarkinivå för kostnadselementdimension, Hierarkiträd för kostnadselementdimension |
| Statistiska dimensionshierarkier  | Hierarkinamn för statistisk dimension, Hierarkinivå för statistisk dimension, Hierarkiträd för statistisk dimension    |
| Transaktionsversioner               | Versionsnamn                                                                                                         |
| Räkenskapskalendrar                   | Kalender, kalenderbeskrivning                                                                                       |
| Räkenskapsår                       | Kalenderår                                                                                                        |
| Räkenskapsperioder                     | Kalenderårsperioder                                                                                                 |
