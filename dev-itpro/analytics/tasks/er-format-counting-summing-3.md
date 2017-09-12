--- 
title: "Använd beräkningar för att skapa utdata för inventering och summering för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 121f00efea6aee8d9df45d67f8f252bbf6b97176
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="04913-103">Använd beräkningar för att skapa utdata för inventering och summering för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="04913-103">Use computations to make the output for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04913-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="04913-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="04913-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="04913-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="04913-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 2: Configure computations)"</span><span class="sxs-lookup"><span data-stu-id="04913-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="04913-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="04913-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="04913-108">Konfigurera den här rapporten om du vill använda inventerings- och summeringsinformation</span><span class="sxs-lookup"><span data-stu-id="04913-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="04913-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="04913-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="04913-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="04913-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="04913-111">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="04913-112">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="04913-113">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="04913-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="04913-114">Click Designer.</span></span>
7. <span data-ttu-id="04913-115">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="04913-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="04913-116">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="04913-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="04913-117">Lägg till en ny datakälla för att få listan över memorerade block.</span><span class="sxs-lookup"><span data-stu-id="04913-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="04913-118">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="04913-119">Ange "$BlocksList" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="04913-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="04913-120">$BlocksList</span></span>  
11. <span data-ttu-id="04913-121">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="04913-121">Click Edit formula.</span></span>
12. <span data-ttu-id="04913-122">Välj "Data collection functions\COLLECTEDLIST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="04913-123">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="04913-123">Click Add function.</span></span>
14. <span data-ttu-id="04913-124">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="04913-124">Click Add data source.</span></span>
15. <span data-ttu-id="04913-125">Ange "COLLECTEDLIST('$BlockName', " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="04913-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="04913-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="04913-127">Ange "COLLECTEDLIST('$BlockName', "*")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "*")'.</span></span>
    * <span data-ttu-id="04913-128">COLLECTEDLIST('$BlockName', "*")</span><span class="sxs-lookup"><span data-stu-id="04913-128">COLLECTEDLIST('$BlockName', "*")</span></span>  
17. <span data-ttu-id="04913-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="04913-129">Click Save.</span></span>
    * <span data-ttu-id="04913-130">Mönstret ”*” innebär att alla block kommer att inkluderas i listan för denna post.</span><span class="sxs-lookup"><span data-stu-id="04913-130">The pattern “*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="04913-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04913-131">Close the page.</span></span>
19. <span data-ttu-id="04913-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="04913-132">Click OK.</span></span>
20. <span data-ttu-id="04913-133">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="04913-133">Click the Format tab.</span></span>
21. <span data-ttu-id="04913-134">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="04913-135">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="04913-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="04913-136">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="04913-137">Ange "Totals by blocks" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="04913-138">Summor per block</span><span class="sxs-lookup"><span data-stu-id="04913-138">Totals by blocks</span></span>  
25. <span data-ttu-id="04913-139">Välj "New line - Windows (CR LF)" i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="04913-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="04913-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="04913-140">Click OK.</span></span>
27. <span data-ttu-id="04913-141">Välj "Intrastat\Data\Totals by blocks" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="04913-142">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="04913-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="04913-143">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="04913-144">Ange "Block code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="04913-145">Blockkod</span><span class="sxs-lookup"><span data-stu-id="04913-145">Block code</span></span>  
31. <span data-ttu-id="04913-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="04913-146">Click OK.</span></span>
32. <span data-ttu-id="04913-147">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="04913-147">Click Add String.</span></span>
33. <span data-ttu-id="04913-148">Ange "Lines counting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="04913-149">Radinventering</span><span class="sxs-lookup"><span data-stu-id="04913-149">Lines counting</span></span>  
34. <span data-ttu-id="04913-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="04913-150">Click OK.</span></span>
35. <span data-ttu-id="04913-151">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="04913-151">Click Add String.</span></span>
36. <span data-ttu-id="04913-152">Ange "Total amount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="04913-153">Totalt antal timmar</span><span class="sxs-lookup"><span data-stu-id="04913-153">Total amount</span></span>  
37. <span data-ttu-id="04913-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="04913-154">Click OK.</span></span>
38. <span data-ttu-id="04913-155">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="04913-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="04913-156">Välj "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="04913-157">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="04913-157">Click Bind.</span></span>
    * <span data-ttu-id="04913-158">Skapa en summeringsrad för varje memorerat block.</span><span class="sxs-lookup"><span data-stu-id="04913-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="04913-159">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="04913-159">Click the Format tab.</span></span>
