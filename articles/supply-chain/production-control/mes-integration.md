---
title: Integrera med tillverkningsutförandesystem från tredje part
description: I denna artikel beskrivs hur du kan integrera Microsoft Dynamics 365 Supply Chain Management med ett körningssystem från tredje part ("MES").
author: johanhoffmann
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8629ef2581a114609d14999a3c1fc48b49c988e0
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336228"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Integrera med tillverkningsutförandesystem från tredje part

[!include [banner](../includes/banner.md)]

Vissa tillverkningsorganisationer som använder Microsoft Dynamics 365 Supply Chain Management använder de ursprungliga funktionerna i Dynamics 365 för att styra sina tillverkningsaktiviteter för maskiner, utrustning och personal. Andra tillverkningsorganisationer, särskilt de som har avancerade tillverkningskrav, använder emellertid i stället ett utförandesystem från tredje part ("MES"). Organisationer kan välja en MES-lösning för tillverkningsutförande från tredje part eftersom den till exempel är skräddarsydd efter deras vertikalintegrerade bransch.

I den integrerade lösningen är datautbytet helt automatiserat och sker i närapå realtid. Därför hålls data uppdaterad i båda system, och manuell datainmatning krävs inte. När materialförbrukning registreras i MES säkerkonfigurerartegreringen till exempel att samma förbrukning också registreras i Dynamics 365. Därför är uppdaterade lagerposter tillgängliga för andra viktiga processer, till exempel planering och försäljning.

Lösningen gör det snabbare, enklare och biligare för Supply Chain Management-användarna att integreras med MES från tredje part. Den erbjuder följande funktioner:

- Affärshändelser och gränssnitt som stöder [nyckelprocesser för tillverkningskörning](#processes-available-for-mes-integration)
- En centraliserad instrumentpanel där du kan spåra historiken för händelsebearbetning och felsöka samt åtgärda processer som misslyckas

I följande bild visas en typisk samling affärshändelser, processer och meddelanden som utbyts i en integrerad lösning.

![Typiskt integreringsscenario.](media/3p-mes-scenario.png "Typiskt integreringsscenario.")

## <a name="turn-on-the-mes-integration-feature"></a>Aktivera integreringsfunktionen för MES

Innan du kan använda den här funktionen måste en administratör aktivera den i ditt system enligt beskrivningen i följande procedur.

1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. Kontrollera att licensnyckeln för **tid och närvaro** är aktiverad (markeras med en bockmarkering). Den här licensnyckeln krävs eftersom den styr tillverkningskörningssystemets funktioner och data. Om den inte är aktiverad gör du så här:
    1. Sätt ditt system i underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. På sidan **Licenskonfiguration** markerar du kryssrutan **Tid och närvaro**.
    1. Inaktivera underhållsläge enligt beskrivningen i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Använd arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) när du vill aktivera funktionen *Integrering med tillverkningskörningssystem*. (Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard.)

## <a name="processes-available-for-mes-integration"></a>Tillgängliga processer för MES-integrering

Du kan aktivera en eller samtliga av följande processer för integrering.

| Processnamn | Beskrivning |
|---|---|
| Frisläpp tillverkningsorder och affärshändelser för ändringar i produktionsorderstatus | Den här processen är en affärshändelse som MES kan lyssna på och som visar information om de tillverkningsorder som ska tillverkas. Referensdata som är relaterade till tillverkningsordern förväntas delas från Supply Chain Management till MES via Open Data Protocol (OData) eller dataenheter. |
| Starta produktionsorder | Den här processen förser Supply Chain Management med information om tillverkningsorder som startas med hjälp av MES. Det garanterar att båda systemen har en aktuell vy över alla tillverkningsaktiviteter. |
| Rapportera producerad eller kasserad kvantitet | Den här processen förser Supply Chain Management med information om lyckade och misslyckade kvantiteter som rapporteras för ett tillverkningsjobb med hjälp av MES. Det garanterar att arbetsledarna på golvet får en aktuell vy av produktionens planförlopp. |
| Rapportera materialförbrukning | Den här processen förser Supply Chain Management med information från MES om de materialkvantiteter som förbrukas. Den gör uppdaterade lagerposter tillgängliga för andra viktiga processer, till exempel planering och försäljning. |
| Rapportera den tid som förbrukats för åtgärden | Denna process förser Supply Chain Management med information om den tid som används för en viss åtgärd. |
| Slutproduktionsorder | Denna process informerar Supply Chain Management om att MES har uppdaterat en tillverkningsorder till dess slutliga status *Avslutad*. Denna status indikerar att inga fler kvantiteter kommer att produceras på tillverkningsordern. |

