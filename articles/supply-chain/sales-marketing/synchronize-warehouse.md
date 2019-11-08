---
title: Synkronisera lagerställen från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
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
ms.openlocfilehash: b55a0b9e54eabdcdbd3f858cf3725b8fe833f65d
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653404"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="840c9-103">Synkronisera lagerställen från Supply Chain Management till Field Service</span><span class="sxs-lookup"><span data-stu-id="840c9-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="840c9-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="840c9-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="840c9-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="840c9-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="840c9-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="840c9-106">Templates and tasks</span></span>
<span data-ttu-id="840c9-107">Följande mall och underliggande uppgifter används för att köra synkronisering av lagerställen från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="840c9-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="840c9-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="840c9-108">**Template in Data integration**</span></span>
- <span data-ttu-id="840c9-109">Lagerställen (Supply Chain Management till Field Service)</span><span class="sxs-lookup"><span data-stu-id="840c9-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="840c9-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="840c9-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="840c9-111">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="840c9-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="840c9-112">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="840c9-112">Entity set</span></span>
| <span data-ttu-id="840c9-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="840c9-113">Field Service</span></span>    | <span data-ttu-id="840c9-114">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="840c9-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="840c9-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="840c9-115">msdyn_warehouses</span></span> | <span data-ttu-id="840c9-116">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="840c9-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="840c9-117">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="840c9-117">Entity flow</span></span>
<span data-ttu-id="840c9-118">Lagerställen som har skapats och underhålls i Supply Chain Management kan synkroniseras till Field Service via ett Common Data Service (CDS) dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="840c9-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="840c9-119">De lagerställen som du vill synkronisera till Field Service kan kontrolleras med avancerad fråga och filtrering i projektet.</span><span class="sxs-lookup"><span data-stu-id="840c9-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="840c9-120">Lagerställen som ska synkroniseras från Supply Chain Management skapas i Field Service med fältet **Underhålls externt** anges till **Ja** och posten är skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="840c9-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="840c9-121">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="840c9-121">Field Service CRM solution</span></span>
<span data-ttu-id="840c9-122">För att stödja integrationen mellan Field Service och Supply Chain Management krävs ytterligare funktioner från Field Service CRM-lösning.</span><span class="sxs-lookup"><span data-stu-id="840c9-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="840c9-123">I lösningen har fältet **Hanteras externt** har lagts till i enheten **Lagerställe (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="840c9-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="840c9-124">Det här fältet hjälper till att identifiera om lagerstället ska hanteras från Supply Chain Management eller om det bara finns i Field Service.</span><span class="sxs-lookup"><span data-stu-id="840c9-124">This field helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="840c9-125">Inställningarna för detta fält är:</span><span class="sxs-lookup"><span data-stu-id="840c9-125">The settings for this field include:</span></span>
- <span data-ttu-id="840c9-126">**Ja** – Lagerstället kommer från Supply Chain Management och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="840c9-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="840c9-127">**Nej** – Lagerstället angavs direkt i Field Service och underhålls här.</span><span class="sxs-lookup"><span data-stu-id="840c9-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="840c9-128">Fältet **Hanteras externt** hjälper till att styra synkroniseringen av lagernivåer, justeringar, överföring och användning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="840c9-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="840c9-129">Endast lagerställen med **Hanteras externt** som anges till **Ja** kan användas för att synkronisera direkt till samma lagerställe i det andra systemet.</span><span class="sxs-lookup"><span data-stu-id="840c9-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="840c9-130">Det går att skapa flera lagerställen i Field Service (med **Hanteras externt** = Nej) och mappa dem till ett enda lager med avancerad fråga och filtreringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="840c9-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="840c9-131">Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="840c9-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="840c9-132">I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="840c9-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="840c9-133">För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="840c9-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="840c9-134">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="840c9-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="840c9-135">Dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="840c9-135">Data Integration project</span></span>
<span data-ttu-id="840c9-136">Se till att uppdatera avancerad fråga och filtrering på projektet före synkroniseringen av lagerställen för att bara inkludera de lagerställen som du vill flytta från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="840c9-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="840c9-137">Observera att du behöver lagerstället i Field Service för att använda det på arbetsorder, justeringar och överföringar.</span><span class="sxs-lookup"><span data-stu-id="840c9-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="840c9-138">Kontrollera att **integreringsnyckel** finns i **msdyn_warehouses** genom att:</span><span class="sxs-lookup"><span data-stu-id="840c9-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="840c9-139">Gå till dataintegration.</span><span class="sxs-lookup"><span data-stu-id="840c9-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="840c9-140">Välj fliken **Anslutningsinställning**.</span><span class="sxs-lookup"><span data-stu-id="840c9-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="840c9-141">Välj anslutningsinställning som används för arbetsordersynkronisering.</span><span class="sxs-lookup"><span data-stu-id="840c9-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="840c9-142">Välj fliken **Integreringsnyckel**.</span><span class="sxs-lookup"><span data-stu-id="840c9-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="840c9-143">Sök efter msdyn_warehouses och bekräfta att nyckeln **msdyn_name (namn)** läggs till.</span><span class="sxs-lookup"><span data-stu-id="840c9-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="840c9-144">Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="840c9-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="840c9-145">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="840c9-145">Template mapping in Data integration</span></span>

<span data-ttu-id="840c9-146">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="840c9-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="840c9-147">Lagerställen (Supply Chain Management till Field Service): lagerställe</span><span class="sxs-lookup"><span data-stu-id="840c9-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="840c9-148">[![Mallmappning i dataintegrering](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="840c9-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
