---
title: "Synkronisera produkter med lagerenhet från Finance and Operations till Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Synkronisera produkter med lagerenhet från Finance and Operations till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

Mallen **Field Service-produkter (Finance and Operations till Field Service)** som används baseras på mallen **Produkter (Finance and Operations till Sales) – direkt** från potentiell kund till kontanter. Mer information finns i [Produkter (Finance and Operations till Sales) – direkt](products-template-mapping-direct.md).

Det här ämnet beskriver bara skillnaden mellan mallarna **Field Service-produkter (Finance and Operations till Field Service)** och **Produkter (Finance and Operations till Field Service) – direkt**.

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

