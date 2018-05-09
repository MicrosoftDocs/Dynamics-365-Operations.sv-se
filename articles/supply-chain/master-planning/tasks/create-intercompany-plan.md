--- 
title: Skapa en koncernintern plan
description: "I den här proceduren visas hur du skapar en koncernintern plan."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 287741ce871f7f7cff7c2e2159b28ec509058240
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="288f6-103">Skapa en koncernintern plan</span><span class="sxs-lookup"><span data-stu-id="288f6-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="288f6-104">I den här proceduren visas hur du skapar en koncernintern plan.</span><span class="sxs-lookup"><span data-stu-id="288f6-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="288f6-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="288f6-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="288f6-106">Skapa en koncernintern planeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="288f6-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="288f6-107">Gå till koncerninterna planeringsgrupper.</span><span class="sxs-lookup"><span data-stu-id="288f6-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="288f6-108">Huvudplanering > Inställningar > Koncerninterna planeringsgrupper</span><span class="sxs-lookup"><span data-stu-id="288f6-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="288f6-109">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="288f6-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="288f6-110">Filtrera till exempel på värdet "10" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="288f6-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="288f6-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="288f6-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="288f6-112">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="288f6-112">Click Delete.</span></span>
    * <span data-ttu-id="288f6-113">Det här steget är nödvändigt för att förkorta den koncerninterna planläggningskörningen.</span><span class="sxs-lookup"><span data-stu-id="288f6-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="288f6-114">Den koncerninterna planeringen kör huvudplaneringen i samtliga företag i en planläggningsgrupp, med början från den lägsta schemaläggningssekvensen.</span><span class="sxs-lookup"><span data-stu-id="288f6-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="288f6-115">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="288f6-115">Click Yes.</span></span>
6. <span data-ttu-id="288f6-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="288f6-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="288f6-117">Skapa en koncernintern plan</span><span class="sxs-lookup"><span data-stu-id="288f6-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="288f6-118">Klicka på Intercompany master planning.</span><span class="sxs-lookup"><span data-stu-id="288f6-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="288f6-119">Detta ligger på arbetsytan Master planning.</span><span class="sxs-lookup"><span data-stu-id="288f6-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="288f6-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intercompany planning group.</span><span class="sxs-lookup"><span data-stu-id="288f6-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="288f6-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="288f6-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="288f6-122">Välj koncernintern planeringsgrupp 10.</span><span class="sxs-lookup"><span data-stu-id="288f6-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="288f6-123">Ange "2" i fältet "Number of intercompany planning iterations".</span><span class="sxs-lookup"><span data-stu-id="288f6-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="288f6-124">Koncernintern planeringsgrupp 10 har två medlemmar.</span><span class="sxs-lookup"><span data-stu-id="288f6-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="288f6-125">Om du vill sprida förskjutningarna från källföretaget (USMF) till kundföretaget (DEMF ) måste du köra koncerninternt i båda företag två gånger.</span><span class="sxs-lookup"><span data-stu-id="288f6-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="288f6-126">Den första upprepningen sprider begäran och identifierar förskjutningarna i källföretaget (USMF).</span><span class="sxs-lookup"><span data-stu-id="288f6-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="288f6-127">Den andra upprepningen sprider förskjutningarna från USMF till DEMF.</span><span class="sxs-lookup"><span data-stu-id="288f6-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="288f6-128">Välj ett alternativ i fältet First iteration.</span><span class="sxs-lookup"><span data-stu-id="288f6-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="288f6-129">Välj "Regeneration" i fältet First iteration.</span><span class="sxs-lookup"><span data-stu-id="288f6-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="288f6-130">I fältet Subsequent iterations väljer du "Regeneration".</span><span class="sxs-lookup"><span data-stu-id="288f6-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="288f6-131">Ange ett nummer i fältet Antal trådar.</span><span class="sxs-lookup"><span data-stu-id="288f6-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="288f6-132">Detta representerar antalet parallella trådar som används för planering.</span><span class="sxs-lookup"><span data-stu-id="288f6-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="288f6-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="288f6-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="288f6-134">Visa resultatet av planen</span><span class="sxs-lookup"><span data-stu-id="288f6-134">View the result of the plan</span></span>
1. <span data-ttu-id="288f6-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.</span><span class="sxs-lookup"><span data-stu-id="288f6-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="288f6-136">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="288f6-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="288f6-137">Klicka på länken för StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="288f6-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="288f6-138">Du måste vara i företaget USMF.</span><span class="sxs-lookup"><span data-stu-id="288f6-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="288f6-139">Klicka på Planerade order.</span><span class="sxs-lookup"><span data-stu-id="288f6-139">Click Planned orders.</span></span>


