---
title: "Innehållspaket för försäljnings- och lönsamhetsprestanda för Power BI"
description: "Det här avsnittet beskriver vad som ingår i Dynamics 365 or Operations – Innehållspaket för försäljnings- och lönsamhetsprestanda för Microsoft Power BI. Det förklarar åtkomst rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
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

# <a name="sales-and-profitability-performance-power-bi-content"></a>Innehållspaket för försäljnings- och lönsamhetsprestanda för Power BI

Det här avsnittet beskriver vad som ingår i Dynamics 365 or Operations – Innehållspaket för försäljnings- och lönsamhetsprestanda för Microsoft Power BI. Det förklarar åtkomst rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

<a name="overview"></a>Översikt
--------

Det här innehållet skapades för försäljningschef vill övervaka viktiga försäljningsmått av omsättning, bruttovinst och vinstmarginaler. Den använder försäljningstransaktionsdata från Dynamics 365 for Operations och ger både en sammanfattning av de företagsomspännande försäljningsuppgifterna och en fördelning av försäljningsprestanda för kunder och produkter. Genom att markera ändringar i intäkter och vinstökning med tiden kan rapporter användas för att avisera chefer om positiva och negativa trender för enskilda kunder och produkter. Kategori och regionala chefer kommer att tycka att det är praktiskt att ha diagram som jämför intäkt och lönsamhet för olika produktkategorier och kundgrupper till varandra för att kan sortera ut eftersläntrare och ledare. En omfattande rapport som visar individuella kunders intäkt jämfört med kontoansvarigas vinstmarginal som ger en grund för säkerhetskopierade data att anpassa deras marknadsföringsansträngningar i respektive profil för varje kund. Innehållspaketet för försäljnings- och lönsamhetsresultat låter försäljningsansvariga analysera försäljningsresultat per:

-   Intäkt, för innevarande år (efter kundgrupp och enskilda kunder, försäljningskategorier och enskilda produkter och områden)
-   Ändring av intäkter, årsbasis (efter kundregion och försäljningskategori)

Lönsamhet kan analyseras med:

-   Bruttovinst och vinstmarginal (efter kundgrupper och produktförsäljningskategorier)
-   Bruttovinständring, årsbasis
-   Kundlönsamhet (efter intäkt jämfört med bruttomarginal)

## <a name="accessing-the-content-pack"></a>Åtkomst till innehållspaketet
Innehållspaket för försäljnings- och lönsamhetsprestanda för Microsoft Power BI. har publicerats som en implementeringstillgång i Lifecycle Services (LCS) och kan nås från Dynamics 365 for Operations. Mer information om hur du öppnar och startar Power BI-rapporter finns i [Power BI-innehåll i LCS från Microsoft och din partner](power-bi-content-microsoft-partners.md).

## <a name="metrics-included-in-the-content-pack"></a>Mått inkluderade i innehållspaketet
Innehållspaketet innehåller en rapport som består av en uppsättning mått som visas som diagram, paneler och register. Nedanstående register ger en översikt över de visualiseringar som används i innehållspaketet.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Rapportsida**        | **Diagram**                                 | **Paneler**                                               |
| Intäkter per kund    | Bästa 10 kunderna per intäkt                | Total intäkt                                           |
|                        | Total intäkt per kund            | YOY vinstökning                                      |
|                        | Genomsnittlig kundintäkt per kundgrupp | Bruttomarginal                                            |
|                        | Intäkt- och bruttomarginal per kundgrupp   |                                                         |
| Intäkt per produkt     | Intäkt- och bruttomarginal per försäljningskategori   | Totalt \# produkter                                    |
|                        | Bästa 10 produkterna per intäkt                 | Totalt antal aktiva produkter och procentuell andel av total |
|                        | Total intäkt per försäljningskategori            | Antal produkter som redovisas för 80 % av intäkter           |
| Intäkter per period\*    | Intäkter per månad                           | YOY vinstökning                                      |
|                        | Ränteinkomstvariation, YOY             | YOY vinstökning %                                    |
|                        | Total försäljningsavvikelse per kundregion    |                                                         |
| Intäkt per plats    | Försäljningsintäkter per ort                      |                                                         |
|                        | YOY vinstökning %                       |                                                         |
|                        | Försäljningsintäkter per region                    |                                                         |
| Kundlönsamhet | Kundlönsamhet jämfört med intäkt, per kund   | Bruttovinst, bruttomarginal, YOY vinstökning          |
| Lönsamhetsanalys | Intäkter och bruttomarginal per månad          |                                                         |
|                        | Bästa 15 kunderna per bruttomarginal           |                                                         |
|                        | Bruttomarginal per månad, YOY                 |                                                         |

\*Intäkter detta och förra året och tillväxt per försäljningskategori.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 for Operations-data används för att fylla i rapportsidorna i Innehållspaketet för försäljnings- och lönsamhetsresultat. Detta visas som sammansatta mått som mellanlagras i enhetsarkivet, som är en Microsoft SQL-databas som är optimerad för analys. Läs mer om detta i bloggen [Power BI-integration med enhetsbutik i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i Sales Cube i Dynamics AX 2012 och AX 2012 R3. För att förbereda kubens sammanlagda mått i enhetsbutiken måste du göra dem driftfärdiga. Mer information finns i proceduren om hur du mellanlagrar sammanlagda mått i enhetsbutiken i bloggen [Power BI-integration med enhetsbutik i Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Följande sammanlagda huvudmått av fakturaradenheten används till grund för innehållspaketet:

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Enhet**    | **Sammanlagda huvudmått**               | **Datakälla för Dynamics 365 for Operations** | **Fält**                                    | **Beskrivning**                          |
| Fakturarader | Intäkt                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Belopp i redovisningsvaluta            |
|               | Kostnader för sålda varor                           | InventTrans                                     | Summa (CostAmountPosted + CostAmountAdjustment) | Kostnadsbelopp + justering                 |
|               | Provisionsradbelopp - redovisningsvaluta | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Provisionsradbelopp i redovisningsvaluta |

Följande tabell visar hur viktiga sammanlagda mått av fakturaradenheten som används för att skapa flera beräknade mått i innehållspaketets datauppsättning.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Mått**       | **Beräknat som**                                                                                |
| Bruttovinst      | SUM(Intäkt - COGS - Provision - Moms (som ingår i radbelopp på kundfaktura)           |
| Bruttomarginal      | SUM(Bruttovinst - COGS - Provision - Moms (som ingår i radbelopp på kundfaktura)              |
| Intäkt ifjol | Intäkt ifjol = BERÄKNA(SUM('Fakturarader'\[intäkter\]), SAMMAPERIODSOMFÖRRAÅRET(datum\[datum\]) |

Följande huvuddimensioner används som filter i **Försäljningskuben** för att dela upp de sammanlagda måtten i syfte att uppnå en förbättrad nivå och ge djupare analysinsikter.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Enhet**       | **Exempel på attribut**                           |
| Kunder        | Kundgrupper, kundregioner, adress, bransch |
| Produkter         | Produktnummer, produktnamn, artikelgruppsnamn       |
| Försäljningskategorier | Namn på försäljningskategori                                 |
| Juridiska personer   | Namn på juridisk person                                   |
| Datum            | Datum                                                |

Normalt visar innehållspaket data för det aktuella kalenderåret, men du kan öppna avsnittet rapportfilter och ändra datumfiltret. Du kan också ändra filtret för företaget.

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)



