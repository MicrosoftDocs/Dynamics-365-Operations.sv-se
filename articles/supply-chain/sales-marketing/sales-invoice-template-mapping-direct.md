---
title: "Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera försäljningsfakturahuvuden och rader direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: e9d7e756c56932372ed931620016973c794fb3fc
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera försäljningsfakturahuvuden och rader direkt från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mall och underliggande uppgifter används för att synkronisera rubriker och rader i försäljningsfakturor mellan Finance and Operations och Sales:

- **Namnet på mallen i dataintegrering:** försäljningsfaktura (Fin and Ops till Sales) - Direkt
- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - Rubrik på försäljningsfakturan
    - Rad i försäljningsfaktura

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsfakturor kan uppstå:

- Produkter (Fin and Ops till Sales) - Direkt
- Konton (Sales till Fin and Ops) - Direkt (vid behov)
- Kontakter (Sales till Fin and Ops) - Direkt (vid behov)
- Rubrik och rader i försäljningsfaktura (Fin and Ops till Sales) - Direkt

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations                               | Försäljning          |
|------------------------------------------------------|----------------|
| Huvuden för kundförsäljningsfakturor som underhålls externt | Fakturor       |
| Rader för kundförsäljningsfakturor som underhålls externt   | Fakturainformation |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsfakturor skapas i Finance and Operations och synkroniseras med Sales.

> [!NOTE]
> För närvarande ingår moms relaterad till avgifter i försäljningsfakturarubriken inte i synkroniseringen från Finance and Operations till Sales. Sales stöder itne skatteinformation på rubriknivå. Moms som är relaterad till tillägg på radnivå ingår emellertid i synkroniseringen.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

- Ett fält för **fakturanummer** har lagts till i entiteten **Faktura** och visas på sidan.
- Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Finance and Operations och synkroniseras med Sales. Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Finance and Operations.
- Värdet **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Finance and Operations har synkroniserats med Sales. Dessutom kan ägaren till den försäljningsorder som fakturan skapades från tilldelas till fakturaägaren. Därför kan ägaren till försäljningsordern kan visa fakturan.

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
- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Finance and Operations.

    En värdemall som har en värdemappning definieras för **SalesUnitSymbol** till **Antal\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.

### <a name="salesinvoiceheader"></a>Rubrik på försäljningsfakturan

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>Rad i försäljningsfaktura

![Mallmappning i dataintegrering](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Finance and Operations](accounts-template-mapping-direct.md)

[Synkronisera produkter direkt från Finance and Operations till produkter i Sales](products-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations](contacts-template-mapping-direct.md)

[Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales](sales-order-template-mapping-direct.md)







