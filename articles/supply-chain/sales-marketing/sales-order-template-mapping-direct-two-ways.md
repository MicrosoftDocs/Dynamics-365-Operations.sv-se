---
title: Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningorder direkt mellan Dynamics 365 Sales och Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 7c8831203ae30991ff8acf1926aafc2d1839aeb2
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251280"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management

[!include [banner](../includes/banner.md)]

I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningorder direkt mellan Dynamics 365 Sales och Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att direktsynkronisera försäljningsorder mellan Sales och Supply Chain Management.

- **Namn på mallar i dataintegrering:** 

    - Försäljningsorder (Sales till Supply Chain Management) - direkt
    - Försäljningsorder (Supply Chain Management till Sales) - direkt

- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - Orderrubrik
    - Orderrad

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:

- Produkter (Supply Chain Management till Sales) - direkt
- Konton (Sales till Supply Chain Management)-direkt (om den används)
- Kontakter till kunder (Sales till Supply Chain Management) - direkt (om den används)

## <a name="entity-set"></a>Ange entiteten

| Hantering av underleverantörer  | Försäljning             |
|-------------------------|-------------------|
| CDS-försäljningsorderrubrik | Försäljningsorder       |
| CDS-försäljningsorderrader   | Försäljningsorderinformation |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsorder skapas i Sales och synkroniseras till Supply Chain Management **Kör projekt** initieras för ett projekt baserat på mallen **Försäljningsorder (Sales till Supply Chain Management) - direkt** mall. Du kan bara aktivera och synkronisera om alla order från Sales om alla **Orderprodukter** består av produkter som underhålls externt. Det kan därför inte finnas någon produkt ej i register. När ordern har aktiverats blir försäljningsorder skrivskyddade i användargränssnittet (UI). Då görs uppdateringar från Supply Chain Management. När försäljningsordern har statusen **bekräftad**, kan ett projekt som baseras på **försäljningsorder (Supply Chain Management till Sales) - direkt** använda mallen för att synkronisera uppdateringar eller slutförandestatus från Supply Chain Management till Sales.

Du behöver inte skapa order i Sales. Du kan skapa nya försäljningsorder i Supply Chain Management i stället. När en försäljningsorder har statusen **bekräftad**, synkroniseras den till Sales som beskrivs ovan.

I Supply Chain Management hjälper filter i mallen till att endast relevanta försäljningsorder inkluderas i synkroniseringen:

- På försäljningsordern härstammar både beställande kund och fakturerande kund från Sales inkluderas i synkroniseringen. I Supply Chain Management används fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** för att filtrera försäljningsorder från dataenheterna.
- Försäljningsordern i Supply Chain Management måste bekräftas. Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis **Levererad** eller **Fakturerad** synkroniseras till Sales.
- När en försäljningsorder skapas eller ändras måste batch-jobbet **Beräkna försäljningstotalen** i Supply Chain Management köras. Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales.

## <a name="freight-tax"></a>Moms för frakt

Sales stöder inte moms på huvudnivå eftersom moms lagras på radnivå. För att stödja moms på huvudnivå från Supply Chain Management, som t.ex moms på frakt, synkroniserar systemet moms på Sales som en produkt ej i register som heter **fraktmoms** och som har momsbeloppet från Supply Chain Management. På så sätt kan standardprisberäkningen i Sales användas för summor, även när det är moms på huvudnivå från Supply Chain Management.

## <a name="discount-calculation-and-rounding"></a>Rabattberäkning och avrundning.

Rabattberäkningsmodellen i Sales avviker från rabattberäkningsmodell i Supply Chain Management. I Supply Chain Management kan det slutgiltiga rabattbeloppet på en försäljningsrad vara resultatet av en kombination av rabattbelopp och rabattsatser. Om detta slutliga rabattbelopp divideras med antalet på raden, kan avrundning uppstå. Den här typen av avrundning inkluderas inte om ett avrundat rabattbelopp per enhet synkroniseras till Sales. För att garantera att det fullständiga rabattbeloppet från en försäljningsrad i Supply Chain Management synkroniseras korrekt till Sales, måste hela beloppet synkroniseras utan att divideras med radkvantiteten. Därför måste du definiera **rabattberäkningsmetod** som **radartikel** i Sales.

När en försäljningsorderrad synkroniseras från Sales till Supply Chain Management används fullständig radrabatt. Eftersom Supply Chain Management inte har några fält som kan innehålla fullständiga rabattbeloppet för en rad, divideras beloppet med kvantiteten och lagras i fältet **radrabatt**. All avrundning som uppstår i denna division lagras i fältet **försäljningstillägg** på försäljningsraden.

### <a name="example"></a>Exempel

**Synkronisering från Sales till Supply Chain Management**

- **Sales:** kvantitet = 3 per radrabatt = $10,00
- **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift =-0,01 $ 

**Synkronisering från Supply Chain Management till Sales**

- **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift =-0,01 $
- **Sales:** kvantitet = 3 per radrabatt = (3 × $3,33) + $0,01 = $10,00

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Nya fält har lagst till i enheten **Order** och visas på sidan:

