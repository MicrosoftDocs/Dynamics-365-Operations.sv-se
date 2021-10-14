---
title: Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
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
ms.openlocfilehash: 6ac346d735bc44e9f9660c60b23a73057e4b7306
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566345"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Den använda mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** baseras på mallen **Field Service-produkter (Supply Chain Management till Field Service)**. Mer information finns i [Synkronisera produkter i Supply Chain Management till produkter i Field Service](field-service-product.md).

Det här avsnittet beskriver endast skillnaderna mellan två mallar: 
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