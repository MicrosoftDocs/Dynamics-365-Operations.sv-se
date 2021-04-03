---
title: Synkronisera arbetsorder med projekt från Field Service till Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Dynamics 365 Field Service till Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 03/12/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d2364378ce8992666e374ec6f665c180d2fa1981
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258033"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Synkronisera arbetsorder med projekt från Field Service till Supply Chain Management

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Dynamics 365 Field Service till Dynamics 365 Supply Chain Management.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Den använda mallen **Arbetsorder med projekt (Field Service till Supply Chain Management)** som används baseras på mallen **Arbetsorder (Field Service till Supply Chain Management)**. Mer information finns i [Synkronisera arbetsorder i Field Service till försäljningsorder i Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Det här avsnittet beskriver endast skillnaderna mellan två mallar:
- **Arbetsorder med projekt (Field Service till Supply Chain Management)**
- **Arbetsorder med projekt (Field Service till Supply Chain Management)**

Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Supply Chain Management innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet. Dessutom använder mallen avancerad fråga och filtrering.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Arbetsorder med projekt (Field Service till Supply Chain Management)

**Namnen på uppgiften i dataintegreringsprojektet:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Fältet **Externt projekt** har lagts till entiteten arbetsorder. Detta fält är ett uppslagsfält och genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Supply Chain Management. När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderHeader

[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderHeaderProject

[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderProduct

[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderService

[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]