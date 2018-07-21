---
title: "Synkronisera projektuppgifter från Project Service Automation"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: sv-se
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="d4fb5-103">Synkronisera projektuppgifter från Project Service Automation direkt till projektaktiviteter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4fb5-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="d4fb5-104">Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="d4fb5-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="d4fb5-106">Dataflöde för Project Service Automation till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4fb5-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="d4fb5-107">Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="d4fb5-108">Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektuppgifter från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="d4fb5-109">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="d4fb5-110">[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="d4fb5-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="d4fb5-111">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="d4fb5-111">Template and task</span></span>

<span data-ttu-id="d4fb5-112">För att få åtkomst till mallen, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="d4fb5-113">Följande mall och underliggande uppgift används för att synkronisera projektuppgifter från Project Service Automation till Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d4fb5-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="d4fb5-114">-**Namnet på mallen för dataintegrering:** projektuppgifter (PSA till Fin and Ops) -**namnet på uppgiften i projektet:** projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="d4fb5-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="d4fb5-115">Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="d4fb5-116">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="d4fb5-116">Entity set</span></span>

|<span data-ttu-id="d4fb5-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d4fb5-117">Project Service Automation</span></span>               | <span data-ttu-id="d4fb5-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4fb5-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="d4fb5-119">Projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="d4fb5-119">Project Tasks</span></span>                           | <span data-ttu-id="d4fb5-120">Integrationsenhet för projektuppgift.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="d4fb5-121">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="d4fb5-121">Entity flow</span></span>

<span data-ttu-id="d4fb5-122">Projektuppgifter hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projektaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="d4fb5-123">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d4fb5-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="d4fb5-124">Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="d4fb5-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="d4fb5-125">Power Query</span></span>

<span data-ttu-id="d4fb5-126">Du måste använda  Microsoft Power Query för att filtrera data om följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="d4fb5-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="d4fb5-127">Du har specifika resursposter inom en projektuppgift.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="d4fb5-128">Om du måste använda Power Query enligt riktlinjerna nedan:</span><span class="sxs-lookup"><span data-stu-id="d4fb5-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="d4fb5-129">Mallen för projektuppgifter (PSA till Fin and Ops) har standardfilter för att utesluta specifika resursposter från inom en projektuppfigt genom att ange filtret i **IsLineTask** till **falsk**.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="d4fb5-130">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d4fb5-131">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="d4fb5-131">Template mapping in Data integration</span></span>

<span data-ttu-id="d4fb5-132">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="d4fb5-133">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4fb5-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="d4fb5-134">[![Mallmappning](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="d4fb5-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


