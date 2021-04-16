---
title: Överför material med kanban-jobb
description: Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46009f09f6e843c45f50351963ad01419e24a878
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831852"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="dd921-103">Överför material med kanban-jobb</span><span class="sxs-lookup"><span data-stu-id="dd921-103">Transfer materials with kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dd921-104">Den här proceduren fokuserar på att köra ett uttagskanban-jobb för att överföra material.</span><span class="sxs-lookup"><span data-stu-id="dd921-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="dd921-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="dd921-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="dd921-106">Den här proceduren är avsedd för lagerarbetaren.</span><span class="sxs-lookup"><span data-stu-id="dd921-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="dd921-107">Visa överföringsjobb</span><span class="sxs-lookup"><span data-stu-id="dd921-107">Display transfer jobs</span></span>
1. <span data-ttu-id="dd921-108">Gå till tillverkningskontroll > Kanban > Kanban board för överföringsjobb.</span><span class="sxs-lookup"><span data-stu-id="dd921-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="dd921-109">Expandera eller komprimera avsnittet Filter.</span><span class="sxs-lookup"><span data-stu-id="dd921-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="dd921-110">I avsnittet Filter kan du ange vilka jobb som du vill visa genom att filtrera efter produktionsflöde, aktivitetsnamn, från lagerställe och plats och till lagerställe och plats.</span><span class="sxs-lookup"><span data-stu-id="dd921-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="dd921-111">Skriv "11" i fältet Från lagerställe.</span><span class="sxs-lookup"><span data-stu-id="dd921-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="dd921-112">Skriv "12" i fältet Till plats.</span><span class="sxs-lookup"><span data-stu-id="dd921-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="dd921-113">Starta ett överföringsjobb</span><span class="sxs-lookup"><span data-stu-id="dd921-113">Start a transfer job</span></span>
1. <span data-ttu-id="dd921-114">Avmarkera den valda raden i listan - om det finns någon sådan.</span><span class="sxs-lookup"><span data-stu-id="dd921-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="dd921-115">Väl rad 4 i listan.</span><span class="sxs-lookup"><span data-stu-id="dd921-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="dd921-116">Välj det första jobbet med statusen Inte planerad.</span><span class="sxs-lookup"><span data-stu-id="dd921-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="dd921-117">Kontrollera att det här är den enda valda jobbet.</span><span class="sxs-lookup"><span data-stu-id="dd921-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="dd921-118">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="dd921-118">Click Start.</span></span>
    * <span data-ttu-id="dd921-119">Observera att en ikon indikerar att jobbet startas.</span><span class="sxs-lookup"><span data-stu-id="dd921-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="dd921-120">Välj ett andra överföringsjobb och ändra kvantiteten</span><span class="sxs-lookup"><span data-stu-id="dd921-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="dd921-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dd921-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dd921-122">Du kan välja flera jobb, men nu väljer du rad 5.</span><span class="sxs-lookup"><span data-stu-id="dd921-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="dd921-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="dd921-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dd921-124">Kontrollera att jobbet i det föregående steget är det enda som har valts.</span><span class="sxs-lookup"><span data-stu-id="dd921-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="dd921-125">Avmarkera alla andra jobb.</span><span class="sxs-lookup"><span data-stu-id="dd921-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="dd921-126">Observera värdet i fältet Jobbkvantitet så att du kan referera till det senare</span><span class="sxs-lookup"><span data-stu-id="dd921-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="dd921-127">Ange jobbkvantiteten till "30".</span><span class="sxs-lookup"><span data-stu-id="dd921-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="dd921-128">Meddelandet OBS!</span><span class="sxs-lookup"><span data-stu-id="dd921-128">Notice the warning!</span></span> <span data-ttu-id="dd921-129">Du kan inte överföra 30.</span><span class="sxs-lookup"><span data-stu-id="dd921-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="dd921-130">Enligt inställningarna för kanban-regel kan du bara överföra den ursprungliga kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="dd921-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="dd921-131">Använd värdet som noterades tidigare i fältet Jobbkvantitet</span><span class="sxs-lookup"><span data-stu-id="dd921-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="dd921-132">Ange jobbkvantiteten till det föregående värdet.</span><span class="sxs-lookup"><span data-stu-id="dd921-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="dd921-133">Starta andra överföringsjobbet</span><span class="sxs-lookup"><span data-stu-id="dd921-133">Start the second transfer job</span></span>
1. <span data-ttu-id="dd921-134">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="dd921-134">Click Start.</span></span>
    * <span data-ttu-id="dd921-135">Då startas överföringen av jobbet på rad 5.</span><span class="sxs-lookup"><span data-stu-id="dd921-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="dd921-136">Slutför båda överföringsjobben</span><span class="sxs-lookup"><span data-stu-id="dd921-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="dd921-137">Väl rad 4 i listan.</span><span class="sxs-lookup"><span data-stu-id="dd921-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="dd921-138">Nu är två överföringsjobb markerade på rad 4 och rad 5.</span><span class="sxs-lookup"><span data-stu-id="dd921-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="dd921-139">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="dd921-139">Click Complete.</span></span>
    * <span data-ttu-id="dd921-140">Detta slutför överföringen av båda jobben.</span><span class="sxs-lookup"><span data-stu-id="dd921-140">This will complete the transfer of both jobs.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]