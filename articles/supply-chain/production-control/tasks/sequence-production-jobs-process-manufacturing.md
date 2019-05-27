---
title: Ordningsföljd för produktionsjobb för processtillverkning
description: Den här proceduren använder målarfärgprodukter som ett exempel för att visa hur du ordnar planerade order enligt prioritet för färg och paketstorlek.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e064f55ed451d44f58e60ba0aa722166981c129
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571506"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="603dc-103">Ordningsföljd för produktionsjobb för processtillverkning</span><span class="sxs-lookup"><span data-stu-id="603dc-103">Sequence production jobs for process manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="603dc-104">Den här proceduren använder målarfärgprodukter som ett exempel för att visa hur du ordnar planerade order enligt prioritet för färg och paketstorlek.</span><span class="sxs-lookup"><span data-stu-id="603dc-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="603dc-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USPI.</span><span class="sxs-lookup"><span data-stu-id="603dc-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="603dc-106">Den här proceduren är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="603dc-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="603dc-107">Kör huvudplanering för USPI</span><span class="sxs-lookup"><span data-stu-id="603dc-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="603dc-108">Gå till Huvudplanering > Huvudplanering > Kör > Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="603dc-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="603dc-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Huvudplan.</span><span class="sxs-lookup"><span data-stu-id="603dc-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="603dc-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="603dc-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="603dc-111">Välj MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="603dc-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="603dc-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="603dc-112">Click OK.</span></span>
    * <span data-ttu-id="603dc-113">Detta startar huvudplanering, inklusive sekvensprocessen.</span><span class="sxs-lookup"><span data-stu-id="603dc-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="603dc-114">Den här processen kan ta några minuter.</span><span class="sxs-lookup"><span data-stu-id="603dc-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="603dc-115">Visa planerade order för målarfärgprodukterna</span><span class="sxs-lookup"><span data-stu-id="603dc-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="603dc-116">Gå till Huvudplanering > Huvudplanering > Planerade order.</span><span class="sxs-lookup"><span data-stu-id="603dc-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="603dc-117">Visa faktaboxen Artikeldetaljer.</span><span class="sxs-lookup"><span data-stu-id="603dc-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="603dc-118">Visa faktaboxen Detaljer om tidsplan.</span><span class="sxs-lookup"><span data-stu-id="603dc-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="603dc-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="603dc-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="603dc-120">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="603dc-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="603dc-121">Välj MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="603dc-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="603dc-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="603dc-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="603dc-123">Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P300.</span><span class="sxs-lookup"><span data-stu-id="603dc-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="603dc-124">Lås upp för att bläddra till höger för att se orderdatum och leveransdatum.</span><span class="sxs-lookup"><span data-stu-id="603dc-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="603dc-125">Observera att dessa artiklar har ett orderdatum för idag och leveransdatum för de planerade order ordnas inte efter prioritet för färg och paketstorlek, som visas i produktnamnet.</span><span class="sxs-lookup"><span data-stu-id="603dc-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="603dc-126">Du kan hovra över ett artikelnummer om du vill se produktnamnet och prioriteten.</span><span class="sxs-lookup"><span data-stu-id="603dc-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="603dc-127">Ordna planerade order för målarfärg</span><span class="sxs-lookup"><span data-stu-id="603dc-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="603dc-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="603dc-128">Close the page.</span></span>
2. <span data-ttu-id="603dc-129">Gå till Huvudplanering > Huvudplanering > Sekventiellt planerade order.</span><span class="sxs-lookup"><span data-stu-id="603dc-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="603dc-130">Visa faktaboxen Artikeldetaljer.</span><span class="sxs-lookup"><span data-stu-id="603dc-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="603dc-131">Visa faktaboxen Detaljer om tidsplan.</span><span class="sxs-lookup"><span data-stu-id="603dc-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="603dc-132">Obs! Här ser du att Startdatum/tid för planerade order ordnas efter färg och paketstorlek inom en gruppsperiod på 28 dagar.</span><span class="sxs-lookup"><span data-stu-id="603dc-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="603dc-133">Dessa perioder definieras av ett nummer i fältet Kampanj.</span><span class="sxs-lookup"><span data-stu-id="603dc-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="603dc-134">Det sekventiellt planerade orderformuläret fungerar som det vanliga planerade orderformuläret och produktionsplaneraren kan bekräfta planerade order här.</span><span class="sxs-lookup"><span data-stu-id="603dc-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="603dc-135">Markera alla rader.</span><span class="sxs-lookup"><span data-stu-id="603dc-135">Mark all rows.</span></span>
6. <span data-ttu-id="603dc-136">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="603dc-136">Click Accept.</span></span>
    * <span data-ttu-id="603dc-137">Detta kommer att uppdatera alla planerade order med den valda sekvensåtgärden av antingen Senarelägg eller Förskott.</span><span class="sxs-lookup"><span data-stu-id="603dc-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="603dc-138">Kontrollera sekvensen av de planerade order</span><span class="sxs-lookup"><span data-stu-id="603dc-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="603dc-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="603dc-139">Close the page.</span></span>
2. <span data-ttu-id="603dc-140">Gå till Huvudplanering > Huvudplanering > Planerade order.</span><span class="sxs-lookup"><span data-stu-id="603dc-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="603dc-141">Visa faktaboxen Artikeldetaljer.</span><span class="sxs-lookup"><span data-stu-id="603dc-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="603dc-142">Visa faktaboxen Detaljer om tidsplan.</span><span class="sxs-lookup"><span data-stu-id="603dc-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="603dc-143">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="603dc-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="603dc-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="603dc-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="603dc-145">Välj MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="603dc-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="603dc-146">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="603dc-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="603dc-147">Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P300.</span><span class="sxs-lookup"><span data-stu-id="603dc-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="603dc-148">Observera att order grupperas nu enligt prioritet för färg och storlek och planerade order börjar på det tidigaste order- och leveransdatumet.</span><span class="sxs-lookup"><span data-stu-id="603dc-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="603dc-149">Validera orderdatumkolumnen eller startdatumet i faktaboxen Detaljer om tidsplan.</span><span class="sxs-lookup"><span data-stu-id="603dc-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  

