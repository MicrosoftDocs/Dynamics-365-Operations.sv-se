---
title: Synkronisera produkter med lagerenhet från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2019
ms.locfileid: "836312"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synkronisera produkter med lagerenhet från Finance and Operations till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Den använda mallen **Field Service-produkter med lagerenhet (Finance and Operations till Field Service)** baseras på mallen **Field Service-produkter (Finance and Operations till Field Service)**. Mer information finns i [Field Service-produkter (Finance and Operations till Field Service)](field-service-product.md).

Det här avsnittet beskriver endast skillnaderna mellan två mallar: 
- **Field Service-produkter med lagerenhet (Finance and Operations till Sales)**
- **Field Service-produkter (Finance and Operations till Field Service)**. 

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Field Service-produkter med lagerenhet (Finance and Operations till Sales)

**Namnen på uppgiften i dataintegreringsprojektet:**

- Produkter

Mallen **Field Service-produkter med lagerenhet (Finance and Operations till Field Service)** innehåller en mappning som inte ingår i mallen **Field Service-produkter (Finance and Operations till Field Service)**. Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Field Service-produkter med lagerenhet (Finance and Operations till Field Service): produkter

[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)
