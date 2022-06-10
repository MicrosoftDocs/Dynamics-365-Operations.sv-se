---
title: Lagerfördelning för Lagersynlighet
description: I det här avsnittet beskrivs hur du ställer in och använder lagerallokeringsfunktionen, där du kan lägga det dedikerade lagret åt sidan för att säkerställa att du kan uppfylla dina mest vinstgivande kanaler eller kunder.
author: yufeihuang
ms.date: 05/20/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 4293ead4ccfc9ba04e8b9da437134b4e97569026
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786957"
---
# <a name="inventory-visibility-inventory-allocation"></a>Lagerfördelning för Lagersynlighet

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Affärsbakgrund och syfte

I många fall måste tillverkare, återförsäljare och andra leverantörer förboka lager för viktiga försäljningskanaler, platser eller kunder eller för särskilda försäljningshändelser. Lagerallokering är ett standardpraxis i planeringen av försäljningsverksamheten och utförs innan de faktiska försäljningsaktiviteterna inträffar och en försäljningsorder skapas.

Till exempel har ett cykelföretag begränsat lager tillgängligt för en mycket populär cykel. Företaget gör både online- och butiksförsäljningar. I varje försäljningskanal har företaget några viktiga partner (marknadsplats och stora återförsäljare) som kräver att en viss del av den tillgängliga lagerbehållningen för dessa ska sparas. Därför måste cykelföretaget kunna balansera lagerfördelningen mellan kanaler och hantera förväntningarna från sina VIP-partners. Det bästa sättet att nå båda målen är att använda lagerallokering, så att varje kanal och återförsäljare kan ta emot specifika allokerade kvantiteter som kan säljas till kunder senare.

Lagerallokeringen har två grundläggande affärssyften:

- **Lagersskydd (ringfencing)** – Organisationer vill i förväg tilldela begränsat eller begränsat lager till prioriterade kanaler, regioner, VIP-kunder och dotterbolag. Allokeringsfunktionen Lagersynlighet är det bästa att skydda det fördelade lagret, så att andra allokeringar, reservationer eller andra försäljningskrav inte påverkar det tidigare fördelade lagret.
- **Överförsäljningskontroll** – Allokeringsfunktionen för lager synlig innebär ett syfte med att begränsa de tidigare fördelade kvantiteterna, så att den mottagande parten (exempelvis en kanal eller kundgrupp) inte kommer att förbruka dem när den faktiska försäljningstransaktionen som baseras på en mjuk reservation genomförs.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Allokeringsdefinition i lagersynlighetstjänst

Även om allokeringsfunktionen i lagersynlighetstjänst inte innebär att fysiska lagerkvantiteter åsidosätts, refererar den till tillgänglig fysisk lagerkvantitet för att definiera dess initiala *inte tillgängliga för fördelning* för att fördela virtuell poolkvantitet. Lagerallokering i Lagersynlighet är en mjuk allokering. Det görs före faktiska försäljningstransaktioner och beror inte på försäljningsorder. Du kan till exempel tilldela lager till dina viktigaste försäljningskanaler eller stora företagsbutiker innan slutkunder besöker försäljningskanal eller butik för att köpa den.

