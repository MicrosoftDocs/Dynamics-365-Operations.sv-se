---
title: Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova
description: Denna artikel beskriver hur du schemalägger framtida beredskapsändringar och beräknar kvantiteter disponibla att lova (ATP).
author: yufeihuang
ms.date: 05/11/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f831c5d5719bbbd72c7cff37b8b35826f48ce6e4
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719319"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova

[!include [banner](../includes/banner.md)]

lagerbehållning beskrivs hur du konfigurerar funktionen *Behållningsschema för ändringsplan* för att kunna tidsplanera framtida ändringar av lagerbehållningen och beräkna kvantiteter som är tillgängliga att lova. ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund i nästa period. Om du använder den här beräkningen kan du öka möjligheten att uppfylla ordern mycket.

För många tillverkare, återförsäljare och säljare räcker det inte att veta vad som finns i nuläget. De måste ha fullständig insyn i framtida tillgänglighet. Framtida tillgänglighet ska ta hänsyn till framtida leverans, framtida efterfrågan och tillgängligt att leverera tillgängligt att leverera.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Aktivera och konfigurera funktionerna

Innan du kan använda slutet på ett leverantörsantal måste du konfigurera en eller flera beräknade mått för att beräkna kvantiteterna för tillgängliga att välja mellan. Du måste även aktivera funktionen och konfigurera inställningar för ATP-inställningar i Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Ställ in beräknade mått för ATP-kvantiteter

*Mått för ATP-kvantiteter* är ett fördefinierat beräknat mått som vanligtvis används för att hitta den tillgängliga kvantiteten som för närvarande är tillgänglig. *Leveranskvantiteten* är summan av kvantiteter för de fysiska mått som har en modifieringstyp av *tillägg* och *efterfrågekvantitet* är summan av kvantiteter för de fysiska mått som har en modifieringstyp av *subtraktion*.

Du kan lägga till flera beräknade mått för att beräkna flera ATP-kvantiteter. Det totala antalet distinkta fysiska mått över alla ATP-beräknade mått bör dock vara mindre än nio.

> [!IMPORTANT]
> Ett beräknat mått är en sammansättningen av fysiska mått. Formeln kan endast innehålla fysiska mått utan dubbletter, inte beräknade mått.

Till exempel ställer du in följande beräknade mått:

**Disponibel lagerbehållning** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

Summan (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) representerar leverans och summan (*ReservPhysical* + *SoftReservePhysical* + *Outbound*) representerar efterfrågan. Därför kan det beräknade måttet förstå på följande sätt:

**Disponibel lagerbehållning** = *Leverans* – *Efterfrågan*

Du kan lägga till ytterligare ett beräknat mått för att beräkna **Fysisk behållning** ATP kvantiteten.

**Fysisk behållning** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*Outbound*)

Det finns åtta distinkta fysiska mått över dessa två ATP-beräknade mått: *PhysicalInvent*, *OnHand*, *Unrestricted*, *QualityInspection*, *Inbound*, *ReservPhysical*, *SoftReservePhysical* och *Outbound*.

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

- **Datum** – Datumet som resultatet gäller. Tidszonen är Coordinated Universal Time (UTC).
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
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | | | 17 | 17 |
    | 2022-02-04 | 20 | | | 17 | 17 |
    | 2022-02-05 | 20 | | | 17 | 17 |
    | 2022-02-06 | 20 | | | 17 | 17 |
    | 2022-02-07 | 20 | | | 17 | 17 |

1. På det aktuella datumet (1 februari 2022) skickar du en tidsplanerad leveranskvantitet på 10 februari 3 februari 2022. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | 10 | | 27 | 27 |
    | 2022-02-04 | 20 | | | 27 | 27 |
    | 2022-02-05 | 20 | | | 27 | 27 |
    | 2022-02-06 | 20 | | | 27 | 27 |
    | 2022-02-07 | 20 | | | 27 | 27 |

