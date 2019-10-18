---
title: Översikt över Project Service Automation
description: Det här ämnet innehåller information om Dynamics 365 Project Service Automation till Dynamics 365 Finance integrationslösning.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250563"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="b6ec5-103">Översikt över Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="b6ec5-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b6ec5-104">Project Service Automation till Finance integreringslösning använder funktionen för dataintegrering för att synkronisera data mellan instanser av Dynamics 365 Finance och Dynamics 365 Project Service Automation via Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="b6ec5-105">De integrationsmallar som medföljer dataintegrationsfunktionen gör et möjligt att aktiver flödet av projekt, projektkontrakt, projektkontraktsrader, projektkontraktraders milstolpar, projektaktiviteter, utgiftstransaktionskategorier, timuppskattningar och utgiftsuppskattningar från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="b6ec5-106">Om du använder version 7.3.0, måste du installera KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="b6ec5-107">Du kan sedan integrera fastprisprojekt.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="b6ec5-108">Om du använder version 7.3.0 och överför avgiftstransaktioner från Project Service Automation måste du installera KB 4345320 för att inkludera dessa avgifter på projektfakturan.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="b6ec5-109">Om du använder version 8.0, kommer du att kunna använda projektets uppgiftsintegration, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och funktionslåsning.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="b6ec5-110">Om du använder version 8.0.1, eller senare kommer du att kunna synkronisera faktiska värden.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="b6ec5-111">Innan du kan integrera Project Service Automation med Finance måste du konfigurera integrationsparametrar för Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="b6ec5-112">Mer information finns i [Integreringsparametrar för Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b6ec5-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="b6ec5-113">Den här integrationslösningen möjliggör direkt synkronisering i följande scenarion:</span><span class="sxs-lookup"><span data-stu-id="b6ec5-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="b6ec5-114">Underhåll projektkontrakt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-115">Skapa projekt i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-116">Underhåll projektkontraktrader i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-117">Underhåll milstolpar för projektkontraktsrad i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-118">Underhåll projektuppgifter i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-119">Underhåll utgiftstransationskategorier i Finance och synkronisera dem direkt från Finance till Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="b6ec5-120">Skapa timuppskattningar för projektet i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-121">Skapa projektets utgiftsupppskattningar i Project Service Automation och synkronisera dem direkt från Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="b6ec5-122">Skapa tid, utgift och verkliga avgiftsvärden för projekt i Project Service Automation och skapa projekttransaktioner i integreringsjournalen för Project Service Automation så att de kan bokföras i Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="b6ec5-123">Datasynkronisering</span><span class="sxs-lookup"><span data-stu-id="b6ec5-123">Data synchronization</span></span>

<span data-ttu-id="b6ec5-124">Följande bild visar hur data synkroniseras som en del av integreringen mellan Project Service Automation och Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ec5-125">Alla mallar är för närvarande inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-125">Not all templates are currently available.</span></span> <span data-ttu-id="b6ec5-126">Mallarna kommer att frisläppas när de slutförs.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="b6ec5-127">[![Project Service Automation-integration med Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="b6ec5-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="b6ec5-128">Systemkrav för Finance</span><span class="sxs-lookup"><span data-stu-id="b6ec5-128">System requirements for Finance</span></span>

<span data-ttu-id="b6ec5-129">Du måste installera, Enterprise edition 7.3 med plattformsuppdateringen 12 eller senare för att kunna använda integrationslösningen Project Service Automation till Finance.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="b6ec5-130">Systemkrav för Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="b6ec5-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="b6ec5-131">Om du vill använda integrationslösningen för Project Service Automation till Finance måste du installera följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="b6ec5-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="b6ec5-132">Dynamics 365 Project Service Automation version 9.0.0.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="b6ec5-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="b6ec5-133">Lösningen Potentiell kund till kontanter för Dynamics 365 Sales, version 1.14.0.0 (v14) eller senare.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="b6ec5-134">Lösning för Project Service Automation till Finance för Dynamics 365 Project Service Automation version 1.0.0.0 or later</span><span class="sxs-lookup"><span data-stu-id="b6ec5-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="b6ec5-135">Installera Project Service Automation till Finance i din Project Service Automation-instans</span><span class="sxs-lookup"><span data-stu-id="b6ec5-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="b6ec5-136">Hämta integreringslösningen Project Service Automation till Finance från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016) och följ de instruktioner som medföljer lösningen.</span><span class="sxs-lookup"><span data-stu-id="b6ec5-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
