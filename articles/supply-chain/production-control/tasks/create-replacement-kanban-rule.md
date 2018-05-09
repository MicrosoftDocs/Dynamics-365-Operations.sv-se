--- 
title: "Skapa en kanban-regel för ersättning"
description: "Den här proceduren fokuserar på att ersätta en befintlig kanban-regel med en ny kanban-regel vid ett visst datum."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 12df41f14973628063b11f20f7368f47b2ad3488
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="a078c-103">Skapa en kanban-regel för ersättning</span><span class="sxs-lookup"><span data-stu-id="a078c-103">Create a replacement kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a078c-104">Den här proceduren fokuserar på att ersätta en befintlig kanban-regel med en ny kanban-regel vid ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="a078c-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="a078c-105">Detta är användbart när ändringar i produktionsflödet eller påfyllnadsregler behöver koordineras och tidsplaneras.</span><span class="sxs-lookup"><span data-stu-id="a078c-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="a078c-106">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="a078c-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="a078c-107">Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen för ett modifierat produktionsflöde eller en ny återanskaffningsregel.</span><span class="sxs-lookup"><span data-stu-id="a078c-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="a078c-108">Denna uppgift ersätter kanban-regel 000022 med en ny regel och ökar den högsta kvantiteten från 48 till 100 för den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="a078c-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="a078c-109">Välj en kanban-regel att ersätta.</span><span class="sxs-lookup"><span data-stu-id="a078c-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="a078c-110">Gå till Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="a078c-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="a078c-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a078c-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a078c-112">Välj kanban-regel 000022.</span><span class="sxs-lookup"><span data-stu-id="a078c-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="a078c-113">Skapa en kanban-regel för ersättning</span><span class="sxs-lookup"><span data-stu-id="a078c-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="a078c-114">Klicka på Ersätt kanban-regel.</span><span class="sxs-lookup"><span data-stu-id="a078c-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="a078c-115">Ange datum och tid i fältet Giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="a078c-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="a078c-116">Välj ett datum i framtiden, till exempel en vecka från och med nu.</span><span class="sxs-lookup"><span data-stu-id="a078c-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="a078c-117">Detta är det datum och den tid då den nya kanban-regel blir aktiv och ersätter den gamla kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="a078c-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="a078c-118">Om kanban-regeln ändrar sökvägen i produktionsflödet kan en annan aktivitet väljas.</span><span class="sxs-lookup"><span data-stu-id="a078c-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="a078c-119">I den här proceduren ska du hålla aktiviteten orörd.</span><span class="sxs-lookup"><span data-stu-id="a078c-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="a078c-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a078c-120">Click OK.</span></span>
    * <span data-ttu-id="a078c-121">Observera att en ny kanban-regel skapas för att ersätta kanban-regel 000022.</span><span class="sxs-lookup"><span data-stu-id="a078c-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="a078c-122">Giltighetsdatumet anges enligt det valda datumet när du ersätter kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="a078c-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="a078c-123">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a078c-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a078c-124">Välj den ersatta kanban-regel 000022.</span><span class="sxs-lookup"><span data-stu-id="a078c-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="a078c-125">Observera att den ersatta kanban-regeln har samma datum som utgångsdatumet eftersom det är datumet när den upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="a078c-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="a078c-126">Väl rad 1 i listan.</span><span class="sxs-lookup"><span data-stu-id="a078c-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="a078c-127">Välj den nya kanban-regel längst upp i listan.</span><span class="sxs-lookup"><span data-stu-id="a078c-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="a078c-128">Detta är kanban-regeln med det högsta kanban-regelnumret.</span><span class="sxs-lookup"><span data-stu-id="a078c-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="a078c-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="a078c-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a078c-130">Klicka på kanban-regelnumret för att öppna kanban-regeln.</span><span class="sxs-lookup"><span data-stu-id="a078c-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="a078c-131">Ändra den högsta kvantiteten för ersättningskanban-regeln</span><span class="sxs-lookup"><span data-stu-id="a078c-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="a078c-132">AngeHögsta kvantitet till "100".</span><span class="sxs-lookup"><span data-stu-id="a078c-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="a078c-133">Visa snabbfliken Kvantiteter om du vill visa fältet Högsta kvantitet.</span><span class="sxs-lookup"><span data-stu-id="a078c-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="a078c-134">Om du ändrar den högsta kvantiteten till 100 kommer upp till 100 kanban att bearbetas.</span><span class="sxs-lookup"><span data-stu-id="a078c-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="a078c-135">Detta är det sista steget i den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a078c-135">This is the last step in this task.</span></span>  


