---
title: Synkronisera information om lagerjusteringar från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 0822bf4bdbb687e040e2ce04842ef263b8dc0e1a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243091"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="f3e2e-103">Synkronisera information om lagerjusteringar från Supply Chain Management till Field Service</span><span class="sxs-lookup"><span data-stu-id="f3e2e-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f3e2e-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera information om lagernivåer från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="f3e2e-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f3e2e-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="f3e2e-106">Templates and tasks</span></span>
<span data-ttu-id="f3e2e-107">Följande mall och underliggande uppgifter används för att synkronisera lagerhållningsnivåer från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="f3e2e-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="f3e2e-108">**Template in Data integration**</span></span>
- <span data-ttu-id="f3e2e-109">Produktlager (Supply Chain Management till Field Service)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="f3e2e-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="f3e2e-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="f3e2e-111">Produktlager</span><span class="sxs-lookup"><span data-stu-id="f3e2e-111">Product inventory</span></span>

<span data-ttu-id="f3e2e-112">Följande synkroniseringsuppgifter krävs före synkronisering av lagernivåer kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="f3e2e-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="f3e2e-113">Lagerställen (Supply Chain Management till Field Service)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="f3e2e-114">Field Service produkter med lagerenhet (Supply Chain Management till Sales)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="f3e2e-115">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="f3e2e-115">Entity set</span></span>

| <span data-ttu-id="f3e2e-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="f3e2e-116">Field Service</span></span>                      | <span data-ttu-id="f3e2e-117">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="f3e2e-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="f3e2e-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="f3e2e-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="f3e2e-119">Dataverse lagerbehållning enligt lagerställe</span><span class="sxs-lookup"><span data-stu-id="f3e2e-119">Dataverse inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="f3e2e-120">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="f3e2e-120">Entity flow</span></span>
<span data-ttu-id="f3e2e-121">Information om lagernivåer från Finance and Operations till Field Service för utvalda produkter</span><span class="sxs-lookup"><span data-stu-id="f3e2e-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="f3e2e-122">Information om lagernivåer inkluderar:</span><span class="sxs-lookup"><span data-stu-id="f3e2e-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="f3e2e-123">Lagerbehållning (aktuell införd fysisk kvantiteten i lagret)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="f3e2e-124">Kvantitet har beställts (total registrerad kvantitet som beställts - dvs försäljningsorder)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="f3e2e-125">Beställd kvantitet beställts (total registrerad beställd kvantitet - dvs försäljningsorder)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="f3e2e-126">Informationen registreras per frisläppt produkt för varje lagerställe och synkroniseras utifrån ändringsspårning när lagernivån ändras.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="f3e2e-127">I Field Service skapar integreringslösningen lagerjournaler för delta, för att få nivåer i Field Service att matcha nivåer i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="f3e2e-128">Supply Chain Management kommer att fungera som mall för lagernivåer.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="f3e2e-129">Därför är det viktigt att ställa in integration för arbetsorder, överföringar och justeringar från Field Service till Supply Chain Management om den funktionen används i Field Service samt synkronisering av lagernivåerna från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="f3e2e-130">Produkter och lagerställen där lagernivåer hanteras från Supply Chain Management kan styras med avancerad fråga och filtrering (Power Query).</span><span class="sxs-lookup"><span data-stu-id="f3e2e-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="f3e2e-131">Det går att skapa flera lagerställen i Field Service (med **Hanteras externt = Nej**) och mappa dem till ett enda lager i Supply Chain Management med avancerad fråga och filtreringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="f3e2e-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="f3e2e-132">Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="f3e2e-133">I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="f3e2e-134">För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="f3e2e-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="f3e2e-135">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="f3e2e-135">Field Service CRM solution</span></span>
<span data-ttu-id="f3e2e-136">Entiteten **Externt produktlager** är en ny entitet som endast används för stöd i integrationen.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="f3e2e-137">Den här entiteten tar emot värdena för lagernivåer från Supply Chain Management i integrationen och omvandlar sedan dessa värden till manuella lagerjournaler, som sedan ändrar lagerprodukterna på lagret.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f3e2e-138">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f3e2e-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="f3e2e-139">Dataintegration</span><span class="sxs-lookup"><span data-stu-id="f3e2e-139">Data integration</span></span>
<span data-ttu-id="f3e2e-140">För att projektet ska fungera måste du se till att integrationsnyckeln uppdateras för msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="f3e2e-141">Gå till **Dataintegration > anslutningsuppsättningar**.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="f3e2e-142">Välj den använda anslutningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="f3e2e-143">På fliken **Integrationsnyckeln**, se till att följande nyckel läggs till msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="f3e2e-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="f3e2e-144">msdynce_productnumber (produktnummer)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="f3e2e-145">msdynce_warehouseid (dist.lager-ID)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="f3e2e-146">Dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="f3e2e-146">Data integration project</span></span>
<span data-ttu-id="f3e2e-147">Du kan tillämpa filter med avancerad fråga och filtrering för att kontrollera att bara önskade produkter och lagerställen skickar information om lagernivåer från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="f3e2e-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f3e2e-148">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="f3e2e-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="f3e2e-149">Produktlager (Supply Chain Management till Field Service): Produktlager</span><span class="sxs-lookup"><span data-stu-id="f3e2e-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="f3e2e-150">[![Mallmappning i dataintegrering](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="f3e2e-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]