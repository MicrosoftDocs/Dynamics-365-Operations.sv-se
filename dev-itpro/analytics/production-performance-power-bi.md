---
title: "Power BI-innehåll för produktionsprestanda"
description: "Det här avsnittet beskriver vad som ingår i Power BI-innehållet för produktionsprestanda. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet."
author: sericks
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 915ff93edff0f68f52a536ad169c8f0f917ac9b2
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017

---

# <a name="production-performance-power-bi-content"></a>Power BI-innehåll för produktionsprestanda

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Microsoft Power BI-innehållet för **Produktionsprestanda**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **Produktionsprestanda** är avsett för produktionschefer eller personer i organisationen som är ansvariga för produktionskontroll.

Rapporterna som ingår tillåter användning av Power BI för att övervaka prestandan i tillverkningsprocesser med avseende på snabbt utförande, kvalitet och kostnad. Rapporterna använder transaktionsdata från produktionsorder och batchorder och innehåller både en aggregerad vy över företagets produktionsmått och en uppdelning av mått efter produkt och resurs.

Power BI-innehållet markerar organisationens förmåga att slutföra produktionen i tid och fullständigt. Framtida prestanda projiceras utifrån produktionsplaner. Omfattande rapporter innehåller detaljerad insyn i produktfel som orsakas av produktionen och felsatser för resurser och operationer.

Power BI-innehållet låter dig även analysera produktionsavvikelser. Produktionsavvikelser beräknas som skillnaden mellan uppskattad och verklig kostnad. Produktionsavvikelser beräknas när produktionsorder eller batchorder uppnår statusen **Avslutad**.

