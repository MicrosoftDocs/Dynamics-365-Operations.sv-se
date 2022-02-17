---
title: Offentliga API:er för Lagersynlighet
description: Detta ämne beskriver de allmänna API:er som anges i Lagersynlighet.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f74bb4bd4ed66520c04261bd9f82faad7775817e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062121"
---
# <a name="inventory-visibility-public-apis"></a>Offentliga API:er för Lagersynlighet

[!include [banner](../includes/banner.md)]


Detta ämne beskriver de allmänna API:er som anges i Lagersynlighet.

Det offentliga REST-API för ett av tilläggen för Lagersynlighet visar flera specifika slutpunkter för integreringen. Den stöder fyra huvudinteraktionstyper:

- Bokföring av ändringar för lagerbehållning i tillägget från ett externt system
- Ställa in eller åsidosätta lagerbehållningskvantiteter i tillägget från ett externt system
- Bokföra reservationsändringar i tillägget från ett externt system
- Fråga om aktuell behållning från ett externt system

I följande tabell finns de API:er som är tillgängliga i nuläget:

| Sökväg | Metod | beskrivning |
|---|---|---|
| /api/environment/{environmentId}/onhand | Bokför | [Skapa en engångs-ändringshändelse](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Bokför | [Skapa flera ändringshändelser](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Bokför | [Ställ in/åsidosätta lagerbehållning](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Bokför | [Skapa en reservationshändelse](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Bokför | [Skapa flera reservationshändelser](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/indexquery | Bokför | [Fråga genom att använda inläggsmetoden](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Hämta | [Fråga genom att använda hämtningsmetoden](#query-with-get-method) |

Microsoft har tillhandahållit en färdig *brevbärar*-begärandesamling. Du kan importera denna samling till ditt *brevbärar* program genom att använda följande delade länk: <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>.

> [!NOTE]
> Delen {environmentId} av sökvägen är miljö-ID:t i Microsoft Dynamics Lifecycle Services (LCS).
> 
> Bulk-API:t kan returnera maximalt 512 poster för varje begäran.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Hitta slutpunkten enligt Lifecycle Services-miljön

Den mikrotjänst som används för Lagersynlighet distribueras för Microsoft Azure Service Fabric, i flera geografiska områden och flera regioner. Det finns i nuläget ingen central slutpunkt som automatiskt kan omdirigera din begäran till motsvarande geografiskt område och region. Du måste därför skapa informationsdelarna i en URL genom att använda följande mönster:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Det korta namnet för regionen finns i Microsoft Dynamics Lifecycle Services-miljön (LCS). I följande tabell finns de regioner som är tillgängliga i nuläget:

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
| Brasilien, södra        | sbr               |
| Södra centrala USA    | scus              |

Öns nummer är där din LCS-miljö finns distribuerad i Service Fabric. Det finns för närvarande inget sätt att få denna information från användarsidan.

Microsoft har skapat ett användargränssnitt (UI) i Power Apps som gör att du kan få den fullständiga slutpunkten för mikrotjänsten. Mer information finns i [Hitta tjänsteslutpunkten](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Äkthetsbevisning

Säkerhetstoken för plattform används för att anropa det offentliga API:t Lagersynlighet. Därför måste du generera en _Azure Active Directory (Azure AD) token_ med hjälp av ditt Azure AD program. Du måste sedan använda Azure AD token för att få _åtkomsttoken_ från säkerhetstjänsten.

Microsoft tillhandahåller en färdig samling för hämta token för *brevbärare*. Du kan importera denna samling till ditt *brevbärar* program genom att använda följande delade länk: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Gör så här om du vill hämta en säkerhetstjänsttoken:

1. Logga in på Azure-portalen och använd den för att hitta värdena `clientId` och `clientSecret` för din Dynamics 365 Supply Chain Management-app.
1. Hämta en Azure AD-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:

   - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **Metod:** `GET`
   - **Brödtext (formulärdata):**

     | Nyckel           | Värde                                |
     | ------------- | ------------------------------------ |
     | klient-ID     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | resurs      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   Du bör få en Azure AD-token (`aadToken`) som svar. Det bör likna följande exempel:

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
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
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
       "context_type": "finops-env"
   }
   ```

   Observera följande:

   - Värdet för `client_assertion` måste vara den Azure AD-token (`aadToken`) som du fick i föregående steg.
   - Värdet `context` måste vara det LCS-miljö-ID där du vill distribuera tillägget.
   - Ställ in de andra värdena enligt exemplet.

1. Hämta en åtkomsttoken (`access_token`) genom att skicka en HTTP-begäran med följande egenskaper:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Metod:** `POST`
   - **HTTP-sidhuvud:** Inkludera API-versionen. (Nyckeln är `Api-Version`, och värdet är `1.0`.)
   - **Brödtext:** - Inkludera den JSON-begäran som du skapade i det föregående steget.

   Du bör få en åtkomsttoken (`access_token`) som svar. Du måste använda denna token som en ägartoken för att anropa API för lagersynlighet. Här är ett exempel:

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> När du använder *brevbärar*-begärandesamling för att anropa offentliga API:er för lagersynlighet måste du lägga till en ägartoken för varje begäran. Om du vill söka efter din ägartoken väljer du fliken **Auktorisering** under begäran-URL, väljer typ av **ägartoken** och kopierar åtkomsttoken som hämtades i det sista steget. I senare avsnitt av detta ämne används `$access_token` för att representera den token som hämtades i det sista steget.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Skapa ändringshändelser för behållning

Det finns två API:er för att skapa ändringshändelser för behållning:

- Skapa en (1) post: `/api/environment/{environmentId}/onhand`
- Skapa flera poster: `/api/environment/{environmentId}/onhand/bulk`

I tabellen nedan sammanfattas vilket betydelse de olika fälten har i JSON-brödtexten.

| Fält-ID | beskrivning |
|---|---|
| `id` | Ett unikt ID för den specifika ändringshändelsen. Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, kommer händelsen inte att räknas två gånger i systemet om den skickas på nytt. |
| `organizationId` | Identifierare för den organisation som är kopplad till händelsen. Detta värde mappas till en organisation eller dataområdes-ID i Supply Chain Management. |
| `productId` | Identifieraren för produkten. |
| `quantities` | Kvantiteten som lagerbehållningen måste ändras med. Om till exempel 10 nya böcker läggs till på en hylla blir detta värde `quantities:{ shelf:{ received: 10 }}`. Om tre böcker tas bort från hyllan eller säljs kommer detta värde att bli `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga. Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan. Lagersynligheten kan använda dimensionskonfigurationen för att mappa de anpassade dimensionerna till de allmänna standarddimensionerna. Om inget värde för `dimensionDataSource` anges kan du endast använda alla [basdimensioner](inventory-visibility-configuration.md#data-source-configuration-dimension) i dina frågor. |
| `dimensions` | Ett dynamiskt nyckel/värde-par. Värdena mappas till några av dimensionerna i Supply Chain Management. Du kan emellertid även lägga till anpassade dimensioner (till exempel _Källa_) för att ange om händelsen kommer från Supply Chain Management eller ett externt system. |

> [!NOTE]
> Parametrarna `SiteId` och `LocationId` skapar [partitionskonfigurationen](inventory-visibility-configuration.md#partition-configuration). Därför måste du ange dem i dimensioner när du skapar händelser för lagerbehållningsändring, ställer in eller åsidosätter lagerbehållningskvantiteter eller skapar reservationshändelser.

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

Följande exempel visar brödtext. I det här exemplet bokför du en ändringshändelse för produkten *T-shirt*. Denna händelse kommer från kassasystemet (POS), och kunden har returnerat en röd T-shirt till din butik. Denna händelse ökar kvantiteten av produkt *T-shirt* med 1.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Skapa flera ändringshändelser

Detta API kan skapa flera poster samtidigt. De enda skillnaderna mellan denna API och [en API med enskild](#create-one-onhand-change-event) är värden `Path` och `Body`. För detta API tillhandahåller `Body` en matris av poster. Det maximala antalet poster är 512, vilket innebär att bulk-API:t för behållningsändring kan stödja upp till 512 ändringshändelser åt gången.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Ställ in/åsidosätta lagerbehållning

API:t _Ställ in behållning_ åsidosätter aktuella data för den angivna produkten.

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

Följande exempel visar brödtext. Beteendet för detta API skiljer sig från beteendet för API:erna som beskrivs i avsnittet [Skapa ändringshändelser för behållning](#create-onhand-change-event). I detta exempel anges kvantiteten för produkten *T-shirt* som 1.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Skapa reservationshändelser

Om du vill använda *reserv*-API:t måste du öppna reservationsfunktionen och slutföra reservationskonfigurationen. Mer information finns i [Konfigurera reservation (tillval)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Skapa en reservationshändelse

Det går att göra en reservation mot olika datakällsinställningar. Om du vill konfigurera den här typen av reservation måste du först ange datakällan i `dimensionDataSource`-parametern. Sedan anger du i `dimensions`-parametern dimensioner enligt dimensionsinställningarna i måldatakällan.

När du anropar reservations-API:t kan du kontrollera reservationsvalideringen genom att ange den booleska parametern `ifCheckAvailForReserv` i begärandetexten. Ett värde `True` betyder att valideringen krävs, medan ett värde av `False` betyder att valideringen inte krävs. Standardvärdet är `True`.

Om du vill annullera en reservation eller ta bort reservationen av angivna lagerkvantiteter ställer du in kvantiteten på ett negativt värde och ställer in parametern `ifCheckAvailForReserv` på `False` för att hoppa över valideringen.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Skapa flera reservationshändelser

Detta API är en bulkversion av [API:t för en enskild händelse](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Behållningsfråga

Använd _Behållningsfråga_ för att hämta aktuella lagerbehållningsdata för dina produkter. API stöder för närvarande frågor upp till 100 enskilda artiklar efter `ProductID` värde. Flera `SiteID` och `LocationID` värden kan också anges i varje fråga. Maxgränsen definieras som `NumOf(SiteID) * NumOf(LocationID) <= 100`.

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

Parametern `groupByValues` bör följa din konfiguration för indexering. Mer information finns i [Hierarkikonfiguration för produktindex](./inventory-visibility-configuration.md#index-configuration).

Parametern `returnNegative` styr om resultatet innehåller negativa poster.

Följande exempel visar brödtext.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
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
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
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
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
