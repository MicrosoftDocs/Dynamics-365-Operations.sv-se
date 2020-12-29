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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437399"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="42d37-103">Batchorderlivscykel för början till start</span><span class="sxs-lookup"><span data-stu-id="42d37-103">Batch order lifecycle from create to start</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42d37-104">I den här proceduren får du hjälp med den första delen av livscykeln för en batchorder.</span><span class="sxs-lookup"><span data-stu-id="42d37-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="42d37-105">Från skapande, kostnadsberäkning och över produktionsjobb tidsplanering till den verkliga början av en batchorder.</span><span class="sxs-lookup"><span data-stu-id="42d37-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="42d37-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="42d37-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="42d37-107">Följande förutsättningar gäller för körning av proceduren med en annan datauppsättning är en frisläppt produkt med aktiv formel och flödesversion.</span><span class="sxs-lookup"><span data-stu-id="42d37-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="42d37-108">Skapa en batchorder</span><span class="sxs-lookup"><span data-stu-id="42d37-108">Create a batch order</span></span>
1. <span data-ttu-id="42d37-109">Gå till Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="42d37-109">Go to All production orders.</span></span>
2. <span data-ttu-id="42d37-110">Klicka på Ny batchorder.</span><span class="sxs-lookup"><span data-stu-id="42d37-110">Click New batch order.</span></span>
3. <span data-ttu-id="42d37-111">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="42d37-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="42d37-112">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="42d37-112">Click Create.</span></span>
5. <span data-ttu-id="42d37-113">Använd snabbfiltret för att filtrera på fältet Produktion med värdet ”b”.</span><span class="sxs-lookup"><span data-stu-id="42d37-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="42d37-114">Visa produktionsformeln och förväntade samprodukter</span><span class="sxs-lookup"><span data-stu-id="42d37-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="42d37-115">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="42d37-116">Klicka på Recept.</span><span class="sxs-lookup"><span data-stu-id="42d37-116">Click Formula.</span></span>
3. <span data-ttu-id="42d37-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-117">Close the page.</span></span>
4. <span data-ttu-id="42d37-118">Klicka på Samprodukter.</span><span class="sxs-lookup"><span data-stu-id="42d37-118">Click Co-products.</span></span>
5. <span data-ttu-id="42d37-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="42d37-120">Uppskatta batchordern</span><span class="sxs-lookup"><span data-stu-id="42d37-120">Estimate the batch order</span></span>
1. <span data-ttu-id="42d37-121">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="42d37-121">Click Estimate.</span></span>
2. <span data-ttu-id="42d37-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42d37-122">Click OK.</span></span>
3. <span data-ttu-id="42d37-123">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="42d37-124">Klicka på Visa beräkningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="42d37-124">Click View calculation details.</span></span>
5. <span data-ttu-id="42d37-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="42d37-126">Frisläpp batchordern</span><span class="sxs-lookup"><span data-stu-id="42d37-126">Release the batch order</span></span>
1. <span data-ttu-id="42d37-127">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="42d37-128">Klicka på Frisläpp.</span><span class="sxs-lookup"><span data-stu-id="42d37-128">Click Release.</span></span>
3. <span data-ttu-id="42d37-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42d37-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="42d37-130">Schemalägg produktionsjobb</span><span class="sxs-lookup"><span data-stu-id="42d37-130">Schedule production jobs</span></span>
1. <span data-ttu-id="42d37-131">Klicka på Tidsplanera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="42d37-132">Klicka på Tidsplanera jobb.</span><span class="sxs-lookup"><span data-stu-id="42d37-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="42d37-133">Välj Nej i fältet Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="42d37-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="42d37-134">Välj Nej i fältet Begränsat material.</span><span class="sxs-lookup"><span data-stu-id="42d37-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="42d37-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42d37-135">Click OK.</span></span>
6. <span data-ttu-id="42d37-136">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="42d37-137">Klicka på Alla jobb.</span><span class="sxs-lookup"><span data-stu-id="42d37-137">Click All jobs.</span></span>
8. <span data-ttu-id="42d37-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="42d37-139">Starta batchordern</span><span class="sxs-lookup"><span data-stu-id="42d37-139">Start the batch order</span></span>
1. <span data-ttu-id="42d37-140">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="42d37-140">Click Start.</span></span>
2. <span data-ttu-id="42d37-141">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="42d37-141">Click the General tab.</span></span>
3. <span data-ttu-id="42d37-142">Välj Nej i fältet Bokför plocklista nu.</span><span class="sxs-lookup"><span data-stu-id="42d37-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="42d37-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42d37-143">Click OK.</span></span>
5. <span data-ttu-id="42d37-144">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="42d37-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="42d37-145">Klicka på Plocklista.</span><span class="sxs-lookup"><span data-stu-id="42d37-145">Click Picking list.</span></span>
7. <span data-ttu-id="42d37-146">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="42d37-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="42d37-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-147">Close the page.</span></span>
9. <span data-ttu-id="42d37-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-148">Close the page.</span></span>
10. <span data-ttu-id="42d37-149">Klicka på Flödeskort.</span><span class="sxs-lookup"><span data-stu-id="42d37-149">Click Route card.</span></span>
11. <span data-ttu-id="42d37-150">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="42d37-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="42d37-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-151">Close the page.</span></span>
13. <span data-ttu-id="42d37-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="42d37-152">Close the page.</span></span>

