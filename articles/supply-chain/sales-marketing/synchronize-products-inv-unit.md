---
title: Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service
description: Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5f7658eacd20aa69a64d6288e9d29e53b6ccb002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887266"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service

[!include[banner](../includes/banner.md)]

Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Den använda mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** baseras på mallen **Field Service-produkter (Supply Chain Management till Field Service)**. Mer information finns i [Synkronisera produkter i Supply Chain Management till produkter i Field Service](field-service-product.md).

Denna artikel beskriver endast skillnaderna mellan två mallar: 
- **Field Service produkter med lagerenhet (Supply Chain Management till Sales)**
- **Field Service-produkter (Supply Chain Management till Field Service)**. 

## <a name="templates-and-tasks"></a>Mallar och uppgifter

**Namnet på mallen i dataintegreringen**

- Field Service produkter med lagerenhet (Supply Chain Management till Sales)

**Namnen på uppgiften i dataintegreringsprojektet:**

- Produkter

Mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** innehåller en mappning som inte är inkluderad i mallen **Field Service-produkter (Supply Chain Management till Field Service)**. Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Field Service-produkter med lagerenhet (Supply Chain Management till Field Service): produkter

[![Mallmappning i dataintegrering.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]