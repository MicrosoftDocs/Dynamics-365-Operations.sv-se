---
title: Synkronisera projektlista från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/14/2019
ms.locfileid: "842614"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="c5265-103">Synkronisera projektlista från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="c5265-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c5265-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c5265-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c5265-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c5265-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c5265-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="c5265-106">Templates and tasks</span></span>
<span data-ttu-id="c5265-107">Följande mall och underliggande uppgifter används för att köra synkronisering av projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c5265-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c5265-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="c5265-108">**Template in Data integration**</span></span>
- <span data-ttu-id="c5265-109">Projekt (Fin and Ops till Field Service)</span><span class="sxs-lookup"><span data-stu-id="c5265-109">Projects (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="c5265-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="c5265-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="c5265-111">Projekt</span><span class="sxs-lookup"><span data-stu-id="c5265-111">Projects</span></span>

<span data-ttu-id="c5265-112">Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="c5265-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="c5265-113">Konton (Sales till Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="c5265-113">Accounts (Sales to Fin and Ops)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="c5265-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="c5265-114">Entity set</span></span>
| <span data-ttu-id="c5265-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="c5265-115">Field Service</span></span>           | <span data-ttu-id="c5265-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c5265-116">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="c5265-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="c5265-117">msdynce_externalprojects</span></span> | <span data-ttu-id="c5265-118">Projekt</span><span class="sxs-lookup"><span data-stu-id="c5265-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="c5265-119">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="c5265-119">Entity flow</span></span>
<span data-ttu-id="c5265-120">Projekt skapas i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c5265-120">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="c5265-121">Projekt med **projekttyp** inställd på **tid och material** och **projektfas** inställd på **pågår** synkroniseras entiteten **externt projekt** i Field Service annat projektnummer, projektnamn, projektfas och kundkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="c5265-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="c5265-122">Listan över **externt projekt** används för att parkoppla Field Service-arbetsorder med Finance and Operations-projekt.</span><span class="sxs-lookup"><span data-stu-id="c5265-122">The **External Project** list is used to pair Field service work orders with Finance and Operations projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c5265-123">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="c5265-123">Field Service CRM solution</span></span>
<span data-ttu-id="c5265-124">Entitet **Externt projekt** får alla projekt från Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c5265-124">The **External Project** entity gets all the projects from Finance and Operations.</span></span> <span data-ttu-id="c5265-125">Fältet **Externt projekt** har lagts till entiteten **arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="c5265-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="c5265-126">Detta fält är ett uppslagsfält så genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c5265-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Finance and Operations.</span></span> <span data-ttu-id="c5265-127">Efter att **Systemstatus** ändras **Öppna – pågår (690 970 000)** till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="c5265-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="c5265-128">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c5265-128">Prerequisites and mapping setup</span></span>
### <a name="finance-and-operations"></a><span data-ttu-id="c5265-129">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c5265-129">Finance and Operations</span></span>
<span data-ttu-id="c5265-130">Aktivera ändringsspårning för dataentitetsprojekt</span><span class="sxs-lookup"><span data-stu-id="c5265-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c5265-131">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="c5265-131">Template mapping in Data integration</span></span>


### <a name="projects-fin-and-ops-to-field-service-projects"></a><span data-ttu-id="c5265-132">Projekt (Fin and Ops till Field Service): projekt</span><span class="sxs-lookup"><span data-stu-id="c5265-132">Projects (Fin and Ops to Field Service): Projects</span></span>

<span data-ttu-id="c5265-133">[![Mallmappning i dataintegrering](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="c5265-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
