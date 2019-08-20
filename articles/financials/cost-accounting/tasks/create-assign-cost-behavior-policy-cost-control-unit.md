---
title: Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet
description: Kostnadsbeteende är klassificeringen av kostnader som fasta eller rörliga.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16d9dceb4c2a22eab9a5ecb8501393444f20498b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841379"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="2095c-103">Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet</span><span class="sxs-lookup"><span data-stu-id="2095c-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2095c-104">Kostnadsbeteende är klassificeringen av kostnader som fasta eller rörliga.</span><span class="sxs-lookup"><span data-stu-id="2095c-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="2095c-105">En policy och motsvarande regler måste tilldelas till en kostnadsstyrenhet för att policyn ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="2095c-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="2095c-106">Använd den här proceduren när du vill skapa en policy och sedan tilldela den till en kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="2095c-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="2095c-107">Skapa en hierarki för kostnadsbeteende</span><span class="sxs-lookup"><span data-stu-id="2095c-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="2095c-108">Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.</span><span class="sxs-lookup"><span data-stu-id="2095c-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="2095c-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-109">Click New.</span></span>
3. <span data-ttu-id="2095c-110">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="2095c-110">Click Create.</span></span>
4. <span data-ttu-id="2095c-111">Skriv "Cost behavior hierarchy" i fältet Dimensionshierarkins namn.</span><span class="sxs-lookup"><span data-stu-id="2095c-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="2095c-112">Ange eller välj ett värde i fältet Dimension.</span><span class="sxs-lookup"><span data-stu-id="2095c-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-113">Välj Kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2095c-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="2095c-114">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2095c-114">Click Save.</span></span>
7. <span data-ttu-id="2095c-115">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="2095c-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="2095c-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-116">Click New.</span></span>
9. <span data-ttu-id="2095c-117">Skriv ett värde i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="2095c-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="2095c-118">Ange fast kostnad.</span><span class="sxs-lookup"><span data-stu-id="2095c-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="2095c-119">Välj Cost behavior hierarchy i trädet.</span><span class="sxs-lookup"><span data-stu-id="2095c-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="2095c-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-120">Click New.</span></span>
12. <span data-ttu-id="2095c-121">Skriv ett värde i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="2095c-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="2095c-122">Ange rörlig kostnad.</span><span class="sxs-lookup"><span data-stu-id="2095c-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="2095c-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2095c-123">Click Save.</span></span>
14. <span data-ttu-id="2095c-124">Välj Cost behavior hierarchy\Fixed cost i trädet.</span><span class="sxs-lookup"><span data-stu-id="2095c-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="2095c-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-125">Click New.</span></span>
16. <span data-ttu-id="2095c-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2095c-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="2095c-127">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="2095c-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-128">Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.</span><span class="sxs-lookup"><span data-stu-id="2095c-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="2095c-129">Ange eller välj ett värde i fältet Till dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="2095c-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-130">Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.</span><span class="sxs-lookup"><span data-stu-id="2095c-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="2095c-131">Välj Cost behavior hierarchy\Variable cost i trädet.</span><span class="sxs-lookup"><span data-stu-id="2095c-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="2095c-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-132">Click New.</span></span>
21. <span data-ttu-id="2095c-133">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2095c-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="2095c-134">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="2095c-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-135">Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.</span><span class="sxs-lookup"><span data-stu-id="2095c-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="2095c-136">Ange eller välj ett värde i fältet Till dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="2095c-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-137">Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.</span><span class="sxs-lookup"><span data-stu-id="2095c-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="2095c-138">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2095c-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="2095c-139">Skapa policyn och regler</span><span class="sxs-lookup"><span data-stu-id="2095c-139">Create the policy and rules</span></span>
1. <span data-ttu-id="2095c-140">Gå till Kostnadsredovisning > Policyer > Kostnadsbeteendepolicyer.</span><span class="sxs-lookup"><span data-stu-id="2095c-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="2095c-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-141">Click New.</span></span>
3. <span data-ttu-id="2095c-142">Skriv ett värde i fältet Policynamn.</span><span class="sxs-lookup"><span data-stu-id="2095c-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="2095c-143">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2095c-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-144">Välj policyhierarkin som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="2095c-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="2095c-145">Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2095c-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-146">Välj Organisation.</span><span class="sxs-lookup"><span data-stu-id="2095c-146">Select Organization.</span></span>  
6. <span data-ttu-id="2095c-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2095c-147">Click Save.</span></span>
7. <span data-ttu-id="2095c-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-148">Click New.</span></span>
8. <span data-ttu-id="2095c-149">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2095c-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="2095c-150">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="2095c-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-151">Expandera hela hierarkin för att Rörlig kostnad.</span><span class="sxs-lookup"><span data-stu-id="2095c-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="2095c-152">Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="2095c-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2095c-153">Som standard är den rörliga procentandelen 100 procent.</span><span class="sxs-lookup"><span data-stu-id="2095c-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="2095c-154">Klicka på Policytilldelningar för kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="2095c-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="2095c-155">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2095c-155">Click New.</span></span>
13. <span data-ttu-id="2095c-156">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="2095c-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="2095c-157">Ange ett datum i fältet Gäller från redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="2095c-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="2095c-158">Reglerna gäller utifrån datum och en regel kan upphöra att gälla genom en användare eller systemet om en nyare version skapas.</span><span class="sxs-lookup"><span data-stu-id="2095c-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="2095c-159">Ange eller välj ett värde i fältet Kostnadsstyrenhet.</span><span class="sxs-lookup"><span data-stu-id="2095c-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="2095c-160">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2095c-160">Click Save.</span></span>

