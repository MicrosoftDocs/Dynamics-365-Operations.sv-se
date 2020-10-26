---
title: Batchorderlivscykel för början till start
description: I den här proceduren får du hjälp med den första delen av livscykeln för en batchorder.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e57cd9254185b73f544e8ff4f7658cf743b672f2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981314"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="024f0-103">Batchorderlivscykel för början till start</span><span class="sxs-lookup"><span data-stu-id="024f0-103">Batch order lifecycle from create to start</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="024f0-104">I den här proceduren får du hjälp med den första delen av livscykeln för en batchorder.</span><span class="sxs-lookup"><span data-stu-id="024f0-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="024f0-105">Från skapande, kostnadsberäkning och över produktionsjobb tidsplanering till den verkliga början av en batchorder.</span><span class="sxs-lookup"><span data-stu-id="024f0-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="024f0-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="024f0-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="024f0-107">Följande förutsättningar gäller för körning av proceduren med en annan datauppsättning är en frisläppt produkt med aktiv formel och flödesversion.</span><span class="sxs-lookup"><span data-stu-id="024f0-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="024f0-108">Skapa en batchorder</span><span class="sxs-lookup"><span data-stu-id="024f0-108">Create a batch order</span></span>
1. <span data-ttu-id="024f0-109">Gå till Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="024f0-109">Go to All production orders.</span></span>
2. <span data-ttu-id="024f0-110">Klicka på Ny batchorder.</span><span class="sxs-lookup"><span data-stu-id="024f0-110">Click New batch order.</span></span>
3. <span data-ttu-id="024f0-111">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="024f0-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="024f0-112">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="024f0-112">Click Create.</span></span>
5. <span data-ttu-id="024f0-113">Använd snabbfiltret för att filtrera på fältet Produktion med värdet ”b”.</span><span class="sxs-lookup"><span data-stu-id="024f0-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="024f0-114">Visa produktionsformeln och förväntade samprodukter</span><span class="sxs-lookup"><span data-stu-id="024f0-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="024f0-115">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="024f0-116">Klicka på Recept.</span><span class="sxs-lookup"><span data-stu-id="024f0-116">Click Formula.</span></span>
3. <span data-ttu-id="024f0-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-117">Close the page.</span></span>
4. <span data-ttu-id="024f0-118">Klicka på Samprodukter.</span><span class="sxs-lookup"><span data-stu-id="024f0-118">Click Co-products.</span></span>
5. <span data-ttu-id="024f0-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="024f0-120">Uppskatta batchordern</span><span class="sxs-lookup"><span data-stu-id="024f0-120">Estimate the batch order</span></span>
1. <span data-ttu-id="024f0-121">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="024f0-121">Click Estimate.</span></span>
2. <span data-ttu-id="024f0-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="024f0-122">Click OK.</span></span>
3. <span data-ttu-id="024f0-123">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="024f0-124">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="024f0-124">Click View calculation details.</span></span>
5. <span data-ttu-id="024f0-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="024f0-126">Frisläpp batchordern</span><span class="sxs-lookup"><span data-stu-id="024f0-126">Release the batch order</span></span>
1. <span data-ttu-id="024f0-127">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="024f0-128">Klicka på Frisläpp.</span><span class="sxs-lookup"><span data-stu-id="024f0-128">Click Release.</span></span>
3. <span data-ttu-id="024f0-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="024f0-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="024f0-130">Schemalägg produktionsjobb</span><span class="sxs-lookup"><span data-stu-id="024f0-130">Schedule production jobs</span></span>
1. <span data-ttu-id="024f0-131">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="024f0-132">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="024f0-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="024f0-133">Välj Nej i fältet Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="024f0-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="024f0-134">Välj Nej i fältet Begränsat material.</span><span class="sxs-lookup"><span data-stu-id="024f0-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="024f0-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="024f0-135">Click OK.</span></span>
6. <span data-ttu-id="024f0-136">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="024f0-137">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="024f0-137">Click All jobs.</span></span>
8. <span data-ttu-id="024f0-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="024f0-139">Starta batchordern</span><span class="sxs-lookup"><span data-stu-id="024f0-139">Start the batch order</span></span>
1. <span data-ttu-id="024f0-140">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="024f0-140">Click Start.</span></span>
2. <span data-ttu-id="024f0-141">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="024f0-141">Click the General tab.</span></span>
3. <span data-ttu-id="024f0-142">Välj Nej i fältet Bokför plocklista nu.</span><span class="sxs-lookup"><span data-stu-id="024f0-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="024f0-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="024f0-143">Click OK.</span></span>
5. <span data-ttu-id="024f0-144">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="024f0-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="024f0-145">Klicka på Plocklista.</span><span class="sxs-lookup"><span data-stu-id="024f0-145">Click Picking list.</span></span>
7. <span data-ttu-id="024f0-146">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="024f0-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="024f0-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-147">Close the page.</span></span>
9. <span data-ttu-id="024f0-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-148">Close the page.</span></span>
10. <span data-ttu-id="024f0-149">Klicka på Flödeskort.</span><span class="sxs-lookup"><span data-stu-id="024f0-149">Click Route card.</span></span>
11. <span data-ttu-id="024f0-150">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="024f0-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="024f0-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-151">Close the page.</span></span>
13. <span data-ttu-id="024f0-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="024f0-152">Close the page.</span></span>

