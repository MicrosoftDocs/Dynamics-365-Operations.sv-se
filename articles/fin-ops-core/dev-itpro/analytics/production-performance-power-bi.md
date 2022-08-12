---
title: Produktionsprestanda för Power BI-innehåll
description: Den här artikeln beskriver vad som ingår i Power BI-innehållet för produktionsprestanda.
author: AndersGirke
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.search.form: ProductionPerformancePowerBI
ms.openlocfilehash: e1b8afcc3d1b64c6828e4081b41a74d3b76731bc
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205746"
---
# <a name="production-performance-power-bi-content"></a>Produktionsprestanda för Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver vad som ingår i **produktionsprestanda** Microsoft Power BI-innehållet. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **Produktionsprestanda** är avsett för produktionschefer eller personer i organisationen som är ansvariga för produktionskontroll.

Rapporterna som ingår tillåter användning av Power BI för att övervaka prestandan i tillverkningsprocesser med avseende på snabbt utförande, kvalitet och kostnad. Rapporterna använder transaktionsdata från produktionsorder och batchorder och innehåller både en aggregerad vy över företagets produktionsmått och en uppdelning av mått efter produkt och resurs.

Power BI-innehållet markerar organisationens förmåga att slutföra produktionen i tid och fullständigt. Framtida prestanda projiceras utifrån produktionsplaner. Omfattande rapporter innehåller detaljerad insyn i produktfel som orsakas av produktionen och felsatser för resurser och operationer.

Power BI-innehållet låter dig även analysera produktionsavvikelser. Produktionsavvikelser beräknas som skillnaden mellan uppskattad och verklig kostnad. Produktionsavvikelser beräknas när produktionsorder eller batchorder uppnår statusen **Avslutad**.

