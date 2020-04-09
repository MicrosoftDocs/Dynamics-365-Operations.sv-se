---
title: Skapa en koncernintern plan
description: I den här proceduren visas hur du skapar en koncernintern plan.
author: ShylaThompson
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a321f7e781f1ae93d8a69ee45a0e6e8e6eeb1e8d
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150342"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="bb6ba-103">Skapa en koncernintern plan</span><span class="sxs-lookup"><span data-stu-id="bb6ba-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bb6ba-104">I den här proceduren visas hur du skapar en koncernintern plan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="bb6ba-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="bb6ba-106">Skapa en koncernintern planeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="bb6ba-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="bb6ba-107">I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Inställningar > Koncerninterna planeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="bb6ba-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bb6ba-109">Filtrera till exempel på värdet "10" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="bb6ba-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="bb6ba-111">Klicka på **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-111">Click **Delete**.</span></span> <span data-ttu-id="bb6ba-112">Det här steget är nödvändigt för att förkorta den koncerninterna planläggningskörningen.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="bb6ba-113">Den koncerninterna planeringen kör huvudplaneringen i samtliga företag i en planläggningsgrupp, med början från den lägsta schemaläggningssekvensen.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="bb6ba-114">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-114">Click **Yes**.</span></span>
6. <span data-ttu-id="bb6ba-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="bb6ba-116">Skapa en koncernintern plan</span><span class="sxs-lookup"><span data-stu-id="bb6ba-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="bb6ba-117">I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Arbetsytor > Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="bb6ba-118">Klicka på **Koncernintern huvudplanering.**</span><span class="sxs-lookup"><span data-stu-id="bb6ba-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="bb6ba-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Koncernintern planeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bb6ba-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="bb6ba-121">Välj koncernintern planeringsgrupp 10.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="bb6ba-122">Ange "2" i fältet **Antal upprepningar av koncernintern planering**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="bb6ba-123">Koncernintern planeringsgrupp 10 har två medlemmar.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="bb6ba-124">Om du vill sprida förskjutningarna från källföretaget (USMF) till kundföretaget (DEMF ) måste du köra koncerninternt i båda företag två gånger.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="bb6ba-125">Den första upprepningen sprider begäran och identifierar förskjutningarna i källföretaget (USMF).</span><span class="sxs-lookup"><span data-stu-id="bb6ba-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="bb6ba-126">Den andra upprepningen sprider förskjutningarna från USMF till DEMF.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="bb6ba-127">Välj "Omgenerering" i fältet **Första upprepning**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="bb6ba-128">Välj Omgenerering i fältet **Efterföljande upprepningar**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="bb6ba-129">Ange ett nummer i fältet **Antal trådar.**</span><span class="sxs-lookup"><span data-stu-id="bb6ba-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="bb6ba-130">Detta representerar antalet parallella trådar som används för planering.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="bb6ba-131">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="bb6ba-132">Visa resultatet av planen</span><span class="sxs-lookup"><span data-stu-id="bb6ba-132">View the result of the plan</span></span>
1. <span data-ttu-id="bb6ba-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Plan**.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="bb6ba-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="bb6ba-135">Klicka på länken för StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="bb6ba-136">Du måste vara i företaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bb6ba-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="bb6ba-137">Klicka på **Planerade order.**</span><span class="sxs-lookup"><span data-stu-id="bb6ba-137">Click **Planned orders**.</span></span>

