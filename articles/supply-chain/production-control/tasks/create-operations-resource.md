--- 
title: Skapa en verksamhetsresurs
description: "En verksamhetsresurs utför aktiviteter för ett projekt eller en produktionsprocess."
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e05eb5df2d29e90ed24fb13ed16543ad470dfe6b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-an-operations-resource"></a><span data-ttu-id="bb96c-103">Skapa en verksamhetsresurs</span><span class="sxs-lookup"><span data-stu-id="bb96c-103">Create an operations resource</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bb96c-104">En verksamhetsresurs utför aktiviteter för ett projekt eller en produktionsprocess.</span><span class="sxs-lookup"><span data-stu-id="bb96c-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="bb96c-105">Proceduren visar hur du definierar en verksamhetsresurs.</span><span class="sxs-lookup"><span data-stu-id="bb96c-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="bb96c-106">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="bb96c-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="bb96c-107">Gå till Resurser.</span><span class="sxs-lookup"><span data-stu-id="bb96c-107">Go to Resources.</span></span>
2. <span data-ttu-id="bb96c-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bb96c-108">Click New.</span></span>
3. <span data-ttu-id="bb96c-109">Ange ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="bb96c-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="bb96c-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="bb96c-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="bb96c-111">Definiera kapacitet och förbrukningparametrar</span><span class="sxs-lookup"><span data-stu-id="bb96c-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="bb96c-112">Expandera avsnittet Operation.</span><span class="sxs-lookup"><span data-stu-id="bb96c-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="bb96c-113">Ange ett nummer i fältet Kassationsprocent.</span><span class="sxs-lookup"><span data-stu-id="bb96c-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="bb96c-114">I fältet Inställningskategori, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bb96c-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="bb96c-115">Ange kostnadskategorin som definierar hur du ska beräkna kostnaden för inställningstid.</span><span class="sxs-lookup"><span data-stu-id="bb96c-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="bb96c-116">I fältet Kategori för körtid, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bb96c-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="bb96c-117">Ange kostnadskategorin som definierar hur du ska beräkna kostnaden för körtid.</span><span class="sxs-lookup"><span data-stu-id="bb96c-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="bb96c-118">Ange eller välj ett värde i fältet Kvantitetskategori.</span><span class="sxs-lookup"><span data-stu-id="bb96c-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="bb96c-119">Ange kostnadskategorin som definierar hur du ska beräkna resurskostnaden baserat på utleveranskvantitet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="bb96c-120">Markera ett alternativ i fältet Kapacitetsenhet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="bb96c-121">Ange enheten för uttryck av kapacitet för verksamhetsresursen.</span><span class="sxs-lookup"><span data-stu-id="bb96c-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="bb96c-122">Välj ett tal i fältet Kapacitet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="bb96c-123">Ange ett nummer i fältet Effektivitet i procent.</span><span class="sxs-lookup"><span data-stu-id="bb96c-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="bb96c-124">Ange effektiviteten som du förväntar dig från verksamhetsresursen.</span><span class="sxs-lookup"><span data-stu-id="bb96c-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="bb96c-125">Effektivitetsprocentsatsen justerar genomflödet från verksamhetsresursen och påverkar den tid som reserverats för resursen.</span><span class="sxs-lookup"><span data-stu-id="bb96c-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="bb96c-126">Ange ett tal i fältet Grovplaneringsprocent.</span><span class="sxs-lookup"><span data-stu-id="bb96c-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="bb96c-127">Ange högsta procentandelen av kapaciteten för verksamhetsresursen som du vill använda i grovplaneringen.</span><span class="sxs-lookup"><span data-stu-id="bb96c-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="bb96c-128">Välj Ja i fältet Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="bb96c-129">Ange det här alternativet som Ja om verksamhetsresursen ska planeras utifrån verklig kapacitet som är tillgänglig och om befintliga kapacitetsreservationer ska inkluderas.</span><span class="sxs-lookup"><span data-stu-id="bb96c-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="bb96c-130">Om det här alternativet är Nej antas verksamhetsresursen ha obegränsad kapacitet och resursen kan överbokas.</span><span class="sxs-lookup"><span data-stu-id="bb96c-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="bb96c-131">Välj Ja i fältet Flaskhalsresurs.</span><span class="sxs-lookup"><span data-stu-id="bb96c-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="bb96c-132">Definiera arbetstider</span><span class="sxs-lookup"><span data-stu-id="bb96c-132">Define working times</span></span>
1. <span data-ttu-id="bb96c-133">Expandera avsnittet Kalendrar.</span><span class="sxs-lookup"><span data-stu-id="bb96c-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="bb96c-134">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="bb96c-134">Click Add.</span></span>
3. <span data-ttu-id="bb96c-135">Ange eller välj ett värde i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="bb96c-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="bb96c-136">Ange arbetstidskalendrar som definierar kapaciteten (i timmar) för resursen.</span><span class="sxs-lookup"><span data-stu-id="bb96c-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="bb96c-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bb96c-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="bb96c-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bb96c-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="bb96c-139">Definiera resurskunskaper</span><span class="sxs-lookup"><span data-stu-id="bb96c-139">Define resource capabilities</span></span>
1. <span data-ttu-id="bb96c-140">Expandera avsnittet Funktioner.</span><span class="sxs-lookup"><span data-stu-id="bb96c-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="bb96c-141">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="bb96c-141">Click Add.</span></span>
    * <span data-ttu-id="bb96c-142">En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="bb96c-143">Planeringsmotorn allokerar resurser genom att matcha resurskrav för varje aktivitet mot kapaciteter hos de tillgängliga verksamhetsresurserna.</span><span class="sxs-lookup"><span data-stu-id="bb96c-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="bb96c-144">Ange eller välj ett värde i fältet Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb96c-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="bb96c-145">Välj ett tal i fältet Nivå.</span><span class="sxs-lookup"><span data-stu-id="bb96c-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="bb96c-146">Ange kompetensnivån som används av resursen för att bearbeta kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="bb96c-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="bb96c-147">Välj ett tal i fältet Prioritet.</span><span class="sxs-lookup"><span data-stu-id="bb96c-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="bb96c-148">Ange prioriteten för verksamhetsresursen med avseende på kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="bb96c-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="bb96c-149">När du planerar med prioritet väljs verksamhetsresursen med högst prioritet (lägst numeriskt värde) först.</span><span class="sxs-lookup"><span data-stu-id="bb96c-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="bb96c-150">Tilldela resurs till resursgrupp</span><span class="sxs-lookup"><span data-stu-id="bb96c-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="bb96c-151">Expandera avsnittet Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="bb96c-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="bb96c-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="bb96c-152">Click Add.</span></span>
    * <span data-ttu-id="bb96c-153">Resursgruppen definierar plats, produktionsenhet och lagerställeskontext för verksamhetsresurser.</span><span class="sxs-lookup"><span data-stu-id="bb96c-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="bb96c-154">Verksamhetsresursen kan bara planeras när den har tilldelats till en resursgrupp och endast på den plats där resursgruppen finns.</span><span class="sxs-lookup"><span data-stu-id="bb96c-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="bb96c-155">I fältet Resursgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="bb96c-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="bb96c-156">Ange eller välj ett värde i fältet Plats för inleverans.</span><span class="sxs-lookup"><span data-stu-id="bb96c-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="bb96c-157">Ange lagerställesplatsen från vilken verksamhetsresursen förbrukar material.</span><span class="sxs-lookup"><span data-stu-id="bb96c-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  


