---
title: Lean-pegging från försäljningsorder
description: Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6a18d24be85e20a7e5824c334855aa94fe61cb5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245983"
---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="831d1-103">Lean-pegging från försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="831d1-103">Lean pegging from sales orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="831d1-104">Den här proceduren är avsedd för att validera peggingträdet från en försäljningsrad där artikeln produceras med kanban.</span><span class="sxs-lookup"><span data-stu-id="831d1-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="831d1-105">När du har validerat pegging-trädet planeras alla kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="831d1-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="831d1-106">Detta är användbart för orderscenarier där ordermottagaren behöver se till att produktion kan starta omedelbart.</span><span class="sxs-lookup"><span data-stu-id="831d1-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="831d1-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="831d1-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="831d1-108">Den här proceduren är avsedd för den avancerade ordermottagaren som arbetar på ett lean-företag.</span><span class="sxs-lookup"><span data-stu-id="831d1-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="831d1-109">Skapa en försäljningsorder för en kanban-kontrollerad artikel</span><span class="sxs-lookup"><span data-stu-id="831d1-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="831d1-110">Gå till Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="831d1-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="831d1-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="831d1-111">Click New.</span></span>
3. <span data-ttu-id="831d1-112">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="831d1-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="831d1-113">Använd US-001.</span><span class="sxs-lookup"><span data-stu-id="831d1-113">Use US-001.</span></span>  
4. <span data-ttu-id="831d1-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="831d1-114">Click OK.</span></span>
5. <span data-ttu-id="831d1-115">Skriv "L0001" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="831d1-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="831d1-116">Ställ in kvantiteten på 30.</span><span class="sxs-lookup"><span data-stu-id="831d1-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="831d1-117">Det är viktigt att kvantiteten är högre än 24 för att utlösa kanban-regeln för händelsen.</span><span class="sxs-lookup"><span data-stu-id="831d1-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="831d1-118">Öppna ett pegging-träd</span><span class="sxs-lookup"><span data-stu-id="831d1-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="831d1-119">Klicka på Produkt och leverans.</span><span class="sxs-lookup"><span data-stu-id="831d1-119">Click Product and supply.</span></span>
2. <span data-ttu-id="831d1-120">Klicka på Visa pegging-träd.</span><span class="sxs-lookup"><span data-stu-id="831d1-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="831d1-121">Observera att peggingträdet visar alla nivåer för peggingen som behövs för försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="831d1-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="831d1-122">I det här fallet finns det två nivåer för kanban och alla nödvändiga komponenter.</span><span class="sxs-lookup"><span data-stu-id="831d1-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="831d1-123">Planera pegging-trädet</span><span class="sxs-lookup"><span data-stu-id="831d1-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="831d1-124">I trädet, välj försäljningsrad 000832\Kanban 000558.</span><span class="sxs-lookup"><span data-stu-id="831d1-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="831d1-125">Expandera avsnittet Kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="831d1-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="831d1-126">Observera att jobbstatusen för kanban-jobbet är Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="831d1-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="831d1-127">Klicka på Planera helt pegging-träd.</span><span class="sxs-lookup"><span data-stu-id="831d1-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="831d1-128">Då planeras alla kanban-jobb i peggingträdet och jobbstatusen ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="831d1-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="831d1-129">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="831d1-129">Refresh the page.</span></span>
    * <span data-ttu-id="831d1-130">Observera att kanban-jobbets status ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="831d1-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="831d1-131">I trädet, välj försäljningsrad 000832\Kanban 000558\Utleverans för L0001\Kanban 000559.</span><span class="sxs-lookup"><span data-stu-id="831d1-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="831d1-132">Jobbet för den andra kanban planeras även, eftersom hela pegging-trädet planeras.</span><span class="sxs-lookup"><span data-stu-id="831d1-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="831d1-133">Observera att kanban-jobbets status ändras från Inte planerad till Planerad.</span><span class="sxs-lookup"><span data-stu-id="831d1-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]