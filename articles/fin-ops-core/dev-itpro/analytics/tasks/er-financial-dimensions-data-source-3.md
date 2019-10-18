---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 29dcf008f342603615241ab75860893cadc2b69e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182449"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a><span data-ttu-id="f4882-103">ER Använd ekonomiska dimensioner som en datakälla (Del 3: Designa rapporten)</span><span class="sxs-lookup"><span data-stu-id="f4882-103">ER Use financial dimensions as a data source (Part 3: Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4882-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="f4882-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="f4882-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="f4882-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="f4882-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping”.</span><span class="sxs-lookup"><span data-stu-id="f4882-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="f4882-107">Designa en rapport för att presentera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="f4882-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="f4882-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f4882-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f4882-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f4882-110">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="f4882-111">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="f4882-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="f4882-112">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="f4882-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="f4882-113">Ange "Ledger journal report" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="f4882-114">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="f4882-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="f4882-115">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f4882-115">Click Create configuration.</span></span>
8. <span data-ttu-id="f4882-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f4882-116">Click Designer.</span></span>
9. <span data-ttu-id="f4882-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="f4882-118">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="f4882-119">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="f4882-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-120">Click OK.</span></span>
13. <span data-ttu-id="f4882-121">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="f4882-122">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="f4882-123">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f4882-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="f4882-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-124">Click OK.</span></span>
17. <span data-ttu-id="f4882-125">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="f4882-126">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="f4882-127">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="f4882-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-128">Click OK.</span></span>
21. <span data-ttu-id="f4882-129">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="f4882-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="f4882-131">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="f4882-132">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="f4882-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-133">Click OK.</span></span>
26. <span data-ttu-id="f4882-134">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f4882-135">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="f4882-136">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="f4882-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-137">Click OK.</span></span>
30. <span data-ttu-id="f4882-138">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="f4882-139">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="f4882-140">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="f4882-141">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="f4882-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-142">Click OK.</span></span>
35. <span data-ttu-id="f4882-143">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="f4882-144">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="f4882-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-145">Click OK.</span></span>
38. <span data-ttu-id="f4882-146">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="f4882-147">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f4882-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="f4882-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-148">Click OK.</span></span>
41. <span data-ttu-id="f4882-149">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="f4882-150">Ange "Dt" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="f4882-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-151">Click OK.</span></span>
44. <span data-ttu-id="f4882-152">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="f4882-153">Ange "Ct" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="f4882-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-154">Click OK.</span></span>
47. <span data-ttu-id="f4882-155">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="f4882-156">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="f4882-157">Ange "Dimensions" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="f4882-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-158">Click OK.</span></span>
51. <span data-ttu-id="f4882-159">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="f4882-160">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f4882-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="f4882-161">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="f4882-162">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="f4882-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-163">Click OK.</span></span>
56. <span data-ttu-id="f4882-164">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="f4882-165">Ange "Value" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="f4882-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-166">Click OK.</span></span>
59. <span data-ttu-id="f4882-167">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="f4882-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="f4882-168">Ange "Desc" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f4882-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="f4882-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f4882-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="f4882-170">Mappa rapportelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="f4882-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="f4882-171">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="f4882-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="f4882-172">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f4882-173">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="f4882-174">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="f4882-175">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="f4882-176">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="f4882-177">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="f4882-178">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-178">Click Bind.</span></span>
9. <span data-ttu-id="f4882-179">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="f4882-180">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="f4882-181">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-181">Click Bind.</span></span>
12. <span data-ttu-id="f4882-182">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="f4882-183">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="f4882-184">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-184">Click Bind.</span></span>
15. <span data-ttu-id="f4882-185">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="f4882-186">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="f4882-187">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-187">Click Bind.</span></span>
18. <span data-ttu-id="f4882-188">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="f4882-189">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="f4882-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-190">Click Bind.</span></span>
21. <span data-ttu-id="f4882-191">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="f4882-192">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="f4882-193">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-193">Click Bind.</span></span>
24. <span data-ttu-id="f4882-194">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="f4882-195">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="f4882-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-196">Click Bind.</span></span>
27. <span data-ttu-id="f4882-197">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="f4882-198">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="f4882-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-199">Click Bind.</span></span>
30. <span data-ttu-id="f4882-200">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="f4882-201">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="f4882-202">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-202">Click Bind.</span></span>
33. <span data-ttu-id="f4882-203">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="f4882-204">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="f4882-205">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-205">Click Bind.</span></span>
36. <span data-ttu-id="f4882-206">Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="f4882-207">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="f4882-208">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-208">Click Bind.</span></span>
39. <span data-ttu-id="f4882-209">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="f4882-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="f4882-210">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="f4882-211">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-211">Click Bind.</span></span>
42. <span data-ttu-id="f4882-212">Välj "Root: XML Element\Company: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="f4882-213">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f4882-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="f4882-214">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f4882-214">Click Bind.</span></span>
45. <span data-ttu-id="f4882-215">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f4882-215">Click Save.</span></span>
46. <span data-ttu-id="f4882-216">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f4882-216">Close the page.</span></span>

