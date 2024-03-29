---
title: Försäljnings- och lönsamhetsresultat Power BI-innehåll
description: Den här artikeln beskriver vad som ingår i Microsoft Power BI-innehållet Försäljnings- och lönsamhetsresultat.
author: Henrikan
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.form: SalesProfitabilityPerformancePowerBI
ms.openlocfilehash: 77271ad9f5a1d7c131e1d7750de280f0c70daaa4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274672"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Försäljnings- och lönsamhetsresultat Power BI-innehåll

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver vad som ingår i Microsoft **Försäljnings- och lönsamhetsresultat** Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

**Försäljnings- och lönsamhetsresultat** Power BI-innehåll skapades så att försäljningschefer kan övervaka viktiga försäljningsmått på omsättning, bruttovinst och vinstmarginaler. Den använder försäljningstransaktionsdata och ger både en sammanfattning av de företagsomspännande försäljningsuppgifterna och en fördelning av försäljningsprestanda för kunder och produkter.

Rapporterna visar ändringar i ökade intäkter och vinst över tid. De kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda kunder och produkter. Diagram jämför dessutom intäkt och lönsamhet för olika produktkategorier och kundgrupper med varandra. Därför kan kategori- och regionala chefer identifiera eftersläntrare och ledare. En sammanfattande rapport visar dessutom en kunds intäkter och vinstmarginal. Kontoansvariga kan därför ha säkerhetskopierade data som en grund. Dessa kan de använda för att finjustera sina insatser med försäljning och marknadsföringsförsök för varje kundprofil.

Innehållet **Försäljnings- och lönsamhetsresultat** låter försäljningsansvariga analysera försäljningsresultat på följande sätt:

- Intäkt, för innevarande år (efter kundgrupp och enskilda kunder, försäljningskategorier och enskilda produkter och områden)
- Ändring av intäkter, årsbasis (efter kundregion och försäljningskategori)

Lönsamhet kan analyseras på följande sätt:

- Bruttovinst och vinstmarginal (efter kundgrupper och produktförsäljningskategorier)
- Bruttovinständring, årsbasis
- Kundlönsamhet (efter intäkt jämfört med bruttomarginal)

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
**Försäljnings- och lönsamhetsprestanda** Power BI-innehåll visas på sidan **Försäljnings- och lönsamhetsprestanda** (**Försäljnings- och marknadsföring** \> **Förfrågningar och rapporter** \> **Analys av försäljningsprestanda** \> **Försäljnings- och lönsamhetsprestanda**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet
**Försäljnings- och lönsamhetsresultat** Power BI omfattar en rapport som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. Nedanstående tabell ger en översikt över de visualiseringar som används i innehållet.

| Rapportsida            | Diagram                                     | Paneler                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
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
Följande data används för att fylla i rapportsidorna **Försäljnings- och lönsamhetsresultat** Power BI-innehållet. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3. För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga. Mer information finns i proceduren för mellanlagring av sammanlagda mått i enhetsbutiken i blogginlägget [Power BI-integration med enhetsbutik i Dynamics](/archive/blogs/dynamicsaxbi/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update).

Följande huvudaggregatmått för fakturaradsenheter används som grund för innehållet:

| Enhet        | Sammanlagda huvudmått                   | Datakälla för Dynamics 365 | Fält                                        | beskrivning                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Fakturarader | Intäkt                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | Belopp i redovisningsvalutan.            |
|               | Kostnader för sålda varor                           | InventTrans                  | Summa (CostAmountPosted + CostAmountAdjustment) | Summan av kostnadsbeloppet och justeringen.    |
|               | Provisionsradbelopp – redovisningsvaluta | CustInvoiceTrans             | SUM(CommissAmountMST)                        | Provionsbeloppet i redovisningsvalutan. |

Följande tabell visar de sammanlagda mått för fakturaradenheten som används för att skapa flera beräknade mått i innehållets datauppsättning.

| Mått           | Beräkning                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Bruttovinst      | SUM(Intäkt – COGS – Provision – Moms (som ingår i radbelopp på kundfaktura))          |
| Bruttomarginal      | SUM(Bruttovinst – COGS – Provision – Moms (som ingår i radbelopp på kundfaktura))             |
| Intäkt ifjol | Intäkt ifjol = BERÄKNA(SUM('Fakturarader'\[intäkter\]), SAMMAPERIODSOMFÖRRAÅRET(datum\[datum\]) |

Följande tabell visar nyckeldimensionerna i försäljningskuben som används som filter för att dela upp de sammanlagda måtten så att du kan uppnå bättre nivåer och få djupare analysinsikter.

| Enhet           | Exempel på attribut                               |
|------------------|------------------------------------------------------|
| Kunder        | Kundgrupper, kundregioner, adress, bransch |
| Produkter         | Produktnummer, produktnamn, artikelgruppsnamn       |
| Försäljningskategorier | Namn på försäljningskategori                                 |
| Juridiska personer   | Namn på juridisk person                                   |
| Datum            | Datum                                                |

Som standard visar innehållet data för det aktuella kalenderåret. Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet. Du kan också ändra filtret för företaget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
