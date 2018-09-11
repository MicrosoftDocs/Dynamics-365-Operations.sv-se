--- 
title: "Skapa en kanban-regel för flera aktiviteter"
description: "Den här proceduren visar hur du skapar en kanban-regel som omfattar flera aktiviteter från ett produktionsflöde."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 16aac6301b6534c4bf95184097ff5fc1b95fe795
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="21eaf-103">Skapa en kanban-regel för flera aktiviteter</span><span class="sxs-lookup"><span data-stu-id="21eaf-103">Create a kanban rule for multiple activities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="21eaf-104">Den här proceduren visar hur du skapar en kanban-regel som omfattar flera aktiviteter från ett produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="21eaf-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="21eaf-105">Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.</span><span class="sxs-lookup"><span data-stu-id="21eaf-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="21eaf-106">Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.</span><span class="sxs-lookup"><span data-stu-id="21eaf-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="21eaf-107">Skapa en ny kanban-regel</span><span class="sxs-lookup"><span data-stu-id="21eaf-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="21eaf-108">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="21eaf-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="21eaf-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="21eaf-109">Click New.</span></span>
3. <span data-ttu-id="21eaf-110">Välj Tidsplanerat i fältet Återanskaffningsstrategi.</span><span class="sxs-lookup"><span data-stu-id="21eaf-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="21eaf-111">Ange eller välj ett värde i fältet Första planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="21eaf-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="21eaf-112">Välj SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="21eaf-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="21eaf-113">Markera kryssrutan Flera aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="21eaf-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="21eaf-114">Syftet är att inkludera mer än en aktivitet i kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="21eaf-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="21eaf-115">Du kan välja en sökväg i produktionsflödet när du väljer den senaste planaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="21eaf-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="21eaf-116">Ange eller välj ett värde i fältet Sista planaktivitet.</span><span class="sxs-lookup"><span data-stu-id="21eaf-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="21eaf-117">Välj SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="21eaf-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="21eaf-118">När du har valt värdet öppnas en sida automatiskt.</span><span class="sxs-lookup"><span data-stu-id="21eaf-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="21eaf-119">Markera kanban-flödet SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="21eaf-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="21eaf-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="21eaf-120">Click OK.</span></span>  
7. <span data-ttu-id="21eaf-121">Expandera avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="21eaf-121">Expand the Details section.</span></span>
8. <span data-ttu-id="21eaf-122">Ange eller välj ett värde i fältet Produkt.</span><span class="sxs-lookup"><span data-stu-id="21eaf-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="21eaf-123">Välj artikel L0006.</span><span class="sxs-lookup"><span data-stu-id="21eaf-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="21eaf-124">Skapa kanban och visa jobb</span><span class="sxs-lookup"><span data-stu-id="21eaf-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="21eaf-125">Expandera avsnittet Kanbans.</span><span class="sxs-lookup"><span data-stu-id="21eaf-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="21eaf-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="21eaf-126">Click Add.</span></span>
3. <span data-ttu-id="21eaf-127">Ange "1" i fältet Antal nya kanban.</span><span class="sxs-lookup"><span data-stu-id="21eaf-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="21eaf-128">Detta skapar en kanban.</span><span class="sxs-lookup"><span data-stu-id="21eaf-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="21eaf-129">Ange produktkvantiteten till "3".</span><span class="sxs-lookup"><span data-stu-id="21eaf-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="21eaf-130">Kanban kommer att bearbeta 3 produkter.</span><span class="sxs-lookup"><span data-stu-id="21eaf-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="21eaf-131">Ange datum och tid i fältet Förfallodatum- och tid.</span><span class="sxs-lookup"><span data-stu-id="21eaf-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="21eaf-132">Du kan ange Idag.</span><span class="sxs-lookup"><span data-stu-id="21eaf-132">You can enter Today.</span></span>  
6. <span data-ttu-id="21eaf-133">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="21eaf-133">Click Create.</span></span>
7. <span data-ttu-id="21eaf-134">Klicka på Detaljer.</span><span class="sxs-lookup"><span data-stu-id="21eaf-134">Click Details.</span></span>
    * <span data-ttu-id="21eaf-135">Observera att kanban har två processjobb från produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="21eaf-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="21eaf-136">Det första är SpeakerAssemblyAndPolish och det andra är SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="21eaf-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="21eaf-137">Detta är det sista steget!</span><span class="sxs-lookup"><span data-stu-id="21eaf-137">This is the last step!</span></span>  


