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
ms.openlocfilehash: 18bedcc99d7d70875ec363a97e4e6eccbace3a9c
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814207"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="280c7-103">Synkronisera produkter med lagerenhet från Supply Chain Management till Field Service</span><span class="sxs-lookup"><span data-stu-id="280c7-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="280c7-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="280c7-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="280c7-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="280c7-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="280c7-106">Den använda mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** baseras på mallen **Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="280c7-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="280c7-107">Mer information finns i [Synkronisera produkter i Supply Chain Management till produkter i Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="280c7-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="280c7-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="280c7-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="280c7-109">**Field Service produkter med lagerenhet (Supply Chain Management till Sales)**</span><span class="sxs-lookup"><span data-stu-id="280c7-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="280c7-110">**Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="280c7-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="280c7-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="280c7-111">Templates and tasks</span></span>

<span data-ttu-id="280c7-112">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="280c7-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="280c7-113">Field Service produkter med lagerenhet (Supply Chain Management till Sales)</span><span class="sxs-lookup"><span data-stu-id="280c7-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="280c7-114">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="280c7-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="280c7-115">Produkter</span><span class="sxs-lookup"><span data-stu-id="280c7-115">Products</span></span>

<span data-ttu-id="280c7-116">Mallen **Field Service-produkter med lagerenhet (Supply Chain Management till Field Service)** innehåller en mappning som inte är inkluderad i mallen **Field Service-produkter (Supply Chain Management till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="280c7-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="280c7-117">Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.</span><span class="sxs-lookup"><span data-stu-id="280c7-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="280c7-118">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="280c7-118">Template mapping in Data integration</span></span>

<span data-ttu-id="280c7-119">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="280c7-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="280c7-120">Field Service-produkter med lagerenhet (Supply Chain Management till Field Service): produkter</span><span class="sxs-lookup"><span data-stu-id="280c7-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="280c7-121">[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="280c7-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
