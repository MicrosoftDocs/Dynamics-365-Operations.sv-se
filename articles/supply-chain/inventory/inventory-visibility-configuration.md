---
title: Konfigurera Lagersynlighet
description: I detta ämne beskrivs hur du konfigurerar Lagersynlighet.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345043"
---
# <a name="inventory-visibility-configuration"></a>Konfigurera Lagersynlighet

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

I detta ämne beskrivs hur du konfigurerar Lagersynlighet.

## <a name="introduction"></a><a name="introduction"></a>Introduktion

Innan du börjar arbeta med Lagersynlighet måste du utföra följande konfiguration så som beskrivs i detta avsnitt:

- [Konfiguration för datakälla](#data-source-configuration)
- [Patritionskonfiguration](#partition-configuration)
- [Konfiguration av produktindexhierarki](#index-configuration)
- [Reservationskonfiguration (valfritt)](#reservation-configuration)
- [Exempel på standardkonfiguration](#default-configuration-sample)

> [!NOTE]
> Du kan visa och redigera konfigurationer av Lagersynlighet i [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). När konfigurationen är slutförd väljer du **Uppdatera konfiguration** i programmet.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Konfiguration för datakälla

Datakällan representerar det system som dina data kommer från. Bland exemplen finns `fno` (som betyder för "Dynamics 365 Finance and Operations-program") och `pos` (som betyder "försäljningsställe").

Datakällskonfigurationen innehåller följande delar:

- Dimension (dimensionsmappning)
- Fysiskt mått
- Beräknat mått

> [!NOTE]
> Datakällan `fno` är reserverad för Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimension (dimensionsmappning)

Syftet med dimensionskonfigurationen är att standardisera integreringen av flera system för bokföring av händelser och frågor, baserat på dimensionskombinationer.

Lagersynlighet stöder följande allmänna basdimensioner.

| Dimensionstyp | Basdimension |
|---|---|
| Produkt | `ColorId` |
| Produkt | `SizeId` |
| Produkt | `StyleId` |
| Produkt | `ConfigId` |
| Spårning | `BatchId` |
| Spårning | `SerialId` |
| Plats | `LocationId` |
| Plats | `SiteId` |
| Lagerstatus | `StatusId` |
| Lagerställespecifik | `WMSLocationId` |
| Lagerställespecifik | `WMSPalletId` |
| Lagerställespecifik | `LicensePlateId` |
| Annat | `VersionId` |
| Lager (anpassat) | `InventDimension1` via `InventDimension12` |
| Anknytning | `ExtendedDimension1` via `ExtendedDimension8` |

> [!NOTE]
> Dimensionstyper som anges i föregående tabell är endast avsedda som referens. Du behöver inte definiera dem i Lagersynlighet.
>
> Lagerdimensioner (anpassade) kan reserveras för Supply Chain Management. I så fall kan du använda de utökade dimensionerna istället.

Externa system kan få åtkomst till Lagersynlighet genom sina RESTful-API:er. För integreringen låter Lagersynlighet dig konfigurera den _externa datakällan_ och mappningen från de _externa dimensionerna_ till _basdimensionerna_. Här följer ett exempel på en mappningstabell för dimensioner.

| Extern dimension | Basdimension |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Genom att konfigurera en dimensionsmappning kan du skicka de externa dimensionerna direkt till Lagersynlighet. Lagersynlighet konverterar då automatiskt externa dimensioner till basdimensioner.

### <a name="physical-measures"></a>Fysiska mått

Fysiska mått ändrar kvanheten och återspeglar lagerstatusen. Du kan definiera dina egna fysiska mått, baserat på dina behov.

Lagerstyrning innehåller en lista över fysiska standardmått som är kopplade till Supply Chain Management (`fno`-datakällan). Följande tabell innehåller ett exempel på fysiska mått.

| Namn på fysiskt mått | beskrivning |
|---|---|
| `NotSpecified` | Har inte angetts |
| `Arrived` | Infört |
| `AvailOrdered` | Tillgängligt beställt |
| `AvailPhysical` | Fysiskt disponibelt |
| `Deducted` | Avdraget |
| `OnOrder` | Beställning |
| `Ordered` | Beställt |
| `PhysicalInvent` | Fysiskt lager |
| `Picked` | Plockad |
| `PostedQty` | Bokförd kvantitet |
| `QuotationIssue` | Offert utleverans |
| `QuotationReceipt` | Offert inleverans |
| `Received` | Mottaget |
| `Registered` | Registrerat |
| `ReservOrdered` | Beställt reserverat |
| `ReservPhysical` | Reserverat fysiskt |

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Beräknade mått

Beräknade mått ger en anpassad beräkningsformel som består av en kombination av fysiska mått. Med hjälp av denna funktion kan du definiera en uppsättning fysiska mått som ska läggas till, och/eller en uppsättning fysiska mått som dras ifrån, för att generera det anpassade måttet.

Du har exempelvis följande frågeresultat:

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Du konfigurerar sedan ett beräknat mått vid namn `MyCustomAvailableforReservation` på det sätt som visas i följande tabell. Detta beräknade mått kommer att förbrukas av förbrukningssystemet.

| Förbrukningssystem | Beräknat mått | Datakälla | Fysiskt mått | Beräkningstyp |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

När denna beräkningsformel används kommer det nya frågeresultatet att omfatta det anpassade måttet.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

`MyCustomAvailableforReservation`-resultatet som baseras på beräkningsinställningen i de anpassade måtten är 100 + 50 + 80 + 90 + 30 – 10 – 20 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Patritionskonfiguration

Partitionskonfigurationen består av en kombination av basdimensioner. Denna definierar datadistributionsmönstret. Dataoperationer i samma partition har stöd för hög prestanda och kostar inte så mycket. Därför kan bra partitionsmönster ge stora fördelar.

Lagerstyrningen innehåller följande standardkonfiguration för partitioner.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> Konfigurationen av standardpartitionen är endast avsedd som referens. Du behöver inte definiera den i Lagersynlighet. För närvarande stöds inte uppgradering av partitionskonfiguration.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Konfiguration av produktindexhierarki

För det mesta kommer lagerbehållningsfrågan inte bara att vara på den högsta "total"-nivån. Istället kanske du också vill visa resultat som sammanställts baserat på lagerdimensionerna.

Lagersynlighet ger större flexibilitet eftersom du då kan konfigurerar _index_. Dessa index baseras på en dimension eller en kombination av dimensioner. Ett index består av ett *uppsättningsnummer*, en *dimension* och en *hierarki* enligt definionen i följande tabell.

| Namn | beskrivning |
|---|---|
| Ange nummer | Dimensioner som tillhör samma uppsättning (index) grupperas tillsammans, och samma uppsättningsnummer tilldelas dem. |
| Dimension | De basdimensioner som frågeresultatet sammanställs på. |
| Hierarki | Hierarkin används för att definiera de dimensionskombinationer som kan efterfrågas. Du kan till exempel konfigurera en dimensionsuppsättning som har en hierarkisekvens bestående av `(ColorId, SizeId, StyleId)`. I detta fall stöder systemet frågor i fyra dimensionskombinationer. Den första kombinationen är tom, den andra är `(ColorId)`, den tredje är `(ColorId, SizeId)`, och den fjärde är `(ColorId, SizeId, StyleId)`. Övriga kombinationer stöds inte. Mer information finns i följande exempel. |

### <a name="example"></a>Exempel

Detta avsnitt innehåller ett exempel som visar hur hierarkin fungerar.

Du har följande artiklar på lager.

| Artikel | ColorId | SizeId | StyleId | Antal |
|---|---|---|---|---|
| T-shirt | Svart | Litet | Bred | 1 |
| T-shirt | Svart | Litet | Vanlig | 2 |
| T-shirt | Svart | Stort | Bred | 3 |
| T-shirt | Svart | Stort | Vanlig | 4 |
| T-shirt | Rött | Litet | Bred | 5 |
| T-shirt | Rött | Litet | Vanlig | 6 |
| T-shirt | Rött | Stort | Vanlig | 7 |

Detta är indexet.

| Ange nummer | Dimension | Hierarki |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

Med indexet kan du fråga efter lagerbehållningen på följande sätt:

- `()` – Gruppering efter alla

    - T-shirt, 28

- `(ColorId)` – Gruppering efter alla `ColorId`

    - T-shirt, svart, 10
    - T-shirt, röd, 18

- `(ColorId, SizeId)` – Gruppering efter kombinationen `ColorId` och `SizeId`

    - T-shirt, svart, liten, 3
    - T-shirt, svart, stor, 7
    - T-shirt, röd, liten, 11
    - T-shirt, röd, stor, 7

- `(ColorId, SizeId, StyleId)` – Gruppering efter kombinationen `ColorId`, `SizeId` och `StyleId`

    - T-shirt, svart, liten, bred, 1
    - T-shirt, svart, liten, standard, 2
    - T-shirt, svart, stor, bred, 3
    - T-shirt, svart, stor, standard, 4
    - T-shirt, röd, liten, bred, 5
    - T-shirt, röd, liten, standard, 6
    - T-shirt, röd, stor, standard, 7

> [!NOTE]
> Basdimensioner som definieras i partitionskonfigurationen ska inte definieras i indexkonfigurationer.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Reservationskonfiguration (valfritt)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Reservationskonfiguration krävs om du vill använda funktionen för preliminär reservation. Konfigurationen består av två grundläggande delar:

- Preliminär reservationsmappning
- Preliminär reservationshierarki

### <a name="soft-reservation-mapping"></a>Preliminär reservationsmappning

När du gör en reservation kanske du vill veta om lagerbehållningen för närvarande är tillgänglig för reservation. Valideringen är kopplad till ett beräknat mått som representerar en beräkningsformel för en kombination av fysiska mått.

Ett reservationsmått baseras till exempel på det fysiska måttet `SoftReservOrdered` från datakällan `iv` (Lagersynlighet). I det här fallet kan du konfigurera det beräknade måttet `AvailableToReserve` för datakällan `iv` som visas här.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `AvailPhysical` |
| Tillägg | `pos` | `Inbound` |
| Subtraktion | `pos` | `Outbound` |
| Subtraktion | `iv` | `SoftReservOrdered` |

Skapa sedan en preliminär mappning i syfte att tillhandahålla en mappning från reservationsmåttet `SoftReservOrdered` till det beräknade måttet `AvailableToReserve`.

| Datakälla för fysiskt mått | Fysiskt mått | Tillgänglig för datakälla för reservation | Tillgänglig för beräknat reservationsmått |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

När du gör reservationer i `SoftReservOrdered` hittar Lagersynlighet nu automatiskt `AvailableToReserve` och dess relaterade beräkningsformel för att utföra reservationsvalideringen.

Du har till exempel följande lagerbehållning i Lagersynlighet.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

I detta fall gäller följande beräkning:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Om du därför försöker göra reservationer på `iv.SoftReservOrdered` och kvantiteten är mindre än eller lika med `AvailableToReserve` (10) kan du göra reservationen.

### <a name="soft-reservation-hierarchy"></a>Preliminär reservationshierarki

Reservationshierarkin beskriver den dimensionssekvens som måste anges när reservationer görs. Detta fungerar på samma sätt som produktindexhierarkin fungerar för behållningsfrågor.

Reservationshierarkin är oberoende av produktindexhierarkin. Tack vare detta oberoende kan du implementera kategorihantering där användare kan bryta ned dimensionerna i detaljer i syfte att specificera kraven för att göra mer exakta reservationer.

Här följer ett exempel på en preliminär reservationshierarki.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

I det här exemplet kan du göra reservationer i följande dimensionssekvenser:

- `()` – Ingen dimension har angetts.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

En giltig dimensionssekvens bör strikt följa reservationshierarkin, dimension för dimension. Hierarkisekvensen är till exempel `(SiteId, LocationId, SizeId)` inte giltig eftersom `ColorId` saknas.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exempel på standardkonfiguration

Under dess initialiseringsfas skapar Lagersynlighet en standardkonfiguration. Du kan ändra konfigurationenvid behov.

### <a name="data-source-configuration"></a>Konfiguration för datakälla

#### <a name="configuration-of-the-iv-data-source"></a>Konfiguration för iv-datakälla

Detta avsnitt beskriver hur `iv`-datakällan konfigureras.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Fysiska mått konfigurerade för iv-datakällan

Följande fysiska mått konfigureras för `iv`-datakällan:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Beräknat mått för ordertotal

Det beräknade `OrderedTotal`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `Ordered` |
| Tillägg | `fno` | `Arrived` |
| Tillägg | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Beräknat behållningsmått

Det beräknade `OnHand`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `PhysicalInvent` |
| Tillägg | `iom` | `OnHand` |
| Tillägg | `erp` | `Unrestricted` |
| Tillägg | `erp` | `QualityInspection` |
| Tillägg | `pos` | `PosInbound` |
| Subtraktion | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>Beräknat mått för reserverat totalt

Det beräknade `ReservedTotal`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `ReservPhysical` |
| Tillägg | `fno` | `ReservOrdered` |
| Tillägg | `iv` | `SoftReservPhysical` |
| Tillägg | `iv` | `SoftReservOrdered` |
| Tillägg | `iv` | `ReservPhysical` |
| Tillägg | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Beräknat mått för reserverat preliminärt

Det beräknade `SoftReserved`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `iv` | `SoftReservPhysical` |
| Tillägg | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>Beräknat mått för slutgiltig reservation

Det beräknade `HardReserved`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `ReservPhysical` |
| Tillägg | `fno` | `ReservOrdered` |
| Tillägg | `iv` | `ReservPhysical` |
| Tillägg | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Beräknat mått för öppen order

Det beräknade `OpenOrder`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `OnOrder` |
| Tillägg | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Beräknat mått för OnHandAvailable

Det beräknade `OnHandAvailable`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `PhysicalInvent` |
| Tillägg | `iom` | `OnHand` |
| Tillägg | `erp` | `Unrestricted` |
| Tillägg | `erp` | `QualityInspection` |
| Tillägg | `pos` | `PosInbound` |
| Subtraktion | `fno` | `ReservPhysical` |
| Subtraktion | `iv` | `SoftReservPhysical` |
| Subtraktion | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Beräknat mått för AvailableToReserve

Det beräknade `AvailableToReserve`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `PhysicalInvent` |
| Tillägg | `iom` | `OnHand` |
| Tillägg | `erp` | `Unrestricted` |
| Tillägg | `erp` | `QualityInspection` |
| Tillägg | `pos` | `PosInbound` |
| Tillägg | `fno` | `Ordered` |
| Tillägg | `fno` | `Arrived` |
| Tillägg | `iv` | `Ordered` |
| Subtraktion | `fno` | `ReservPhysical` |
| Subtraktion | `fno` | `ReservOrdered` |
| Subtraktion | `iv` | `SoftReservPhysical` |
| Subtraktion | `iv` | `SoftReservOrdered` |
| Subtraktion | `iv` | `ReservPhysical` |
| Subtraktion | `iv` | `ReservOrdered` |
| Subtraktion | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Beräknat mått för InventorySupply

Det beräknade `InventorySupply`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `Ordered` |
| Tillägg | `fno` | `Arrived` |
| Tillägg | `iv` | `Ordered` |
| Tillägg | `fno` | `PhysicalInvent` |
| Tillägg | `iom` | `OnHand` |
| Tillägg | `erp` | `Unrestricted` |
| Tillägg | `erp` | `QualityInspection` |
| Tillägg | `pos` | `PosInbound` |
| Subtraktion | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Beräknat mått för InventoryDemand

Det beräknade `InventoryDemand`-måttet konfigureras för `iv`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `OnOrder` |
| Tillägg | `iom` | `OnOrder` |
| Tillägg | `iv` | `SoftReservPhysical` |
| Tillägg | `iv` | `SoftReservOrdered` |
| Tillägg | `fno` | `ReservPhysical` |
| Tillägg | `fno` | `ReservOrdered` |
| Tillägg | `iv` | `ReservPhysical` |
| Tillägg | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Konfiguration för fno-datakällan

Detta avsnitt beskriver hur `fno`-datakällan konfigureras.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Dimensionsmappningar för fno-datakällan

Dimensionsmappningarna som listas i följande tabell konfigureras för `fno`-datakällan.

| Extern dimension | Basdimension |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Fysiska mått konfigurerade för fno-datakällan

Följande fysiska mått konfigureras för `fno`-datakällan:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Konfiguration för pos-datakällan

Detta avsnitt beskriver hur `pos`-datakällan konfigureras.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fysiska mått för kassadatakällan

Följande fysiska mått konfigureras för `pos`-datakällan:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Beräknat mått för AvailQuantity

Det beräknade `AvailQuantity`-måttet konfigureras för `pos`-datakällan enligt följande tabell.

| Beräkningstyp | Datakälla | Fysiskt mått |
|---|---|---|
| Tillägg | `fno` | `AvailPhysical` |
| Tillägg | `pos` | `PosInbound` |
| Subtraktion | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Konfiguration för iom-datakälla

Följande fysiska mått konfigureras för `iom`-datakällan (Intelligent Order Management):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Konfiguration för erp-datakälla

Följande fysiska mått konfigureras för `erp`-datakällan (resursplanering för företag):

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Patritionskonfiguration

Följande tabell visar konfigurationen för standardpartitionen.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Indexkonfiguration

Följande tabell visar konfigurationen för standardindex.

| Ange nummer | Dimension | Hierarki |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Reservationskonfiguration

Detta avsnitt beskriver standardreservationskonfigurationen.

#### <a name="reservation-mapping"></a>Reservationsmappning

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Följande tabell visar standardmappningen för reservation.

| Datakälla för fysiskt mått | Fysiskt mått | Tillgänglig för datakälla för reservation | Tillgänglig för beräknat reservationsmått |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Reservationshierarki

Följande tabell visar standardhierarkin för reservation.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
