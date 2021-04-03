---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 1 - Designa datamodell)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 1)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5ecae444d80698c03ac050b49894daa1b090f74
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570202"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="f717b-104">ER Använd ekonomiska dimensioner som en datakälla (Del 1 - Designa datamodell)</span><span class="sxs-lookup"><span data-stu-id="f717b-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f717b-105">I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="f717b-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="f717b-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="f717b-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="f717b-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="f717b-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="f717b-108">Skapa en ny datamodell</span><span class="sxs-lookup"><span data-stu-id="f717b-108">Create a new data model</span></span>
1. <span data-ttu-id="f717b-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f717b-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f717b-110">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="f717b-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="f717b-111">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="f717b-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="f717b-112">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="f717b-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f717b-113">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="f717b-114">Ange "Financial dimensions sample model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="f717b-115">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f717b-115">Click Create configuration.</span></span>
6. <span data-ttu-id="f717b-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f717b-116">Click Designer.</span></span>
7. <span data-ttu-id="f717b-117">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="f717b-118">Ange "Entry" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="f717b-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-119">Click Add.</span></span>
10. <span data-ttu-id="f717b-120">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="f717b-121">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f717b-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="f717b-122">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-122">Click Add.</span></span>
    * <span data-ttu-id="f717b-123">Vi ska lägga till en ny postlista till vår modell.</span><span class="sxs-lookup"><span data-stu-id="f717b-123">We will add to our model a new record list.</span></span> <span data-ttu-id="f717b-124">Den här listan kommer att visa inställningarna för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="f717b-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="f717b-125">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens inställning.</span><span class="sxs-lookup"><span data-stu-id="f717b-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="f717b-126">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="f717b-127">Ange "Dimensions setting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="f717b-128">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="f717b-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-129">Click Add.</span></span>
17. <span data-ttu-id="f717b-130">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="f717b-131">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="f717b-132">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="f717b-133">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-133">Click Add.</span></span>
21. <span data-ttu-id="f717b-134">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="f717b-135">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f717b-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="f717b-136">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-136">Click Add.</span></span>
24. <span data-ttu-id="f717b-137">Välj "Entry" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f717b-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="f717b-138">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="f717b-139">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="f717b-140">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="f717b-141">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-141">Click Add.</span></span>
29. <span data-ttu-id="f717b-142">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="f717b-143">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="f717b-144">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="f717b-145">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-145">Click Add.</span></span>
33. <span data-ttu-id="f717b-146">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="f717b-147">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="f717b-148">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="f717b-149">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-149">Click Add.</span></span>
37. <span data-ttu-id="f717b-150">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="f717b-151">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="f717b-152">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="f717b-153">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-153">Click Add.</span></span>
41. <span data-ttu-id="f717b-154">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="f717b-155">Ange "Debit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="f717b-156">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="f717b-157">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-157">Click Add.</span></span>
45. <span data-ttu-id="f717b-158">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="f717b-159">Ange "Credit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="f717b-160">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-160">Click Add.</span></span>
48. <span data-ttu-id="f717b-161">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="f717b-162">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f717b-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="f717b-163">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="f717b-164">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-164">Click Add.</span></span>
52. <span data-ttu-id="f717b-165">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="f717b-166">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="f717b-167">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-167">Click Add.</span></span>
55. <span data-ttu-id="f717b-168">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="f717b-169">Ange "Dimensions data" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="f717b-170">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="f717b-171">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-171">Click Add.</span></span>
    * <span data-ttu-id="f717b-172">Vi har lagt till en ny postlisa i vår modell.</span><span class="sxs-lookup"><span data-stu-id="f717b-172">We added to our model a new record list.</span></span> <span data-ttu-id="f717b-173">Den här listan kommer att visa värdena för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="f717b-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="f717b-174">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens värden.</span><span class="sxs-lookup"><span data-stu-id="f717b-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="f717b-175">Dimensionsnamn visas även i denna post som ett fält som vid behov ska användas för urval.</span><span class="sxs-lookup"><span data-stu-id="f717b-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="f717b-176">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="f717b-177">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f717b-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="f717b-178">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f717b-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="f717b-179">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-179">Click Add.</span></span>
63. <span data-ttu-id="f717b-180">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="f717b-181">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f717b-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="f717b-182">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-182">Click Add.</span></span>
66. <span data-ttu-id="f717b-183">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f717b-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="f717b-184">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f717b-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="f717b-185">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f717b-185">Click Add.</span></span>
69. <span data-ttu-id="f717b-186">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f717b-186">Click Save.</span></span>
70. <span data-ttu-id="f717b-187">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f717b-187">Close the page.</span></span>

![Sidan ER-datamodelldesigner](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]