---
title: Skapa en kanban-regel för försäljningshändelse
description: Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel som utlöses under genereringen av försäljningsorder.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1759adea6db8120078e2f32bff79178545c2328a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210867"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="67172-103">Skapa en kanban-regel för försäljningshändelse</span><span class="sxs-lookup"><span data-stu-id="67172-103">Create a sales event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="67172-104">Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel som utlöses under genereringen av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="67172-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="67172-105">Den händelsebaserade kanban-regeln fyller på behov som har sitt ursprung i försäljningsorderrader.</span><span class="sxs-lookup"><span data-stu-id="67172-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="67172-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="67172-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="67172-107">Proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.</span><span class="sxs-lookup"><span data-stu-id="67172-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="67172-108">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="67172-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="67172-109">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="67172-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="67172-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="67172-110">Click New.</span></span>
3. <span data-ttu-id="67172-111">Välj Händelse i fältet för återanskaffningsstrategi.</span><span class="sxs-lookup"><span data-stu-id="67172-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="67172-112">Om du väljer Händelse innebär det att kanban-regeln utlösas av en händelse, till exempel genereringen av en försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="67172-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="67172-113">Detta gäller för områden där varje kanban ska täcka en viss efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="67172-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="67172-114">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="67172-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="67172-115">Välj Slutmontering.</span><span class="sxs-lookup"><span data-stu-id="67172-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="67172-116">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="67172-116">Expand the Details section.</span></span>
6. <span data-ttu-id="67172-117">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="67172-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="67172-118">Välj L0050.</span><span class="sxs-lookup"><span data-stu-id="67172-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="67172-119">Definiera en händelse</span><span class="sxs-lookup"><span data-stu-id="67172-119">Define an event</span></span>
1. <span data-ttu-id="67172-120">Expandera avsnittet Händelser.</span><span class="sxs-lookup"><span data-stu-id="67172-120">Expand the Events section.</span></span>
2. <span data-ttu-id="67172-121">Välj Automatisk i fältet Försäljningshändelse.</span><span class="sxs-lookup"><span data-stu-id="67172-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="67172-122">Genom att välja försäljningshändelsen Automatisk kommer denna kanban-regel att utlösas automatiskt när en försäljningsrad matchar produkt- och inleveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="67172-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="67172-123">I den här proceduren är det produkten L0050 på lagerställe 13.</span><span class="sxs-lookup"><span data-stu-id="67172-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="67172-124">Ange den minsta händelsekvantiteten till "50".</span><span class="sxs-lookup"><span data-stu-id="67172-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="67172-125">Med en minsta händelsekvantitet på 50 kommer kanban-regeln endast att utlösas av händelser med en kvantitet på 50 eller mer.</span><span class="sxs-lookup"><span data-stu-id="67172-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="67172-126">Expandera avsnittet Produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="67172-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="67172-127">Observera att inleveransplatsen är lagerställe 13.</span><span class="sxs-lookup"><span data-stu-id="67172-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="67172-128">Detta innebär att den här kanban-regeln utlöses för den här platsen.</span><span class="sxs-lookup"><span data-stu-id="67172-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="67172-129">I det här exemplet utlöser en försäljningsrad för produkten L0050, med en kvantitet på 50 eller mer, på lagerställe 13, den här kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="67172-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="67172-130">Skapa försäljningsrader för att utlösa kanban-regel för händelse</span><span class="sxs-lookup"><span data-stu-id="67172-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="67172-131">Gå till Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="67172-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="67172-132">Ett varningsmeddelande visas när kanban-regeln sparas, vilket innebär att kanbans skapas i realtid under genereringen av försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="67172-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="67172-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="67172-133">Click New.</span></span>
3. <span data-ttu-id="67172-134">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="67172-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="67172-135">Välj till exempel US-003.</span><span class="sxs-lookup"><span data-stu-id="67172-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="67172-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="67172-136">Click OK.</span></span>
5. <span data-ttu-id="67172-137">Skriv "L0050" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="67172-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="67172-138">Skriv "1" i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="67172-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="67172-139">Välj Plats 1 eftersom Lagerställe 13 finns på Plats 1.</span><span class="sxs-lookup"><span data-stu-id="67172-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="67172-140">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="67172-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="67172-141">Ange lagerstället till 13.</span><span class="sxs-lookup"><span data-stu-id="67172-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="67172-142">Ställ in kvantiteten på 75.</span><span class="sxs-lookup"><span data-stu-id="67172-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="67172-143">Ange en kvantitet på 50 eller högre för att utlösa den skapade kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="67172-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="67172-144">Kontrollera att kanban skapas</span><span class="sxs-lookup"><span data-stu-id="67172-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="67172-145">Klicka på Produkt och leverans.</span><span class="sxs-lookup"><span data-stu-id="67172-145">Click Product and supply.</span></span>
2. <span data-ttu-id="67172-146">Klicka på Visa pegging-träd.</span><span class="sxs-lookup"><span data-stu-id="67172-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="67172-147">Lägg märke till att en kanban med samma kvantitet som försäljningsraden skapas.</span><span class="sxs-lookup"><span data-stu-id="67172-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="67172-148">Du kan även se materialet som behövs för att producera L0050.</span><span class="sxs-lookup"><span data-stu-id="67172-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="67172-149">Detta är det sista steget i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="67172-149">This is the last step in this procedure.</span></span>  

