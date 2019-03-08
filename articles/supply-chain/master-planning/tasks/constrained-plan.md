---
title: Generera en begränsad plan
description: I den här proceduren visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "336047"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="8f886-103">Generera en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="8f886-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f886-104">I den här proceduren visas hur du skapar en plan som tar hänsyn till både material- och kapacitetsbegränsningar.</span><span class="sxs-lookup"><span data-stu-id="8f886-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="8f886-105">Planen garanterar att produktionen inte startas innan det finns tillgängligt material och resurserna inte är överbokade.</span><span class="sxs-lookup"><span data-stu-id="8f886-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="8f886-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8f886-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8f886-107">Den här proceduren är avsedd för produktionsplaneraren.</span><span class="sxs-lookup"><span data-stu-id="8f886-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="8f886-108">Ställ in en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="8f886-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="8f886-109">Klcka på Huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="8f886-109">Click Master planning.</span></span>
2. <span data-ttu-id="8f886-110">Klcka på Huvudplaner.</span><span class="sxs-lookup"><span data-stu-id="8f886-110">Click Master plans.</span></span>
3. <span data-ttu-id="8f886-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8f886-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8f886-112">Exempel: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="8f886-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="8f886-113">Välj Ja i fältet Begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="8f886-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="8f886-114">Ange "30 "i fältet Tidsgräns för begränsad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="8f886-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="8f886-115">Expandera avsnittet Tidsgräns i dagar.</span><span class="sxs-lookup"><span data-stu-id="8f886-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="8f886-116">Välj Ja i fältet Kapacitet.</span><span class="sxs-lookup"><span data-stu-id="8f886-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="8f886-117">Ange ett tal i fältet Tidsgräns för kapacitetsplanering (dagar).</span><span class="sxs-lookup"><span data-stu-id="8f886-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="8f886-118">Exempel: 60</span><span class="sxs-lookup"><span data-stu-id="8f886-118">Example: 60</span></span>  
9. <span data-ttu-id="8f886-119">Välj Ja i fältet Beräknade fördröjningar.</span><span class="sxs-lookup"><span data-stu-id="8f886-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="8f886-120">Ange ett tal i fältet Beräkna fördröjningstidsgräns (dagar).</span><span class="sxs-lookup"><span data-stu-id="8f886-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="8f886-121">Exempel: 60</span><span class="sxs-lookup"><span data-stu-id="8f886-121">Example: 60</span></span>  
11. <span data-ttu-id="8f886-122">Expandera avsnittet Beräknade fördröjningar.</span><span class="sxs-lookup"><span data-stu-id="8f886-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="8f886-123">Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.</span><span class="sxs-lookup"><span data-stu-id="8f886-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="8f886-124">Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.</span><span class="sxs-lookup"><span data-stu-id="8f886-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="8f886-125">Välj Ja i fältet Lägg till den beräknade fördröjningen för behovsdatumet.</span><span class="sxs-lookup"><span data-stu-id="8f886-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="8f886-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8f886-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="8f886-127">Skapa en begränsad plan</span><span class="sxs-lookup"><span data-stu-id="8f886-127">Create a constrained plan</span></span>
1. <span data-ttu-id="8f886-128">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="8f886-128">Click Run.</span></span>
2. <span data-ttu-id="8f886-129">Ange eller välj ett värde i fältet Huvudplan.</span><span class="sxs-lookup"><span data-stu-id="8f886-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="8f886-130">Välj den plan som du har ställt in begränsningar för.</span><span class="sxs-lookup"><span data-stu-id="8f886-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="8f886-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8f886-131">Click OK.</span></span>
    * <span data-ttu-id="8f886-132">Detta kan ta ett tag.</span><span class="sxs-lookup"><span data-stu-id="8f886-132">This may take a while.</span></span>  
4. <span data-ttu-id="8f886-133">Klicka på Planerade order.</span><span class="sxs-lookup"><span data-stu-id="8f886-133">Click Planned orders.</span></span>

