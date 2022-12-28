---
title: Konfigurera Inventory Visibility
description: I denna artikel beskrivs hur du konfigurerar Lagersynlighet.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 2a368535c9644e174d1a2460ac0891c9dc1b1b3f
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850034"
---
# <a name="configure-inventory-visibility"></a>Konfigurera Inventory Visibility

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar Lagersynlighet via Lagersynlighet-appen i Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introduktion

Innan du börjar arbeta med Lagersynlighet måste du utföra följande konfiguration så som beskrivs i denna artikel:

- [Konfiguration för datakälla](#data-source-configuration)
- [Patritionskonfiguration](#partition-configuration)
- [Konfiguration av produktindexhierarki](#index-configuration)
- [Reservationskonfiguration (valfritt)](#reservation-configuration)
- [Förinläsningskonfiguration för fråga (valfritt)](#query-preload-configuration)
- [Exempel på standardkonfiguration](#default-configuration-sample)

## <a name="prerequisites"></a>Krav

Innan du börjar installerar och konfigurerar du tillägget Lagersynlighet enligt beskrivningen i [Installera och konfigurera Lagersynlighet](inventory-visibility-setup.md).

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>Konfigurationssidan i appen Lagersynlighet

I Power Apps, på sidan **Konfiguration** i [Lagersynlighet-appen](inventory-visibility-power-platform.md), kan du konfigurera behållningskonfigurationen och konfigurationen av preliminär reservation. När tillägget har installerats innehåller standardkonfigurationen värdet från Microsoft Dynamics 365 Supply Chain Management (datakällan `fno`). Du kan granska standardinställningarna. Baserat på dina affärsbehov och lagerbokföringskraven i det externa systemet kan du modifiera konfigurationen för att standardisera det sätt på vilket lagerändringar kan bokföras, ordnas och efterfrågas i flera olika system. I de återstående avsnitten i denna artikel beskrivs hur du använder respektive del av sidan **Konfiguration**.

När konfigurationen är slutförd, se till att du väljer **Uppdatera konfiguration** i appen.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Aktivera funktioner för lagersynlighet i Power Apps-funktionshantering

Tillägget Lagersynlighet lägger till flera nya funktioner i Power Apps-installationen. Dessa funktioner är avstängda som standard. Om du vill använda dem öppnar du sidan **Konfiguration** i och aktiverar följande funktioner på fliken **Funktionshantering**.

| Funktionshanteringsnamn | Beskrivning |
|---|---|
| *OnHandReservation* | Denna funktion låter dig skapa reservationsfunktionen för att skapa reservationer, förbruka reservationer och/eller avmarkera angivna lagerkvantiteter med hjälp av Lagersynlighet. Mer information finns i [Reservationer för Lagersynlighet](inventory-visibility-reservations.md). |
| *OnHandMostSpecificBackgroundService* | Denna funktion ger en lagersammanfattning för produkter tillsammans med alla dimensioner. Data för lagersammanfattningen synkroniseras regelbundet från Lagersynlighet. Standardsynkronisering frekvensen är en gång var 15:e minut och kan ställas in så högt som en gång var 5:e minut. Mer information finns i [Lagersammanfattning](inventory-visibility-power-platform.md#inventory-summary). |
| *OnHandIndexQueryPreloadBackgroundService* | Denna funktion hämtar och lagrar regelbundet en uppsättning samlingsdata för lagerbehållning baserat på dina förkonfigurerade dimensioner. Den innehåller en lagersammanfattning som bara omfattar dimensioner som är relevanta för din dagliga verksamhet och som är kompatibla med artiklar som aktiverats för lagerstyrningsprocesser (WMS). Mer information finns i [Aktivera och konfigurera förinlästa behållningsfrågor](#query-preload-configuration) och [förinläsning av en strömlinjeformad behållningsfråga](inventory-visibility-power-platform.md#preload-streamlined-onhand-query). |
| *OnhandChangeSchedule* | Med hjälp av denna valfria funktion får du åtkomst till funktionerna för lagerändringsschema för lagerbehållning och disponibelt att lova (ATP). Mer information finns i [Ändringsschema för lagersynlighet för lagerbehållning som är disponibel att lova](inventory-visibility-available-to-promise.md). |
| *Allokering* | Denna valfria funktion gör att Lagersynlighet kan skydda lagret (ringfencing) och överförsäljningskontroll. Mer information finns i [Lagerallokering för Lagersynlighet](inventory-visibility-allocation.md). |
| *Aktivera lagerartiklar i lagersynlighet* | Denna tillvalsfunktion gör att Lagersynlighet kan stödja artiklar som har aktiverats för lagerstyrningsprocesser (WMS). Mer information finns i [Stöd för lagersynlighet för WMS-artiklar](inventory-visibility-whs-support.md). |

> [!IMPORTANT]
> Vi rekommenderar att du antingen använder funktionen *OnHandIndexQueryPreloadBackgroundService* eller *OnHandMostSpecificBackgroundService*, inte båda. Om du aktiverar båda funktionerna påverkas prestandan.

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Hitta tjänstslutpunkten

Om du inte känner till rätt tjänstslutpunkt för Lagersynlighet öppnar du sidan **Konfiguration** i Power Apps och sedan **Visa information om tjänsten** i det övre högra hörnet. Sidan visar korrekt tjänstslutpunkt. Du hittar även slutpunkten i Microsoft Dynamics Lifecycle Services enligt beskrivningen i [Hitta slutpunkten enligt Lifecycle Services-miljö](inventory-visibility-api.md#endpoint-lcs).

> [!NOTE]
> Användning av en felaktig slutpunkt kan orsaka en misslyckad installation av lagersynlighet och fel när Supply Chain Management synkroniseras med lagersynlighet. Om du inte är säker på vad slutpunkten är kontaktar du systemadministratören. Slutpunkts-URL använder följande format:
>
> `https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Konfiguration för datakälla

Varje datakälla representerar ett system som dina data kommer från. Namn på exempeldatakällor är `fno` (som motsvarar Supply Chain Management) och `pos` (som betyder "kassa"). Standardinställningen är att Supply Chain Management konfigureras som standarddatakälla (`fno`) i Lagersynlighet.

> [!NOTE]
> Datakällan `fno` är reserverad för Supply Chain Management. Om tillägget lagersynlighet är integrerat i en Supply Chain Management-miljö rekommenderar vi att du inte tar bort konfigurationer som är relaterade till `fno` i datakällan.

Följ dessa steg för att lägga till en datakälla.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla**, välj **Ny datakälla** för att lägga till en datakälla (t.ex. `ecommerce` eller ett annat beskrivande datakäll-ID).

> [!NOTE]
> När du lägger till en datakälla måste du kontrollera namn, fysiska mått och dimensionsmappningar för datakällan innan du uppdaterar konfigurationen för tjänsten Lagersynlighet. Du kan inte ändra dessa inställningar efter det att du har valt **Uppdatera konfiguration**.

Datakällskonfigurationen innehåller följande delar:

- Dimensioner (dimensionsmappning)
- Fysiska mått
- Beräknade mått

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensioner (dimensionsmappning)

Syftet med dimensionskonfigurationen är att standardisera integreringen av flera system för bokföring av händelser och frågor, baserat på dimensionskombinationer. Lagersynligheten innehåller en lista över basdimensioner som kan mappas från datakällans dimensioner. Det finns 33 dimensioner att tillgå för mappning.

- Om du använder Supply Chain Management som en av dina datakällor mappas som standard 13 dimensioner till standarddimensionerna i Supply Chain Management. Tolv andra dimensioner (`inventDimension1` till `inventDimension12`) mappas till anpassade dimensioner i Supply Chain Management. Återstående åtta dimensioner (`ExtendedDimension1` till `ExtendedDimension8`) som du kan mappa till externa datakällor.
- Om du inte använder Supply Chain Management som en av dina datakällor kan du mappa dimensionerna fritt. Följande tabell visar den fullständiga listan över tillgängliga dimensioner.

> [!NOTE]
> Om du använder Supply Chain Management och ändrar standarddimensionsmappningarna mellan Supply Chain Management och Lagersynlighet kommer den ändrade dimensionen inte att synkronisera data. Om din dimension inte finns i standarddimensionslistan och du använder en extern datakälla rekommenderar vi att du använder `ExtendedDimension1` via `ExtendedDimension8` för att utföra mappningen.

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

Externa system kan få åtkomst till Lagersynlighet genom sina RESTful-API:er. För integreringen låter Lagersynlighet dig konfigurera den *externa datakällan* och mappningen från de *externa dimensionerna* till *basdimensionerna*. Här följer ett exempel på en mappningstabell för dimensioner.

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
1. På fliken **Datakälla** väljer du den datakälla där du vill mappa dimensioner. I avsnittet **Dimensionsmappningar**, välj **Lägg till** om du vill lägga till dimensionsmappningar.

    ![Lägga till dimensionsmappningar](media/inventory-visibility-dimension-mapping.png "Lägga till dimensionsmappningar")

1. I fältet **Dimensionsnman** anger du källdimensionen.
1. I fältet **Till basdimension** anger du den dimension i Lagersynlighet som du vill mappa.
1. Välj **Spara**.

Du har till exempel redan skapat en datakälla med namnet `ecommerce` och den innehåller en produktfärgsdimension. I det här fallet, för att göra mappningen, kan du först lägga till `ProductColor` till fältet **Dimensionsnamn** i `ecommerce` datakällan och välj `ColorId` i fältet **Till basdimension**.

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Fysiska mått

När en datakälla bokför en lagerändring i Lagersynlighet bokför den denna ändring med hjälp av *fysiska mått*. Fysiska mått ändrar kvanheten och återspeglar lagerstatusen. Du kan definiera dina egna fysiska mått, baserat på dina behov. Frågor kan baseras på de fysiska måtten.

Lagersynlighet innehåller en lista över fysiska standardmått som är mappade till Supply Chain Management (`fno`-datakällan). Dessa fysiska standardmått tas från lagertransaktionens status på sidan **Lagerbehållningslista** i Supply Chain Management (**Lagerstyrning \> Förfrågningar och rapporter \> Behållningslista**). Följande tabell innehåller ett exempel på fysiska mått.

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
1. Välj den **datakälla** som fysiska mått ska läggas till i (till exempel datakällan) på fliken `ecommerce` datakälla. I avsnittet **Fysiska mått** väljer du **Lägg till** och ange måttets namn (t.ex. `Returned` om du vill registrera returnerade kvantiteter i denna datakälla till lagersynlighet). Spara ändringarna.

### <a name="extended-dimensions"></a>Utbyggda dimensioner

Kunder som vill använda externa datakällor i datakällan kan dra nytta av den utbyggbarhet som Dynamics 365 erbjuder genom att skapa [klasstillägg](../../fin-ops-core/dev-itpro/extensibility/class-extensions.md) för klasserna `InventOnHandChangeEventDimensionSet` och `InventInventoryDataServiceBatchJobTask`.

Se till att synkronisera med databasen efter att du har skapat tilläggen för att de anpassade fälten ska läggas till i `InventSum` registret. Du kan sedan referera till dimensionsavsnittet tidigare i den här artikeln för att mappa dina anpassade dimensioner till någon av de åtta utbyggda dimensionerna i `BaseDimensions` i Lager.

> [!NOTE] 
> Mer information om hur du skapar tillägg finns på [startsidan utbyggbarhet](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

### <a name="calculated-measures"></a>Beräknade mått

Du kan använda Lagersynlighet när du vill söka efter både fysiska lagermått *och anpassade beräknade mått*. Beräknade mått ger en anpassad beräkningsformel som består av en kombination av fysiska mått. Med hjälp av denna funktion kan du definiera en uppsättning fysiska mått som ska läggas till, och/eller en uppsättning fysiska mått som dras ifrån, för att generera det anpassade måttet.

> [!IMPORTANT]
> Ett beräknat mått är en sammansättningen av fysiska mått. Formeln kan endast innehålla fysiska mått utan dubbletter, inte beräknade mått.

Konfigurationen låter dig definiera en uppsättning beräknade måttformler som inkluderar modifierare av addition eller subtraktion för att få den totala aggregerade utdatakvantiteten.

Följ stegen nedan för att konfigurera ett anpassat beräknat mått.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Beräknat mått** väljer du **Ny måttberäkning** om du vill lägga till ett beräknat mått.
1. Ställ in följande fält för det nya beräknade måttet:

    - **Nytt beräknat måttnamn** – Ange namnet på det beräknade måttet.
    - **Datakälla** – Välj den datakälla för att inkludera det nya beräknade måttet. Frågesystemet är en datakälla.

1. Välj **Lägg till** om du vill lägga till en modifierare till det nya beräknade måttet.
1. Ställ in följande fält för den nya modifieraren:

    - **Modifierare** – Välj typ av modifierare (*Tillägg* eller *Avdrag*).
    - **Datakälla** – Välj den datakälla där måttet som tillhandahåller ändringsvärdet ska hittas.
    - **Mått** – Välj namnet på måttet (från den valda datakällan) som ger modifieraren värdet.

1. Upprepa steg 5 till 6 tills du har lagt till alla nödvändiga modifierare och slutfört formeln för ditt beräknade mått.
1. Välj **Spara**.

Ett modeföretag har till exempel verksamhet i tre datakällor:

- `pos`– Motsvarar butikskanal.
- `fno` – Motsvarar Supply Chain Management.
- `ecommerce` – Motsvarar din webbkanal.

Utan beräknade mått, när du frågar efter produkt D0002 (skåp) under plats 1, lager 11 och `ColorID` dimensionsvärdet `Red`, du kan få följande frågeresultat, som visar lagerkvantiteter under varje förkonfigurerat fysiskt mått. Du har däremot ingen insyn i de totala tillgängliga för reservationskvantiteter i alla dina datakällor.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
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
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `received` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `scheduled` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `issued` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `reserved` | `Subtraction` |

När denna beräkningsformel används kommer det nya frågeresultatet att omfatta det anpassade måttet.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CrossChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

`MyCustomAvailableforReservation`-resultatet som baseras på beräkningsinställningen i de anpassade måtten är 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Patritionskonfiguration

För närvarande består partitionskonfigurationen av två grunddimensioner (`SiteId` och `LocationId`) som anger hur data distribueras. Åtgärder under samma partition kan leverera högre prestanda till lägre kostnad. Följande tabell visar standardpartitionskonfigurationen som Tillägg för lagersynlighet tillhandahåller.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

Lösningen innehåller som standard den här partitionskonfigurationen. Därför *måste du inte definiera själv*.

> [!IMPORTANT]
> Anpassa inte standardkonfigurationen för partitionen. Om du tar bort eller ändrar den kan det leda till oväntade fel.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Konfiguration av produktindexhierarki

För det mesta kommer lagerbehållningsfrågan inte bara att vara på den högsta "total"-nivån. Istället kanske du också vill visa resultat som sammanställts baserat på lagerdimensionerna.

Lagersynlighet ger större flexibilitet eftersom du då kan konfigurerar *index* för att förbättra prestandan för dina frågor. Dessa index baseras på en dimension eller en kombination av dimensioner. Ett index består av ett *uppsättningsnummer*, en *dimension* och en *hierarki* enligt definionen i följande tabell.

| Namn | beskrivning |
|---|---|
| Ange nummer | Dimensioner som tillhör samma uppsättning (index) grupperas tillsammans, och samma uppsättningsnummer tilldelas dem. |
| Dimension | De basdimensioner som frågeresultatet sammanställs på. |
| Hierarki | Med hierarkin kan du öka prestandan för specifika dimensionskombinationer när du används i filter och frågeparametrar grupp för. Om du till exempel ställer in en dimensionsuppsättning med hierarkisekvensen `(ColorId, SizeId, StyleId)`, kan frågor som är relaterade till fyra dimensionskombinationer bearbetas snabbare i systemet. Den första kombinationen är tom, den andra är `(ColorId)`, den tredje är `(ColorId, SizeId)`, och den fjärde är `(ColorId, SizeId, StyleId)`. Andra kombinationer spedlar inte upp. Filter begränsas inte per order, utan måste finnas inuti dessa dimensioner om du vill förbättra deras prestanda. Mer information finns i följande exempel. |

Följ dessa steg för att konfigurera ditt index för produkthierarki.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Index för produkthierarki**, i avsnittet **Dimensionsmappningar**, väljer du **Lägg till** om du vill lägga till dimensionsmappningar.
1. En lista över index finns som standard. Om du vill ändra ett befintligt index väljer du **Redigera** eller **Lägg till** i avsnittet för relevant index. Välj **Ny indexuppsättning** om du vill skapa en ny indexuppsättning. I fältet **Dimension** väljer du i listan över basdimensioner för respektive rad i respektive indexuppsättning. Värden för följande fält genereras automatiskt:

    - **Ange nummer** – Dimensioner som tillhör samma grupp (index) grupperas tillsammans och samma uppsättningsnummer tilldelas dem.
    - **Hierarki** – Med hierarkin kan du öka prestandan för specifika dimensionskombinationer när du används i filter och frågeparametrar grupp för.

> [!TIP]
> Nedan finns några tips att tänka på när du konfigurerar din indexhierarki:
>
> - Basdimensioner som definieras i partitionskonfigurationen ska inte definieras i indexkonfigurationer. Om en basdimension definieras igen i indexkonfigurationen kommer du inte att kunna fråga efter detta index.
> - Om du bara behöver fråga lager som aggregeras av alla dimensionskombinationer bör du konfigurera ett enda index som innehåller basdimensionen `Empty`.

### <a name="example"></a>Exempel

Detta avsnitt innehåller ett exempel som visar hur hierarkin fungerar.

Följande tabell innehåller en lista över tillgängligt lager för detta exempel.

| Objekt | ColorId | SizeId | StyleId | Antal |
|---|---|---|---|---|
| D0002 | Svart | Litet | Bred | 1 |
| D0002 | Svart | Litet | Vanlig | 2 |
| D0002 | Svart | Stort | Bred | 3 |
| D0002 | Svart | Stort | Vanlig | 4 |
| D0002 | Röd | Litet | Bred | 5 |
| D0002 | Röd | Litet | Vanlig | 6 |
| D0002 | Röd | Stort | Vanlig | 7 |

Följande tabell visar hur indexhierarkin ställs in.

| Ange nummer | Dimension | Hierarki |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

Med indexet kan du fråga efter lagerbehållningen på följande sätt:

- `()` – Gruppering efter alla

    - D0002, 28

- `(ColorId)` – Gruppering efter alla `ColorId`

    - D0002, svart, 10
    - D0002, röd, 18

- `(ColorId, SizeId)` – Gruppering efter kombinationen `ColorId` och `SizeId`

    - D0002, svart, liten, 3
    - D0002, svart, stor, 7
    - D0002, röd, liten, 11
    - D0002, röd, stor, 7

- `(ColorId, SizeId, StyleId)` – Gruppering efter kombinationen `ColorId`, `SizeId` och `StyleId`

    - D0002, svart, liten, bred 1
    - D0002, svart, liten, vanlig 2
    - D0002, svart, stor, bred 3
    - D0002, svart, stor, vanlig 4
    - D0002, röd, liten, bred 5
    - D0002, röd, liten, vanlig 6
    - D0002, röd, stor, vanlig 7

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Reservationskonfiguration (valfritt)

Reservationskonfiguration krävs om du vill använda funktionen för preliminär reservation. Konfigurationen består av två grundläggande delar:

- Preliminär reservationsmappning
- Preliminär reservationshierarki

### <a name="soft-reservation-mapping"></a>Preliminär reservationsmappning

När du gör en reservation kanske du vill veta om lagerbehållningen för närvarande är tillgänglig för reservation. Valideringen är kopplad till ett beräknat mått som representerar en beräkningsformel för en kombination av fysiska mått.

Genom att konfigurera mappningen från det fysiska måttet till det beräknade måttet aktiverar du tjänsten Lagersynlighet för att automatiskt validera reservationstillgängligheten, baserat på det fysiska måttet.

Innan du konfigurerar den här mappningen måste de fysiska måtten, de beräknade måtten och dessas datakällor definieras på flikarna **Datakälla** och **Beräknat mått** på sidan **Konfiguration** i Power Apps (enligt beskrivet i denna artikel).

Om du vill definiera mappningen för preliminär reservation följer du dessa steg.

1. Definiera det fysiska mått som fungerar som mått på preliminär reservation (till exempel `SoftReservPhysical`).
1. På fliken **Beräknat mått** på fliken **Konfiguration** definierar du det *beräknade måttet för reservation* (AFR) som innehåller den AFR-beräkningsformel som du vill mappa till det fysiska måttet. Du kan till exempel konfigurera `AvailableToReserve` (tillgängligt för reservation) så att detta mappas till det tidigare definierade fysiska måttet `SoftReservPhysical`. På det här sättet kan du se vilka kvantiteter med lagerstatusen `SoftReservPhysical` som är tillgängliga för reservation. Följande tabell visar beräkningsformeln för AFR.

    | Beräkningstyp | Datakälla | Fysiskt mått |
    |---|---|---|
    | Tillägg | `fno` | `AvailPhysical` |
    | Tillägg | `pos` | `Inbound` |
    | Subtraktion | `pos` | `Outbound` |
    | Subtraktion | `iv` | `SoftReservPhysical` |

    Vi rekommenderar att du konfigurerar det beräknade måttet så att det innehåller det fysiska mått som reservationsmåttet baseras på. På det här sättet påverkas den beräknade måttkvantiteten av reservationsmåttkvantiteten. I det här exemplet ska därför det beräknade måttet `AvailableToReserve` för datakällan `iv` innehålla det fysiska måttet `SoftReservPhysical` från `iv` som en komponent.

1. Öppna sidan **Konfiguration**.
1. På fliken **Preliminär reservationsmappning** konfigurerar du mappnignen från fysiskt mått till beräkna mått. I det föregående exemplet kan du använda följande inställningar för att mappa `AvailableToReserve`till det tidigare definierade fysiska `SoftReservPhysical`-måttet.

    | Datakälla för fysiskt mått | Fysiskt mått | Tillgänglig för datakälla för reservation | Tillgänglig för beräknat reservationsmått |
    |---|---|---|---|
    | `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Om du inte kan redigera fliken **Preliminär reservationsmappning** kan du behöva du aktivera funktionen *OnHandReservation* på fliken **Funktionshantering**.

När du gör reservationer i `SoftReservPhysical` hittar Lagersynlighet nu automatiskt `AvailableToReserve` och dess relaterade beräkningsformel för att utföra reservationsvalideringen.

Du har till exempel följande lagerbehållning i Lagersynlighet.

```json
{
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservPhysical": 90
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

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservPhysical`  
= 70 + 50 – 20 – 90  
= 10

Om du därför försöker göra reservationer på `iv.SoftReservPhysical` och kvantiteten är mindre än eller lika med `AvailableToReserve` (10) kan mjuka reservationen lyckas.

> [!NOTE]
> När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True`betyder att valideringen krävs, medan ett värde på `False` betyder att valideringen inte krävs (även om du kan sluta med en negativ `AvailableToReserve` kvantitet, kommer systemet fortfarande att tillåta dig att mjuka reservera). Standardvärdet är `True`.

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

## <a name="available-to-promise-configuration-optional"></a>Konfiguration av tillgänglig för löfte (valfritt)

Du kan konfigurera lagersynlighet så att du kan tidsplanera framtida ändringar av lagerbehållningen och beräkna kvantiteter som är tillgängliga att lova. ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund i nästa period. Om du använder den här beräkningen kan du öka möjligheten att uppfylla ordern mycket. Om du vill använda funktionen måste du aktivera den på fliken **Funktionshantering** och sedan konfigurera den på fliken **ATP-inställningar**. Mer information finns i [Lagerinventeringsbehållningens ändringsscheman och som är tillgängliga att lova](inventory-visibility-available-to-promise.md).

## <a name="turn-on-and-configure-preloaded-on-hand-queries-optional"></a><a name="query-preload-configuration"></a>Aktivera och konfigurera förinlästa behållningsfrågor (valfritt)

Lagersynlighet kan regelbundet hämta och lagra en uppsättning samlingsdata för lagerbehållning baserat på dina förkonfigurerade dimensioner. Detta ger följande fördelar:

- En vy som lagrar en lagersammanfattning som bara innehåller de dimensioner som är relevanta för din dagliga verksamhet.
- En lagersammanfattning som är kompatibel med artiklar som aktiverats för lagerstyrningsprocesser (WMS).

Mer information om hur du arbetar med den här funktionen finns i [Förinläsning av en strömlinjeformad behållningsfråga](inventory-visibility-power-platform.md#preload-streamlined-onhand-query).

> [!IMPORTANT]
> Vi rekommenderar att du antingen använder funktionen *OnHandIndexQueryPreloadBackgroundService* eller *OnHandMostSpecificBackgroundService*, inte båda. Om du aktiverar båda funktionerna påverkas prestandan.

Följ dessa steg för att konfigurera funktionen:

1. Logga in på Power Apps för lagersynlighet.
1. Gå till **Konfiguration \> Funktionshantering och inställningar**.
1. Om funktionen *OnHandIndexQueryPreloadBackgroundService* redan har aktiverats rekommenderar vi att du stänger av den för tillfället eftersom rensningsprocessen kan ta mycket lång tid att slutföra. Du kan aktivera den senare under denna procedur.
1. Öppna fliken **Förinläsningsinställningar** .
1. I avsnittet **Steg 1: Rensa förinläst lager**, välj **Rensa** om du vill rensa databasen och gör den klar att acceptera dina nya gruppera efter-inställning.
1. I avsnittet **Steg 2: Ställ in grupp efter värden** i fältet **Gruppera resultat efter** anger du en kommaavgränsad lista med fältnamn som frågeresultaten ska grupperas efter. När det finns data i förinläsningsdatabasen kan du inte ändra den här inställningen förrän du har rensat databasen, enligt beskrivningen i föregående steg.
1. Gå till **Konfiguration \> Funktionshantering och inställningar**.
1. Aktivera funktionen *OnHandIndexQueryPreloadBackgroundService*.
1. Välj **Uppdatera konfiguration** i det övre högra hörnet på sidan **Konfiguration** om du vill utföra ändringarna.

## <a name="complete-and-update-the-configuration"></a>Slutför och uppdatera konfigurationen

När du har slutfört konfigurationen måste du utföra alla ändringar av lagersynligheten. Följ dessa steg för att genomföra dina ändringar.

1. I Power Apps, på sidan **Konfiguration**, välj **Uppdateringskonfiguration** i det övre högra hörnet. 
1. Inloggningsuppgifterna för systembegäranden. Ange följande värden:

    - **Klient-ID** – Det Azure-program-ID som du har skapat för Lagersynlighet.
    - **Klientorganisations-ID** – Ditt ID för Azure-klientorganisation.
    - **Klienthemlighet** – Den hemlighet för Azure-program som du har skapat för Lagersynlighet.

    För mer information om dessa referenser och hur du hittar dem, se [Installera och konfigurera lagersynlighet](inventory-visibility-setup.md).

    > [!IMPORTANT]
    > Se till att validera namn, fysiska mått och dimensionsmappningar för din datakälla innan du uppdaterar konfigurationen. Du kan inte ändra dessa inställningar efter det att du har valt att uppdatera den.

1. När du har loggat in väljer du **Uppdatera konfiguration** igen. Systemet tillämpar dina inställningar och visar vad som har ändrats.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exempel på standardkonfiguration

Under dess initieringsfas skapar Lagersynlighet en standardkonfiguration som beskrivs här. Du kan ändra denna konfiguration vid behov.

### <a name="data-source-configuration"></a>Konfiguration för datakälla

#### <a name="configuration-of-the-iv-data-source"></a>Konfiguration för iv-datakälla

Detta avsnitt beskriver hur `iv`-datakällan konfigureras.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Fysiska mått konfigurerade för datakällan "iv"

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

#### <a name="configuration-of-the-fno-data-source"></a>Konfiguration datakällan "fno"

Detta avsnitt beskriver hur `fno`-datakällan konfigureras.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Dimensionsmappningar för datakällan "fno"

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

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Fysiska mått konfigurerade för datakällan "fno"

Följande fysiska mått konfigureras för `fno`-datakällan:

- `Arrived`
- `PhysicalInvent`
- `ReservPhysical`
- `onorder`
- `notspecified`
- `availordered`
- `availphysical`
- `picked`
- `postedqty`
- `quotationreceipt`
- `received`
- `ordered`
- `ReservOrdered`

#### <a name="configuration-of-the-pos-data-source"></a>Konfiguration för datakällan "pos"

Detta avsnitt beskriver hur `pos`-datakällan konfigureras.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fysiska mått för datakällan "pos"

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

#### <a name="configuration-of-the-iom-data-source"></a>Konfiguration för datakällan "iom"

Följande fysiska mått konfigureras för `iom`-datakällan (Intelligent Order Management):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Konfiguration för datakällan "erp"

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
| `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Reservationshierarki

Följande tabell visar standardhierarkin för reservation.

| Basdimension | Hierarki |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
