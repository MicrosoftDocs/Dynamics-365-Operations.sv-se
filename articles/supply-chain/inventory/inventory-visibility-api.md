---
title: Offentliga API:er för Inventory Visibility
description: Denna artikel beskriver de allmänna API:er som anges i Lagersynlighet.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8b0b8ca261237fbb2190f2a94cc11b816ae05af5
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762845"
---
# <a name="inventory-visibility-public-apis"></a>Offentliga API:er för Inventory Visibility

[!include [banner](../includes/banner.md)]

Denna artikel beskriver de allmänna API:er som anges i Lagersynlighet.

Det offentliga REST-API för ett av tilläggen för Lagersynlighet visar flera specifika slutpunkter för integreringen. Den stöder fyra huvudinteraktionstyper:

- Bokföring av ändringar för lagerbehållning i tillägget från ett externt system
- Ställa in eller åsidosätta lagerbehållningskvantiteter i tillägget från ett externt system
- Bokföra reservationsändringar i tillägget från ett externt system
- Fråga om aktuell behållning från ett externt system

I följande tabell finns de API:er som är tillgängliga i nuläget:

| Sökväg | Metod | beskrivning |
|---|---|---|
| /api/environment/{environmentId}/onhand | Bokför | [Skapa en engångs-ändringshändelse](#create-one-onhand-change-event)|
| /api/environment/{environmentId}/onhand/bulk | Bokför | [Skapa flera ändringshändelser](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Bokför | [Ställ in/åsidosätta lagerbehållning](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Bokför | [Skapa en mjuk reservationshändelse](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Bokför | [Skapa flera mjuka reservationshändelser](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Bokför | [Återför en mjuk reservationshändelse](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Bokför | [Återför flera mjuka reservationshändelser](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Bokför | [Skapa en schemalagd engångs-ändring](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Bokför | [Skapa flera engångs-ändringar med datum](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Bokför | [Fråga genom att använda inläggsmetoden](#query-with-post-method) (rekommenderad) |
| /api/environment/{environmentId}/onhand | Hämta | [Fråga genom att använda hämtningsmetoden](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Bokför | [Exakt fråga genom att använda inläggsmetoden](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation<wbr>/allocate | Bokför | [Skapa en allokerad händelse](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/unallocate | Bokför | [Skapa en ej allokerad händelse](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/reallocate | Bokför | [Skapa en ej omallokerad händelse](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/consume | Bokför | [Skapa en förbrukningshändelse](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/query | Bokför | [Resultat för frågeallokering](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> {environmentId} delen för vägen är miljö-ID är Microsoft Dynamics Lifecycle Services.
> 
> Bulk-API:t kan returnera maximalt 512 poster för varje begäran.

Microsoft har tillhandahållit en färdig *brevbärar*-begärandesamling. Du kan importera denna samling till ditt *brevbärar* program genom att använda följande delade länk: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a><a name = "endpoint-lcs"></a>Hitta slutpunkten enligt Lifecycle Services-miljön

Den mikrotjänst som används för Lagersynlighet distribueras för Microsoft Azure Service Fabric, i flera geografiska områden och flera regioner. Det finns i nuläget ingen central slutpunkt som automatiskt kan omdirigera din begäran till motsvarande geografiskt område och region. Du måste därför skapa informationsdelarna i en URL genom att använda följande mönster:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Det korta namnet för regionen finns i Lifecycle Services-miljön. I följande tabell finns de regioner som är tillgängliga i nuläget:

| Azure-region        | Kortnamn för region |
| ------------------- | ----------------- |
| Östra Australien      | eau               |
| Sydöstra Australien | seau              |
| Centrala Kanada      | cca               |
| Östra Kanada         | eca               |
| Nordeuropa        | neu               |
| Västeuropa         | weu               |
| Östra USA             | eus               |
| Västra USA             | wus               |
| Södra Storbritannien            | suk               |
| Västra Storbritannien             | wuk               |
| Japan, östra          | ejp               |
| Japan, västra          | wjp               |
| Centrala Indien       | cin               |
| Södra Indien         | sin               |
| Schweiz, norra   | nch               |
| Schweiz, västra    | wch               |
| Frankrike, syd        | sfr               |
| Östasien           | eas               |
| Sydostasien     | seas              |
| Förenade Arabemiraten, norra           | nae               |
| Norge, östra         | eno               |
| Norge, västra         | wno               |
| Sydafrika, västra   | wza               |
| Sydafrika, norra  | nza               |

Öns nummer är där din Lifecycle Services-miljö finns distribuerad i Service Fabric. Det finns för närvarande inget sätt att få denna information från användarsidan.

Microsoft har skapat ett användargränssnitt (UI) i Power Apps som gör att du kan få den fullständiga slutpunkten för mikrotjänsten. Mer information finns i [Hitta tjänsteslutpunkten](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Äkthetsbevisning

Säkerhetstoken för plattform används för att anropa det offentliga API:t Lagersynlighet. Därför måste du generera en *Azure Active Directory (Azure AD) token* med hjälp av ditt Azure AD program. Du måste sedan använda Azure AD token för att få *åtkomsttoken* från säkerhetstjänsten.

Microsoft tillhandahåller en färdig samling för hämta token för *brevbärare*. Du kan importera denna samling till ditt *brevbärar* program genom att använda följande delade länk: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Gör så här om du vill hämta en säkerhetstjänsttoken:

1. Logga in på Azure-portalen och använd den för att hitta värdena `clientId` och `clientSecret` för din Dynamics 365 Supply Chain Management-app.
1. Hämta en Azure AD-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
    - **Metod:** `GET`
    - **Brödtext (formulärdata):**

        | Nyckel           | Värde                                            |
        | ------------- | -------------------------------------------------|
        | klient-ID     | ${aadAppId}                                      |
        | client_secret | ${aadAppSecret}                                  |
        | grant_type    | client_credentials                               |
        | omfattning         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.default    |

    Du bör få en Azure AD-token (`aadToken`) som svar. Det bör likna följande exempel:

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formulera en JSON-begäran (JavaScript Object Notation) som liknar följande exempel.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "{$LCS_environment_id}",
        "context_type": "finops-env"
    }
    ```

    Observera följande:

    - Värdet för `client_assertion` måste vara den Azure AD-token (`aadToken`) som du fick i föregående steg.
    - Värdet `context` måste vara det Lifecycle Services miljö-ID där du vill distribuera tillägget.
    - Ställ in de andra värdena enligt exemplet.

1. Hämta en åtkomsttoken (`access_token`) genom att skicka en HTTP-begäran med följande egenskaper:

    - **URL:** `https://securityservice.operations365.dynamics.com/token`
    - **Metod:** `POST`
    - **HTTP-sidhuvud:** Inkludera API-versionen. (Nyckeln är `Api-Version`, och värdet är `1.0`.)
    - **Brödtext:** - Inkludera den JSON-begäran som du skapade i det föregående steget.

    Du bör få en åtkomsttoken (`access_token`) som svar. Du måste använda denna token som en ägartoken för att anropa API för lagersynlighet. Här följer ett exempel.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

> [!IMPORTANT]
> När du använder *brevbärar*-begärandesamling för att anropa offentliga API:er för lagersynlighet måste du lägga till en ägartoken för varje begäran. Om du vill söka efter din ägartoken väljer du fliken **Auktorisering** under begäran-URL, väljer typ av **ägartoken** och kopierar åtkomsttoken som hämtades i det sista steget. I senare avsnitt av denna artikel används `$access_token` för att representera den token som hämtades i föregående steg.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Skapa ändringshändelser för behållning

Det finns två API:er för att skapa ändringshändelser för behållning:

- Skapa en (1) post: `/api/environment/{environmentId}/onhand`
- Skapa flera poster: `/api/environment/{environmentId}/onhand/bulk`

I tabellen nedan sammanfattas vilket betydelse de olika fälten har i JSON-brödtexten.

| Fält-ID | Beskrivning |
|---|---|
| `id` | Ett unikt ID för den specifika ändringshändelsen. Om en ny inlämning inträffar på grund av ett tjänstefel, används detta ID för att säkerställa att samma händelse inte räknas två gånger i systemet. |
| `organizationId` | Identifierare för den organisation som är kopplad till händelsen. Detta värde mappas till en organisation eller dataområdes-ID i Supply Chain Management. |
| `productId` | Identifieraren för produkten. |
| `quantities` | Kvantiteten som lagerbehållningen måste ändras med. Om till exempel 10 nya böcker läggs till på en hylla blir detta värde `quantities:{ shelf:{ received: 10 }}`. Om tre böcker tas bort från hyllan eller säljs kommer detta värde att bli `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga. Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan. Lagersynligheten kan använda dimensionskonfigurationen för att mappa de anpassade dimensionerna till de allmänna standarddimensionerna. Om inget värde för `dimensionDataSource` anges kan du endast använda alla [basdimensioner](inventory-visibility-configuration.md#data-source-configuration-dimension) i dina frågor. |
| `dimensions` | Ett dynamiskt nyckel/värde-par. Värdena mappas till några av dimensionerna i Supply Chain Management. Du kan emellertid även lägga till anpassade dimensioner (till exempel *Källa*) för att ange om händelsen kommer från Supply Chain Management eller ett externt system. |

> [!NOTE]
> Parametrarna `siteId` och `locationId` skapar [partitionskonfigurationen](inventory-visibility-configuration.md#partition-configuration). Därför måste du ange dem i dimensioner när du skapar händelser för lagerbehållningsändring, konfigurerar eller åsidosätter lagerbehållningskvantiteter eller skapar reservationshändelser.

Följande delgrupper ger exempel som visar hur dessa API:er används.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Skapa en ändringshändelse för behållning

Detta API skapar en enskild ändringshändelse för behållning.

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

Följande exempel visar brödtext. I det här exemplet har företaget ett kassasystem (POS) som bearbetar in butikstransaktioner och därmed lagerändringar. Kunden har returnerat en röd T-shirt till din butik. För att återspegla ändringen lägger du upp en enda ändringshändelse för produkten *T-shirt*. Denna händelse ökar kvantiteten av produkt *T-shirt* med 1.

```json
{
    "id": "Test201",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

Följande exempel visar brödtext utan `dimensionDataSource`. I detta fall är `dimensions` [basdimensionerna](inventory-visibility-configuration.md#data-source-configuration-dimension). Om `dimensionDataSource` har ställts in kan `dimensions` vara antingen datakällsdimensionerna eller basdimensionerna.

```json
{
    "id": "Test202",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Skapa flera ändringshändelser

Detta API kan skapa ändringshändelser på samma sätt som [API:t för enstaka händelser](#create-one-onhand-change-event). Den enda skillnaden är att denna API kan skapa flera poster samtidigt. Därför skiljer sig värdena `Path` och `Body` åt. För detta API tillhandahåller `Body` en matris av poster. Det maximala antalet poster är 512. Därför kan det tillgängliga bulk-API:et för ändring stödja upp till 512 ändringshändelser åt gången. 

Till exempel bearbetade en kassaapparat i butik följande två transaktioner:

- En returorder av en röd T-shirt
- En försäljningstransaktion med tre svart T-shirts

I det här fallet kan du inkludera båda lageruppdateringarna i ett API-anrop.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
        ...
    ]
```

Följande exempel visar brödtext.

```json
[
    {
        "id": "Test203",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "Site1",
            "LocationId": "11",
            "posMachineId&quot;: &quot;0001"
            "colorId&quot;: &quot;red"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensions": {
            "siteId": "1",
            "locationId": "11",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Ställ in/åsidosätta lagerbehållning

API:t *Ställ in behållning* åsidosätter aktuella data för den angivna produkten. Den här funktionen används normalt för lagerinventeringsuppdateringar. Till exempel, under sin dagliga lagerräkning, kan en butik upptäcka att det faktiska lagret för en röd T-shirt är 100. Därför måste den inkommande kvantiteten i kassan uppdateras till 100, oavsett vad den tidigare kvantiteten var. Du kan använda denna API för att åsidosätta det befintliga värdet.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

Följande exempel visar brödtext. Beteendet för detta API skiljer sig från beteendet för API:erna som beskrivs i avsnittet [Skapa ändringshändelser för behållning](#create-onhand-change-event) tidigare i denna artikel. I detta exempel anges kvantiteten för produkten *T-shirt* som 1.

```json
[
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "posMachineId": "0001"
            "colorId": "red"
        },
        "quantities": {
            "pos": {
                "inbound": 100
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Skapa reservationshändelser

Om du vill använda *reserv*-API:t måste du öppna reservationsfunktionen och slutföra reservationskonfigurationen. Mer information (inklusive ett dataflöde och exempelscenario) finns i [Reservationskonfiguration (valfritt)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Skapa en reservationshändelse

Det går att göra en reservation mot olika datakällsinställningar. Om du vill konfigurera den här typen av reservation måste du först ange datakällan i `dimensionDataSource`-parametern. Sedan anger du i `dimensions`-parametern dimensioner enligt dimensionsinställningarna i måldatakällan.

När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True` betyder att valideringen krävs, medan ett värde av `False` betyder att valideringen inte krävs. Standardvärdet är `True`.

Om du vill annullerar en reservation eller ta bort reservationen av angivna lagerkvantiteter ställer du in kvantiteten på ett negativt värde och konfigurerar parametern `ifCheckAvailForReserv` på `False` för att hoppa över valideringen. Det finns också en dedikerad API för att göra samma sak. Skillnaden skiljer sig bara mellan de två API:erna. Det är enklare att återföra en viss reservationshändelse genom att använda `reservationId` med *utan reservation* API. Mer information finns i avsnittet [Avboka en reservationshändelse](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

Följande exempel visar brödtext.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

Följande exempel visar ett lyckat svar.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Skapa flera reservationshändelser

Detta API är en bulkversion av [API:t för en enskild händelse](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Återför en reservationshändelser

*Avboka* API fungerar som den omvända åtgärden för händelser [*Reservation*](#create-reservation-events). Det är ett sätt att återföra en reservationshändelse som anges av `reservationId` eller minska reservationskvantiteten.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Återför en reservationshändelse

När en reservation skapas inkluderas `reservationId` kommer att ingå i svarsinstansen. Du måste ange samma för `reservationId` att annullera reservationen, och inkludera samma `organizationId` och `dimensions` använda för reservations-API-anropet. Slutligen anger du ett `OffsetQty` värde som representerar antalet artiklar som ska frigöras från den tidigare reservationen. En reservation kan antingen återföras helt eller delvis beroende på vilken information som angetts `OffsetQty`. Om till exempel *100* enheter av artiklar reserverats kan du ange `OffsetQty: 10` avreservera *10* av det ursprungliga reserverade beloppet.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

Följande kod visar ett exempel på brödtext.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

Följande kod visar ett exempel på en framgångsrik svarsinstans.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> Svarstexten, när den `OffsetQty`är mindre än eller lika med reservationskvantiteten, `processingStatus` blir "*lyckad*" och `totalInvalidOffsetQtyByReservId` blir *0*.
>
> Om `OffsetQty` är större än reserverat belopp `processingStatus` blir "*partialSuccess*" och `totalInvalidOffsetQtyByReservId` kommer skillnaden mellan `OffsetQty` och det reserverade beloppet.
>
>Om reservationen till exempel har kvantiteten *10* och `OffsetQty` värdet *12* är den `totalInvalidOffsetQtyByReservId` bli *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Återför flera reservationshändelser

Detta API är en bulkversion av [API:t för en enskild händelse](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [      
        {
            id: string,
            organizationId: string,
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Behållningsfråga

Använd *Behållningsfråga* för att hämta aktuella lagerbehållningsdata för dina produkter. Du kan använda detta API när du måste känna till lagret, till exempel när du vill granska produktlagernivåer på din e-handelswebbplats, eller när du vill kontrollera produkttillgänglighet mellan regioner eller i närliggande butiker och lagerställen. API stöder för närvarande frågor upp till 5000 enskilda artiklar efter `productID` värde. Flera `siteID` och `locationID` värden kan också anges i varje fråga. Maxgränsen definieras i följande formel:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Fråga genom att använda inläggsmetoden

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

I brödtexten i denna begäran är `dimensionDataSource` fortfarande en valfri parameter. Om den inte är inställd behandlas `filters` som *basdimensioner*. Det finns fyra obligatoriska fält för `filters`: `organizationId`, `productId``siteId` och `locationId`.

- `organizationId` bör bara innehålla ett värde, men det är fortfarande en matris.
- `productId` kan innehålla ett eller flera värden. Om det är en tom matris kommer alla produkter att returneras.
- `siteId` och `locationId` används för partitionering i Lagersynlighet. Du kan ange mer än ett `siteId` och `locationId` värde i en förfrågan *Behållningsfråga*. I den aktuella versionen måste du ange både `siteId` och `locationId` värden.

Vi föreslår att du använder parametern `groupByValues` bör följa din konfiguration för indexering. Mer information finns i [Hierarkikonfiguration för produktindex](./inventory-visibility-configuration.md#index-configuration).

Parametern `returnNegative` styr om resultatet innehåller negativa poster.

> [!NOTE]
> Om du har aktiverat funktionerna för förändring av behållningslistan och tillgängligt att lova-funktionerna, kan frågan också inkludera den `QueryATP` booleska parametern som styr om frågeresultaten omfattar information om tillgängligt att lova. Mer information och exempel finns i [Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova](inventory-visibility-available-to-promise.md).

Följande exempel visar brödtext. Det visar att du kan söka efter lagerbehållningen från flera platser (lagerställen).

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "locationId": ["11","12","13"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

Följande exempel visar hur du frågar efter alla produkter på en viss webbplats och plats.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "locationId": ["11"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Fråga genom att använda hämtningsmetoden

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

Här är ett exempel på URL-adressen. Denna hämtbegäran är exakt densamma som bokföringsexemplet som angavs tidigare.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="on-hand-exact-query"></a><a name="exact-query-with-post-method"></a>Behållning för exakt fråga

Behållnings exakta frågor liknar vanliga behållningsfrågor, men du kan ange en mappningshierarki mellan en webbplats och en plats. Du har exempelvis följande två webbplatser:

- Webbplats 1, som mappas till plats A
- Webbplats 2, som mappas till plats B

För en vanlig behållningsfråga gäller `"siteId": ["1","2"]` och `"locationId": ["A","B"]`, lagersynlighet kommer automatiskt att fråga efter resultatet för följande webbplatser och platser:

- Webbplats 1, plats A
- Webbplats 1, plats B
- Webbplats 2, plats A
- Webbplats 2, plats B

Som du ser känner den vanliga behållningsfrågan inte igen att plats A endast finns på webbplats 1 och plats B finns bara på webbplats 2. Därför skapar den redundanta frågor. För att passa denna hierarkiska mappning kan du använda en exakt fråga vid behållning och ange platsmappningarna i frågetexten. I så fall söker du efter och tar emot resultat endast för webbplats 1, plats A och webbplats 2, plats B.

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Exakt fråga genom att använda inläggsmetoden

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

I brödtexten i denna begäran är `dimensionDataSource` en valfri parameter. Om den inte är inställd `dimensions` i `filters` behandlas *basdimensioner*. Det finns fyra obligatoriska fält för `filters`: `organizationId`, `productId``dimensions` och `values`.

- `organizationId` bör bara innehålla ett värde, men det är fortfarande en matris.
- `productId` kan innehålla ett eller flera värden. Om det är en tom matris kommer alla produkter att returneras.
- I `dimensions` matris, `siteId` och `locationId` krävs men kan visas med andra element i valfri ordning.
- `values` kan innehålla en eller flera olika tupplar av värden som motsvarar `dimensions`.

`dimensions` i `filters` kommer automatiskt att läggas till `groupByValues`.

Parametern `returnNegative` styr om resultatet innehåller negativa poster.

Följande exempel visar brödtext.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

Följande exempel visar hur du frågar efter alla produkter på flera webbplatser och platser.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Disponibelt att lova

Du kan konfigurera lagersynlighet så att du kan tidsplanera framtida ändringar av lagerbehållningen och beräkna ATP-kvantiteter. ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund i nästa period. Om du använder ATP beräkningen kan du öka möjligheten att uppfylla ordern mycket. Information om hur du aktiverar funktionen, och hur du kan interagera med lagersynlighet genom dess API när funktionen har aktiverats, finns i [Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Allokering

Allokeringsrelaterade API:er finns i [Allokering för lagersynlighet](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
