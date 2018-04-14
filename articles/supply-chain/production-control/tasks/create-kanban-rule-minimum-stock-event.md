--- 
title: "Skapa en kanban-regel med en minsta lagerhändelse"
description: "Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel med hjälp av en minsta lagerhändelse för att se till att en specifik produkt alltid är tillgänglig på en viss plats."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
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
ms.openlocfilehash: c5f795f8d3c31c9acdbddd94879dbd427145956c
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="9089b-103">Skapa en kanban-regel med en minsta lagerhändelse</span><span class="sxs-lookup"><span data-stu-id="9089b-103">Create a kanban rule using a minimum stock event</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9089b-104">Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel med hjälp av en minsta lagerhändelse för att se till att en specifik produkt alltid är tillgänglig på en viss plats.</span><span class="sxs-lookup"><span data-stu-id="9089b-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="9089b-105">En kanban-regel skapas för att överföra material till platsen när lagernivån sjunker under 200 enheter.</span><span class="sxs-lookup"><span data-stu-id="9089b-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="9089b-106">Genom att köra bearbetning av pegging-händelse skapas de nödvändiga kanbans.</span><span class="sxs-lookup"><span data-stu-id="9089b-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="9089b-107">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="9089b-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="9089b-108">Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.</span><span class="sxs-lookup"><span data-stu-id="9089b-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="9089b-109">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="9089b-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="9089b-110">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="9089b-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="9089b-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9089b-111">Click New.</span></span>
3. <span data-ttu-id="9089b-112">Välj "Uttag" i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="9089b-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="9089b-113">Denna typ används för att skapa överföringskanban.</span><span class="sxs-lookup"><span data-stu-id="9089b-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="9089b-114">Välj Händelse i fältet för återanskaffningsstrategi.</span><span class="sxs-lookup"><span data-stu-id="9089b-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="9089b-115">Händelsestrategin används om du vill skapa överföringen av kanban baserat på en händelse.</span><span class="sxs-lookup"><span data-stu-id="9089b-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="9089b-116">Senare under proceduren kommer du att utlösa överföringskanban genom att använda lageråteranskaffning.</span><span class="sxs-lookup"><span data-stu-id="9089b-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="9089b-117">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="9089b-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="9089b-118">Ange eller välj ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="9089b-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="9089b-119">Den här överföringsaktiviteten har mottagande lagerställe (utleverans) och plats 12, vilket innebär att material ska flyttas till plats 12 på lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="9089b-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="9089b-120">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="9089b-120">Expand the Details section.</span></span>
7. <span data-ttu-id="9089b-121">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="9089b-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="9089b-122">Välj M0007.</span><span class="sxs-lookup"><span data-stu-id="9089b-122">Select M0007.</span></span>  
8. <span data-ttu-id="9089b-123">Expandera avsnittet Händelser.</span><span class="sxs-lookup"><span data-stu-id="9089b-123">Expand the Events section.</span></span>
9. <span data-ttu-id="9089b-124">Välj "Batch" i fältet Lagerpåfyllnadshändelse.</span><span class="sxs-lookup"><span data-stu-id="9089b-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="9089b-125">Då skapas kanban för att uppfylla materialbehoven på den relaterade platsen under bearbetning av pegging-händelse.</span><span class="sxs-lookup"><span data-stu-id="9089b-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="9089b-126">Ange minsta kvantitet för artikeln</span><span class="sxs-lookup"><span data-stu-id="9089b-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="9089b-127">Klicka för att följa länken i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="9089b-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="9089b-128">Klicka för att följa länken i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="9089b-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="9089b-129">Expandera faktaboxen för produktbilden.</span><span class="sxs-lookup"><span data-stu-id="9089b-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="9089b-130">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9089b-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="9089b-131">Klicka på Artikeldisponering.</span><span class="sxs-lookup"><span data-stu-id="9089b-131">Click Item coverage.</span></span>
6. <span data-ttu-id="9089b-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9089b-132">Click New.</span></span>
7. <span data-ttu-id="9089b-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="9089b-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9089b-134">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="9089b-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="9089b-135">Ange lagerstället till 12.</span><span class="sxs-lookup"><span data-stu-id="9089b-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="9089b-136">Ange minsta till "200".</span><span class="sxs-lookup"><span data-stu-id="9089b-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="9089b-137">Kör jobbet för att skapa batch-händelse.</span><span class="sxs-lookup"><span data-stu-id="9089b-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="9089b-138">Gå till Produktionskontroll > Periodiska uppgifter > Batchbearbetning av kanban-jobb > Bearbetning av pegging-händelse.</span><span class="sxs-lookup"><span data-stu-id="9089b-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="9089b-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9089b-139">Click OK.</span></span>
3. <span data-ttu-id="9089b-140">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="9089b-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="9089b-141">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9089b-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9089b-142">Välj kanban-regeln som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="9089b-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="9089b-143">Expandera avsnittet Kanbans.</span><span class="sxs-lookup"><span data-stu-id="9089b-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="9089b-144">Observera att en kanban skapades för att överföra det nödvändiga materialet till lagerställe 12.</span><span class="sxs-lookup"><span data-stu-id="9089b-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  


