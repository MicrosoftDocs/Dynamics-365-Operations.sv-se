--- 
title: "Kör kanban-processjobb"
description: "Den här proceduren är avsedd för att köra kanban-processjobb."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 62be1f116dfecbc4c6ba11053b94efc874baa3e3
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="5be48-103">Kör kanban-processjobb</span><span class="sxs-lookup"><span data-stu-id="5be48-103">Execute kanban process jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5be48-104">Den här proceduren är avsedd för att köra kanban-processjobb.</span><span class="sxs-lookup"><span data-stu-id="5be48-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="5be48-105">Det första jobbet är slutfört med den förväntade kvantiteten och har inga fel.</span><span class="sxs-lookup"><span data-stu-id="5be48-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="5be48-106">Det andra jobbet slutförs med fel.</span><span class="sxs-lookup"><span data-stu-id="5be48-106">The second job is completed with errors.</span></span> <span data-ttu-id="5be48-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5be48-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="5be48-108">Den här proceduren är avsedd för maskinoperatören.</span><span class="sxs-lookup"><span data-stu-id="5be48-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="5be48-109">Välj ett kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="5be48-109">Select a kanban job</span></span>
1. <span data-ttu-id="5be48-110">Gå till Produktionskontroll > Kanban > Kanban-tavla för processjobb.</span><span class="sxs-lookup"><span data-stu-id="5be48-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="5be48-111">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5be48-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5be48-112">Klicka på raden med resursgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="5be48-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="5be48-113">Detta filtrerar jobblistan så att endast jobben för arbetsgrupp 1250 visas.</span><span class="sxs-lookup"><span data-stu-id="5be48-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="5be48-114">Markera raden som har jobbstatusen Planerad.</span><span class="sxs-lookup"><span data-stu-id="5be48-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="5be48-115">Slutför ett jobb med förväntad kvantitet</span><span class="sxs-lookup"><span data-stu-id="5be48-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="5be48-116">Visa eller dölj avsnittet Detaljer.</span><span class="sxs-lookup"><span data-stu-id="5be48-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="5be48-117">Det här avsnittet visar viktig information om kortnummer, artikelnummer, beställd kvantitet och aktivitetsnamn.</span><span class="sxs-lookup"><span data-stu-id="5be48-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="5be48-118">Visa eller dölj avsnittet Produktionsinstruktioner.</span><span class="sxs-lookup"><span data-stu-id="5be48-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="5be48-119">Det här avsnittet visar produktioninstruktioner för aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="5be48-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="5be48-120">Instruktionerna kan vara text, bilder, ritningar och andra dokument.</span><span class="sxs-lookup"><span data-stu-id="5be48-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="5be48-121">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="5be48-121">Click Start.</span></span>
    * <span data-ttu-id="5be48-122">Välj ett jobb som inte har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5be48-122">Select a job that is not completed.</span></span> <span data-ttu-id="5be48-123">Använd statusikoner i fältet Jobbstatus för att visa jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="5be48-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="5be48-124">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="5be48-124">Click Complete.</span></span>
    * <span data-ttu-id="5be48-125">Jobbet är slutfört med den förväntade kvaliteten.</span><span class="sxs-lookup"><span data-stu-id="5be48-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="5be48-126">Slutför ett jobb med fel</span><span class="sxs-lookup"><span data-stu-id="5be48-126">Complete a job with errors</span></span>
1. <span data-ttu-id="5be48-127">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="5be48-127">Click Start.</span></span>
    * <span data-ttu-id="5be48-128">När ett jobb utförs, markeras nästa jobb i listan automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5be48-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="5be48-129">Detta beror på att du inte behöver välja ett jobb innan du klickar på Start.</span><span class="sxs-lookup"><span data-stu-id="5be48-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="5be48-130">I åtgärdsfönstret, klicka på Tillverka.</span><span class="sxs-lookup"><span data-stu-id="5be48-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="5be48-131">Klicka på Slutfört (detaljer).</span><span class="sxs-lookup"><span data-stu-id="5be48-131">Click Complete (details).</span></span>
4. <span data-ttu-id="5be48-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5be48-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="5be48-133">Ange ett nummer i fältet Felkvantitet.</span><span class="sxs-lookup"><span data-stu-id="5be48-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="5be48-134">Ange ett värde i fältet Godkänd kvantitet.</span><span class="sxs-lookup"><span data-stu-id="5be48-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="5be48-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5be48-135">Click OK.</span></span>