## <a name="monitor-incoming-messages"></a>Övervaka inkommande meddelanden

Du övervakar inkommande meddelanden till systemet genom att öppna sidan **Integrering av körningssystem för tillverkning**. Där kan du visa, bearbeta och felsöka ärenden.

Alla meddelanden för en viss tillverkningsorder bearbetas i den ordning de tas emot. Det kan dock hända att meddelanden för olika tillverkningsorder inte bearbetas i den mottagna serien eftersom batchjobb bearbetas parallellt. Om det misslyckas försöker batchjobbet att bearbeta varje meddelande tre gånger innan det får statusvärdet *Misslyckat*.

## <a name="call-the-api"></a>Anropa API

Om du vill anropa API för MES-integrering ska du skicka en `POST`-begäran till följande slutpunkts-URL:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

Brödtexten i den begäran som du skickar bör se ut ungefär som i följande exempel. Byt ut värdena för `_companyId`, `_messageType` och `_messageContent` efter behov. Information om olika meddelandetyper som API har stöd för och hur du utformar dessas innehåll finns i nästa avsnitt.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Meddelandetyper och innehåll för API

I det här avsnittet beskrivs varje enskild meddelandetyp som kan utbytas via API för MES-integrering.

### <a name="start-production-order-message"></a>Meddelandet Starta produktionsorder

För meddelandet om *starta produktionsorder* är värdet för `_messageType` lika med `ProdProductionOrderStart`. Följande tabell visar de fält som detta meddelande stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ProductionOrderNumber` | Obligatoriskt | Sträng |
| `StartedQuantity` | Valfritt | Realtal |
| `StartedDate` | Valfritt | Datum |
| `AutomaticBOMConsumptionRule` | Valfritt | Uppräkning (FlushingPrincip \| Alltid \| Aldrig) |

### <a name="report-as-finished-message"></a>Meddelandet Rapportera som färdig

För meddelandet *Rapportera som färdig* är värdet `_messageType` lika med `ProdProductionOrderReportFinished`. Följande tabell visar de fält som detta meddelande stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ProductionOrderNumber` | Obligatoriskt | Sträng |
| `ReportFinishedLines` | Obligatoriskt | En lista med rader (minst en) där var och en innehåller den nyttolast som beskrivs i nästa tabell |

Följande tabell visar de fält som varje rad i `ReportFinishedLines`-avsnittet av `ProdProductionOrderReportFinished`-meddelandet stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `LineNumber` | Valfritt | Realtal |
| `ItemNumber` | Valfritt | Sträng|
| `ProductionType` | Valfritt | Uppräkning (MainItem \| Formel \| Strukturlista \| Co_Product \| By_Product \| Ingen), utbyggbar |
| `ReportedErrorQuantity` | Valfritt | Realtal|
| `ReportedGoodQuantity` | Valfritt | Realtal|
| `ReportedErrorCatchWeightQuantity` | Valfritt | Realtal |
| `ReportedGoodCatchWeightQuantity` | Valfritt | Realtal |
| `AcceptError` | Valfritt | Enum (Ja \|nej) |
| `ErrorCause` | Valfritt | Uppräkning (Ingen \| Material \| Maskin \| OperatingStaff), utbyggbar |
| `ExecutedDateTime` | Valfritt | DatumTid |
| `ReportAsFinishedDate` | Valfritt | Datum |
| `AutomaticBOMConsumptionRule` | Valfritt | Uppräkning (FlushingPrincip \| Alltid \| Aldrig) |
| `AutomaticRouteConsumptionRule` | Valfritt |Uppräkning (RouteDependent \| Alltid \| Aldrig) |
| `RespectFlushingPrincipleDuringOverproduction` | Valfritt | Enum (Ja \|nej) |
| `ProductionJournalNameId` | Valfritt | Sträng |
| `PickingListProductionJournalNameId` | Valfritt | Sträng|
| `RouteCardProductionJournalNameId` | Valfritt | Sträng |
| `FromOperationNumber` | Valfritt | Heltal|
| `ToOperationNumber` | Valfritt | Heltal|
| `InventoryLotId` | Valfritt | Sträng |
| `BaseValue` | Valfritt | Sträng |
| `EndJob` | Valfritt | Enum (Ja \|nej) |
| `EndPickingList` | Valfritt | Enum (Ja \|nej) |
| `EndRouteCard` | Valfritt | Enum (Ja \|nej) |
| `PostNow` | Valfritt | Enum (Ja \|nej) |
| `AutoUpdate` | Valfritt | Enum (Ja \|nej) |
| `ProductColorId` | Valfritt | Sträng|
| `ProductConfigurationId` | Valfritt | Sträng |
| `ProductSizeId` | Valfritt | Sträng |
| `ProductStyleId` | Valfritt | Sträng |
| `ProductVersionId` | Valfritt | Sträng |
| `ItemBatchNumber` | Valfritt | Sträng |
| `ProductSerialNumber` | Valfritt | Sträng |
| `LicensePlateNumber` | Valfritt | Sträng |
| `InventoryStatusId` | Valfritt | Sträng |
| `ProductionWarehouseId` | Valfritt | Sträng |
| `ProductionSiteId` | Valfritt | Sträng |
| `ProductionWarehouseLocationId` | Valfritt | Sträng |
| `InventoryDimension1` till `InventoryDimension12` | Valfritt | Sträng |

