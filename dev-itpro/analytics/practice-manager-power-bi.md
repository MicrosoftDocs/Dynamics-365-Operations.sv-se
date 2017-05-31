---
title: "Power BI-innehåll för praxischef"
description: "Det här avsnittet beskriver vad som ingår i innehållet för praxischef för Power BI. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Power BI-innehåll för praxischef

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver vad som ingår i Microsoft Power BI-innehållet för **Praxischef**. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **Praxischef** har skapats för praxischefer och projektledare. Det tillhandahåller viktiga mätvärden som är relaterade till de projekt som organisationen med. Instrumentpanelen ger en översikt över projekt och tillhörande kunder. Ett rapportnivåfilter kan användas för rapporter till specifika juridiska personer. Detta Power BI-innehåll hämtar data från projektredovisningens sammanlagda värden för Microsoft Dynamics 365 for Operations.

Power BI-innehållet för **Praxischef** innehåller fem rapportsidor: en översiktssida och fyra sidor som ger information om projektkostnader, intäkter, hantering av upparbetat värde samt timmätvärden som vrids och vänds över flera olika dimensioner.

Alla belopp i innehållet visas i systemvalutan. Du kan ange systemvalutan på sidan **Systemparametrar**.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll

Du kan hitta Power BI-innehållet **Praxischef** i biblioteket för gemensamma tillgångar i Microsoft Dynamics Lifecycle Services (LCS). Mer information om hur du hämtar innehållspaketet och kopplar det till dina Microsoft Dynamics 365 for Operations-data, se [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md).

Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Praxischef**.

| Rapportsida                                          | Mätvärden               |
|------------------------------------------------------|-----------------------------------------------|
| Instrumentpanel  | Skapade projekt<br>Uppskattade projekt<br>Pågående projekt<br>Antal projekt efter stadium<br>Antal projekt efter stad<br>Faktiskt intäkt efter kund<br>Budget-bruttomarginal efter projekt<br>Översikt - Hantering av intjänat värde |
| Kostnad                                                 | Faktiskt kostnad jämförd med budgetkostnad efter månad<br>Faktiskt kostnad jämförd med budgetkostnad efter år<br>Faktisk kostnad jämförd med budgetkostnad efter kategori<br>Faktisk kostnad efter transaktionstyp       |
| Intäkt                                              | Faktiskt intäkt efter månad<br>Faktisk intäkt efter postnummer<br>Faktisk intäkt jämförd med budgetintäkt efter kategori<br>Faktiskt intäkt efter kundbransch        |
| EVM                                                  | Index för kostnad och schemaprestanda efter projekt                 |
| Timmar                                                | Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar kontra budgeterade timmar<br>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter projekt<br>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter resurs<br>Kvot för faktiska fakturerbara timmar efter projekt<br>Kvot för faktiska fakturerbara timmar efter resurs |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Du kan också använda funktionen Exportera underliggande data för att exportera underliggande data som summerats i en visualisering.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Dynamics 365 for Operations-data används för att fylla i rapportsidorna i Power-Bi-innehållet **Praxischef**. Informationen visas som sammansatta mått som mellanlagras i enhetsarkivet, som är en Microsoft SQL-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Nedanstående avsnitt beskriver de sammanlagda mått som används i respektive enhet.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Enhet: ProjectAccountingCube_ActualHourUtilization
**Datakälla**: ProjEmplTrans

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Summan av faktiska fakturerbara utnyttjade timmar |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Summan av faktiska omkostnader             |

### <a name="entity-projectaccountingcubeactuals"></a>Enhet: ProjectAccountingCube_Actuals
**Datakälla**: ProjTransPosting

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Summan av bokförda intäkter för alla transaktioner |   
| ActualCost   |                             Sum(ActualCost)           |    Summan av bokförda kostnader för alla transaktionstyper    |

### <a name="entity-projectaccountingcubecustomer"></a>Enhet: ProjectAccountingCube_Customer
**Datakälla**: CustTable

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Antal projekt        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Antal tillgängliga projekt    |


### <a name="entity-projectaccountingcubeforecasts"></a>Enhet: ProjectAccountingCube_Forecasts
**Datakälla**: ProjTransBudget

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Summan av prognosticerade kostnader för alla transaktionstyper     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    Summan av upplupen prognos/fakturerad intäkt         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Skillnaden mellan summan av den totala prognosticerade intäkten och summan av den totala prognoskostnaden

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Enhet: ProjectAccountingCube_ProjectPlanCostsView
**Datakällsnamn**: Projekt

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Total självkostnad i uppskattningar för alla projekttransaktionstyper med planerade uppgifter |

### <a name="entity-projectaccountingcubeprojects"></a>Enhet: ProjectAccountingCube_Projects
**Datakällsnamn**: Projekt

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Index för kostnadsresultat  |ProjectAccountingCube_Projects [upparbetat värde] / ProjectAccountingCube_Projects [faktisk totalkostnad för slutförda uppgifter] |     Beräkningen av det totala upparbetade värdet delat med total faktisk kostnad|
|  Index för tidsplansresultat |ProjectAccountingCube_Projects [upparbetat värde] / ProjectAccountingCube_Projects [planerad totalkostnad för slutförda uppgifter]|Beräkningen av det totala upparbetade värdet delat med total planerad kostnad |
|Procent av slutfört arbete |Procent av slutfört arbete = ProjectAccountingCube_Project[faktisk totalkostnad för slutförda uppgifter] / (ProjectAccountingCube_Projects [faktisk totalkostnad för slutförda uppgifter] + ProjectAccountingCube_Projects [total planerad kostnad för projekt] - ProjectAccountingCube_Projects [total planerad kostnad för slutförda uppgifter])|Total procentandel färdigt arbete baserat på faktisk totalkostnad för slutförd uppgift och planerad projektkostnad|
|Projektkvot för faktiska fakturerbara timmar|ProjectAccountingCube_Projects [totala faktiska fakturerbara utnyttjade projekttimmar] / (ProjectAccountingCube_Projects [totala faktiska fakturerbara utnyttjade projekttimmar] + ProjectAccountingCube_Projects [projektets totala faktiska fakturerbara ej fakturerbara timmar]|Faktiska fakturerbara timmar totalt utifrån använda + ej fakturerbara|
|Intjänat värde|ProjectAccountingCube_Projects [total planerad projektkostnad] * ProjectAccountingCube_Projects [procentandel av slutfört arbete]|Planerad totalkostnad multipliceras med procentandelen slutfört arbete|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Enhet: ProjectAccountingCube_TotalEstimatedCosts 
**Datakälla**: ProjTable

| Sammanlagda huvudmått                | Fält                                | beskrivning                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Total självkostnad i uppskattningar för alla projekttransaktionstyper med slutförda uppgifter|

## <a name="additional-resources"></a>Ytterligare resurser

Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

- [Datatabeller](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Konfigurera Power BI-integrering för arbetsytor](configure-power-bi-integration.md)

