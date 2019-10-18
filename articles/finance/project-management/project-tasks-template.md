---
title: Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Microsoft Dynamics 365 Project Service Automation till Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 977037f0e2b313ebf05a3e1616d34567f82e82d7
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250402"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="1b0e8-103">Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1b0e8-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1b0e8-104">Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektuppgifter direkt från Dynamics 365 Project Service Automation till Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="1b0e8-105">Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i version 8.0.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="1b0e8-106">Om du använder Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="1b0e8-107">Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="1b0e8-108">Integrering av faktiska uppgifter finns i version 8.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="1b0e8-109">Dataflöde för Project Service Automation till Finance</span><span class="sxs-lookup"><span data-stu-id="1b0e8-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="1b0e8-110">Automatisering av integrationslösningen Project Service Automation till Finance-integrationslösningen använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="1b0e8-111">Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektuppgifter från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="1b0e8-112">Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="1b0e8-113">[![Dataflöde för integration av Project Service Automation med Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="1b0e8-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="1b0e8-114">Mall och uppgift</span><span class="sxs-lookup"><span data-stu-id="1b0e8-114">Template and task</span></span>

<span data-ttu-id="1b0e8-115">För att få åtkomst till mallen väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-115">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="1b0e8-116">Följande mall och underliggande uppgift används för att synkronisera projektuppgifter från Project Service Automation till Finance:</span><span class="sxs-lookup"><span data-stu-id="1b0e8-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="1b0e8-117">**Namn på mallen i dataintegrering:** Projektuppgifter ("PSA till Fin och Ops")</span><span class="sxs-lookup"><span data-stu-id="1b0e8-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="1b0e8-118">**Namn på uppgiften i projektet:** Projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="1b0e8-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="1b0e8-119">Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="1b0e8-120">Ange entiteten</span><span class="sxs-lookup"><span data-stu-id="1b0e8-120">Entity set</span></span>

| <span data-ttu-id="1b0e8-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="1b0e8-121">Project Service Automation</span></span> | <span data-ttu-id="1b0e8-122">Finansiellt</span><span class="sxs-lookup"><span data-stu-id="1b0e8-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="1b0e8-123">Projektuppgifter</span><span class="sxs-lookup"><span data-stu-id="1b0e8-123">Project Tasks</span></span>              | <span data-ttu-id="1b0e8-124">Integrationsenhet för projektuppgift</span><span class="sxs-lookup"><span data-stu-id="1b0e8-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="1b0e8-125">Flöde för entitet</span><span class="sxs-lookup"><span data-stu-id="1b0e8-125">Entity flow</span></span>

<span data-ttu-id="1b0e8-126">Projektuppgifter hanteras i Project Service Automation och de synkroniseras till Finance som projektaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="1b0e8-127">Ställa in mappning och förutsättningar</span><span class="sxs-lookup"><span data-stu-id="1b0e8-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="1b0e8-128">Innan synkroniseringen av projektuppgifter kan utföras måste du synkronisera projektkontrakt och projekt.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="1b0e8-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="1b0e8-129">Power Query</span></span>

<span data-ttu-id="1b0e8-130">Du måste använda Microsoft Power Query för Excel för att filtrera data om följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="1b0e8-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="1b0e8-131">Du har resursspecifika poster i en projektuppgift.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="1b0e8-132">Om du måste använda Power Query, följ då dessa riktlinjer:</span><span class="sxs-lookup"><span data-stu-id="1b0e8-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="1b0e8-133">Mallen för projektuppgifter ("PSA till Fin och Ops") har ett standardfilter som exkluderar resursspecifika poster från en projektuppgift genom att ange filtret i **IsLineTask** som **False**.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="1b0e8-134">Om du skapar en egen mall måste du lägga till filtret.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="1b0e8-135">Mallmappning i dataintegrering</span><span class="sxs-lookup"><span data-stu-id="1b0e8-135">Template mapping in Data integration</span></span>

<span data-ttu-id="1b0e8-136">I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="1b0e8-137">Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="1b0e8-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="1b0e8-138">[![Mallmappning](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="1b0e8-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
