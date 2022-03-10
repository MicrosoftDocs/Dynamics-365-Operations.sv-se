---
title: Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera entiteterna Kontakt (kontakter) och Kontakt (kunder) direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 57a9c2a860e99855e841f0f4276ba2f92767c2b1
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062525"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management

[!include [banner](../includes/banner.md)]



> [!NOTE]
> Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](/powerapps/administrator/data-integrator).

I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera tabellerna Kontakt (kontakter) och Kontakt (kunder) direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund-till-pengar.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att synkronisera tabellerna kontakt (kontakter) i Sales och tabellerna kontakt (kunder) i Supply Chain Management.

- **Namn på mallar i dataintegrering**

    - Kontakter (Sales till Supply Chain Management) - direkt
    - Kontakter till kunder (Sales till Supply Chain Management) - direkt

- **Namnen på uppgifterna i dataintegreringsprojektet**

    - Kontakter
    - ContactToCustomer

Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Supply Chain Management)

## <a name="entity-sets"></a>Entitetsuppsättningar

| Försäljning    | Hantering av underleverantörer |
|----------|------------------------|
| Kontakter | Dataverse-kontakter           |
| Kontakter | Kunder V2           |

## <a name="entity-flow"></a>Flöde för entitet

Kontakter hanteras i Sales och synkroniseras med Supply Chain Management.

En kontakt i Sales kan antingen bli en kontakt eller en kund i Supply Chain Management. För att ta reda på om en kontakt i Sales ska synkroniseras mot Supply Chain Management som en kontakt eller en kund, tittar systemet på följande egenskaper för en kontakt i Sales:

- **Synkronisering till en kund i Supply Chain Management:** kontakter där **är aktiv kund** anges till **Ja**
- **Synkronisering till en kontakt i Supply Chain Management:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

En ny kolumn för **är aktiv kund** har lagts till kontakten. Den här kolumnen används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet. **Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor. Endast dessa kontakter synkroniseras till Supply Chain Management som kunder.

En ny kolumn för **IsCompanyAnAccount** har lagts till kontakten. Den här kolumnen indikerar om en kontakt är kopplad till ett företag (överordnat konto/kontakt) av typen **konto**. Denna information används för att identifiera kontakter som ska synkroniseras mot Supply Chain Management som kontakter.

En ny kolumn för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration. När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie. Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **CON-01000-BVRCPS**

När integrationslösningen för Sales används, anger ett uppgraderingsskript kolumnen **kontaktnummer** för befintliga kontakter med nummerserien som beskrivits tidigare. Uppgraderingsskriptet anger också kolumnen **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.

## <a name="in-supply-chain-management"></a>I Supply Chain Management

Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**. Den här egenskapen anger att en kontakt hanteras externt. I det här fallet underhålls externt underhållna kontakter i Sales.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="contact-to-customer"></a>Kontakt till kund

- **CustomerGroup** krävs i Supply Chain Management. För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen. Detta standardvärde används sedan om kolumnen lämnas tomt i Sales.

    Standardmallvärdet är **10**.

- Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Supply Chain Management. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** - en standardplats kan också definieras på produkter i Supply Chain Management. En plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.

        Ett mallvärde för **SiteId** är inte definierad.

    - **WarehouseId** - ett standardlagerställe kan också definieras på produkter i Supply Chain Management. Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.

        Ett mallvärde för **WarehouseId** är inte definierad.

    - **LanguageId** – ett språk plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management.
    
        Standardmallvärdet är **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken kolumninformation som kommer att synkroniseras från Sales till Supply Chain Management.

### <a name="contact-to-contact-example"></a>Exempel på kontakt till kontakt

![Mallmappning för kontakt till kontakt i dataintegratör.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer-example"></a>Exempel på kontakt till kund

![Mallmappning för kontakt till kund i dataintegratör.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till pengar](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Supply Chain Management](accounts-template-mapping-direct.md)

[Synkronisera produkter direkt från Supply Chain Management till produkter i Sales](products-template-mapping-direct.md)

[Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]