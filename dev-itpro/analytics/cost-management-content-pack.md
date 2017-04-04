---
title: "Kostnadshantering Power BI-innehåll"
description: "Det här avsnittet beskriver vad som ingår i kostnadshantering Power BI-innehåll. Det förklaras hur du öppnar Power BI-rapporter och ger information om enheter som används för att skapa innehåll och datamodellen."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Kostnadshantering Power BI-innehåll

Det här avsnittet beskriver vad som ingår i kostnadshantering Power BI-innehåll. Det förklaras hur du öppnar Power BI-rapporter och ger information om enheter som används för att skapa innehåll och datamodellen.

# <a name="overview"></a>Översikt

Den **kostnad management** Microsoft Power BI innehållet riktar sig till revisorer lager eller personer i organisationen som är ansvarig för lagret. Den **kostnad management** Power BI-innehåll är ledarskap inblick i lager och lager av varor i arbete (PIA) och kostnaden väg genom dem efter kategori med tiden. Informationen kan också användas som komplement till ekonomirapporten detaljerad.

## <a name="key-measures"></a>Viktiga åtgärder

+ Ingående saldo
+ Slutsaldo
+ Nettoändring
+ Nettoförändring i %
+ Åldersfördelning

## <a name="key-performance-indicators"></a>Prestationsindikatorer
+ Lageromsättning
+ Lagerprecision

