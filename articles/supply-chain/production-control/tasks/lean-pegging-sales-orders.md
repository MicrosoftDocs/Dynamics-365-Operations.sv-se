--- 
title: "Lean-pegging från försäljningsorder"
description: "Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 16e2eb864f092ef221374e3d26b2d04a93be4de4
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="0b450-103">Lean-pegging från försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="0b450-103">Lean pegging from sales orders</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0b450-104">Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban.</span><span class="sxs-lookup"><span data-stu-id="0b450-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="0b450-105">När du har validerat pegging-trädet planeras alla kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="0b450-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="0b450-106">Detta är användbart för orderscenarier där ordermottagaren behöver se till att produktion kan starta omedelbart.</span><span class="sxs-lookup"><span data-stu-id="0b450-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="0b450-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="0b450-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0b450-108">Den här proceduren är avsedd för den avancerade ordermottagaren som arbetar på ett lean-företag.</span><span class="sxs-lookup"><span data-stu-id="0b450-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="0b450-109">Skapa en försäljningsorder för en kanban-kontrollerad artikel</span><span class="sxs-lookup"><span data-stu-id="0b450-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="0b450-110">Gå till Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="0b450-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="0b450-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0b450-111">Click New.</span></span>
3. <span data-ttu-id="0b450-112">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="0b450-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="0b450-113">Använd US-001.</span><span class="sxs-lookup"><span data-stu-id="0b450-113">Use US-001.</span></span>  
4. <span data-ttu-id="0b450-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0b450-114">Click OK.</span></span>
5. <span data-ttu-id="0b450-115">Skriv "L0001" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="0b450-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="0b450-116">Ställ in kvantiteten på 30.</span><span class="sxs-lookup"><span data-stu-id="0b450-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="0b450-117">Det är viktigt att kvantiteten är högre än 24 för att utlösa kanban-regeln för händelsen.</span><span class="sxs-lookup"><span data-stu-id="0b450-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="0b450-118">Öppna ett pegging-träd</span><span class="sxs-lookup"><span data-stu-id="0b450-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="0b450-119">Klicka på Produkt och leverans.</span><span class="sxs-lookup"><span data-stu-id="0b450-119">Click Product and supply.</span></span>
2. <span data-ttu-id="0b450-120">Klicka på Visa pegging-träd.</span><span class="sxs-lookup"><span data-stu-id="0b450-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="0b450-121">Observera att peggingträdet visar alla nivåer för peggingen som behövs för försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="0b450-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="0b450-122">I det här fallet finns det två nivåer för kanban och alla nödvändiga komponenter.</span><span class="sxs-lookup"><span data-stu-id="0b450-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="0b450-123">Planera pegging-trädet</span><span class="sxs-lookup"><span data-stu-id="0b450-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="0b450-124">I trädet, välj försäljningsrad 000832\Kanban 000558.</span><span class="sxs-lookup"><span data-stu-id="0b450-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="0b450-125">Expandera avsnittet Kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="0b450-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="0b450-126">Observera att jobbstatusen för kanban-jobbet är Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="0b450-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="0b450-127">Klicka på Planera helt pegging-träd.</span><span class="sxs-lookup"><span data-stu-id="0b450-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="0b450-128">Då planeras alla kanban-jobb i peggingträdet och jobbstatusen ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="0b450-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="0b450-129">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="0b450-129">Refresh the page.</span></span>
    * <span data-ttu-id="0b450-130">Observera att kanban-jobbets status ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="0b450-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="0b450-131">I trädet, välj försäljningsrad 000832\Kanban 000558\Utleverans för L0001\Kanban 000559.</span><span class="sxs-lookup"><span data-stu-id="0b450-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="0b450-132">Jobbet för den andra kanban planeras även, eftersom hela pegging-trädet planeras.</span><span class="sxs-lookup"><span data-stu-id="0b450-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="0b450-133">Observera att kanban-jobbets status ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="0b450-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  


