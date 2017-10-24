---
title: "Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales"
description: "Avsnittet diskuterar de mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsfakturor mellan Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales

[!include[banner](../includes/banner.md)]

Avsnittet diskuterar de mallar och underliggande uppgifter som används för att synkronisera rubriker och rader i försäljningsfakturor mellan Microsoft Dynamics 365 for Finance and Operations, Enterprise edition och Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Mallar och uppgifter

Följande mallar och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsfakturor mellan Finance and Operations och Sales:

- **Namnet på mallen i dataintegreringen** 

     - Försäljningsfakturor (Fin and Ops till Sales)

- **Namnen på uppgifterna i dataintegreringsprojektet**

    - Rubrik på försäljningsfakturan
    - Rad i försäljningsfaktura

Synkronisera uppgifter som krävs före synkronisering av rubrik och rader i försäljningsfaktura:
-   Produkter (Fin and Ops till Sales)
-   Konton (Sales till Fin and Ops) (vid behov)
-   Kontakter (Sales till Fin and Ops) (vid behov)
-   Rubrik och rader i försäljningsfaktura (Fin and Ops till Sales)

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations                               | Common Data Service (CDS)              | Försäljning          |
|------------------------------------------------------|------------------|----------------|
| Huvuden för kundförsäljningsfakturor som underhålls externt | Försäljningsfaktura     | Fakturor       |
| Rader för kundförsäljningsfakturor som underhålls externt   | Rad i försäljningsfaktura | Fakturainformation |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsfakturor skapas i Finance and Operations och synkroniseras med Sales.

> [!NOTE]
> Skatter relaterade till **försäljningsfakturans rubrik** ingår i nuläget inte i synkroniseringen mellan Finance and Operations och Sales. Anledningen till det är att Sales inte stöder skatteinformation på rubriknivå. Skatter som berör avgifter på radnivå är inkluderade.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

-  Ett **fält för fakturanummer** läggs till i entiteten **Faktura** och visas på sidan.
 
-  Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales. Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Finance and Operations.
 
-  **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Finance and Operations har synkroniserats med Sales. Ägaren till den försäljningsorder som fakturan skapades ur görs dessutom till fakturaägare. Detta ger försäljningsfakturans ägare möjlighet att granska fakturan.
 
## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar försäljningsfakturor är det viktigt att du uppdaterar systemen med följande inställning:

### <a name="setup-in-sales"></a>Inställningar i Sales

- Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Använd systemets prisberäkningssystem** är inställd på **Ja**. 

- Under **Inställningar** > **Administration** > **Systeminställningar** > **Sales**, kontrollera att inställningen **Metod för rabattberäkning** är inställd på **Radobjekt**. 

### <a name="setup-in-the-data-integration-project"></a>Inställningar i dataintegreringsprojektet

#### <a name="salesinvoiceheader-task"></a>Rubrikuppgift på försäljningsfakturan

- Uppdatera mappningen för **ID för CDS-organisation** under **Källa** > **CDS**. 

    -  Värdet för standardmall för **Försäljningsorder_Organisation_Organisations-Id** är ORG001.
    -  Värdet för standardmall för **Konto_Organisation_Organisations-Id** är ORG001.
    -  Värdet för standardmall för **Organisation_Organisations-Id** är ORG001.

- Se till att erforderlig mappning finns under **Källa** > **CDS för FakturaLandRegions-Id** till **Faktureringsadress_Land**.

    -  Mallvärdet är **ValueMap**, med ett antal länder mappade.

- **Prislista** krävs för att skapa fakturor i Sales. Uppdatera **ValueMap** i **CDS** > **Destination för pricelevelid.name [namn på prislista]** till den **prislista** som används i Sales efter valuta. Du kan välja mellan att använda den förvalda **Prislistan** för en enstaka valuta eller att använda **ValueMap** om du har **prislistor** i flera olika valutor.

    -  Mallvärdet för **pricelevelid.name [prislistans namn]** är **ValueMap** baserad på **Valuta**.
    -  usd: CRM Service USA (exempel). 

#### <a name="salesinvoiceline-task"></a>Raduppgift i försäljningsfaktura

- Se till att erforderlig mappning finns under **Källa** > **CDS för måttenhet**.

- Se till att erforderlig **ValueMap** för **Säljenhetssymbol** i Finance and Operations finns under **Källa** > **CDS-mappning**. 
    
    - Mallvärde med **ValueMap** har definierats för **Säljenhetssymbol till kvantitet_UOM**.
    
-  Uppdatera mappningen för **ID för CD-organisation i källa** > **CDS**. 

    -  Värdet för standardmall för **Försäljningsfaktura_Organisation_Organisations-Id** är ORG001.
    -  Värdet för standardmall för **Produkt_Organisation_Organisations-Id** är ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegreraren

> [!NOTE]
> **Betalningsvillkor**, **Fraktvillkor**, **Leveransvillkor**, **Leveransmetod** och **Leveranssätt** ingår inte i standardmappningen. Mappning av dessa fält kräver att värdemappning konfigureras som är specifik för datan i de organisationer mellan vilka entiteten synkroniseras.

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera produkter från Finance and Operations till produkter i Sales](products-template-mapping.md)

[Synkronisera konton från Sales till kunder i Finance and Operations](accounts-template-mapping.md)

[Synkronisera kontakter från Sales till kontakter i Finance and Operations](contacts-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations](sales-quotation-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales](sales-order-template-mapping.md)


