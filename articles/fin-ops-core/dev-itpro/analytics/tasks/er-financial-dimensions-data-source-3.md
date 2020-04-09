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
ms.openlocfilehash: 7bbbc81eaf8c13e8d13e30a0276e38453e07ead9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142534"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="469d5-103">ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)</span><span class="sxs-lookup"><span data-stu-id="469d5-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="469d5-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="469d5-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="469d5-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="469d5-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="469d5-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping”.</span><span class="sxs-lookup"><span data-stu-id="469d5-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="469d5-107">Designa en rapport för att presentera ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="469d5-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="469d5-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="469d5-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="469d5-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="469d5-110">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="469d5-111">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="469d5-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="469d5-112">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="469d5-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="469d5-113">Ange "Ledger journal report" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="469d5-114">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="469d5-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="469d5-115">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="469d5-115">Click Create configuration.</span></span>
8. <span data-ttu-id="469d5-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="469d5-116">Click Designer.</span></span>
9. <span data-ttu-id="469d5-117">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="469d5-118">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="469d5-119">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="469d5-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-120">Click OK.</span></span>
13. <span data-ttu-id="469d5-121">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="469d5-122">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="469d5-123">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="469d5-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="469d5-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-124">Click OK.</span></span>
17. <span data-ttu-id="469d5-125">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="469d5-126">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="469d5-127">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="469d5-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-128">Click OK.</span></span>
21. <span data-ttu-id="469d5-129">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="469d5-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="469d5-131">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="469d5-132">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="469d5-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-133">Click OK.</span></span>
26. <span data-ttu-id="469d5-134">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="469d5-135">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="469d5-136">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="469d5-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-137">Click OK.</span></span>
30. <span data-ttu-id="469d5-138">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="469d5-139">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="469d5-140">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="469d5-141">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="469d5-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-142">Click OK.</span></span>
35. <span data-ttu-id="469d5-143">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="469d5-144">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="469d5-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-145">Click OK.</span></span>
38. <span data-ttu-id="469d5-146">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="469d5-147">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="469d5-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="469d5-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-148">Click OK.</span></span>
41. <span data-ttu-id="469d5-149">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="469d5-150">Ange "Dt" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="469d5-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-151">Click OK.</span></span>
44. <span data-ttu-id="469d5-152">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="469d5-153">Ange "Ct" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="469d5-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-154">Click OK.</span></span>
47. <span data-ttu-id="469d5-155">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="469d5-156">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="469d5-157">Ange "Dimensions" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="469d5-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-158">Click OK.</span></span>
51. <span data-ttu-id="469d5-159">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="469d5-160">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="469d5-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="469d5-161">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="469d5-162">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="469d5-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-163">Click OK.</span></span>
56. <span data-ttu-id="469d5-164">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="469d5-165">Ange "Value" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="469d5-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-166">Click OK.</span></span>
59. <span data-ttu-id="469d5-167">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="469d5-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="469d5-168">Ange "Desc" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="469d5-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="469d5-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="469d5-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="469d5-170">Mappa rapportelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="469d5-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="469d5-171">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="469d5-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="469d5-172">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="469d5-173">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="469d5-174">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="469d5-175">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="469d5-176">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="469d5-177">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="469d5-178">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-178">Click Bind.</span></span>
9. <span data-ttu-id="469d5-179">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="469d5-180">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="469d5-181">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-181">Click Bind.</span></span>
12. <span data-ttu-id="469d5-182">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="469d5-183">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="469d5-184">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-184">Click Bind.</span></span>
15. <span data-ttu-id="469d5-185">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="469d5-186">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="469d5-187">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-187">Click Bind.</span></span>
18. <span data-ttu-id="469d5-188">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="469d5-189">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="469d5-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-190">Click Bind.</span></span>
21. <span data-ttu-id="469d5-191">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="469d5-192">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="469d5-193">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-193">Click Bind.</span></span>
24. <span data-ttu-id="469d5-194">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="469d5-195">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="469d5-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-196">Click Bind.</span></span>
27. <span data-ttu-id="469d5-197">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="469d5-198">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="469d5-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-199">Click Bind.</span></span>
30. <span data-ttu-id="469d5-200">Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="469d5-201">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="469d5-202">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-202">Click Bind.</span></span>
33. <span data-ttu-id="469d5-203">I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="469d5-204">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="469d5-205">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-205">Click Bind.</span></span>
36. <span data-ttu-id="469d5-206">Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="469d5-207">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="469d5-208">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-208">Click Bind.</span></span>
39. <span data-ttu-id="469d5-209">I trädet väljer du "Root: XML Element\Journal: XML Element".</span><span class="sxs-lookup"><span data-stu-id="469d5-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="469d5-210">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="469d5-211">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-211">Click Bind.</span></span>
42. <span data-ttu-id="469d5-212">Välj "Root: XML Element\Company: XML Attribute" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="469d5-213">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="469d5-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="469d5-214">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="469d5-214">Click Bind.</span></span>
45. <span data-ttu-id="469d5-215">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="469d5-215">Click Save.</span></span>
46. <span data-ttu-id="469d5-216">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="469d5-216">Close the page.</span></span>

