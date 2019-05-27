---
title: Synkronisera lagerställen från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535685"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="4cdf2-103">Synkronisera lagerställen från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="4cdf2-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4cdf2-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="4cdf2-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="4cdf2-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4cdf2-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="4cdf2-106">Templates and tasks</span></span>
<span data-ttu-id="4cdf2-107">Följande mall och underliggande uppgifter används för att köra synkronisering av lagerställen från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="4cdf2-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="4cdf2-108">**Template in Data integration**</span></span>
- <span data-ttu-id="4cdf2-109">Lagerställen (Fin and Ops till Field Service)</span><span class="sxs-lookup"><span data-stu-id="4cdf2-109">Warehouses (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="4cdf2-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="4cdf2-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="4cdf2-111">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="4cdf2-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="4cdf2-112">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="4cdf2-112">Entity set</span></span>
| <span data-ttu-id="4cdf2-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="4cdf2-113">Field Service</span></span>    | <span data-ttu-id="4cdf2-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4cdf2-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="4cdf2-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="4cdf2-115">msdyn_warehouses</span></span> | <span data-ttu-id="4cdf2-116">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="4cdf2-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="4cdf2-117">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="4cdf2-117">Entity flow</span></span>
<span data-ttu-id="4cdf2-118">Lagerställen som har skapats och underhålls i Finance and Operations kan synkroniseras till Field Service via ett Common Data Service (CDS) dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="4cdf2-119">De lagerställen som du vill synkronisera till Field Service kan kontrolleras med avancerad fråga och filtrering i projektet.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="4cdf2-120">Lagerställen som ska synkroniseras från Finance and Operations skapas i Field Service med fältet **Underhålls externt** anges till **Ja** och posten är skrivskyddad.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="4cdf2-121">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="4cdf2-121">Field Service CRM solution</span></span>
<span data-ttu-id="4cdf2-122">För att stödja integrationen mellan Field Service och Finance and Operations krävs ytterligare funktioner från Field Service CRM-lösning.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="4cdf2-123">I lösningen har fältet **Hanteras externt** har lagts till i enheten **Lagerställe (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="4cdf2-124">Det här fältet hjälper till att identifiera om lagerstället ska hanteras från Finance and Operations eller om det bara finns i Field Service.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="4cdf2-125">Inställningarna för detta fält är:</span><span class="sxs-lookup"><span data-stu-id="4cdf2-125">The settings for this field include:</span></span>
- <span data-ttu-id="4cdf2-126">**Ja** – Lagerstället kommer från Finance and Operations och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="4cdf2-127">**Nej** – Lagerstället angavs direkt i Field Service och underhålls här.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="4cdf2-128">Fältet **Hanteras externt** hjälper till att styra synkroniseringen av lagernivåer, justeringar, överföring och användning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="4cdf2-129">Endast lagerställen med **Hanteras externt** som anges till **Ja** kan användas för att synkronisera direkt till samma lagerställe i det andra systemet.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="4cdf2-130">Det går att skapa flera lagerställen i Field Service (med **Hanteras externt** = Nej) och mappa dem till ett enda lager i Finance and Operations med avancerad fråga och filtreringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="4cdf2-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="4cdf2-131">Detta används när du vill att Field Service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="4cdf2-132">I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="4cdf2-133">För ytterligare information, se [Synkronisera lagerjusteringar från Field Service till Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) och [Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="4cdf2-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="4cdf2-134">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4cdf2-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="4cdf2-135">Dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="4cdf2-135">Data Integration project</span></span>
<span data-ttu-id="4cdf2-136">Se till att uppdatera avancerad fråga och filtrering på projektet före synkroniseringen av lagerställen för att bara inkludera de lagerställen som du vill flytta från Finance and Operations till Field Service.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="4cdf2-137">Observera att du behöver lagerstället i Field Service för att använda det på arbetsorder, justeringar och överföringar.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="4cdf2-138">Kontrollera att **integreringsnyckel** finns i **msdyn_warehouses** genom att:</span><span class="sxs-lookup"><span data-stu-id="4cdf2-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="4cdf2-139">Gå till dataintegration.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="4cdf2-140">Välj fliken **Anslutningsinställning**.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="4cdf2-141">Välj anslutningsinställning som används för arbetsordersynkronisering.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="4cdf2-142">Välj fliken **Integreringsnyckel**.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="4cdf2-143">Sök efter msdyn_warehouses och bekräfta att nyckeln **msdyn_name (namn)** läggs till.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="4cdf2-144">Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4cdf2-145">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="4cdf2-145">Template mapping in Data integration</span></span>

<span data-ttu-id="4cdf2-146">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="4cdf2-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a><span data-ttu-id="4cdf2-147">Lagerställen (Fin and Ops till Field Service): Lagerställe</span><span class="sxs-lookup"><span data-stu-id="4cdf2-147">Warehouses (Fin and Ops to Field Service): Warehouse</span></span>

<span data-ttu-id="4cdf2-148">[![Mallmappning i dataintegrering](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="4cdf2-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