De 12 utökningsbara dimensionerna (`InventoryDimension1` genom `InventoryDimension12`) kräver anpassning och används inte alltid. Mer information om dem finns i [Lägg till nya lagerdimensioner via tillägg](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Meddelande om materialförbrukning (plocklista)

För meddelandet *materialförbrukning (plocklista)* är värdet för `_messageType` lika med `ProdProductionOrderPickingList`. Följande tabell visar de fält som detta meddelande stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ProductionOrderNumber` | Obligatoriskt | Sträng |
| `JournalNameId` | Valfritt | Sträng |
| `PickingListLines` | Obligatoriskt | En lista med rader (minst en) där var och en innehåller den nyttolast som beskrivs i nästa tabell |

Följande tabell visar de fält som varje rad i `PickingListLines`-avsnittet av `ProdProductionOrderPickingList`-meddelandet stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ItemNumber` | Obligatoriskt | Sträng |
| `ConsumptionBOMQuantity` | Valfritt | Realtal |
| `ProposalBOMQuantity` | Valfritt | Realtal |
| `ScrapBOMQuantity` | Valfritt | Realtal |
| `BOMUnitSymbol` | Valfritt | Sträng |
| `ConsumptionInventoryQuantity` | Valfritt | Realtal |
| `ProposalInventoryQuantity` | Valfritt | Realtal |
| `ConsumptionCatchWeightQuantity` | Valfritt | Realtal |
| `ProposalCatchWeightQuantity` | Valfritt | Realtal |
| `ConsumptionDate` | Valfritt | Datum |
| `OperationNumber` | Valfritt | Heltal |
| `LineNumber` | Valfritt | Realtal |
| `PositionNumber` | Valfritt | Sträng |
| `IsConsumptionEnded` | Valfritt | Enum (Ja \|nej) |
| `ErrorCause` | Valfritt | Uppräkning (Ingen \| Material \| Maskin \| OperatingStaff), utbyggbar |
| `InventoryLotId` | Valfritt | Sträng |

### <a name="time-used-for-operation-route-card-message"></a>Tid som används för åtgärdsmeddelande (flödeskort)

För meddelandet *tid som används för åtgärd (flödeskort)* är värdet för `_messageType` lika med `ProdProductionOrderRouteCard`. Följande tabell visar de fält som detta meddelande stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ProductionOrderNumber` | Obligatoriskt | Sträng |
| `JournalNameId` | Valfritt | Sträng |
| `RouteCardLines` | Obligatoriskt | En lista med rader (minst en) där var och en innehåller den nyttolast som beskrivs i nästa tabell |

Följande tabell visar de fält som varje rad i `RouteCardLines`-avsnittet av `ProdProductionOrderRouteCard`-meddelandet stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `OperationNumber` | Obligatoriskt | Heltal |
| `OperationPriority` | Valfritt | Uppräkning (Primär \| Sekundär1 \| Sekundär2 \| ... \| Sekundär20) |
| `OperationId` | Valfritt | Sträng |
| `OperationsResourceId` | Valfritt | Sträng |
| `Worker` | Valfritt | Sträng |
| `HoursRouteCostCategoryId` | Valfritt | Sträng |
| `QuantityRouteCostCategoryId` | Valfritt | Sträng |
| `HourlyRate` | Valfritt | Realtal |
| `Hours` | Valfritt | Realtal |
| `GoodQuantity` | Valfritt | Realtal |
| `ErrorQuantity` | Valfritt | Realtal |
| `CatchWeightGoodQuantity` | Valfritt | Realtal |
| `CatchWeightErrorQuantity` | Valfritt | Realtal |
| `QuantityPrice` | Valfritt | Realtal |
| `ProcessingPercentage` | Valfritt | Realtal |
| `ConsumptionDate` | Valfritt | Datum |
| `TaskType` | Valfritt | Uppräkning (QueueBefore \| Konfiguration \| Process \| Överlappning \| Transport \| QueueAfter \| Ej fakturerbart) |
| `ErrorCause` | Valfritt | Uppräkning (Ingen \| Material \| Maskin \| OperatingStaff), utbyggbar |
| `OperationCompleted` | Valfritt | Enum (Ja \|nej) |
| `BOMConsumption` | Valfritt | Enum (Ja \|nej) |
| `ReportAsFinished` | Valfritt | Enum (Ja \|nej) |

### <a name="end-production-order-message"></a>Meddelandet Avsluta produktionsorder

För meddelandet *avsluta produktionsorder* är värdet för `_messageType` lika med `ProdProductionOrderEnd`. Följande tabell visar de fält som detta meddelande stöder.

| Fältnamn | Status | Typ |
|---|---|---|
| `ProductionOrderNumber` | Obligatoriskt | Sträng |
| `ExecutedDateTime` | Valfritt | DatumTid |
| `EndedDate` | Valfritt | Datum |
| `UseTimeAndAttendanceCost` | Valfritt | Enum (Ja \|nej) |
| `AutoReportAsFinished` | Valfritt | Enum (Ja \|nej) |
| `AutoUpdate` | Valfritt | Enum (Ja \|nej) |

## <a name="other-production-information"></a>Annan produktionsinformation

Meddelandena stöder åtgärder eller händelser som inträffar i arbetsgolvet. De bearbetas med hjälp av MES-integreringsramverket som beskrivs i denna artikel. Designen förutsätter att annan referensinformation som ska delas med MES (till exempel produktrelaterad information, strukturlista eller flöde (med dess specifika inställnings- och konfigurationstider) som används i en viss tillverkningsorder) hämtas från systemet med hjälp av [dataenheter](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#data-entities) via filöverföring eller OData.

## <a name="receive-feedback-about-the-state-of-a-message"></a>Få feedback om statusen för ett meddelande

När MES har skickat ett meddelande till Supply Chain Management kan det vara relevant för Supply Chain Management att returnera feedback om meddelandets status. Här följer några exempel på situationer där den här metoden kan vara användbar:

- Det finns ingen person som ansvarar för ansvar för konstant övervakning av MES-integreringen.
- Den person som ansvarar för att övervaka MES-integreringen vill meddelas via e-post när ett meddelande misslyckas, så att han eller hon vet att de måste vidta åtgärder.
- MES måste visa ett felmeddelande i syfte att informera operatorn på golvet eller någon på IT-avdelningen om att de måste vidta åtgärder.
- MES måste omberäkna orderschemat när det har fått ett felmeddelande (till exempel eftersom tillverkningsordern inte kunde starta).

I dessa fall kan du använda standard-notifieringsfunktionen i Supply Chain Management. Mer information om hur standardvarningar fungerar finns i följande resurser:

- Hjälpartikel: [Notifieringar – översikt](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Video: [Alternativ för notifieringsregel i Ekonomi och drift](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Du kan till exempel konfigurera följande notifieringar om du vill ge återkoppling rörande en meddelandestatus:

- Skapa en affärshändelse ("Skicka externt") som används när ett meddelande *misslyckats*.
- Skicka ett meddelande och e-post till IT-admin eller produktionschefen.

