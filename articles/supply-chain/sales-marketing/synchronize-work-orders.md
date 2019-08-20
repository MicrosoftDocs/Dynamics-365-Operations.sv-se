---
title: Synkronisera arbetsorder med projekt från Field Service till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 77358513ffdf791ab10d6efe1b84f598ffb5ec26
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843419"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="7f63e-103">Synkronisera arbetsorder med projekt från Field Service till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7f63e-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7f63e-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7f63e-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="7f63e-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="7f63e-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="7f63e-106">Den använda mallen **Arbetsorder med projekt (Field Service till Fin and Ops)** som används baseras på mallen **Arbetsorder (Field Service till Fin and Ops)**.</span><span class="sxs-lookup"><span data-stu-id="7f63e-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="7f63e-107">Mer information finns i [Synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="7f63e-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="7f63e-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="7f63e-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="7f63e-109">**Arbetsorder med projekt (Field Service till Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="7f63e-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="7f63e-110">**Arbetsorder (Field Service till Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="7f63e-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="7f63e-111">Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Finance and Operations innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet.</span><span class="sxs-lookup"><span data-stu-id="7f63e-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="7f63e-112">Dessutom använder mallen avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="7f63e-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7f63e-113">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="7f63e-113">Templates and tasks</span></span>

<span data-ttu-id="7f63e-114">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="7f63e-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="7f63e-115">Arbetsorder med projekt (Field Service till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7f63e-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="7f63e-116">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="7f63e-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="7f63e-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="7f63e-117">WorkOrderHeader</span></span>
- <span data-ttu-id="7f63e-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="7f63e-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="7f63e-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="7f63e-119">WorkOrderProduct</span></span>
- <span data-ttu-id="7f63e-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="7f63e-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="7f63e-121">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="7f63e-121">Field Service CRM solution</span></span>
<span data-ttu-id="7f63e-122">Fältet **Externt projekt** har lagts till entiteten arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="7f63e-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="7f63e-123">Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7f63e-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="7f63e-124">När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="7f63e-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7f63e-125">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="7f63e-125">Template mapping in Data integration</span></span>

<span data-ttu-id="7f63e-126">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="7f63e-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="7f63e-127">Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="7f63e-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="7f63e-128">[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="7f63e-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="7f63e-129">Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="7f63e-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="7f63e-130">[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="7f63e-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="7f63e-131">Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="7f63e-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="7f63e-132">[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="7f63e-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="7f63e-133">Arbetsorder med projekt (Field Service till Fin and Ops): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="7f63e-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="7f63e-134">[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="7f63e-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
