---
title: Inköps- och utgiftsanalys för Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet Inköps- och utgiftsanalys.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a40d4f39a7119def9ed0393d4ced2be1f7e801a5c1c3f984b002e5224299915a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716122"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Inköps- och utgiftsanalys för Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i **Inköps- och utgiftsanalys** Microsoft Power BI-innehåll. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet **Inköps- och utgiftsanalys** har utvecklats för att inköpschefer och chefer som ansvarar för budgetar ska kunna hålla koll på köputgifterna. Chefer kan analysera inköpsutgifter på följande sätt:

- Ackumulerat inköp för i år (efter leverantörsgrupp och enskilda leverantörer, anskaffningskategori och enskilda produkter samt leverantörens plats)
- Inköpsförändring på årsbasis (efter leverantörsgrupp och upphandlingskategori)

Innehållet använder inköpstransaktionsdata och ger både en sammanfattning av de företagsomspännande inköpsuppgifterna och en fördelning av inköpsutgifter efter leverantör och produkt. Rapporter visar ändringar i inköpsutgifter över tiden. Rapporterna kan därför användas för att uppmärksamma chefer på positiva och negativa utgiftstrender för enskilda leverantörer och produkter. Diagram visar dessutom inköpsutgifter för olika anskaffningskategorier och leverantörsgrupper. Kategorichefer och regionala chefer kan använda diagrammen för att identifiera ändringar i utgiftsbeteende.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll
**Analys av inköpsutgift** Power BI-innehåll visas på sidan **Analys av inköp och utgifter** (**Anskaffning och källa** \> **Förfrågningar och rapporter** \> **Analys av köpprestanda** \> **Analys av inköp och utgifter**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mätvärden som ingår i Power BI-innehållet
Power BI-innehåll för **analys av inköpsutgift** innehåller en rapport som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. 

Nedanstående avsnitt ger en översikt över visualiseringarna.

### <a name="purchase-by-vendor-report-page"></a>Sidan inköp per leverantörrapport
**Diagram**
- De 10 främsta leverantörerna per inköp (stapeldiagram)
- Totalt inköp per leverantörsgrupp / land / namn (cirkeldiagram)
- Inköp per leverantörsgrupp / land / namn (stapeldiagram)
- Genomsnittligt inköp per leverantörsgrupp / land / namn (stapeldiagram)

**Paneler**
- Totalt inköp
- YOY inköpstillväxt
- Totalt antal leverantörer
- Totalt antal aktiva leverantörer

**Exempel**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Sidan produkt per leverantörrapport

**Diagram**
- Inköp per anskaffningskategori / produktnamn (stapeldiagram)
- Totalt inköp per anskaffningskategori / produktnamn (cirkeldiagram)
- De 10 främsta produkterna efter inköp (stapeldiagram)

**Paneler**
- Totalt antal produkter</li>
- Totalt antal aktiva produkters procentuella andel av totalt antal produkter
- Antal produkter som står för 80 % av inköp

**Exempel**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Sidan inköp per periodrapport
Den här sidan visar inköp i år och förra året och tillväxt efter upphandlingskategori.

**Diagram** 
- Inköp per månad / dag (stapeldiagram)
- Ackumulerad YOY inköpsavvikelse (vattenfallsdiagram)
- Totala YOY inköpstillväxt (stapeldiagram)
- Anskaffningsutdrag (matris)

**Paneler**
- YOY inköpstillväxt
- YOY inköpstillväxt %

**Exempel**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Sidan inköp per leverantörplatsrapport

**Diagram**
- Inköp per ort
- Inköp YOY tillväxt %
- Inköp per land

**Exempel**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Analys av inköpsutgift per tidsrapport

**Diagram** 
- Inköp innevarande år per månad / dag (linjediagram)
- Inköp innevarande år och föregående år (linje- och stapeldiagram)

**Exempel**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Analys av inköpsutgift per leverantörsrapport

**Diagram** 
- Topp 10 leverantörers inköp % av inköp (tratt)
- Topp 10 leverantörer med ökad utgifts YOY
- Topp 10 leverantörer med minskad utgifts YOY

**Exempel** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Datamodell och enheter
Följande data används för att fylla i rapportsidorna i Power BI-innehållet **Inköps- och utgiftsanalys**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Power BI-integrering med enhetsarkiv](power-bi-integration-entity-store.md).

De sammanlagda måtten i det här innehållspaketet är del av de sammanlagda mått som fanns i inköpskuben i Microsoft Dynamics AX 2012 och Microsoft Dynamics AX 2012 R3. För att förbereda kubens sammanlagda mått i Enhetslagring måste du göra dem driftfärdiga. Mer information finns i proceduren för mellanlagring av sammanlagda mått i Enhetslagring i [Power BI-integrering med Enhetslagring](power-bi-integration-entity-store.md). Följande sammanlagda huvudmått är tillgängliga direkt från fakturaradenheten och används som grund för innehållet.

| Enhet        | Sammanlagda huvudmått | Datakälla                                 | Fält              | beskrivning                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Fakturarader | Inköp                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Belopp i redovisningsvalutan. |

Följande tabell visar viktiga mått som beräknas i innehållet som beräknas från fakturaradenheten.

| Mått               | Beräkning                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Inköp innevarande år | Inköp innevarande år = SUM('Fakturarader'\[Inköp\])                                            |
| Inköp i fjol    | Inköp i fjol = CALCULATE(SUM('Fakturarader'\[Inköp\]), SAMEPERIODLASTYEAR(Datum\[Datum\])) |
| YOY inköpstillväxt   | YOY inköpstillväxt = \[Inköp innevarande år\] – \[Inköp i fjol\]                            |

Följande huvuddimensioner i innehållet används som filter för att dela upp de sammanlagda måtten så att du kan uppnå fler nivåer och få djupare analysinsikter.

| Enhet                 | Exempel på attribut                                |
|------------------------|-------------------------------------------------------|
| Leverantörer                | Leverantörsgrupper, leverantörers land eller regioner, leverantörsnamn |
| Produkter               | Produktnummer, produktnamn, artikelgruppsnamn        |
| Anskaffningskategorier | Anskaffningskategori, anskaffningskategorinamn      |
| Juridiska personer         | Namn på juridisk person                                     |
| Datum                  | Datum, Förskjutning för år                                    |

Som standard visar innehållet data för det aktuella kalenderåret. Du kan dock ändra filtret i datumavsnittet i rapportfilteravsnittet. Du kan också ändra filtret för företaget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]