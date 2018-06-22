---
title: Project Service Automation
description: "Den här lösningen använder funktionen Dataintegrering för att synkronisera data över instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="c9a90-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="c9a90-103">Project Service Automation</span></span>

<span data-ttu-id="c9a90-104">Integrationslösningen Project Service Automation till Finance and Operations använder funktionen Dataintegrering för att synkronisera data över instanser av Microsoft Dynamics 365 for Finance and Operations och Microsoft Dynamics 365 for Project Service Automation via Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="c9a90-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="c9a90-105">Aktivera integrationsmallarna som medföljer dataintegrationsfunktionen för att tillåta flöde av projekt, projektkontrakt, projektkontraktsrader, projektkontraktraders milstolpar, projektaktiviteter, utgiftstransaktionskategorier, timuppskattningar, och utgiftsuppskattningar från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="c9a90-106">Om du använder Dynamics 365 for Finance and Operations, Enterprise Edition, 7.3.0, måste du installera KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="c9a90-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="c9a90-107">Detta gör att du kan integrera fastprisprojekt.</span><span class="sxs-lookup"><span data-stu-id="c9a90-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="c9a90-108">Om du använder Dynamics 365 for Finance and Operations version 8.0 kommer du att kunna använda projektets uppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattningar av utgift och funktionslåsning.</span><span class="sxs-lookup"><span data-stu-id="c9a90-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="c9a90-109">Om du använder Dynamics 365 for Finance and Operations version 8.0.1 kan du synkronisera verkliga värden.</span><span class="sxs-lookup"><span data-stu-id="c9a90-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="c9a90-110">Om du använder Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning.</span><span class="sxs-lookup"><span data-stu-id="c9a90-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="c9a90-111">Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="c9a90-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="c9a90-112">Innan du kan integrera Project Service Automation med Finance and Operations måste du konfigurera integrationsparametrar för Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="c9a90-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="c9a90-113">Mer information finns i integrationsparametrar för Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="c9a90-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="c9a90-114">Den här integrationslösningen möjliggör direkt synkronisering i följande scenarion:</span><span class="sxs-lookup"><span data-stu-id="c9a90-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="c9a90-115">Underhåll projektkontrakt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-116">Skapa projekt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-117">Underhåll projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-118">Underhåll milstolpar för projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-119">Underhåll projektuppgifter i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-120">Underhåll utgiftstransationskategorier i Finance and Operations och synkronisera dem direkt från Finance and Operations till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="c9a90-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="c9a90-121">Skapa timuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c9a90-122">Skapa utgiftsuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="c9a90-123">Datasynkronisering</span><span class="sxs-lookup"><span data-stu-id="c9a90-123">Data synchronization</span></span>
<span data-ttu-id="c9a90-124">Följande bild visar hur data synkroniseras som en del av integreringen mellan Project Service Automation och Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="c9a90-125">Alla mallar är för närvarande inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="c9a90-125">Not all templates are currently available.</span></span> <span data-ttu-id="c9a90-126">Mallarna kommer att frisläppas när de slutförs.</span><span class="sxs-lookup"><span data-stu-id="c9a90-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="c9a90-127">[![Project Service Automation med Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="c9a90-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="c9a90-128">Systemkrav för Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c9a90-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="c9a90-129">Du måste installera Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 med plattformsuppdateringen 12 eller senare för att kunna använda integrationslösningen Project Service Automation till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c9a90-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="c9a90-130">Systemkrav för Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="c9a90-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="c9a90-131">Om du vill använda integrationslösningen för Project Service Automation till Finance and Operations måste du installera följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="c9a90-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="c9a90-132">Microsoft Dynamics 365 för Project Service Automation version 9.0.0.0 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c9a90-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="c9a90-133">Lösningen Potentiell kund till kontanter för Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.</span><span class="sxs-lookup"><span data-stu-id="c9a90-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="c9a90-134">Lösningen Project Service Automation till Operations för Dynamics 365 for Project Service Automation version 1.0.0.0 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c9a90-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="c9a90-135">Installera Project Service Automation till Finance and Operations i din Project Service Automation-instans</span><span class="sxs-lookup"><span data-stu-id="c9a90-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