Den **Produktionsprestanda** som Power BI-innehållet omfattar inkluderar data som har hämtats från produktionsorder och batchorder. Rapporterna innehåller inte data som är relaterade till kanban-produktioner.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, uppdatering juli 2017 visas Power BI-innehållet **Lagerställeprestanda** på sidan **Produktionsprestanda** (**Produktionsstyrning** > **Förfrågningar och rapporter** > **Produktionsprestandaanalyser** > **Produktionsprestanda**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehållet

Power BI-innehållet **Produktionsprestanda** omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualiseras som diagram, brickor och tabeller.

Följande register ger en översikt över visualiseringar som ingår.

| Rapportsida                                | Diagram                                               | Paneler |
|--------------------------------------------|------------------------------------------------------|-------|
| Produktionsprestanda                     | <ul><li>Antal produktionsrader efter datum</li><li>Antal produktioner per produkt- och artikelgrupp</li><li>Antal planerade produktionsorder efter datum</li><li>Nedre 10 produkter efter i tid och i sin helhet</li></ul> | <ul><li>Totalt antal order</li><li>I tid och i sin helhet i procent</li><li>Ofullständiga i procent</li><li>Tidiga i procent</li><li>Sena i procent</li></ul> |
| Fel efter produkt                         | <ul><li>Defektgrad (ppm) efter datum</li><li>Defektgrad (ppm) efter produkt- och artikelgrupp</li><li>Producerad kvantitet efter datum</li><li>Topp 10-produkter efter effektiva ränta</li></ul> | <ul><li>Defektgrad (ppm)</li><li>Defekt kvantitet</li><li>Total kvantitet</li></ul> |
| Feltrend efter produkt                   | Defektgrad (ppm) efter producerad kvantitet | Defektgrad (ppm) |
| Defektgrad per resurs                        | <ul><li>Defektgrad (ppm) efter datum</li><li>Defektgrad (ppm) per resurs- och plats</li><li>Defektgrad (ppm) efter operation</li><li>Topp 10-resurser efter defektgrad</li></ul> | Defekt kvantitet |
| Feltrend efter resurs                  | Defektgrad (ppm) efter processad kvantitet | |
| Produktionsavvikelser för kostnadsberäkning av jobborder | <ul><li>Produktionsavvikelse efter datum och kostnadsgruppstyp</li><li>Produktionsavvikelse efter plats och kostnadsgruppstyp</li><li>Topp 10-produkter med negativ produktionsavvikelse</li><li>Topp 10-produkter med produktionsavvikelse efter resurs</li></ul> | <ul><li>Realiserad kostnad</li><li>Produktionsavvikelse</li><li>Produktionsavvikelse i procent</li></ul> |

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Microsoft Dynamics 365. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys.

Du hittar Power BI-innehållet **Produktionsprestanda** i biblioteket Gemensamma tillgångar i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

Hämta innehållet för **Produktionsprestanda** som avser versionen av Dynamics 365 som du använder.

> [!NOTE]
> Om du använder Microsoft Dynamics 365 for Operations version 1611 krävs KB 4011327 för detta Power BI-innehåll. När du loggar in på LCS får du åtkomst till KB här: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapportsidorna Power Bi-innehållet **Produktionsprestanda**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information om enhetslagring finns i [Power BI-integration med enhetslagring](power-bi-integration-entity-store.md).

Följande tabeller visar huvudaggregatmått som ligger till grund för Power BI-innehållet.

| Enhet                   | Sammanlagda huvudmått  | Datakällan för Finance and Operations | Fält              |
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
| Produktionsavvikelse i procent   | SUM (produktionsavvikelse [produktionsavvikelse])/SUM (produktionsavvikelse [uppskattad kostnad]) |
| Alla planerade order       | COUNTROWS (planerade produktionsorder) |
| Årlig                    | COUNTROWS (FILTER (”planerad tillverkningsorder”, ”planerad tillverkningsorder” [schemalagt slutdatum] \< ”planerad tillverkningsorder” [behovsdatum])) |
| Sent                     | COUNTROWS (FILTER (”planerad tillverkningsorder”, ”planerad tillverkningsorder” [schemalagt slutdatum] \> ”planerad tillverkningsorder” [behovsdatum])) |
| I tid                  | COUNTROWS (FILTER (”planerad tillverkningsorder”, ”planerad tillverkningsorder” [schemalagt slutdatum] = ”planerad tillverkningsorder” [behovsdatum])) |
| I tid i procent                | IF (”planerad tillverkningsorder” [i tid] \<\>0 'planerad tillverkningsorder' [i tid], IF (”planerad tillverkningsorder” [alla planerade order] \<\>0, 0, TOMT()))/”planerad tillverkningsorder” [alla planerade order] |
| Ifylld                | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsorder' [är RAF'ed] = TRUE)) |
| Defektgrad (ppm)     | IF ('Tillverkningsordern ”[sammanlagd kvantitet] = 0, BLANK(), (SUM ('Tillverkningsordern' [Antal felaktiga]) / 'Tillverkningsorder” [sammanlagd kvantitet]) \*1000000) |
| Fördröjd produktionsorderandel  | 'Tillverkningsordern' [sen \#] / 'Tillverkningsordern' [slutförd] |
| Tidit och fullständig          | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsordern' [är helt] = TRUE & & 'Tillverkningsordern' [är tidig] = TRUE)) |
| Tidig \#                 | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsorder' [är tidig] = TRUE)) |
| Tidig i procent                  | IFERROR (IF ('Tillverkningsordern' [tidig \#] \<\>0, Production order' [tidig \#] IF (”tillverkningsordern' [Summa order] = 0, BLANK(), 0)) / 'Tillverkningsordern' [Totalt antal order] BLANK()) |
| Ofullständigt               | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsorder' [Fullständigt] = FALSE & & 'Tillverkningsordern' [Är RAF'ed] = TRUE)) |
| Ofullständiga i procent             | IFERROR (IF ('Tillverkningsordern' [Ofullständig ] \<\> 0, Produktionsorder' [Ofullständig ] IF (”tillverkningsorder' [Totalt antal order] = 0, BLANK(), 0)) / 'Tillverkningsorder' [Totalt antal order] BLANK()) |
| Är fördröjd               | 'Produktionsorder'[Is RAF'ed] = TRUE && 'Produktionsorder'[Fördröjt värde] = 1 |
| Är tidig                 | 'Produktionsorder'[Är RAF'ed] = TRUE && 'Produktionsorder'[Dagar försenad] \< = 0 |
| Fullständigt               | 'Tillverkningsorder' [Bra kvantitet] \>= 'Tillverkningsorder' [schemalagd kvantitet] |
| Är RAF'ed                | 'Tillverkningsorder' [produktionens statusvärde] = 5 \|\| 'Tillverkningsorder' [produktionens statusvärde] = 7 \ |
| Sen & fullständig           | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsorder' [Fullständig] = TRUE & & 'Tillverkningsordern' [Fördröjd] = TRUE)) |
| Sen \#                  | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsorder' [Fördröjd] = TRUE)) |
| Sen i procent                   | IFERROR (IF ('Tillverkningsordern' [Sen \#] \<\>0, Production order' [Sen \#] IF (”tillverkningsordern' [Summa order] = 0, BLANK(), 0)) / 'Tillverkningsordern' [Totalt antal order] BLANK()) |
| I tid och fullständig        | COUNTROWS (FILTER ('Produktionsorder', 'Tillverkningsordern' [Fullständig] = TRUE & & ''[är försenad] = FALSKT & & 'Tillverkningsordern' [är tidig] = FALSE)) |
| I tid och i sin helhet i procent      | IFERROR (IF ('Tillverkningsordern' [I tid och fullständig ] \<\> 0, Produktionsorder' [I tid och fullständig ] IF (”tillverkningsorder' [Totalt antal order] = 0, BLANK(), 0)) / 'Tillverkningsorder' [Slutförd] BLANK()) |
| Totalt antal order             | COUNTROWS (produktionsorder) |
| Total kvantitet           | SUM('Produktionsorder'[Bra kvantitet]) + SUM('Production order'[Fel kvantitet]) |
| Defektgrad (ppm)        | IF ('Flödestransaktioner' [kvantitet bearbetad] = 0, BLANK(), (SUMMA ('Flödestransaktioner' [Antal felaktiga]) / 'Flödestransaktioner' [kvantitet bearbetad]) \*1000000) |
| Defektgrad blandad (ppm) | IF ('Flödestransaktioner' [Total blandad kvantitet] = 0, BLANK(), (SUMMA ('Flödestransaktioner' [Antal felaktiga]) / 'Flödestransaktioner' [Total blandad kvantitet]) \*1000000) |
| Bearbetad kvantitet       | SUM ('Flödestransaktioner' [Bra kvantitet]) + SUM ('Flödestransaktioner' [Felaktig kvantitet]) |
| Total blandad kvantitet     | SUM ('Produktionsorder' [Bra kvantitet]) + SUM ('Flödestransaktioner' [Felaktig kvantitet]) |

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

## <a name="additional-resources"></a>Ytterligare resurser

Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

- [Datatabeller](https://ax.help.dynamics.com/en/wiki/data-entities/)
- [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Lägga till Power BI-rutor till arbetsytor](http://ax.help.dynamics.com/en/wiki/configuring-powerbi-integration/)

