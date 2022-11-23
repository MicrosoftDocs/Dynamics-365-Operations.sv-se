---
title: Lagerallokering med Inventory Visibility
description: I denna artikel beskrivs hur du konfigurerar och använder funktionen för lagerallokering, där du kan lägga det dedikerade lagret åt sidan i syfte att säkerställa att du kan tillmötesgå dina mest vinstgivande kanaler eller kunder.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762683"
---
# <a name="inventory-visibility-inventory-allocation"></a>Lagerallokering med Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Affärsbakgrund och syfte

Organisationer måste ofta förallokera sin lagerbehållning i sina viktigaste försäljningskanaler, kundgrupper, regioner och kampanjhändelser för att säkerställa att det förallokerade lagret skyddas mot annan användning och bara kan förbrukas via försäljningstransaktioner som är relevanta för allokeringen. Lagerallokering i lagersynlighet är en komponent i planeringen av försäljningsverksamheten och utförs innan de faktiska försäljningsaktiviteterna inträffar och en försäljningsorder skapas.

Ett företag som kallas Contoso producerar till exempel en populär användare. Eftersom den senaste störningarna i leveranskedjan har påverkat all lagerhållning på väg där, har Contoso bara begränsat lagerbehållningen och måste använda den på bästa sätt. Contoso gör både online- och butiksförsäljningar. I varje försäljningskanal har företaget några viktiga partners (marknadsplatser och stora återförsäljare) som kräver att en viss del av den tillgängliga lagerbehållningen för cykeln ska sparas åt dem. Därför måste cykelföretaget kunna balansera lagerfördelningen mellan kanaler och hantera förväntningarna från sina VIP-partners. Det bästa sättet att nå båda målen är att använda lagerallokering, så att varje kanal och återförsäljare kan ta emot specifika allokerade kvantiteter som kan säljas till kunder senare.

Lagerallokeringen har två grundläggande affärssyften:

- **Lagersskydd (ringfencing)** – Organisationer vill i förväg tilldela begränsat eller begränsat lager till prioriterade kanaler, regioner, VIP-kunder och dotterbolag. Allokeringsfunktionen Lagersynlighet är det bästa att skydda det fördelade lagret, så att andra allokeringar, reservationer eller andra försäljningskrav inte påverkar det tidigare fördelade lagret.
- **Överförsäljningskontroll** – Allokeringsfunktionen för lager synlig innebär ett syfte med att begränsa de tidigare fördelade kvantiteterna, så att den mottagande parten (exempelvis en kanal eller kundgrupp) inte kommer att förbruka dem när den faktiska försäljningstransaktionen som baseras på en mjuk reservation genomförs.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Allokeringsdefinition i lagersynlighetstjänst

### <a name="allocation-virtual-pool"></a>Virtuell allokeringspool

Även om allokeringsfunktionen i lagersynlighet inte innebär att fysiska lagerkvantiteter åsidosätts, refererar den till tillgänglig fysisk lagerkvantitet för att definiera dess initiala *inte tillgängliga för fördelning* för att fördela virtuell poolkvantitet. Lagerallokering i Lagersynlighet är en mjuk allokering. Det görs före faktiska försäljningstransaktioner och beror inte på försäljningsorder. Du kan till exempel tilldela lager till dina viktigaste försäljningskanaler eller stora företagsåterförsäljare innan slutkunder besöker försäljningskanal eller butik för att köpa.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Skillnad mellan lagerallokering och mjuk reservation

