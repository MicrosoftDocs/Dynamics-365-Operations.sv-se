---
title: Synkronisera produkter med lagerenhet från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "359254"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="c3dcd-103">Synkronisera produkter med lagerenhet från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="c3dcd-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c3dcd-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter med lagerenhet från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c3dcd-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="c3dcd-106">Mallen **Field Service-produkter (Finance and Operations till Field Service)** som används baseras på mallen **Produkter (Finance and Operations till Sales) – direkt** från potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="c3dcd-107">Mer information finns i [Produkter (Finance and Operations till Sales) – direkt](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="c3dcd-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="c3dcd-108">Det här ämnet beskriver bara skillnaden mellan mallarna **Field Service-produkter (Finance and Operations till Field Service)** och **Produkter (Finance and Operations till Field Service) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c3dcd-109">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="c3dcd-109">Templates and tasks</span></span>

<span data-ttu-id="c3dcd-110">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="c3dcd-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c3dcd-111">Field Service-produkter med lagerenhet (Finance and Operations till Sales)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="c3dcd-112">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="c3dcd-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c3dcd-113">Produkter</span><span class="sxs-lookup"><span data-stu-id="c3dcd-113">Products</span></span>

<span data-ttu-id="c3dcd-114">Mallen **Field Service-produkter med lagerenhet (Finance and Operations till Field Service)** innehåller en mappning som inte ingår i mallen **Field Service-produkter (Finance and Operations till Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="c3dcd-115">Den här mappningen garanterar att den lagerenhet som behövs för synkronisering på nivå lager ingår.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c3dcd-116">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="c3dcd-116">Template mapping in Data integration</span></span>

<span data-ttu-id="c3dcd-117">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="c3dcd-118">Field Service-produkter med lagerenhet (Finance and Operations till Field Service): produkter</span><span class="sxs-lookup"><span data-stu-id="c3dcd-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="c3dcd-119">[![Mallmappning i dataintegrering](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
