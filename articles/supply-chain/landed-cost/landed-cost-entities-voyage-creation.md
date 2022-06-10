---
title: Enheter för skapandet av färd
description: I det här avsnittet finns information om hur du skapar dataenheter, som grupperar de dataenheter som krävs för att skapa en arbetsinformation.
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
ms.openlocfilehash: 17f63af3ce1f858ed3e2086fc81c5e17c5e76be0
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813133"
---
# <a name="voyage-creation-entities"></a>Enheter för skapandet av färd

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Enheter för skapandet av färd grupperar de dataenheter som krävs för att skapa en arbetsinformation. Du eller din fraktspeditör kan använda dessa dataenheter för att skapa poster för färd, fraktbehållare, folio och färdlinje som refererar till befintliga inköpsorder- eller överföringsorderrader.

## <a name="voyages-itmtableentity"></a>Färder (ITMTableEntity)

Denna utgör ett värde för inkommande varor och fungerar som kostnadsområde på den högsta nivån i Hemtagningskostnad. Den innehåller information på huvudnivå som har att göra med, om ursprungsporten och destinationsporten. Denna funktion stöds av entiteten `ITMTableEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Leveranssätt | ITMTable.DlvModeId | Nvarchar(10) | Nej | Nej |
| Mäklaren har informerats | ITMTable.ITMBrokerAdvised | DatumTid | Nej | Nej |
| Kundmöte | ITMTable.ITMCustomerAppointment | DatumTid | Nej | Nej |
| Levererad vid distributionslager | ITMTable.ITMDelAtWarehouse | DatumTid | Nej | Nej |
| Leveransinstruktioner | ITMTable.ITMDeliveryInstructions | DatumTid | Nej | Nej |
| Avresedatum | ITMTable.ITMDepartureDate | DatumTid | Nej | Nej |
| Varor som frisläppts | ITMTable.ITMGoodsReleased | DatumTid | Nej | Nej |
| Datum för lokal transport | ITMTable.ITMLocalTransportDate | DatumTid | Nej | Nej |
| Tid för lokal transport | ITMTable.ITMLocalTransportTime | Int | Nej | Nej |
| Skickad ursprunglig fraktsedel | ITMTable.ITMOriginalBOLSebt | DatumTid | Nej | Nej |
| Mottagna originaldokument | ITMTable.ITMOriginalDocsReceived | DatumTid | Nej | Nej |
| Status på inköpsorder | ITMTable.ITMPurchStatus | Int | Nej | Nej |
| Verifieringsdatum | ITMTable.ITMVerificationDate | DatumTid | Nej | Nej |
| Identifierare för tullpost | ITMTable.ShipCustomsEntryId | Nvarchar(20) | Nej | Nej |
| Transportdatum | ITMTable.ShipDate | DatumTid | Nej | Nej |
| Beskrivning | ITMTable.ShipDescription | Nvarchar(60) | Nej | Nej |
| Mottagna dokument | ITMTable.ShipDocReceived | Int | Nej | Nej |
| Uppskattat leveransdatum | ITMTable.ShipEstDlvDate | DatumTid | Nej | Nej |
| Beräknad ankomst vid leveranshamn | ITMTable.ShipEstPortDate | DatumTid | Nej | Nej |
| Från hamn | ITMTable.ShipFromPort | Nvarchar(20) | Nej | Nej |
| HAWB/fraktsedel | ITMTable.ShipHAWB | Nvarchar(20) | Nej | Nej |
| Sjötransport | ITMTable.ShipId | Nvarchar(20) | **Ja** | **Ja** |
| Bokningsreferens | ITMTable.ShipIdExternal | Nvarchar(20) | Nej | Nej |
| Resemall | ITMTable.ShipJourneyId | Nvarchar(20) | Nej | Nej |
| Lokal vidarebefordrare | ITMTable.ShipLocalForwarder | Nvarchar(20) | Nej | Nej |
| Huvud för flygfraktsedel/fraktsedel | ITMTable.ShipMAWB | Nvarchar(20) | Nej | Nej |
| Mått | ITMTable.ShipMeasurement | Numerisk(32, 6) | Nej | Nej |
| Måttenhet | ITMTable.ShipMeasurementUnit | Int | Nej | Nej |
| Antal lastpallar | ITMTable.ShipNoOfPallets | Int | Nej | Nej |
| Väntande sjötransport | ITMTable.ShipPending | Int | Nej | Nej |
| Kommentarer | ITMTable.ShipRemarks | Nvarchar(MAX) | Nej | Nej |
| Hyra | ITMTable.ShipRental | Int | Nej | Nej |
| Sjötransportens status | ITMTable.ShipStatusId | Nvarchar(20) | Nej | Nej |
| Märke i nummer | ITMTable.ShipTallyInNumber | Nvarchar(20) | Nej | Nej |
| Till hamn | ITMTable.ShipToPort | Nvarchar(20) | Nej | Nej |
| Värderingsdatum | ITMTable.ShipValuationDate | DatumTid | Nej | Nej |
| Speditör | ITMTable.ShipVendAccount | Nvarchar(20) | Nej | Nej |
| Fartyg | ITMTable.ShipVesselId | Nvarchar(20) | Nej | **Ja** |
| ID för extern sjötransport | ITMTable.ShipVoyage | Nvarchar(20) | Nej | Nej |

### <a name="number-sequences-for-voyages"></a>Antal sekvenser för färder

Den delade nummersekvensen för resor styr tilldelningen av rese-ID.

Det värde som överförs till dataenheten som värdet **färd-ID** (`ShipId`) används för att identifiera en befintlig post för uppdatering. Om den posten inte finns beror beteendet på om den tilldelade nummerserien är konfigurerad för manuell inmatning:

- Om manuell inmatning aktiveras skapas en ny post med det godkända värdet.
- Om manuell inmatning inte är aktiverad används nästa nummer i den tilldelade nummerserien istället för det godkända värdet.

Under importsessionen sparas det platshållarvärde som importeras när ID:t sparas. Detta beteende säkerställer att leveransbehållare och rader som refererar till platshållaren tas med i programmet och att de uppdateras för att återspegla det värde som har tilldelats från nummerserien.

### <a name="automatic-cost-transactions"></a>Automatiska kostnadstransaktioner

Automatiska kostnader kan läggas till i en färd från sidan **Automatiska kostnader** i Microsoft Dynamics 365 Supply Chain Management (**Hemtagningskostnad \> Inställningar för kostnadsredovisning \> Automatiska kostnader**). Poster för automatiska kostnader kan också skapas med hjälp av dataenheter för kostnadstransaktion för varje kostnadsområde som Hemtagningskostnad stöder.

Automatiska kostnader som konfigureras i Supply Chain Management tillämpas på raden när en rad skapas. Inga kostnader visas mot posten förrän rubrikposten är kopplad till radinformationen.

## <a name="shipping-containers-itmcontainersentity"></a>Fraktcontainrar (ITMContainersEntity)

En fraktbehållare representerar en fysisk behållare som gods transporteras i. Denna fysiska behållare kan vara en fraktbehållare för sjöfrakt eller en enkel lastpall för flygfrakt. Leveransbehållaren innehåller information på huvudnivå som är relaterad till leveransbehållare-ID, plomberingsnummer och leveransbehållaretyp. (Containertypen för försändelse innehåller dimensionsinformation.) Den här funktionen stöds av `ITMContainersEntity` enheten. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Avresedatum | ITMContainers.ITMDepartureDate | DatumTid | Nej | Nej |
| Datum för lokal transport | ITMContainers.ITMLocalTransportDate | DatumTid | Nej | Nej |
| Tid för lokal transport | ITMContainers.ITMLocalTransportTime | Int | Nej | Nej |
| Ursprunglig sjötransport | ITMContainers.OrigShipId | Nvarchar(20) | Nej | Nej |
| Faktisk vikt | ITMContainers.ShipActualWeight | Numerisk(32, 6) | Nej | Nej |
| Mäklaren har informerats | ITMContainers.ShipBrokerAdvised | DatumTid | Nej | Nej |
| Fraktcontainer | ITMContainers.ShipContainerId | Nvarchar(20) | **Ja** | **Ja** |
| Typ av fraktcontainer | ITMContainers.ShipContainerTypeId | Nvarchar(20) | Nej | Nej |
| Enhetstyp | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | Nej | Nej |
| Konverterad till hyrd | ITMContainers.ShipConvertedToRental | Int | Nej | Nej |
| Kundmöte | ITMContainers.ShipCustomerAppointment | DatumTid | Nej | Nej |
| Transportdatum | ITMContainers.ShipDate | DatumTid | Nej | Nej |
| Levererad vid distributionslager | ITMContainers.ShipDelAtWarehouse | DatumTid | Nej | Nej |
| Leveransinstruktioner | ITMContainers.ShipDeliveryInstructions | DatumTid | Nej | Nej |
| Kontrollintyg tillämpat den | ITMContainers.ShipECAppliedDate | DatumTid | Nej | Nej |
| Utgångsdatum för kontrollintyg | ITMContainers.ShipECExpiryDate | DatumTid | Nej | Nej |
| Nummer på kontrollintyg | ITMContainers.ShipECNum | Nvarchar(20) | Nej | Nej |
| Mottagningsdatum för kontrollintyg | ITMContainers.ShipECReceivedDate | DatumTid | Nej | Nej |
| Uppskattat leveransdatum | ITMContainers.ShipEstDlvDate | DatumTid | Nej | Nej |
| Beräknad ankomst vid leveranshamn | ITMContainers.ShipEstPortDate | DatumTid | Nej | Nej |
| Förväntat lastningsdatum | ITMContainers.ShipExpectedLoadingDate | DatumTid | Nej | Nej |
| Från hamn | ITMContainers.ShipFromPort | Nvarchar(20) | Nej | Nej |
| Beskrivning av varor | ITMContainers.ShipGoodsDesc | Nvarchar(60) | Nej | Nej |
| Varor som frisläppts | ITMContainers.ShipGoodsReleased | DatumTid | Nej | Nej |
| Enhet för GPS-spåraren | ITMContainers.ShipGPSUnit | Nvarchar(30) | Nej | Nej |
| HAWB/fraktsedel | ITMContainers.ShipHAWB | Nvarchar(20) | Nej | Nej |
| Sjötransport | ITMContainers.ShipId | Nvarchar(20) | **Ja** | **Ja** |
| Resemall | ITMContainers.ShipJourneyId | Nvarchar(20) | Nej | Nej |
| Lokal vidarebefordrare | ITMContainers.ShipLocalForwarder | Nvarchar(20) | Nej | Nej |
| Mått | ITMContainers.ShipMeasurement | Numerisk(32, 6) | Nej | Nej |
| Måttenhet | ITMContainers.ShipMeasurementUnit | Int | Nej | Nej |
| Antal kartonger | ITMContainers.ShipNoOfCartons | Numerisk(32, 6) | Nej | Nej |
| Skickad ursprunglig fraktsedel | ITMContainers.ShipOriginalBOLSebt | DatumTid | Nej | Nej |
| Mottagna originaldokument | ITMContainers.ShipOriginalDocsReceived | DatumTid | Nej | Nej |
| Vårt plomberingsnummer | ITMContainers.ShipOurSealNum | Nvarchar(20) | Nej | Nej |
| Används | ITMContainers.ShipPendingUsed | Int | Nej | Nej |
| Status på inköpsorder | ITMContainers.ShipPurchStatus | Int | Nej | Nej |
| Kylningstyp | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | Nej | Nej |
| Kommentarer | ITMContainers.ShipRemarks | Nvarchar(MAX) | Nej | Nej |
| Hyra | ITMContainers.ShipRental | Int | Nej | Nej |
| Returnerbara | ITMContainers.ShipReturnable | Int | Nej | Nej |
| Sjötransportens status | ITMContainers.ShipStatusId | Nvarchar(20) | Nej | Nej |
| Speditörens förseglingsnummer | ITMContainers.ShipTheirSealNum | Nvarchar(20) | Nej | Nej |
| Till hamn | ITMContainers.ShipToPort | Nvarchar(20) | Nej | Nej |
| Verifieringsdatum | ITMContainers.ShipVerificationDate | DatumTid | Nej | Nej |
| Fartyg | ITMContainers.ShipVesselId | Nvarchar(20) | Nej | **Ja** |

### <a name="voyage-id-validation"></a>Validering av färd-ID

Container-ID:t som inte kontrolleras av en nummerserie. Den är unik endast i samband med färden som den används på.

Om entiteten fraktbehållare (`ITMContainersEntity`) används oberoende av entiteten färd (`ITMTableEntity`), värdet **Färd-ID** (`ShipId`) måste matcha en befintlig post i färdtabellen. I annat fall misslyckas importen.

Om entiteten för fraktbehållare (`ITMContainersEntity`) och entiteten för färd (`ITMTableEntity`) används som en del av samma importsession, måste entiteten för färd före skapandet av en fraktcontainer. Annars kan inte värdet för **Färd-ID** (`ShipId`) kan inte valideras. Om ett platshållarvärde används för värdet **Färd-ID** (`ShipId`) kan association skapas endast om samma platshållare används som värdet **Färd-ID** (`ShipId`) i entiteten fraktbehållare.

### <a name="other-field-validations"></a>Valideringar av andra fält

Följande tabell visar de fält i tabellen fraktbehållare (`ITMContainers`) som valideras mot register för Hemtagningskostnad. Här visas även dataentiteten Hemtagningskostnad som en frakttransportör kan använda för att läsa de befintliga värdena och se till att giltiga värden tas emot i din miljö.

| Fältet i tabellen ITMContainers | Dataentiteten för Hemtagningskostnad |
|---|---|
| Typ av fraktcontainer | ITMShippingContainerTypeEntity |
| Beskrivning av varor | ITMGoodsDescriptionEntity |
| Kylningstyp | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folios (ITMFolioEntity)

En folio motsvarar en gruppering av artiklar i en fraktbehållare för tulldeklarationer. Denna folio innehåller information på huvudnivå som är relaterad till tullmäklaren och en beskrivning av varorna. Denna funktion stöds av entiteten `ITMFolioEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Mäklaren har informerats | ITMFolioTable.ShipBrokerAdvised | DatumTid | Nej | Nej |
| Lastens kontrollnummer | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | Nej | Nej |
| Kundmöte | ITMFolioTable.ShipCustomerAppointment | DatumTid | Nej | Nej |
| Tullmäklare | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | Nej | Nej |
| Tull-ID | ITMFolioTable.ShipCustomsId | Nvarchar(60) | Nej | Nej |
| Företag | ITMFolioTable.ShipDataArea | Nvarchar(4) | Nej | **Ja** |
| Levererad vid distributionslager | ITMFolioTable.ShipDelAtWarehouse | DatumTid | Nej | Nej |
| Leveransinstruktioner | ITMFolioTable.ShipDeliveryInstructions | DatumTid | Nej | Nej |
| Mottagna dokument | ITMFolioTable.ShipDocReceived | Int | Nej | Nej |
| Uppskattat leveransdatum | ITMFolioTable.ShipEstDlvDate | DatumTid | Nej | Nej |
| Beräknad ankomst vid leveranshamn | ITMFolioTable.ShipEstPortDate | DatumTid | Nej | Nej |
| Exportör | ITMFolioTable.ShipExporterId | Nvarchar(20) | Nej | Nej |
| Namn | ITMFolioTable.ShipExporterName | Nvarchar(60) | Nej | Nej |
| Foliodatum | ITMFolioTable.ShipFolioDate | DatumTid | Nej | Nej |
| Folio | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Ja** | **Ja** |
| Från hamn | ITMFolioTable.ShipFromPort | Nvarchar(20) | Nej | Nej |
| Beskrivning av varor | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | Nej | Nej |
| Varor som frisläppts | ITMFolioTable.ShipGoodsReleased | DatumTid | Nej | Nej |
| HAWB/fraktsedel | ITMFolioTable.ShipHAWB | Nvarchar(20) | Nej | Nej |
| Sjötransport | ITMFolioTable.ShipId | Nvarchar(20) | Nej | **Ja** |
| Mått | ITMFolioTable.ShipMeasurement | Numerisk(32, 6) | Nej | Nej |
| Måttenhet | ITMFolioTable.ShipMeasurementUnit | Int | Nej | Nej |
| Antal kartonger | ITMFolioTable.ShipNoOfCartons | Numerisk(32, 6) | Nej | Nej |
| Skickad ursprunglig fraktsedel | ITMFolioTable.ShipOriginalBOLSebt | DatumTid | Nej | Nej |
| Mottagna originaldokument | ITMFolioTable.ShipOriginalDocsReceived | DatumTid | Nej | Nej |
| Status på inköpsorder | ITMFolioTable.ShipPurchStatus | Int | Nej | Nej |
| Kommentarer | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | Nej | Nej |
| Sjötransportens status | ITMFolioTable.ShipStatusId | Nvarchar(20) | Nej | Nej |
| Tariffkod | ITMFolioTable.ShipTariffCode | Nvarchar(10) | Nej | Nej |
| Till hamn | ITMFolioTable.ShipToPort | Nvarchar(20) | Nej | Nej |
| Värderingsdatum | ITMFolioTable.ShipValuationDate | DatumTid | Nej | Nej |
| Verifieringsdatum | ITMFolioTable.ShipVerificationDate | DatumTid | Nej | Nej |
| Leverantörskonto | ITMFolioTable.VendAccount | Nvarchar(20) | Nej | Nej |

