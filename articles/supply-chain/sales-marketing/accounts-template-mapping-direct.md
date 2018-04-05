---
title: "Synkronisera konton direkt från Sales till kunder i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations."
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: fb694db32638756328623c186594cf5ba2e7d6b8
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Synkronisera konton direkt från Sales till kunder i Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration).

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton direkt från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales.  Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://preview.admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mallar och underliggande uppgifter används för att synkronisera konton från Sales till Finance and Operations:

- **Namnet på mallen i dataintegrering:** konton (Sales till Fin and Ops) - Direkt
- **Namnet på aktiviteten i projektet:** Konton - Kunder

Inga synkroniseringsuppgifter krävs innan synkroniseringen av konto/kund kan utföras.

## <a name="entity-set"></a>Ange entiteten

| Försäljning    | Finance and Operations |
|----------|------------------------|
| Konton | Kunder V2           |

## <a name="entity-flow"></a>Flöde för entitet

Konton hanteras i Sales och synkroniseras till Finance and Operations som kunder. Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales. Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Fältet **kontonummer** är tillgängligt på sidan **konto**. Det har gjorts en fysisk och en unik nyckel för att stödja integreringen. Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder fältet **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto. Integrationslösningen stöder för närvarande inte fallet.

När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **ACC-01000-BVRCPS**

När integrationslösningen för Sales används kommer ett uppgraderingsskript angs på fältet **kontonummer** för befintliga konton i Sales. Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Mappningen **CustomerGroupId** måste uppdateras till ett giltigt värde i Finance and Operations. Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning.

    Standardmallvärdet är **10**.

- Genom att lägga till följande mappningar kan du minska antalet manuella uppdateringar som krävs för Finance and Operations. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. En standardplats kan tas antingen från produkten eller från kunden från orderrubriken.

        Standardmallvärdet är **1**.

    - **WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Finance and Operations.

        Standardmallvärdet är **13**.

    - **LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations. Som standard används språk från orderrubriken från kunden.

        Standardmallvärdet är **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.

![Mallmappning i dataintegrering](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Relaterade ämnen


[Potentiell kund till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Finance and Operations](accounts-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations](contacts-template-mapping-direct.md)

[Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales](sales-invoice-template-mapping-direct.md)


