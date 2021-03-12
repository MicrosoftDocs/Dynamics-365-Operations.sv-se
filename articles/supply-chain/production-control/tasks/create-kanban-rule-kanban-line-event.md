---
title: Skapa en kanban-regel med en kanban-radhändelse
description: Den här proceduren skapar en kanban-regel genom att använda inställningen för kanban-radhändelsen för att utlösa drag från en processaktivitet.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02511fea05cb1dfde17b1b8acaac97dcc136c062
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981265"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="66fd9-103">Skapa en kanban-regel med en kanban-radhändelse</span><span class="sxs-lookup"><span data-stu-id="66fd9-103">Create a kanban rule using a kanban line event</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="66fd9-104">Den här proceduren skapar en kanban-regel genom att använda inställningen för kanban-radhändelsen för att utlösa drag från en processaktivitet.</span><span class="sxs-lookup"><span data-stu-id="66fd9-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="66fd9-105">Kanban-regeln utlöses av en kanban processaktivitet med en kvantitet lika med eller större än 25 vardera.</span><span class="sxs-lookup"><span data-stu-id="66fd9-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="66fd9-106">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="66fd9-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="66fd9-107">Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.</span><span class="sxs-lookup"><span data-stu-id="66fd9-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="66fd9-108">Skapa en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="66fd9-108">Create a kanban rule</span></span>
1. <span data-ttu-id="66fd9-109">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="66fd9-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="66fd9-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="66fd9-110">Click New.</span></span>
3. <span data-ttu-id="66fd9-111">Välj Händelse i fältet för återanskaffningsstrategi.</span><span class="sxs-lookup"><span data-stu-id="66fd9-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="66fd9-112">Detta skapar kanban direkt från efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="66fd9-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="66fd9-113">Den används för att ställa in regler som definierar ett tillverkas på beställning-scenario.</span><span class="sxs-lookup"><span data-stu-id="66fd9-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="66fd9-114">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="66fd9-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="66fd9-115">Ange eller välj SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="66fd9-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="66fd9-116">Den första aktiviteten av en tillverkningskanban-regel är en processaktivitet i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="66fd9-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="66fd9-117">När du väljer en aktivitet, kopieras giltighetsdatum för aktiviteten till giltighetsdatum för kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="66fd9-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="66fd9-118">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="66fd9-118">Expand the Details section.</span></span>
6. <span data-ttu-id="66fd9-119">Ange "L0001" i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="66fd9-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="66fd9-120">Expandera avsnittet Händelser.</span><span class="sxs-lookup"><span data-stu-id="66fd9-120">Expand the Events section.</span></span>
8. <span data-ttu-id="66fd9-121">Välj "Automatisk" i fältet Kanban-radhändelse.</span><span class="sxs-lookup"><span data-stu-id="66fd9-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="66fd9-122">Då skapas händelse-kanbans på begäran.</span><span class="sxs-lookup"><span data-stu-id="66fd9-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="66fd9-123">Detta fällt används för att konfigurera kanban-regeln som fyller på det material som behövs för en underordnad processaktivitet.</span><span class="sxs-lookup"><span data-stu-id="66fd9-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="66fd9-124">När du väljer Automatiskt, skapas händelse-kanbans med efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="66fd9-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="66fd9-125">Den här inställningen rekommenderas om du förväntar dig att köra produktion samma dag.</span><span class="sxs-lookup"><span data-stu-id="66fd9-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="66fd9-126">Ange den minsta händelsekvantiteten till "25".</span><span class="sxs-lookup"><span data-stu-id="66fd9-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="66fd9-127">Händelse-kanban skapas när efterfrågekvantiteten är lika med eller fler än det här fältet.</span><span class="sxs-lookup"><span data-stu-id="66fd9-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="66fd9-128">Detta är användbart om du vill producera en orderkvantitet som är mindre än det här fältet på en dator och mer än det här fältet på en annan dator.</span><span class="sxs-lookup"><span data-stu-id="66fd9-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="66fd9-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="66fd9-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="66fd9-130">Skapa försäljningsorder och utlösa kanbankedjan</span><span class="sxs-lookup"><span data-stu-id="66fd9-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="66fd9-131">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="66fd9-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="66fd9-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="66fd9-132">Click New.</span></span>
3. <span data-ttu-id="66fd9-133">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="66fd9-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="66fd9-134">Välj kundkontot US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="66fd9-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="66fd9-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="66fd9-135">Click OK.</span></span>
5. <span data-ttu-id="66fd9-136">Skriv "L0001" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="66fd9-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="66fd9-137">L0001 är den artikel som du skapat för kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="66fd9-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="66fd9-138">Ställ in kvantiteten på 27.</span><span class="sxs-lookup"><span data-stu-id="66fd9-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="66fd9-139">Eftersom 27 är högre än minimikvantiteten på 25 på kanban-regel, kommer detta att utlösa en händelse-kanban.</span><span class="sxs-lookup"><span data-stu-id="66fd9-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="66fd9-140">Skriv "1" i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="66fd9-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="66fd9-141">Ange eller välj ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="66fd9-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="66fd9-142">Välj lagerställe 13.</span><span class="sxs-lookup"><span data-stu-id="66fd9-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="66fd9-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="66fd9-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="66fd9-144">Visa den kanban som genereras av kanban-regeln</span><span class="sxs-lookup"><span data-stu-id="66fd9-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="66fd9-145">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="66fd9-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="66fd9-146">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="66fd9-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="66fd9-147">Expandera avsnittet Kanbans.</span><span class="sxs-lookup"><span data-stu-id="66fd9-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="66fd9-148">Observera att en kanban för 27 skapades för att bearbeta den aktivitet som baseras på den skapade kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="66fd9-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="66fd9-149">Detta är det sista steget.</span><span class="sxs-lookup"><span data-stu-id="66fd9-149">This is the last step.</span></span>  

