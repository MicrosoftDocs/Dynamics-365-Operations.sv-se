---
title: "Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontaktentiteter (kunder) från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 021a43c78cec83b23aff5dcc40db1a4be81aefc3
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontaktentiteter (kunder) direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att synkronisera entiteterna kontakt (kontakter) i Sales och entiteterna kontakt (kunder) i Finance and Operations:

- **Namn på mallar i dataintegrering:**

    - Kontakter (Sales till Fin and Ops) - Direkt
    - Kontakter till kund (Sales till Fin and Ops) - Direkt

- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - Kontakter
    - ContactToCustomer

Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Fin and Ops)

## <a name="entity-sets"></a>Entitetsuppsättningar

| Försäljning    | Finance and Operations |
|----------|------------------------|
| Kontakter | CDS-kontakter           |
| Kontakter | Kunder V2           |

## <a name="entity-flow"></a>Flöde för entitet

Kontakter hanteras i Sales och synkroniseras till Finance and Operations.

En kontakt i Sales kan antingen bli en kontakt eller enkund i Finance and Operations. För att ta reda på om en kontakt i Sales ska synkroniseras mot Finance and Operations som en kontakt eller en kund, tittar systemet på följande egenskaper för en kontakt i Sales:

- **Synkronisering till en kund i Finance and Operations:** kontakter där **är aktiv kund** anges till **Ja**
- **Synkronisering till en kontakt i Finance and Operations:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Ett nytt fält för **är aktiv kund** har lagts till kontakten. Det här fältet används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet. **Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor. Endast dessa kontakter synkroniseras till Finance and Operations som kunder.

Ett nytt fält för **IsCompanyAnAccount** har lagts till kontakten. Det här fältet indikerar om en kontakt är kopplad till ett företag (överordnat konto/kontakt) av typen **konto**. Denna information används för att identifiera kontakter som ska synkroniseras mot Finance and Operations som kontakter.

Ett nytt fält för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration. När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie. Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **CON-01000-BVRCPS**

När integrationslösningen för Sales används, anger ett uppgraderingsskript fältet **kontaktnummer** för befintliga kontakter med nummerserien som beskrivits tidigare. Uppgraderingsskriptet anger också fältet **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.

## <a name="in-finance-and-operations"></a>I Finance and Operations

Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**. Den här egenskapen anger att en kontakt hanteras externt. I det här fallet underhålls externt underhållna kontakter i Sales.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="contact-to-customer"></a>Kontakt till kund

- **Kundgrupp** krävs i Finance and Operations. För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen. Detta standardvärde används sedan om fältet lämnas tomt i Sales.

    Standardmallvärdet är **10**.

- Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Finance and Operations. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** - en standardplats kan också definieras på produkter i Finance and Operations. En plats måste anges för att skapa offerter och försäljningsorder i Finance and Operations.

        Ett mallvärde för **SiteId** är inte definierad.

    - **WarehouseId** - ett standardlagerställe kan också definieras på produkter i Finance and Operations. Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Finance and Operations.

        Ett mallvärde för **WarehouseId** är inte definierad.

    - **LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations.
    
        Standardmallvärdet är **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.

### <a name="contact-to-contact"></a>Kontakt till kontakt

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Kontakt till kund

![Mallmappning i dataintegreraren](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Finance and Operations](accounts-template-mapping-direct.md)

[Synkronisera produkter direkt från Finance and Operations till produkter i Sales](products-template-mapping-direct.md)

[Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales](sales-invoice-template-mapping-direct.md)



