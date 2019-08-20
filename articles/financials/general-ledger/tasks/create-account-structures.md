---
title: Skapa kontostrukturer
description: Den här uppgiften leder dig genom stegen för att skapa en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2183f88356fc8094781af147bf079c4e53ffb2b4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846713"
---
# <a name="create-account-structures"></a><span data-ttu-id="8b0f3-103">Skapa kontostrukturer</span><span class="sxs-lookup"><span data-stu-id="8b0f3-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b0f3-104">Den här uppgiften leder dig genom stegen för att skapa en kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="8b0f3-105">Demoföretaget USMF används i stegen.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="8b0f3-106">Gå till Redovisning > Kontoplan > Strukturer > Konfigurera kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="8b0f3-107">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="8b0f3-108">Ange ett namn som beskriver syftet med kontostrukturen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="8b0f3-109">Ange en beskrivning för att ange syftet med kontostrukturen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="8b0f3-110">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-110">Click Create.</span></span>
6. <span data-ttu-id="8b0f3-111">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-111">Click Add segment.</span></span>
7. <span data-ttu-id="8b0f3-112">I listan Dimensioner väljer du den dimension du vill lägga till i kontostrukturen.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="8b0f3-113">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-113">Click Add segment.</span></span>
9. <span data-ttu-id="8b0f3-114">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-114">Click Add segment.</span></span>
10. <span data-ttu-id="8b0f3-115">I listan Dimensioner väljer du den dimension du vill lägga till i kontostrukturen.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="8b0f3-116">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-116">Click Add segment.</span></span>
12. <span data-ttu-id="8b0f3-117">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-117">Click Add segment.</span></span>
13. <span data-ttu-id="8b0f3-118">I listan Dimensioner väljer du den dimension du vill lägga till i kontostrukturen.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="8b0f3-119">Klicka på Lägg till segment.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-119">Click Add segment.</span></span>
15. <span data-ttu-id="8b0f3-120">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="8b0f3-121">Klicka till exempel i Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="8b0f3-122">Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="8b0f3-123">Ange ett värde i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-124">Exempelvis 600000.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-124">For example, 600000.</span></span>  
18. <span data-ttu-id="8b0f3-125">Skriv ett värde i fältet via.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-126">Exempelvis 699999.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-126">For example, 699999.</span></span>  
19. <span data-ttu-id="8b0f3-127">Klicka på Verkställ.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-127">Click Apply.</span></span>
20. <span data-ttu-id="8b0f3-128">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="8b0f3-129">Till exempel Avdelning.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-129">For example, Department.</span></span>  
21. <span data-ttu-id="8b0f3-130">Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="8b0f3-131">Ange ett värde i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-132">Exempelvis 022.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-132">For example, 022.</span></span>  
23. <span data-ttu-id="8b0f3-133">Skriv ett värde i fältet via.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-134">Exempelvis 031.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-134">For example, 031.</span></span>  
24. <span data-ttu-id="8b0f3-135">Klicka på Lägg till nya kriterier.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="8b0f3-136">Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="8b0f3-137">Ange ett värde i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-138">Exempelvis 033.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-138">For example, 033.</span></span>  
27. <span data-ttu-id="8b0f3-139">Skriv ett värde i fältet via.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-140">Exempelvis 034.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-140">For example, 034.</span></span>  
28. <span data-ttu-id="8b0f3-141">Klicka på Verkställ.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-141">Click Apply.</span></span>
29. <span data-ttu-id="8b0f3-142">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="8b0f3-143">Till exempel Kostnadsställe</span><span class="sxs-lookup"><span data-stu-id="8b0f3-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="8b0f3-144">Skriv ett värde i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-145">Till exempel 007..021.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="8b0f3-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-146">Click Add.</span></span>
32. <span data-ttu-id="8b0f3-147">Ange ett värde i fältet MainAccount.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-148">Till exempel 600000..699999</span><span class="sxs-lookup"><span data-stu-id="8b0f3-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="8b0f3-149">I rutnätet väljer du segmentet för att redigera de tillåtna värdena.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="8b0f3-150">Till exempel Avdelning.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-150">For example, Department.</span></span>  
34. <span data-ttu-id="8b0f3-151">Ange ett värde i fältet Avdelning.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-152">Exempelvis 032.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-152">For example, 032.</span></span>  
35. <span data-ttu-id="8b0f3-153">Skriv ett värde i fältet CostCenter.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="8b0f3-154">Exempelvis 086.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-154">For example, 086.</span></span>  
36. <span data-ttu-id="8b0f3-155">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-155">Click Validate.</span></span>
37. <span data-ttu-id="8b0f3-156">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-156">Click Activate.</span></span>
38. <span data-ttu-id="8b0f3-157">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="8b0f3-157">Click Activate.</span></span>

