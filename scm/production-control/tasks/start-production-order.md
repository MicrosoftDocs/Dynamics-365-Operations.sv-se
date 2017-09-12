--- 
title: Starta en produktionsorder
description: "Den här proceduren visar hur du startar en produktionsorder i fabriken."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 33558053d33d9fe4a2ecb3576da569b2c441db80
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="start-a-production-order"></a><span data-ttu-id="08bc5-103">Starta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="08bc5-103">Start a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08bc5-104">Den här proceduren visar hur du startar en produktionsorder i fabriken.</span><span class="sxs-lookup"><span data-stu-id="08bc5-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="08bc5-105">Tids- och materialförbrukning rapporteras i den här processen.</span><span class="sxs-lookup"><span data-stu-id="08bc5-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="08bc5-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="08bc5-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="08bc5-107">Detta är den femte proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="08bc5-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="08bc5-108">Starta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="08bc5-108">Start a production order</span></span>
1. <span data-ttu-id="08bc5-109">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="08bc5-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="08bc5-110">Välj en produktionsorder som har statusen Frisläppt.</span><span class="sxs-lookup"><span data-stu-id="08bc5-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="08bc5-111">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08bc5-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="08bc5-112">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="08bc5-112">Click Start.</span></span>
    * <span data-ttu-id="08bc5-113">På den här sidan kan du bekräfta produktionsorderns start.</span><span class="sxs-lookup"><span data-stu-id="08bc5-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="08bc5-114">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="08bc5-114">Click the General tab.</span></span>
5. <span data-ttu-id="08bc5-115">I Från Oper.</span><span class="sxs-lookup"><span data-stu-id="08bc5-115">In the From Oper.</span></span> <span data-ttu-id="08bc5-116">Nr.</span><span class="sxs-lookup"><span data-stu-id="08bc5-116">No.</span></span> <span data-ttu-id="08bc5-117">fältet, ange"10".</span><span class="sxs-lookup"><span data-stu-id="08bc5-117">field, enter '10'.</span></span>
6. <span data-ttu-id="08bc5-118">Välj "Alltid" i fältet Automatisk flödesförbrukning.</span><span class="sxs-lookup"><span data-stu-id="08bc5-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="08bc5-119">Klicka på kryssrutan Bokför ruttkort nu.</span><span class="sxs-lookup"><span data-stu-id="08bc5-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="08bc5-120">Välj "Alltid" i fältet Automatisk strukturlisteförbrukning.</span><span class="sxs-lookup"><span data-stu-id="08bc5-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="08bc5-121">Klicka på kryssrutan Bokför plocklista nu.</span><span class="sxs-lookup"><span data-stu-id="08bc5-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="08bc5-122">Klicka på kryssrutan Skriv ut plocklista.</span><span class="sxs-lookup"><span data-stu-id="08bc5-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="08bc5-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08bc5-123">Click OK.</span></span>
    * <span data-ttu-id="08bc5-124">Det här är den utskrivna plocklistan som visar det material som används för produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="08bc5-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="08bc5-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="08bc5-126">Validera plocklistan</span><span class="sxs-lookup"><span data-stu-id="08bc5-126">Validate the picking list</span></span>
1. <span data-ttu-id="08bc5-127">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08bc5-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="08bc5-128">Klicka på Plocklista.</span><span class="sxs-lookup"><span data-stu-id="08bc5-128">Click Picking list.</span></span>
3. <span data-ttu-id="08bc5-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="08bc5-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="08bc5-131">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="08bc5-131">Click Edit.</span></span>
6. <span data-ttu-id="08bc5-132">Ange ett värde i fältet Förbrukning.</span><span class="sxs-lookup"><span data-stu-id="08bc5-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="08bc5-133">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="08bc5-133">Click Post.</span></span>
8. <span data-ttu-id="08bc5-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08bc5-134">Click OK.</span></span>
    * <span data-ttu-id="08bc5-135">I plocklistejournalen bokförs materialet som förbrukas av produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="08bc5-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="08bc5-136">Innan du bokför journalen kan du göra justeringar om det finns en skillnad mellan den beräknade kvantiteten och den verkliga förbrukade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="08bc5-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="08bc5-137">Klicka på fliken GridPanel.</span><span class="sxs-lookup"><span data-stu-id="08bc5-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="08bc5-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="08bc5-139">Verifiera flödeskortjournalen</span><span class="sxs-lookup"><span data-stu-id="08bc5-139">Verify the route card journal</span></span>
1. <span data-ttu-id="08bc5-140">Klicka på Visa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08bc5-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="08bc5-141">Klicka på Flödeskort.</span><span class="sxs-lookup"><span data-stu-id="08bc5-141">Click Route card.</span></span>
3. <span data-ttu-id="08bc5-142">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="08bc5-143">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="08bc5-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="08bc5-144">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="08bc5-144">Click Edit.</span></span>
6. <span data-ttu-id="08bc5-145">Ange ett värde i fältet Timmar.</span><span class="sxs-lookup"><span data-stu-id="08bc5-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="08bc5-146">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="08bc5-146">Click Post.</span></span>
8. <span data-ttu-id="08bc5-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="08bc5-147">Click OK.</span></span>
    * <span data-ttu-id="08bc5-148">I flödeskortjournalen registreras tidsåtgången för enskilda åtgärder.</span><span class="sxs-lookup"><span data-stu-id="08bc5-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="08bc5-149">Varu- och felkvantiteten kan också rapporteras.</span><span class="sxs-lookup"><span data-stu-id="08bc5-149">Good and error quantity can also be reported.</span></span>  


