---
title: Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova
description: Det här ämnet beskriver hur du schemalägger framtida beredskapsändringar och beräknar kvantiteter disponibelt att lova (ATP).
author: yufeihuang
ms.date: 03/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 7ce868871f093fd734a466bb8a06c5782bf83302
ms.sourcegitcommit: a3b121a8c8daa601021fee275d41a95325d12e7a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2022
ms.locfileid: "8525892"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in funktionen *schema för ändringsplan* för att kunna tidsplanera framtida ändringar av lagerbehållningen och beräkna kvantiteter som är tillgängliga att lova. ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund i nästa period. Om du använder den här beräkningen kan du öka möjligheten att uppfylla ordern mycket.

För många tillverknings-, butiks- och säljare räcker det inte att veta vad som finns i nuläget. De måste ha fullständig insyn i framtida tillgänglighet. Framtida tillgänglighet ska ta hänsyn till framtida leverans, framtida efterfrågan och tillgängligt att leverera tillgängligt att leverera.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Aktivera och ställa in funktionerna

Innan du kan använda slutet på ett leverantörsantal måste du ställa in en eller flera beräknade mått för att beräkna kvantiteterna för tillgängliga att välja mellan. Du måste även aktivera funktionen och konfigurera inställningar för ATP-inställningar i Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Ställ in beräknade mått för ATP-kvantiteter

*Mått för ATP-kvantiteter* är ett fördefinierat beräknat mått som vanligtvis används för att hitta den tillgängliga kvantiteten som för närvarande är tillgänglig. Summan av dess additionsmodifierande kvantiteter är utbudskvantiteten, och summan av dess subtraktionsmodifierande kvantiteter är efterfrågekvantiteten.

Du kan lägga till flera beräknade mått för att beräkna ATP-kvantiteter. Det totala antalet modifierare för alla beräknade ATP-mått bör dock vara mindre än nio.

Till exempel ställer du in följande beräknade mått:

**Disponibel lagerbehållning** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

Summan (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) representerar leverans och summan (*ReservPhysical* + *SoftReservePhysical* + *Outbound*) representerar efterfrågan. Därför kan det beräknade måttet förstå på följande sätt:

**Disponibel lagerbehållning** = *Leverans* – *Efterfrågan*

