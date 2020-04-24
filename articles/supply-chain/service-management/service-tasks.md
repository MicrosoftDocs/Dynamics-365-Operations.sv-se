---
title: Serviceuppgifter – översikt
description: Använd serviceuppgifter om du vill beskriva den aktivitet som utförs under en serviceorder. Den här informationen är tillgänglig för både tekniker och kunder.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2864b481c67c078df73436d752069a6b6c78640
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206045"
---
# <a name="service-tasks-overview"></a><span data-ttu-id="ebe0a-104">Serviceuppgifter – översikt</span><span class="sxs-lookup"><span data-stu-id="ebe0a-104">Service tasks overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebe0a-105">Använd serviceuppgifter om du vill beskriva den aktivitet som utförs under en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="ebe0a-106">Den här informationen är tillgänglig för både tekniker och kunder.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="ebe0a-107">Skapa serviceuppgifter på sidan **serviceuppgifter** och associera serviceuppgifterna med ett specifikt serviceavtal eller en specifik serviceorder genom att skapa serviceuppgiftsrelationer.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="ebe0a-108">Varje gång du skapar en serviceuppgiftsrelation kan du skapa följande:</span><span class="sxs-lookup"><span data-stu-id="ebe0a-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="ebe0a-109">Interna anteckningar om uppgiften, som detaljerade tekniska beskrivningar för uppgiften som är viktiga för teknikern att känna till.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="ebe0a-110">Externa anteckningar som kunden kan se.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-110">External notes that the customer can see.</span></span> <span data-ttu-id="ebe0a-111">De här anteckningarna kan innehålla en enklare förklaring av den uppgift som utförs enligt avtalet mellan kunden och serviceföretaget.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="ebe0a-112">När du har skapat en serviceuppgiftsrelation mellan en serviceuppgift och en serviceorder eller ett serviceavtal, kan du specificera denna serviceuppgift när du skapar serviceorderrader eller serviceavtalsrader för den aktuella serviceordern eller serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="ebe0a-113">När du genererar serviceorder från ett serviceavtal, kan du använda de serviceuppgifter som är tilldelade till respektive serviceavtalsrad för att gruppera serviceorderrader i serviceorder.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="ebe0a-114">Skapa en serviceuppgift</span><span class="sxs-lookup"><span data-stu-id="ebe0a-114">Create a service task</span></span>

1. <span data-ttu-id="ebe0a-115">Klicka på **servicehantering** \> **inställningar** \> **serviceuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="ebe0a-116">Skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-116">Create a new line.</span></span>
3. <span data-ttu-id="ebe0a-117">Ange service-ID och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="ebe0a-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="ebe0a-118">Example</span></span>

<span data-ttu-id="ebe0a-119">En tekniker måste utföra två jobb på en växellåda (serviceobjekt GB-1234) hos en kund.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="ebe0a-120">Ett serviceavtal skapas för kunden, och flera transaktioner associeras med jobben.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="ebe0a-121">Serviceavtalet och serviceavtalsraderna för de två jobben är enligt följande:</span><span class="sxs-lookup"><span data-stu-id="ebe0a-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="ebe0a-122">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="ebe0a-122">Service agreement</span></span>

| <span data-ttu-id="ebe0a-123">Project</span><span class="sxs-lookup"><span data-stu-id="ebe0a-123">Project</span></span> | <span data-ttu-id="ebe0a-124">Serviceavtal</span><span class="sxs-lookup"><span data-stu-id="ebe0a-124">Service agreement</span></span> | <span data-ttu-id="ebe0a-125">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ebe0a-125">Description</span></span>                                  | <span data-ttu-id="ebe0a-126">Grupp</span><span class="sxs-lookup"><span data-stu-id="ebe0a-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="ebe0a-127">9012</span><span class="sxs-lookup"><span data-stu-id="ebe0a-127">9012</span></span>    | <span data-ttu-id="ebe0a-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="ebe0a-128">000008\_001</span></span>       | <span data-ttu-id="ebe0a-129">Inspektion och planerat byte – GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="ebe0a-130">Bonus</span><span class="sxs-lookup"><span data-stu-id="ebe0a-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="ebe0a-131">Serviceavtalsrader</span><span class="sxs-lookup"><span data-stu-id="ebe0a-131">Service agreement lines</span></span>