- **Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Supply Chain Management.
- **Bearbetningsstatus** - Detta fält visar bearbetningsstatusen för ordern i Supply Chain Management. Följande värden finns:

    - **Utkast** – inledande status när en order skapas i Sales. I Sales kan endast order med denna bearbetningsstatus redigeras.
    - **Aktiv** – statusen efter att ordern har aktiverats i Sales med hjälp av knappen **aktivera**.
    - **Bekräftat**
    - **Följesedel**
    - **Fakturerad**
    - **Plockad**
    - **Delvis plockad**
    - **Delvis förpackad**
    - **Skeppat**
    - **Delvis levererad**
    - **Delvis fakturerad**
    - **Avbröts**

Inställningen **Har endast externt hanterade produkter** används under orderaktivering för att konstant spåra om en försäljningsorder består av externt underhållna produkter. Om en försäljningsorder helt består av externt underhållna produkter, underhålls produkter i Supply Chain Management. Denna inställning hjälper till att garantera att du inte aktiverar och försöker synkronisera försäljningsorderraderna som har produkter som är okända för Supply Chain Management.

Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Supply Chain Management och synkroniseras med Sales. Dessa order kan inte redigeras eftersom försäljningsorderinformationen synkroniseras från Supply Chain Management efter aktivering.

Status för försäljningsorder förblir **aktiv** för att se till att ändringar från Supply Chain Management når Försäljningsordern i Sales. För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv** i dataintegreringsprojektetet.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar följande inställningar i systemen.

### <a name="setup-in-sales"></a>Inställningar i Sales

- Se till att behörigheterna ställs in för teamet som användaren från din Sales-anslutning har tilldelats. Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst. Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.

    Gå till **Inställningar** &gt; **Säkerhet** &gt; **Team**, välj relevant team, klicka på **Hantera rolelr** och välj en roll med önskade behörigheter, t.ex. **systemadministratör**.

- För att säkerställa korrekt beräkning av rabatter i både Sales och Supply Chain Management **Metod för rabattberäkning** måste anges till **Radartikel**.
- Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:

    - Alternativet **Använd systemets prisberäkningssystem** är **Ja**.
    - Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="setup-in-supply-chain-management"></a>Konfigurera i Supply Chain Management

- Gå till **Försäljning och marknadsföring** &gt; **3periodiska uppgifter** &gt; **Beräkna försäljningssummor** och ange att jobbet ska köras som ett batchjobb. Ange alternativet **Beräkna summor för försäljningsorder** till **Ja**. Detta steg är viktigt eftersom endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales. Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.

Om du också använder integration av arbetsorder måste du ställa in försäljningsursprung. Försäljningsursprunget används för att särskilja försäljningsorder i Supply Chain Management som skapats från arbetsorder i Field Service. När försäljningsordern har sitt försäljningsursprung av typen **Integrering av arbetsorder** visas fältet **Extern arbetsorderstatus** på försäljningsorderns rubrik. Dessutom hjälper försäljningsursprunget till att garantera att försäljningsorder som har skapats från arbetsorder i Field Service filtreras bort under synkroniseringen från Supply Chain Management till Field Service.

1. Gå till **Försäljning och marknadsföring** \> **Inställningar** \> **Försäljningsorder** \> **Alla försäljningsorder**.
2. Välj **Ny** för att skapa ett nytt försäljningsursprung.
3. I fältet **Försäljningsursprung** anger du ett namn för försäljningsursprung som t.ex. **Försäljningsorder**.
4. I fältet **Beskrivning** anger du en beskrivning såsom **Försäljningsorder från försäljning**.
5. Markera kryssrutan **Tilldelning av ursprungstyp**.
6. Ange fältet **Typ av försäljningsursprung** till **Försäljningsorder av arbetsorder**.
7. Välj **Spara**.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Inställningen i försäljningsorder (Sales till Supply Chain Management) - Direkt dataintegreringsprojekt

- Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**. Du kan göra ett standardvärde tomt i värdemappningen så slipper du ange land för nationella order. Ange värdet på vänster sida till "Tom" och ange höger sida till önskat land eller region.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där "Tomt" = USA.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Inställningen i försäljningsorder (Supply Chain Management till Sales) - Direkt dataintegreringsprojekt

#### <a name="salesheader-task"></a>Aktivitet för försäljningsrubrik

- En prislista krävs för att skapa order i Sales. Uppdatera värdemappen för **pricelevelid.name \[Price List Name\]** till den prislista som används i Sales efter valuta. Du kan använda standardprislistan för en enda valuta. Om du har prislistor i flera valutor kan du använda en värdekarta.

    Standardmallvärdet för **pricelevelid.name \[Price List Name\]** är **CRM Service USA (exempel)**.

#### <a name="salesline-task"></a>Aktivitet på försäljningsrad

- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Supply Chain Management.
- Kontrollera att nödvändiga enheter definieras i Sales.

    En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Supply Chain Management till Sales eller från Supply Chain Management till Sales.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Försäljningsorder (Supply Chain Management till Sales) - direkt: OrderHeader

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Försäljningsorder (Supply Chain Management till Sales) - direkt: OrderLine

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Försäljningsorder (Sales till Supply Chain Management) - direkt: OrderHeader

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Försäljningsorder (Sales till Supply Chain Management) - direkt: OrderLine

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)
