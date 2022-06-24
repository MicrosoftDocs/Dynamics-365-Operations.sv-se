---
title: Entiteter för kostnadstransaktioner
description: Denna artikel ger information om kostnadstransaktionsenheter, som gör det möjligt att dela upp värdet av en kostnad mellan innehållet i ett kostnadsområde genom att välja en fördelningsmetod.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 3aabc1356eba27de797fa696dd928cb401d8501b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860824"
---
# <a name="cost-transaction-entities"></a>Enheter för kostnadstransaktioner

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Fördelning

Med hemtagningskostnad kan värdet av en kostnad delas upp i innehållet i ett kostnadsområde (leveransbehållare och så vidare) genom att använda en fördelningsmetoden. Fördelningsmetoden ställs in som en del av konfigurationen av automatiska kostnader som baseras på affärsregler. Den dras igenom som en del av kostnaden när en färdrad skapas.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Konfigurera fördelningsmappning för användning med dataenheter

När en kostnad skapas från en extern källa, till exempel en fraktspeditör, kan den externa källan inte ange den metod som föredras för kostnadsvärdet. I mappningen definieras standardmetoden för fördelning av kostnadstyper för respektive kostnadstypkod. Tabellen för fördelningsmappning från sidan **Fördelningsmappning** i Microsoft Dynamics 365 Supply Chain Management (**Hemtagningskostnad \> Inställningar för kostnadsredovisning \> Fördelningsmappning**).

Om en mappningskombination har definierats och en kostnad som matchar kostnadstypskoden skapas genom att använda en kostnadstransaktionsenhet, kommer den mappade fördelningsmetoden att användas istället för alla värden som har tillhandahållits till enheten.

Om det inte finns något värde i mappningsregistret, men enheten har ett värde, används det angivna värdet.

Om det inte finns något värde i mappningsregistret eller posten som har skickats till enheten kommer skapandet att misslyckas.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Fördelningsmappning (ITMApportionmentMapping)

Enheten för fördelningsmappning (`ITMApportionmentMapping`) skapar relationer för fördelningsmappning och gör det möjligt för användarna att skapa eller uppdatera poster.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Fördelningsmetod | ITMApportionmentMapping.ApportionmentMethod | Int | Nej | Nej |
| Kod för kostnadstyp | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Ja** | Nej |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Kostnader för sjötransport (ITMCostTransVoyageEntity)

Entiteten sjötransportkostnad (`ITMCostTransVoyageEntity`) skapar kostnadstransaktioner för sjötransport som tillämpas på färdnivå. Under importprocessen använder systemet värdena **Kategori** och **Fördelningsmetod** som ingår i företaget för att fastställa hur värdet av kostnaden fördelas över resans innehåll.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Fördelningsmetod | ITMCostTrans.ApportionmentMethod | Int | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Sjötransport | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Kostnader för fraktcontainer (ITMCostTransShippingContainerEntity)

Entiteten för kostnad för fraktcontainer (`ITMCostTransShippingContainerEntity`) skapar kostnader för fraktbehållare som används på nivån för fraktbehållare. Under importprocessen använder systemet värdena **Kategori** och **Fördelningsmetod** som ingår i företaget för att fastställa hur värdet av kostnaden fördelas över fraktcontainerns innehåll.

Fälten **Aggregera**, **Etapp** och **Länkad etapp** är specifika för poster där värdet **Kostnadsområde** är *Fraktcontainer*. Därför finns de inte i dataenheter för andra kostnadsområden.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Sammansättning | ITMCostTrans.AggregatedCost | Int | Nej | Nej |
| Fördelningsmetod | ITMCostTrans.ApportionmentMethod | Int | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Länkad etapp | ITMCostTrans.LinkLegId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Fraktcontainer | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Sjötransport | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Etapp | ITMCostTrans.ShipLegId | Nvarchar(20) | Nej | Nej |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |

## <a name="folio-costs-itmcosttransfolioentity"></a>Foliokostnader (ITMCostTransFolioEntity)

Entiteten foliokostnad (`ITMCostTransFolioEntity`) skapar kostnadstransaktionsposter som gäller för folionivån. Under importprocessen använder systemet värdena **Kategori** och **Fördelningsmetod** som ingår i företaget för att fastställa hur värdet av kostnaden fördelas över innehållet för varje folio.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Fördelningsmetod | ITMCostTrans.ApportionmentMethod | Int | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Folio | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Inköpsorderkostnader (ITMCostTransPurchaseEntity)

Entiteten inköpsorderkostnad (`ITMCostTransPurchaseEntity`) skapar kostnadstransaktioner som gäller för inköparorderrubriken. Under importprocessen använder systemet värdena **Kategori** och **Fördelningsmetod** som ingår i företaget för att fastställa hur värdet av kostnaden fördelas över innehållet för varje folio.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Fördelningsmetod | ITMCostTrans.ApportionmentMethod | Int | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Inköpsorder | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |

