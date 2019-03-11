---
title: Synkronisera arbetsorder med projekt från Field Service till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "329860"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Synkronisera arbetsorder med projekt från Field Service till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

Mallen **Field Service-produkter (Finance and Operations till Field Service)** som används baseras på mallen **Produkter (Finance and Operations till Sales) – direkt** från potentiell kund till kontanter. Mer information finns i [Produkter (Finance and Operations till Sales) – direkt](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Det här ämnet beskriver bara skillnaden mellan mallarna **Field Service-produkter (Finance and Operations till Field Service)** och **Produkter (Finance and Operations till Field Service) – direkt**.

Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Finance and Operations innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet. Dessutom använder mallen avancerad fråga och filtrering.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Arbetsorder med projekt (Field Service till Finance and Operations)

**Namnen på uppgiften i dataintegreringsprojektet:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Fältet **Externt projekt** har lagts till entiteten arbetsorder. Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Finance and Operations. När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderHeader

[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderHeaderProject

[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderProduct

[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderService

[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)
