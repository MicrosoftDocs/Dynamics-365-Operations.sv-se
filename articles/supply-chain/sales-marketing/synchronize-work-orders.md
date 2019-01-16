---
title: "Synkronisera arbetsorder från Finance and Operations till Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="0e619-103">Synkronisera arbetsorder med projekt från Field Service till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0e619-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0e619-104">Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera arbetsorder med projektnummer från Microsoft Dynamics 365 for Field Service till Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e619-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0e619-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="0e619-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="0e619-106">Mallen **Field Service-produkter (Finance and Operations till Field Service)** som används baseras på mallen **Produkter (Finance and Operations till Sales) – direkt** från potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="0e619-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="0e619-107">Mer information finns i [Produkter (Finance and Operations till Sales) – direkt](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="0e619-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="0e619-108">Det här ämnet beskriver bara skillnaden mellan mallarna **Field Service-produkter (Finance and Operations till Field Service)** och **Produkter (Finance and Operations till Field Service) – direkt**.</span><span class="sxs-lookup"><span data-stu-id="0e619-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="0e619-109">Den största skillnaden är att den här mallen inkluderar mappning av det projektnummer som tilldelats arbetsordern i Field Service och säkerställer att försäljningsordern från Finance and Operations innehåller projektnumret och att fakturering kan inträffa på det relaterade projektet.</span><span class="sxs-lookup"><span data-stu-id="0e619-109">The main difference is that this template include mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="0e619-110">Dessutom använder mallen avancerad fråga och filtrering.</span><span class="sxs-lookup"><span data-stu-id="0e619-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0e619-111">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="0e619-111">Templates and tasks</span></span>

<span data-ttu-id="0e619-112">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="0e619-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="0e619-113">Arbetsorder med projekt (Field Service till Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="0e619-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="0e619-114">**Namnen på uppgiften i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="0e619-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="0e619-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="0e619-115">WorkOrderHeader</span></span>
- <span data-ttu-id="0e619-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="0e619-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="0e619-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="0e619-117">WorkOrderProduct</span></span>
- <span data-ttu-id="0e619-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="0e619-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="0e619-119">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="0e619-119">Field Service CRM solution</span></span>
<span data-ttu-id="0e619-120">Fältet **Externt projekt** har lagts till entiteten arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="0e619-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="0e619-121">Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e619-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="0e619-122">När **systemstatus** från öppen – pågår (690 970 000) till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="0e619-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0e619-123">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="0e619-123">Template mapping in Data integration</span></span>

<span data-ttu-id="0e619-124">I följande illustrationer visas en mallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="0e619-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="0e619-125">Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="0e619-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="0e619-126">[![Mallmappning i dataintegrering](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="0e619-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="0e619-127">Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="0e619-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="0e619-128">[![Mallmappning i dataintegrering](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="0e619-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="0e619-129">Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="0e619-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="0e619-130">[![Mallmappning i dataintegrering](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="0e619-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="0e619-131">Arbetsorder med projekt (Field Service till Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="0e619-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="0e619-132">[![Mallmappning i dataintegrering](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="0e619-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>