Skillnaden mellan lagerfördelning och [reservation av mjukt lager](inventory-visibility-reservations.md) är att mjuk reservation vanligtvis är kopplad till faktiska försäljningstransaktioner (försäljningsorderrader). Om du vill använda allokerings- och mjukreservationsfunktionerna tillsammans rekommenderar vi därför att du först gör lagerallokering och sedan en mjuk reserv mot de fördelade kvantiteterna. Mer information finns i [Förbruka som en mjuk reservation](#consume-to-soft-reserved).

Med lagerallokeringsfunktionen kan våra försäljningsplanerare eller nyckelkontochefer hantera och förallokering av viktigt lager över allokeringsgrupper (t.ex. kanaler, regioner och kundgrupper). Det stöder också spårning, justering och analys av förbrukning i realtid mot allokerade kvantiteter så att påfyllnad eller omfördelning kan göras i tid. Denna förmåga att ha insyn i realtid i allokering, förbrukning och allokeringsbalans är särskilt viktig vid snabbförsäljning eller kampanjevenemang.

## <a name="terminology"></a>Terminologi

Följande termer och koncept är användbara i diskussioner om lagerallokering:

- **Allokeringsgrupp** – Gruppen som äger allokeringen, till exempel en försäljningskanal, kundgrupp eller ordertyp.
- **Allokeringsgruppvärde** – Värdet för varje allokeringsgrupp. Till exempel kan *webben* eller *butiken* vara värdet för allokeringsgruppen för försäljningskanal, medan *VIP* eller *normal* kan vara värdet för kundallokeringsgruppen.
- **Allokeringshierarki** – Ett sätt att kombinera allokeringsgrupper på ett hierarkiskt sätt. Du kan till exempel definiera *kanal* som hierarkinivå 1, *region* som nivå 2 och *kundgrupp* som nivå 3. Vid lagerallokering måste du följa allokeringshierarkisekvensen när du anger värdet för allokeringsgruppen. Till exempel kan du tilldela 200 röda cyklar till kanalen *Webb* regionen *London* och kundgruppen *VIP*.
- **Tillgänglig för allokering** – Den *virtuella gemensamma poolen* som anger vilken kvantitet som är tillgänglig för ytterligare allokering. Det är ett beräknat mått som du fritt kan definiera med hjälp av din egen formel. Om du även använder funktionen för mjuk reservation rekommenderar vi att du använder samma formel för att beräkna tillgängligt att fördela och tillgängligt att reservera.
- **Fördelat** – Ett fysiskt mått som visar den fördelade kvoten som kan förbrukas av allokeringsgrupperna.
- **Förbrukat** – Ett fysiskt mått som anger att kvantiteter som har förbrukats mot den ursprungliga allokerade kvantiteten. När antal läggs till det här fysiska måttet minskas det fördelade fysiska måttet automatiskt.

Följande illustration visar affärsflödet för lagerfördelning.

![Inventering Synlighetstilldelning affärsflöde.](media/inventory-visibility-allocation-flow.png "Inventering Synlighetstilldelning affärsflöde.")

## <a name="set-up-inventory-allocation"></a>Konfigurera Lagerfördelning

Lagerallokeringsfunktionen består av följande komponenter:

- De fördefinierade, allokeringsrelaterade datakällan, fysiska mått och beräknade mått.
- Anpassningsbara allokeringsgrupper som har maximalt åtta nivåer.
- En uppsättning av API:er (Allocation Application Programming Interfaces):

    - allokera
    - omallokera
    - ej allokerad
    - förbruka
    - fråga

Konfigureringsprocessen för allokeringsfunktionen har två steg:

- Ställ in [datakällan](inventory-visibility-configuration.md#data-source-configuration) och dess [mått](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Ställ in namn och hierarki för allokeringsgruppen.

### <a name="predefined-data-source"></a>Fördefinierad datakälla

När du aktiverar allokeringsfunktionen och anropar konfigurationsuppdaterings-API:t, skapar Lagersynlighet en fördefinierad datakälla och flera initiala mått.

Datakällan med namnet `@iv`.

Här är de första fysiska måtten:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Här är de första beräknade måtten:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Lägg till andra fysiska mått på det beräknade måttet som är tillgängligt att fördela

Om du vill använda allokering måste du ställa in det beräknade måttet som är tillgängligt att fördela (`@iv`.`@available_to_allocate`). Du har till exempel `fno` datakälla och `onordered` mått, kommer `pos` datakälla och `inbound` och du vill göra allokering till hands för summan av `fno.onordered` och `pos.inbound`. I detta fall ska `@iv.@available_to_allocate` innehålla `pos.inbound` och `fno.onordered` i formeln. Här är ett exempel:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Ändra namnet på allokeringsgruppen

Maximalt åtta namn på allokeringsgrupp kan ställas in. Grupperna har en hierarki.

Du ställer in gruppnamnen på sidan **Lagersynlighet Power App-konfiguration**. För att öppna den här sidan, i din Microsoft Dataverse miljö, öppna appen Lagersynlighet och välj **Konfiguration \> Allokering**.

Till exempel om du använder fyra gruppnamn och ställer in dem på \[`channel`, `customerGroup`, `region`, `orderType`\], dessa namn kommer att vara giltiga för tilldelningsrelaterade förfrågningar när du anropar API:et för konfigurationsuppdatering.

### <a name="allcoation-using-tips"></a>Tilldelning med tips

- För varje produkt ska allokeringsfunktionen använda på samma dimensionsnivå enligt den produktgrupphierarki du ställt in i [konfigurationen för produktindexhierarkin](inventory-visibility-configuration.md#index-configuration). Till exempel är indexhierarkin Webbplats, Plats, Färg, Storlek. Om du fördelar en viss kvantitet för en produkt på webbplatsen, plats, färgnivån. Nästa gång du använder för att allokera, bör även på Webbplats, Plats, Färgnivå, om du använder Webbplats, Plats, Färg, Storleksnivå eller Webbplats, Platsnivå, kommer data inte att vara konsekventa.
- Ändring av allokeringsgrupp påverkar inte data som sparas i tjänsten.
- Allokering ska ske när produkten har den positiva lagerkvantiteten.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Använda allokerings-API:t

För närvarande öppnas fem allokerings-API:er:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Allokera

Anropa `Allocate` API:t för att allokera en produkt som har särskilda dimensioner. Här är schemat för begärandetext.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Till exempel vill du tilldela en kvantitet på 10 för produkt *Cykel*, webbplats *1*, plats *11*, färg *röd*, kanal *Online*, kundgrupp *VIP* och region *USA*. För att göra denna allokering kan du ringa ett samtal som har följande brödtextinnehåll.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

Kvantiteten måste alltid vara mer än 0 (noll).

#### <a name="unallocate"></a>Ej allokerad

Använd `Unallocate` API om du vill återföra `Allocate` operation. Negativ kvantitet som inte är tillåten i en `Allocate` operation. Brödtexten för `Unallocate` är identisk med brödtexten `Allocate`.

#### <a name="reallocate"></a>Omallokera

Använd `Reallocate` API om du vill flytta en allokerad kvantitet till en annan gruppkombination. Här är schemat för begärandetext.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Du kan till exempel flytta två cyklar som har måtten \[site=1, location=11, color=red\] från allokeringsgruppen \[Online, VIP, US\] till allokeringsgruppen \[Online, VIP, EU\] genom att anropa `Reallocate` API och ange följande brödtext.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Förbruka

Använd `Consume` API när du vill bokföra förbrukningskvantiteten mot allokering. Du kan till exempel använda denna API för att flytta fördelad kvantitet till några verkliga mått. Här är schemat för begärandetext.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Det finns till exempel åtta allokerade allokeringar som har dimensionerna \[site=1, location=11, color=red\] för allokeringsgruppen \[Online, VIP, USA\]. Följande formel används för att fördela recept:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

Åtta till antalet allokeras från `pos.inbound` måttet.

Nu säljs tre sålda varor och de tas från allokeringspoolen. För att registrera denna flytt kan du ringa ett samtal som har följande begärandetext.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Efter detta samtal minskas den fördelade kvantiteten för produkten med 3. Dessutom kommer lagersynlighet att generera en ändringshändelse där `pos.inbound` = *-3*. Alternativt kan du behålla värdet för `pos.inbound` som det är och bara förbruka den tilldelade kvantiteten. I detta fall måste du antingen skapa ett annat fysiskt mått för att behålla de förbrukade kvantiteterna eller använda det fördefinierade måttet `@iv.@consumed`.

På denna begäran ska du observera att det fysiska mått du använder i brödtexten för comsume reqlgt ska använda motsatt modifertyp(Addition or Subtraktion), jämfört med modifierartypen som används i det beräknade måttet. Så i denna förbrukade brödtext, `iv.inbound` har värdet `Subtraction`, inte `Addition`.

`fno` datakällan kan inte användas i konsumtionskroppen eftersom vi alltid hävdade att lagersynlighet inte kan ändra någon data för `fno` datakällan. Dataflödet är enväg, vilket innebär att alla kvantitetsändringar för `fno` datakällan måste komma från din Supply Chain Management-miljö.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Förbruka som en mjuk reservation

`Consume` API kan också förbruka den allokerade kvantiteten som en mjuk reservation. I detta fall minskar operationen `Consume` den tilldelade kvantiteten och gör sedan en mjuk reservation för denna kvantitet. För att använda detta tillvägagångssätt måste du också använda funktionen [mjuk reservation](inventory-visibility-reservations.md) för Lagersynlighet.

Du har till exempel ställt in en modifierare för mjuk reservation (mått) som `iv.softreserved`. Följande formel används för det beräknade måttet som är tillgängligt att reservera:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

För att använda denna inställning med allokeringsfunktionen, lägg till `@iv.@allocated` till `iv.available_to_reserve` för att skapa följande formel:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved` – `@iv.@allocated`

Uppdatera sedan `@iv.@available_to_allocate` till samma värde.

När du vill förbruka en kvantitet på 3 och direkt reservera denna kvantitet, kan du ringa ett samtal som har följande förfrågan.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

Lägg märke till det i denna begäran `iv.softreserved` har värdet `Addition`, inte `Subtraction`.

#### <a name="query"></a>Fråga

Använd `Query` API när du vill hämta allokeringsrelaterad information för vissa produkter. Du kan begränsa resultatet med hjälp av dimensionsfilter och allokeringsgruppsfilter. Dimensionerna måste matcha exakt den som du vill hämta till exempel, \[site=1, location=11\] kommer att ha icke-relaterade resultat jämfört med \[site=1, location=11, color=red\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Använd till exempel \[site=1, location=11, color=red\] och tomt gruppfält för att få alla allokeringsposter:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Använd \[site=1, location=11, color=red\] och grupper \[channel=Online, customerGroup=VIP, region=US\] för att få allokeringsposter för den här gruppen:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
