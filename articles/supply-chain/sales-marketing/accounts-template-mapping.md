---
title: "Synkronisera konton från Sales till kunder i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: f322c5b273c29d863c059092bf1a41c424c19a7d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Synkronisera konton från Sales till kunder i Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration). 

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera konton från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).

## <a name="template-and-task"></a>Mall och uppgift

Följande mallar och underliggande uppgifter används för att synkronisera konton från Sales till Finance and Operations:

- **Mallens namn:** Konton (Sales till Fin and Ops)
- **Namnet på aktiviteten i projektet:** - Konton - Konto - Kunder

Synkronisering av uppgifter krävs innan synkronisering av konto/kund: ingen

## <a name="entity-set"></a>Ange entiteten

| Försäljning    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Konton | Konto | Kunder              |

## <a name="entity-flow"></a>Flöde för entitet

Konton hanteras i Sales och synkroniseras till Finance and Operations som kunder. Egenskapen **hanteras externt** på dessa kunder anges till **Ja** för att spåra kunder som kommer från Sales. Den här informationen används vid fakturering för att filtrera fakturor som ska synkroniseras med Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Fältet **kontonummer** är tillgängligt på sidan **konto**. Det har gjorts en fysisk och en unik nyckel stödja integreringen. Fysiska nyckeln i CRM-lösningen (Customer Relationship Management) kan påverka kunder som redan använder fältet **kontonummer** men som inte använder unika **kontonummer**-värden för varje konto. Integrationslösningen stöder för närvarande inte fallet.

När ett nytt konto skapas om ett **kontonummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **ACC** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **ACC-01000-BVRCPS**

När integrationslösningen för Sales används kommer ett uppgraderingsskript angs på fältet **kontonummer** för befintliga konton i Sales. Om det inte finns några **kontonummer**-värden kommer nummerserien som beskrivits ovan att användas.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- **CustomerGroupId**-mappning från **CDS &gt; Destination** måste uppdateras till ett giltigt värde i Finance and Operations. Du kan ange ett standardvärde eller du kan ange värdet genom att använda en värdemappning. Standardmallvärdet är **10**.
- Fältet **adress landskod** krävs i Finance and Operations. För att undvika problem med synkronisering kan du ange ett standardvärde i mappningen från **CDS &gt; Destination**. Detta standardvärde används sedan om fältet lämnas tomt i Sales.

    - Standardvärdet för mallen **AddressCountryRegionISOCode** är **USA**.
    - Standardvärdet för mallen **DeliveryAddressCountryRegionISOCode** är **USA**.

- Genom att lägga till följande mappningar från **CDS &gt; Destination**, kan du minska antalet manuella uppdateringar som krävs för Finance and Operations. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. En standardplats kan tas antingen från produkten eller från kunden från orderrubriken. Standardvärdet för mallen **SiteId** är **USA**.
    - **WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. Ett standardlager kan tas antingen från produkten eller från kunden från orderrubriken i Finance and Operations. Standardvärdet för mallen **WarehouseId** är **13**.
    - **LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations. Som standard används språk från orderrubriken från kunden. Standardvärdet för mallen **LanguageId** är **en-us**.

- Uppdatera CDS organisations-ID (**Organization_OrganizationId**) i **källa -&gt; CDS**-mappning. Standardmallvärdet är **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

> [!NOTE]
> Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du ställa in en värdemappning. Värdemappningarna är specifika för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

![Mallmappning i dataintegratör](./media/accounts-template-mapping-data-integrator-1.png)

![Mallmappning för konton i dataintegratör](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera produkter från Finance and Operations till produkter i Sales](products-template-mapping.md)

[Synkronisera kontakter från Sales till kontakter i Finance and Operations](contacts-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations](sales-quotation-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales](sales-order-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales](sales-invoice-template-mapping.md)




