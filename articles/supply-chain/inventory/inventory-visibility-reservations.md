---
title: Inventory Visibility-reservationer
description: I denna artikel beskrivs hur du konfigurerar reservationsfunktionen för att skapa reservationer, förbruka reservationer och/eller avmarkera angivna lagerkvantiteter med hjälp av Lagersynlighet.
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
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762752"
---
# <a name="inventory-visibility-reservations"></a>Inventory Visibility-reservationer

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver ett vanligt användningsfall för mjuka reservationer och förklarar hur du ställer in dem i lagersynlighet. Det inkluderar information om hur du skapar mjuka reservationer, förskjuter dem vid fysisk förbrukning och justerar eller inte reserverar angivna lagerkvantiteter.

## <a name="sample-use-case-for-soft-reservation"></a>Provanvändningsfall för mjuk reservation

Mjuka reservationer hjälper organisationer att uppnå en enda sanningskälla för tillgängligt lager, särskilt under uppfyllelseprocessen för order. Den här funktionen är användbar för organisationer där följande villkor föreligger:

- Organisationen har minst två olika system som direkt tar utgående order.
- Organisationen är mycket strikt och vill förhindra dubbelbokning av produktlager, vilket kan inträffa om flera system kan överboka den sista lagerartikeln. Situationen förhindras när alla ordersystem kan göra snabb, mjuk reservations-API-anrop till Lagersynlighet, som tillhandahåller en enda källa till ära för lagertillgänglighet.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Lagersynlighet mjuka reservationer" width="720" />](media/inventory-visibility-soft-reservation.png)

I den föregående illustrationen visas hur mjuk reservation fungerar och markerar följande operationer:

