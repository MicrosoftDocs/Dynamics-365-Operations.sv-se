---
title: "Innehåll i Power BI-kostnadshanteringen"
description: "Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kostnadshantering. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet."
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

# <a name="cost-management-power-bi-content"></a>Innehåll i Power BI-kostnadshanteringen

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kostnadshantering. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet.

# <a name="overview"></a>Översikt

Microsoft Power BI-innegållet **Kostnadshantering** riktar sig till lagerrevisorer eller personer inom organisationen med ansvar för lagret. Power BI-innehållet **Kostnadshantering** ger ledarskapsinblick i lager och PIA-lager (projekt i arbete), samt hur kostnadsflöden passerar genom dem per kategori och över tid. Informationen kan också användas som ett detaljerat komplement till bokslutet.

## <a name="key-measures"></a>Huvudmått

+ Ingående saldo
+ Slutsaldo
+ Nettoändring
+ Nettoändring i procent
+ Åldersfördelning

## <a name="key-performance-indicators"></a>Prestationsindikatorer
+ Lageromsättning
+ Lagerprecision

Den primära datakällan för CostAggregatedCostStatementEntryEntity är registret CostStatementCache. Det här registret hanteras av cacheramverket Datauppsättning. Registret uppdateras var 24: e timme som standard, men du kan aktivera manuella uppdateringar i cachkonfigurationen för data. Du kan sedan göra en manuell uppdatering i arbetsytan **Kostnadshantering** eller **Kostnadsanalys**. När uppdateringen av CostStatementCache har körts måste du uppdatera OData-anslutningen på Power BI.com för att visa uppdaterade data på webbplatsen. Avvikelseåtgärderna (inköp, produktion) i Power BI-innehållet gäller endast artiklar som bedömts av lagermetoden Standardkostnad. Produktionsavvikelsen beräknas som skillnaden mellan aktiv och verklig kostnad. Produktionsavvikelsen beräknas när produktionsordern har statusen **Avslutad**. Mer information om olika produktionsavvikelser och hur varje typ beräknas finns i [Analysera avvikelser för en avslutad tillverkningsorder](https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power Bi-innehållet **Kostnadshantering** är tillgängligt från PowerBI.com. Mer information om hur du ansluter och laddar dina Microsoft Dynamics 365 for Operations-data, se [Åtkomst till Power BI-innehåll från PowerBI.com](power-bi-home-page.md).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mått som ingår i Power BI-innehållet
Innehållet omfattar en uppsättning rapportsidor. Sidorna består av en uppsättning mått som visualiseras som diagram, brickor och tabeller. Följande register ger en översikt över de visuella effekterna i Power BI-innehållet **Kostnadshantering**.

| Rapportsida | Diagram | Titlar |
|---|---|---|
|Övergripande lager (standard efter aktuell period) |Precision |Lageråtgärder:<br>Avslutande lagersaldo<br>Nettoändring av lagerstatus<br>Nettoändring av lagerstatus i procent<br>|
| |Lageromsättning | |
| |Utgående lagersaldo efter resursgrupp | |
| |Lagrets nettoändring efter kategorinamn (nivå 1) och kategorinamn (nivå 2)| |
| |Inköpsavvikelser efter resursgrupp och kategorinamn (nivå 3) | |
|Lager efter plats (standard efter aktuell period) |Utgående lagersaldo efter platsnamn och resursgrupp | |
| |Lageromsättning efter platsnamn och resursgrupp | |
| |Utgående lagersaldo efter stad och resursgrupp | |
|Lager efter resursgrupp (standard efter aktuell period) |Lageråtgärder | |
| |Lagerexakthet efter belopp efter resursgrupp | |
| |Lageromsättning efter belopp efter resursgrupp | |
|Lager-YOY (standard för innevarande år kontra föregående år) |Lageråtgärder | |
| |Lager-KPI:er<br>Lageromsättning<br>Lagerprecision | |
| |Utgående lagersaldo efter år och resursgrupp | |
| |Inköpsavvikelser efter år och kategorinamn (nivå 3) | |
|Lagerföråldring (standard efter innevarande år) |Lagerföråldring efter kvartal och resursgrupp | |
| |Lagerföråldring efter kvartal och platsnamn | |
|Övergripande PIA (standard efter aktuell period) |Nettoändring för PIA efter kategorinamn (nivå 1) och kategorinamn (nivå 2) |PIA-åtgärder för pågående arbete:<br>Slutsaldo för PIA<br>Nettoändring för PIA<br>Nettoändring för PIA i procent<br> |
| |Produktionsavvikelser efter resursgrupp och kategorinamn (nivå 3) | |
| |Nettoändring för PIA per resursgrupp | |
|PIA efter plats (standard efter aktuell period) |PIA-åtgärder för pågående arbete | |
| |Nettoändring för PIA efter platsnamn och kategorinamn (nivå 2) | |
| |Produktionsavvikelser efter platsnamn och kategorinamn (nivå 3) | |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna
Dynamics 365 for Operations-data används för att fylla i rapportsidorna Power-Bi-innehållet **Kostnadshantering**. Informationen visas som sammansatta mått som mellanlagras i enhetsarkivet, som är en Microsoft SQL-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md). Följande sammanlagda huvudmått används till grund för innehållet:

