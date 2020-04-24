---
title: Synkronisera projektlista från Supply Chain Management till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: d80fce409ee92973a6134d96ce839b9722980918
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215940"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a><span data-ttu-id="8936f-103">Synkronisera projektlista från Supply Chain Management till Field Service</span><span class="sxs-lookup"><span data-stu-id="8936f-103">Synchronize project list from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8936f-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="8936f-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="8936f-105">[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="8936f-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="8936f-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="8936f-106">Templates and tasks</span></span>
<span data-ttu-id="8936f-107">Följande mall och underliggande uppgifter används för att köra synkronisering av projekt från Supply Chain Management till Field Service.</span><span class="sxs-lookup"><span data-stu-id="8936f-107">The following template and underlying tasks are used to run synchronization of projects from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="8936f-108">**Mall i dataintegrering**</span><span class="sxs-lookup"><span data-stu-id="8936f-108">**Template in Data integration**</span></span>
- <span data-ttu-id="8936f-109">Projekt (Supply Chain Management till Field Service)</span><span class="sxs-lookup"><span data-stu-id="8936f-109">Projects (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="8936f-110">**Uppgift i dataintegreringsprojektet**</span><span class="sxs-lookup"><span data-stu-id="8936f-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="8936f-111">Projekt</span><span class="sxs-lookup"><span data-stu-id="8936f-111">Projects</span></span>

<span data-ttu-id="8936f-112">Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="8936f-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="8936f-113">Konton (Sales till Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="8936f-113">Accounts (Sales to Supply Chain Management)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="8936f-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="8936f-114">Entity set</span></span>
| <span data-ttu-id="8936f-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="8936f-115">Field Service</span></span>           | <span data-ttu-id="8936f-116">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="8936f-116">Supply Chain Management</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="8936f-117">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="8936f-117">msdynce_externalprojects</span></span> | <span data-ttu-id="8936f-118">Projekt</span><span class="sxs-lookup"><span data-stu-id="8936f-118">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="8936f-119">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="8936f-119">Entity flow</span></span>
<span data-ttu-id="8936f-120">Projekt skapas i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8936f-120">Projects are created in Supply Chain Management.</span></span> <span data-ttu-id="8936f-121">Projekt med **projekttyp** inställd på **tid och material** och **projektfas** inställd på **pågår** synkroniseras entiteten **externt projekt** i Field Service annat projektnummer, projektnamn, projektfas och kundkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="8936f-121">Projects with **Project type** set to **Time and material** and **Project stage** set to **In process** will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage, and Customer account information.</span></span> <span data-ttu-id="8936f-122">Listan över **externt projekt** används för att parkoppla Field Service-arbetsorder med Supply Chain Management-projekt.</span><span class="sxs-lookup"><span data-stu-id="8936f-122">The **External Project** list is used to pair Field service work orders with Supply Chain Management projects.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="8936f-123">CRM-lösning för Field Service</span><span class="sxs-lookup"><span data-stu-id="8936f-123">Field Service CRM solution</span></span>
<span data-ttu-id="8936f-124">Entitet **Externt projekt** får alla projekt från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8936f-124">The **External Project** entity gets all the projects from Supply Chain Management.</span></span> <span data-ttu-id="8936f-125">Fältet **Externt projekt** har lagts till entiteten **arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="8936f-125">The **External Project** field has been added to the **Work Order** entity.</span></span> <span data-ttu-id="8936f-126">Detta fält är ett uppslagsfält så genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8936f-126">This is a lookup field, so by tagging your work order with a project, the sales order will be connected to a project within Supply Chain Management.</span></span> <span data-ttu-id="8936f-127">Efter att **Systemstatus** ändras **Öppna – pågår (690 970 000)** till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="8936f-127">After the **System Status** changes **Open – In Progress(690,970,000)** to a higher status, the **External Project** field will be locked and you can no longer add, remove, or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="8936f-128">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="8936f-128">Prerequisites and mapping setup</span></span>
### <a name="supply-chain-management"></a><span data-ttu-id="8936f-129">Hantering av underleverantörer</span><span class="sxs-lookup"><span data-stu-id="8936f-129">Supply Chain Management</span></span>
<span data-ttu-id="8936f-130">Aktivera ändringsspårning för dataentitetsprojekt</span><span class="sxs-lookup"><span data-stu-id="8936f-130">Enable change tracking for Data entity projects.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="8936f-131">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="8936f-131">Template mapping in Data integration</span></span>


### <a name="projects-supply-chain-management-to-field-service-projects"></a><span data-ttu-id="8936f-132">Projekt (Supply Chain Management till Field Service): projekt</span><span class="sxs-lookup"><span data-stu-id="8936f-132">Projects (Supply Chain Management to Field Service): Projects</span></span>

<span data-ttu-id="8936f-133">[![Mallmappning i dataintegrering](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="8936f-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>
