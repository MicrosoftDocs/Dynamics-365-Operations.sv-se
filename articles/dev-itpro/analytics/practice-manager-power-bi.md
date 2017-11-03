---
title: "Power BI-innehåll för praxischef"
description: "Det här avsnittet beskriver vad som ingår i innehållet för praxischef för Power BI. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållet."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99e5b5087cc72c01ff3e92d0b2b3a6279385eb19
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="practice-manager-power-bi-content"></a>Power BI-innehåll för praxischef

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Microsoft Power BI-innehållet för **Praxischef**. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **Praxischef** har skapats för praxischefer och projektledare. Det tillhandahåller viktiga mätvärden som är relaterade till de projekt som organisationen med. Instrumentpanelen ger en översikt över projekt och tillhörande kunder. Ett rapportnivåfilter kan användas för rapporter till specifika juridiska personer. Detta Power BI-innehåll hämtar data från sammanlagda mått för projektredovisning.

Power BI-innehållet för **Praxischef** innehåller fem rapportsidor: en översiktssida och fyra sidor som ger information om projektkostnader, intäkter, hantering av upparbetat värde samt timmätvärden som är fördelade över flera olika dimensioner.

Alla belopp i innehållet visas i systemvalutan. Du kan ange systemvalutan på sidan **Systemparametrar**.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) visas Power BI-innehållet **Praxischef** i arbetsytan **Projekthantering**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **Praxischef**.

| Rapportsida       | Mätvärden |
|-------------------|---------|
| Projektöversikt | <ul><li>Skapade projekt</li><li>Uppskattade projekt</li><li>Pågående projekt</li><li>Antal projekt efter stadium</li><li>Antal projekt efter stad</li><li>Faktiskt intäkt efter kund</li><li>Budget-bruttomarginal efter projekt</li><li>Översikt - Hantering av intjänat värde</li></ul> |
| Kostnad              | <ul><li>Faktiskt kostnad jämförd med budgetkostnad efter månad</li><li>Faktiskt kostnad jämförd med budgetkostnad efter år</li><li>Faktisk kostnad jämförd med budgetkostnad efter kategori</li><li>Faktisk kostnad efter transaktionstyp</li></ul> |
| Intäkt           | <ul><li>Faktiskt intäkt efter månad</li><li>Faktisk intäkt efter postnummer</li><li>Faktisk intäkt jämförd med budgetintäkt efter kategori</li><li>Faktiskt intäkt efter kundbransch</li></ul> |
| EVM               | Index för kostnad och schemaprestanda efter projekt |
| Timmar             | <ul><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar kontra budgeterade timmar</li><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter projekt</li><li>Faktiska fakturerbara utnyttjade timmar kontra faktiska fakturerbara ej fakturerbara timmar efter resurs</li><li>Kvot för faktiska fakturerbara timmar efter projekt</li><li>Kvot för faktiska fakturerbara timmar efter resurs</li></ul> |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Du kan också använda funktionen Exportera underliggande data för att exportera underliggande data som summerats i en visualisering.

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter eller modeller och sedan publicera dem till din Power BI.com-innehavare för analys. 

Du hittar Power BI-innehåll för **Praxischef** i biblioteket Gemensamma tillgångar i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

Hämta innehållet för **Praxischef** som gäller för den version av Dynamics 365 som du använder.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapportsidorna i Power-Bi-innehållet **Praxischef**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Nedanstående avsnitt beskriver de sammanlagda mått som används i respektive enhet.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Enhet: ProjectAccountingCube_ActualHourUtilization
**Datakälla:** ProjEmplTrans

| Sammanlagda huvudmått      | Fält                              | beskrivning | 
|--------------------------------|------------------------------------|-------------|
| Faktiska fakturerbara utnyttjade timmar | Sum(ActualUtilizationBillableRate) | Summan av faktiska fakturerbara utnyttjade timmar. |
| Faktiska fakturerbara ej fakturerbara timmar   | Sum(ActualBurdenBillableRate)      | Summan av de faktiska omkostnaderna. |

### <a name="entity-projectaccountingcubeactuals"></a>Enhet: ProjectAccountingCube_Actuals
**Datakälla:** ProjTransPosting