[Mjuk reservationer](inventory-visibility-reservations.md) länkas vanligtvis till faktiska försäljningstransaktioner (försäljningsorderrader). Både allokering och mjuk reservation kan användas oberoende av varandra, men om du vill använda dem tillsammans bör mjuk reservation göras efter allokeringen. Vi rekommenderar att du först gör lagerallokering och sedan mjuk reserverar mot de allokerade kvantiteterna för att uppnå nästan realtidsförbrukning mot allokering. Mer information finns i [Förbruka som en mjuk reservation](#consume-to-soft-reserved).

Med lagerallokeringsfunktionen kan våra försäljningsplanerare eller nyckelkontochefer hantera och förallokering av viktigt lager över allokeringsgrupper (t.ex. kanaler, regioner och kundgrupper). Det stöder också spårning, justering och analys av förbrukning i realtid mot allokerade kvantiteter så att påfyllnad eller omfördelning kan göras i tid. Denna förmåga att ha insyn i realtid i allokering, förbrukning och allokeringsbalans är särskilt viktig vid snabbförsäljning eller kampanjevenemang.

## <a name="terminology"></a>Terminologi

Följande termer och koncept är användbara i diskussioner om lagerallokering:

- **Allokeringsgrupp** – Gruppen som äger allokeringen, till exempel en försäljningskanal, kundgrupp eller ordertyp.
- **Allokeringsgruppvärde** – Värdet för varje allokeringsgrupp. Till exempel kan *webben* eller *butiken* vara värdet för allokeringsgruppen för försäljningskanal, medan *VIP* eller *normal* kan vara värdet för kundallokeringsgruppen.
- **Allokeringshierarki** – Ett sätt att kombinera allokeringsgrupper på ett hierarkiskt sätt. Du kan till exempel definiera *kanal* som hierarkinivå 1, *region* som nivå 2 och *kundgrupp* som nivå 3. Vid lagerallokering måste du följa allokeringshierarkisekvensen när du anger värdet för allokeringsgruppen. Till exempel kan du tilldela 200 röda cyklar till kanalen *Webb* regionen *London* och kundgruppen *VIP*.
- **Tillgänglig för allokering** – Den *virtuella gemensamma poolen* som anger vilken kvantitet som är tillgänglig för ytterligare allokering. Det är ett beräknat mått som du fritt kan definiera med hjälp av din egen formel. Om du även använder funktionen för mjuk reservation rekommenderar vi att du använder samma formel för att beräkna tillgängligt att fördela och tillgängligt att reservera.
- **Fördelat** – Ett fysiskt mått som visar den fördelade kvoten som kan förbrukas av allokeringsgrupperna. Dras av samtidigt som den förbrukade kvantiteten läggs till.
- **Förbrukat** – Ett fysiskt mått som anger att kvantiteter som har förbrukats mot den ursprungliga allokerade kvantiteten. När antal läggs till det här fysiska måttet minskas det fördelade fysiska måttet automatiskt.

Följande illustration visar affärsflödet för lagerfördelning.

![Inventering Synlighetstilldelning affärsflöde.](media/inventory-visibility-allocation-flow.png "Inventering Synlighetstilldelning affärsflöde.")

I följande bild visas allokeringshierarkin och allokeringsgrupperna. Den *virtuella gemensamma poolen* som visas här är kvantiteten som är tillgänglig att fördela.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Allokeringshierarki med lagersynlighet" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

Konfigureringsprocessen för allokeringsfunktionen har tre steg:

- Aktivera funktionen i programmet lagersynlighet genom att gå till **Konfiguration \> Funktionshantering och inställningar \> Allokering**.
- Ställ in [datakällan](inventory-visibility-configuration.md#data-source-configuration) och dess [mått](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Ställ in namn och hierarki för allokeringsgruppen.

### <a name="predefined-data-source"></a>Fördefinierad datakälla

När du aktiverar allokeringsfunktionen och anropar konfigurationsuppdaterings-API:t, skapar Lagersynlighet en fördefinierad datakälla och flera initiala mått.

Datakällan med namnet `@iv`. Den innehåller en uppsättning fysiska standardmått. Du kan visa dem från programmet Lagersynlighet genom att gå till **Konfiguration av \> Datakälla**. Du bör se **Datakälla – @IV**. Expandera `@iv` datakällan om du vill visa listan över inledande fysiska mått:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Välj fliken **Beräknade mått** om du vill visa det ursprungliga beräknade måttet, som kallas `@iv.@available_to_allocate`:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Lägg till andra fysiska mått på det beräknade måttet som är tillgängligt att fördela

Om du vill använda allokering måste du korrekt konfigurera formeln för det beräknade måttet som är tillgängligt att allokera (`@iv.@available_to_allocate`). Du har till exempel `fno` datakälla och `onordered` mått, kommer `pos` datakälla och `inbound` och du vill göra allokering för lagerbehållning för summan av `fno.onordered` och `pos.inbound`. I detta fall ska `@iv.@available_to_allocate` innehålla `pos.inbound` och `fno.onordered` i formeln. Här följer ett exempel:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> Datakälla `@iv` är en fördefinierad datakälla och de fysiska mått som definierats i `@iv` med prefixet `@` är fördefinierade mått. Måtten är en fördefinierad konfiguration för allokeringsfunktionen. Det gör att du inte ändrar eller tar bort dem eller du kanske stöter på oväntade fel när du använder allokeringsfunktionen.
>
> Du kan lägga till nya fysiska mått till det fördefinierade beräknade `@iv.@available_to_allocate` måttet, men du får inte ändra dess namn.

### <a name="manage-allocation-groups"></a>Hantera allokeringsgrupper

Maximalt åtta namn på allokeringsgrupp kan ställas in. Grupperna har en hierarki. Följ dessa steg för att visa och uppdatera allokeringsgrupper.

1. Logga in i din Power Apps-miljö och öppna **Lagersynlighet**.
1. Öppna sidan **Konfiguration** och på fliken **Allokering** välj **Redigera konfiguration**. Som standard finns det en allokeringshierarki som har fyra lager: `Channel` (översta lagret), `customerGroup` (andra lagret),`Region` (tredje lagret) och `OrderType` (fjärde lagret).
1. Du kan ta bort en befintlig allokeringsgrupp genom att markera ett **X** bredvid den. Du kan också lägga till nya allokeringsgrupper i hierarkin genom att ange namnet på varje ny grupp direkt i fältet.

    > [!IMPORTANT]
    > Var försiktig när du tar bort eller ändrar allokeringshierarkimappningen. Anvisningar finns i [Tips om hur du använder allokering](#allocation-tips).

1. När du är klar med konfigureringen av allokeringsgruppen och hierarkiinställningarna sparar du ändringarna och väljer sedan **Uppdatera konfiguration** uppe till höger. Värdena för de konfigurerade allokeringsgrupperna kommer att uppdateras när du skapar en tilldelning genom att använda antingen användargränssnittet eller API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). Mer information om båda tillvägagångssätten finns senare i den här artikeln.

Om du använder fyra gruppnamn och konfigurerar dem på \[`channel`, `customerGroup`, `region`, `orderType`\], dessa namn kommer att vara giltiga för tilldelningsrelaterade förfrågningar när du anropar API:et för konfigurationsuppdatering.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Tips för att använda allokering

- För varje produkt ska allokeringsfunktionen använda samma *dimensionsnivå* enligt den produktindexhierarki du angett i [hierarkikonfigurationen för produktindex](inventory-visibility-configuration.md#index-configuration). Låt oss anta att din indexhierarki är \[`Site`, `Location`, `Color`. `Size`\] Om du allokerar viss kvantitet för en produkt på dimensionsnivån \[`Site`, `Location`, `Color`\] bör du nästa gång du vill allokera den här produkten också allokera på samma nivå, \[`Site`, `Location`, `Color`\]. Om du använder nivån \[`Site`, `Location`, `Color`, `Size`\] eller \[`Site`, `Location`\] kommer datan att vara inkonsekvent.
- **Ändring av allokeringsgrupper och hierarkin:** Om allokeringsdata redan finns i systemet, kommer radering av befintliga allokeringsgrupper eller en förändring i allokeringsgruppshierarkin att korrumpera den befintliga mappningen mellan allokeringsgrupperna. Se därför till att rensa alla gamla data manuellt innan du uppdaterar din nya konfiguration. Eftersom tillägg av nya allokeringsgrupper i den lägsta hierarkin inte påverkar befintliga mappningar behöver du dock inte rensa data.
- Allokeringen lyckas bara om produkten har en positiv `available_to_allocate` kvantitet.
- Om du vill allokera produkter från en grupp med hög *allokeringsnivå* till en undergrupp använder du `Reallocate`-API:t. Du har till exempel en hierarki för allokeringsgrupp \[`channel`, `customerGroup`, `region`, `orderType`\] och vill allokera en viss produktmängd från allokeringsgruppen \[Online, VIP\] till underallokeringsgruppen \[Online, VIP, EU\] - använd då API:t `Reallocate` för att flytta kvantiteten. Om du använder APIT:t `Allocate` allokeras kvantiteten från den virtuella gemensamma poolen.
- För att se övergripande produkttillgänglighet (den gemensamma poolen), använd [lagerbehållning](inventory-visibility-api.md#query-on-hand) API för att begära lagerbeloppet som är *tillgänglig att allokera*. Du kan sedan fatta allokering beslut utifrån denna information.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Använda allokerings-API:t

För närvarande öppnas fem allokerings-API:er:

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** – Detta API används för att skapa den initiala allokeringen.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Detta API används för att återställa eller ta bort de tilldelade kvantiteterna.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Detta API används för att flytta den tilldelade kvantiteten från en befintlig allokering till andra allokeringsgrupper.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Detta API används för att dra av (använda) den tilldelade kvantiteten.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Detta API används för att kontrollera befintliga allokeringsposter mot allokeringsgrupperna och hierarkin.

### <a name="allocate"></a>Allokera

Anropa `Allocate` API:t för att allokera en produkt som har särskilda dimensioner. Här är schemat för begärandetexten.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Ej allokerad

Använd `Unallocate` API om du vill återföra åtgärden `Allocate`. Negativ kvantitet som inte är tillåten i en `Allocate`-åtgärd. Brödtexten för `Unallocate` är identisk med brödtexten `Allocate`.

### <a name="reallocate"></a>Omallokera

Använd `Reallocate` API om du vill flytta en allokerad kvantitet till en annan gruppkombination. Här är schemat för begärandetexten.

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Förbruka

Använd `Consume` API när du vill bokföra förbrukningskvantiteten mot allokering. Du kan till exempel använda denna API för att flytta fördelad kvantitet till några verkliga mått. Här är schemat för begärandetexten.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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

Nu säljs tre cyklar, som tas från allokeringspoolen. För att registrera denna flytt kan du ringa ett samtal som har följande begärandetext.

```json
{
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

I denna begäran ska du observera att det fysiska mått du använder i begärandetexten för förbrukning (consume) ska använda motsatt modifertyp (Addition eller Subtraktion) jämfört med modifierartypen som används i det beräknade måttet. Så i denna förbrukade brödtext, `iv.inbound` har värdet `Subtraction`, inte `Addition`.

`fno`-datakällan kan inte användas i brödtexten för consume eftersom vi alltid hävdat att Lagersynlighet inte kan ändra någon data för `fno`-datakällan. Dataflödet är enväg, vilket innebär att alla kvantitetsändringar för `fno` datakällan måste komma från din Supply Chain Management-miljö.

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Förbruka som en mjuk reservation

`Consume` API kan också förbruka den allokerade kvantiteten som en mjuk reservation. I detta fall minskar åtgärden `Consume` den tilldelade kvantiteten och gör sedan en mjuk reservation för denna kvantitet. För att använda detta tillvägagångssätt måste du också använda funktionen [mjuk reservation](inventory-visibility-reservations.md) för Lagersynlighet.

Du har till exempel ställt in en fysiskt mått för mjuk reservation som `iv.softreserved`. Följande formel används för det beräknade måttet som är tillgängligt att reservera:

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Fråga

Använd `Query`-API när du vill hämta allokeringsrelaterad information för vissa produkter. Du kan begränsa resultatet med hjälp av dimensionsfilter och allokeringsgruppsfilter. Dimensionerna måste matcha exakt den som du vill hämta. Till exempel kommer \[site=1, location=11\] att ha icke-relaterade resultat jämfört med \[site=1, location=11, color=red\].

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Användargränssnittet för allokering

Du kan hantera tilldelningar manuellt via användargränssnittet genom att öppna appen Lagersynlighet och gå till **Driftsynlighet \> Allokering**. Därifrån kan du utföra någon av de åtgärder som beskrivs i följande delgrupper.

### <a name="create-an-allocation"></a>Skapa en allokering

Följ de här stegen när du vill skapa en allokering från sidan **Allokering** i programmet lagersynlighet.

1. Välj **Allokera**.
1. Ställ in basfält, dimensioner och målallokeringsgruppers värden. (När du väljer att samla in datakällan i avsnittet **Dimension**, använd först listrutan för att ange dimensionerna (till exempel `siteId`). Ange sedan dimensionsvärden i de fält som visas.)
1. Välj **skicka**.

### <a name="consume-an-allocation"></a>Förbruka en allokering

Välj **Förbruka** om en allokering ska förbrukas. För att säkerställa att du konsumerar inom rätt allokeringsgrupp och hierarki anger du samma uppsättningar av organisations- och dimensionsdetaljer som du angav när du skapade allokeringen.

### <a name="reallocate-an-allocation"></a>Omallokera en allokering

Välj **Omallokera** om att flytta befintlig allokerad kvantitet från en uppsättning allokeringsgrupper till en annan.

### <a name="query-existing-allocations"></a>Fråga befintliga allokeringar

Välj **Fråga** och ange sedan värden för produkt, organisation, dimension och allokeringsgrupp för att erhålla frågeresultat från befintliga allokeringar.
