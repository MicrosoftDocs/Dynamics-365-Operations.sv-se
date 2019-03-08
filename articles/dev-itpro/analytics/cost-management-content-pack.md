---
title: Kostnadshantering Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kostnadshantering.
author: ShylaThompson
manager: AnnBe
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f67b1c901267bdf79c94e4f4c698c8731c515bb4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "327813"
---
# <a name="cost-management-power-bi-content"></a>Kostnadshantering Power BI-innehåll

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Microsoft Power BI-innehållet **Kostnadshantering** riktar sig till lagerredovisare eller personer i organisationen som är ansvarig för eller i intresserad av status för lager eller resurser i arbete (PIA) eller som är ansvarig för eller vill analysera standardkostnadsavvikelser.

> [!NOTE]
> **Kostnadshantering** Power BI-iinehåll som beskrivs i detta avsnitt gäller Dynamics 365 for Finance and Operations 8.0.
> 
> Power BI-innehållspaketet **Kostnadshantering** som finns tillgänglig på webbplatsen för AppSource har tagits bort. Mer information om denna borttagning finns i [Power BI innehållspaket finns på AppSource](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Detta Power BI-innehållet ger ett kategoriserat format som hjälper dig att övervaka prestanda för lager och visualisera hur kostnadsflödet går mellan dem. Du kan få ledarskapsinsikt som t.ex. omsättningshastighet, antalet dagar som lager finns, exakthet och ”ABC-klassificeringen” på din föredragna aggregerade nivå (företag, artikel, artikelgrupp eller site) Informationen som görs tillgänglig kan också användas som ett detaljerat komplement till bokslutet.

Power BI-innehåll bygger på de sammanlagda måtten **CostObjectStatementCacheMonthly** som har en **CostObjectStatementCache**-tabell som primär datakälla. Det här registret hanteras av cacheramverket Datauppsättning. Registret uppdateras var 24: e timme som standard, men du kan ändra uppdateringsfrekvensen eller aktivera manuella uppdateringar i konfigurationen av cachedatamängd. Manuella uppdateringar kan köras antingen i arbetsytan **Kostnadsredovisning** eller **Kostnadsanalys**.

Efter varje uppdatering av tabellen **CostObjectStatementCache** måste den sammanlagda mätningen **CostObjectStatementCacheMonthly** uppdateras innan data i Power BI-visualiseringarna uppdateras.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll

Power BI-innehållet **kostnadshantering** visas i arbetsytorna **Kostnadsredovisning** och **Kostnadsanalys**.

Arbetsytan **Kostnadsredovisning** innehåller följande flikar:

- **Översikt** – den här fliken visar programdata.
- **Lagrets redovisningsstatus** – den här fliken visar Power BI-innehåll.
- **Tillverkningens redovisningsstatus** – den här fliken visar Power BI-innehåll.

Arbetsytan **Kostnadsanalys** innehåller följande flikar:

- **Översikt** – den här fliken visar programdata.
- **Lagrets redovisningsanalys** – den här fliken visar Power BI-innehåll.
- **Tillverkningens redovisningsanalys** – den här fliken visar Power BI-innehåll.
- **Analys av standardkostnadsavvikelse** – den här fliken visar Power BI-innehåll.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Rapportsidor som ingår i Power BI-innehållet

Power BI-innehållet **Kostnadshantering** omfattar en uppsättning rapportsidor som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. 

Följande register ger en översikt över de visuella effekterna i Power BI-innehållet **Kostnadshantering**.

### <a name="inventory-accounting-status"></a>Status för lagerredovisning

| Rapportsida                               | Visualisering                                   |
|-------------------------------------------|-------------------------------------------------|
| Lager – översikt                        | Ingående saldo                               |
|                                           | Nettoändring                                      |
|                                           | Nettoändring %                                    |
|                                           | Slutsaldo                                  |
|                                           | Lagerprecision                              |
|                                           | Lageromsättningshastighet                        |
|                                           | Lagerbehållning räknat i dagar                          |
|                                           | Aktiv produkt i period                        |
|                                           | Aktiva kostnadsobjekt i period                   |
|                                           | Saldo per artikelgrupp                           |
|                                           | Saldo per plats                                 |
|                                           | Utdrag per kategori                           |
|                                           | Nettoändring per kvartal                           |
| Lager – Översikt per site- och artikelgrupp | Lagerprecision per site                      |
|                                           | Lageromsättningshastighet per site                |
|                                           | Avslutande lagersaldo per site                |
|                                           | Lagerprecision per artikelgrupp                |
|                                           | Lageromsättningshastighet per artikelgrupp          |
|                                           | Utgående lagersaldo per site eller artikelgrupp |
| Lagerutdrag                       | Lagerutdrag                             |
| Lagerutdrag per plats               | Lagerutdrag per plats                     |
| Lagerutdrag per produkthierarki  | Lagerutdrag                             |
| Lagerutdrag per produkthierarki  | Lagerutdrag per plats                     |

### <a name="manufacturing-accounting-status"></a>Status för tillverkningsredovisning

| Rapportsida                | Visualisering                       |
|----------------------------|-------------------------------------|
| WIP översikt YTD           | Ingående saldo                   |
|                            | Nettoändring                          |
|                            | Nettoändring %                        |
|                            | Slutsaldo                      |
|                            | PIA omsättningshastighet                  |
|                            | PIA räknat i dagar                    |
|                            | Aktiva kostnadsobjekt i period        |
|                            | Nettoändring per resursgrupp        |
|                            | Saldo per plats                     |
|                            | Utdrag per kategori               |
|                            | Nettoändring per kvartal               |
| PIA-utdrag              | Ingående saldo                   |
|                            | Slutsaldo                      |
|                            | PIA-utdrag per kategori           |
| PIA-utdrag per site      | Ingående saldo                   |
|                            | Slutsaldo                      |
|                            | PIA-utdrag per kategori och site  |
| PIA-utdrag per hierarki | Ingående saldo                   |
|                            | Slutsaldo                      |
|                            | PIA-utdrag per kategorihierarki |

### <a name="inventory-accounting-analysis"></a>Analys av lagerredovisning

| Rapportsida        | Visualisering                                                                |
|--------------------|------------------------------------------------------------------------------|
| Lagerdetaljer  | 10 högsta resurser efter utgående balans                                           |
|                    | 10 högsta resurser efter ökad nettoförändring                                      |
|                    | 10 högsta resurser efter minskad nettoförändring                                      |
|                    | 10 högsta resurser efter omsättningshastighet för lager                                 |
|                    | Resurser efter låg omsättningshastighet för lager och utgående balans över tröskelvärdet |
|                    | 10 högsta resurser efter sämre precision                                             |
| ABC-klassificering | Avslutande lagersaldo                                                     |
|                    | Förbrukat material                                                            |
|                    | Såld (COGS)                                                                  |
| Lager trender   | Avslutande lagersaldo                                                     |
|                    | Nettoändring av lagerstatus                                                         |
|                    | Lageromsättningshastighet                                                     |
|                    | Lagerprecision                                                           |

### <a name="manufacturing-accounting-analysis"></a>Analys av tillverkningsredovisning

| Rapportsida | Visualisering      |
|-------------|--------------------|
| PIA-trender  | Slutsaldo för PIA |
|             | Nettoändring för PIA     |
|             | PIA-omsättningshastighet |

### <a name="std-cost-variance-analysis"></a>Analys av standardkostnadsavvikelse

| Rapportsida                             | Visualisering                                        |
|-----------------------------------------|------------------------------------------------------|
| Inköpsprisavvikelse (standardkostnad) YTD | Upphandlat saldo                                     |
|                                         | Inköpsprisavvikelse                              |
|                                         | Inköpsprisavvikelseförhållande                        |
|                                         | Avvikelse per artikelgrupp                               |
|                                         | Avvikelse per site                                     |
|                                         | Inköpspris per kvartal                            |
|                                         | Inköpspris per kvartal och artikelgrupp             |
|                                         | 10 främsta resurser per ofördelaktigt inköpsprisförhållande |
|                                         | 10 främsta resurser per fördelaktigt inköpsprisförhållande   |
| Produktionsavvikelse (standardkostnad) YTD     | Tillverkningskostnad                                    |
|                                         | Produktionsavvikelse                                  |
|                                         | Produktionsavvikelseförhållande                            |
|                                         | Avvikelse per artikelgrupp                               |
|                                         | Avvikelse per site                                     |
|                                         | Produktionsavvikelse per kvartal                       |
|                                         | Produktionsavvikelse per kvartal och avvikelsetyp     |
|                                         | 10 främsta resurser per ofördelaktiga produktionsavvikelse  |
|                                         | 10 främsta resurser per fördelaktiga produktionsavvikelse    |

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Data från Microsoft Dynamics 365 for Finance and Operations används för att fylla i rapportsidorna i **Kostnadshantering** Power BI-innehåll. Informationen visas som sammansatta mått som mellanlagras i enhetsarkivet, som är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

Huvudaggregatmått för följande objekt ligger till grund för Power BI-innehållet.

| Objekt                          | Sammanlagda huvudmått | Datakällan för Finance and Operations | Fält               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Tid                     | CostObjectStatementCache               | Tid              |
| CostObjectStatementCacheMonthly | Kvantitet                   | CostObjectStatementCache               | Kvt                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

Nedan visas de viktigaste beräknade måtten i Power BI-innehållet.

| Mått                            | Beräkning |
|------------------------------------|-------------|
| Ingående saldo                  | Ingående saldo = \[Slutsaldo\]-\[Nettoförändring\] |
| Ingående saldokvantitet             | Ingående saldokvantitet = \[Slutsaldokvantitet\]-\[Nettoförändringskvantitet\] |
| Slutsaldo                     | Utgående saldo = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Slutsaldokvantitet                | Slutsaldokvantitet = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Nettoändring                         | Nettoändring = SUM(\[AMOUNT\]) |
| Nettoändringskvantitet                    | Nettoändringskvantitet = SUM(\[QTY\]) |
| Lageromsättningshastighet per belopp | Lageromsättningshastighet per belopp = if(OR(\[Genomsnittligt lagersaldo\] \<= 0, \[Sålt lager eller förbrukad utleverans\] \>= 0), 0, ABS(\[Sålt lager eller förbrukad utleverans\])/\[Genomsnittligt lagersaldo\]) |
| Genomsnittligt lagersaldo          | Genomsnittligt lagersaldo = ((\[Utgående saldo\] + \[Ingående saldo\]) / 2) |
| Lagerbehållning räknat i dagar             | Lagerbehållning räknat i dagar = 365 / CostObjectStatementEntries\[Lageromsättningshastighet per belopp\] |
| Lagerprecision                 | Lagerexakthet efter belopp = IF(\[Slutsaldo\] \<= 0, IF(OR(\[Inventerat lagerbelopp\] \<\> 0, \[Slutsaldo\] \< 0), 0, 1), MAX(0, (\[Slutsaldo\] - ABS(\[Inventerat lagerbelopp\]))/\[Slutsaldo\])) |

Följande tabell visar nyckeldimensionerna används som filter för att dela upp de sammanlagda måtten så att du kan uppnå bättre nivåer och få djupare analysinsikter.


| Enhet                                                  | Exempel på attribut                          |
|---------------------------------------------------------|-------------------------------------------------|
| Produkter                                                | Produktnummer, produktnamn, enhet, artikelgrupper |
| Kategorihierarkier (tilldelad rollen kostnadshantering) | Kategorihierarki, kategorinivå              |
| Juridiska personer                                          | Namn på juridisk person                              |
| Räkenskapskalendrar                                        | Räkenskapskalender, år, kvartal, period, månad   |
| Webbplats                                                    | ID, namn, adress, delstat, land               |
