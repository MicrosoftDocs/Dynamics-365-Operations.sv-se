---
title: "Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mall och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsorder från Finance and Operations till Sales:

- **Namnet på mallen i dataintegrering:** försäljningsorder (Fin and Ops till Sales) - Direkt
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

Försäljningsorder skapas i Finance and Operations och synkroniseras till Sales.

Filter i mallen ser till att endast relevanta försäljningsorder inkluderas i synkroniseringen:

- På försäljningsordern härstammar både beställande kund och fakturerande kund från Sales inkluderas i synkroniseringen. Fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** används för att spåra synkroniseringen i dataenheterna.
- Försäljningsordern i Finance and Operations måste bekräftas. Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis **Levererad** eller **Fakturerad** synkroniseras till Sales.
- När en försäljningsorder skapas eller ändras måste batch-jobbet **Beräkna försäljningstotalen** i Finance and Operations köras. Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales.

> [!NOTE]
> För närvarande ingår moms relaterad till avgifter i försäljningsorderrubriken inte i synkroniseringen från Finance and Operations till Sales. Sales stöder itne skatteinformation på rubriknivå. Moms som är relaterad till tillägg på radnivå ingår emellertid i synkroniseringen.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Nya fält har lagst till i enheten **Order** och visas på sidan:

- **Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Finance and Operations.
- **Bearbetningsstatus** - Detta fält visar bearbetningsstatusen för ordern i Finance and Operations. Följande värden finns:

    - Aktiva
    - Bekräftat
    - Följesedel
    - Fakturerat
    - Plockat
    - Delvis plockad
    - Delvis förpackad
    - Skeppat
    - Delvis levererad
    - Delvis fakturerad
    - Avbröts

Inställningen **Har endast externt hanterade produkter** används i andra scenarier för försäljningsorder (t.ex. synkronisering från Sales till Finance and Operation) i syfte att konstant hålla reda på om en försäljningsordern helt består av externt underhållna produkter. Om en försäljningsorder helt består av externt underhållna produkter, underhålls produkter i Finance and Operations. Denna inställning hjälper till att garantera att du inte försöker synkronisera försäljningsorderraderna som har produkter som är okända för Finance and Operations.

Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales. Ordersidan kan inte redigeras eftersom försäljningsorderinformationen synkroniseras från Finance and Operations.

Status för försäljningsorder förblir **aktiv** för att se till att ändringar från Finance and Operations når Försäljningsordern i Sales. För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv** i dataintegreringsprojektetet.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar följande inställningar i systemen.

### <a name="setup-in-sales"></a>Inställningar i Sales

- Se till att behörigheterna ställs in för teamet som användaren från din Sales-anslutning har tilldelats. Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst. Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.

    Gå till **Inställningar** > **Säkerhet** > **Team**, väljer du relevant team, klickar på **Hantera roller** och väljer en roll med önskade behörigheter, t.ex. **systemadministratör**.

- Gå till **inställningar** > **Administration** > **systeminställningar** > **Sales** och säkerställ att följande inställningar används:

    - Alternativet **Använd systemets prisberäkningssystem** är **Ja**.
    - Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="setup-in-finance-and-operations"></a>Inställningar i Finance and Operations

Gå till **försäljning och maarknadsföring** > **periodiska uppgifter** > **Beräkna försäljningssummor** och ange att jobbet ska köras som ett batchjobb. Ange alternativet **Beräkna summor för försäljningsorder** till **Ja**. Detta steg är viktigt eftersom endast försäljningsorder med beräknade försäljningstotaler synkroniseras med Sales. Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.

### <a name="setup-in-the-data-integration-project"></a>Inställningar i dataintegreringsprojektet

#### <a name="salesheader-task"></a>Aktivitet för försäljningsrubrik

- Kontrollera att nödvändig mappning finns för **InvoiceCountryRegionId** till **BillingAddress\_Country** och för **DeliveryCountryRegionId** till **DeliveryAddress\_Country**.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas.

- En prislista krävs för att skapa order i Sales. Uppdatera värdemappen för **pricelevelid.name \[Price list name\]** till den prislista som används i Sales efter valuta. Du kan använda standardprislistan för en enda valuta. Om du har prislistor i flera valutor kan du använda en värdekarta.

    Standardmallvärdet för **pricelevelid.name \[Prislistenamn\]** är **CRM Service USA (exempel)**.

#### <a name="salesline-task"></a>Aktivitet på försäljningsrad

- Kontrollera att nödvändig mappning finns i **DeliveryCountryRegionId** till **DeliveryAddress\_Country**.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas.

- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.

    En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **Antal\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.

### <a name="orderheader"></a>Orderrubrik

![Mallmappning i dataintegreraren](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>Orderrad

![Mallmappning i dataintegreraren](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Finance and Operations](accounts-template-mapping-direct.md)

[Synkronisera produkter direkt från Finance and Operations till produkter i Sales](products-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations](contacts-template-mapping-direct.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales](sales-invoice-template-mapping-direct.md)




