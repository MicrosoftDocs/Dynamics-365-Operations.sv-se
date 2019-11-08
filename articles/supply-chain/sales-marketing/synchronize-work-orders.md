---
title: Synkronisera arbetsorder med projekt från Field Service till Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Dynamics 365 Field Service till Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 5c57b8d1e09fd57611accec83ec3da4bc596fd00
ms.sourcegitcommit: 4d6ec2b1a9674712e1efb8c46b919d554f21a2b3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2019
ms.locfileid: "2627561"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="c3744-103">Synkronisera arbetsorder med projekt från Field Service till Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c3744-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c3744-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder med projektnummer från Dynamics 365 Field Service till Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3744-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c3744-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c3744-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="c3744-106">Den använda mallen **Arbetsorder med projekt (Field Service till Supply Chain Management)** som används baseras på mallen **Arbetsorder (Field Service till Supply Chain Management)**.</span><span class="sxs-lookup"><span data-stu-id="c3744-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="c3744-107">Mer information finns i [Synkronisera arbetsorder i Field Service till försäljningsorder i Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="c3744-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="c3744-108">Det här avsnittet beskriver endast skillnaderna mellan två mallar:</span><span class="sxs-lookup"><span data-stu-id="c3744-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="c3744-109">**Arbetsorder med projekt (Field Service till Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="c3744-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="c3744-110">**Arbetsorder med projekt (Field Service till Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="c3744-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="c3744-111">Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Supply Chain Management innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet.</span><span class="sxs-lookup"><span data-stu-id="c3744-111">The main difference is that this template includes mapping of the project number assigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="c3744-112">Dessutom använder mallen avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="c3744-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c3744-113">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="c3744-113">Templates and tasks</span></span>

<span data-ttu-id="c3744-114">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="c3744-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c3744-115">Arbetsorder med projekt (Field Service till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="c3744-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="c3744-116">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="c3744-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c3744-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c3744-117">WorkOrderHeader</span></span>
- <span data-ttu-id="c3744-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c3744-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="c3744-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c3744-119">WorkOrderProduct</span></span>
- <span data-ttu-id="c3744-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c3744-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c3744-121">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="c3744-121">Field Service CRM solution</span></span>
<span data-ttu-id="c3744-122">Fältet **Externt projekt** har lagts till entiteten arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="c3744-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="c3744-123">Detta fält är ett uppslagsfält och genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3744-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="c3744-124">När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="c3744-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c3744-125">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="c3744-125">Template mapping in Data integration</span></span>

<span data-ttu-id="c3744-126">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="c3744-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="c3744-127">Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c3744-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="c3744-128">[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="c3744-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="c3744-129">Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c3744-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="c3744-130">[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="c3744-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="c3744-131">Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c3744-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="c3744-132">[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="c3744-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="c3744-133">Arbetsorder med projekt (Field Service till Supply Chain Management): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c3744-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="c3744-134">[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="c3744-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
