---
title: Synkronisera arbetsorder med projekt från Field Service till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536743"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synkronisera arbetsorder med projekt från Field Service till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Den använda mallen **Arbetsorder med projekt (Field Service till Fin and Ops)** som används baseras på mallen **Arbetsorder (Field Service till Fin and Ops)**. Mer information finns i [Synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

Det här avsnittet beskriver endast skillnaderna mellan två mallar:
- **Arbetsorder med projekt (Field Service till Fin and Ops)**
- **Arbetsorder (Field Service till Fin and Ops)**

Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Finance and Operations innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet. Dessutom använder mallen avancerad fråga och filtrering.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Arbetsorder med projekt (Field Service till Fin and Ops)

**Namnen på uppgiften i dataintegreringsprojektet:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Fältet **Externt projekt** har lagts till entiteten arbetsorder. Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Finance and Operations. När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderHeader

[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderHeaderProject

[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderProduct

[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderService

[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)
