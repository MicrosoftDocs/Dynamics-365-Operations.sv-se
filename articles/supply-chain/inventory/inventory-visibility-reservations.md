---
title: Reservationer för Lagersynlighet
description: I detta ämne beskrivs hur du ställer in reservationsfunktionen för att skapa reservationer, förbruka reservationer och/eller avmarkera angivna lagerkvantiteter med hjälp av Lagersynlighet.
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
ms.openlocfilehash: acc5d5f93f3f625892aac37780a44e221b6eb5ac
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475046"
---
# <a name="inventory-visibility-reservations"></a>Lagersynlighetsreservationer

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

I detta ämne beskrivs hur du ställer in reservationsfunktionen för att skapa reservationer, förbruka reservationer och/eller avmarkera angivna lagerkvantiteter med hjälp av Lagersynlighet.

Reservationer utgör en kvantitet av lager som ska användas i framtiden. När du skapar en reservation förhindrar systemet att andra order reserverar eller förbrukar reserverade varor tills reservationen antingen förbrukas eller inte längre reserveras. Reservationer skapas, förbrukas och annulleras med hjälp av API-anrop till tjänsten för lagersynlighet.

Om du vill kan du ställa in Microsoft Dynamics 365 Supply Chain Management (och andra tredjepartssystem) för att automatiskt motboka den kvantitet som har reserverats med hjälp av Lagersynlighet. Motbokningskvantiteten tas bort från reservationsposterna i Lagersynlighet.

När du aktiverar reservationsfunktionen blir Supply Chain Management automatiskt redo att motboka reservationer som görs med hjälp av Lagersynlighet.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Aktivera och konfigurera reservationsfunktionen

Följ dessa steg för att aktivera reservationsfunktionen.

1. Logga in i Power Apps och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. I fliken **Funktionshantering** aktiverar du funktionen *OnHandReservation*.
1. Logga in på Supply Chain Management.
1. Gå till arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen *Integrering av Lagersynlighet med reservationsmotbokning* (kräver version 10.0.22 eller senare).
1. Gå till **Lagerhantering \> Konfigurera \> Parametrar för integrering av lagersynlighet**, öppna fliken **Reservationsmotbokning** och gör följande inställningar:
    - **Aktivera reservationsmotbokning** – ställ in till *Ja* om du vill aktivera den här funktionen.
    - **Modifierare för reservationsmotbokning** – välj det lagertransaktionsstatus som motbokar reservationer som gjorts i Lagersynlighet. Den här inställningen avgör vilken orderbearbetningsfas som utlöser motbokningar. Fasen spåras med hjälp av orderns lagertransaktionsstatus. Välj en av följande:
        - *För order* – För statusen *vid transaktion* skickar en order en begäran om motbokning när den skapas. Motbokningskvantiteten är kvantiteten för den skapade ordern.
        - *Reservera* – För statusen *Reservera beställd transaktion* skickar en order en begäran om motbokning när den reserveras, plockas, följesedelsbokförs eller faktureras. Denna begäran utlöses bara en gång - för det första steget när den omstämda processen inträffar. Motbokningskvantiteten är den kvantitet där lagertransaktionens status ändras från *Har beställts* till *Reserverat beställt* (eller senare status) på motsvarande orderrad.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Använd reservationsfunktionen i Lagersynlighet

När du anropar reservations-API:t markerar systemet reservationen av de angivna varorna och kvantiteterna. Du måste definiera en reservationshierarki och bokföra förfrågningar som matchar reservationshierarkin. Reservationerna kan sedan göras genom att anropa reservations-API:erna direkt.

### <a name="configure-the-reservation-hierarchy"></a>Konfigurera reservationshierarkin

Reservationshierarkin beskriver den dimensionssekvens som måste anges när reservationer görs. Detta fungerar på samma sätt som indexhierarkin fungerar för behållningsfrågor.

Reservationshierarkin kan skilja sig åt från indexhierarkin. Tack vare detta oberoende kan du implementera kategorihantering där användare kan bryta ned dimensionerna i detaljer i syfte att specificera kraven för att göra mer exakta reservationer.

Om du vill konfigurera en hierarki för preliminär reservation i Power Apps öppnar du sidan **Konfiguration** innan du, på sidan **Preliminär reservationshierarki**, konfigurerar reservationshierarkin genom att lägga till och/eller modifiera dimensioner och dessas hierarkinivåer.

Din preliminära reservationshierarki bör innehålla `SiteId` och `LocationId` som komponenter eftersom de skapar partitionskonfigurationen.

För mer information om hur du konfigurerar reservationer finns i [Reservationskonfiguration](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Anropa reservations-API

Reservationer görs i tjänsten Lagersynlighet genom att skicka en POST-begäran till tjänstens URL, till exempel `/api/environment/{environment-ID}/onhand/reserve`.

För en reservation måste begärandetexten innehålla ett organisations-ID, ett produkt-ID, reserverade kvantiteter och dimensioner. Förfrågningen genererar ett unikt reservations-ID för varje enskild reservationspost. Reservationsposten innehåller den unika kombinationen av produkt-ID och dimensioner.

När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True` betyder att valideringen krävs, medan ett värde av `False` betyder att valideringen inte krävs. Standardvärdet är `True`.

Om du vill annullera en reservation eller ta bort reservationen av angivna lagerkvantiteter ställer du in kvantiteten på ett negativt värde och ställer in parametern `ifCheckAvailForReserv` på `False` för att hoppa över valideringen.

Här är ett exempel på begärandetext (för referens).

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Motboka reservationer i Supply Chain Management

För lagertransaktionsstatus som inkluderar en angiven reservmodifierare för motbokning, kommer transaktionsuppdateringen att motboka motsvarande reservationspost när alla följande villkor uppfyllts:

- Reservations-ID:t för lagertransaktionen matchar reservations-ID:t för reservationsposten i tjänsten Lagersynlighet.
- Dimensionerna för lagertransaktionen är identiska med dimensionerna för reservationsposten i tjänsten Lagersynlighet.
- Ändringar i lagertransaktionens statusutlösare motbokas för reservationer när lagertransaktionens status återspeglar att en orderprocess har slutförts eller hoppats över.

Avbokningskvantiteten följer den lagerkvantitet som anges på lagertransaktioner. Motbokningen används inte om ingen reserverad kvantitet finns kvar i tjänsten Lagersynlighet.

### <a name="set-up-the-reservation-offset-modifier"></a>Konfigurera modifieraren för reservationsmotbokning

Om du inte redan har gjort det konfigurerar du reservationsmodifieraren enligt beskrivningen i [Aktivera och konfigurera reservationsfunktionen](#turn-on).

### <a name="set-up-reservation-ids"></a>Konfigurera reservations-ID

Reservations-ID:t markerar unikt en reservationspost i Lagersynlighet. I Supply Chain Management reserverar användare orderrader för att markera motbokningen för motsvarande reservationspost.

Gör på följande sätt när du vill konfigurera reservations-ID:n i Supply Chain Management.

1. Öppna en försäljningsorder (till exempel från sidan **Alla försäljningsorder**).
1. På snabbfliken **Försäljningsorderrader** väljer du en orderrad.
1. I verktygsfältet på snabbfliken **Försäljningsorderrader** väljer du **Uppdatera rad \> Lager \> Integrering av Lagersynlighet**.
1. Ange relevanta reservations-ID:n.

Lagerstatusändringen matchar inställningarna för modifieraren för motbokningar.