## <a name="item-costs-itmcosttransitementity"></a>Artikelkostnader (ITMCostTransItemEntity)

Entiteten artikelkostnad (`ITMCostTransItemEntity`) skapar kostnadstransaktioner som gäller för artikelnivån. Den här enheten är specifik för artiklar på inköpsorderrader. Kostnadsvärdet används fullständigt på raden.

Fälten **Justeringsbelopp** och **Värdejustering** är specifika för kostnadsområdena på radnivå. Därför finns de inte i dataenheter för andra kostnadsområden.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Justeringsbelopp | ITMCostTrans.AdjustmentAmount | Numerisk(32, 6) | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Inköpsorder | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Inköpsorderradnummer | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |
| Värdejustering | ITMCostTrans.ValueAdjustmentMethod | Int | Nej | Nej |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Överför radkostnader (ITMCostTransTransferLineEntity)

Entiteten överföringsradskostnad (`ITMCostTransTransferLineEntity`) skapar kostnadstransaktioner som gäller för nivån för överföringsorderraden. Värdet av dessa kostnader appliceras i sin helhet på överföringsorderraden.

Fälten **Justeringsbelopp** och **Värdejustering** är specifika för kostnadsområdena på radnivå. Därför finns de inte i dataenheter för andra kostnadsområden.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Justeringsbelopp | ITMCostTrans.AdjustmentAmount | Numerisk(32, 6) | Nej | Nej |
| Kostnadsvärde | ITMCostTrans.CostValue | Numerisk(32, 6) | Nej | Nej |
| Valuta | ITMCostTrans.CurrencyCode | Nvarchar(3) | Nej | **Ja** |
| Radnummer | ITMCostTrans.LineNum | Numerisk(32, 16) | **Ja** | Nej |
| Länkad kostnadstyp | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Nej | Nej |
| Minimikostnad | ITMCostTrans.MinCostAmount | Numerisk(32, 6) | Nej | Nej |
| Kategori | ITMCostTrans.ShipCostCategory | Int | Nej | Nej |
| Kod för kostnadstyp | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Nej | Nej |
| Företag | ITMCostTrans.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Överföringsorder | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Överföringsorderradsnummer | ITMCostTrans.TransRecId | Nvarchar(20) | **Ja** | Nej |
| Artikelmomsgrupp | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Nej | Nej |
| Värdejustering | ITMCostTrans.ValueAdjustmentMethod | Int | Nej | Nej |

### <a name="transaction-table"></a>Transaktionsregister

En kostnadstransaktionspost associeras till ett kostnadsområde genom tilldelning av ett transaktionsregisternummer (`TransTableId`). När specifika register-ID-nummer krävs delas enheterna upp baserat på dessa värden, så att det finns en enhet för varje kostnadsområde.

Värdet för transaktionsregistret (`TransTableId`) är det samma som i valet av kostnadstransaktionsenhet.

### <a name="calculated-fields"></a>Beräknade fält

Följande fält är inte tillgängliga för att infoga eller uppdatera när en kostnadstransaktionsenhet används, eftersom dessa fält endast ställs in när specifika åtgärder vidtas mot färdposten:

- **Uppskattad kostnad** – Detta fält ställs in när en faktura bokförs för inköpsordern eller när en överföring tas emot.
- **Uppskattad kostnadsvaluta** – Detta fält ställs in när en faktura bokförs för inköpsordern eller när en överföring tas emot.
- **Faktisk kostnad** – Detta fält ställs in när en leverantörsfaktura bokförs. Det är kopplat till kostnaden.

### <a name="find-auto-costs"></a>Sök efter automatiska kostnader

Med knappen **Sök efter automatiska kostnader** som är tillgänglig för varje kostnadsområde (fraktbehållare och så vidare) kan du uppdatera kostnadstransaktionerna för detta kostnadsområde från informationen i konfigurationsregistren. När du väljer knappen för ett kostnadsområde rensar systemet befintliga kostnader för det kostnadsområdet och skapar nya poster baserat på den aktuella konfigurationen för tabell för inställningen av automatisk kostnad.

Kostnadstransaktionsposter som skapas med hjälp av en dataenhet flaggas som importerade. Dessa poster tas inte bort när du väljer **Sök efter automatiska kostnader**, eftersom de inte skapas på samma sätt från de automatiska kostnadsinställningarna. En kostnadstransaktionspost som flaggas som importerad kan ändå tas bort.

### <a name="linked-fields"></a>Länkade fält

Varje kostnadstransaktion kan associeras med en annan post i samma kostnadsområde. Denna koppling upprättas i fältet **Länkad kostnadstyp**. Det gör att ett kostnadsvärde kan beräknas som en procentsats av en annan kostnad.

Fältet **Länkad kostnadstyp** kan endast valideras om posten som refereras bearbetas först, eller om den redan finns i registret. Samma krav gäller i fältet **Länkad etapp** som endast används för kostnader i kostnadsområdet för fraktbehållare.
