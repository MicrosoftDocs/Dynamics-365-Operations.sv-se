---
title: "Synkronisera lagerställen från Finance and Operations till Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="52d63-103">Synkronisera lagerställen från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="52d63-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="52d63-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="52d63-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="52d63-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="52d63-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="52d63-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="52d63-106">Templates and tasks</span></span>
<span data-ttu-id="52d63-107">Följande mall och underliggande uppgifter används för att synkronisera lagerställen från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="52d63-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="52d63-108">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="52d63-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="52d63-109">Lagerställen (Finance and Operations till Field Service)</span><span class="sxs-lookup"><span data-stu-id="52d63-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="52d63-110">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="52d63-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="52d63-111">Lagerställe</span><span class="sxs-lookup"><span data-stu-id="52d63-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="52d63-112">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="52d63-112">Entity set</span></span>
| <span data-ttu-id="52d63-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="52d63-113">Field Service</span></span>    | <span data-ttu-id="52d63-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="52d63-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="52d63-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="52d63-115">msdyn_warehouses</span></span> | <span data-ttu-id="52d63-116">Lagerställen</span><span class="sxs-lookup"><span data-stu-id="52d63-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="52d63-117">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="52d63-117">Entity flow</span></span>
<span data-ttu-id="52d63-118">Lagerställen som har skapats och underhålls i Finance and Operations kan synkroniseras till Field Service via ett Common Data Service (CDS) dataintegreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="52d63-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="52d63-119">Önskade lagerställen som ska synkroniseras till Field Service kan kontrolleras med avancerad fråga och filtrering i projektet.</span><span class="sxs-lookup"><span data-stu-id="52d63-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="52d63-120">Lagerställen som ska synkroniseras från Finance and Operations skapas i Field Service med fältet Underhålls externt angett till Ja och posten blir endast läst.</span><span class="sxs-lookup"><span data-stu-id="52d63-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="52d63-121">CRM-lösning för Field Service för att stödja integrationen mellan Field Service och Finance and Operations krävs ytterligare funktioner från Field Service CRM-lösning.</span><span class="sxs-lookup"><span data-stu-id="52d63-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="52d63-122">Lösningen omfattar följande ändringar.</span><span class="sxs-lookup"><span data-stu-id="52d63-122">The solution includes the following changes.</span></span>
<span data-ttu-id="52d63-123">Fältet **Hanteras ecternt** har lagts till i enheten **Lagerställe (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="52d63-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="52d63-124">Det här fältet hjälper till att identifiera om lagerstället ska hanteras från Operations eller om bara finns i Field Service.</span><span class="sxs-lookup"><span data-stu-id="52d63-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="52d63-125">Ja – Lagerstället kommer från Finance and Operations och kan inte redigeras i Sales.</span><span class="sxs-lookup"><span data-stu-id="52d63-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="52d63-126">Nej – Lagerstället angavs direkt i Field Service och underhålls här.</span><span class="sxs-lookup"><span data-stu-id="52d63-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="52d63-127">Fältet **Hanteras externt** hjälper till att styra synkroniseringen av lagernivåer, justeringar, överföring och användning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="52d63-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="52d63-128">Endast lagerställen med **Hanteras externt** = Ja kan användas för att synkronisera direkt till samma lagerställe i det andra systemet.</span><span class="sxs-lookup"><span data-stu-id="52d63-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="52d63-129">Obs! Det går att skapa flera lagerställen i Field Services (med **Hanteras externt** = Nej) och mappa dem till ett enda lager i Finance and Operations med avancerad fråga och filtreringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="52d63-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="52d63-130">Detta används när du vill att Field service ska hantera detaljerad lagernivå och bara skicka uppdateringar till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="52d63-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="52d63-131">I detta fall kommer Field Service inte att få uppdateringar av lagernivåer från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="52d63-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="52d63-132">Visa ytterligare information i Synkronisera lagerjusteringar från Field Service till Finance and Operations och Synkronisera arbetsorder i Field Service till försäljningsorder som är kopplade till projekt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="52d63-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="52d63-133">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="52d63-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="52d63-134">I dataintegreringsprojektet</span><span class="sxs-lookup"><span data-stu-id="52d63-134">In the Data Integration project</span></span>
<span data-ttu-id="52d63-135">Se till att uppdatera avancerad fråga och filtrering på projektet före synkroniseringen av lagerställen för att bara inkludera de lagerställen som du vill flytta från Finance and Operations till Field Service.</span><span class="sxs-lookup"><span data-stu-id="52d63-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="52d63-136">Observera att du behöver lagerstället i Field Service för att använda det på arbetsorder, justeringar och överföringar.</span><span class="sxs-lookup"><span data-stu-id="52d63-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="52d63-137">Kontrollera att **integreringsnyckel** finns i **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="52d63-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="52d63-138">Gå till dataintegration</span><span class="sxs-lookup"><span data-stu-id="52d63-138">Go to Data Integration</span></span>
2. <span data-ttu-id="52d63-139">Välj fliken **Anslutningsinställning**</span><span class="sxs-lookup"><span data-stu-id="52d63-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="52d63-140">Välj anslutningsinställning som används för arbetsordersynkronisering</span><span class="sxs-lookup"><span data-stu-id="52d63-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="52d63-141">Välj fliken **Integreringsnyckel**</span><span class="sxs-lookup"><span data-stu-id="52d63-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="52d63-142">Söka efter msdyn_warehouses och kontrollera att nyckeln **msdyn_name (namn)** läggs till.</span><span class="sxs-lookup"><span data-stu-id="52d63-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="52d63-143">Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan</span><span class="sxs-lookup"><span data-stu-id="52d63-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="52d63-144">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="52d63-144">Template mapping in Data integration</span></span>

<span data-ttu-id="52d63-145">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="52d63-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="52d63-146">Lagerställen (Finance and Operations till Field Service): lagerställe</span><span class="sxs-lookup"><span data-stu-id="52d63-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="52d63-147">[![Mallmappning i dataintegrering](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="52d63-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

