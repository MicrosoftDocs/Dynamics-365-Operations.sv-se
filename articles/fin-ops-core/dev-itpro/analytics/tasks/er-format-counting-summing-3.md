---
title: ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 3)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a69dd28051d8e98643eb95c663525075bed8dec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092982"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="9d5b5-104">ER Konfigurera format för att utföra inventering och summering (Del 3 - Använd beräkningar för att skapa utmatningen)</span><span class="sxs-lookup"><span data-stu-id="9d5b5-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9d5b5-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="9d5b5-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="9d5b5-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 2: Configure computations)"</span><span class="sxs-lookup"><span data-stu-id="9d5b5-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="9d5b5-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="9d5b5-109">Konfigurera den här rapporten om du vill använda inventerings- och summeringsinformation</span><span class="sxs-lookup"><span data-stu-id="9d5b5-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="9d5b5-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9d5b5-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9d5b5-112">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="9d5b5-113">Expandera "Intrastat model\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="9d5b5-114">Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="9d5b5-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-115">Click Designer.</span></span>
7. <span data-ttu-id="9d5b5-116">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="9d5b5-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="9d5b5-118">Lägg till en ny datakälla för att få listan över memorerade block.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="9d5b5-119">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="9d5b5-120">Ange "$BlocksList" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="9d5b5-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="9d5b5-121">$BlocksList</span></span>  
11. <span data-ttu-id="9d5b5-122">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-122">Click Edit formula.</span></span>
12. <span data-ttu-id="9d5b5-123">Välj "Data collection functions\COLLECTEDLIST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="9d5b5-124">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-124">Click Add function.</span></span>
14. <span data-ttu-id="9d5b5-125">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-125">Click Add data source.</span></span>
15. <span data-ttu-id="9d5b5-126">Ange "COLLECTEDLIST('$BlockName', " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="9d5b5-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="9d5b5-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="9d5b5-128">Ange "COLLECTEDLIST('$BlockName', "\*")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="9d5b5-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="9d5b5-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="9d5b5-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-130">Click Save.</span></span>
    * <span data-ttu-id="9d5b5-131">Mönstret ”\*” innebär att alla block kommer att inkluderas i listan för denna post.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="9d5b5-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-132">Close the page.</span></span>
19. <span data-ttu-id="9d5b5-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-133">Click OK.</span></span>
20. <span data-ttu-id="9d5b5-134">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-134">Click the Format tab.</span></span>
21. <span data-ttu-id="9d5b5-135">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="9d5b5-136">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="9d5b5-137">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="9d5b5-138">Ange "Totals by blocks" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="9d5b5-139">Summor per block</span><span class="sxs-lookup"><span data-stu-id="9d5b5-139">Totals by blocks</span></span>  
25. <span data-ttu-id="9d5b5-140">Välj "New line - Windows (CR LF)" i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="9d5b5-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-141">Click OK.</span></span>
27. <span data-ttu-id="9d5b5-142">Välj "Intrastat\Data\Totals by blocks" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="9d5b5-143">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="9d5b5-144">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="9d5b5-145">Ange "Block code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="9d5b5-146">Blockkod</span><span class="sxs-lookup"><span data-stu-id="9d5b5-146">Block code</span></span>  
31. <span data-ttu-id="9d5b5-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-147">Click OK.</span></span>
32. <span data-ttu-id="9d5b5-148">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-148">Click Add String.</span></span>
33. <span data-ttu-id="9d5b5-149">Ange "Lines counting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="9d5b5-150">Radinventering</span><span class="sxs-lookup"><span data-stu-id="9d5b5-150">Lines counting</span></span>  
34. <span data-ttu-id="9d5b5-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-151">Click OK.</span></span>
35. <span data-ttu-id="9d5b5-152">Klicka på Add string.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-152">Click Add String.</span></span>
36. <span data-ttu-id="9d5b5-153">Ange "Total amount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="9d5b5-154">Totalt antal timmar</span><span class="sxs-lookup"><span data-stu-id="9d5b5-154">Total amount</span></span>  
37. <span data-ttu-id="9d5b5-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-155">Click OK.</span></span>
38. <span data-ttu-id="9d5b5-156">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="9d5b5-157">Välj "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="9d5b5-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-158">Click Bind.</span></span>
    * <span data-ttu-id="9d5b5-159">Skapa en summeringsrad för varje memorerat block.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="9d5b5-160">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-160">Click the Format tab.</span></span>
