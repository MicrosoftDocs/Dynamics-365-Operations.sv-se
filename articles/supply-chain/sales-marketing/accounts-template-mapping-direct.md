---
title: Synkronisera konton direkt från Sales till kunder i Supply Chain Management
description: Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera konton från Dynamics 365 Sales till Supply Chain Management.
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
ms.openlocfilehash: 8d415174f62c511626852b91f3591f907b4a85ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851577"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Synkronisera konton direkt från Sales till kunder i Supply Chain Management

[!include [banner](../includes/banner.md)]



> [!NOTE]
> Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Microsoft Dataverse för appar](/powerapps/administrator/data-integrator).

Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera konton direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales.  Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund-till-pengar.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [Power Apps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mall och underliggande uppgift används för att synkronisera konton från Sales till Supply Chain Management:

- **Namnet på mallen i dataintegrering:** konton (Sales till Fin and Ops) - Direkt
- **Namnet på aktiviteten i projektet:** Konton - Kunder

Inga synkroniseringsuppgifter krävs innan synkroniseringen av konto/kund kan utföras.

## <a name="entity-set"></a>Ange entiteten

| Försäljning    | Hantering av underleverantörer |
|----------|------------------------|
| Konton | Kunder V2           |

## <a name="entity-flow"></a>Flöde för entitet

Konton hanteras i Sales och synkroniseras med Supply Chain Management som kunder. Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales. Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Kolumnen **kontonummer** är tillgängligt på sidan **konto**. Det har gjorts en fysisk och en unik nyckel för att stödja integreringen. Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder kolumnen **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto. Integreringslösningen stöder för närvarande inte fallet.

När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **ACC-01000-BVRCPS**

När integreringslösningen för Sales används kommer ett uppgraderingsskript anges på kolumnen **kontonummer** för befintliga konton i Sales. Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Mappningen **CustomerGroupId** måste uppdateras till ett giltigt värde i Supply Chain Management. Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning.

    Standardmallvärdet är **10**.

- Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Supply Chain Management. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management. En standardplats kan tas antingen från produkten eller från kunden från orderrubriken.

        Standardmallvärdet är **1**.

    - **WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management. Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Supply Chain Management.

        Standardmallvärdet är **13**.

    - **LanguageId** – ett språk plats måste anges för att skapa offerter och försäljningsorder i Supply Chain Management. Som standard används språk från orderrubriken från kunden.

        Standardmallvärdet är **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Kolumnerna **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa kolumner måste du konfigurera en värdemappning som är specifik för data i organisationer som tabellen synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken kolumninformation som kommer att synkroniseras från Sales till Supply Chain Management.

![Mallmappning i dataintegrering.](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-articles"></a>Relaterade artiklar


[Potentiell kund till pengar](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Supply Chain Management](accounts-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management](contacts-template-mapping-direct.md)

[Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]