---
title: Synkronisera information om lagernivåer från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b81694f1ed56d8542de46203ac5faf5fae2b6645
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "356793"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="2cf56-103">Synkronisera information om lagernivåer från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="2cf56-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2cf56-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="2cf56-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="2cf56-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="2cf56-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2cf56-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="2cf56-106">Templates and tasks</span></span>
<span data-ttu-id="2cf56-107">Följande mall och underliggande uppgifter används för att synkronisera lagerhållningsnivåer från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="2cf56-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="2cf56-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="2cf56-108">**Template in Data integration**</span></span>
- <span data-ttu-id="2cf56-109">Produktlager (Finance and Operations till Field Service)</span><span class="sxs-lookup"><span data-stu-id="2cf56-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="2cf56-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="2cf56-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="2cf56-111">Produktlager</span><span class="sxs-lookup"><span data-stu-id="2cf56-111">Product inventory</span></span>

<span data-ttu-id="2cf56-112">Följande synkroniseringsuppgifter krävs före synkronisering av lagernivåer kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="2cf56-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="2cf56-113">Lagerställen (Finance and Operations till Field Service)</span><span class="sxs-lookup"><span data-stu-id="2cf56-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="2cf56-114">Field Service-produkter med lagerenhet (Finance and Operations till Sales)</span><span class="sxs-lookup"><span data-stu-id="2cf56-114">Field Service products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="2cf56-115">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="2cf56-115">Entity set</span></span>

| <span data-ttu-id="2cf56-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="2cf56-116">Field Service</span></span>                      | <span data-ttu-id="2cf56-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2cf56-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="2cf56-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="2cf56-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="2cf56-119">CDS lagerbehållning enligt lagerställe</span><span class="sxs-lookup"><span data-stu-id="2cf56-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="2cf56-120">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="2cf56-120">Entity flow</span></span>
<span data-ttu-id="2cf56-121">Information om lagernivåer från Finance and Operations till Field Service för utvalda produkter</span><span class="sxs-lookup"><span data-stu-id="2cf56-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="2cf56-122">Information om lagernivåer inkluderar:</span><span class="sxs-lookup"><span data-stu-id="2cf56-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="2cf56-123">Lagerbehållning (aktuell införd fysisk kvantiteten i lagret)</span><span class="sxs-lookup"><span data-stu-id="2cf56-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="2cf56-124">Kvantitet har beställts (total registrerad kvantitet som beställts - dvs försäljningsorder)</span><span class="sxs-lookup"><span data-stu-id="2cf56-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="2cf56-125">Beställd kvantitet beställts (total registrerad beställd kvantitet - dvs försäljningsorder)</span><span class="sxs-lookup"><span data-stu-id="2cf56-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="2cf56-126">Informationen registreras per frisläppt produkt för varje lagerställe och synkroniseras utifrån ändringsspårning när lagernivån ändras.</span><span class="sxs-lookup"><span data-stu-id="2cf56-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="2cf56-127">I Field Service skapar integreringslösningen lagerjournaler för delta, för att få nivåer i Field Service att matcha nivåer i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2cf56-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="2cf56-128">Finance and Operations kommer att fungera som mall för lagernivåer.</span><span class="sxs-lookup"><span data-stu-id="2cf56-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="2cf56-129">Därför är det viktigt att ställa in integration för arbetsorder, överföringar och justeringar från Field Service till Finance and Operations om den funktionen används i Field Service samt synkronisering av lagernivåerna från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2cf56-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="2cf56-130">Produkter och lagerställen där lagernivåer hanteras från Finance and Operations kan styras med avancerad fråga och filtrering (Power Query).</span><span class="sxs-lookup"><span data-stu-id="2cf56-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="2cf56-131">Det går att skapa flera lagerställen i Field Service (med **Hanteras externt = Nej**) och mappa dem till ett enda lager i Finance and Operations med avancerad fråga och filtreringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="2cf56-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="2cf56-132">Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2cf56-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="2cf56-133">I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2cf56-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="2cf56-134">För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="2cf56-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="2cf56-135">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="2cf56-135">Field Service CRM solution</span></span>
<span data-ttu-id="2cf56-136">Entiteten **Externt produktlager** är en ny entitet som endast används för stöd i integrationen.</span><span class="sxs-lookup"><span data-stu-id="2cf56-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="2cf56-137">Den här entiteten tar emot värdena för lagernivåer från Finance and Operations i integrationen och omvandlar sedan dessa värden till manuella lagerjournaler, som sedan ändrar lagerprodukterna på lagret.</span><span class="sxs-lookup"><span data-stu-id="2cf56-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="2cf56-138">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2cf56-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration-project"></a><span data-ttu-id="2cf56-139">Dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="2cf56-139">Data integration project</span></span>
<span data-ttu-id="2cf56-140">Du kan tillämpa filter med avancerad fråga och filtrering för att kontrollera att bara önskade produkter och lagerställen skickar information om lagernivåer från Finance and Operations till Field Service.</span><span class="sxs-lookup"><span data-stu-id="2cf56-140">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2cf56-141">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="2cf56-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="2cf56-142">Produktlager (Finance and Operations till Field Service): Produktlager</span><span class="sxs-lookup"><span data-stu-id="2cf56-142">Product inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="2cf56-143">[![Mallmappning i dataintegrering](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="2cf56-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