42. <span data-ttu-id="9d5b5-161">Välj "Intrastat\Data\Totals by blocks\Block code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="9d5b5-162">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="9d5b5-163">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-163">Click Edit formula.</span></span>
45. <span data-ttu-id="9d5b5-164">Ange ""Block id: " & "  " i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="9d5b5-165">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="9d5b5-165">"Block id: " &</span></span>  
46. <span data-ttu-id="9d5b5-166">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="9d5b5-167">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="9d5b5-168">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-168">Click Add data source.</span></span>
49. <span data-ttu-id="9d5b5-169">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-169">Click Save.</span></span>
50. <span data-ttu-id="9d5b5-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-170">Close the page.</span></span>
51. <span data-ttu-id="9d5b5-171">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-171">Click the Format tab.</span></span>
52. <span data-ttu-id="9d5b5-172">Välj "Intrastat\Data\Totals by blocks\Lines counting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="9d5b5-173">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="9d5b5-174">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-174">Click Edit formula.</span></span>
    * <span data-ttu-id="9d5b5-175">Skapa utleverans för det antal rader i varje block som presenteras i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="9d5b5-176">I formelfältet anger du ""Number of lines in this block: " & ".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="9d5b5-177">"Antal rader i detta block:  " & </span><span class="sxs-lookup"><span data-stu-id="9d5b5-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="9d5b5-178">I formelfältet anger du ""Number of lines in this block: " & TEXT(".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="9d5b5-179">"Antal rader i detta block: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="9d5b5-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="9d5b5-180">Välj "Data collection functions\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="9d5b5-181">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-181">Click Add function.</span></span>
59. <span data-ttu-id="9d5b5-182">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-182">Click Add data source.</span></span>
60. <span data-ttu-id="9d5b5-183">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="9d5b5-184">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="9d5b5-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="9d5b5-185">Expandera "$BlocksList" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="9d5b5-186">Välj "$BlocksList\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="9d5b5-187">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-187">Click Add data source.</span></span>
64. <span data-ttu-id="9d5b5-188">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="9d5b5-189">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="9d5b5-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="9d5b5-190">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="9d5b5-191">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-191">Click Add data source.</span></span>
67. <span data-ttu-id="9d5b5-192">I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="9d5b5-193">"Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="9d5b5-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="9d5b5-194">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-194">Click Save.</span></span>
69. <span data-ttu-id="9d5b5-195">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-195">Close the page.</span></span>
70. <span data-ttu-id="9d5b5-196">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-196">Click the Format tab.</span></span>
71. <span data-ttu-id="9d5b5-197">I trädet väljer du "Intrastat\Data\Totals by blocks\Total amount".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="9d5b5-198">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="9d5b5-199">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-199">Click Edit formula.</span></span>
    * <span data-ttu-id="9d5b5-200">Skapa utleverans som ska vara summan av det fakturerade beloppet för varje textblock som visas i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="9d5b5-201">I formelfältet anger du ""Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))".</span><span class="sxs-lookup"><span data-stu-id="9d5b5-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="9d5b5-202">”Summan av det fakturerade beloppet: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="9d5b5-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="9d5b5-203">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-203">Click Save.</span></span>
76. <span data-ttu-id="9d5b5-204">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-204">Close the page.</span></span>
77. <span data-ttu-id="9d5b5-205">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-205">Click Save.</span></span>
78. <span data-ttu-id="9d5b5-206">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d5b5-206">Close the page.</span></span>