### <a name="number-sequences-for-folios"></a>Nummerserier för folios

Nummersekvensen för folios styr tilldelningen av folio-ID:n.

Det värde som överförs till dataenheten som värdet **Folio-ID** (`FolioId`) används för att identifiera en befintlig post för uppdatering. Om den posten inte finns beror beteendet på om den tilldelade nummerserien är konfigurerad för manuell inmatning:

- Om manuell inmatning aktiveras skapas en ny post med det godkända värdet.
- Om manuell inmatning inte är aktiverad används nästa nummer i den tilldelade nummerserien istället för det godkända värdet.

Under importsessionen sparas det platshållarvärde som importeras när Folio-ID sparas. Detta beteende säkerställer att reselinjer som refererar till platshållaren är korrekt associerade och att de uppdateras för att återspegla det värde som har tilldelats från nummerserien.

### <a name="field-validations"></a>Fältvalideringar

Fältet **Beskrivning av varor** i registret folio (`ITMFolioTable`) valideras mot registret inställningar för Hemtagningskostnad med samma namn. En fraktspeditör kan använda `ITMGoodsDescriptionEntity` dataentiteten för Hemtagningskostnad för att läsa de befintliga värdena och se till att giltiga värden tas emot i din miljö.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Sjötransportrader för inköpsorder (ITMPurchaseLineEntity)

