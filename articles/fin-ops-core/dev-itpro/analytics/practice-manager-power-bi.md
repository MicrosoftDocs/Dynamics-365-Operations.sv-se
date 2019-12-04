---
title: Praxischef Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i innehållet för praxischef för Power BI. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet.
author: KimANelson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a6e6b8d6243c1f7c5831baaee91baf38d51e0c26
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770007"
---
# <a name="practice-manager-power-bi-content"></a>Praxischef Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i **praxischef** Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

**Praxischef** Power BI-innehåll har skapats för praxischefer och projektledare. Det tillhandahåller viktiga mätvärden som är relaterade till de projekt som organisationen med. Instrumentpanelen ger en översikt över projekt och tillhörande kunder. Ett rapportnivåfilter kan användas för rapporter till specifika juridiska personer. Detta Power BI-innehåll hämtar data från sammanlagda mått för projektredovisning.

Innehållet för **Praxischef** Power BI innehåller fem rapportsidor: en översiktssida och fyra sidor som ger information om projektkostnader, intäkter, hantering av upparbetat värde samt timmätvärden som är fördelade över flera olika dimensioner.

Alla belopp i innehållet visas i systemvalutan. Du kan ange systemvalutan på sidan **Systemparametrar**.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll

Power BI-innehållet **Praxischef** visas i arbetsytan **Projekthantering**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Praxischef**.

| Rapportsida       | Mätvärden |
|-------------------|---------|
| Projektöversikt | <ul><li>Skapade projekt</li><li>Uppskattade projekt</li><li>Pågående projekt</li><li>Faktiskt intäkt efter kund</li><li>Budget-bruttomarginal efter projekt</li><li>Översikt - Hantering av intjänat värde</li></ul> |
| Kostnad              | <ul><li>Faktiskt kostnad jämförd med budgetkostnad efter månad</li><li>Faktiskt kostnad jämförd med budgetkostnad efter år</li><li>Faktisk kostnad jämförd med budgetkostnad efter kategori</li><li>Faktisk kostnad efter transaktionstyp</li></ul> |
| Intäkt           | <ul><li>Faktiskt intäkt efter månad</li><li>Faktisk intäkt efter postnummer</li><li>Faktisk intäkt jämförd med budgetintäkt efter kategori</li><li>Faktiskt intäkt efter kundbransch</li></ul> |
| EVM               | Index för kostnad och schemaprestanda efter projekt |
| Timmar             | <ul><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar kontra budgeterade timmar</li><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter projekt</li><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter resurs</li><li>Kvot för faktiska fakturerbara timmar efter projekt</li><li>Kvot för faktiska fakturerbara timmar efter resurs</li></ul> |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Du kan också använda funktionen Exportera underliggande data för att exportera underliggande data som summerats i en visualisering.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Praxischef**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Nedanstående avsnitt beskriver de sammanlagda mått som används i respektive enhet.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Enhet: ProjectAccountingCube\_ActualHourUtilization
**Datakälla:** ProjEmplTrans

| Sammanlagda huvudmått      | Fält                              | beskrivning |
|--------------------------------|------------------------------------|-------------|
| Faktiska fakturerbara utnyttjade timmar | Sum(ActualUtilizationBillableRate) | Summan av faktiska fakturerbara utnyttjade timmar. |
| Faktiska fakturerbara ej fakturerbara timmar   | Sum(ActualBurdenBillableRate)      | Summan av de faktiska omkostnaderna. |

### <a name="entity-projectaccountingcube_actuals"></a>Enhet: ProjectAccountingCube\_Actuals
**Datakälla:** ProjTransPosting

| Sammanlagda huvudmått | Fält              | beskrivning |
|---------------------------|--------------------|-------------|
| Faktisk intäkt            | Sum(ActualRevenue) | Summan av bokförda intäkter för alla transaktioner. |
| Faktisk kostnad               | Sum(ActualCost)    | Summan av bokförda kostnader för alla transaktionstyper. |

### <a name="entity-projectaccountingcube_customer"></a>Enhet: ProjectAccountingCube\_Customer
**Datakälla:** CustTable

