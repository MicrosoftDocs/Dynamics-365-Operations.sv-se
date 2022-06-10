---
title: Entiteter för leverantörsfaktura
description: Det här ämnet ger information om leverantörsfakturaenheter, som gör det möjligt att konfigurera kostnadstypkoder för interna eller externt härledda kostnader.
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
ms.openlocfilehash: 4bbe0fdbf95050ebfa707224f602e5e71ddb3a8f
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813138"
---
# <a name="vendor-invoice-entities"></a>Entiteter för leverantörsfaktura

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Med modulen **Hemtagningskostnad** kan kostnadstypskoder konfigureras för interna kostnader eller externa härledda kostnader. Om en kostnad är extern för ett företag, förväntas en faktura från serviceprovidern. Denna faktura bearbetas som en fakturajournal som kan associeras med ett s.ex. och värdet på fakturan kan fördelas på en eller flera kostnader för avbetalningen.

Med hjälp av leverantörsfakturaenheterna kan värdet på en journalrad fördelas över en eller flera kostnader för en kund som har samma kostnadstypkod.

En kostnad kan bara tilldelas om fakturajournalhuvudet och fakturajournalraderna finns.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Kostnadsallokeringar för leverantörsfärd (ITMLedgerJournalCostLinesVoyagesEntity)

Dataenheten kostnadsallokeringar för leverantörsfärd gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i leverantörskostnadsområdet. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesVoyagesEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |
| Sjötransport | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Leverantörens allokeringar för fraktcontainerkostnad (ITMLedgerJournalCostLinesContainersEntity)

Dataenheten kostnadsallokeringar för leverantörens fraktcontainer gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i fraktbehållarens kostnadsområdet. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesContainersEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Fraktcontainer | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |
| Sjötransport | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Kostnadsallokeringar för leverantörsfolio (ITMLedgerJournalCostLinesFoliosEntity)

Dataenheten kostnadsallokeringar för leverantörsfolio gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i folio kostnadsområdet. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesFoliosEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Folio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Kostnadsallokeringar för leverantörsinköpsorder (ITMLedgerJournalCostLinesPurchTableEntity)

Dataenheten kostnadsallokeringar för inköpsorder gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i inköpsorderns kostnadsområde. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesPurchTableEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |
| Inköpsorder | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Kostnadsallokeringar för leverantörsartikel (ITMLedgerJournalCostLinesPurchLineEntity)

Dataenheten kostnadsallokeringar för leverantörsartikel gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i artikelns kostnadsområde. Artikelkostnadsområdet omfattar kostnader på inköpsorderraden. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesPurchLineEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |
| Inköpsorder | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |
| Inköpsorderradnummer | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Allokering av radkostnadsallokeringar för leverantörsöverföringar (ITMLedgerJournalCostLinesTransferLineEntity)

Dataenheten kostnadsallokeringar för överföringsorderraden gör det möjligt att allokera en leverantörsfakturarad över en eller flera kostnader som används i överföringsradens kostnadsområde. Denna funktion stöds av entiteten `ITMLedgerJournalCostLinesTransferLineEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Tilldelat belopp | ITMLedgerJournalCostLines.Amount | Numerisk(32, 6) | Nej | Nej |
| Radnummer för kostnadstransaktion | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalradnummer | ITMLedgerJournalCostLines.RefRecId | Numerisk(32, 16) | **Ja** | Nej |
| Journalnummer | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Ja** | Nej |
| Överföringsorder | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Ja** | Nej |
| Överföringsorderradsnummer | ITMLedgerJournalCostLines.CostTransRefRecId | Numerisk(32, 16) | **Ja** | Nej |

### <a name="reference-table"></a>Referensregister

Rader för sjötransportkostnad har en direkt koppling till en kostnadstransaktionspost. Den här posten innehåller värdet **referensregister-ID**. Det här värdet är unikt för varje kostnadsområde (färd, leveransbehållare och så vidare). När specifika registernummer refereras till för data som skapas med hjälp av datatabeller, delas enheterna upp baserat på värden för **referensregister-ID**.

Värdena för referenstabellen (`RefTableId`) och transaktionstypen (`TransType`) är implicita i valet av antingen enhet för inköpslinje för landade kostnader eller överföring av Hemtagningskostnad.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Leverantörsfakturajournalens rader (VendorInvoiceJournalLineEntity)

Innan ett journalradvärde kan allokeras till en eller flera kostnader i modulen **Hemtagningskostnad** måste journalraden vara kopplad till ett kostnadsområde. Som ett stöd för dessa funktioner lägger modulen **Hemtagningskostnad** till nya fält i journalradsregistret (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Fält som läggs till leverantörens fakturajournalradenhet

I följande register visas de fält som modulen **Hemtagningskostnad** lägger till i leverantörens fakturajournalradenhet (`VendorInvoiceJournalLineEntity`). Med hjälp av dessa fält kan journalrader skapas och kostnader fördelas mot dem.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Kostnadsområde | LedgerJournalTrans.ITMCostArea | Int | Nej | Nej |
| Kod för kostnadstyp | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | Nej | Nej |

### <a name="mainoffset-account"></a>Huvud/motkonto

Huvud/motkontot för en fakturajournalrad som är associerad med en Hemtagningskostnad avgörs av kostnadstypens kod. När kostnadstypskoden är inkluderad på fakturajournalraden används clearingkontot för koden som huvudkonto eller motkonto, beroende på scenariot:

- **Enradsjournal** – Om ett huvudkonto (med andra ord leverantörskontot) är definierat och en kostnadstypskod tillhandahålls, kommer clearingkontovärdet för den kostnadstypkoden att anges på motkontot.
- **Flerradsjournal** – Om ett huvudkonto inte är definierat men en kostnadstypskod tillhandahålls, kommer clearingkontovärdet för den kostnadstypkoden att anges på huvudkontot. Journalraden som krediterar leverantören refererar inte till någon kostnadstypkod.

## <a name="sequencing"></a>Ordningsföljd

På grund av beroenden mellan registren för journal och journalrader måste den skapas först. Färdraderna kan skapas först efter att färden, fraktbehållaren och folios har skapats.

För att tilldela en resa faktura, systemet måste systemet bearbeta enheterna i följande ordning:

1. Journalhuvud för faktura (`VendInvoiceJournalHeaderEntity`)
1. Fakturajournalsrad (`VendInvoiceJournalLineEntity`)
1. Allokeringar av hemtagningskostnad (`ITMLedgerJournalEntities`)
