---
title: Planera laster och utleveranser med workbench för lastplanering
description: I den här proceduren visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "343913"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="143af-103">Planera laster och utleveranser med workbench för lastplanering</span><span class="sxs-lookup"><span data-stu-id="143af-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="143af-104">I den här proceduren visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="143af-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="143af-105">Som en förutsättning skapar vi försäljningsordern först.</span><span class="sxs-lookup"><span data-stu-id="143af-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="143af-106">Den här proceduren utgör en del av det dagliga arbetet för transportkoordinatorn.</span><span class="sxs-lookup"><span data-stu-id="143af-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="143af-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="143af-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="143af-108">Skapa en försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="143af-108">Create a sales order</span></span>
1. <span data-ttu-id="143af-109">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="143af-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="143af-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="143af-110">Click New.</span></span>
3. <span data-ttu-id="143af-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="143af-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="143af-112">Välj kontot US-004.</span><span class="sxs-lookup"><span data-stu-id="143af-112">Select account US-004.</span></span>
5. <span data-ttu-id="143af-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="143af-113">Click OK.</span></span>
6. <span data-ttu-id="143af-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="143af-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="143af-115">Välj artikel A0001.</span><span class="sxs-lookup"><span data-stu-id="143af-115">Select item A0001.</span></span>
    * <span data-ttu-id="143af-116">A0001 har aktiverats för transporthantering.</span><span class="sxs-lookup"><span data-stu-id="143af-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="143af-117">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="143af-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="143af-118">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="143af-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="143af-119">Skriv "24" i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="143af-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="143af-120">Välj lagerställe 24 i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="143af-120">In this example select warehouse 24.</span></span> <span data-ttu-id="143af-121">Lagerstället aktiveras för transportledning och avancerad lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="143af-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="143af-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="143af-122">Click Save.</span></span>
12. <span data-ttu-id="143af-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="143af-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="143af-124">Skapa en ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="143af-124">Create a new load</span></span>
1. <span data-ttu-id="143af-125">Gå till Transporthantering > Planering > Workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="143af-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="143af-126">Klicka på fliken Försäljningsrader.</span><span class="sxs-lookup"><span data-stu-id="143af-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="143af-127">Nu skapar du beläggningen för den försäljningsorder som du precis skapade.</span><span class="sxs-lookup"><span data-stu-id="143af-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="143af-128">Beläggningar kan skapas med utgångspunkt i tillgång och efterfrågan från inköpsorder, överföringsorder och försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="143af-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="143af-129">Klicka på Tillgång och efterfrågan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="143af-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="143af-130">Klicka på Till ny beläggning.</span><span class="sxs-lookup"><span data-stu-id="143af-130">Click To new load.</span></span>
5. <span data-ttu-id="143af-131">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Beläggningsmall-ID.</span><span class="sxs-lookup"><span data-stu-id="143af-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="143af-132">Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen.</span><span class="sxs-lookup"><span data-stu-id="143af-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="143af-133">Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil.</span><span class="sxs-lookup"><span data-stu-id="143af-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="143af-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="143af-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="143af-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="143af-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="143af-136">Tariff och rutt för beläggningen</span><span class="sxs-lookup"><span data-stu-id="143af-136">Rate and route the load</span></span>
1. <span data-ttu-id="143af-137">Klicka på Värdering och rutt.</span><span class="sxs-lookup"><span data-stu-id="143af-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="143af-138">Klicka på Ruttworkbench för tariff.</span><span class="sxs-lookup"><span data-stu-id="143af-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="143af-139">Klicka på Tariffbutik.</span><span class="sxs-lookup"><span data-stu-id="143af-139">Click Rate shop.</span></span>
4. <span data-ttu-id="143af-140">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="143af-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="143af-141">Klicka på Tilldela.</span><span class="sxs-lookup"><span data-stu-id="143af-141">Click Assign.</span></span>
6. <span data-ttu-id="143af-142">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="143af-142">Close the page.</span></span>
7. <span data-ttu-id="143af-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="143af-143">Close the page.</span></span>

