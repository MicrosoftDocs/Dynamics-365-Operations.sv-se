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
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="3ee27-103">Synkronisera produkter med lagerenhet från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="3ee27-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3ee27-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="3ee27-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="3ee27-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="3ee27-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="3ee27-106">Den använda mallen **Field Service-produkter med lagerenhet (Finance and Operations till Field Service)** baseras på mallen **Field Service-produkter (Finance and Operations till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="3ee27-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="3ee27-107">Mer information finns i [Field Service-produkter (Finance and Operations till Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="3ee27-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="3ee27-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="3ee27-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="3ee27-109">**Field Service-produkter med lagerenhet (Finance and Operations till Sales)**</span><span class="sxs-lookup"><span data-stu-id="3ee27-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="3ee27-110">**Field Service-produkter (Finance and Operations till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="3ee27-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="3ee27-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="3ee27-111">Templates and tasks</span></span>

<span data-ttu-id="3ee27-112">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="3ee27-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="3ee27-113">Field Service-produkter med lagerenhet (Finance and Operations till Sales)</span><span class="sxs-lookup"><span data-stu-id="3ee27-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="3ee27-114">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="3ee27-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="3ee27-115">Produkter</span><span class="sxs-lookup"><span data-stu-id="3ee27-115">Products</span></span>

<span data-ttu-id="3ee27-116">Mallen **Field Service-produkter med lagerenhet (Finance and Operations till Field Service)** innehåller en mappning som inte ingår i mallen **Field Service-produkter (Finance and Operations till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="3ee27-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="3ee27-117">Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.</span><span class="sxs-lookup"><span data-stu-id="3ee27-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3ee27-118">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="3ee27-118">Template mapping in Data integration</span></span>

<span data-ttu-id="3ee27-119">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="3ee27-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="3ee27-120">Field Service-produkter med lagerenhet (Finance and Operations till Field Service): produkter</span><span class="sxs-lookup"><span data-stu-id="3ee27-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="3ee27-121">[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="3ee27-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
