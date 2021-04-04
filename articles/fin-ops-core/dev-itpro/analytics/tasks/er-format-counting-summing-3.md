---
title: ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af95399118b9059b9bead3a1b84203cf3b6e74c2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567126"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="49695-104">ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)</span><span class="sxs-lookup"><span data-stu-id="49695-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="49695-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="49695-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="49695-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="49695-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="49695-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 2: Configure computations)"</span><span class="sxs-lookup"><span data-stu-id="49695-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="49695-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="49695-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="49695-109">Konfigurera den här rapporten om du vill använda inventerings- och summeringsinformation</span><span class="sxs-lookup"><span data-stu-id="49695-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="49695-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="49695-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="49695-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="49695-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="49695-112">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="49695-113">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="49695-114">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="49695-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="49695-115">Click Designer.</span></span>
7. <span data-ttu-id="49695-116">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="49695-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="49695-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="49695-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="49695-118">Lägg till en ny datakälla för att få listan över memorerade block.</span><span class="sxs-lookup"><span data-stu-id="49695-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="49695-119">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="49695-120">Ange "$BlocksList" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="49695-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="49695-121">$BlocksList</span></span>  
11. <span data-ttu-id="49695-122">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="49695-122">Click Edit formula.</span></span>
12. <span data-ttu-id="49695-123">Välj "Data collection functions\COLLECTEDLIST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="49695-124">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="49695-124">Click Add function.</span></span>
14. <span data-ttu-id="49695-125">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="49695-125">Click Add data source.</span></span>
15. <span data-ttu-id="49695-126">Ange "COLLECTEDLIST('$BlockName', " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="49695-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="49695-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="49695-128">Ange "COLLECTEDLIST('$BlockName', "\*")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="49695-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="49695-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="49695-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="49695-130">Click Save.</span></span>
    * <span data-ttu-id="49695-131">Mönstret ”\*” innebär att alla block kommer att inkluderas i listan för denna post.</span><span class="sxs-lookup"><span data-stu-id="49695-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="49695-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49695-132">Close the page.</span></span>
19. <span data-ttu-id="49695-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49695-133">Click OK.</span></span>
20. <span data-ttu-id="49695-134">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="49695-134">Click the Format tab.</span></span>
21. <span data-ttu-id="49695-135">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="49695-136">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="49695-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="49695-137">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="49695-138">Ange "Totals by blocks" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="49695-139">Summor per block</span><span class="sxs-lookup"><span data-stu-id="49695-139">Totals by blocks</span></span>  
25. <span data-ttu-id="49695-140">Välj "New line - Windows (CR LF)" i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="49695-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="49695-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49695-141">Click OK.</span></span>
27. <span data-ttu-id="49695-142">Välj "Intrastat\Data\Totals by blocks" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="49695-143">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="49695-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="49695-144">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="49695-145">Ange "Block code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="49695-146">Blockkod</span><span class="sxs-lookup"><span data-stu-id="49695-146">Block code</span></span>  
31. <span data-ttu-id="49695-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49695-147">Click OK.</span></span>
32. <span data-ttu-id="49695-148">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="49695-148">Click Add String.</span></span>
33. <span data-ttu-id="49695-149">Ange "Lines counting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="49695-150">Radinventering</span><span class="sxs-lookup"><span data-stu-id="49695-150">Lines counting</span></span>  
34. <span data-ttu-id="49695-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49695-151">Click OK.</span></span>
35. <span data-ttu-id="49695-152">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="49695-152">Click Add String.</span></span>
36. <span data-ttu-id="49695-153">Ange "Total amount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="49695-154">Totalt antal timmar</span><span class="sxs-lookup"><span data-stu-id="49695-154">Total amount</span></span>  
37. <span data-ttu-id="49695-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="49695-155">Click OK.</span></span>
38. <span data-ttu-id="49695-156">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="49695-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="49695-157">Välj "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="49695-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="49695-158">Click Bind.</span></span>
    * <span data-ttu-id="49695-159">Skapa en summeringsrad för varje memorerat block.</span><span class="sxs-lookup"><span data-stu-id="49695-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="49695-160">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="49695-160">Click the Format tab.</span></span>
42. <span data-ttu-id="49695-161">Välj "Intrastat\Data\Totals by blocks\Block code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="49695-162">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="49695-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="49695-163">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="49695-163">Click Edit formula.</span></span>
45. <span data-ttu-id="49695-164">Ange ""Block id: " & "  " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="49695-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="49695-165">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="49695-165">"Block id: " &</span></span>  
46. <span data-ttu-id="49695-166">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="49695-167">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="49695-168">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="49695-168">Click Add data source.</span></span>
49. <span data-ttu-id="49695-169">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="49695-169">Click Save.</span></span>
50. <span data-ttu-id="49695-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49695-170">Close the page.</span></span>
51. <span data-ttu-id="49695-171">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="49695-171">Click the Format tab.</span></span>
52. <span data-ttu-id="49695-172">Välj "Intrastat\Data\Totals by blocks\Lines counting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="49695-173">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="49695-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="49695-174">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="49695-174">Click Edit formula.</span></span>
    * <span data-ttu-id="49695-175">Skapa utleverans för det antal rader i varje block som presenteras i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="49695-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="49695-176">I formelfältet anger du ""Number of lines in this block: " & ".</span><span class="sxs-lookup"><span data-stu-id="49695-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="49695-177">"Antal rader i detta block:  " & </span><span class="sxs-lookup"><span data-stu-id="49695-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="49695-178">I formelfältet anger du ""Number of lines in this block: " & TEXT(".</span><span class="sxs-lookup"><span data-stu-id="49695-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="49695-179">"Antal rader i detta block: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="49695-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="49695-180">Välj "Data collection functions\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="49695-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="49695-181">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="49695-181">Click Add function.</span></span>
59. <span data-ttu-id="49695-182">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="49695-182">Click Add data source.</span></span>
60. <span data-ttu-id="49695-183">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="49695-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="49695-184">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="49695-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="49695-185">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="49695-186">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="49695-187">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="49695-187">Click Add data source.</span></span>
64. <span data-ttu-id="49695-188">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="49695-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="49695-189">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="49695-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="49695-190">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="49695-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="49695-191">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="49695-191">Click Add data source.</span></span>
67. <span data-ttu-id="49695-192">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="49695-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="49695-193">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="49695-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="49695-194">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="49695-194">Click Save.</span></span>
69. <span data-ttu-id="49695-195">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49695-195">Close the page.</span></span>
70. <span data-ttu-id="49695-196">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="49695-196">Click the Format tab.</span></span>
71. <span data-ttu-id="49695-197">I trädet väljer du "Intrastat\Data\Totals by blocks\Total amount".</span><span class="sxs-lookup"><span data-stu-id="49695-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="49695-198">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="49695-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="49695-199">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="49695-199">Click Edit formula.</span></span>
    * <span data-ttu-id="49695-200">Skapa utleverans som ska vara summan av det fakturerade beloppet för varje textblock som visas i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="49695-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="49695-201">I formelfältet anger du ""Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="49695-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="49695-202">”Summan av det fakturerade beloppet: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="49695-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="49695-203">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="49695-203">Click Save.</span></span>
76. <span data-ttu-id="49695-204">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49695-204">Close the page.</span></span>
77. <span data-ttu-id="49695-205">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="49695-205">Click Save.</span></span>
78. <span data-ttu-id="49695-206">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="49695-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]