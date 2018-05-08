---
title: "Synkronisering av försäljningsorder direkt mellan Sales och Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att direktsynkronisera försäljningsorder mellan Microsoft Dynamics 365 for Sales och Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e26244ffc380291a40edfbd2c2cb5911b0d8b3cb
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="synchronization-of-sales-orders-directly-between-sales-and-finance-and-operations"></a>Synkronisering av försäljningsorder direkt mellan Sales och Finance and Operations

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att direktsynkronisera försäljningsorder mellan Microsoft Dynamics 365 for Sales och Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att direktsynkronisera försäljningsorder mellan Sales och Finance and Operations:

- **Namn på mallar i dataintegrering:** 

    - Försäljningsorder  (Sales till Fin and Ops) - Direkt
    - Försäljningsorder  (Fin and Ops till Sales) - Direkt

- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - Orderrubrik
    - Orderrad

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:

- Produkter (Fin and Ops till Sales) - Direkt
- Konton (Sales till Fin and Ops) - Direkt (vid behov)
- Kontakter till kunder (Sales till Fin and Ops) - Direkt (vid behov)

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations  | Försäljning             |
|-------------------------|-------------------|
| CDS-försäljningsorderrubriker | Försäljningsorder       |
| CDS-försäljningsorderrader   | Försäljningsorderinformation |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsorder skapas i Sales och synkroniseras till Finance and Operations **Kör projekt** initieras för ett projekt baserat på mallen **Försäljningsorder (Sales till Fin och Ops) - direkt** mall. Du kan bara aktivera och synkronisera om alla order från Sales om alla **Orderprodukter** består av produkter som underhålls externt. Det kan därför inte finnas någon produkt ej i register. När ordern har aktiverats blir försäljningsorder skrivskyddade i användargränssnittet (UI). Då görs uppdateringar från Finance and Operations. När försäljningsordern har statusen **bekräftad**, kan ett projekt som baseras på **försäljningsorder (Fin and Ops till Sales) - direkt** använda mallen för att synkronisera uppdateringar eller slutförandestatus från Finance and Operations till Sales.

Du behöver inte skapa order i Sales. Du kan skapa nya försäljningsorder i Finance and Operations i stället. När en försäljningsorder har statusen **bekräftad**, synkroniseras den till Sales som beskrivs ovan.

I Finance and Operations hjälper filter i mallen till att endast relevanta försäljningsorder inkluderas i synkroniseringen:

- På försäljningsordern härstammar både beställande kund och fakturerande kund från Sales inkluderas i synkroniseringen. Fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** används för att filtrera försäljningsorder från dataenheterna.
- Försäljningsordern i Finance and Operations måste bekräftas. Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis **Levererad** eller **Fakturerad** synkroniseras till Sales.
- När en försäljningsorder skapas eller ändras måste batch-jobbet **Beräkna försäljningstotalen** i Finance and Operations köras. Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales.

## <a name="freight-tax"></a>Moms för frakt

Sales stöder inte moms på huvudnivå eftersom moms lagras på radnivå. För att stödja moms på huvudnivå från Finance and Operations, som t.ex moms på frakt, synkroniserar systemet moms på Sales som en produkt ej i register som heter **fraktmoms** och som har momsbeloppet från Finance and Operations. På så sätt kan standardprisberäkningen i Sales användas för summor, även när det är moms på huvudnivå från Finance and Operations.

## <a name="discount-calculation-and-rounding"></a>Rabattberäkning och avrundning.

Rabattberäkningsmodellen i Sales avviker från rabattberäkningsmodell i Finance and Operations. I Finance and Operations kan det slutgiltiga rabattbeloppet på en försäljningsrad vara resultatet av en kombination av rabattbelopp och rabattsatser. Om detta slutliga rabattbelopp divideras med antalet på raden, kan avrundning uppstå. Den här typen av avrundning inkluderas inte om ett avrundat rabattbelopp per enhet synkroniseras till Sales. För att garantera att det fullständiga rabattbeloppet från en försäljningsrad i Finance and Operations synkroniseras korrekt till Sales, måste hela beloppet synkroniseras utan att divideras med radkvantiteten. Därför måste du definiera **rabattberäkningsmetod** som **radartikel** i Sales.

När en försäljningsorderrad synkroniseras från Sales till Finance and Operations används fullständig radrabatt. Eftersom Finance and Operations inte har några fält som kan innehålla fullständiga rabattbeloppet för en rad, divideras beloppet med kvantiteten och lagras i fältet **radrabatt**. All avrundning som uppstår i denna division lagras i fältet **försäljningstillägg** på försäljningsraden.

