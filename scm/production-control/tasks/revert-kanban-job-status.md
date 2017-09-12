--- 
title: "Återställ kanban-jobbstatus"
description: "Den här proceduren är avsedd för att återställa en felaktig kanban-jobbstatus."
author: YuyuScheller
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
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 55d359232da5f3087b1e6baed182a20da09aeff7
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="e730f-103">Återställ kanban-jobbstatus</span><span class="sxs-lookup"><span data-stu-id="e730f-103">Revert kanban job status</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e730f-104">Den här proceduren är avsedd för att återställa en felaktig kanban-jobbstatus.</span><span class="sxs-lookup"><span data-stu-id="e730f-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="e730f-105">Detta är användbart om maskinoperatören uppdaterar fel jobb eller ställer in fel status av misstag.</span><span class="sxs-lookup"><span data-stu-id="e730f-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="e730f-106">I den här proceduren registreras ett kanban-jobb som förberett av misstag och statusvärdet återställas.</span><span class="sxs-lookup"><span data-stu-id="e730f-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="e730f-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="e730f-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e730f-108">Den här proceduren är avsedd för den arbetsansvarige eller maskinoperatören som arbetar i ett lean manufacturing-företag.</span><span class="sxs-lookup"><span data-stu-id="e730f-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="e730f-109">Öppna processtavlan för arbetsgruppen</span><span class="sxs-lookup"><span data-stu-id="e730f-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="e730f-110">Gå till Kanban-tavla för processjobb.</span><span class="sxs-lookup"><span data-stu-id="e730f-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="e730f-111">I fältet Arbetsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="e730f-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="e730f-112">Välj arbetsgrupp 1260.</span><span class="sxs-lookup"><span data-stu-id="e730f-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="e730f-113">Förbereda kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="e730f-113">Prepare kanban job</span></span>
1. <span data-ttu-id="e730f-114">Klicka på Förbered.</span><span class="sxs-lookup"><span data-stu-id="e730f-114">Click Prepare.</span></span>
    * <span data-ttu-id="e730f-115">Om du inte kan klicka på Förbered eftersom den gråas ut, se till att det valda kanban-jobbet har statusen Planerad som anges med en tom kanban-ikon.</span><span class="sxs-lookup"><span data-stu-id="e730f-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="e730f-116">Om Förbered misslyckas, se till att allt material i plocklistan är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="e730f-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="e730f-117">I listan, välj det förberedda jobbet.</span><span class="sxs-lookup"><span data-stu-id="e730f-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="e730f-118">Välj det första jobbet du precis har förberett.</span><span class="sxs-lookup"><span data-stu-id="e730f-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="e730f-119">Observera att jobbstatusen förbereds, vilket anges med en triangel i kanban-ikonen.</span><span class="sxs-lookup"><span data-stu-id="e730f-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="e730f-120">Återställa statusen för det förberedda kanban-jobbet</span><span class="sxs-lookup"><span data-stu-id="e730f-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="e730f-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e730f-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e730f-122">Välj det första jobbet som har förberetts.</span><span class="sxs-lookup"><span data-stu-id="e730f-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="e730f-123">I åtgärdsfönstret, klicka på Tillverka.</span><span class="sxs-lookup"><span data-stu-id="e730f-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="e730f-124">Klicka på Återställ status.</span><span class="sxs-lookup"><span data-stu-id="e730f-124">Click Revert status.</span></span>
    * <span data-ttu-id="e730f-125">Du kan använda en alternativ kanban-regel när följande villkor är sant: återanskaffningsstrategin är densamma för båda reglerna.</span><span class="sxs-lookup"><span data-stu-id="e730f-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="e730f-126">- Den version av produktionsflödet är densamma för båda regler.</span><span class="sxs-lookup"><span data-stu-id="e730f-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="e730f-127">- Produkten som levereras är densamma för båda regler.</span><span class="sxs-lookup"><span data-stu-id="e730f-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="e730f-128">- Vissa nedströmsaktiviteter som konfigurerats för den senaste aktiviteten för kanban-reglerna måste vara samma för båda regler.</span><span class="sxs-lookup"><span data-stu-id="e730f-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="e730f-129">- Samma levererade lagerdimensioner måste ha konfigurerats för båda reglerna.</span><span class="sxs-lookup"><span data-stu-id="e730f-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="e730f-130">- Statusen för materialhanteringsenheten måste vara Inte tilldelat.</span><span class="sxs-lookup"><span data-stu-id="e730f-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="e730f-131">- Konfigurationen för händelse-kanbans måste vara samma.</span><span class="sxs-lookup"><span data-stu-id="e730f-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="e730f-132">Kontrollera att den nya statusen är Planerat.</span><span class="sxs-lookup"><span data-stu-id="e730f-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="e730f-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e730f-133">Click OK.</span></span>
5. <span data-ttu-id="e730f-134">Avmarkera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e730f-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="e730f-135">Välj samma jobb.</span><span class="sxs-lookup"><span data-stu-id="e730f-135">Select the same job.</span></span>  
    * <span data-ttu-id="e730f-136">Observera att jobbstatusen för kanban-jobbet återställs till Planerat, vilket anges med en tom kanban-ikon.</span><span class="sxs-lookup"><span data-stu-id="e730f-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  