| Sammanlagda huvudmått | Fält                                             | beskrivning |
|---------------------------|---------------------------------------------------|-------------|
| Antal projekt        | COUNTA(ProjectAccountingCube\_Projects\[PROJEKT\]) | Antal tillgängliga projekt. |

### <a name="entity-projectaccountingcube_forecasts"></a>Enhet: ProjectAccountingCube\_Forecasts
**Datakälla:** ProjTransBudget

| Sammanlagda huvudmått | Fält                  | beskrivning |
|---------------------------|------------------------|-------------|
| Budgeterad kostnad               | Sum(BudgetCost)        | Summan av prognosticerade kostnader för alla transaktionstyper. |
| Budgeterad intäkt            | Sum(BudgetRevenue)     | Summan av upplupen prognos/fakturerad intäkt. |
| Budgeterad bruttomarginal       | Sum(BudgetGrossMargin) | Skillnaden mellan summan av den totala prognosticerade intäkten och summan av den totala prognoskostnaden. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Enhet: ProjectAccountingCube\_ProjectPlanCostsView
**Datakälla:** Projekt

| Sammanlagda huvudmått | Fält                    | beskrivning |
|---------------------------|--------------------------|-------------|
| Planerad kostnad              | Sum(SumOfTotalCostPrice) | Total självkostnad i uppskattningar för alla projekttransaktionstyper med planerade uppgifter. |

### <a name="entity-projectaccountingcube_projects"></a>Enhet: ProjectAccountingCube\_Projects
**Datakälla:** Projekt

| Sammanlagda huvudmått    | Fält | beskrivning |
|------------------------------|-------|-------------|
| Index för kostnadsresultat       | ProjectAccountingCube\_Projects\[Intjänat värde\] ÷ ProjectAccountingCube\_Projects\[Faktisk totalkostnad för slutförda uppgifter\] | Beräkningen av det totala upparbetade värdet delat med den totala faktiska kostnaden. |
| Index för tidsplansresultat   | ProjectAccountingCube\_Projects\[Intjänat värde\] ÷ ProjectAccountingCube\_Projects\[Planerad totalkostnad för slutförda uppgifter\] | Beräkningen av det totala upparbetade värdet delat med den totala planerade kostnaden. |
| Procent av slutfört arbete | Procent av slutfört arbete = ProjectAccountingCube\_Projects\[Faktisk totalkostnad för slutförda uppgifter\] ÷ (ProjectAccountingCube\_Projects\[Faktisk totalkostnad för slutförda uppgifter\] + ProjectAccountingCube\_Projects\[Total planerad kostnad för projekt\] – ProjectAccountingCube\_Projects\[Total planerad kostnad för slutförda uppgifter\]) | Total procentandel färdigt arbete baserat på faktisk totalkostnad för slutförda uppgifter och den planerade projektkostnaden. |
| Kvot för faktiska fakturerbara timmar  | ProjectAccountingCube\_Projects\[Totala faktiska fakturerbara utnyttjade projekttimmar\] ÷ (ProjectAccountingCube\_Projects\[Totala faktiska fakturerbara utnyttjade projekttimmar\] + ProjectAccountingCube\_Projects\[Projektets totala faktiska fakturerbara ej fakturerbara timmar\]) | Totala faktiska fakturerbara timmar, baserat på utnyttjad timmar och ej fakturerbara timmar. |
| Intjänat värde                 | ProjectAccountingCube\_Projects\[total planerad projektkostnad\] × ProjectAccountingCube\_Projects\[procentandel av slutfört arbete\] | Planerad totalkostnad multiplicerad med procentandelen slutfört arbete. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Enhet: ProjectAccountingCube\_TotalEstimatedCosts 
**Datakälla:** ProjTable

| Sammanlagda huvudmått       | Fält               | beskrivning |
|---------------------------------|---------------------|-------------|
| Planerad kostnad för slutförd aktivitet | Sum(TotalCostPrice) | Uppskattad total självkostnad för alla projekttransaktionstyper som har slutförda uppgifter. |
