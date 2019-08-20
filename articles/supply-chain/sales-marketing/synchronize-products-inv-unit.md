---
title: Synkronisera produkter med lagerenhet från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 78e8d8fa609b015cf2fceaf498279fe091325dbb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835704"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="e90a6-103">Synkronisera produkter med lagerenhet från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="e90a6-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e90a6-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="e90a6-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="e90a6-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="e90a6-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="e90a6-106">Den använda mallen **Field Service-produkter med lagerenhet (Fin and Ops till Field Service)** baseras på mallen **Field Service-produkter (Fin and Ops till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="e90a6-106">The used **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template is based on the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="e90a6-107">Mer information finns i [Field Service-produkter (Finance and Operations till Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="e90a6-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="e90a6-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="e90a6-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="e90a6-109">**Field Service-produkter med lagerenhet (Fin and Ops till Sales)**</span><span class="sxs-lookup"><span data-stu-id="e90a6-109">**Field Service Products with Inventory unit (Fin and Ops to Sales)**</span></span>
- <span data-ttu-id="e90a6-110">**Fältserviceprodukter (Fin and Ops till Field Service)**</span><span class="sxs-lookup"><span data-stu-id="e90a6-110">**Field Service Products (Fin and Ops to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="e90a6-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="e90a6-111">Templates and tasks</span></span>

<span data-ttu-id="e90a6-112">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="e90a6-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="e90a6-113">Field Service-produkter med lagerenhet (Fin and Ops till Sales)</span><span class="sxs-lookup"><span data-stu-id="e90a6-113">Field Service Products with Inventory unit (Fin and Ops to Sales)</span></span>

<span data-ttu-id="e90a6-114">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="e90a6-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="e90a6-115">Produkter</span><span class="sxs-lookup"><span data-stu-id="e90a6-115">Products</span></span>

<span data-ttu-id="e90a6-116">Mallen **Field Service-produkter med lagerenhet (Fin and Ops till Field Service)** innehåller en mappning som inte ingår i mallen **Field Service-produkter (Fin and Ops till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="e90a6-116">The **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="e90a6-117">Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.</span><span class="sxs-lookup"><span data-stu-id="e90a6-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="e90a6-118">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="e90a6-118">Template mapping in Data integration</span></span>

<span data-ttu-id="e90a6-119">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="e90a6-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a><span data-ttu-id="e90a6-120">Field Service-produkter med lagerenhet (Fin and Ops till Field Service): produkter</span><span class="sxs-lookup"><span data-stu-id="e90a6-120">Field Service Products with Inventory unit (Fin and Ops to Field Service): Products</span></span>

<span data-ttu-id="e90a6-121">[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="e90a6-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
