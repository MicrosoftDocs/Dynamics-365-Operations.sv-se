---
title: Överför material med kanban-jobb
description: Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2db7b9fb960beb5b4a851aabb9f28a0f9e3d3da
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571460"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="d4493-103">Överför material med kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="d4493-103">Transfer materials with kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4493-104">Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material.</span><span class="sxs-lookup"><span data-stu-id="d4493-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="d4493-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d4493-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d4493-106">Den här proceduren är avsedd för lagerarbetaren.</span><span class="sxs-lookup"><span data-stu-id="d4493-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="d4493-107">Visa överföringsjobb</span><span class="sxs-lookup"><span data-stu-id="d4493-107">Display transfer jobs</span></span>
1. <span data-ttu-id="d4493-108">Gå till tillverkningskontroll > Kanban > Kanban board för överföringsjobb.</span><span class="sxs-lookup"><span data-stu-id="d4493-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="d4493-109">Expandera eller komprimera avsnittet Filter.</span><span class="sxs-lookup"><span data-stu-id="d4493-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="d4493-110">I avsnittet Filter kan du ange vilka jobb som du vill visa genom att filtrera efter produktionsflöde, aktivitetsnamn, från lagerställe och plats och till lagerställe och plats.</span><span class="sxs-lookup"><span data-stu-id="d4493-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="d4493-111">Skriv "11" i fältet Från lagerställe.</span><span class="sxs-lookup"><span data-stu-id="d4493-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="d4493-112">Skriv "12" i fältet Till plats.</span><span class="sxs-lookup"><span data-stu-id="d4493-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="d4493-113">Starta ett överföringsjobb</span><span class="sxs-lookup"><span data-stu-id="d4493-113">Start a transfer job</span></span>
1. <span data-ttu-id="d4493-114">Avmarkera den valda raden i listan - om det finns någon sådan.</span><span class="sxs-lookup"><span data-stu-id="d4493-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="d4493-115">Väl rad 4 i listan.</span><span class="sxs-lookup"><span data-stu-id="d4493-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="d4493-116">Välj det första jobbet med statusen Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="d4493-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="d4493-117">Kontrollera att det här är den enda valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="d4493-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="d4493-118">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="d4493-118">Click Start.</span></span>
    * <span data-ttu-id="d4493-119">Observera att en ikon indikerar att jobbet startas.</span><span class="sxs-lookup"><span data-stu-id="d4493-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="d4493-120">Välj ett andra överföringsjobb och ändra kvantiteten</span><span class="sxs-lookup"><span data-stu-id="d4493-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="d4493-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4493-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d4493-122">Du kan välja flera jobb, men nu väljer du rad 5.</span><span class="sxs-lookup"><span data-stu-id="d4493-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="d4493-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d4493-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d4493-124">Kontrollera att jobbet i det föregående steget är det enda som har valts.</span><span class="sxs-lookup"><span data-stu-id="d4493-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="d4493-125">Avmarkera alla andra jobb.</span><span class="sxs-lookup"><span data-stu-id="d4493-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="d4493-126">Observera värdet i fältet Jobbkvantitet så att du kan referera till det senare</span><span class="sxs-lookup"><span data-stu-id="d4493-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="d4493-127">Ange jobbkvantiteten till "30".</span><span class="sxs-lookup"><span data-stu-id="d4493-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="d4493-128">Meddelandet OBS!</span><span class="sxs-lookup"><span data-stu-id="d4493-128">Notice the warning!</span></span> <span data-ttu-id="d4493-129">Du kan inte överföra 30.</span><span class="sxs-lookup"><span data-stu-id="d4493-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="d4493-130">Enligt inställningarna för kanban-regel kan du bara överföra den ursprungliga kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="d4493-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="d4493-131">Använd värdet som noterades tidigare i fältet Jobbkvantitet</span><span class="sxs-lookup"><span data-stu-id="d4493-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="d4493-132">Ange jobbkvantiteten till det föregående värdet.</span><span class="sxs-lookup"><span data-stu-id="d4493-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="d4493-133">Starta andra överföringsjobbet</span><span class="sxs-lookup"><span data-stu-id="d4493-133">Start the second transfer job</span></span>
1. <span data-ttu-id="d4493-134">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="d4493-134">Click Start.</span></span>
    * <span data-ttu-id="d4493-135">Då startas överföringen av jobbet på rad 5.</span><span class="sxs-lookup"><span data-stu-id="d4493-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="d4493-136">Slutför båda överföringsjobben</span><span class="sxs-lookup"><span data-stu-id="d4493-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="d4493-137">Väl rad 4 i listan.</span><span class="sxs-lookup"><span data-stu-id="d4493-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="d4493-138">Nu är två överföringsjobb markerade på rad 4 och rad 5.</span><span class="sxs-lookup"><span data-stu-id="d4493-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="d4493-139">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="d4493-139">Click Complete.</span></span>
    * <span data-ttu-id="d4493-140">Detta slutför överföringen av båda jobben.</span><span class="sxs-lookup"><span data-stu-id="d4493-140">This will complete the transfer of both jobs.</span></span>  

