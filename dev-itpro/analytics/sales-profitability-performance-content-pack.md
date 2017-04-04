---
title: "Försäljning och lönsamhet prestanda Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i Dynamics 365 för verksamhet – försäljnings- och lönsamhet prestanda innehållet för Microsoft Power BI. Det förklaras hur du öppnar rapporter i content pack och ger information om datamodellen och enheter som används för att skapa innehåll pack."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Försäljning och lönsamhet prestanda Power BI-innehåll

Det här avsnittet beskriver vad som ingår i Dynamics 365 för verksamhet – försäljnings- och lönsamhet prestanda innehållet för Microsoft Power BI. Det förklaras hur du öppnar rapporter i content pack och ger information om datamodellen och enheter som används för att skapa innehåll pack.

<a name="overview"></a>Översikt
--------

Det här innehållet skapades för försäljningschef vill övervaka viktiga försäljning mått omsättning, bruttovinst och vinstmarginaler. Den använder transaktionell försäljningsdata från Dynamics 365 för operationer och innehåller både en aggregerad vy över företagets försäljningssiffror och en uppdelning av försäljningsresultat för kunder och produkter. Genom att markera ändringar i intäkter och vinst ökade med tiden kan rapporter användas för att Avisera chefer om positiva och negativa trender för enskilda kunder och produkter. Kategori och regionala chefer ska vara praktiskt att ha jämförs intäkt och lönsamhet olika produktkategorier och kundgrupper till varandra kan sortera ut Eftersläntrare och företag. En omfattande rapport som visar viss kunds intäkten jämfört med Kontoansvariga vinstmarginal som ger en grund för säkerhetskopierade data att attune sina insatser för försäljning och marknadsföring i respektive profil för varje kund. Försäljnings- och lönsamhet innehåll pack kan försäljningsansvariga Försäljningsresultat per Analysera prestanda:

-   Intäkt för innevarande år (genom kundgrupp enskilda kunder, försäljning kategorier och enskilda produkter och områden)
-   Ändring av intäkter, år över år (per kund regioner och försäljning-kategori)

Lönsamhet kan analyseras med:

-   Bruttovinst och vinstmarginal (efter kundgrupper och försäljning av produktkategorier)
-   Bruttovinst ändring år över år
-   Kundlönsamhet (genom att skillnaden mellan bruttomarginal)

## <a name="accessing-the-content-pack"></a>Åtkomst till content pack
Försäljnings- och lönsamhet prestanda Power BI innehåll pack har publicerats som en tillgång implementering Lifecycle Services (LCS) och kan nås från Dynamics 365 för operationer. Mer information om hur du öppnar och starta Power BI-rapporter finns i [Power BI innehåll från Microsoft och partner LCS](power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>Mått i content pack
Content pack innehåller en rapport som består av en uppsättning visualized som diagram, tabeller och rutor mått. Nedan visas en översikt över visualisations i content pack.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Rapportsida**        | **Charts**                                 | **Sida vid sida**                                               |
| Intäkt per kund    | 10 främsta kunder efter intäkter                | Total intäkt                                           |
|                        | Total intäkt per kund            | Vinstökning under YOY                                      |
|                        | Kunden genomsnittliga omsättning efter kundgrupp | Bruttomarginal                                            |
|                        | Intäkter och bruttomarginal per kund   |                                                         |
| Intäkt per produkt     | Intäkter och bruttomarginal per försäljningskategori   | Totala \#av produkter                                    |
|                        | Topp 10-produkter efter intäkter                 | Totalt antal aktiva produkter och procentuell andel |
|                        | Total intäkt per försäljningskategori            | Antal produkter redovisning av intäkter 80 %           |
| Intäkt per period\*    | Intäkt per månad                           | Vinstökning under YOY                                      |
|                        | Efterföljande YOY intäkter avvikelse             | YOY intäkt growth %                                    |
|                        | Total avvikelse av försäljning per region för kund    |                                                         |
| Intäkt per lagerställe    | Försäljningsintäkter efter ort                      |                                                         |
|                        | YOY intäkt growth %                       |                                                         |
|                        | Försäljningsintäkter efter region                    |                                                         |
| Kundlönsamhet | Bruttomarginal jämfört med intäkter per kund   | Bruttovinst, bruttomarginal Vinstökning under YOY          |
| Lönsamhetsanalys | Intäkter och bruttomarginal per månad          |                                                         |
|                        | Högsta 15 kunder efter bruttomarginal           |                                                         |
|                        | Bruttomarginal per månad, YOY                 |                                                         |

\*Intäkter detta och förra året och tillväxt per försäljningskategori.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer används för att fylla i rapporten i försäljnings- och lönsamhet prestanda innehållet. Detta visas som sammansatta mått som mellanlagras i arkivet entitet som är en Microsoft SQL-databas för analys. Läs mer om i bloggen [Power BI integration med Store enhet i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Sammansatta måtten i det här innehållet är del av de sammanlagda mått som fanns i kuben Sales i Dynamics AX 2012 och AX 2012 R3. För att förbereda kubens aggregerade mått i butiken enheten måste du göra dem kan. Mer information finns i proceduren om hur mellanlagra aggregerade mått till butiken i bloggen entiteten [Power BI integration med Store enhet i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Följande viktiga aggregerade mätningar för fakturaentiteten rader används som bas för innehållet.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | **Sammansatta centrala nyckeltal**               | **Datakälla för Dynamics 365 för operationer** | **Field**                                    | **Description**                          |
| Fakturarader | Intäkt                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Belopp i redovisningsvaluta            |
|               | Kostnader för sålda varor                           | InventTrans                                     | Summa (CostAmountPosted + CostAmountAdjustment) | Kostnadsbelopp + justering                 |
|               | Kommissionen Radbelopp – redovisningsvaluta | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Provisionsbelopp i redovisningsvalutan |

Följande tabell visar viktiga aggregerade mätningar av fakturaentiteten rader som används för att skapa flera beräknade mått i en datauppsättning på innehållet.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | **Beräknat som**                                                                                |
| Bruttovinst      | Summa (intäkt – kostnad för sålda varor – provisionen – moms (som ingår i Radbelopp på kundfaktura))          |
| Bruttomarginal      | Summa (bruttovinst / (intäkt - moms (som ingår i Radbelopp på kundfaktura)))             |
| Intäkt ifjol | Intäkt ifjol = BERÄKNA (SUMMA ('Fakturarader'\[intäkter\]), SAMEPERIODLASTYEAR (datum\[datum\]) |

Ange följande dimensioner i den **försäljningskuben** används som filter för att dela upp sammansatta måtten för att uppnå förbättrad säkerhetsadministration och analytiska djupare kunskaper.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | **Exempel på attribut**                           |
| Kunder        | Kundgrupper, regioner kund, adress, bransch |
| Produkter         | Produktnummer, produktnamn, grupper-objektnamn       |
| Försäljningskategorier | Namn på försäljningskategori                                 |
| Juridiska personer   | Namn på juridisk person                                   |
| Datum            | Datum                                                |

Normalt innehåll pack visar data för det aktuella kalenderåret, men du kan öppna rapportavsnittet filter och ändra datumfiltret. Du kan också ändra filtret för företaget.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)