### <a name="example"></a>Exempel

**Synkronisering från Sales till Finance and Operations**

- **Sales:** kvantitet = 3 per radrabatt = $10,00
- **Finance and Operations:** kvantitet = 3 radrabatt = $3,33 Försäljningskostnad =-$0,01 

**Synkronisering från Sales till Finance and Operations till Sales**

- **Finance and Operations:** kvantitet = 3 radrabatt = $3,33 Försäljningskostnad =-$0,01
- **Sales:** kvantitet = 3 per radrabatt = (3 × $3,33) + $0,01 = $10,00

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Nya fält har lagst till i enheten **Order** och visas på sidan:

- **Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Finance and Operations.
- **Bearbetningsstatus** - Detta fält visar bearbetningsstatusen för ordern i Finance and Operations. Följande värden finns:

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

Inställningen **Har endast externt hanterade produkter** används under orderaktivering för att konstant spåra om en försäljningsorder består av externt underhållna produkter. Om en försäljningsorder helt består av externt underhållna produkter, underhålls produkter i Finance and Operations. Denna inställning hjälper till att garantera att du inte aktiverar och försöker synkronisera försäljningsorderraderna som har produkter som är okända för Finance and Operations.

Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales. Dessa order kan inte redigeras eftersom försäljningsorderinformationen synkroniseras från Finance and Operations efter aktivering.

Status för försäljningsorder förblir **aktiv** för att se till att ändringar från Finance and Operations når Försäljningsordern i Sales. För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv** i dataintegreringsprojektetet.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar följande inställningar i systemen.

### <a name="setup-in-sales"></a>Inställningar i Sales

- Se till att behörigheterna ställs in för teamet som användaren från din Sales-anslutning har tilldelats. Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst. Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.

    Gå till **Inställningar** &gt; **Säkerhet** &gt; **Team**, välj relevant team, klicka på **Hantera rolelr** och välj en roll med önskade behörigheter, t.ex. **systemadministratör**.

- För att säkerställa korrekt beräkning av rabatter i både Sales och Finance and Operations **Metod för rabattberäkning** måste anges till **Radartikel**.
- Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:

    - Alternativet **Använd systemets prisberäkningssystem** är **Ja**.
    - Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="setup-in-finance-and-operations"></a>Inställningar i Finance and Operations

- Gå till **Försäljning och marknadsföring** &gt; **3periodiska uppgifter** &gt; **Beräkna försäljningssummor** och ange att jobbet ska köras som ett batchjobb. Ange alternativet **Beräkna summor för försäljningsorder** till **Ja**. Detta steg är viktigt eftersom endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales. Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.

### <a name="setup-in-the-sales-orders-sales-to-fin-and-ops---direct-data-integration-project"></a>Inställningen i försäljningsorder (Sales till Fin and Ops) - Direkt dataintegreringsprojekt

- Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**. Du kan göra ett standardvärde tomt i värdemappningen så slipper du ange land för nationella order. Ange värdet på vänster sida till "Tom" och ange höger sida till önskat land eller region.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där "Tomt" = USA.

### <a name="setup-in-the-sales-orders-fin-and-ops-to-sales---direct-data-integration-project"></a>Inställningen i försäljningsorder (Fin and Ops till Sales) - Direkt dataintegreringsprojekt

#### <a name="salesheader-task"></a>Aktivitet för försäljningsrubrik

- En prislista krävs för att skapa order i Sales. Uppdatera värdemappen för **pricelevelid.name \[Price List Name\]** till den prislista som används i Sales efter valuta. Du kan använda standardprislistan för en enda valuta. Om du har prislistor i flera valutor kan du använda en värdekarta.

    Standardmallvärdet för **pricelevelid.name \[Price List Name\]** är **CRM Service USA (exempel)**.

#### <a name="salesline-task"></a>Aktivitet på försäljningsrad

- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.
- Kontrollera att nödvändiga enheter definieras i Sales.

    En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering.

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations eller från Finance and Operations till Sales.

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderheader"></a>Försäljningsorder (Fin and Ops till Sales) - Direkt: Orderrubrik

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderline"></a>Försäljningsorder (Fin and Ops till Sales) - Direkt: Orderrad

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderheader"></a>Försäljningsorder (Sales till Fin and Ops) - Direkt: Orderrubrik

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderline"></a>Försäljningsorder (Sales till Fin and Ops) - Direkt: Orderrad

[![Mallmappning i dataintegrering](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

