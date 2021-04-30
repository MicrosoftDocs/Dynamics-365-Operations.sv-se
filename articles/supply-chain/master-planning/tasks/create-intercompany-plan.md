---
title: Skapa en koncernintern plan
description: I den här proceduren visas hur du skapar en koncernintern plan.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867360"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="bfe58-103">Skapa en koncernintern plan</span><span class="sxs-lookup"><span data-stu-id="bfe58-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bfe58-104">I den här proceduren visas hur du skapar en koncernintern plan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="bfe58-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="bfe58-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="bfe58-106">Skapa en koncernintern planeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="bfe58-106">Set up an intercompany planning group</span></span>

1. <span data-ttu-id="bfe58-107">I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Inställningar > Koncerninterna planeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="bfe58-108">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="bfe58-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bfe58-109">Filtrera till exempel på värdet "10" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="bfe58-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="bfe58-110">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="bfe58-111">Välj **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-111">Select **Delete**.</span></span> <span data-ttu-id="bfe58-112">Det här steget är nödvändigt för att förkorta den koncerninterna planläggningskörningen.</span><span class="sxs-lookup"><span data-stu-id="bfe58-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="bfe58-113">Den koncerninterna planeringen kör huvudplaneringen i samtliga företag i en planläggningsgrupp, med början från den lägsta schemaläggningssekvensen.</span><span class="sxs-lookup"><span data-stu-id="bfe58-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="bfe58-114">Välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-114">Select **Yes**.</span></span>
6. <span data-ttu-id="bfe58-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-115">Close the page.</span></span>

## <a name="create-an-intercompany-master-plan"></a><span data-ttu-id="bfe58-116">Skapa en koncernintern huvudplan</span><span class="sxs-lookup"><span data-stu-id="bfe58-116">Create an intercompany master plan</span></span>

1. <span data-ttu-id="bfe58-117">I **navigeringfönstret**, gå till **Moduler > Huvudplanering > Arbetsytor > Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="bfe58-118">Välj **Koncernintern huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-118">Select **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="bfe58-119">Öppna sökningen genom att välja listrutan i fältet **Koncernintern planeringsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-119">In the **Intercompany planning group** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bfe58-120">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-120">In the list, select the link in the selected row.</span></span> <span data-ttu-id="bfe58-121">Välj koncernintern planeringsgrupp 10.</span><span class="sxs-lookup"><span data-stu-id="bfe58-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="bfe58-122">Ange "2" i fältet **Antal upprepningar av koncernintern planering**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="bfe58-123">Koncernintern planeringsgrupp 10 har två medlemmar.</span><span class="sxs-lookup"><span data-stu-id="bfe58-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="bfe58-124">Om du vill sprida förskjutningarna från källföretaget (USMF) till kundföretaget (DEMF ) måste du köra koncerninternt i båda företag två gånger.</span><span class="sxs-lookup"><span data-stu-id="bfe58-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="bfe58-125">Den första upprepningen sprider begäran och identifierar förskjutningarna i källföretaget (USMF).</span><span class="sxs-lookup"><span data-stu-id="bfe58-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="bfe58-126">Den andra upprepningen sprider förskjutningarna från USMF till DEMF.</span><span class="sxs-lookup"><span data-stu-id="bfe58-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="bfe58-127">Välj "Omgenerering" i fältet **Första upprepning**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="bfe58-128">Välj Omgenerering i fältet **Efterföljande upprepningar**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="bfe58-129">Ange ett nummer i fältet **Antal trådar.**</span><span class="sxs-lookup"><span data-stu-id="bfe58-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="bfe58-130">Detta representerar antalet parallella trådar som används för planering.</span><span class="sxs-lookup"><span data-stu-id="bfe58-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="bfe58-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-131">Select **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="bfe58-132">Visa resultatet av planen</span><span class="sxs-lookup"><span data-stu-id="bfe58-132">View the result of the plan</span></span>

1. <span data-ttu-id="bfe58-133">Öppna sökningen genom att välja listrutan i fältet **Planera**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-133">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="bfe58-134">Klicka på länken på önskad rad i valda listan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-134">In the list, select the link in the selected row.</span></span> <span data-ttu-id="bfe58-135">Välj länken för StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="bfe58-135">Select the link for StaticPlan.</span></span> <span data-ttu-id="bfe58-136">Du måste vara i företaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bfe58-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="bfe58-137">Välj **Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="bfe58-137">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]