---
title: Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsfakturahuvud och rader direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d7f104b3f2e132b5b517443577a020fda7fa9af3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975020"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales

[!include [banner](../includes/banner.md)]

I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsfakturahuvud och rader direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [Power Apps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader i försäljningsfakturor direkt i försäljningsofferter från Supply Chain Management till Sales:

- **Namnet på mallen i dataintegrering:** försäljningsfaktura (Fin and Ops till Sales) - Direkt
- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - Rubrik på försäljningsfakturan
    - Rad i försäljningsfaktura

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:

- Produkter (Supply Chain Management till Sales) - direkt
- Konton (Sales till Supply Chain Management)-direkt (om den används)
- Kontakter (Sales till Supply Chain Management)-direkt (om den används)
- Rubrik och rader i försäljningsfaktura (Supply Chain Management till Sales) - Direkt

## <a name="entity-set"></a>Ange entiteten

| Hantering av underleverantörer                              | Försäljning          |
|------------------------------------------------------|----------------|
| Huvuden för kundförsäljningsfakturor som underhålls externt | Fakturor       |
| Rader för kundförsäljningsfakturor som underhålls externt   | Fakturainformation |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsfakturor skapas i Supply Chain Management och synkroniseras med Sales.

> [!NOTE]
> För närvarande ingår moms relaterad till avgifter i försäljningsfakturarubriken inte i synkroniseringen från Supply Chain Management till Sales. Sales stöder itne skatteinformation på rubriknivå. Moms som är relaterad till tillägg på radnivå ingår emellertid i synkroniseringen.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

- Ett fält för **fakturanummer** har lagts till i entiteten **Faktura** och visas på sidan.
- Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Supply Chain Management och synkroniseras med Sales. Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Supply Chain Management.
- Värdet **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Supply Chain Management har synkroniserats med Sales. Dessutom kan ägaren till den försäljningsorder som fakturan skapades från tilldelas till fakturaägaren. Därför kan ägaren till försäljningsordern kan visa fakturan.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar försäljningsfakturor är det viktigt att du uppdaterar följande inställningar i systemen.

### <a name="setup-in-sales"></a>Inställningar i Sales

Gå till **inställningar** > **Administration** > **systeminställningar** > **Sales** och säkerställ att följande inställningar används:

- Alternativet **Använd systemets prisberäkningssystem** är **Ja**.
- Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="setup-in-the-data-integration-project"></a>Inställningar i dataintegreringsprojektet

#### <a name="salesinvoiceheader-task"></a>Rubrikuppgift på försäljningsfakturan

- Kontrollera att nödvändig mappning finns i **InvoiceCountryRegionId** till **BillingAddress\_Country**.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas.

- En prislista krävs för att skapa fakturor i Sales. Uppdatera värdemappen för **pricelevelid.name \[Price list name\]** till den prislista som används i Sales efter valuta. Du kan använda standardprislistan för en enda valuta. Om du har prislistor i flera valutor kan du använda en värdekarta.

    Mallvärdet för **pricelevelid.name \[prislistans namn\]** är en värdemappning som baseras på valuta med USD = CRM Service USA (exempel).  
    
#### <a name="salesinvoiceline-task"></a>Raduppgift i försäljningsfaktura

- Kontrollera att nödvändig mappning finns i **Måttenhet**.
- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Supply Chain Management.

    En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **Antal\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Supply Chain Management.

### <a name="salesinvoiceheader"></a>Rubrik på försäljningsfakturan

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>Rad i försäljningsfaktura

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Relaterade ämnen

[Prospekt till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Supply Chain Management](accounts-template-mapping-direct.md)

[Synkronisera produkter direkt från Supply Chain Management till produkter i Sales](products-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management](contacts-template-mapping-direct.md)

[Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]