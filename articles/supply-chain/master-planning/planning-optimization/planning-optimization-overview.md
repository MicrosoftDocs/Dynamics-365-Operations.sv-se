---
title: Rådgivning om optimering – översikt
description: Det här avsnittet innehåller en översikt över funktionen för rådgivning om optimering.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: f88ee8067fdd816ba6890ee28bafe8fa4d3b3ac5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208741"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="76608-103">Rådgivning om optimering – översikt</span><span class="sxs-lookup"><span data-stu-id="76608-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="76608-104">Tillägget planerings optimering för Microsoft Dynamics 365 Supply Chain Management gör det möjligt att utföra en beräkning av huvudplanering utanför Dynamics 365 Supply Chain Management och den relaterade SQL-databasen.</span><span class="sxs-lookup"><span data-stu-id="76608-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="76608-105">De fördelar som är kopplade till funktionerna för planeringsoptimering omfattar förbättrad prestanda och minimal inverkan på SQL-databasen under huvudplaneringskörningen.</span><span class="sxs-lookup"><span data-stu-id="76608-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="76608-106">Snabba planeringskörningar kan göras även under kontorstid, så att planerare omedelbart kan reagera på efterfrågan eller parameterändringar.</span><span class="sxs-lookup"><span data-stu-id="76608-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="76608-107">Om du vill använda planeringsoptimering måste du installera tillägget planeringsoptimering från ditt projekt i Microsoft Dynamics Lifecycle Services (LCS) och aktivera planeringsoptimeringsfunktionen i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76608-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="76608-108">Mer information finns i [komma igång med planeringsoptimering](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="76608-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="76608-109">Följande illustration visar fördelen med att använda planeringsoptimering under kontorstid.</span><span class="sxs-lookup"><span data-stu-id="76608-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Fördelar med att använda planeringsoptimering under kontorstid](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="76608-111">Förbättrad prestanda</span><span class="sxs-lookup"><span data-stu-id="76608-111">Improved performance</span></span>

<span data-ttu-id="76608-112">Planeringsoptimering kan användas i scenarier som innefattar huvudplaner som körs länge.</span><span class="sxs-lookup"><span data-stu-id="76608-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="76608-113">Den är särskilt utformad för mycket snabba beräkningar som innebär mycket stora datavolymer.</span><span class="sxs-lookup"><span data-stu-id="76608-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="76608-114">Eftersom den är byggd som en hyperskalbar tjänst för flera innehavare kan flera instanser samarbeta samtidigt för att beräkna planen.</span><span class="sxs-lookup"><span data-stu-id="76608-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="76608-115">Dessutom tar planeringstjänsten bort belastningen på huvudplaneringen från systemet och fungerar med en dataström som minimerar serverbelastningen.</span><span class="sxs-lookup"><span data-stu-id="76608-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="76608-116">Planeringsoptimeringen hjälper dig att uppnå följande mål:</span><span class="sxs-lookup"><span data-stu-id="76608-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="76608-117">Förbättra planeringsprestandan genom en kortare körningstid.</span><span class="sxs-lookup"><span data-stu-id="76608-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="76608-118">Minska påverkan på andra processer under körningen av huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="76608-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="76608-119">Utför mer frekventa planeringskörningar.</span><span class="sxs-lookup"><span data-stu-id="76608-119">Do more frequent planning runs.</span></span> <span data-ttu-id="76608-120">(Du är inte begränsad till daglig körning.)</span><span class="sxs-lookup"><span data-stu-id="76608-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="76608-121">Var säker på att framtida affärstillväxt inte överbelastar planeringssystemet.</span><span class="sxs-lookup"><span data-stu-id="76608-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="76608-122">Arkitektur och dataflöde</span><span class="sxs-lookup"><span data-stu-id="76608-122">Architecture and data flow</span></span>

<span data-ttu-id="76608-123">När tillägget för planeringsoptimering installeras från LCS, upprättas en säker anslutning till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="76608-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="76608-124">Tjänsten finns i samma datacenterland eller -region som den relaterade instansen för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76608-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="76608-125">När planeringsoptimeringen har ställts in, när huvudplaneringen körs, skickas huvuddata och transaktionsdata från Supply Chain Management till planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="76608-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="76608-126">Om tillägget för planeringsoptimering avinstalleras tas alla relaterade data i planeringsoptimeringstjänsten bort.</span><span class="sxs-lookup"><span data-stu-id="76608-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="76608-127">Dataflöde på hög nivå för återskapande körs</span><span class="sxs-lookup"><span data-stu-id="76608-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="76608-128">Klienten för Supply Chain Management skickar en signal för att begära en planeringskörning från planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="76608-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="76608-129">Planeringsoptimering begär nödvändiga data via den integrerade anslutaren.</span><span class="sxs-lookup"><span data-stu-id="76608-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="76608-130">SQL-databasen skickar den begärda informationen om installations-, huvud- och transaktionsdata för planeringsoptimering via anslutningen.</span><span class="sxs-lookup"><span data-stu-id="76608-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="76608-131">Anslutningen översätter information mellan Supply Chain Management och planeringsoptimeringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="76608-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="76608-132">Planeringsoptimeringstjänsten innehåller planeringsrelaterade data i minnet och de beräkningar som krävs.</span><span class="sxs-lookup"><span data-stu-id="76608-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="76608-133">Planeringsresultatet skickas till Supply Chain Management-databasen via anslutaren.</span><span class="sxs-lookup"><span data-stu-id="76608-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="76608-134">Resultaten innehåller information som t.ex. planerade order och pegging-information.</span><span class="sxs-lookup"><span data-stu-id="76608-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="76608-135">Planeringsoptimering skickar en signal till Supply Chain Management som visar att planeringskörningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="76608-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="76608-136">Alla relevanta meddelanden och varningar skickas också.</span><span class="sxs-lookup"><span data-stu-id="76608-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="76608-137">Illustrationen som följer visar dataflöde.</span><span class="sxs-lookup"><span data-stu-id="76608-137">The following illustration shows the data flow.</span></span>

![Dataflöde för återskapande körs](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="76608-139">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="76608-139">Related resources</span></span>

[<span data-ttu-id="76608-140">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="76608-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="76608-141">Planera analys av optimeringsanpassning</span><span class="sxs-lookup"><span data-stu-id="76608-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="76608-142">Visa planhistorik och planeringsloggar</span><span class="sxs-lookup"><span data-stu-id="76608-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="76608-143">Använda filter på en plan</span><span class="sxs-lookup"><span data-stu-id="76608-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="76608-144">Annullera ett planeringsjobb</span><span class="sxs-lookup"><span data-stu-id="76608-144">Cancel a planning job</span></span>](cancel-planning-job.md)
