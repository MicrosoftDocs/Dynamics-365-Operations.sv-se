---
title: Skapa en policy för samlade kostnader
description: Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f1fa434061832bd306cef13afc46c7f3adab0c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "362612"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="a0e66-103">Skapa en policy för samlade kostnader</span><span class="sxs-lookup"><span data-stu-id="a0e66-103">Create a cost rollup policy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0e66-104">Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn.</span><span class="sxs-lookup"><span data-stu-id="a0e66-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="a0e66-105">De demonstrationsdata som används för att skapa den här proceduren är USP2.</span><span class="sxs-lookup"><span data-stu-id="a0e66-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="a0e66-106">Skapa en policy</span><span class="sxs-lookup"><span data-stu-id="a0e66-106">Create a policy</span></span>
1. <span data-ttu-id="a0e66-107">Gå till Kostnadsredovisning > Policyer > redovisningPolicyer för samlade kostnader.</span><span class="sxs-lookup"><span data-stu-id="a0e66-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="a0e66-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0e66-108">Click New.</span></span>
3. <span data-ttu-id="a0e66-109">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="a0e66-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="a0e66-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a0e66-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a0e66-111">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a0e66-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-112">Välj Samlade kostnader CC.</span><span class="sxs-lookup"><span data-stu-id="a0e66-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="a0e66-113">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-114">Välj Samlade kostnader CC.</span><span class="sxs-lookup"><span data-stu-id="a0e66-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="a0e66-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a0e66-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="a0e66-116">Skapa regler för policyn för samlad kostnad</span><span class="sxs-lookup"><span data-stu-id="a0e66-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="a0e66-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0e66-117">Click New.</span></span>
2. <span data-ttu-id="a0e66-118">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a0e66-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="a0e66-119">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a0e66-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-120">Välj 007.</span><span class="sxs-lookup"><span data-stu-id="a0e66-120">Select 007.</span></span>  
4. <span data-ttu-id="a0e66-121">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-122">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="a0e66-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="a0e66-123">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-124">I det här exemplet ska du mappa det sekundära kostnadselementet CC-007 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="a0e66-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="a0e66-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0e66-125">Click New.</span></span>
7. <span data-ttu-id="a0e66-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a0e66-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="a0e66-127">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a0e66-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-128">Välj 008.</span><span class="sxs-lookup"><span data-stu-id="a0e66-128">Select 008.</span></span>  
9. <span data-ttu-id="a0e66-129">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-130">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="a0e66-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="a0e66-131">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-132">I det här exemplet ska du mappa det sekundära kostnadselementet CC-008 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="a0e66-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="a0e66-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a0e66-133">Click New.</span></span>
12. <span data-ttu-id="a0e66-134">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="a0e66-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a0e66-135">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="a0e66-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-136">Välj 009.</span><span class="sxs-lookup"><span data-stu-id="a0e66-136">Select 009.</span></span>  
14. <span data-ttu-id="a0e66-137">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-138">Välj Samlade kostnader CE.</span><span class="sxs-lookup"><span data-stu-id="a0e66-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="a0e66-139">Ange eller välj ett värde i fältet Sekundärt kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="a0e66-140">I det här exemplet ska du mappa det sekundära kostnadselementet CC-009 till kostnadsstället.</span><span class="sxs-lookup"><span data-stu-id="a0e66-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="a0e66-141">Fortsätt tills alla kostnadsställen har mappats till deras motsvarande sekundära kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="a0e66-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="a0e66-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a0e66-142">Click Save.</span></span>

