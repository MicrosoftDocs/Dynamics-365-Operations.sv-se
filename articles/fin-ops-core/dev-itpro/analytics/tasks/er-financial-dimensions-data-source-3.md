---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a12f88f1e8b5e451bc8a5c5486d820da61bf3ad0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684797"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="ade74-103">ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)</span><span class="sxs-lookup"><span data-stu-id="ade74-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ade74-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="ade74-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ade74-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="ade74-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="ade74-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping)”.</span><span class="sxs-lookup"><span data-stu-id="ade74-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="ade74-107">Designa en rapport för att presentera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="ade74-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="ade74-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="ade74-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ade74-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ade74-110">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="ade74-111">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="ade74-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="ade74-112">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="ade74-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="ade74-113">Ange "Ledger journal report" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="ade74-114">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="ade74-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="ade74-115">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ade74-115">Click Create configuration.</span></span>
8. <span data-ttu-id="ade74-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="ade74-116">Click Designer.</span></span>
9. <span data-ttu-id="ade74-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="ade74-118">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="ade74-119">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="ade74-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-120">Click OK.</span></span>
13. <span data-ttu-id="ade74-121">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="ade74-122">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="ade74-123">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="ade74-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="ade74-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-124">Click OK.</span></span>
17. <span data-ttu-id="ade74-125">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="ade74-126">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="ade74-127">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="ade74-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-128">Click OK.</span></span>
21. <span data-ttu-id="ade74-129">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="ade74-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="ade74-131">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="ade74-132">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="ade74-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-133">Click OK.</span></span>
26. <span data-ttu-id="ade74-134">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="ade74-135">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="ade74-136">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="ade74-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-137">Click OK.</span></span>
30. <span data-ttu-id="ade74-138">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="ade74-139">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="ade74-140">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="ade74-141">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="ade74-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-142">Click OK.</span></span>
35. <span data-ttu-id="ade74-143">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="ade74-144">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="ade74-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-145">Click OK.</span></span>
38. <span data-ttu-id="ade74-146">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="ade74-147">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="ade74-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="ade74-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-148">Click OK.</span></span>
41. <span data-ttu-id="ade74-149">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="ade74-150">Ange "Dt" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="ade74-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-151">Click OK.</span></span>
44. <span data-ttu-id="ade74-152">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="ade74-153">Ange "Ct" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="ade74-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-154">Click OK.</span></span>
47. <span data-ttu-id="ade74-155">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="ade74-156">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="ade74-157">Ange "Dimensions" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="ade74-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-158">Click OK.</span></span>
51. <span data-ttu-id="ade74-159">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="ade74-160">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ade74-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="ade74-161">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="ade74-162">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="ade74-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-163">Click OK.</span></span>
56. <span data-ttu-id="ade74-164">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="ade74-165">Ange "Value" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="ade74-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-166">Click OK.</span></span>
59. <span data-ttu-id="ade74-167">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="ade74-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="ade74-168">Ange "Desc" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="ade74-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="ade74-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ade74-169">Click OK.</span></span>
<span data-ttu-id="ade74-170">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="ade74-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="ade74-171">Mappa rapportelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="ade74-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="ade74-172">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="ade74-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ade74-173">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ade74-174">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="ade74-175">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="ade74-176">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="ade74-177">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="ade74-178">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="ade74-179">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-179">Click Bind.</span></span>
9. <span data-ttu-id="ade74-180">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="ade74-181">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="ade74-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-182">Click Bind.</span></span>
12. <span data-ttu-id="ade74-183">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="ade74-184">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="ade74-185">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-185">Click Bind.</span></span>
15. <span data-ttu-id="ade74-186">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="ade74-187">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="ade74-188">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-188">Click Bind.</span></span>
18. <span data-ttu-id="ade74-189">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="ade74-190">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="ade74-191">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-191">Click Bind.</span></span>
21. <span data-ttu-id="ade74-192">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="ade74-193">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="ade74-194">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-194">Click Bind.</span></span>
24. <span data-ttu-id="ade74-195">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="ade74-196">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="ade74-197">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-197">Click Bind.</span></span>
27. <span data-ttu-id="ade74-198">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="ade74-199">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="ade74-200">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-200">Click Bind.</span></span>
30. <span data-ttu-id="ade74-201">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="ade74-202">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="ade74-203">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-203">Click Bind.</span></span>
33. <span data-ttu-id="ade74-204">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="ade74-205">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="ade74-206">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-206">Click Bind.</span></span>
36. <span data-ttu-id="ade74-207">Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="ade74-208">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="ade74-209">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-209">Click Bind.</span></span>
39. <span data-ttu-id="ade74-210">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="ade74-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="ade74-211">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="ade74-212">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-212">Click Bind.</span></span>
42. <span data-ttu-id="ade74-213">Välj "Root: XML Element\Company: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="ade74-214">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="ade74-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="ade74-215">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="ade74-215">Click Bind.</span></span>
45. <span data-ttu-id="ade74-216">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ade74-216">Click Save.</span></span>
46. <span data-ttu-id="ade74-217">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ade74-217">Close the page.</span></span>
<span data-ttu-id="ade74-218">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="ade74-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