| <span data-ttu-id="ebe0a-132">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ebe0a-132">Description</span></span>             | <span data-ttu-id="ebe0a-133">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="ebe0a-133">Transaction type</span></span> | <span data-ttu-id="ebe0a-134">Serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="ebe0a-134">Service object</span></span> | <span data-ttu-id="ebe0a-135">Serviceuppgift</span><span class="sxs-lookup"><span data-stu-id="ebe0a-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="ebe0a-136">Inspektion och rengöring</span><span class="sxs-lookup"><span data-stu-id="ebe0a-136">Inspection and cleaning</span></span> | <span data-ttu-id="ebe0a-137">Timme</span><span class="sxs-lookup"><span data-stu-id="ebe0a-137">Hour</span></span>             | <span data-ttu-id="ebe0a-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-138">GB-1234</span></span>        | <span data-ttu-id="ebe0a-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-139">I/C - GB1234</span></span> |
| <span data-ttu-id="ebe0a-140">Resor</span><span class="sxs-lookup"><span data-stu-id="ebe0a-140">Travel</span></span>                  | <span data-ttu-id="ebe0a-141">Expense</span><span class="sxs-lookup"><span data-stu-id="ebe0a-141">Expense</span></span>          | <span data-ttu-id="ebe0a-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-142">GB-1234</span></span>        | <span data-ttu-id="ebe0a-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-143">I/C - GB1234</span></span> |
| <span data-ttu-id="ebe0a-144">Material</span><span class="sxs-lookup"><span data-stu-id="ebe0a-144">Materials</span></span>               | <span data-ttu-id="ebe0a-145">Artikel</span><span class="sxs-lookup"><span data-stu-id="ebe0a-145">Item</span></span>             | <span data-ttu-id="ebe0a-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-146">GB-1234</span></span>        | <span data-ttu-id="ebe0a-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-147">I/C - GB1234</span></span> |
| <span data-ttu-id="ebe0a-148">Planerat byte</span><span class="sxs-lookup"><span data-stu-id="ebe0a-148">Routine replacement</span></span>     | <span data-ttu-id="ebe0a-149">Timme</span><span class="sxs-lookup"><span data-stu-id="ebe0a-149">Hour</span></span>             | <span data-ttu-id="ebe0a-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-150">GB-1234</span></span>        | <span data-ttu-id="ebe0a-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-151">RR - GB1234</span></span>  |
| <span data-ttu-id="ebe0a-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="ebe0a-152">GR-1</span></span>                    | <span data-ttu-id="ebe0a-153">Artikel</span><span class="sxs-lookup"><span data-stu-id="ebe0a-153">Item</span></span>             | <span data-ttu-id="ebe0a-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-154">GB-1234</span></span>        | <span data-ttu-id="ebe0a-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-155">RR - GB1234</span></span>  |
| <span data-ttu-id="ebe0a-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="ebe0a-156">GR-5</span></span>                    | <span data-ttu-id="ebe0a-157">Artikel</span><span class="sxs-lookup"><span data-stu-id="ebe0a-157">Item</span></span>             | <span data-ttu-id="ebe0a-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-158">GB-1234</span></span>        | <span data-ttu-id="ebe0a-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-159">RR - GB1234</span></span>  |

<span data-ttu-id="ebe0a-160">Det finns två serviceuppgifter kopplade till serviceavtalsraderna för de två jobben.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="ebe0a-161">Serviceuppgifterna fastställer vilka transaktioner som tillhör respektive jobb.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="ebe0a-162">I det första fallet identifierar serviceuppgiften I/C - GB1234 alla serviceavtalsrader som ingår i inspektionen samt rengöring av objekt GB-1234.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="ebe0a-163">I det andra fallet identifierar serviceuppgiften RR - GB1234 alla serviceavtalsrader som ingår i ett jobb med planerade byten.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="ebe0a-164">Följande serviceuppgiftsrelationer kopplar serviceuppgifterna till det specifika avtalet:</span><span class="sxs-lookup"><span data-stu-id="ebe0a-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="ebe0a-165">Serviceuppgifter</span><span class="sxs-lookup"><span data-stu-id="ebe0a-165">Service tasks</span></span>

| <span data-ttu-id="ebe0a-166">Serviceuppgift</span><span class="sxs-lookup"><span data-stu-id="ebe0a-166">Service task</span></span> | <span data-ttu-id="ebe0a-167">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ebe0a-167">Description</span></span>                             | <span data-ttu-id="ebe0a-168">Intern anteckning</span><span class="sxs-lookup"><span data-stu-id="ebe0a-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="ebe0a-169">Extern anteckning</span><span class="sxs-lookup"><span data-stu-id="ebe0a-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="ebe0a-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-170">I/C - GB1234</span></span> | <span data-ttu-id="ebe0a-171">Inspektion av växellåda GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="ebe0a-172">Visuell och mekanisk inspektion och rengöring av växellådan GB1234.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="ebe0a-173">Rutininspektion av växellåda</span><span class="sxs-lookup"><span data-stu-id="ebe0a-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="ebe0a-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-174">RR - GB1234</span></span>  | <span data-ttu-id="ebe0a-175">Planerat byte av delar i GB-1234</span><span class="sxs-lookup"><span data-stu-id="ebe0a-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="ebe0a-176">Planerade servicebyten av komponenterna GR-1 och GR-5 (för växellådor som tillverkats före 2002, byt även komponenten GR-2)</span><span class="sxs-lookup"><span data-stu-id="ebe0a-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="ebe0a-177">Planerat byte av reservdelar</span><span class="sxs-lookup"><span data-stu-id="ebe0a-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="ebe0a-178">Gruppera serviceorder</span><span class="sxs-lookup"><span data-stu-id="ebe0a-178">Group service orders</span></span>

<span data-ttu-id="ebe0a-179">När du automatiskt skapar serviceorder kan du använda serviceuppgifter som ett grupperingskriterium.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="ebe0a-180">Om du vill gruppera serviceorder efter serviceuppgifter ska du på serviceavtalet definiera att serviceorder som baseras på serviceavtalet ska grupperas efter serviceuppgifts-ID som ursprungligt grupperingskriterium.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="ebe0a-181">**Gruppera efter serviceuppgift**</span><span class="sxs-lookup"><span data-stu-id="ebe0a-181">**Group by service task**</span></span>

1. <span data-ttu-id="ebe0a-182">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="ebe0a-183">På fliken **inställningar** välj **per serviceuppgift** i fältet för **kombinera serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="ebe0a-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>


