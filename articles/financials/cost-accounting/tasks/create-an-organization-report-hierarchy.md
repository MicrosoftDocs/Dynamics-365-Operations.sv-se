--- 
title: Skapa en organisationsrapporthierarki
description: "Använd den här proceduren för att skapa en rapporthierarki för organisationsrapportering."
author: YuyuScheller
manager: AnnBe
ms.date: 10/30/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: afac613bdf366c4abcac4ee551e2db3db041803c
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="99d1e-103">Skapa en organisationsrapporthierarki</span><span class="sxs-lookup"><span data-stu-id="99d1e-103">Create an organization report hierarchy</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="99d1e-104">Använd den här proceduren för att skapa en rapporthierarki för organisationsrapportering.</span><span class="sxs-lookup"><span data-stu-id="99d1e-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="99d1e-105">Syftet med den här inspelningen är att guida dig genom dimensionshierarkin så att du kan fortsätta tills hela organisationens rapportstruktur har skapats.</span><span class="sxs-lookup"><span data-stu-id="99d1e-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="99d1e-106">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="99d1e-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="99d1e-107">Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.</span><span class="sxs-lookup"><span data-stu-id="99d1e-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="99d1e-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-108">Click New.</span></span>
3. <span data-ttu-id="99d1e-109">Välj Hierarki för dimensionsklassificering i fältet HierarchyTypeComboBox.</span><span class="sxs-lookup"><span data-stu-id="99d1e-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="99d1e-110">Välj Hierarki för dimensionsklassificering.</span><span class="sxs-lookup"><span data-stu-id="99d1e-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="99d1e-111">Typen Hierarki för dimensionsklassificering används för att definiera regler för rapporteringsändamål.</span><span class="sxs-lookup"><span data-stu-id="99d1e-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="99d1e-112">Den stöder alla dimensioner, till exempel kostnadsobjekt, kostnadselement och statistiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="99d1e-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="99d1e-113">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="99d1e-113">Click Create.</span></span>
5. <span data-ttu-id="99d1e-114">Skriv "Oganization USP2" i namnfältet för dimensionshierarki.</span><span class="sxs-lookup"><span data-stu-id="99d1e-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="99d1e-115">Ange eller välj ett värde i fältet Dimension.</span><span class="sxs-lookup"><span data-stu-id="99d1e-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-116">Välj Kostnadsställen.</span><span class="sxs-lookup"><span data-stu-id="99d1e-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="99d1e-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-117">Click Save.</span></span>
8. <span data-ttu-id="99d1e-118">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="99d1e-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="99d1e-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-119">Click New.</span></span>
10. <span data-ttu-id="99d1e-120">Skriv "CEO" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="99d1e-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-121">Click Save.</span></span>
12. <span data-ttu-id="99d1e-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-122">Click New.</span></span>
13. <span data-ttu-id="99d1e-123">Skriv "CEO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="99d1e-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-124">Click Save.</span></span>
15. <span data-ttu-id="99d1e-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-125">Click New.</span></span>
16. <span data-ttu-id="99d1e-126">Skriv "Region East" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="99d1e-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-127">Click Save.</span></span>
18. <span data-ttu-id="99d1e-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-128">Click New.</span></span>
19. <span data-ttu-id="99d1e-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="99d1e-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="99d1e-130">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="99d1e-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-131">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="99d1e-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="99d1e-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-132">Click Save.</span></span>
22. <span data-ttu-id="99d1e-133">Välj Oganization USP2\CEO\CEO cost centers i trädet.</span><span class="sxs-lookup"><span data-stu-id="99d1e-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="99d1e-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-134">Click New.</span></span>
24. <span data-ttu-id="99d1e-135">Skriv "Region West" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="99d1e-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-136">Click Save.</span></span>
26. <span data-ttu-id="99d1e-137">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-137">Click New.</span></span>
27. <span data-ttu-id="99d1e-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="99d1e-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="99d1e-139">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="99d1e-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-140">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="99d1e-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="99d1e-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-141">Click Save.</span></span>
30. <span data-ttu-id="99d1e-142">Välj Oganization USP2\CEO i trädet.</span><span class="sxs-lookup"><span data-stu-id="99d1e-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="99d1e-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-143">Click New.</span></span>
32. <span data-ttu-id="99d1e-144">Skriv "CFO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="99d1e-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-145">Click Save.</span></span>
34. <span data-ttu-id="99d1e-146">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-146">Click New.</span></span>
35. <span data-ttu-id="99d1e-147">Skriv "Marketing campa" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="99d1e-148">Skriv "Marketing campaign" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="99d1e-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-149">Click Save.</span></span>
38. <span data-ttu-id="99d1e-150">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-150">Click New.</span></span>
39. <span data-ttu-id="99d1e-151">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="99d1e-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="99d1e-152">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="99d1e-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-153">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="99d1e-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="99d1e-154">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-154">Click Save.</span></span>
42. <span data-ttu-id="99d1e-155">I trädet väljer du "Organisation USP2\CEO\CFO kostnadsställen".</span><span class="sxs-lookup"><span data-stu-id="99d1e-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="99d1e-156">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-156">Click New.</span></span>
44. <span data-ttu-id="99d1e-157">Skriv "Trade shows" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="99d1e-158">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-158">Click Save.</span></span>
46. <span data-ttu-id="99d1e-159">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-159">Click New.</span></span>
47. <span data-ttu-id="99d1e-160">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="99d1e-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="99d1e-161">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="99d1e-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-162">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="99d1e-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="99d1e-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-163">Click Save.</span></span>
50. <span data-ttu-id="99d1e-164">Välj Oganization USP2\CEO i trädet.</span><span class="sxs-lookup"><span data-stu-id="99d1e-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="99d1e-165">Skriv "CIO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="99d1e-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-166">Click Save.</span></span>
53. <span data-ttu-id="99d1e-167">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-167">Click New.</span></span>
54. <span data-ttu-id="99d1e-168">Skriv "Call centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="99d1e-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="99d1e-169">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-169">Click Save.</span></span>
56. <span data-ttu-id="99d1e-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="99d1e-170">Click New.</span></span>
57. <span data-ttu-id="99d1e-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="99d1e-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="99d1e-172">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="99d1e-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="99d1e-173">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="99d1e-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="99d1e-174">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="99d1e-174">Click Save.</span></span>


