---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 3)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9594a12c28109d80c6ee07a9ee38f4923963dca
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565248"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="56e7f-104">ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)</span><span class="sxs-lookup"><span data-stu-id="56e7f-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="56e7f-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="56e7f-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="56e7f-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="56e7f-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="56e7f-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping)”.</span><span class="sxs-lookup"><span data-stu-id="56e7f-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="56e7f-108">Designa en rapport för att presentera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="56e7f-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="56e7f-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="56e7f-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="56e7f-110">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="56e7f-111">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="56e7f-112">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="56e7f-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="56e7f-113">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="56e7f-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="56e7f-114">Ange "Ledger journal report" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="56e7f-115">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="56e7f-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="56e7f-116">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="56e7f-116">Click Create configuration.</span></span>
8. <span data-ttu-id="56e7f-117">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="56e7f-117">Click Designer.</span></span>
9. <span data-ttu-id="56e7f-118">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="56e7f-119">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="56e7f-120">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="56e7f-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-121">Click OK.</span></span>
13. <span data-ttu-id="56e7f-122">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="56e7f-123">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="56e7f-124">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="56e7f-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="56e7f-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-125">Click OK.</span></span>
17. <span data-ttu-id="56e7f-126">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="56e7f-127">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="56e7f-128">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="56e7f-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-129">Click OK.</span></span>
21. <span data-ttu-id="56e7f-130">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="56e7f-131">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="56e7f-132">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="56e7f-133">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="56e7f-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-134">Click OK.</span></span>
26. <span data-ttu-id="56e7f-135">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="56e7f-136">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="56e7f-137">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="56e7f-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-138">Click OK.</span></span>
30. <span data-ttu-id="56e7f-139">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="56e7f-140">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="56e7f-141">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="56e7f-142">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="56e7f-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-143">Click OK.</span></span>
35. <span data-ttu-id="56e7f-144">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="56e7f-145">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="56e7f-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-146">Click OK.</span></span>
38. <span data-ttu-id="56e7f-147">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="56e7f-148">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="56e7f-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="56e7f-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-149">Click OK.</span></span>
41. <span data-ttu-id="56e7f-150">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="56e7f-151">Ange "Dt" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="56e7f-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-152">Click OK.</span></span>
44. <span data-ttu-id="56e7f-153">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="56e7f-154">Ange "Ct" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="56e7f-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-155">Click OK.</span></span>
47. <span data-ttu-id="56e7f-156">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="56e7f-157">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="56e7f-158">Ange "Dimensions" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="56e7f-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-159">Click OK.</span></span>
51. <span data-ttu-id="56e7f-160">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="56e7f-161">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="56e7f-162">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="56e7f-163">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="56e7f-164">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-164">Click OK.</span></span>
56. <span data-ttu-id="56e7f-165">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="56e7f-166">Ange "Value" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="56e7f-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-167">Click OK.</span></span>
59. <span data-ttu-id="56e7f-168">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="56e7f-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="56e7f-169">Ange "Desc" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="56e7f-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="56e7f-170">Click OK.</span></span>
<span data-ttu-id="56e7f-171">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="56e7f-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="56e7f-172">Mappa rapportelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="56e7f-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="56e7f-173">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="56e7f-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="56e7f-174">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="56e7f-175">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="56e7f-176">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="56e7f-177">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="56e7f-178">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="56e7f-179">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="56e7f-180">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-180">Click Bind.</span></span>
9. <span data-ttu-id="56e7f-181">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="56e7f-182">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="56e7f-183">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-183">Click Bind.</span></span>
12. <span data-ttu-id="56e7f-184">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="56e7f-185">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="56e7f-186">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-186">Click Bind.</span></span>
15. <span data-ttu-id="56e7f-187">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="56e7f-188">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="56e7f-189">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-189">Click Bind.</span></span>
18. <span data-ttu-id="56e7f-190">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="56e7f-191">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="56e7f-192">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-192">Click Bind.</span></span>
21. <span data-ttu-id="56e7f-193">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="56e7f-194">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="56e7f-195">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-195">Click Bind.</span></span>
24. <span data-ttu-id="56e7f-196">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="56e7f-197">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="56e7f-198">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-198">Click Bind.</span></span>
27. <span data-ttu-id="56e7f-199">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="56e7f-200">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="56e7f-201">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-201">Click Bind.</span></span>
30. <span data-ttu-id="56e7f-202">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="56e7f-203">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="56e7f-204">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-204">Click Bind.</span></span>
33. <span data-ttu-id="56e7f-205">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="56e7f-206">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="56e7f-207">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-207">Click Bind.</span></span>
36. <span data-ttu-id="56e7f-208">Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="56e7f-209">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="56e7f-210">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-210">Click Bind.</span></span>
39. <span data-ttu-id="56e7f-211">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="56e7f-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="56e7f-212">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="56e7f-213">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-213">Click Bind.</span></span>
42. <span data-ttu-id="56e7f-214">Välj "Root: XML Element\Company: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="56e7f-215">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="56e7f-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="56e7f-216">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="56e7f-216">Click Bind.</span></span>
45. <span data-ttu-id="56e7f-217">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="56e7f-217">Click Save.</span></span>
46. <span data-ttu-id="56e7f-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="56e7f-218">Close the page.</span></span>
<span data-ttu-id="56e7f-219">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="56e7f-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]