Sjötransportraden representerar en enda inköpsorderrad som ingår i den. Den här relationen upprättas genom fälten **Inköpsordernummer** och **Inköpsradnummer**. Sjötransportraden refererar till varje tidigare post som skapades för resan, fraktbehållaren och folio. Denna funktion stöds av entiteten `ITMPurchaseLineEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Valuta | ITMLine.CurrencyCode | Nvarchar(3) | Nej | Nej |
| Nettobelopp | ITMLine.LineAmountMST | Numerisk(32, 6) | Nej | Nej |
| Inköpsradnummer | ITMLine.RefRecId | Numerisk(32, 6) | **Ja** | Nej |
| Fraktcontainer | ITMLine.ShipContainerId | Int | Nej | Nej |
| Företag | ITMLine.ShipDataArea | Nvarchar(20) | **Ja** | Nej |
| Deklarerad kvantitet | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nej | Nej |
| Folio | ITMLine.ShipFolioId | Numerisk(32, 6) | Nej | Nej |
| Sjötransport | ITMLine.ShipId | Nvarchar(20) | **Ja** | Nej |
| Artikelnummer | ITMLine.ShipItemId | Nvarchar(20) | Nej | Nej |
| Mått | ITMLine.ShipMeasurement | Nvarchar(20) | Nej | Nej |
| Måttenhet | ITMLine.ShipMeasurementUnit | Numerisk(32, 6) | Nej | Nej |
| Antal kartonger | ITMLine.ShipNoOfCartons | Int | Nej | Nej |
| Plats | ITMLine.ShipPosition | Numerisk(32, 6) | Nej | Nej |
| Antal | ITMLine.ShipQty | Int | Nej | Nej |
| Inköpsordernummer | ITMLine.TransRefId | Numerisk(32, 6) | **Ja** | Nej |
| Enhet | ITMLine.UnitId | Int | Nej | Nej |
| Volym | ITMLine.Volume | Nvarchar(10) | Nej | Nej |
| Vikt | ITMLine.Weight | Numerisk(32, 6) | Nej | Nej |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Överföringsorderrader (ITMTransferLineEntity)

Sjötransportraden representerar en enda överföringsorderrad som ingår i den. Den här relationen upprättas genom fälten **Överföringsorderrad** och **Överföringsradnummer**. Sjötransportraden refererar till varje tidigare post som skapades för resan, fraktbehållaren och folio. Denna funktion stöds av entiteten `ITMTransferLineEntity`. I följande register visas de fält och mappningar som utgör den här enheten.

| Namn | Mappning | Datatyp | Nyckelord | Obligatoriskt |
|---|---|---|---|---|
| Valuta | ITMLine.CurrencyCode | Nvarchar(3) | Nej | Nej |
| Nettobelopp | ITMLine.LineAmountMST | Numerisk(32, 6) | Nej | Nej |
| Fraktcontainer | ITMLine.ShipContainerId | Int | Nej | Nej |
| Företag | ITMLine.ShipDataArea | Nvarchar(20) | **Ja** | Nej |
| Deklarerad kvantitet | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nej | Nej |
| Folio | ITMLine.ShipFolioId | Numerisk(32, 6) | Nej | Nej |
| Sjötransport | ITMLine.ShipId | Nvarchar(20) | **Ja** | Nej |
| Artikelnummer | ITMLine.ShipItemId | Nvarchar(20) | Nej | Nej |
| Mått | ITMLine.ShipMeasurement | Nvarchar(20) | Nej | Nej |
| Måttenhet | ITMLine.ShipMeasurementUnit | Numerisk(32, 6) | Nej | Nej |
| Antal kartonger | ITMLine.ShipNoOfCartons | Int | Nej | Nej |
| Plats | ITMLine.ShipPosition | Numerisk(32, 6) | Nej | Nej |
| Antal | ITMLine.ShipQty | Int | Nej | Nej |
| Överföringsradnummer | ITMLine.TransferLineNumber | Numerisk(32, 6) | **Ja** | Nej |
| Nummer på överföringsorder | ITMLine.TransRefId | Numerisk(32, 6) | **Ja** | Nej |
| Enhet | ITMLine.UnitId | Int | Nej | Nej |
| Volym | ITMLine.Volume | Nvarchar(10) | Nej | Nej |
| Vikt | ITMLine.Weight | Numerisk(32, 6) | Nej | Nej |

### <a name="reference-table"></a>Referensregister

Sjötransportrader skapas genom en association med en öppen inkommande orderrad. Raden kan finnas på en inköpsorder eller också kan det vara in mottagningstransaktionen på en överföringsorder. Fältet `RefTableId` i radregistret (`ITMLine`) anger vilken ordertyp raden hör till genom att referera till registernumret. Om specifika registernummer refereras i registret där data skapas, delas enheterna in baserat på dessa värden.

Värdena för referenstabellen (`RefTableId`) och transaktionstypen (`TransType`) är implicita i valet av antingen enhet för inköpslinje för landade kostnader eller enhet för överföring av Hemtagningskostnad.

### <a name="validation"></a>Validering

En färdrad refererar direkt till en färdpost, en fraktcontainerpost och en foliopost. Om entiteten inköpsrad (`ITMPurchaseLinesEntity`) eller entiteten överföringsrad (`ITMPurchaseLinesEntity`) används oberoende av de enheter som används för att skapa dessa referensposter, måste värdena **Färd-ID** (`ShipId`), **Fraktcontainer** (`ShipContainerId`) och **Folio** (`ShipFolioId`) måste matcha en befintlig post i motsvarande tabeller. I annat fall misslyckas importen.

Om antingen radenheten används som en del av samma importsession, måste dessa andra enheter innan en sådan skapas. Annars kan värdena inte valideras. Om ett platshållarvärde används för resan eller folionumret, kan föreningen skapas endast om samma platshållare används för resan eller folionumret i entiteten färdraden.

Om inköpsordern eller överföringsorderraden redan är tilldelad en befintlig rad, skapas inte den nya raden. Innan orderraden kan tilldelas en ny sjötransport måste den tas bort från sin nuvarande sjötransport.

### <a name="order-line-identification"></a>Identifiering av orderrad

Sjötransportrader refererar direkt till referensen **Post-ID** (`RefRecId`), **Lagerdimensions-ID** värden (`InventDimId`) och **Lagertransaktions-ID** (`InventTransId`). Dessa värden behöver inte längre inkluderas när dataenheten används. Istället måste nu orderradsnumret inkluderas. Tillsammans gör orderradsnumret och ordernumret det möjligt att identifiera vart och ett av dessa referensvärden.

### <a name="voyage-line-quantity"></a>Sjötransportrad, kvantitet

Eftersom en rad är direkt associerad med en orderrad, värde **kvantitet** (`ShipQty`) som skrivs in med hjälp av entiteten kräver att värdena matchar. Valideringen körs mot kvantiteten på inköpsorderraden eller överföringsraden. Om valideringen misslyckas kommer posten inte att bearbetas.

### <a name="calculated-fields"></a>Beräknade fält

Fälten **Vikt** och **Volym** beräknade accepterar värdena som tas emot via dataenheten. Om inga värden anges används systemvärdena för att uppdatera fälten om systemvärden är tillgängliga. För Hemtagningskostnad beräknas värdena på följande sätt:

- *Vikt* = *Kvantitet* × *Bruttovikt artikel*
- *Volym* = *Kvantitet* × (*Bruttovikt artikel* × *Bruttohöjd artikel* × *Bruttovikt artikel*)

## <a name="sequencing"></a>Ordningsföljd

På grund av beroenden mellan registren måste den skapas först. Färdraden kan skapas först efter att färden, fraktbehållaren och folios har skapats.

Om du vill skapa en dator utan valideringsvarningar måste systemet bearbeta enheterna i följande ordning:

1. Sjötransporter (`ITMTableEntity`)
1. Fraktcontainrar (`ITMContainersEntity`)
1. Folios (`ITMFolioTableEntity`)
1. Sjötransportrader (`ITMPurchaseLinesEntity` eller `ITMTransferLinesEntity`)
