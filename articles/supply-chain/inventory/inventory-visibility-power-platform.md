---
title: Appen Lagersynlighet
description: I detta ämne beskrivs hur du använder appen för Lagersynlighet.
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
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345012"
---
# <a name="inventory-visibility-app"></a>appen Lagersynlighet

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

I detta ämne beskrivs hur du använder appen för Lagersynlighet.

Lagersynligheten innehåller en modellbaserad app för visualisering. Appen innehåller tre sidor: **Konfiguration**, **Verksamhetens synlighet** och **Lagersammanfattning**. Den har följande värden:

- Den tillhandahåller ett användargränssnitt (UI) för praktisk konfiguration och konfiguration av preliminär reservation.
- De stöder lagerbehållningsfrågor i realtid för olika dimensionskombinationer.
- Den tillhandahåller ett användargränssnitt för bokföring av reservationsförfrågningar.
- Den tillhandahåller en anpassad vy av lagerbehållningen för produkter tillsammans med alla dimensioner

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar installerar och konfigurerar du tillägget Lagersynlighet enligt beskrivningen i [Konfigurera Lagersynlighet](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Inställningar

På sidan **Konfiguration** kan du konfigurera behållningskonfigurationen och konfigurationen för preliminär reservation. När tillägget har installerats innehåller standardkonfigurationen värdet från Microsoft Dynamics 365 Supply Chain Management (datakällan `fno`). Du kan granska standardinställningen. Baserat på dina affärsbehov och lagerbokföringskraven i det externa systemet kan du modifiera konfigurationen i [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) för att standardisera det sätt på vilket lagerändringar kan bokföras, ordnas och efterfrågas i flera olika system.

### <a name="define-data-sources"></a>Definiera datakällor

Du definierar varje *datakälla* som du vill integrera med Lagersynlighet. Lagersynligheten stöder integrering med olika datakällor, till exempel ditt kassasystem (POS), Supply Chain Management och andra externa system. Standardinställningen är att Supply Chain Management konfigureras som standarddatakälla (`fno`) i Lagersynlighet.

Följ dessa steg för att lägga till en datakälla.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla** väljer du **Ny datakälla** om du vill lägga till en datakälla.

> [!NOTE]
> När du lägger till en datakälla måste du kontrollera namn, fysiska mått och dimensionsmappningar för datakällan innan du uppdaterar konfigurationen för tjänsten Lagersynlighet. Du kan inte ändra dessa inställningar efter det att du har valt **Uppdatera konfiguration**.

### <a name="set-up-dimension-mappings"></a>Ställ in dimensionsmappningar

Lagersynligheten innehåller en lista över basdimensioner som kan mappas från datakällans dimensioner. Det finns 33 dimensioner att tillgå för mappning.

- Om du använder Supply Chain Management som en av dina datakällor mappas som standard 13 dimensioner till standarddimensionerna i Supply Chain Management. Tolv andra dimensioner (`inventDimension1` till `inventDimension12`) mappas till anpassade dimensioner i Supply Chain Management. Återstående åtta dimensioner är utökade dimensioner som du kan mappa till externa datakällor.
- Om du inte använder Supply Chain Management som en av dina datakällor kan du mappa dimensionerna fritt. Följande tabell visar den fullständiga listan över tillgängliga dimensioner.

> [!NOTE]
> Om din dimension inte finns i standarddimensionslistan och du använder en extern datakälla rekommenderar vi att du använder `ExtendedDimension1` via `ExtendedDimension8` för att utföra mappningen.

| Dimensionstyp | Dimensionsnamn |
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
| Övriga | `VersionId` |
| Lager (anpassat) | `InventDimension1` via `InventDimension12` |
| Övriga | `ExtendedDimension1` via `ExtendedDimension8` |

Om du vill lägga till dimensionsmappningar följer du dessa steg.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla**, i avsnittet **Dimensionsmappningar**, väljer du **Lägg till** om du vill lägga till dimensionsmappningar.
1. I fältet **Dimensionsnman** anger du källdimensionen.
1. I fältet **Till basdimension** anger du den dimension i Lagersynlighet som du vill mappa.
1. Välj **Spara**.

![Lägga till dimensionsmappningar](media/inventory-visibility-dimension-mapping.png "Lägga till dimensionsmappningar")

Om datakällan till exempel innehåller en produktfärgsdimension kan du mappa den till basdimensionen `ColorId` för att lägga till en anpassad `ProductColor`- dimension i `exterchannel`-datakällan. Den mappas sedan till `ColorId`-basdimensionen.

## <a name="create-a-physical-measure"></a>Skapa ett fysiskt mått

När en datakälla bokför en lagerändring i Lagersynlighet bokför den denna ändring med hjälp av *fysiska mått*. Fysiska mått är modifierare som återspeglar summerad status för lagertransaktioner. Frågor kan baseras på de fysiska måtten.

Lagersynligheten har en lista över fysiska standardmått. Dessa fysiska standardmått tas från lagertransaktionens status på sidan **Lagerbehållningslista** i Supply Chain Management (**Lagerstyrning \> Förfrågningar och rapporter \> Behållningslista**).

| Modifierare | Namn |
|---|---|
| `PhysicalInvent` | Fysiskt lager |
| `ReservPhysical` | Fysiskt reserverat |
| `AvailPhysical` | Fysiskt disponibelt |
| `ReservOrdered` | Beställt reserverat |
| `PostedQty` | Bokförd kvanhet |
| `Deducted` | Avdraget |
| `Picked` | Plockad |
| `Received` | Mottaget |
| `Registered` | Registrerat |
| `Arrived` | Infört |
| `Ordered` | Beställt |
| `OnOrder` | Har beställts |
| `QuotationReceipt` | Offertinleverans |
| `QuotationIssue` | Offertärende |

Om datakällan är Supply Chain Management behöver du inte skapa de fysiska standardmåtten på nytt. För externa datakällor kan du emellertid skapa nya fysiska mått genom att följa dessa steg.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Datakälla**, i avsnittet **Fysiska mått** väljer du **Lägg till**, anger ett källmåttnamn samt sparar dina ändringar.

## <a name="define-the-product-hierarchy-index"></a>Definiera produkthierarkiindex

Genom att ställa in sammanlagda dimensionsgrupper kan du använda Lagersynbarhet för att söka efter status för lagerbehållning. I Lagersynlighet kallas varje dimensionsgrupp för ett *index*. Varje index motsvarar ett fast nummer. Du kan bestämma vilka dimensioner som ska användas för att ställa in indexeringen, baserat på hur du ställer in frågor om lagersynlighet.

Följ dessa steg för att konfigurera ditt index för produkthierarki.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. På fliken **Index för produkthierarki**, i avsnittet **Dimensionsmappningar**, väljer du **Lägg till** om du vill lägga till dimensionsmappningar.
1. En lista över index finns som standard. Om du vill ändra ett befintligt index väljer du **Redigera** eller **Lägg till** i avsnittet för relevant index. Välj **Ny indexuppsättning** om du vill skapa en ny indexuppsättning. I fältet **Dimension** väljer du i listan över basdimensioner för respektive rad i respektive indexuppsättning. Värden för följande fält genereras automatiskt:

    - **Ange nummer** – Dimensioner som tillhör samma grupp (index) grupperas tillsammans och samma uppsättningsnummer tilldelas dem.
    - **Hierarki** – Hierarkin används för att definiera de dimensionskombinationer som stöds och som kan efterfrågas i en dimensionsgrupp (index). Om du till exempel ställer in en dimensionsgrupp med hierarkisekvsekvensen *Format*, *Färg* och *Storlek* stöds resultatet av tre frågegrupper. Den första gruppen gäller endast formatet. Den andra gruppen är en kombination av format och färg. Den tredje gruppen är en kombination av format, färg och storlek. Övriga kombinationer stöds inte.

Mer information finns i [Hierarkikonfiguration för produktindex](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Exempel

Detta avsnitt innehåller ett exempel som visar hur hierarkin fungerar. Följande tabell innehåller en lista över tillgängligt lager för detta exempel.

| Artikel | Utförande | Färg | Storlek | Antal |
|---|---|---|---|---|
| I0001 | Bred | Svart | Litet | 1 |
| I0001 | Bred | Svart | Stort | 2 |
| I0001 | Bred | Rött | Litet | 3 |
| I0001 | Vanlig | Svart | Litet | 4 |
| I0001 | Vanlig | Svart | Stort | 5 |
| I0001 | Vanlig | Rött | Litet | 6 |
| I0001 | Vanlig | Rött | Stort | 7 |

Följande tabell visar hur indexhierarkin ställs in.

| Nyckel | Ange nummer | Hierarki |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Dimensionskombinationen för frågan om Lagersynlighet är *Format*, *Färg* och *Storlek* baserat på föregående inställningar. Med hjälp av hierarkiinställningen kan externa system ställa frågor angående lagerbehållningen på följande sätt:

- `()` – Gruppering efter alla. Detta är resultatet:

    - I0001, 28

- `(StyleId)` – Gruppering efter format. Detta är resultatet:

    - I0001, bred, 6
    - I0001, standard, 22

- `(StyleId, ColorId)` – Gruppering efter en kombination av format och färg. Detta är resultatet:

    - I0001, bred, svart, 3
    - I0001, bred, röd, 3
    - I0001, vanlig, svart, 9
    - I0001, vanlig, röd, 13

- `(StyleId, ColorId, SizeId)` – Gruppering efter en kombination av format, färg och storlek. Detta är resultatet:

    - I0001, bred, svart, liten, 1
    - I0001, bred, svart, stor, 2
    - I0001, bred, röd, liten, 3
    - I0001, vanlig, svart, liten, 4
    - I0001, vanlig, svart, stor, 5
    - I0001, vanlig, röd, liten, 6
    - I0001, vanlig, röd, stor, 7

## <a name="set-up-a-custom-calculated-measure"></a>Ställ in ett anpassat beräknat mått

Du kan använda Lagersynlighet när du vill söka efter både fysiska lagermått *och anpassade beräknade mått*.

Med konfigurationen kan du definiera en uppsättning modifierare som läggs till eller dras ifrån för att få den totala sammanlagda utleveranskvanheten.

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

Följande tabell ger ett exempel på det anpassade beräknade måttet `MyCustomAvailableforReservation`. Mer information om det här exemplet finns i [Konfiguration för datakälla](inventory-visibility-configuration.md#data-source-configuration).

| Datakälla för beräknat mått | Beräknat mått | Modifierarare för datakälla | Modifierare | Modifierartyp |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Konfigurera en preliminär reservationsmappning

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Innan du kan redigera fliken **Mappning med preliminär reservation** måste du aktivera funktionen *OnHandReservation* på fliken **Funktionshantering**.

Genom att ställa in mappningen från det fysiska måttet till det beräknade måttet aktiverar du tjänsten Lagersynlighet för att automatiskt validera reservationstillgängligheten, baserat på det fysiska måttet.

Innan du ställer in den här mappningen måste de fysiska måtten, de beräknade måtten och dessas datakällor definieras på flikarna **Datakälla** och **Beräknat mått** på sidan **Konfiguration** i Power Apps (enligt beskrivet i detta ämne).

Om du vill definiera mappningen för preliminär reservation följer du dessa steg.

1. Definiera det fysiska mått som fungerar som mått på preliminär reservation (till exempel `softreservordered`).
1. På fliken **Beräknat mått** på fliken **Konfiguration** definierar du det *beräknade måttet för reservation* (AFR) som innehåller den AFR-beräkningsformel som du vill mappa till det fysiska måttet. Du kan till exempel konfigurera `availforreserv` (tillgängligt för reservation) så att detta mappas till det tidigare definierade fysiska måttet `softreservordered`. På det här sättet kan du se vilka kvantiteter med lagerstatusen `softreservordered` som är tillgängliga för reservation. Följande tabell visar beräkningsformeln för AFR.

    | Modifierare | Datakälla | Mått |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Öppna sidan **Konfiguration**.
1. På fliken **Preliminär reservationsmappning** konfigurerar du mappnignen från fysiskt mått till beräkna mått. I det föregående exemplet kan du använda följande inställningar för att mappa `availforreserv`till det tidigare definierade fysiska `softreservordered`-måttet.

    | Datakälla för fysiskt mått | Fysiskt mått | Tillgänglig för datakälla för reservation | Tillgänglig för beräknat reservationsmått |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Konfigurera en preliminär reservationshierarki

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Innan du kan redigera fliken **Hierarki med preliminär reservation** måste du aktivera funktionen *OnHandReservation* på fliken **Funktionshantering**.

Reservationshierarkin beskriver den dimensionssekvens som måste anges när reservationer görs. Detta fungerar på samma sätt som produktindexhierarkin fungerar för behållningsfrågor.

Reservationshierarkin kan skilja sig åt från hierarkin för behållningsindex. Tack vare detta oberoende kan du implementera kategorihantering där användare kan bryta ned dimensionerna i detaljer i syfte att specificera kraven för att göra mer exakta reservationer.

#### <a name="example"></a>Exempel

Följande reservationshierarki har konfigurerats i systemet.

| Dimension | Hierarki |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Med denna reservationshierarki kan du skapa reservationer i följande dimensionsorder:

- `()` – Ingen dimension har angetts.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

Dimensionsordern bör strikt följa reservationshierarkin, dimension för dimension. Reservationer som har `(ColorId, StyleId)` tillåts exempelvis inte i det här exemplet eftersom denna sekvens inte har definierats i reservationshierarkin.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Hantering av kontrollfunktioner

Tillägget Lagersynlighet innehåller funktioner som *OnHandReservation* och *OnHandMostSpecificBackgroundService*. Dessa funktioner är avstängda som standard. Om du vill använda dem öppnar du sidan **Konfiguration** i Power Apps innan du aktiverar dem på fliken **Funktionshantering**.

### <a name="complete-and-update-the-configuration"></a>Slutför och uppdatera konfigurationen

När du har slutfört konfigurationen måste du utföra alla ändringar av lagersynligheten. Om du vill utföra ändringar väljer du **Uppdateringskonfiguration** i det övre högra hörnet på sidan **Konfiguration** i Power Apps.

Första gången du väljer **Uppdateringskonfiguration** efterfrågar systemet dina autentiseringsuppgifter.

- **Klient-ID** – Det Azure-program-ID som du har skapat för Lagersynlighet.
- **Klientorganisations-ID** – Ditt ID för Azure-klientorganisation.
- **Klienthemlighet** – Den hemlighet för Azure-program som du har skapat för Lagersynlighet.

När du har loggat in uppdateras konfigurationen i tjänsten Lagersynlighet.

> [!NOTE]
> Se till att validera namn, fysiska mått och dimensionsmappningar för din datakälla innan du uppdaterar konfigurationen för tjänsten Lagersynlighet. Du kan inte ändra dessa inställningar efter det att du har valt **Uppdatera konfiguration**.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Hitta tjänstslutpunkten

Om du inte känner till rätt tjänstslutpunkt för Lagersynlighet öppnar du sidan **Konfiguration** i Power Apps och sedan **Visa tjänstslutpunkt** i det övre högra hörnet. Sidan visar korrekt tjänstslutpunkt.

## <a name="operational-visibility"></a>Verksamhetens synlighet

Sidan **Verksamhetens synlighet** innehåller resultaten av en realtidsfråga om lagerbehållning, baserat på olika dimensionskombinationer. När funktionen *OnHandReservation* är aktiverad kan du också bokföra reservationsbegäranden från sidan **Verksamhetssynlighet**.

### <a name="on-hand-query"></a>Behållningsfråga

Fliken **Behållningsfråga** visar resultaten av en realtidsfråga om lagerbehållning.

När du väljer fliken **Behållningsfråga** begär systemet dina autentiseringsuppgifter så att det får den ägartoken som krävs för att fråga efter tjänsten Lagersynlighet. Du kan klistra in ägartoken i fältet **BearerToken** och stänga dialogrutan. Du kan sedan bokföra en begäran om behållningsfråga.

Om ägartoken inte är giltig eller har löpt ut måste du klistra in en ny i fältet **BearerToken**. Ange rätt värde för **Kund-ID**, **Klientorganisations-ID**, **Klienthemlighet** och sedan **Uppdatera**. Systemet får automatiskt en ny, giltig ägartoken.

Om du vill bokföra en behållningsfråga anger du frågan i begärandetexten. Använd det mönster som beskrivs i [Fråga genom att använda inläggsmetoden.](inventory-visibility-api.md#query-with-post-method).

![Inställningar för behållningsfråga](media/inventory-visibility-query-settings.png "Inställningar för behållningsfråga")

### <a name="reservation-posting"></a>Reservationsbokföring

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Använd fliken **Bokföring av** när du bokför en reservationsbegäran. Innan du kan bokföra en reservationsbegäran måste du aktivera funktionen *OnHandReservation*. Mer information om denna funktion finns i [Reservationer för lagersynlighet](inventory-visibility-reservations.md).

Om du vill bokföra en reservationsbegäran måste du ange ett värde i begärandetexten. Använd det mönster som beskrivs i [Skapa en reservationshändelse](inventory-visibility-api.md#create-one-reservation-event). Välj sedan **Bokför**. Om du vill visa information om begärandesvar väljer du **Visa detaljer**. Du kan också få värdet **reservationId** från svarsdetaljerna.

## <a name="inventory-summary"></a>Lagersammanfattning

**Lagersammanfattning** är en anpassad vy för entiteten *Inventory OnHand Sum*. Den ger en lagersammanfattning för produkter tillsammans med alla dimensioner. Genom att använda det **avancerade filter** som Dataverse tillhandahåller kan du skapa en personlig vy som visar de rader som är av vikt för dig. Med hjälp av de avancerade filteralternativen kan du skapa många olika vyer, från enkla till komplexa. Du kan också lägga till grupperade och kapslade villkor i filtren.

Mer information om hur du använder det **Avancerade filtret** finns i [Redigera eller skapa personliga vyer med avancerade filter](/powerapps/user/grid-filters-advanced)

Högst upp i den anpassade vyn finns tre fält: **Standarddimension**, **Anpassad dimension** samt **Mått**. Du kan använda dessa fält för att kontrollera vilka kolumner som är synliga.

Du kan välja kolumnrubriken för att filtrera eller sortera det aktuella resultatet.

Längst ned i den anpassade vyn visas information som "50 poster (29 valda) eller "50 poster". Denna information refererar till de poster som läses in för närvarande från resultatet av det **avancerade filtret**. Texten "29 markerade" syftar på antalet poster som har markerats med hjälp av kolumnrubrikfiltret för de inlästa posterna.

Längst ned i vyn finns knappen **Läs in fler** som du använder för att läsa in fler poster från Dataverse. Standardantalet poster som läses in är 50. När du väljer **Läs in fler** läses nästa 1 000 tillgängliga poster in i vyn. Numret på knappen **Läs in fler** visar de poster som för närvarande lästs in samt det totala antalet poster för resultatet för det **avancerade filtret**.

![Lagersammanfattning](media/inventory-visibility-onhand-list.png "Lagersammanfattning")