| Enhet            | Sammanlagda huvudmått | Datakälla för Dynamics 365 for Operations | Fält             | beskrivning                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Utdragsposter | Nettoändring                | CostAggregatedCostStatementEntryEntity      | summa(\[Belopp\])   | Belopp i redovisningsvalutan |
| Utdragsposter | Kvantitet för nettoändring       | CostAggregatedCostStatementEntryEntity      | summa(\[Kvantitet\]) |                                   |

Följande tabell visar hur viktiga sammanlagda mått används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått                                 | Hur åtgärden beräknas                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ingående saldo                       | \[Utgående saldo\]-\[Nettoförändring\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Ingående saldokvantitet              | \[Slutsaldokvantitet\]-\[Nettoförändring kvantitet\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Slutsaldo                          | BERÄKNA(SUM (\[Belopp\]), FILTER(ALLEXCEPT ("Räkenskapskalendrar", "Räkenskapskalendrar"\[LedgerRecId\], "personer"\[ID\], "personer"\[Namn\], "Kundreskontra"\[Valuta\], "Kundreskontra"\[Beskrivning\], "Kundreskontra"\[Namn\]), "Räkenskapskalendrar"\[Datum\] &lt;= MAX ("Räkenskapskalendrar"\[Datum\])))                                                                                                                                                                                           |
| Slutsaldokvantitet                 | BERÄKNA(SUM (\[Kvantitet\]), FILTER(ALLEXCEPT ("Räkenskapskalendrar", "Räkenskapskalendrar"\[LedgerRecId\], "personer"\[ID\], "personer"\[Namn\], "Kundreskontra"\[Valuta\], "Kundreskontra"\[Beskrivning\], "Kundreskontra"\[Namn\]), "Räkenskapskalendrar"\[Datum\] &lt;= MAX ("Räkenskapskalendrar"\[Datum\])))                                                                                                                                                                                         |
| Ingående saldo för lager             | BERÄKNA(\[Ingående saldo\], "Utdragsposter"\[Utdragstyp\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                      |
| Avslutande lagersaldo                | BERÄKNA(\[Slutsaldo\], "Utdragsposter"\[Utdragstyp\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                         |
| Nettoändring av lagerstatus                    | BERÄKNA(\[Nettoändring\], "Utdragsposter"\[Utdragstyp\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                             |
| Nettoändring av lagerstatus (kvantitet)           | BERÄKNA(\[Nettoändringskvantitet\], "Utdragsposter"\[Utdragstyp\] = "Lager")                                                                                                                                                                                                                                                                                                                                                                                    |
| Nettoändring av lagerstatus i procent                  | OM(\[Slutsaldo för lager\] = 0, 0, \[Nettoförändring för lager\] / \[Lagrets slutsaldo\])                                                                                                                                                                                                                                                                                                                                                                           |
| Lageromsättning efter belopp                | Om(ELLER(\[Genomsnittligt lagersaldo\] &lt;= 0, \[Sålt lager eller förbrukad utleverans\] &gt;= 0), 0 ABS (\[Sålt lager eller förbrukad utleverans\]) /\[Genomsnittligt lagersaldo\])                                                                                                                                                                                                                                                                                                  |
| Genomsnittligt lagersaldo               | (\[Slutsaldo för lager\] + \[Startsaldo för lager\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sålt lager eller förbrukad utleverans       | \[Såldt lager\] + \[Förbrukad materialkostnad för lager\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Förbrukad materialkostnad för lager        | BERÄKNA(\[Nettoförändring för lager\], "Utdragsposter"\[Kategorinamn - nivå 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Sålt lager                          | BERÄKNA(\[Nettoförändring för lager\], "Utdragsposter"\[Kategorinamn - nivå 2\_\] = "Såld")                                                                                                                                                                                                                                                                                                                                                                             |
| Lagerexakthet efter belopp            | OM(\[Lagrets slutsaldo\] &lt;= 0, OM(ELLER(\[Inventerat lagerbelopp\] &lt;&gt; 0, \[Lagrets slutsaldo\] &lt; 0), 0, 1), MAX (0, (\[Lagrets slutsaldo\] -ABS (\[Inventerat lagerbelopp\])) /\[Lagrets slutsaldo\]))                                                                                                                                                                                                                              |
| Inventerat lagerbelopp                | BERÄKNA(\[Nettoförändring för lager\], "Utdragsposter"\[Kategorinamn - nivå 3\_\] = "Inventering")                                                                                                                                                                                                                                                                                                                                                                         |
| Lagerföråldring                         | Om(ÄRTOM(max("Räkenskapskalendrar"\[Datum\])), blank(), MAX(0, MIN (\[Kvantitet, lagerföråldring inleverans\], \[Kvantitet, lagerföråldring slutsaldo\] - \[Framtida kvantitet, lagerföråldring inleverans\]))) \* \[Lager, genomsn. enhetskostnad\]                                                                                                                                                                                                                                |
| Kvantitet, lageröråldring inleverans       | OM(\[minDate\] = \[minDateAllSelected\], BERÄKNA(\[Kvantitet, lagrets nettoförändring\], "Utsragsposter"\[Kvantitet\] &gt; 0, FILTER(ALLEXCEPT ('Räkenskapskalendrar", "Räkenskapskalendrar"\[LedgerRecId\], "personer"\[ID\], "personer"\[namn\], "Redovisning"\[valuta\], "Redovisning"\[beskrivning\], "Redovisning"\[namn\]), 'Räkenskapskalendrar'\[Datum\] &lt;= MAX("Räkenskapskalendrar"\[datum\]))), BERÄKNA (\[Kvantitet, lagrets nettoförändring\], "Utdragsposter"\[kvantitet\] &gt; 0)) |
| Slutsaldo, kvantitet för lagerföråldring | \[Slutsaldo för lagerkvantitet\] + BERÄKNA\[Nettosaldo för lagerkvantitet\], FILTER(ALLEXCEPT("Räkenskapskalendrar", "Räkenskapskalendrar"'\[LedgerRecId\], "Enheter"\[ID\], "enheter"\[Namn\], "Redovisning"\[Valuta\], "Redovisning"\[Beskrivning\], "Redovisning"\[Namn\]), "Räkenskapskalendrar"\[Datum\] &gt; max("Räkenskapskalendrar"\[Datum\]) ))                                                                                                                                 |
| Framtida lagerföråldring bland inleveranser  | BERÄKNA\[Nettoändring av lagerstatus\], "Utdragningsposter"\[Belopp\] &gt; 0, FILTER(ALLEXCEPT("Räkenskapskalendrar", "Räkenskapskalendrar"\[LedgerRecId\], "enheter"\[ID\], "enheter"\[Namn\], "Redovisning"\[Valuta\], "Redovisning"\[Beskrivning\], "Redovisning"\[Namn\]), "Räkenskapskalendrar"\[Datum\] &gt; MAX("Räkenskapskalendrar"\[Datum\])))                                                                                                                                             |
| Genomsnittlig enhetskostnad för lager                 | BERÄKNA\[Avslutande lagersaldo\] / \[Kvantitet, avslutande lagersaldo\],ALLEXCEPT("Räkenskapskalendrar", "Räkenskapskalendrar"\[LedgerRecId\], "enheter"\[ID\], "entities"\[Namn\], "Redovisning"\[Valuta\], "Redovisning"\[Beskrivning"\], "Redovisning"\[Namn\]))                                                                                                                                                                                                                 |
| Inköpsprisavvikelser                      | BERÄKNA(SUMMA(\[Belopp\]), "Utdragsposter"\[Kategorinamn - nivå 2\_\] = "Inköpt", "Utdragsposter"\[Utdragstyp\] = "Avvikelse")                                                                                                                                                                                                                                                                                                                              |
| Ingående saldo för PIA                   | BERÄKNA(\[Ingående saldo\], "Utdragsposter"\[Utdragstyp\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                            |
| Slutsaldo för PIA                      | BERÄKNA(\[Slutsaldo\], "Utdragsposter"\[Utdragstyp\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                               |
| Nettoändring för PIA                          | BERÄKNA(\[Nettoändring\], "Utdragsposter"\[Utdragstyp\] = "PIA")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Nettoändring för PIA i procent                        | OM(\[Slutsaldo för PIA\] = 0, 0, \[Nettoförändring för PIA-\] / \[Slutsaldo för PIA\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Produktionsavvikelser                    | BERÄKNA(SUMMA(\[Belopp\]), "Utdragsposter"\[Kategorinamn - nivå 2\_\] = "ManufacturedCost", "Utdragsposter"\[Utdragstyp\] = "Avvikelse")                                                                                                                                                                                                                                                                                                                      |
| Kategorinamn - nivå 1                 | växla(\[Kategorinamn - nivå 1\_\], "Ingen", "Ingen", "NetSourcing" "Nettoanskaffning", "NetUsage", "Nettoanvändning", "NetConversionCost", "Netto-konverteringskostnad", "NetCostOfGoodsManufactured", "Nettokostnad för tillverkade varor", "BeginningBalance", "Ingående balans")                                                                                                                                                                                                         |
| Kategorinamn - nivå 2                 | växla (\[Kategorinamn - nivå 2\_\], "Ingen", "Ingen", "Inköpt", "Inköpt", "Avyttrad", "Avyttrad", "Överförd", "Överförd", "Såld", "Såld", "ConsumedMaterialsCost", "Kostnad för förbrukade material", "ConsumedManufacturingCost", "Förbrukad tillverkningskostnad", "ConsumedOutsourcingCost", "Förbrukad outsourcingkostnad", "ConsumedIndirectCost", "Förbrukad indirekt kostnad", "ManufacturedCost", "Tillverkningskostnad", "Avvikelser", "Avvikelser")                            |
| Kategorinamn - nivå 3                 | växla(\[Kategorinamn - nivå 3\_\], "Ingen", "Ingen", "Inventering" "Ingen", "ProductionPriceVariance", "Produktionspris", "QuantityVariance", "Kvantitet", "SubstitutionVariance", "Ersättning", "ScrapVariance", "Kassation", "LotSizeVariance", "Partistorlek", "RevaluationVariance", "Omvärdering", "PurchasePriceVariance", "Inköpspris" "CostChangeVariance" "Kostnadsändring", "RoundingVariance" "Avrundningsavvikelse")                                                   |

Följande huvuddimensioner används som filter för att dela upp de sammanlagda måtten i syfte att uppnå en förbättrad nivå och ge djupare analysinsikter.

| Enhet           | Exempel på attribut                       |
|------------------|----------------------------------------------|
| Enheter         | ID, namn                                     |
| Räkenskapskalendrar | Kalender, månad, period, kvartal, år       |
| KPI-mål        | Mål för lagerexakthet, lageromsättningsmål |
| Redovisningar          | Valuta, namn, beskrivning                  |
| Platser            | ID, namn, land, ort                      |

## <a name="additional-resources"></a>Ytterligare resurser
Nedan följer några användbara länkar som är relaterade till enheter och till att skapa innehåll för Power BI:

-   [Datatabeller](..\data-entities\data-entities.md)
-   [Skapa innehållspaket för organisationer](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Datamodeller med hjälp av Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Lägga till Power BI-rutor till arbetsytor](configure-power-bi-integration.md)





