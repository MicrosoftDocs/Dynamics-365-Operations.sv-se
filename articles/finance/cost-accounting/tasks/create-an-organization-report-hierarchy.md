---
title: Skapa en organisationsrapporthierarki
description: Använd den här proceduren för att skapa en rapporthierarki för organisationsrapportering.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 727a77b5a3a64bd4b679103e24d8c4c384a113e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815750"
---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="fbc3a-103">Skapa en organisationsrapporthierarki</span><span class="sxs-lookup"><span data-stu-id="fbc3a-103">Create an organization report hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fbc3a-104">Använd den här proceduren för att skapa en rapporthierarki för organisationsrapportering.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="fbc3a-105">Syftet med den här inspelningen är att guida dig genom dimensionshierarkin så att du kan fortsätta tills hela organisationens rapportstruktur har skapats.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="fbc3a-106">I den här inspelningen används demonstrationsföretaget USP2.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="fbc3a-107">Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="fbc3a-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-108">Click New.</span></span>
3. <span data-ttu-id="fbc3a-109">Välj Hierarki för dimensionsklassificering i fältet HierarchyTypeComboBox.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="fbc3a-110">Välj Hierarki för dimensionsklassificering.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="fbc3a-111">Typen Hierarki för dimensionsklassificering används för att definiera regler för rapporteringsändamål.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="fbc3a-112">Den stöder alla dimensioner, till exempel kostnadsobjekt, kostnadselement och statistiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="fbc3a-113">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-113">Click Create.</span></span>
5. <span data-ttu-id="fbc3a-114">Skriv "Oganization USP2" i namnfältet för dimensionshierarki.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="fbc3a-115">Ange eller välj ett värde i fältet Dimension.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-116">Välj Kostnadsställen.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="fbc3a-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-117">Click Save.</span></span>
8. <span data-ttu-id="fbc3a-118">Klicka p Visa hierarki</span><span class="sxs-lookup"><span data-stu-id="fbc3a-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="fbc3a-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-119">Click New.</span></span>
10. <span data-ttu-id="fbc3a-120">Skriv "CEO" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="fbc3a-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-121">Click Save.</span></span>
12. <span data-ttu-id="fbc3a-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-122">Click New.</span></span>
13. <span data-ttu-id="fbc3a-123">Skriv "CEO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="fbc3a-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-124">Click Save.</span></span>
15. <span data-ttu-id="fbc3a-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-125">Click New.</span></span>
16. <span data-ttu-id="fbc3a-126">Skriv "Region East" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="fbc3a-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-127">Click Save.</span></span>
18. <span data-ttu-id="fbc3a-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-128">Click New.</span></span>
19. <span data-ttu-id="fbc3a-129">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="fbc3a-130">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-131">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="fbc3a-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-132">Click Save.</span></span>
22. <span data-ttu-id="fbc3a-133">Välj Oganization USP2\CEO\CEO cost centers i trädet.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="fbc3a-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-134">Click New.</span></span>
24. <span data-ttu-id="fbc3a-135">Skriv "Region West" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="fbc3a-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-136">Click Save.</span></span>
26. <span data-ttu-id="fbc3a-137">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-137">Click New.</span></span>
27. <span data-ttu-id="fbc3a-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="fbc3a-139">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-140">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="fbc3a-141">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-141">Click Save.</span></span>
30. <span data-ttu-id="fbc3a-142">Välj Oganization USP2\CEO i trädet.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="fbc3a-143">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-143">Click New.</span></span>
32. <span data-ttu-id="fbc3a-144">Skriv "CFO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="fbc3a-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-145">Click Save.</span></span>
34. <span data-ttu-id="fbc3a-146">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-146">Click New.</span></span>
35. <span data-ttu-id="fbc3a-147">Skriv "Marketing campa" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="fbc3a-148">Skriv "Marketing campaign" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="fbc3a-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-149">Click Save.</span></span>
38. <span data-ttu-id="fbc3a-150">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-150">Click New.</span></span>
39. <span data-ttu-id="fbc3a-151">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="fbc3a-152">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-153">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="fbc3a-154">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-154">Click Save.</span></span>
42. <span data-ttu-id="fbc3a-155">I trädet väljer du "Organisation USP2\CEO\CFO kostnadsställen".</span><span class="sxs-lookup"><span data-stu-id="fbc3a-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="fbc3a-156">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-156">Click New.</span></span>
44. <span data-ttu-id="fbc3a-157">Skriv "Trade shows" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="fbc3a-158">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-158">Click Save.</span></span>
46. <span data-ttu-id="fbc3a-159">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-159">Click New.</span></span>
47. <span data-ttu-id="fbc3a-160">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="fbc3a-161">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-162">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="fbc3a-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-163">Click Save.</span></span>
50. <span data-ttu-id="fbc3a-164">Välj Oganization USP2\CEO i trädet.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="fbc3a-165">Skriv "CIO cost centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="fbc3a-166">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-166">Click Save.</span></span>
53. <span data-ttu-id="fbc3a-167">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-167">Click New.</span></span>
54. <span data-ttu-id="fbc3a-168">Skriv "Call centers" i fältet för nodnamn.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="fbc3a-169">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-169">Click Save.</span></span>
56. <span data-ttu-id="fbc3a-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-170">Click New.</span></span>
57. <span data-ttu-id="fbc3a-171">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="fbc3a-172">Ange eller välj ett värde i fältet Från dimensionsmedlem.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="fbc3a-173">Välj den dimensionsmedlem som motsvarar noden.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="fbc3a-174">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-174">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]