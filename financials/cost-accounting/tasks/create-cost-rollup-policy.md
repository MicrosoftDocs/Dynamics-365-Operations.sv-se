--- 
title: "Skapa en policy för samlade kostnader"
description: "Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 42656cbf445fd3f79844884d7d35243c5b051a4a
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="2c8f2-103">Skapa en policy för samlade kostnader</span><span class="sxs-lookup"><span data-stu-id="2c8f2-103">Create a cost rollup policy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c8f2-104">Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="2c8f2-105">De demonstrationsdata som används för att skapa den här proceduren är USP2.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="2c8f2-106">Skapa en policy</span><span class="sxs-lookup"><span data-stu-id="2c8f2-106">Create a policy</span></span>
1. <span data-ttu-id="2c8f2-107">Gå till Kostnadsredovisning > Policyer > redovisningPolicyer för samlade kostnader.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="2c8f2-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-108">Click New.</span></span>
3. <span data-ttu-id="2c8f2-109">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="2c8f2-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2c8f2-111">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-112">Välj Samlade kostnader CC.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="2c8f2-113">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-114">Välj Samlade kostnader CC.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="2c8f2-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="2c8f2-116">Skapa regler för policyn för samlad kostnad</span><span class="sxs-lookup"><span data-stu-id="2c8f2-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="2c8f2-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-117">Click New.</span></span>
2. <span data-ttu-id="2c8f2-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2c8f2-119">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-120">Välj 007.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-120">Select 007.</span></span>  
4. <span data-ttu-id="2c8f2-121">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-122">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="2c8f2-123">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-124">I det här exemplet ska du mappa det sekundära kostnadselementet CC-007 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="2c8f2-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-125">Click New.</span></span>
7. <span data-ttu-id="2c8f2-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2c8f2-127">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-128">Välj 008.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-128">Select 008.</span></span>  
9. <span data-ttu-id="2c8f2-129">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-130">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="2c8f2-131">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-132">I det här exemplet ska du mappa det sekundära kostnadselementet CC-008 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="2c8f2-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-133">Click New.</span></span>
12. <span data-ttu-id="2c8f2-134">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="2c8f2-135">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-136">Välj 009.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-136">Select 009.</span></span>  
14. <span data-ttu-id="2c8f2-137">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-138">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="2c8f2-139">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2c8f2-140">I det här exemplet ska du mappa det sekundära kostnadselementet CC-009 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="2c8f2-141">Fortsätt tills alla kostnadsställen har mappats till deras motsvarande sekundära kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="2c8f2-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2c8f2-142">Click Save.</span></span>


