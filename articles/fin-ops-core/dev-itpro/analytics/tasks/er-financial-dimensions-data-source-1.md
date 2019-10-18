---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 1 - Designa datamodell)
description: I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca295d651838f34106c9b91a53efc1f4faad4e4a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182495"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="a92ba-103">ER Använd ekonomiska dimensioner som en datakälla (Del 1: Designa datamodell)</span><span class="sxs-lookup"><span data-stu-id="a92ba-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a92ba-104">I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="a92ba-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="a92ba-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="a92ba-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="a92ba-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="a92ba-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="a92ba-107">Skapa en ny datamodell</span><span class="sxs-lookup"><span data-stu-id="a92ba-107">Create a new data model</span></span>
1. <span data-ttu-id="a92ba-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a92ba-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a92ba-109">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="a92ba-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="a92ba-110">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="a92ba-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="a92ba-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="a92ba-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="a92ba-112">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="a92ba-113">Ange "Financial dimensions sample model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="a92ba-114">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a92ba-114">Click Create configuration.</span></span>
6. <span data-ttu-id="a92ba-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a92ba-115">Click Designer.</span></span>
7. <span data-ttu-id="a92ba-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="a92ba-117">Ange "Entry" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="a92ba-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-118">Click Add.</span></span>
10. <span data-ttu-id="a92ba-119">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="a92ba-120">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a92ba-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="a92ba-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-121">Click Add.</span></span>
    * <span data-ttu-id="a92ba-122">Vi ska lägga till en ny postlista till vår modell.</span><span class="sxs-lookup"><span data-stu-id="a92ba-122">We will add to our model a new record list.</span></span> <span data-ttu-id="a92ba-123">Den här listan kommer att visa inställningarna för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="a92ba-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="a92ba-124">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens inställning.</span><span class="sxs-lookup"><span data-stu-id="a92ba-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="a92ba-125">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="a92ba-126">Ange "Dimensions setting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="a92ba-127">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="a92ba-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-128">Click Add.</span></span>
17. <span data-ttu-id="a92ba-129">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="a92ba-130">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="a92ba-131">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="a92ba-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-132">Click Add.</span></span>
21. <span data-ttu-id="a92ba-133">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="a92ba-134">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a92ba-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="a92ba-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-135">Click Add.</span></span>
24. <span data-ttu-id="a92ba-136">Välj "Entry" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="a92ba-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="a92ba-138">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="a92ba-139">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="a92ba-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-140">Click Add.</span></span>
29. <span data-ttu-id="a92ba-141">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="a92ba-142">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="a92ba-143">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="a92ba-144">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-144">Click Add.</span></span>
33. <span data-ttu-id="a92ba-145">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="a92ba-146">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="a92ba-147">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="a92ba-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-148">Click Add.</span></span>
37. <span data-ttu-id="a92ba-149">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="a92ba-150">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="a92ba-151">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="a92ba-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-152">Click Add.</span></span>
41. <span data-ttu-id="a92ba-153">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="a92ba-154">Ange "Debit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="a92ba-155">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="a92ba-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-156">Click Add.</span></span>
45. <span data-ttu-id="a92ba-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="a92ba-158">Ange "Credit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="a92ba-159">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-159">Click Add.</span></span>
48. <span data-ttu-id="a92ba-160">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="a92ba-161">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a92ba-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="a92ba-162">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="a92ba-163">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-163">Click Add.</span></span>
52. <span data-ttu-id="a92ba-164">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="a92ba-165">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="a92ba-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-166">Click Add.</span></span>
55. <span data-ttu-id="a92ba-167">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="a92ba-168">Ange "Dimensions data" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="a92ba-169">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="a92ba-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-170">Click Add.</span></span>
    * <span data-ttu-id="a92ba-171">Vi har lagt till en ny postlisa i vår modell.</span><span class="sxs-lookup"><span data-stu-id="a92ba-171">We added to our model a new record list.</span></span> <span data-ttu-id="a92ba-172">Den här listan kommer att visa värdena för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="a92ba-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="a92ba-173">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens värden.</span><span class="sxs-lookup"><span data-stu-id="a92ba-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="a92ba-174">Dimensionsnamn visas även i denna post som ett fält som vid behov ska användas för urval.</span><span class="sxs-lookup"><span data-stu-id="a92ba-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="a92ba-175">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="a92ba-176">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a92ba-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="a92ba-177">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="a92ba-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="a92ba-178">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-178">Click Add.</span></span>
63. <span data-ttu-id="a92ba-179">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="a92ba-180">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a92ba-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="a92ba-181">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-181">Click Add.</span></span>
66. <span data-ttu-id="a92ba-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="a92ba-183">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a92ba-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="a92ba-184">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a92ba-184">Click Add.</span></span>
69. <span data-ttu-id="a92ba-185">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a92ba-185">Click Save.</span></span>
70. <span data-ttu-id="a92ba-186">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a92ba-186">Close the page.</span></span>

