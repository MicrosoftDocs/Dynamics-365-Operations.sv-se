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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cef61787e50561eaac4fd52741ab5f90d9c4171d
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406507"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="1849f-103">ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)</span><span class="sxs-lookup"><span data-stu-id="1849f-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1849f-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="1849f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="1849f-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="1849f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="1849f-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping”.</span><span class="sxs-lookup"><span data-stu-id="1849f-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="1849f-107">Designa en rapport för att presentera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="1849f-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="1849f-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="1849f-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="1849f-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="1849f-110">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="1849f-111">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="1849f-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="1849f-112">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="1849f-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="1849f-113">Ange "Ledger journal report" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="1849f-114">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="1849f-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="1849f-115">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="1849f-115">Click Create configuration.</span></span>
8. <span data-ttu-id="1849f-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="1849f-116">Click Designer.</span></span>
9. <span data-ttu-id="1849f-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="1849f-118">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="1849f-119">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="1849f-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-120">Click OK.</span></span>
13. <span data-ttu-id="1849f-121">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="1849f-122">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="1849f-123">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="1849f-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="1849f-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-124">Click OK.</span></span>
17. <span data-ttu-id="1849f-125">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="1849f-126">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="1849f-127">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="1849f-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-128">Click OK.</span></span>
21. <span data-ttu-id="1849f-129">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="1849f-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="1849f-131">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="1849f-132">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="1849f-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-133">Click OK.</span></span>
26. <span data-ttu-id="1849f-134">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="1849f-135">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="1849f-136">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="1849f-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-137">Click OK.</span></span>
30. <span data-ttu-id="1849f-138">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="1849f-139">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="1849f-140">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="1849f-141">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="1849f-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-142">Click OK.</span></span>
35. <span data-ttu-id="1849f-143">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="1849f-144">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="1849f-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-145">Click OK.</span></span>
38. <span data-ttu-id="1849f-146">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="1849f-147">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="1849f-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="1849f-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-148">Click OK.</span></span>
41. <span data-ttu-id="1849f-149">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="1849f-150">Ange "Dt" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="1849f-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-151">Click OK.</span></span>
44. <span data-ttu-id="1849f-152">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="1849f-153">Ange "Ct" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="1849f-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-154">Click OK.</span></span>
47. <span data-ttu-id="1849f-155">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="1849f-156">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="1849f-157">Ange "Dimensions" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="1849f-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-158">Click OK.</span></span>
51. <span data-ttu-id="1849f-159">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="1849f-160">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1849f-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="1849f-161">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="1849f-162">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="1849f-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-163">Click OK.</span></span>
56. <span data-ttu-id="1849f-164">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="1849f-165">Ange "Value" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="1849f-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-166">Click OK.</span></span>
59. <span data-ttu-id="1849f-167">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="1849f-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="1849f-168">Ange "Desc" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="1849f-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="1849f-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1849f-169">Click OK.</span></span>
<span data-ttu-id="1849f-170">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="1849f-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="1849f-171">Mappa rapportelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="1849f-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="1849f-172">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="1849f-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="1849f-173">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="1849f-174">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="1849f-175">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="1849f-176">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="1849f-177">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="1849f-178">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="1849f-179">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-179">Click Bind.</span></span>
9. <span data-ttu-id="1849f-180">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="1849f-181">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="1849f-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-182">Click Bind.</span></span>
12. <span data-ttu-id="1849f-183">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="1849f-184">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="1849f-185">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-185">Click Bind.</span></span>
15. <span data-ttu-id="1849f-186">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="1849f-187">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="1849f-188">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-188">Click Bind.</span></span>
18. <span data-ttu-id="1849f-189">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="1849f-190">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="1849f-191">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-191">Click Bind.</span></span>
21. <span data-ttu-id="1849f-192">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="1849f-193">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="1849f-194">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-194">Click Bind.</span></span>
24. <span data-ttu-id="1849f-195">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="1849f-196">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="1849f-197">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-197">Click Bind.</span></span>
27. <span data-ttu-id="1849f-198">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="1849f-199">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="1849f-200">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-200">Click Bind.</span></span>
30. <span data-ttu-id="1849f-201">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="1849f-202">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="1849f-203">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-203">Click Bind.</span></span>
33. <span data-ttu-id="1849f-204">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="1849f-205">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="1849f-206">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-206">Click Bind.</span></span>
36. <span data-ttu-id="1849f-207">Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="1849f-208">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="1849f-209">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-209">Click Bind.</span></span>
39. <span data-ttu-id="1849f-210">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="1849f-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="1849f-211">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="1849f-212">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-212">Click Bind.</span></span>
42. <span data-ttu-id="1849f-213">Välj "Root: XML Element\Company: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="1849f-214">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="1849f-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="1849f-215">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="1849f-215">Click Bind.</span></span>
45. <span data-ttu-id="1849f-216">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1849f-216">Click Save.</span></span>
46. <span data-ttu-id="1849f-217">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1849f-217">Close the page.</span></span>
<span data-ttu-id="1849f-218">![ER-åtgärdsdesignersida](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="1849f-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