Den primära datakällan för CostAggregatedCostStatementEntryEntity är CostStatementCache. Den här tabellen hanteras av ramverket datauppsättning cachen. Registret uppdateras var 24: e timme som standard men du kan aktivera manuella uppdateringar i cachen konfiguration. Du kan sedan göra en manuell uppdatering i den **kostnad management** eller **analys av** arbetsytan. När uppdateringen av CostStatementCache har körts måste du uppdatera OData-anslutning på rätt BI.com att visa uppdaterade data på webbplatsen. Åtgärderna i Power BI innehållet avvikelse (inköp, produktion) gäller endast artiklar som valuated av metoden standardkostnad lager. Produktionsavvikelse beräknas som skillnaden mellan aktiv och verklig kostnad. Produktion avvikelsen beräknas när produktionsordern har statusen **avslutat**. Mer information om avvikelsen produktionstyper och hur beräknas varje typ finns [om att analysera avvikelser för en avslutad tillverkningsorder](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Power BI-innehåll
Den **kostnad management** Power BI-innehåll är tillgängligt från PowerBI.com. Mer information om hur du ansluter och läsa in dina Microsoft Dynamics 365 för operationer finns [Power BI åtkomst innehåll från PowerBI.com](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehåll
Innehållet omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualized som, brickor, t.ex. Följande tabell ger en översikt över de visuella effekterna i den **kostnad management** Power BI-innehåll.

| Rapportsida | Diagram | Titlar |
|---|---|---|
|Övergripande lager (standard efter aktuell period) |Precision |Lager-åtgärder:<br>Lager, utgående balans<br>Förändring av lager<br>Lager nettoförändringen %<br>|
| |Lageromsättning | |
| |Utgående balans av resursgruppen lager | |
| |Lagrets Nettoändring per kategori namn nivå 1 och kategori namn 2| |
| |Inköpsavvikelser av resursgrupp och namnet kategorinivå 3 | |
|Lager per site (standard efter aktuell period) |Utgående balans platsnamn som resursgruppen lager | |
| |Stänga lagret genom platsnamn och resursgrupp | |
| |Utgående balans per resurs och orten lager | |
|Lager per resursgrupp (standard efter aktuell period) |Åtgärder för lager | |
| |Lagret är korrekt genom att mängden resursgrupp | |
| |Stänga lagret genom att mängden resursgrupp | |
|Lager-YOY (standard innevarande år jämfört med föregående år) |Åtgärder för lager | |
| |Lager-KPI: er:<br>Lageromsättning<br>Lagerprecision | |
| |Utgående balans per år och resurs lager | |
| |Inköpsavvikelser per år och kategori namn 3 | |
|Åldersfördelning lager (standard med innevarande år) |Åldersfördelning för lager per kvartal och resurs | |
| |Åldersfördelning lager efter kvartal och platsens namn | |
|Total PIA (standard efter aktuell period) |Netto PIA ändra namnet kategorinivå 1 och kategori namn 2 |Produkter i arbete PIA-åtgärder:<br>PIA-slutsaldo<br>PIA-Nettoförändring<br>PIA-Nettoförändring %<br> |
| |Produktionsavvikelser per resursgrupp och namnet kategorinivå 3 | |
| |PIA Nettoändring per resursgrupp | |
|PIA per site (standard efter aktuell period) |Produkter i arbete PIA-åtgärder | |
| |Ändra netto PIA genom platsnamn och namn kategorinivå 2 | |
| |Produktionsavvikelser per platsnamn och namn kategorinivå 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 för operationer data för att bedöma rapportsidorna i den **kostnad management** Power BI-innehåll. Informationen visas som sammansatta mått som mellanlagras i arkivet entitet som är en Microsoft SQL-databas som är optimerad för analys. Mer information finns i [översikt Power BI integration med entiteten arkivet](power-bi-integration-entity-store.md). Följande viktiga aggregerade mätningar används som bas för innehållet.

| Enhet            | Nyckelmätpunkt aggregerade | Datakälla för Dynamics 365 för operationer | Fält             | beskrivning                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Utdrag-transaktioner | Nettoändring                | CostAggregatedCostStatementEntryEntity      | Summa (\[belopp\])   | Belopp i redovisningsvaluta |
| Utdrag-transaktioner | Nettoförändring kvantitet       | CostAggregatedCostStatementEntryEntity      | Summa (\[kvantitet\]) |                                   |

Följande tabell visar hur viktiga aggregerade mått som används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått                                 | Hur åtgärden ska beräknas.                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ingående saldo                       | \[Utgående balans\]-\[Nettoförändring\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Startkvantitet saldo              | \[Största Saldokvantitet\]-\[Nettoförändring kvantitet\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Slutsaldo                          | BERÄKNA (SUMMAN (\[belopp\]), FILTER (ALLEXCEPT ('Räkenskapskalendrar', 'Räkenskapskalendrar'\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]), 'Räkenskapskalendrar'\[datum\]&lt;= MAX ('Räkenskapskalendrar'\[datum\])))                                                                                                                                                                                           |
| Antal slut saldo                 | BERÄKNA (SUMMAN (\[kvantitet\]), FILTER (ALLEXCEPT ('Räkenskapskalendrar', 'Räkenskapskalendrar'\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]), 'Räkenskapskalendrar'\[datum\]&lt;= MAX ('Räkenskapskalendrar'\[datum\])))                                                                                                                                                                                         |
| Lager, ingående balans             | BERÄKNA (\[ingående balans\], 'Uttrycket transaktioner'\[utdragstypen\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                      |
| Lager, utgående balans                | BERÄKNA (\[slutsaldo\], 'Uttrycket transaktioner'\[utdragstypen\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                         |
| Förändring av lager                    | BERÄKNA (\[Nettoförändring\], 'Uttrycket transaktioner'\[utdragstypen\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                             |
| Nettoförändring lagerkvantitet           | BERÄKNA (\[kvantitet Nettoförändring,\], 'Poster uttrycket'\[utdragstypen\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                    |
| Lager nettoförändringen %                  | IF (\[lager slutsaldo\] = 0, 0, \[lager nettoförändringen\] / \[lagrets slutsaldo\])                                                                                                                                                                                                                                                                                                                                                                           |
| Stänga lagret med belopp                | Om (eller (\[lager Genomsnittligt saldo\]&lt;= 0, \[lager har sålts eller förbrukats problem\]&gt;= 0), 0 ABS (\[lager har sålts eller förbrukats problem\]) /\[lagrets Genomsnittligt saldo\])                                                                                                                                                                                                                                                                                                  |
| Genomsnittligt saldo lager               | (\[Lager slutsaldo\] + \[lager Startsaldot\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Lager har sålts eller förbrukats problem       | \[Sålda\] + \[lager förbrukas materialkostnad\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Lager förbrukas materialkostnad        | BERÄKNA (\[lager nettoförändringen\], 'Uttrycket transaktioner'\[kategorinamnet - nivå 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Sålt lager                          | BERÄKNA (\[lager nettoförändringen\], 'Uttrycket transaktioner'\[kategorinamnet - nivå 2\_\] = "Såld")                                                                                                                                                                                                                                                                                                                                                                             |
| Lagret är korrekt med belopp            | IF (\[lagrets slutsaldo\]&lt;= 0, om (eller (\[lager räknade beloppet\]&lt;&gt; 0, \[lagrets slutsaldo\]&lt; 0), 0, 1), MAX (0, (\[lagrets slutsaldo\] -ABS (\[lager räknade beloppet\])) /\[lagrets slutsaldo\]))                                                                                                                                                                                                                              |
| Det räknade beloppet lager                | BERÄKNA (\[lager nettoförändringen\], 'Uttrycket transaktioner'\[kategorinamnet - nivå 3\_\] = "Inventering")                                                                                                                                                                                                                                                                                                                                                                         |
| Lagerföråldring                         | Om (ÄRTOM (max ('Räkenskapskalendrar'\[datum\])), blank(), MAX (0, MIN (\[lager åldersfördelning för e-postkvitton kvantitet\], \[lagrets slutkvantiteten saldo för åldersfördelningsperiod\] - \[lager åldersfördelning e-postkvitton kvantitet i framtiden\]))) \*\[lager Genomsnittlig enhetskostnad\]                                                                                                                                                                                                                                |
| Kvantitet av inleveranser åldrande lager       | Om (\[minDate\] = \[minDateAllSelected\], BERÄKNA (\[lagrets Nettoförändring kvantitet\], 'Transaktioner uttrycket'\[kvantitet\]&gt; 0, FILTER (ALLEXCEPT ('Räkenskapskalendrar', 'Räkenskapskalendrar'\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]), 'Räkenskapskalendrar'\[datum\]&lt;= MAX ('Räkenskapskalendrar'\[datum\]))), BERÄKNA (\[lagrets Nettoförändring kvantitet\], 'Transaktioner uttrycket'\[kvantitet\]&gt; 0)) |
| Lager vid åldersfördelning Slutkvantitet saldo | \[Slutkvantitet saldo lager\] + BERÄKNA (\[lagrets Nettoförändring kvantitet\], FILTER (ALLEXCEPT ('Räkenskapskalendrar', "Räkenskapskalendrar"\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]), 'Räkenskapskalendrar'\[datum\]&gt; max ('Räkenskapskalendrar'\[datum\])))                                                                                                                                 |
| Åldersfördelning lagerinleveranser i framtiden  | BERÄKNA (\[lagrets Nettoförändring\], 'Transaktioner uttrycket'\[belopp\]&gt; 0, FILTER (ALLEXCEPT ('Räkenskapskalendrar', 'Räkenskapskalendrar'\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]), 'Räkenskapskalendrar'\[datum\]&gt; MAX ('Räkenskapskalendrar'\[datum\])))                                                                                                                                             |
| Lager Genomsnittlig enhetskostnad                 | BERÄKNA (\[lagrets slutsaldo\] / \[lagrets slutkvantiteten saldot\], ALLEXCEPT ('Räkenskapskalendrar', "Räkenskapskalendrar"\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Kundreskontra"\[valuta\], "Kundreskontra"\[beskrivning\], "Kundreskontra"\[namn\]))                                                                                                                                                                                                                 |
| Inköpsavvikelser                      | BERÄKNA (SUMMA (\[belopp\]), 'Poster uttrycket'\[kategorinamnet - nivå 2\_\] = "Procured", 'Uttrycket transaktioner'\[utdragstypen\] = "Avvikelse")                                                                                                                                                                                                                                                                                                                              |
| Startsaldot PIA                   | BERÄKNA (\[ingående balans\], 'Uttrycket transaktioner'\[utdragstypen\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                            |
| PIA-slutsaldo                      | BERÄKNA (\[slutsaldo\], 'Uttrycket transaktioner'\[utdragstypen\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                               |
| PIA-Nettoförändring                          | BERÄKNA (\[Nettoförändring\], 'Uttrycket transaktioner'\[utdragstypen\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                                   |
| PIA-Nettoförändring %                        | IF (\[PIA slutsaldo\] = 0, 0, \[Nettoförändring PIA-\] / \[PIA slutsaldo\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Produktionsavvikelser                    | BERÄKNA (SUMMA (\[belopp\]), 'Poster uttrycket'\[kategorinamnet - nivå 2\_\] = "ManufacturedCost", 'Uttrycket transaktioner'\[utdragstypen\] = "Avvikelse")                                                                                                                                                                                                                                                                                                                      |
| Kategorinamnet - nivå 1                 | Växla (\[kategorinamnet - nivå 1\_\], "Ingen", "Ingen", "NetSourcing" "Net ursprung", "NetUsage", "Net användning", "NetConversionCost", "Netto-konverteringskostnad", "NetCostOfGoodsManufactured", "Net kostnader för tillverkade varor", "BeginningBalance", "Ingående balans")                                                                                                                                                                                                         |
| Kategorinamnet - nivå 2                 | Växla (\[kategorinamnet - nivå 2\_\], "Ingen", "Ingen", "Procured", "Procured", "Disposed", "Disposed", "Överförd", "Överförd", "Såld", "Såld", "ConsumedMaterialsCost", "Förbrukning materialkostnaden", "ConsumedManufacturingCost", "Förbrukad kostnad tillverkning", "ConsumedOutsourcingCost", "Förbrukning entreprenad kostnad", "ConsumedIndirectCost", "Förbrukad indirekt kostnad", "ManufacturedCost", "Fabricerad kostnad", "Avvikelser", "Avvikelser")                            |
| Kategorinamnet - nivå 3                 | Växla (\[kategorinamnet - nivå 3\_\], "Ingen", "Ingen", "Inventering" "Ingen", "ProductionPriceVariance", "Produktionspris", "QuantityVariance", "Kvantitet", "SubstitutionVariance", "Ersättning", "ScrapVariance", "Kassation", "LotSizeVariance", "Partistorleken", "RevaluationVariance", "Omvärdering", "PurchasePriceVariance", "Inköpspris" "CostChangeVariance" "Kostnadsändringen", "RoundingVariance" "Avrundningsavvikelse")                                                   |

Skära totala måtten för att uppnå förbättrad säkerhetsadministration och ger en bättre förståelse för analytiska används följande viktiga dimensionerna som filter.

| Enhet           | Exempel på attribut                       |
|------------------|----------------------------------------------|
| Enheter         | ID, namn                                     |
| Räkenskapskalendrar | Kalender, månad, Period, kvartal, år       |
| KPI-mål        | Lagret är korrekt målet lager aktiverar mål |
| Redovisningar          | Valuta, namn, beskrivning                  |
| Platser            | ID, namn, land, ort                      |

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)