- Den ursprungliga lagernivån synkroniseras till lagersynlighet från Microsoft Dynamics 365 Supply Chain Management.
- Mjuk reservationer bokförs från alla dina orderkanaler eller system till lagersynlighet. Lagersynlighet validerar lagertillgänglighet och försöker göra en mjuk reservation. Om den mjuka reservationen lyckats läggs lagersynligheten till den mjuka reserverade kvantiteten, dras av från kvantiteten som är tillgänglig för reservation (AFR) och svarar med ett mjuk reservations-ID.
- Din fysiska lagerkvantitet förblir oförändrad just nu.
- Du kan sedan synkronisera antingen enstaka eller aggregerade, mjukreserverade order (orderrader) i Supply Chain Management för att göra hårdreservationer och frisläppa till lagerstället eller uppdatera den slutgiltiga lagerkvantiteten.
- Du kan ställa in systemet för att [motboka mjuka reservationer](#offset-scm) när fysiskt lager uppdateras i Supply Chain Management.

Mjuka reservationer skapas, förbrukas och annulleras vanligtvis med hjälp av API-anrop till tjänsten för lagersynlighet.

> [!NOTE]
> Om du vill kan du konfigurera Supply Chain Management (och andra tredjepartssystem) för att automatiskt motboka den kvantitet som har reserverats med hjälp av Lagersynlighet. Motbokningskvantiteten tas bort från reservationsposterna i Lagersynlighet.
>
> Förvalt funktionen aktiveras automatiskt när du aktiverar funktionen för mjuk reservation.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Aktivera och konfigurera reservationsfunktionen

Följ dessa steg för att aktivera reservationsfunktionen.

1. Logga in i Power Apps och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration**.
1. I fliken **Funktionshantering** aktiverar du funktionen *OnHandReservation*.
1. Logga in i din miljö för Supply Chain Management.
1. Gå till arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen *Integrering av Lagersynlighet med reservationsmotbokning* (kräver version 10.0.22 eller senare).
1. Gå till **Lagerhantering \> Konfigurera \> Parametrar för integrering av lagersynlighet**, öppna fliken **Reservationsmotbokning** och gör följande inställningar:

    - **Aktivera reservationsmotbokning** – ställ in till *Ja* om du vill aktivera den här funktionen.
    - **Modifierare för reservationsmotbokning** – välj det lagertransaktionsstatus som motbokar reservationer som gjorts i Lagersynlighet. Den här inställningen avgör vilken orderbearbetningsfas som utlöser motbokningar. Fasen spåras med hjälp av orderns lagertransaktionsstatus. Välj ett av följande värden:

        - *För order* – Order som har statusen *Har beställts* skickar en order en begäran om motbokning när den skapas. Motbokningskvantiteten är kvantiteten för den skapade ordern (rad).
        - *Reservera* – Order som har statusen *Reservera* skickar en motbegäran när de antingen är order som reserverats eller reserverats fysiskt. När du motbokar vid statusen *Reservera*, skickar ordern en motbegäran vid en ny lagerstatus som är närmast reserverad (till exempel plockad, följesedelsbokförd eller fakturerad). Detta beteende inträffar även om du hoppar över reservationen i Supply Chain Management och fortsätter till en annan lagerstatus (till exempel om du hoppar från frisläppning till lagerställe för att plocka och packa). Förfrågningen kommer endast att initieras en gång. Om den har utlösts vid plockningen kommer den inte att duplicera motbokning när en följesedel bokförs. Motbokningskvantiteten kommer att vara densamma som kvantiteten för lagertransaktionsstatusen när offset utlöstes (med andra ord, *Reserverat beställt*/*Reserverat beställt*, eller en senare status, på motsvarande orderrad).

1. Logga in igen på Lagersynligt-appen, gå till **Konfiguration** och sedan på fliken **Mjuk reservation**, granska den förinställda mjuka reservationshierarkin. Lägg till nya dimensioner i hierarkin om det behövs.
1. Visa standardinställningarna i avsnittet **Ställ in mjuk reservationsmappning**. Som standard registreras de mjukreserverade lagerkvantiteterna mot `softreservephysical` datakällans fysiska mått `iv`. Det beräknade måttet *Tillgänglig för reservation* mappas till `availabletoreserve`. Om du vill uppdatera det beräknade måttet `availabletoreserve`, gå till sidan **Konfiguration** och sedan på fliken **Beräknat mått** expanderar och ändrar sedan det beräknade måttet

Mer information finns i [Konfigurera Lagersynlighet](inventory-visibility-configuration.md).

> [!NOTE]
> Reservationshierarkin beskriver den dimensionssekvens som måste anges när reservationer görs. Den fungerar på samma sätt som indexhierarkin fungerar för behållningsfrågor, men den används oberoende av varandra så att användare kan ange dimensionsdetaljer för att göra mer precisa reservationer.
>
> Din preliminära reservationshierarki bör innehålla `SiteId` och `LocationId` som komponenter eftersom de skapar partitionskonfigurationen av lagersynlighet.

För mer information om hur du konfigurerar reservationer finns i [Reservationskonfiguration](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Använd reservationsfunktionen i Lagersynlighet

När du anropar reservations-API:t markerar systemet reservationen av de angivna varorna och kvantiteterna.

Här är ett exempelscenario och en exempel-API-frågetext. Företaget Contoso säljer produkten D0002 (Cabinet) från sin e-handelswebbplats. En kund lägger en försäljningsorder för ett litet rött skåp via webbplatsen. Contoso bestämmer sig för att uppfylla ordern genom att använda följande dimensioner:

- Organisations-ID = usmf
- Webbplats = 1
- Lagerställe = 11
- Produkt = D0002
- Färg = röd
- Storlek = liten

Contoso har redan ställt in en API-anslutning till lagersynlighet från sitt eget e-handelssystem. När ordern tas emot utlöser systemet ett API-anrop för att göra en mjuk reservation för skåpet i Lagersynlighet.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Skapa mjuka reservationer med hjälp av reservations-API:t

Reservationer görs i tjänsten Lagersynlighet genom att skicka en POST-begäran till tjänstens URL, till exempel `/api/environment/{environmentId}/onhand/reserve`.

För en reservation måste begärandetexten innehålla ett organisations-ID, ett produkt-ID, reserverade kvantiteter och dimensioner.

När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True` betyder att valideringen krävs, medan ett värde av `False` betyder att valideringen inte krävs. Standardvärdet är `True`.

Om du vill annullera en reservation eller ta bort reservationen av angivna lagerkvantiteter ställer du in kvantiteten på ett negativt värde och konfigurerar parametern `ifCheckAvailForReserv` på `False` för att hoppa över valideringen.

Här är ett exempel på förfrågningstexten som refererar till försäljningsordern i det föregående sammanhanget.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

En lyckad begäran om mjuk reservation returnerar ett *mjuk reservations-ID* för varje reservationspost. Det mjuka reservations-ID som inte är en unik identifierare för en enskild, mjuk reservationspost, utan en kombination av produkt-ID och dimensionsvärden som är associerade med den mjuk reservationsbegäran. Du kan registrera det mjuka reservations-ID:t på orderraden när du synkroniserar de slutförda orderna till Supply Chain Management eller ett annat ERP-system för motbokning.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Motboka mjuka reservationer i Supply Chain Management

Du kan motboka en mjuk reserverad kvantitet efter att kvantiteten på en order har dragits av fysiskt i Supply Chain Management eller ett annat ERP-system. Lagersynlighet erbjuder "medföljande" motbokning av integration med Supply Chain Management.

Följ dessa steg för att motboka en mjuk reservation.

1. Logga in på Supply Chain Management.
1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Skapa om den externa försäljningsordern och lägg till en försäljningsrad med exakt samma produkt-ID, organisation, webbplats, lagerställe och dimensionsvärden.
1. På snabbfliken **Försäljningsorderrader** välj försäljningsraden som du just angav och välj sedan i verktygsfältet **Lager \> Reservations-ID**.
1. Gör något av följande:

    - Kopiera det mjuk reservations-ID:t i ditt svar på den mjuka reservationsförfrågningen och klistra in det i fältet **Reservations-ID**.
    - Lämna fältet **Reservations-ID** tomt, men markera kryssrutan **Automatisk motbokning av lagertjänst**. Systemet fastställer automatiskt vilka produkt- och produktdimensioner som ska motbokas, baserat på de artikel-ID och dimensionsvärden som anges på den valda raden.

1. Välj **OK**.
1. Medan samma försäljningsrad fortfarande är vald, reservera den beställda kvantiteten fysiskt genom att välja **Lager \> Reservation** i verktygsfältet på snabbfliken **Försäljningsorderrader**.
1. Om du tidigare ställt in fältet **Modifierare för reservationsmotbokning** till *Reserverad*, utlöses motbokningen när orderraden har status *Reservera fysiskt* eller *Reservera beställd*. Ett batchjobb körs en gång i minuten när motbokningsförfrågningar synkroniseras från Supply Chain Management till lagersynlighet.

> [!NOTE]
> För transaktionsstatus som inkluderar en angiven reservmodifierare för motbokning, kommer transaktionsuppdateringen att motboka motsvarande reservationspost när alla följande villkor uppfyllts:
>
> - Reservations-ID:t för lagertransaktionen matchar reservations-ID:t för reservationsposten i Lagersynlighet.
> - Dimensionerna för lagertransaktionen matchar dimensionerna för reservationsposten i Lagersynlighet.
> - Ändringar i lagertransaktionens statusutlösare motbokas för reservationer när lagertransaktionens status återspeglar att en orderprocess har slutförts eller hoppats över.

Motbokningskvantiteten följer de lagerkvantiteter som anges på relevanta lagertransaktioner. Motbokningen används endast om reserverad kvantitet finns kvar i Lagersynlighet.

### <a name="cancel-or-revert-a-soft-reservation"></a>Avbryta eller återställa en mjuk reservation

Om en ursprunglig orderrad annulleras eller tas bort och du måste återställa motsvarande mjuk reservation, bokför en negativ kvantitet som har exakt samma information i din API-frågetext.