1. På aktuellt datum (1 februari 2022) skickar du följande planerade kvantitetsändringar:

    - Efterfrågekvantitet på 15 februari 4 februari 2022
    - Leveranskvantitet på 1 februari 5 februari 2022
    - Leveranskvantitet på 3 februari 6 februari 2022

    Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 12 |
    | 2022-02-02 | 20 | | | 17 | 12 |
    | 2022-02-03 | 20 | 10 | | 27 | 12 |
    | 2022-02-04 | 20 | | 15 | 12 | 12 |
    | 2022-02-05 | 20 | 1 | | 13 | 13 |
    | 2022-02-06 | 20 | 3 | | 16 | 16 |
    | 2022-02-07 | 20 | | | 16 | 16 |

1. På aktuellt datum (1 februari 2022) du skickar den planerade efterfrågan på 3. Därför måste du bekräfta ändringen så att den återspeglas i din faktiska lagerhållningskvantitet. Om du vill bekräfta ändringen skickar du en händelse för behållningsändring som har en utgående kvantitet på 3. Du måste sedan återställa den tidsplanerade ändringen genom att skicka en tidsplan för som har en utgående kvantitet på -3. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 17 | | 0 | 17 | 12 |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |

1. På nästa dag (2 februari 2022) skiftar tidsplanperioden framåt med en dag. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |
    | 2022-02-08 | 17 | | | 16 | 16 |

1. Två dagar senare (4 februari 2022) har dock leveranskvantiteten 10 som planerats för den 3 februari inte anlänt. Tabellen nedan visar resultatet.

    | Datum | Behållning | Schemalagd leverans | Schemalagd efterfrågan | Projekterad behållning | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-04 | 17 | | 15 | 2 | 2 |
    | 2022-02-05 | 17 | 1 | | 3 | 3 |
    | 2022-02-06 | 17 | 3 | | 6 | 6 |
    | 2022-02-07 | 17 | | | 6 | 6 |
    | 2022-02-08 | 17 | | | 6 | 6 |
    | 2022-02-09 | 17 | | | 6 | 6 |
    | 2022-02-10 | 17 | | | 6 | 6 |

    Som du ser påverkas inte de planerade (men inte utfästa) lagerändringarna den faktiska lagerhållningskvantiteten.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Skicka ändringsscheman, ändringshändelser och ATP-frågor via API:t

Med följande URL-adresser för program programming interface (API) kan du skicka behållningsändringsscheman, ändra händelser och frågor.

| Sökväg | Metod | Beskrivning |
| --- | --- | --- |
| `/api/environment/{environmentId}/onhand/changeschedule` | `POST` | Skapa en schemalagd engångs-ändring. |
| `/api/environment/{environmentId}/onhand/changeschedule/bulk` | `POST` | Skapa flera schemalagda engångs-ändringar. |
| `/api/environment/{environmentId}/onhand` | `POST` | Skapa en ändringshändelse för behållning. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Skapa flera ändringshändelser. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Fråga genom att använda `POST` metoden. |
| `/api/environment/{environmentId}/onhand` | `GET` | Fråga genom att använda `GET` metoden. |
| `/api/environment/{environmentId}/onhand/exactquery` | `POST` | Exakt fråga genom att använda `POST` metoden. |

Mer information finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md).

### <a name="create-one-on-hand-change-schedule"></a>Skapa ett aktuellt förändringsschema

