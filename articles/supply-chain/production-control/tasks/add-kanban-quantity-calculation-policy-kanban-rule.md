---
title: Lägg till en beräkning av kanban-kvantitet i en kanban-regel
description: Den här proceduren fokuserar på att skapa en beräkningspolicy för kanban-kvantitet som läggs till den i en kanban-regel för att optimera kanban-storlek och kvantiteter.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93f0c2024e7fbe7d9c6525d41207b788032e763a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147214"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="409f5-103">Lägg till en beräkning av kanban-kvantitet i en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="409f5-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="409f5-104">Den här proceduren fokuserar på att skapa en beräkningspolicy för kanban-kvantitet som läggs till den i en kanban-regel för att optimera kanban-storlek och kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="409f5-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="409f5-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="409f5-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="409f5-106">Den här proceduren är avsedd för den värdeströmsansvarige.</span><span class="sxs-lookup"><span data-stu-id="409f5-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="409f5-107">Den här proceduren är en förutsättning när du skapar proceduren Beräkna förslag till kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="409f5-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="409f5-108">Skapa en beräkningspolicy för kanban-kvantitet</span><span class="sxs-lookup"><span data-stu-id="409f5-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="409f5-109">Gå till Produktionskontroll > Periodiska uppgifter > Beräkning av kanban-kvantitet > Beräkningspolicyer för kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="409f5-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="409f5-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="409f5-110">Click New.</span></span>
3. <span data-ttu-id="409f5-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="409f5-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="409f5-112">Skriv till exempel Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="409f5-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="409f5-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Huvudplan.</span><span class="sxs-lookup"><span data-stu-id="409f5-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="409f5-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="409f5-115">Välj StaticPlan för att beräkna behov.</span><span class="sxs-lookup"><span data-stu-id="409f5-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="409f5-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="409f5-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="409f5-117">Click Save.</span></span>
8. <span data-ttu-id="409f5-118">Ange "1" i fältet Minsta kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="409f5-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="409f5-119">Detta är det extra antal kanbans som ingår i beräkningen av kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="409f5-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="409f5-120">Ange säkerhetsfaktorn till "1".</span><span class="sxs-lookup"><span data-stu-id="409f5-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="409f5-121">Detta är den faktor som används för att beräkna ytterligare kvantitet för säkerhetslager.</span><span class="sxs-lookup"><span data-stu-id="409f5-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="409f5-122">Ange "30" i fältet Dagar före.</span><span class="sxs-lookup"><span data-stu-id="409f5-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="409f5-123">Detta är det antal dagar före beräkningsdatumet för kanban-kvantitet som ingår i efterfrågeberäkningen.</span><span class="sxs-lookup"><span data-stu-id="409f5-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="409f5-124">Ange "30" i fältet Dagar efter.</span><span class="sxs-lookup"><span data-stu-id="409f5-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="409f5-125">Detta är det antal dagar framåt från beräkningsdatumet för kanban-kvantitet som ingår i efterfrågeberäkningen.</span><span class="sxs-lookup"><span data-stu-id="409f5-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="409f5-126">Den formel som används för beräkning visas med de faktiska värdena.</span><span class="sxs-lookup"><span data-stu-id="409f5-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="409f5-127">Till exempel, Kanban-kvantitet = ((Genomsnittlig daglig efterfrågan x ledtid x 2,00) / produktkvantitet per materialhanteringsenhet) + 1</span><span class="sxs-lookup"><span data-stu-id="409f5-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="409f5-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="409f5-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="409f5-129">Lägg till beräkningspolicyn för kanban-kvantitet till en kanban-regel</span><span class="sxs-lookup"><span data-stu-id="409f5-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="409f5-130">Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="409f5-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="409f5-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="409f5-132">Välj kanban-regel 000020 för den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="409f5-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="409f5-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="409f5-134">Växla expanderingen av avsnittet Beräkningspolicyer för kanban-kvantitet.</span><span class="sxs-lookup"><span data-stu-id="409f5-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="409f5-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="409f5-135">Click Add.</span></span>
    * <span data-ttu-id="409f5-136">Lägg till beräkningspolicyn för kanban-kvantitet som du precis har skapat i föregående underuppgift.</span><span class="sxs-lookup"><span data-stu-id="409f5-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="409f5-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="409f5-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="409f5-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="409f5-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="409f5-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="409f5-140">Välj policyn Speaker2016 som du precis har skapat i föregående underuppgift.</span><span class="sxs-lookup"><span data-stu-id="409f5-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

