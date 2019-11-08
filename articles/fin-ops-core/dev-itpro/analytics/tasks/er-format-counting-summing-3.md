---
title: ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7bbef7048488056f50ec8967a9af53d468666856
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550773"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="fa3a2-103">ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)</span><span class="sxs-lookup"><span data-stu-id="fa3a2-103">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fa3a2-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="fa3a2-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="fa3a2-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 2: Configure computations)"</span><span class="sxs-lookup"><span data-stu-id="fa3a2-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="fa3a2-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="fa3a2-108">Konfigurera den här rapporten om du vill använda inventerings- och summeringsinformation</span><span class="sxs-lookup"><span data-stu-id="fa3a2-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="fa3a2-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="fa3a2-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="fa3a2-111">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="fa3a2-112">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="fa3a2-113">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="fa3a2-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-114">Click Designer.</span></span>
7. <span data-ttu-id="fa3a2-115">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="fa3a2-116">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="fa3a2-117">Lägg till en ny datakälla för att få listan över memorerade block.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="fa3a2-118">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="fa3a2-119">Ange "$BlocksList" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="fa3a2-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="fa3a2-120">$BlocksList</span></span>  
11. <span data-ttu-id="fa3a2-121">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-121">Click Edit formula.</span></span>
12. <span data-ttu-id="fa3a2-122">Välj "Data collection functions\COLLECTEDLIST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="fa3a2-123">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-123">Click Add function.</span></span>
14. <span data-ttu-id="fa3a2-124">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-124">Click Add data source.</span></span>
15. <span data-ttu-id="fa3a2-125">Ange "COLLECTEDLIST('$BlockName', " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="fa3a2-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="fa3a2-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="fa3a2-127">Ange "COLLECTEDLIST('$BlockName', "\*")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="fa3a2-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="fa3a2-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="fa3a2-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-129">Click Save.</span></span>
    * <span data-ttu-id="fa3a2-130">Mönstret ”\*” innebär att alla block kommer att inkluderas i listan för denna post.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="fa3a2-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-131">Close the page.</span></span>
19. <span data-ttu-id="fa3a2-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-132">Click OK.</span></span>
20. <span data-ttu-id="fa3a2-133">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-133">Click the Format tab.</span></span>
21. <span data-ttu-id="fa3a2-134">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="fa3a2-135">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="fa3a2-136">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="fa3a2-137">Ange "Totals by blocks" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="fa3a2-138">Summor per block</span><span class="sxs-lookup"><span data-stu-id="fa3a2-138">Totals by blocks</span></span>  
25. <span data-ttu-id="fa3a2-139">Välj "New line - Windows (CR LF)" i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="fa3a2-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-140">Click OK.</span></span>
27. <span data-ttu-id="fa3a2-141">Välj "Intrastat\Data\Totals by blocks" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="fa3a2-142">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="fa3a2-143">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="fa3a2-144">Ange "Block code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="fa3a2-145">Blockkod</span><span class="sxs-lookup"><span data-stu-id="fa3a2-145">Block code</span></span>  
31. <span data-ttu-id="fa3a2-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-146">Click OK.</span></span>
32. <span data-ttu-id="fa3a2-147">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-147">Click Add String.</span></span>
33. <span data-ttu-id="fa3a2-148">Ange "Lines counting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="fa3a2-149">Radinventering</span><span class="sxs-lookup"><span data-stu-id="fa3a2-149">Lines counting</span></span>  
34. <span data-ttu-id="fa3a2-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-150">Click OK.</span></span>
35. <span data-ttu-id="fa3a2-151">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-151">Click Add String.</span></span>
36. <span data-ttu-id="fa3a2-152">Ange "Total amount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="fa3a2-153">Totalt antal timmar</span><span class="sxs-lookup"><span data-stu-id="fa3a2-153">Total amount</span></span>  
37. <span data-ttu-id="fa3a2-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-154">Click OK.</span></span>
38. <span data-ttu-id="fa3a2-155">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="fa3a2-156">Välj "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="fa3a2-157">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-157">Click Bind.</span></span>
    * <span data-ttu-id="fa3a2-158">Skapa en summeringsrad för varje memorerat block.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="fa3a2-159">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-159">Click the Format tab.</span></span>
42. <span data-ttu-id="fa3a2-160">Välj "Intrastat\Data\Totals by blocks\Block code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="fa3a2-161">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="fa3a2-162">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-162">Click Edit formula.</span></span>
45. <span data-ttu-id="fa3a2-163">Ange ""Block id: " & "  " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="fa3a2-164">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="fa3a2-164">"Block id: " &</span></span>  
46. <span data-ttu-id="fa3a2-165">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="fa3a2-166">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="fa3a2-167">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-167">Click Add data source.</span></span>
49. <span data-ttu-id="fa3a2-168">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-168">Click Save.</span></span>
50. <span data-ttu-id="fa3a2-169">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-169">Close the page.</span></span>
51. <span data-ttu-id="fa3a2-170">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-170">Click the Format tab.</span></span>
52. <span data-ttu-id="fa3a2-171">Välj "Intrastat\Data\Totals by blocks\Lines counting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="fa3a2-172">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="fa3a2-173">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-173">Click Edit formula.</span></span>
    * <span data-ttu-id="fa3a2-174">Skapa utleverans för det antal rader i varje block som presenteras i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="fa3a2-175">I formelfältet anger du ""Number of lines in this block: " & ".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="fa3a2-176">"Antal rader i detta block:  " & </span><span class="sxs-lookup"><span data-stu-id="fa3a2-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="fa3a2-177">I formelfältet anger du ""Number of lines in this block: " & TEXT(".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="fa3a2-178">"Antal rader i detta block: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="fa3a2-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="fa3a2-179">Välj "Data collection functions\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="fa3a2-180">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-180">Click Add function.</span></span>
59. <span data-ttu-id="fa3a2-181">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-181">Click Add data source.</span></span>
60. <span data-ttu-id="fa3a2-182">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="fa3a2-183">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="fa3a2-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="fa3a2-184">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="fa3a2-185">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="fa3a2-186">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-186">Click Add data source.</span></span>
64. <span data-ttu-id="fa3a2-187">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="fa3a2-188">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="fa3a2-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="fa3a2-189">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="fa3a2-190">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-190">Click Add data source.</span></span>
67. <span data-ttu-id="fa3a2-191">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="fa3a2-192">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="fa3a2-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="fa3a2-193">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-193">Click Save.</span></span>
69. <span data-ttu-id="fa3a2-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-194">Close the page.</span></span>
70. <span data-ttu-id="fa3a2-195">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-195">Click the Format tab.</span></span>
71. <span data-ttu-id="fa3a2-196">I trädet väljer du "Intrastat\Data\Totals by blocks\Total amount".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="fa3a2-197">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="fa3a2-198">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-198">Click Edit formula.</span></span>
    * <span data-ttu-id="fa3a2-199">Skapa utleverans som ska vara summan av det fakturerade beloppet för varje textblock som visas i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="fa3a2-200">I formelfältet anger du ""Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="fa3a2-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="fa3a2-201">”Summan av det fakturerade beloppet: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="fa3a2-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="fa3a2-202">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-202">Click Save.</span></span>
76. <span data-ttu-id="fa3a2-203">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-203">Close the page.</span></span>
77. <span data-ttu-id="fa3a2-204">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-204">Click Save.</span></span>
78. <span data-ttu-id="fa3a2-205">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fa3a2-205">Close the page.</span></span>

