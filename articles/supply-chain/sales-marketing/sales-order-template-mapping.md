---
title: "Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsorder från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Mall och uppgifter

Följande mallar och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsorder från Finance and Operations till Sales:

- **Namnet på mallen i dataintegrering** 

    - Försäljningsorder (Fin and Ops till Sales)
    
- **Namn på aktiviteter i dataintegreringsprojekt**

    - Orderrubrik
    - Orderrad

Synkroniseringsuppgifter som krävs före säljfakturahuvud och radsynkronisering:

- Produkter (Fin and Ops till Sales)
- Konton (Sales till Fin and Ops) (vid behov)
- Kontakter till kunder (Sales till Fin and Ops) (vid behov)

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations |    Common Data Service (CDS)         |     Försäljning      |
|------------------------|----------------|----------------|
| CDS-försäljningsorderrubriker| SalesOrder     | Försäljningsorder |
| CDS-försäljningsorderrader  | Försäljningsorderrad | Försäljningsorderinformation|

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsorder skapas i Finance and Operations och synkroniseras till Sales.

Filter i mallen ser till att endast relevanta försäljningsorder inkluderas i synkroniseringen:

- Både beställande och fakturerande kund på försäljningsordern som härstammar från försäljningen inkluderas i synkroniseringen. Fälten **Beställande kund hanteras externt** och **Fakturakund hanteras externt** används för att spåra synkroniseringen i dataenheterna.

- **Försäljningsordern** i Finance and Operations måste bekräftas. Endast bekräftade försäljningsorder eller försäljningsorder med högre bearbetningsstatus, exempelvis statusen Levererad eller Fakturerad, synkroniseras till Sales.

- När du skapar eller ändrar en försäljningsorder måste batch-jobbet **Beräkna försäljningstotalen** i Finance and Operations köras. Endast försäljningsorder med beräknade försäljningstotaler synkroniseras med CDS och Sales.

> [!NOTE]
> Moms relaterat till avgifter i **Försäljningsorderrubriken** ingår i nuläget inte i synkroniseringen från Finance and Operations till Sales. Anledningen till det är att Sales inte stöder skatteinformation på rubriknivå. Skatter som berör avgifter på radnivå är inkluderade.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Nya fält läggs till i enheten **Order** och visas på sidan:

- **Hanteras externt** - Värdet anges som **Ja** när ordern kommer från Finance and Operations.

- **Bearbetningsstatus** - Används för att visa bearbetningsstatusen för ordern i Finance and Operations. Värdena är:

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

Inställningen **Har endast externt hanterade produkter** används i andra scenarier för försäljningsorder (synkronisering från Sales till Finance and Operation) i syfte att konstant hålla reda på huruvida försäljningsordern enbart består av **Externt hanterade Produkter** - i detta fall hanteras produkterna i Finance and Operations. Detta säkerställer att du inte försöker synkronisera försäljningsorderraderna med produkter som är okända för Finance and Operations.
 
Knapparna **Skapa faktura**, **Annullera order**, **Beräkna om**, **Hämta produkter** och **Slå upp adress** på sidan **Försäljningsorder** döljs för externt hanterade order eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales. Ordersidan kan inte registreras eftersom försäljningsorderinformationen synkroniseras från Finance and Operations.
 
**Status för försäljningsorder** förblir aktiv för att se till att ändringar från Finance and Operations når **Försäljningsordern** i Sales. Detta styrs genom att ange standard **Statuskod [Status]** som **Aktiv** i dataintegreringsprojektetet.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar 

Innan du synkroniserar försäljningsorder är det viktigt att du uppdaterar systemen med följande inställning:

### <a name="setup-in-sales"></a>Inställning i Sales

- Kontrollera behörigheterna för teamet som användaren (från **Anslutning skapad** i Sales) har tilldelats. Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte teamet. Utan detta visas ett felmeddelande som det primära teamet saknar när projektet körs från dataintegreraren. 

    - Under **Inställningar** > **Säkerhet** > **Team**väljer du relevant team, klickar på **Hantera roller** och väljer en roll med önskade behörigheter, t.ex. systemadministratör.

- Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Använd systemets prisberäkningssystem** är inställd på **Ja**. 

- Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Metod för rabattberäkning** är inställd på **Radobjekt**. 

### <a name="setup-in-finance-and-operations"></a>Inställningar i Finance and Operations

Ange att **Försäljning och marknadsföring** > **Periodiska uppgifter** > **Beräkna försäljningstotaler** ska köras som ett batch-jobb, med **Beräkna totaler för försäljningsorder** inställt på **Ja**. Detta är viktigt endast försäljningsorder med beräknade försäljningstotaler synkroniseras med CDS och Sales. Batch-jobbets frekvens ska vara densamma som frekvensen för synkroniseringen av försäljningsordern.

### <a name="setup-in-the-data-integration-project"></a>Inställningar i dataintegreringsprojektet

#### <a name="salesheader-task"></a>Aktivitet för försäljningsrubrik

- Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**.

    - Värdet för standardmall för **Konto_Organisation_Organisations-Id** är ORG001.
    - Standardvärdet för **Fakturakonto_Organisation_Organisation-ID** är ORG001.
    - Värdet för standardmall för **Organisation_Organisations-Id** är ORG001.

- Kontrollera att nödvändig mappning finns i **Källa** > **CDS för FakturaLandRegions-ID till Faktureringsadress_Land** och **LeveransLandRegions-ID till LeveransAdress_Land**.

    - Mallvärdet är **ValueMap**, med ett antal länder mappade.

- **Prislista** krävs för att skapa order i Sales. Uppdatera **ValueMap** i **CDS** > **Destination** för **pricelevelid.name [prislistans namn]** till den **Prislista** som används i Sales efter valuta. Du kan antingen använda förvald **Prislista** för gemensam valuta eller använda **ValueMap** om du har **Prislistor** i flera olika valutor.
    
    - Standardvärdet för **pricelevelid.name [prislistans namn]** är CRM-tjänsten i USA (prov). 

#### <a name="salesline-task"></a>Aktivitet på försäljningsrad

- Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**. 
    
    - Värdet för standardmall för **Försäljningsorder_Organisation_Organisations-Id** är ORG001.
    - Värdet för standardmall för **Produkt_Organisation_Organisations-Id** är ORG001.

- Kontrollera att nödvändig mappning finns i **Källa** > **CDS** för **LeveransLandRegion-ID** till **LeveransAdress_Land**.

    - Mallvärdet är **ValueMap**, med ett antal länder mappade.
    
- Se till att erforderlig **ValueMap** för **Säljenhetssymbol** i Finance and Operations finns under **Källa** > **CDS-mappning**.

    - Mallvärde med **ValueMap** har definierats för **Säljenhetssymbol till kvantitet_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

### <a name="orderheader"></a>Orderrubrik

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>Orderrad

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera produkter från Finance and Operations till produkter i Sales](products-template-mapping.md)

[Synkronisera konton från Sales till kunder i Finance and Operations](accounts-template-mapping.md)

[Synkronisera kontakter från Sales till kontakter i Finance and Operations](contacts-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations](sales-quotation-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales](sales-invoice-template-mapping.md)