Power BI-innehåll för **Produktionsprestanda** omfattar inkluderar data som har hämtats från produktionsorder och batchorder. Rapporterna innehåller inte data som är relaterade till kanban-produktioner.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
**Produktionsprestanda** Power BI-innehåll visas på sidan **Produktionsprestanda** (**Produktionskontroll** \> **Förfrågningar och rapporter** \> **Analys av produktionsprestanda** \> **Produktionsprestanda**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet

Power BI-innehållet **Produktionsprestanda** omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualiseras som diagram, brickor och tabeller.

Följande register ger en översikt över visualiseringar som ingår.

| Rapportsida                                | Diagram | Paneler |
|--------------------------------------------|--------|-------|
| Produktionsprestanda                     | <ul><li>Antal produktionsrader efter datum</li><li>Antal produktioner per produkt- och artikelgrupp</li><li>Antal planerade produktionsorder efter datum</li><li>Nedre 10 produkter efter i tid &amp; i sin helhet</li></ul> | <ul><li>Totalt antal order</li><li>I tid &amp; i sin helhet i procent</li><li>Ofullständiga i procent</li><li>Tidiga i procent</li><li>Sena i procent</li></ul> |
| Fel efter produkt                         | <ul><li>Defektgrad (ppm) efter datum</li><li>Defektgrad (ppm) efter produkt- och artikelgrupp</li><li>Producerad kvantitet efter datum</li><li>Topp 10-produkter efter effektiva ränta</li></ul> | <ul><li>Defektgrad (ppm)</li><li>Defekt kvantitet</li><li>Total kvantitet</li></ul> |
| Feltrend efter produkt                   | Defektgrad (ppm) efter producerad kvantitet | Defektgrad (ppm) |
| Defektgrad per resurs                        | <ul><li>Defektgrad (ppm) efter datum</li><li>Defektgrad (ppm) per resurs- och plats</li><li>Defektgrad (ppm) efter operation</li><li>Topp 10-resurser efter defektgrad</li></ul> | Defekt kvantitet |
| Feltrend efter resurs                  | Defektgrad (ppm) efter processad kvantitet | |
| Produktionsavvikelser för kostnadsberäkning av jobborder | <ul><li>Produktionsavvikelse efter datum och kostnadsgruppstyp</li><li>Produktionsavvikelse efter plats och kostnadsgruppstyp</li><li>Topp 10-produkter med negativ produktionsavvikelse</li><li>Topp 10-produkter med produktionsavvikelse efter resurs</li></ul> | <ul><li>Realiserad kostnad</li><li>Produktionsavvikelse</li><li>Produktionsavvikelse i procent</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapportsidorna Power BI-innehållet **Produktionsprestanda**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information om enhetslagring finns i [Power BI-integration med enhetslagring](power-bi-integration-entity-store.md).

Följande tabeller visar huvudaggregatmått som ligger till grund för Power BI-innehållet.

| Enhet                   | Sammanlagda huvudmått  | Datakällan för appar för ekonomi och drift | Fält              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

Följande tabell visar hur viktiga sammanlagda mått används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått                  | Hur åtgärden beräknas |
|--------------------------|-------------------------------|
| Produktionsavvikelse i procent   | SUM('produktionsavvikelse'\[produktionsavvikelse\]) / SUM('produktionsavvikelse'\[uppskattad kostnad\]) |
| Alla planerade order       | COUNTROWS (planerade produktionsorder) |
| Årlig                    | COUNTROWS(FILTER('planerad tillverkningsorder', 'planerad tillverkningsorder'\[schemalagt slutdatum\] \< 'planerad tillverkningsorder'\[behovsdatum\])) |
| Sen                     | COUNTROWS(FILTER('planerad tillverkningsorder', 'planerad tillverkningsorder'\[schemalagt slutdatum\] \> 'planerad tillverkningsorder'\[behovsdatum\])) |
| I tid                  | COUNTROWS(FILTER('planerad tillverkningsorder', 'planerad tillverkningsorder'\[schemalagt slutdatum\] = 'planerad tillverkningsorder'\[behovsdatum\])) |
| I tid i procent                | IF (”planerad tillverkningsorder”\[i tid\] \<\> 0, ”planerad tillverkningsorder”\[i tid\], IF (”planerad tillverkningsorder”\[Alla planerade ordrar\] \<\> 0, 0, BLANK()) ) / ”planerad tillverkningsorder”\[Alla planerade ordrar\] |
| Slutfördes                | COUNTROWS(FILTER('Produktionsorder', 'Produktionsorder'\[är RAF'ed\] = TRUE)) |
| Defektgrad (ppm)     | IF('Tillverkningsorder'\[sammanlagd kvantitet\] = 0, BLANK(), (SUM('Tillverkningsorder'\[Antal felaktiga\]) / 'Tillverkningsorder'\[sammanlagd kvantitet\]) \* 1000000) |
| Fördröjd produktionsorderandel  | 'Tillverkningsorder'\[Late \#\] / 'Tillverkningsorder'\[slutförd\] |
| Tidit och fullständig          | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[är hel\] = TRUE && 'Tillverkningsorder'\[är tidig\] = TRUE)) |
| Tidig \#                 | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[är tidig\] = TRUE)) |
| Tidiga i procent                  | IFERROR( IF('Tillverkningsorder'\[tidig \#\] \<\> 0, 'Tillverkningsorder'\[tidig \#\], IF('Tillverkningsorder''\[Summa order\] = 0, BLANK(), 0)) / 'Tillverkningsorder'\[Summa order\], BLANK()) |
| Ofullständigt               | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[fullständig\] = FALSE && 'Tillverkningsorder'\[är RAF'ed\] = TRUE)) |
| Ofullständiga i procent             | IFERROR( IF('Tillverkningsorder'\[Ofullständig\] \<\> 0, 'Tillverkningsorder'\[Ofullständig\], IF('Tillverkningsorder'\[Totalt antal order\] = 0, BLANK(), 0)) / 'Tillverkningsorder'\[Totalt antal order\], BLANK()) |
| Är fördröjd               | 'Tillverkningsorder'\[är RAF'ed\] = TRUE && 'Tillverkningsorder'\[Fördröjt värde\] = 1 |
| Är tidig                 | 'Tillverkningsorder'\[är RAF'ed\] = TRUE && 'Tillverkningsorder'\[Dagar fördröjt\] \< 0 |
| Fullständigt               | 'Tillverkningsorder'\[Bra kvantitet\] \>= 'Tillverkningsorder'\[Schemalagd kvantitet\] |
| Är RAF'ed                | 'Tillverkningsorder'\[Tillverkningsstatusvärde\] = 5 \|\| 'Tillverkningsorder'\[Tillverkningsstatusvärde\] = 7 |
| Sen & fullständig           | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[är fullständig\] = TRUE && 'Tillverkningsorder'\[är fördröjd\] = TRUE)) |
| Sen \#                  | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[är fördröjd\] = TRUE)) |
| Sena i procent                   | IFERROR( IF('Tillverkningsorder'\[sen \#\] \<\> 0, 'Tillverkningsorder'\[sen \#\], IF('Tillverkningsorder'\[Totalt antal order\] = 0, BLANK(), 0)) / 'Tillverkningsorder'\[Totalt antal order\], BLANK()) |
| I tid och fullständig        | COUNTROWS(FILTER('Tillverkningsorder', 'Tillverkningsorder'\[är fullständig\] = TRUE && 'Tillverkningsorder'\[är fördröjd\] = FALSE && 'Tillverkningsorder'\[är tidig\] = FALSE)) |
| I tid och i sin helhet i procent      | IFERROR( IF('Tillverkningsorder'\[I tid och fullständig\] \<\> 0, 'Tillverkningsorder'\[I tid och fullständig\], IF('Tillverkningsorder'\[Slutförd\] = 0, BLANK(), 0)) / 'Tillverkningsorder'\[Slutförd\], BLANK()) |
| Totalt antal order             | COUNTROWS (produktionsorder) |
| Total kvantitet           | SUM('Tillverkningsorder'\[Bra kvantitet\]) + SUM('Tillverkningsorder'\[Felaktig kvantitet\]) |
| Defektgrad (ppm)        | IF( 'Flödestransaktioner'\[Bearbetad kvantitet\] = 0, BLANK(), (SUM('Flödestransaktioner'\[Felaktig kvantitet\]) / 'Flödestransaktioner'\[Bearbetad kvantitet\]) \* 1000000) |
| Defektgrad blandad (ppm) | IF( 'Flödestransaktioner'\[Total blandad kvantitet\] = 0, BLANK(), (SUM('Flödestransaktioner'\[Felaktig kvantitet\]) / 'Flödestransaktioner'\[Total blandad kvantitet\]) \* 1000000) |
| Bearbetad kvantitet       | SUM('Flödestransaktioner'\[Bra kvantitet\]) + SUM('Flödestransaktioner'\[Felaktig kvantitet\]) |
| Total blandad kvantitet     | SUM('Tillverkningsorder'\[Bra kvantitet\]) + SUM('Flödestransaktioner'\[Felaktig kvantitet\]) |

Följande tabell visar nyckeldimensionerna som används som filter för att dela upp de sammanlagda måtten så att du kan uppnå bättre nivåer och får djupare analysinsikter.

| Enhet                    | Exempel på attribut                                        |
|---------------------------|---------------------------------------------------------------|
| Datum för rapportering som avslutad | Motkonto för ifyllning, avvikelse dag, månad och år                 |
| Slutade den                | Avvikelse för avslutad månad och månad                                  |
| Behovsdatum          | Behovsdatum, månadsavvikelse och behovsdatum            |
| Flödestransaktionsdatum    | Flödestransaktion, månadsavvikelse och datum                       |
| Platser                     | Plats-ID, platsnamn, tillstånd och ort                          |
| Enheter                  | Id och Namn                                                   |
| Resurser                 | Resurs-ID, resursnamn, resurstyp och resursgrupp |
| Produkter                  | Produktnummer, produktnamn, artikel-ID och artikelgrupp         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
