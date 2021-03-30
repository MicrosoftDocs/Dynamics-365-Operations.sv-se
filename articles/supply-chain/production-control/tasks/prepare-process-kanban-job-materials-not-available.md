---
title: Förbered ett kanban-processjobb när material är inte tillgängliga för arbetsgruppen
description: I den här proceduren ligger fokus på att förbereda ett kanban-processjobb när en del av materialet inte är tillgängligt för arbetsgruppen och det därför är nödvändigt att plocka material från lagerstället.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 742ac97c4b730d3552f532c53409ef54320b263a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204578"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="5a70e-103">Förbered ett kanban-processjobb när material är inte tillgängliga för arbetsgruppen</span><span class="sxs-lookup"><span data-stu-id="5a70e-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5a70e-104">I den här proceduren ligger fokus på att förbereda ett kanban-processjobb när en del av materialet inte är tillgängligt för arbetsgruppen och det därför är nödvändigt att plocka material från lagerstället.</span><span class="sxs-lookup"><span data-stu-id="5a70e-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="5a70e-105">Proceduren "Förbered ett kanban-processjobb när material är tillgängliga" är en förutsättning när du skapar den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5a70e-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="5a70e-106">Den här proceduren är avsedd för maskinoperatören.</span><span class="sxs-lookup"><span data-stu-id="5a70e-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="5a70e-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5a70e-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="5a70e-108">Gå till Produktionskontroll > Kanban > Kanban-tavla för processjobb.</span><span class="sxs-lookup"><span data-stu-id="5a70e-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="5a70e-109">Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5a70e-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="5a70e-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5a70e-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5a70e-111">Välj arbetsgrupp 1250.</span><span class="sxs-lookup"><span data-stu-id="5a70e-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="5a70e-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5a70e-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5a70e-113">Välj Kanban 000356.</span><span class="sxs-lookup"><span data-stu-id="5a70e-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="5a70e-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5a70e-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5a70e-115">I listan avmarkerar du rad 4.</span><span class="sxs-lookup"><span data-stu-id="5a70e-115">In the list, deselect row 4.</span></span> <span data-ttu-id="5a70e-116">eller rad 4 om du inte har slutfört uppgiften "Förbered ett kanban-processjobb när material är tillgängliga".</span><span class="sxs-lookup"><span data-stu-id="5a70e-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="5a70e-117">Växla expansionen av avsnittet Plocklista.</span><span class="sxs-lookup"><span data-stu-id="5a70e-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="5a70e-118">Ikonen Ingen post i tillförselstatusen visar att det saknas 48 st. av artikeln P0002 för arbetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="5a70e-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="5a70e-119">Överför material till arbetsgrupp</span><span class="sxs-lookup"><span data-stu-id="5a70e-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="5a70e-120">Växla expansionen av avsnittet Överför jobb.</span><span class="sxs-lookup"><span data-stu-id="5a70e-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="5a70e-121">Använd snabbfiltret för att filtrera på fältet Artikelnummer med värdet P0002.</span><span class="sxs-lookup"><span data-stu-id="5a70e-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="5a70e-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="5a70e-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="5a70e-123">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="5a70e-123">Click Start.</span></span>
    * <span data-ttu-id="5a70e-124">Överföring pågår.</span><span class="sxs-lookup"><span data-stu-id="5a70e-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="5a70e-125">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="5a70e-125">Click Complete.</span></span>
    * <span data-ttu-id="5a70e-126">Artikeln P0002 är nu tillgänglig i plocklistan för kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="5a70e-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="5a70e-127">Det innebär att vi kan förbereda kanban med alla nödvändiga material.</span><span class="sxs-lookup"><span data-stu-id="5a70e-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="5a70e-128">Klicka på Förbered.</span><span class="sxs-lookup"><span data-stu-id="5a70e-128">Click Prepare.</span></span>
    * <span data-ttu-id="5a70e-129">Lägg märke till att en ikon i jobbstatusen indikerar att jobbet nu är klart.</span><span class="sxs-lookup"><span data-stu-id="5a70e-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]