För mer information om beräknade mått, se [Beräknat mått](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Aktivera funktionen för ändring av behållning och konfigurera ATP-inställningar

Följ de här stegen om du vill aktivera funktionen *schema för ändringsplan* i Power Apps och konfigurera ATP-inställningarna.

1. Logga in i Power Apps och öppna Lagersynlighet.
1. Öppna sidan **Konfiguration**.
1. I fliken **Funktionshantering** aktiverar du funktionen *OnhandChangeSchedule*.
1. Välj fliken **ATP-inställningar**.
1. När du fråga efter Lagersynlighet ger det ett resultat som inkluderar varje beräknat ATP-mått som du lägger till här. Välj **Lägg till** om du vill lägga till det nya beräknade måttet för ATP.
1. Ange följande fält.

    - **Datakälla** – Välj den datakälla som är associerad med den beräknade måttet.
    - **Beräknat mått** – Välj det beräknade mått som är associerat med den valda datakällan och som du vill använda för att hitta den tillgängliga lagerkvantiteten.
    - **Tidsplanperiod** – Ange hur många dagar som användare kan visa och skicka planerade ändringar av behållning när det valda beräknade måttet används. Användare som söker efter lagerinformation får lagerhållningskvantiteten, planerade ändringar av lagerhållningen och maximalt kvantiteten att använda per dag under den här perioden, med början på det aktuella datumet. Välj ett heltal mellan 1 och 7.

    > [!IMPORTANT]
    > I tidsplanperioden ingår aktuellt datum. Därför kan användarna tidsplanlägga ändringar av behållningen så att de inträffar när som helst från aktuellt datum (dagen då ändringen skickas) till och med (tidsplanperiod – 1) dagar i framtiden.

1. Välj **Spara**.
1. Upprepa steg 5 till och med 7 tills du har lagt till alla beräknade mått som du behöver för ATP.
1. När du är klar med konfigureringen av alla nödvändiga inställningar väljer du **Uppdatera konfiguration**.

Mer information finns i [Slutför och uppdatera konfigurationen](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Så här går det att ändra tidsplanering och beräkningar av ATP

En *tidsplan för förändring av lagerhållning* som visar förväntade datum och kvantiteter av tidsplanerade ändringar av lagerhållningen. Du kan skicka en tidsplan för förändring av lagerbehållningen till Lagersynlighet under förutsättning att datumen ligger inom den period som definieras i inställningen **Tidsplaneringsperiod** (se avsnittet [Aktivera och ställ in funktioner](#setup)). Användare som söker efter lagerinformation får lagerhållningskvantiteten, planerade ändringar av lagerhållningen och maximalt kvantiteten att använda per dag under den här perioden.

Planerade ändringar är inledningsvis obekräftade och påverkar därför inte din faktiska lagerhållning i systemet. Om du vill genomföra ändringarna måste du skicka en *ändringshändelser för behållning*, som uppdaterar den faktiska tillgängliga lagerhållningskvantiteten. Du måste sedan återställa den tidsplanerade ändringen genom att skicka en tidsplan för lagerändring för en matchande negativ kvantitet.

Du kan till exempel göra en order på tio cyklar, och förvänta dig att den inkommer imorgon. Därför skickar du in en tidsplan för lagerändring som har en inkommande kvantitet på 10 och är daterad för imorgon. När ordern inkommer nästa dag lägger du till den fysiska lagerbehållningen. Du måste sedan bekräfta ändringen av systemet för att uppdatera den faktiska lagerhållningskvantiteten. Om du vill bekräfta ändringen skickar du en händelse för behållningsändring som har en inkommande kvantitet på 10. Du måste sedan återställa den tidsplanerade ändringen genom att skicka en tidsplan för som har en inkommande kvantitet på -10.

När du fråga efter lagersynlighet för lagerbehållnings- och lagerbehållningskvantiteter returnerar det följande information för varje dag under planeringsperioden:

- **Datum** – Datumet som resultatet gäller.
- **Lagerhållningskvantitet** – Den faktiska lagerhållningskvantiteten för det angivna datumet. Beräkningen görs i enlighet med det beräknade måttet för maximalt lager som har konfigurerats för Lagerfinlighet.
- **Tidsplanerad leverans** – Summan av alla planerade inkommande kvantiteter som inte har blivit fysiskt tillgängliga för omedelbar förbrukning eller leverans på angivet datum.
- **Planerad efterfrågan** – Summan av alla planerade utgående kvantiteter som inte har förbrukats eller levererats på det angivna datumet.
- **ATP-kvantitet** – Den minsta beräknade tillgängliga kvantiteten som är tillgänglig från det angivna datumet till slutet av schemaperioden. Den här kvantiteten omfattar alla planerade kvantitetsjusteringar. Det är den maximikvantitet som kan utlovas på aktuellt leverans- eller förbrukningsdatum den dagen.

Om det aktuella datumet till exempel är 1 februari 2022 och tidsplanperioden är 7, kan användarna skicka planerade ändringar i behållning som förväntas ske från 1 februari till 7 februari 2022. I det här fallet beräknas ATP-kvantiteten för den 3 februari, till exempel, baserat på den tillgängliga kvantiteten för den dagen och de schemalagda kvantiteterna från den 3 februari till den 7 februari.

## <a name="example"></a>Exempel

Följande exempel visar hur en serie av schemalagda kvantitetsändringar påverkar de tillgängliga kvantiteterna och ATP-kvantiteterna som lagersynlighet rapporterar. Här visas också hur du genomför en tidsplanerad ändring, hur en utfäst tidsplanändring påverkar resultatet och vad som kan inträffa om du inte genomför en tidsplanerad ändring.

Resultaten i det här exemplet visar ett värde för *projekterade behållning*. Detta värde införlivar alla planerade uppdateringar i illustrationssyfte men rapporteras inte när du fråga på Lagersynlighet.

1. Följande inställningar är konfigurerade för ditt system på sidan **ATP-inställning** i Power Apps:

    - **AtP-beräknat mått** – Du har ett beräknat mått som kallas *Behållning*. Den beräknas som *Behållning = Leverans – Efterfrågan*. Du väljer måttet här.
    - **Planeringsperiod** – du väljer *7*.

1. Följande villkor gäller:

    - Det aktuella datumet är den 1 februari 2022.
    - Den aktuella lagerbehållningen är 20.

1. För aktuellt datum (1 februari 2022) skickar du en tidsplanerad efterfrågekvantitet på 3 till Lagersynlighet. Därför är den beräknade tillgängliga kvantiteten 17. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/01 | 20 | | 3 | 17 | 17 |
    | 2022/02/02 | 20 | | | 17 | 17 |
    | 2022/02/03 | 20 | | | 17 | 17 |
    | 2022/02/04 | 20 | | | 17 | 17 |
    | 2022/02/05 | 20 | | | 17 | 17 |
    | 2022/02/06 | 20 | | | 17 | 17 |
    | 2022/02/07 | 20 | | | 17 | 17 |

1. På det aktuella datumet (1 februari 2022) skickar du en tidsplanerad leveranskvantitet på 10 februari 3 februari 2022. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/01 | 20 | | 3 | 17 | 17 |
    | 2022/02/02 | 20 | | | 17 | 17 |
    | 2022/02/03 | 20 | 10 | | 27 | 27 |
    | 2022/02/04 | 20 | | | 27 | 27 |
    | 2022/02/05 | 20 | | | 27 | 27 |
    | 2022/02/06 | 20 | | | 27 | 27 |
    | 2022/02/07 | 20 | | | 27 | 27 |

1. På aktuellt datum (1 februari 2022) skickar du följande planerade kvantitetsändringar:

    - Efterfrågekvantitet på 15 februari 4 februari 2022
    - Leveranskvantitet på 1 februari 5 februari 2022
    - Efterfrågekvantitet på 3 februari 6 februari 2022

    Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/01 | 20 | | 3 | 17 | 12 |
    | 2022/02/02 | 20 | | | 17 | 12 |
    | 2022/02/03 | 20 | 10 | | 27 | 12 |
    | 2022/02/04 | 20 | | 15 | 12 | 12 |
    | 2022/02/05 | 20 | 1 | | 13 | 13 |
    | 2022/02/06 | 20 | 3 | | 16 | 16 |
    | 2022/02/07 | 20 | | | 16 | 16 |

1. På aktuellt datum (1 februari 2022) du skickar den planerade efterfrågan på 3. Därför måste du bekräfta ändringen så att den återspeglas i din faktiska lagerhållningskvantitet. Om du vill bekräfta ändringen skickar du en händelse för behållningsändring som har en utgående kvantitet på 3. Du måste sedan återställa den tidsplanerade ändringen genom att skicka en tidsplan för som har en utgående kvantitet på -3. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/01 | 17 | | 0 | 17 | 12 |
    | 2022/02/02 | 17 | | | 17 | 12 |
    | 2022/02/03 | 17 | 10 | | 27 | 12 |
    | 2022/02/04 | 17 | | 15 | 12 | 12 |
    | 2022/02/05 | 17 | 1 | | 13 | 13 |
    | 2022/02/06 | 17 | 3 | | 16 | 16 |
    | 2022/02/07 | 17 | | | 16 | 16 |

1. På nästa dag (2 februari 2022) skiftar tidsplanperioden framåt med en dag. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/02 | 17 | | | 17 | 12 |
    | 2022/02/03 | 17 | 10 | | 27 | 12 |
    | 2022/02/04 | 17 | | 15 | 12 | 12 |
    | 2022/02/05 | 17 | 1 | | 13 | 13 |
    | 2022/02/06 | 17 | 3 | | 16 | 16 |
    | 2022/02/07 | 17 | | | 16 | 16 |
    | 2022/02/08 | 17 | | | 16 | 16 |

1. Två dagar senare (4 februari 2022) har dock leveranskvantiteten 10 som planerats för den 3 februari inte anlänt. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022/02/04 | 17 | | 15 | 2 | 2 |
    | 2022/02/05 | 17 | 1 | | 3 | 3 |
    | 2022/02/06 | 17 | 3 | | 6 | 6 |
    | 2022/02/07 | 17 | | | 6 | 6 |
    | 2022/02/08 | 17 | | | 6 | 6 |
    | 2022/02/09 | 17 | | | 6 | 6 |
    | 2022/02/10 | 17 | | | 6 | 6 |

    Som du ser påverkas inte de planerade (men inte utfästa) lagerändringarna den faktiska lagerhållningskvantiteten.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Skicka ändringsscheman, ändringshändelser och ATP-frågor via API:t

Med följande URL-adresser för program programming interface (API) kan du skicka behållningsändringsscheman, ändra händelser och frågor.

| Sökväg | Metod | Beskrivning |
| --- | --- | --- |
| `/api/environment/{environmentId}/on-hand/changeschedule` | `POST` | Skapa en schemalagd engångs-ändring. |
| `/api/environment/{environmentId}/on-hand/changeschedule/bulk` | `POST` | Skapa flera schemalagda engångs-ändringar. |
| `/api/environment/{environmentId}/onhand` | `POST` | Skapa en ändringshändelse för behållning. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Skapa flera ändringshändelser. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Fråga genom att använda `POST` metoden. |
| `/api/environment/{environmentId}/onhand` | `GET` | Fråga genom att använda `GET` metoden. |

Mer information finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md).

### <a name="submit-on-hand-change-schedules"></a>Skicka tidsplaner för förändring av behållning

Tidsplaner för ändringar av lagerbehållning görs genom att du skickar en `POST` begäran till relevant URL för lagertjänst (mer information finns i [Skicka ändringsscheman, ändringshändelser och ATP-frågor via API](#api-urls)-avsnittet). Du kan även skicka bulkbegäranden.

För att kunna skicka en tidsplan för förändring av lagerhållningen måste förfrågan innehålla ett organisations-ID, ett produkt-ID, ett tidsplanerat datum och kvantiteter per datum. Det tidsplanerade datumet måste vara mellan det aktuella datumet och slutet för den aktuella tidsplanerade perioden.

#### <a name="example-request-body-that-contains-a-single-update"></a>Exempel på begäran som innehåller en enda uppdatering

Exempel på begäran som innehåller en enda uppdatering.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule

# Method
Post

# Header
# Replace {access_token} with the one from your security service
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
        "SizeId": "Small"
    },
    "quantitiesByDate":
    {
        "2022/02/01": // today
        {
            "pos":{
                "inbound": 10,
            },
        },
    },
}
```

#### <a name="example-request-body-that-contains-multiple-bulk-updates"></a>Exempel på begäran som innehåller flera (bulk) uppdateringar

Exempel på begäran som innehåller flera (bulk) uppdateringar.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/changeschedule/bulk

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/01": // today
            {
                "pos":{
                    "inbound": 10,
                },
            },
        },
    },
    {
        "id": "id-bike-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId": "Small"
        },
        "quantitiesByDate":
        {
            "2022/02/05":
            {
                "pos":{
                    "outbound": 10,
                },
            },
        },
    }
]
```

### <a name="submit-on-hand-change-events"></a>Skicka ändringshändelser för behållning

Ändringshändelser för behållning görs genom att du skickar en `POST` begäran till relevant URL för lagertjänst (mer information finns i [Skicka ändringsscheman, ändringshändelser och ATP-frågor via API](#api-urls)-avsnittet). Du kan även skicka bulkbegäranden.

> [!NOTE]
> Ändringshändelser vid handen är inte unika för ATP-funktionaliteten utan är en del av standardinventeringssynlighets-API. Det här exemplet har inkluderats eftersom händelser är relevanta när du arbetar med ATP. Ändringshändelser vid handen är inte unika för ATP-funktionaliteten utan är en del av standardinventeringssynlighets-API `quantities` i stället för `quantityByDate` i meddelandetexten. Mer information om händelser för lagerbehållningsändring och andra funktioner i API:erna för lager synlighet finns i [Allmänna API:er för lager](inventory-visibility-api.md).

För att kunna skicka en händelse för behållning måste begärandetexten innehålla ett organisations-ID, ett produkt-ID, ett tidsplanerat datum och kvantiteter per datum. Det tidsplanerade datumet måste vara mellan det aktuella datumet och slutet för den aktuella tidsplanerade perioden.

Exempel på begäran som innehåller en enskild ändringshändelse för behållning.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# Replace {access_token} with the one from your security service
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
        "SizeId": "Big",
        "ColorId": "Red",
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Fråga de schemalagda ändringarna och ATP-resultaten

Du kan fråga efter schemalagda aktuella ändringar och ATP-resultat genom att skicka antingen en `POST`-begäran eller en `GET` begäran till lämplig API-URL (se [Skicka ändringsscheman, ändringshändelser och ATP-frågor via API:etI](#api-urls) avsnitt).

I din begäran, ange `QueryATP` till *true* om du vill fråga efter schemalagda ändringar och ATP-resultat.

- Om du skickar en begäran med hjälp av `GET` metoden ställer du in den här parametern i URL-adressen.
- Om du skickar en begäran med hjälp av `POST` metoden ställer du in den här parametern i begärandetext.

> [!NOTE]
> Oavsett om `returnNegative` parametern är inställd på *true* eller *false* i begärandetext, kommer resultatet att innehålla negativa värden när du ställer frågor för tidsplanerade ändringar av behållning och resultat av valörerna. Dessa negativa värden inkluderas eftersom, om endast efterfrågeorder planeras, eller om leveranskvantiteterna är mindre än efterfrågekvantiteterna, kommer de planerade lagerändringskvantiteterna att vara negativa. Om negativa värden inte ingår i det här programmet blir resultaten det verkliga. Mer information om det här alternativet och hur det fungerar för andra typer av frågor finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md).

### <a name="post-method-example"></a>Exempel på POST-metod

Följande exempel visar hur du skapar ett förfrågnings brödtext som kan skickas till Lagerfinlighet med hjälp av `POST`-metoden.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/on-hand/indexquery

# Method
Post

# Header
# replace {access_token} with the one from your security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true,
}
```

### <a name="get-method-example"></a>Exempel på GET-metod

Följande exempel visar hur du skapar en URL för en begäran som en `GET` begäran.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

Resultatet av denna `GET` begäran är exakt detsamma som resultatet av `POST` begäran i det föregående exemplet.

### <a name="query-result-example"></a>Exempel på frågeresultat

Båda tidigare frågeexempel kan ge följande svar. I det här exemplet konfigureras systemet med följande inställningar:

- **ATP beräknat mått:** *iv.onhand = pos.inbound – pos.outbound*
- **Tidsplanera datum för period:** *7*

Här följer ett exempel på svarstexten.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
