---
title: Konfigurera lagersynlighet
description: I detta ämne beskrivs hur du konfigurerar Lagersynlighet.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: fcbace2bd28a843fca8aa2f4f998c08f238c29d6
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920308"
---
# <a name="configure-inventory-visibility"></a>Konfigurera lagersynlighet

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

I det här avsnittet beskrivs hur du konfigurerar Lagersynlighet via Lagersynlighet-appen i Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introduktion

Innan du börjar arbeta med Lagersynlighet måste du utföra följande konfiguration så som beskrivs i detta avsnitt:

- [Konfiguration för datakälla](#data-source-configuration)
- [Patritionskonfiguration](#partition-configuration)
- [Konfiguration av produktindexhierarki](#index-configuration)
- [Reservationskonfiguration (valfritt)](#reservation-configuration)
- [Exempel på standardkonfiguration](#default-configuration-sample)

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar installerar och konfigurerar du tillägget Lagersynlighet enligt beskrivningen i [Installera och konfigurera Lagersynlighet](inventory-visibility-setup.md).

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Aktivera funktioner för lagersynlighet i Power Apps-funktionshantering

Tillägget Lagersynlighet lägger till flera nya funktioner i Power Apps-installationen. Dessa funktioner är avstängda som standard. Om du vill använda dem öppnar du sidan **Konfiguration** i Power Apps och aktiverar följande funktioner på fliken **Funktionshantering**.

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Hitta tjänstslutpunkten

Om du inte känner till rätt tjänstslutpunkt för Lagersynlighet öppnar du sidan **Konfiguration** i Power Apps och sedan **Visa tjänstslutpunkt** i det övre högra hörnet. Sidan visar korrekt tjänstslutpunkt.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>Konfigurationssidan i appen Lagersynlighet

I Power Apps, på sidan **Konfiguration** i [Lagersynlighet-appen](inventory-visibility-power-platform.md), kan du konfigurera behållningskonfigurationen och konfigurationen av preliminär reservation. När tillägget har installerats innehåller standardkonfigurationen värdet från Microsoft Dynamics 365 Supply Chain Management (datakällan `fno`). Du kan granska standardinställningarna. Baserat på dina affärsbehov och lagerbokföringskraven i det externa systemet kan du modifiera konfigurationen för att standardisera det sätt på vilket lagerändringar kan bokföras, ordnas och efterfrågas i flera olika system. I de återstående avsnitten i det här ämnet beskrivs hur du använder varje del av sidan **Konfiguration**.

När konfigurationen är slutförd, se till att du väljer **Uppdatera konfiguration** i appen.

## <a name="data-source-configuration"></a>Konfiguration för datakälla

Varje datakälla representerar ett system som dina data kommer från. Namn på exempeldatakällor är bland annat `fno` (som betyder för "Dynamics 365 Finance and Operations-program") och `pos` (som betyder "försäljningsställe"). Standardinställningen är att Supply Chain Management konfigureras som standarddatakälla (`fno`) i Lagersynlighet.

> [!NOTE]
> Datakällan `fno` är reserverad för Supply Chain Management. Om tillägget Lagerhantering är integrerat i en miljö för Supply Chain Management rekommenderar vi att du inte tar bort konfigurationer som är relaterade till `fno` datakällan.

Följ dessa steg för att lägga till en datakälla.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla** väljer du **Ny datakälla** om du vill lägga till en datakälla.

> [!NOTE]
> När du lägger till en datakälla måste du kontrollera namn, fysiska mått och dimensionsmappningar för datakällan innan du uppdaterar konfigurationen för tjänsten Lagersynlighet. Du kan inte ändra dessa inställningar efter det att du har valt **Uppdatera konfiguration**.

Datakällskonfigurationen innehåller följande delar:

- Dimensioner (dimensionsmappning)
- Fysiska mått
- Beräknade mått

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensioner (dimensionsmappning)

Syftet med dimensionskonfigurationen är att standardisera integreringen av flera system för bokföring av händelser och frågor, baserat på dimensionskombinationer. Lagersynligheten innehåller en lista över basdimensioner som kan mappas från datakällans dimensioner. Det finns 33 dimensioner att tillgå för mappning.

- Om du använder Supply Chain Management som en av dina datakällor mappas som standard 13 dimensioner till standarddimensionerna i Supply Chain Management. Tolv andra dimensioner (`inventDimension1` till `inventDimension12`) mappas till anpassade dimensioner i Supply Chain Management. Återstående åtta dimensioner är utökade dimensioner som du kan mappa till externa datakällor.
- Om du inte använder Supply Chain Management som en av dina datakällor kan du mappa dimensionerna fritt. Följande tabell visar den fullständiga listan över tillgängliga dimensioner.

> [!NOTE]
> Om din dimension inte finns i standarddimensionslistan och du använder en extern datakälla rekommenderar vi att du använder `ExtendedDimension1` via `ExtendedDimension8` för att utföra mappningen.

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
| Tillägg | `ExtendedDimension1` via `ExtendedDimension8` |
| System | `Empty` |

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

Om du vill lägga till dimensionsmappningar följer du dessa steg.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla**, i avsnittet **Dimensionsmappningar**, väljer du **Lägg till** om du vill lägga till dimensionsmappningar.
    ![Lägga till dimensionsmappningar](media/inventory-visibility-dimension-mapping.png "Lägga till dimensionsmappningar")

1. I fältet **Dimensionsnman** anger du källdimensionen.
1. I fältet **Till basdimension** anger du den dimension i Lagersynlighet som du vill mappa.
1. Välj **Spara**.

Om datakällan till exempel innehåller en produktfärgsdimension kan du mappa den till basdimensionen `ColorId` för att lägga till en anpassad `ProductColor`- dimension i `exterchannel`-datakällan. Den mappas sedan till `ColorId`-basdimensionen.

### <a name="physical-measures"></a>Fysiska mått

När en datakälla bokför en lagerändring i Lagersynlighet bokför den denna ändring med hjälp av *fysiska mått*. Fysiska mått ändrar kvanheten och återspeglar lagerstatusen. Du kan definiera dina egna fysiska mått, baserat på dina behov. Frågor kan baseras på de fysiska måtten.

Lagerstyrning innehåller en lista över fysiska standardmått som är kopplade till Supply Chain Management (`fno`-datakällan). Dessa fysiska standardmått tas från lagertransaktionens status på sidan **Lagerbehållningslista** i Supply Chain Management (**Lagerstyrning \> Förfrågningar och rapporter \> Behållningslista**). Följande tabell innehåller ett exempel på fysiska mått.

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

Om datakällan är Supply Chain Management behöver du inte skapa de fysiska standardmåtten på nytt. För externa datakällor kan du emellertid skapa nya fysiska mått genom att följa dessa steg.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla**, i avsnittet **Fysiska mått** väljer du **Lägg till**, anger ett källmåttnamn samt sparar dina ändringar.

### <a name="calculated-measures"></a>Beräknade mått

Du kan använda Lagersynlighet när du vill söka efter både fysiska lagermått *och anpassade beräknade mått*. Beräknade mått ger en anpassad beräkningsformel som består av en kombination av fysiska mått. Med hjälp av denna funktion kan du definiera en uppsättning fysiska mått som ska läggas till, och/eller en uppsättning fysiska mått som dras ifrån, för att generera det anpassade måttet.

Med konfigurationen kan du definiera en uppsättning modifierare som läggs till eller dras ifrån för att få den totala sammanlagda utleveranskvanheten.

Följ stegen nedan för att konfigurera ett anpassat beräknat mått.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Beräknat mått** väljer du **Ny måttberäkning** om du vill lägga till ett beräknat mått. Ställ sedan in fälten enligt beskrivningen i följande tabell.

    | Fält | Värde |
    |---|---|
    | Nytt beräknat måttnamn | Ange namnet på det beräknade måttet. |
    | Datakälla | Frågesystemet är en datakälla. |
    | Modifierarare för datakälla | Ange modifierarens datakälla. |
    | Modifierare | Ange modifierarens namn. |
    | Modifierartyp | Välj typ av modifierare (*Tillägg* eller *Avdrag*). |

Du kan exempelvis ha följande frågeresultat.

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

`MyCustomAvailableforReservation`-resultatet som baseras på beräkningsinställningen i de anpassade måtten är 100 + 50 - 10 + 80 - 20 + 90 + 30 - 60 - 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Patritionskonfiguration

För närvarande består partitionskonfigurationen av två grunddimensioner (`SiteId` och `LocationId`) som anger hur data distribueras. Operationer under samma partition kan leverera högre prestanda till lägre kostnad. Följande tabell visar standardpartitionskonfigurationen som Tillägg för lagersynlighet tillhandahåller.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

Lösningen innehåller som standard den här partitionskonfigurationen. Därför *måste du inte definiera själv*.

> [!IMPORTANT]
> Anpassa inte standardkonfigurationen för partitionen. Om du tar bort eller ändrar den kan det leda till oväntade fel.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Konfiguration av produktindexhierarki

För det mesta kommer lagerbehållningsfrågan inte bara att vara på den högsta "total"-nivån. Istället kanske du också vill visa resultat som sammanställts baserat på lagerdimensionerna.

Lagersynlighet ger större flexibilitet eftersom du då kan konfigurerar _index_. Dessa index baseras på en dimension eller en kombination av dimensioner. Ett index består av ett *uppsättningsnummer*, en *dimension* och en *hierarki* enligt definionen i följande tabell.

| Namn | beskrivning |
|---|---|
| Ange nummer | Dimensioner som tillhör samma uppsättning (index) grupperas tillsammans, och samma uppsättningsnummer tilldelas dem. |
| Dimension | De basdimensioner som frågeresultatet sammanställs på. |
| Hierarki | Hierarkin används för att definiera de dimensionskombinationer som kan efterfrågas. Du kan till exempel konfigurera en dimensionsuppsättning som har en hierarkisekvens bestående av `(ColorId, SizeId, StyleId)`. I detta fall stöder systemet frågor i fyra dimensionskombinationer. Den första kombinationen är tom, den andra är `(ColorId)`, den tredje är `(ColorId, SizeId)`, och den fjärde är `(ColorId, SizeId, StyleId)`. Övriga kombinationer stöds inte. Mer information finns i följande exempel. |

Följ dessa steg för att konfigurera ditt index för produkthierarki.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Index för produkthierarki**, i avsnittet **Dimensionsmappningar**, väljer du **Lägg till** om du vill lägga till dimensionsmappningar.
1. En lista över index finns som standard. Om du vill ändra ett befintligt index väljer du **Redigera** eller **Lägg till** i avsnittet för relevant index. Välj **Ny indexuppsättning** om du vill skapa en ny indexuppsättning. I fältet **Dimension** väljer du i listan över basdimensioner för respektive rad i respektive indexuppsättning. Värden för följande fält genereras automatiskt:

    - **Ange nummer** – Dimensioner som tillhör samma grupp (index) grupperas tillsammans och samma uppsättningsnummer tilldelas dem.
    - **Hierarki** – Hierarkin används för att definiera de dimensionskombinationer som stöds och som kan efterfrågas i en dimensionsgrupp (index). Om du till exempel ställer in en dimensionsgrupp med hierarkisekvsekvensen *Format*, *Färg* och *Storlek* stöds resultatet av tre frågegrupper. Den första gruppen gäller endast formatet. Den andra gruppen är en kombination av format och färg. Den tredje gruppen är en kombination av format, färg och storlek. Övriga kombinationer stöds inte.

### <a name="example"></a>Exempel

Detta avsnitt innehåller ett exempel som visar hur hierarkin fungerar.

Följande tabell innehåller en lista över tillgängligt lager för detta exempel.

| Artikel | ColorId | SizeId | StyleId | Antal |
|---|---|---|---|---|
| T-shirt | Svart | Litet | Bred | 1 |
| T-shirt | Svart | Litet | Vanlig | 2 |
| T-shirt | Svart | Stort | Bred | 3 |
| T-shirt | Svart | Stort | Vanlig | 4 |
| T-shirt | Rött | Litet | Bred | 5 |
| T-shirt | Rött | Litet | Vanlig | 6 |
| T-shirt | Rött | Stort | Vanlig | 7 |

Följande tabell visar hur indexhierarkin ställs in.

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
> 
> Om du måste fråga endast lager som aggregeras av alla dimensionskombinationer kan du konfigurera ett enda index som innehåller basdimensionen `Empty`.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Reservationskonfiguration (valfritt)

Reservationskonfiguration krävs om du vill använda funktionen för preliminär reservation. Konfigurationen består av två grundläggande delar:

- Preliminär reservationsmappning
- Preliminär reservationshierarki

### <a name="soft-reservation-mapping"></a>Preliminär reservationsmappning

När du gör en reservation kanske du vill veta om lagerbehållningen för närvarande är tillgänglig för reservation. Valideringen är kopplad till ett beräknat mått som representerar en beräkningsformel för en kombination av fysiska mått.

Genom att ställa in mappningen från det fysiska måttet till det beräknade måttet aktiverar du tjänsten Lagersynlighet för att automatiskt validera reservationstillgängligheten, baserat på det fysiska måttet.

Innan du ställer in den här mappningen måste de fysiska måtten, de beräknade måtten och dessas datakällor definieras på flikarna **Datakälla** och **Beräknat mått** på sidan **Konfiguration** i Power Apps (enligt beskrivet i detta ämne).

Om du vill definiera mappningen för preliminär reservation följer du dessa steg.

1. Definiera det fysiska mått som fungerar som mått på preliminär reservation (till exempel `SoftReservOrdered`).
1. På fliken **Beräknat mått** på fliken **Konfiguration** definierar du det *beräknade måttet för reservation* (AFR) som innehåller den AFR-beräkningsformel som du vill mappa till det fysiska måttet. Du kan till exempel konfigurera `AvailableToReserve` (tillgängligt för reservation) så att detta mappas till det tidigare definierade fysiska måttet `SoftReservOrdered`. På det här sättet kan du se vilka kvantiteter med lagerstatusen `SoftReservOrdered` som är tillgängliga för reservation. Följande tabell visar beräkningsformeln för AFR.

    | Beräkningstyp | Datakälla | Fysiskt mått |
    |---|---|---|
    | Tillägg | `fno` | `AvailPhysical` |
    | Tillägg | `pos` | `Inbound` |
    | Subtraktion | `pos` | `Outbound` |
    | Subtraktion | `iv` | `SoftReservOrdered` |

    Vi rekommenderar att du konfigurerar det beräknade måttet så att det innehåller det fysiska mått som reservationsmåttet baseras på. På det här sättet påverkas den beräknade måttkvantiteten av reservationsmåttkvantiteten. I det här exemplet ska därför det beräknade måttet `AvailableToReserve` för datakällan `iv` innehålla det fysiska måttet `SoftReservOrdered` från `iv` som en komponent.

1. Öppna sidan **Konfiguration**.
1. På fliken **Preliminär reservationsmappning** konfigurerar du mappnignen från fysiskt mått till beräkna mått. I det föregående exemplet kan du använda följande inställningar för att mappa `AvailableToReserve`till det tidigare definierade fysiska `SoftReservOrdered`-måttet.

    | Datakälla för fysiskt mått | Fysiskt mått | Tillgänglig för datakälla för reservation | Tillgänglig för beräknat reservationsmått |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Om du inte kan redigera fliken **Preliminär reservationsmappning** kan du behöva du aktivera funktionen *OnHandReservation* på fliken **Funktionshantering**.

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

> [!NOTE]
> När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True` betyder att valideringen krävs, medan ett värde av `False` betyder att valideringen inte krävs. Standardvärdet är `True`.

### <a name="soft-reservation-hierarchy"></a>Preliminär reservationshierarki

Reservationshierarkin beskriver den dimensionssekvens som måste anges när reservationer görs. Detta fungerar på samma sätt som produktindexhierarkin fungerar för behållningsfrågor.

Reservationshierarkin är oberoende av produktindexhierarkin. Tack vare detta oberoende kan du implementera kategorihantering där användare kan bryta ned dimensionerna i detaljer i syfte att specificera kraven för att göra mer exakta reservationer. Din preliminära reservationshierarki bör innehålla `SiteId` och `LocationId` som komponenter eftersom de skapar partitionskonfigurationen. När du gör reservationen måste du ange en partition för produkten.

Här följer ett exempel på en preliminär reservationshierarki.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

I det här exemplet kan du göra reservationer i följande dimensionssekvenser. Du måste ange en partition för produkten när du gör reservationen. Därför är `(SiteId, LocationId)` den grundläggande hierarki som du kan använda.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

En giltig dimensionssekvens bör strikt följa reservationshierarkin, dimension för dimension. Hierarkisekvensen är till exempel `(SiteId, LocationId, SizeId)` inte giltig eftersom `ColorId` saknas.

## <a name="complete-and-update-the-configuration"></a>Slutför och uppdatera konfigurationen

När du har slutfört konfigurationen måste du utföra alla ändringar av lagersynligheten. Om du vill utföra ändringar väljer du **Uppdateringskonfiguration** i det övre högra hörnet på sidan **Konfiguration** i Power Apps.

Första gången du väljer **Uppdateringskonfiguration** efterfrågar systemet dina autentiseringsuppgifter.

- **Klient-ID** – Det Azure-program-ID som du har skapat för Lagersynlighet.
- **Klientorganisations-ID** – Ditt ID för Azure-klientorganisation.
- **Klienthemlighet** – Den hemlighet för Azure-program som du har skapat för Lagersynlighet.

När du har loggat in uppdateras konfigurationen i tjänsten Lagersynlighet.

> [!NOTE]
> Se till att validera namn, fysiska mått och dimensionsmappningar för din datakälla innan du uppdaterar konfigurationen för tjänsten Lagersynlighet. Du kan inte ändra dessa inställningar efter det att du har valt **Uppdatera konfiguration**.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exempel på standardkonfiguration

Under dess initieringsfas skapar Lagersynlighet en standardkonfiguration som beskrivs här. Du kan ändra denna konfiguration vid behov.

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
