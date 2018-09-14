--- 
title: "Ändra kanban-regel för ett processjobb"
description: "Den här proceduren fokuserar på att ändra den använda kanban-regeln för en viss kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 38d9ff0a7d6aeb0a589fd6b9ab34b818c46644cc
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="1577e-103">Ändra kanban-regel för ett processjobb</span><span class="sxs-lookup"><span data-stu-id="1577e-103">Change kanban rules for a process job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1577e-104">Den här proceduren fokuserar på att ändra den använda kanban-regeln för en viss kanban.</span><span class="sxs-lookup"><span data-stu-id="1577e-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="1577e-105">Det här är användbart för att utjämna beläggningsresurser eller i händelse av ett fel.</span><span class="sxs-lookup"><span data-stu-id="1577e-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="1577e-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="1577e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1577e-107">Den här proceduren är avsedd för planeraren som arbetar på ett lean manufacturing företag och är ansvarig för värdeströmmen.</span><span class="sxs-lookup"><span data-stu-id="1577e-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="1577e-108">Kopiera kanban-regel</span><span class="sxs-lookup"><span data-stu-id="1577e-108">Copy kanban rule</span></span>
1. <span data-ttu-id="1577e-109">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="1577e-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="1577e-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1577e-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1577e-111">Välj händelsen Kanban-regel 000022 för L0001.</span><span class="sxs-lookup"><span data-stu-id="1577e-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="1577e-112">Klicka på Duplicera kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="1577e-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="1577e-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1577e-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="1577e-114">Ändra kanban-regel</span><span class="sxs-lookup"><span data-stu-id="1577e-114">Change kanban rule</span></span>
1. <span data-ttu-id="1577e-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1577e-115">Close the page.</span></span>
2. <span data-ttu-id="1577e-116">Gå till Kanban-jobbplanering.</span><span class="sxs-lookup"><span data-stu-id="1577e-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="1577e-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="1577e-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1577e-118">Markera raden med Kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="1577e-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="1577e-119">Klicka på Använd alternativ kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="1577e-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="1577e-120">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="1577e-120">Click Next.</span></span>
6. <span data-ttu-id="1577e-121">I fältet Kanban-regel, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="1577e-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="1577e-122">Välj kanban-regeln som har skapats tidigare.</span><span class="sxs-lookup"><span data-stu-id="1577e-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="1577e-123">Detta är kanban-regeln med det högsta numret.</span><span class="sxs-lookup"><span data-stu-id="1577e-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="1577e-124">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="1577e-124">Click Finish.</span></span>
    * <span data-ttu-id="1577e-125">Nu använder kanban-jobbet en annan kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="1577e-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="1577e-126">Det kan vara bra för att utjämna beläggningen av arbetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="1577e-126">This can be useful to level load work cells.</span></span>  