42. <span data-ttu-id="04913-160">Välj "Intrastat\Data\Totals by blocks\Block code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="04913-161">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="04913-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="04913-162">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="04913-162">Click Edit formula.</span></span>
45. <span data-ttu-id="04913-163">Ange ""Block id: " & "  " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="04913-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="04913-164">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="04913-164">"Block id: " &</span></span>  
46. <span data-ttu-id="04913-165">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="04913-166">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="04913-167">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="04913-167">Click Add data source.</span></span>
49. <span data-ttu-id="04913-168">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="04913-168">Click Save.</span></span>
50. <span data-ttu-id="04913-169">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04913-169">Close the page.</span></span>
51. <span data-ttu-id="04913-170">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="04913-170">Click the Format tab.</span></span>
52. <span data-ttu-id="04913-171">Välj "Intrastat\Data\Totals by blocks\Lines counting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="04913-172">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="04913-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="04913-173">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="04913-173">Click Edit formula.</span></span>
    * <span data-ttu-id="04913-174">Skapa utleverans för det antal rader i varje block som presenteras i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="04913-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="04913-175">I formelfältet anger du ""Number of lines in this block: " & ".</span><span class="sxs-lookup"><span data-stu-id="04913-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="04913-176">"Antal rader i detta block:  " & </span><span class="sxs-lookup"><span data-stu-id="04913-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="04913-177">I formelfältet anger du ""Number of lines in this block: " & TEXT(".</span><span class="sxs-lookup"><span data-stu-id="04913-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="04913-178">"Antal rader i detta block: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="04913-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="04913-179">Välj "Data collection functions\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="04913-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="04913-180">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="04913-180">Click Add function.</span></span>
59. <span data-ttu-id="04913-181">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="04913-181">Click Add data source.</span></span>
60. <span data-ttu-id="04913-182">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="04913-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="04913-183">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="04913-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="04913-184">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="04913-185">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="04913-186">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="04913-186">Click Add data source.</span></span>
64. <span data-ttu-id="04913-187">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="04913-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="04913-188">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="04913-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="04913-189">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="04913-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="04913-190">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="04913-190">Click Add data source.</span></span>
67. <span data-ttu-id="04913-191">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))".</span><span class="sxs-lookup"><span data-stu-id="04913-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="04913-192">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="04913-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
68. <span data-ttu-id="04913-193">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="04913-193">Click Save.</span></span>
69. <span data-ttu-id="04913-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04913-194">Close the page.</span></span>
70. <span data-ttu-id="04913-195">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="04913-195">Click the Format tab.</span></span>
71. <span data-ttu-id="04913-196">I trädet väljer du "Intrastat\Data\Totals by blocks\Total amount".</span><span class="sxs-lookup"><span data-stu-id="04913-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="04913-197">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="04913-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="04913-198">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="04913-198">Click Edit formula.</span></span>
    * <span data-ttu-id="04913-199">Skapa utleverans som ska vara summan av det fakturerade beloppet för varje textblock som visas i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="04913-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="04913-200">I formelfältet anger du ""Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))".</span><span class="sxs-lookup"><span data-stu-id="04913-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="04913-201">”Summan av det fakturerade beloppet: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="04913-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
75. <span data-ttu-id="04913-202">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="04913-202">Click Save.</span></span>
76. <span data-ttu-id="04913-203">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04913-203">Close the page.</span></span>
77. <span data-ttu-id="04913-204">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="04913-204">Click Save.</span></span>
78. <span data-ttu-id="04913-205">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04913-205">Close the page.</span></span>


