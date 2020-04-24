---
title: Tidsplanera en produktionsorder
description: I den här proceduren visas hur du tidsplanerar en produktionsorder.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: daaf7a593f8ae5185333c33b9e475dfd62358eb8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210443"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="0602e-103">Tidsplanera en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="0602e-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0602e-104">I den här proceduren visas hur du tidsplanerar en produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="0602e-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="0602e-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="0602e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0602e-106">Detta är den tredje proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="0602e-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="0602e-107">Tidsplanera en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="0602e-107">Schedule a production order</span></span>
1. <span data-ttu-id="0602e-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="0602e-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="0602e-109">Välj en produktionsorder som har statusen Uppskattad.</span><span class="sxs-lookup"><span data-stu-id="0602e-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="0602e-110">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0602e-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="0602e-111">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="0602e-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="0602e-112">Parametrarna för schemaläggning ställs in på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="0602e-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="0602e-113">Du kan ställa in parametrarna för vissa användare eller alla användare.</span><span class="sxs-lookup"><span data-stu-id="0602e-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="0602e-114">Välj Framåt från idag i fältet Planeringsriktning.</span><span class="sxs-lookup"><span data-stu-id="0602e-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="0602e-115">Ange ett datum i fältet Planeringsdatum.</span><span class="sxs-lookup"><span data-stu-id="0602e-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="0602e-116">Markera eller avmarkera kryssrutan Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="0602e-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="0602e-117">Markera eller avmarkera kryssrutan Begränsat material.</span><span class="sxs-lookup"><span data-stu-id="0602e-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="0602e-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0602e-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="0602e-119">Visa resultaten av tidsplaneringen</span><span class="sxs-lookup"><span data-stu-id="0602e-119">View the scheduling results</span></span>
1. <span data-ttu-id="0602e-120">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0602e-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="0602e-121">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="0602e-121">Click All jobs.</span></span>
    * <span data-ttu-id="0602e-122">På den här sidan visas schemalagda jobb som du precis har genererat.</span><span class="sxs-lookup"><span data-stu-id="0602e-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="0602e-123">Utöka eller komprimera avsnittet Tidsplanering.</span><span class="sxs-lookup"><span data-stu-id="0602e-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="0602e-124">På snabbfliken Tidsplanering kan du visa det schemalagda datumet och tiden.</span><span class="sxs-lookup"><span data-stu-id="0602e-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="0602e-125">Klicka på Förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="0602e-125">Click Inquiries.</span></span>
5. <span data-ttu-id="0602e-126">Klicka på Kapacitetsbeläggning.</span><span class="sxs-lookup"><span data-stu-id="0602e-126">Click Capacity load.</span></span>
    * <span data-ttu-id="0602e-127">Sidan Kapacitetsbeläggning visar den kapacitet som reserverats genom finplanering, det totala antalet timmar som är reserverat för närvarande för resursen och antalet timmar som återstår för finplanering för resursen.</span><span class="sxs-lookup"><span data-stu-id="0602e-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="0602e-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0602e-128">Close the page.</span></span>
7. <span data-ttu-id="0602e-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0602e-129">Close the page.</span></span>

