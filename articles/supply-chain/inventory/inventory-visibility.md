---
title: Tillägg för lagersynlighet
description: I det här avsnittet beskrivs hur du installerar och konfigurerar tillägg för lagersynlighet för Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114680"
---
# <a name="inventory-visibility-add-in"></a>Tillägg för lagersynlighet

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.

All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå. Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.

Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov. Det går också att uppgradera indexet för att göra lagerfrågor.

Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare. Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.

I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).

## <a name="install-the-inventory-visibility-add-in"></a>Installera tillägget för lagersynlighet

Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS). LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.

Mer information finns i [Lifecycle Services, resurser](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Förutsättningar

Innan du installerar tillägget för lagersynlighet måste du göra följande:

- Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.
- Generera betanycklarna för erbjudandet i LCS.
- Aktivera betanycklarna för ditt erbjudande för din användare i LCS.
- Kontakta Microsoft produktteam för lagersynlighet och ange ett miljö-ID där du vill distribuera tilläggsprogrammet för lagersynlighet.

Om du har några frågor om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Installera tillägget

För att installera tillägget för lagersynlighet måste du göra följande:

1. Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.
1. Välj det projekt där miljön har distribuerats på startsidan.
1. Välj den miljö där du vill installera tillägget på projektsidan.
1. Bläddra nedåt på sidan miljö, tills avsnittet **miljötillägg** visas. Om avsnittet inte visas kontrollerar du att de nödvändiga betanycklarna har bearbetats fullständigt.
1. I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.
    ![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")
1. Välj länken **installera ett nytt tillägg**. En lista med tillgängliga tillägg öppnas.
1. Välj **lagertjänst** i listan. (Observera att detta nu kan vara listat som **Tillägg för lagersynlighet för Dynamics 365 Supply Chain Management**).
1. Ange värden för följande fält i miljön:

    - **AAD app-ID**
    - **AAD klientorganisationens ID**

    ![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")

1. Godkänn villkoren genom att markera kryssrutan **villkor**.
1. Välj **Installera**. Tilläggets status visas som **installerar**. När det är klart uppdaterar du sidan så att status ändras till **installerad**.

### <a name="get-a-security-service-token"></a>Hämta en säkerhetstoken för säkerhetstjänst

Hämta en säkerhetstjänsttoken genom att göra följande:

1. Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.
1. Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Metod** - `GET`
    - **Brödtext (formulärdata)**:

        | nyckel | värde |
        | --- | --- |
        | klient-ID | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resurs | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Du bör få `aadToken` i svar, som liknar följande exempel.

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

1. Formulera en JSON-begäran som liknar följande:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Där:
    - Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.
    - Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.
    - Ställ in alla andra värden enligt exemplet.

1. Skicka en HTTP-begäran med följande egenskaper:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Metod** - `POST`
    - **HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)
    - **Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.

1. Du får ett `access_token` i svar. Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet. Här är ett exempel:

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Avinstallera tillägget

För att avinstallera tillägget, välj **avinstallera**. Uppdatera LCS och tillägget för lagersynlighet tas bort. Avinstallationsprocessen kommer att ta bort registreringen av tillägget och även starta ett jobb för att rensa alla affärsdata som lagras i tjänsten.

## <a name="inventory-visibility-add-in-public-api"></a>Tillägg för lagersynlighet i ofentlig API

Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen. Den stöder tre huvudinteraktionstyper:

- Bokföring av behållningsändringar i tillägget från ett externt system.
- Fråga om aktuell behållning från ett externt system.
- Automatisk synkronisering med behållning av Supply Chain Management.

Den automatiska synkroniseringen ingår inte i det offentliga API utan hanteras i stället i bakgrunden för miljöer där tillägget lager synlighet har aktiverats.

### <a name="authentication"></a>Äkthetsbevisning

Plattformens säkerhetstoken används för att anropa tillägget för lagersynlighet, så du måste generera en Azure Active Directory token med Azure Active Directory-appen.

Mer information om hur du hämtar säkerhetstoken finns i [installera tillägget för lagersynlighet](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Konfigurera API för lagersynlighet

Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt. Konfigurationen kan variera beroende på vad som gäller för din miljö. Den omfattar huvudsakligen fyra delar:

- [Partitionering](#partitioning)
- [Dimensionskonfigurationer](#dimension-configurations)
- [Indexering](#indexing)
- [Anpassat mått](#custom-measurement)

#### <a name="partitioning"></a>Partitionering

Partitionering kan i stor grad påverka prestandan för API för lagersynlighet. Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågor.

`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*. Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.

> [!NOTE]
> *Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet. I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)

### <a name="dimension-configurations"></a>Dimensionskonfigurationer

Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.

I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.

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

> [!NOTE]
> Dimensionstypen som visas i föregående tabell är endast referens. Du behöver inte ange dimensionstypen i lagersynlighet.

Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.

Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar. Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.

Måldimensionerna måste vara en av följande:

- Standarddimensioner vid lagersynlighet
- Anpassade dimensioner

Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågan på dimensioner och bokföringshändelsen med dimensioner.

#### <a name="indexing"></a>Indexering

För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.

Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.

> [!NOTE]
> För närvarande kan du bara konfigurera index till maximalt fem. Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov. Om du till exempel vill söka efter produkter enligt följande:

- Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.
- I vissa fall vill du bara fråga den totala produkten.

Två index är definierade som följande:

- `["ColorId", "SizeId"]`
- `[]`

Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.

Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning. I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`. Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.

Du kan ange frågevillkor i den begärandetext.

Här är en exempel fråga på produkten med kombinationen färg och storlek.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Anpassat mått

Standardmåttkvantiteterna är kopplade till Supply Chain Management, men du kanske vill ha en kvantitet som består av en kombination av standardmått. För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågorna.

Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.

Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Förbrukningssystem | Beräknade mått | Datakälla | Modifierare | Beräkningstyp för modifierare |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Subtraktion |

Med detta kommer frågan för den anpassade måttkvantiteten att returnera följande resultat.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Bokföra lagerbehållningsändringar

Den exakta URL som händelsen ska skickas till beror på din geografiska region. Formuläret kommer att ha följande format:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.

En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till. Exempel:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Skicka behållningsändringar fråga exempel 1

I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.

Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Skicka behållningsändringar fråga exempel 2

I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna. Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>JSON dokumentfältegenskaper

De fält från exempel för JSON-frågor som tidigare har angetts har de egenskaper som anges i följande tabell.

| Fält-ID | beskrivning |
|---|---|
| `id` | Ett unikt ID för den specifika ändringshändelsen. Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet. |
| `organizationId` | Identifierare för den organisation som är kopplad till händelsen. Detta mappar till Supply Chain Management organisations eller dataområdes-ID. |
| `productId` | Den unika identifieraren av produkten i fråga. |
| `quantity` | Kvantiteten som behållningen måste ändras med. Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10. Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3. |
| `dimensionDataSource` | Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga. Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan. Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna. Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågorna.   |
| `dimensions` | En dynamisk uppsättning nyckel/värde-par. Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system. |

### <a name="querying-current-on-hand"></a>Fråga aktuell behållning

Slutpunkten för att hämta den aktuella behållningen har en liknande URL:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Den kommer att frågas med HTTP `POST`-metoden.

#### <a name="current-on-hand-query-example-1"></a>Aktuellt behållningsexempel 1

I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.

Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner. Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Aktuellt behållningsexempel 2

I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna. Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exempel på returresultat

Frågorna som visas i föregående exempel kan returnera resultatet.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
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

Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]