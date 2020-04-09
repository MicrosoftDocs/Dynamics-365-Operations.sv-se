---
title: Generera en begränsad plan
description: I det här avsnittet visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 126122d7be36cf1585f372adbae3ced8d6b15134
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150365"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="7aec2-103">Generera en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="7aec2-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7aec2-104">I det här avsnittet visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="7aec2-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="7aec2-105">Planen garanterar att produktionen inte startas innan det finns tillgängligt material och resurserna inte är överbokade.</span><span class="sxs-lookup"><span data-stu-id="7aec2-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="7aec2-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="7aec2-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7aec2-107">Den här proceduren är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="7aec2-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="7aec2-108">Ställ in en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="7aec2-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="7aec2-109">På startsidan väljer du arbetsytan **Huvudplanering**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="7aec2-110">Välj **Huvudplaner** i listan med länkar längst till höger på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="7aec2-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="7aec2-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7aec2-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="7aec2-112">Exempel: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="7aec2-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="7aec2-113">Välj **Ja** i fältet **Begränsad kapacitet**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="7aec2-114">Ange `30` i fältet **Tidsgräns för begränsad kapacitet**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="7aec2-115">Expandera avsnittet **Tidsgräns i dagar**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="7aec2-116">Välj **Ja** i fältet **Kapacitet**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="7aec2-117">Ange en siffra i fältet **Tidsgräns för kapacitetsplanering (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="7aec2-118">Exempel: `60`</span><span class="sxs-lookup"><span data-stu-id="7aec2-118">Example: `60`</span></span>  
9. <span data-ttu-id="7aec2-119">Välj **Ja** i fältet **Beräknade fördröjningar**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="7aec2-120">Ange en siffra i fältet **Beräkna fördröjningstidsgräns (dagar)**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="7aec2-121">Exempel: `60`</span><span class="sxs-lookup"><span data-stu-id="7aec2-121">Example: `60`</span></span> 
11. <span data-ttu-id="7aec2-122">Expandera avsnittet **Beräknade fördröjningar**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="7aec2-123">Välj **Ja** i alla fält **Lägg till den beräknade fördröjningen för behovsdatumet**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="7aec2-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7aec2-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="7aec2-125">Skapa en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="7aec2-125">Create a constrained plan</span></span>
1. <span data-ttu-id="7aec2-126">Välj **kör**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-126">Select **Run**.</span></span>
2. <span data-ttu-id="7aec2-127">Ange eller välj den plan som du har ställt in begränsningar för i fältet **Huvudplan** .</span><span class="sxs-lookup"><span data-stu-id="7aec2-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="7aec2-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-128">Select **OK**.</span></span>
4. <span data-ttu-id="7aec2-129">Välj **Planerade order**.</span><span class="sxs-lookup"><span data-stu-id="7aec2-129">Select **Planned orders**.</span></span>

