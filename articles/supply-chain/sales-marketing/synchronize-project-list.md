---
title: "Synkronisera projektlista från Finance and Operations till Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
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
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a><span data-ttu-id="3b818-103">Synkronisera projektlista från Finance and Operations till Field Service</span><span class="sxs-lookup"><span data-stu-id="3b818-103">Synchronize project list from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3b818-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="3b818-104">This topic discusses the templates and underlying tasks that are used to synchronize projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="3b818-105">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span><span class="sxs-lookup"><span data-stu-id="3b818-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="3b818-106">Mallar och uppgifter</span><span class="sxs-lookup"><span data-stu-id="3b818-106">Templates and tasks</span></span>
<span data-ttu-id="3b818-107">Följande mall och underliggande uppgifter används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="3b818-107">The following template and underlying tasks are used to run synchronization of projects from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="3b818-108">**Namnet på mallen i dataintegreringen**</span><span class="sxs-lookup"><span data-stu-id="3b818-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="3b818-109">Projekt (Finance and Operations till Field Service)</span><span class="sxs-lookup"><span data-stu-id="3b818-109">Projects (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="3b818-110">**Namnen på uppgifterna i dataintegreringsprojektet:**</span><span class="sxs-lookup"><span data-stu-id="3b818-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="3b818-111">Projekt</span><span class="sxs-lookup"><span data-stu-id="3b818-111">Projects</span></span>

<span data-ttu-id="3b818-112">Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:</span><span class="sxs-lookup"><span data-stu-id="3b818-112">The following synchronization tasks are required before synchronization of project list can occur:</span></span>
- <span data-ttu-id="3b818-113">Konton (Sales till Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="3b818-113">Accounts (Sales to Finance and Operations)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="3b818-114">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="3b818-114">Entity set</span></span>
<span data-ttu-id="3b818-115">Field Service   Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b818-115">Field Service   Finance and Operations</span></span>

| <span data-ttu-id="3b818-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="3b818-116">Field Service</span></span>           | <span data-ttu-id="3b818-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b818-117">Finance and Operations</span></span>  |
|-------------------------|-------------------------|
|<span data-ttu-id="3b818-118">msdynce_externalprojects</span><span class="sxs-lookup"><span data-stu-id="3b818-118">msdynce_externalprojects</span></span> | <span data-ttu-id="3b818-119">Projekt</span><span class="sxs-lookup"><span data-stu-id="3b818-119">Projects</span></span>                |

## <a name="entity-flow"></a><span data-ttu-id="3b818-120">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="3b818-120">Entity flow</span></span>
<span data-ttu-id="3b818-121">Projekt skapas i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b818-121">Projects are created in Finance and Operations.</span></span> <span data-ttu-id="3b818-122">Projekt med **projekttypen** tid och material och **projektfas** pågår synkroniseras till entiteten **externt projekt** i Field Service, bland annat projektnummer, projektnamn, projektfas och kundkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="3b818-122">Projects with **Project type** Time and material and **Project stage** In process will synchronize to the **External Project** entity in Field Service, including Project number, Project name, Project stage and Customer account information.</span></span> <span data-ttu-id="3b818-123">Listan över **externt projekt** används för att parkoppla Field service-arbetsorder med Finance and Operations-projekt.</span><span class="sxs-lookup"><span data-stu-id="3b818-123">The list of **External Project** is used to pair Field service Work orders with Finance and Operations projects.</span></span>
<span data-ttu-id="3b818-124">CRM-lösning för Field Service, Externt projekt är en ny entitet som hämtar alla projekt från Operations.</span><span class="sxs-lookup"><span data-stu-id="3b818-124">Field Service CRM solution The External Project is a new entity that gets all the Projects from Operations.</span></span>
<span data-ttu-id="3b818-125">Fältet Externt projekt har lagts till entiteten arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3b818-125">The External Project field has been added to the Work Order entity.</span></span> <span data-ttu-id="3b818-126">Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Operations.</span><span class="sxs-lookup"><span data-stu-id="3b818-126">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Operations.</span></span> <span data-ttu-id="3b818-127">När systemstatus ändras, öppen – pågår (690 970 000) till en högre status kommer fältet Externt projekt att låsas och du kan inte lägga till, ta bort eller ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="3b818-127">Ones the System Status changes Open – In Progress(690,970,000) to a higher status the External Project field will be locked and you can't add, remove or change the value.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="3b818-128">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="3b818-128">Prerequisites and mapping setup</span></span>
### <a name="in-finance-and-operations"></a><span data-ttu-id="3b818-129">I Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3b818-129">In Finance and Operations</span></span>
<span data-ttu-id="3b818-130">Aktivera ändringsspårning för dataentitetsprojekt</span><span class="sxs-lookup"><span data-stu-id="3b818-130">Enable change tracking for Data entity Projects</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="3b818-131">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="3b818-131">Template mapping in Data integration</span></span>


### <a name="projects-finance-and-operations-to-field-service-projects"></a><span data-ttu-id="3b818-132">Projekt (Finance and Operations till Field Service): projekt</span><span class="sxs-lookup"><span data-stu-id="3b818-132">Projects (Finance and Operations to Field Service): Projects</span></span>

<span data-ttu-id="3b818-133">[![Mallmappning i dataintegrering](./media/FSProject1.png)](./media/FSProject1.png)</span><span class="sxs-lookup"><span data-stu-id="3b818-133">[![Template mapping in Data integration](./media/FSProject1.png)](./media/FSProject1.png)</span></span>