| Sammanlagda huvudmått | Fält              | beskrivning | 
|---------------------------|--------------------|-------------|
| Faktisk intäkt            | Sum(ActualRevenue) | Summan av bokförda intäkter för alla transaktioner. |   
| Faktisk kostnad               | Sum(ActualCost)    | Summan av bokförda kostnader för alla transaktionstyper. |

### <a name="entity-projectaccountingcubecustomer"></a>Enhet: ProjectAccountingCube_Customer
**Datakälla:** CustTable

| Sammanlagda huvudmått | Fält                                            | beskrivning | 
|---------------------------|--------------------------------------------------|-------------|
| Antal projekt        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | Antal tillgängliga projekt. |


### <a name="entity-projectaccountingcubeforecasts"></a>Enhet: ProjectAccountingCube_Forecasts
**Datakälla:** ProjTransBudget

| Sammanlagda huvudmått | Fält                  | beskrivning | 
|---------------------------|------------------------|-------------|
| Budgeterad kostnad               | Sum(BudgetCost)        | Summan av prognosticerade kostnader för alla transaktionstyper. |
| Budgeterad intäkt            | Sum(BudgetRevenue)     | Summan av upplupen prognos/fakturerad intäkt.  |
| Budgeterad bruttomarginal       | Sum(BudgetGrossMargin) | Skillnaden mellan summan av den totala prognosticerade intäkten och summan av den totala prognoskostnaden. |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Enhet: ProjectAccountingCube_ProjectPlanCostsView
**Datakälla:** Projekt

| Sammanlagda huvudmått | Fält                    | beskrivning | 
|---------------------------|--------------------------|-------------|
| Planerad kostnad              | Sum(SumOfTotalCostPrice) | Total självkostnad i uppskattningar för alla projekttransaktionstyper med planerade uppgifter. |

### <a name="entity-projectaccountingcubeprojects"></a>Enhet: ProjectAccountingCube_Projects
**Datakälla:** Projekt

| Sammanlagda huvudmått    | Fält | beskrivning | 
|------------------------------|-------|-------------|
| Index för kostnadsresultat       | ProjectAccountingCube_Projects [upparbetat värde] / ProjectAccountingCube_Projects [faktisk totalkostnad för slutförda uppgifter] | Beräkningen av det totala upparbetade värdet delat med den totala faktiska kostnaden. |
| Index för tidsplansresultat   | ProjectAccountingCube_Projects [upparbetat värde] / ProjectAccountingCube_Projects [planerad totalkostnad för slutförda uppgifter] | Beräkningen av det totala upparbetade värdet delat med den totala planerade kostnaden. |
| Procent av slutfört arbete | Procent av slutfört arbete = ProjectAccountingCube_Project[faktisk totalkostnad för slutförda uppgifter] / (ProjectAccountingCube_Projects [faktisk totalkostnad för slutförda uppgifter] + ProjectAccountingCube_Projects [total planerad kostnad för projekt] - ProjectAccountingCube_Projects [total planerad kostnad för slutförda uppgifter]) | Total procentandel färdigt arbete baserat på faktisk totalkostnad för slutförda uppgifter och den planerade projektkostnaden. |
| Kvot för faktiska fakturerbara timmar  | ProjectAccountingCube_Projects [totala faktiska fakturerbara utnyttjade projekttimmar] / (ProjectAccountingCube_Projects [totala faktiska fakturerbara utnyttjade projekttimmar] + ProjectAccountingCube_Projects [projektets totala faktiska fakturerbara ej fakturerbara timmar] | Totala faktiska fakturerbara timmar, baserat på utnyttjad timmar och ej fakturerbara timmar. |
| Intjänat värde                 | ProjectAccountingCube_Projects [total planerad projektkostnad] * ProjectAccountingCube_Projects [procentandel av slutfört arbete] | Planerad totalkostnad multiplicerad med procentandelen slutfört arbete. |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Enhet: ProjectAccountingCube_TotalEstimatedCosts 
**Datakälla:** ProjTable

| Sammanlagda huvudmått       | Fält               | beskrivning | 
|---------------------------------|---------------------|-------------|
| Planerad kostnad för slutförd aktivitet | Sum(TotalCostPrice) | Uppskattad total självkostnad för alla projekttransaktionstyper som har slutförda uppgifter. |

