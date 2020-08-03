---
title: Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 62ed33d101f7d7e47b560c417dc05e5aecc83478
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546348"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="a2bdf-103">Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service</span><span class="sxs-lookup"><span data-stu-id="a2bdf-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a2bdf-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="a2bdf-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="a2bdf-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="a2bdf-106">Den använda mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** baseras på mallen **Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="a2bdf-107">Mer information finns i [Synkronisera produkter i Supply Chain Management till produkter i Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="a2bdf-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="a2bdf-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="a2bdf-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="a2bdf-109">**Field Service produkter med lagerenhet (Supply Chain Management till Sales)**</span><span class="sxs-lookup"><span data-stu-id="a2bdf-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="a2bdf-110">**Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="a2bdf-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="a2bdf-111">Templates and tasks</span></span>

<span data-ttu-id="a2bdf-112">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="a2bdf-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="a2bdf-113">Field Service produkter med lagerenhet (Supply Chain Management till Sales)</span><span class="sxs-lookup"><span data-stu-id="a2bdf-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="a2bdf-114">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="a2bdf-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="a2bdf-115">Produkter</span><span class="sxs-lookup"><span data-stu-id="a2bdf-115">Products</span></span>

<span data-ttu-id="a2bdf-116">Mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** innehåller en mappning som inte är inkluderad i mallen **Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="a2bdf-117">Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a2bdf-118">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="a2bdf-118">Template mapping in Data integration</span></span>

<span data-ttu-id="a2bdf-119">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="a2bdf-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="a2bdf-120">Field Service-produkter med lagerenhet (Supply Chain Management till Field Service): produkter</span><span class="sxs-lookup"><span data-stu-id="a2bdf-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="a2bdf-121">[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="a2bdf-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