Planerad lagerbehållningsändring skapas genom att du skickar en `POST` begäran till relevant URL för lagertjänst (mer information finns i [Skicka ändringsscheman, ändringshändelser och ATP-frågor via API](#api-urls)-avsnittet). Du kan även skicka bulkbegäranden.

Planerad lagerbehållningsändring måste vara mellan det aktuella datumet och slutet för den aktuella tidsplanerade perioden. Datumtidsformatet skulle vara *år-månad-dag* (till exempel, **2022-02-01**). Tidsformatet måste bara vara korrekt till dagen.

Detta API skapar en enskild planerad lagerbehållningsändring.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule
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
        dimensionDataSource: string, # optional
        dimensions: {
            [key:string]: string,
        },
        quantitiesByDate: {
            [datetime:datetime]: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
    }
```

Följande exempel visar brödtext utan `dimensionDataSource`.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    },
    "quantitiesByDate":
    {
        "2022-02-01": // today
        {
            "pos":{
                "inbound": 10
            }
        }
    }
}
```

### <a name="create-multiple-on-hand-change-schedules"></a>Skapa flera planerade lagerbehållningsändringar

Detta API kan skapa flera poster samtidigt. De enda skillnaderna mellan denna API och en API med enskild är värden `Path` och `Body` värden. För detta API tillhandahåller `Body` en matris av poster. Det maximala antalet poster är 512. Därför kan bulk-API:et för befintliga förändringsscheman stödja upp till 512 schemalagda ändringar åt gången.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule/bulk
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
            quantitiesByDate: {
                [datetime:datetime]: {
                    [dataSourceName:string]: {
                        [key:string]: number,
                    },
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
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-01": // today
            {
                "pos":{
                    "inbound": 10
                }
            }
        }
    },
    {
        "id": "id-car-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-05":
            {
                "pos":{
                    "outbound": 10
                }
            }
        }
    }
]
```

### <a name="create-on-hand-change-events"></a>Skapa ändringshändelser för behållning

Ändringshändelser för behållning görs genom att du skickar en `POST` begäran till relevant URL för lagertjänst (mer information finns i [Skicka ändringsscheman, ändringshändelser och ATP-frågor via API](#api-urls)-avsnittet). Du kan även skicka bulkbegäranden.

> [!NOTE]
> Ändringshändelser vid handen är inte unika för ATP-funktionaliteten utan är en del av standardinventeringssynlighets-API. Det här exemplet har inkluderats eftersom händelser är relevanta när du arbetar med ATP. Ändringshändelser vid handen är inte unika för ATP-funktionaliteten utan är en del av standardinventeringssynlighets-API `quantities` i stället för `quantityByDate` i meddelandetexten. Mer information om händelser för lagerbehållningsändring och andra funktioner i API:erna för lager synlighet finns i [Allmänna API:er för lager](inventory-visibility-api.md#create-one-onhand-change-event).

Exempel på begäran som innehåller en enskild ändringshändelse för behållning.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red"
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
> Oavsett om `returnNegative` parametern är inställd på *true* eller *false* i begärandetext, kommer resultatet att innehålla negativa värden när du ställer frågor för tidsplanerade ändringar av behållning och resultat av valörerna. Dessa negativa värden inkluderas eftersom, om endast efterfrågeorder planeras, eller om leveranskvantiteterna är mindre än efterfrågekvantiteterna, kommer de planerade lagerändringskvantiteterna att vara negativa. Om negativa värden inte ingår i det här programmet blir resultaten det verkliga. Mer information om det här alternativet och hur det fungerar för andra typer av frågor finns i [Offentliga API:er för Lagersynlighet](inventory-visibility-api.md#query-with-post-method).

### <a name="query-by-using-the-post-method"></a>Fråga genom att använda POST-metoden

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

Följande exempel visar hur du skapar ett indexfråga brödtext som kan skickas till Lagersynlighet med hjälp av `POST`-metoden.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "SiteId": ["1"],
        "LocationId": ["11"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-by-using-the-get-method"></a>Fråga genom att använda GET-metoden

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

Följande exempel visar hur du skapar indexfråga för en begäran-URL som en `GET` begäran.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&LocationId=11&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

Resultatet av denna `GET` begäran är exakt detsamma som resultatet av `POST` begäran i det föregående exemplet.

### <a name="exact-query-by-using-the-post-method"></a>Exakt fråga genom att använda POST-metoden

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

Följande exempel visar hur du skapar ett exakt fråga brödtext som kan skickas till Lagerfinlighet med hjälp av `POST`-metoden.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "dimensions": ["SiteId", "LocationId"],
        "values": [
            ["1", "11"]
        ]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-result-example"></a>Exempel på frågeresultat

Någon tidigare frågeexempel kan ge följande svar. I det här exemplet konfigureras systemet med följande inställningar:

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
