---
title: Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8b65e9640106c5d351270074e39c121e70917228
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251234"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Den använda mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** baseras på mallen **Field Service-produkter (Supply Chain Management till Field Service)**. Mer information finns i [Field Service-produkter (Supply Chain Management till Field Service)](field-service-product.md).

Det här avsnittet beskriver endast skillnaderna mellan två mallar: 
- **Field Service produkter med lagerenhet (Supply Chain Management till Sales)**
- **Field Service-produkter (Supply Chain Management till Field Service)**. 

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Field Service produkter med lagerenhet (Supply Chain Management till Sales)

**Namnen på uppgiften i dataintegreringsprojektet:**

- Produkter

Mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** innehåller en mappning som inte är inkluderad i mallen **Field Service-produkter (Supply Chain Management till Field Service)**. Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Field Service-produkter med lagerenhet (Supply Chain Management till Field Service): produkter

[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)
