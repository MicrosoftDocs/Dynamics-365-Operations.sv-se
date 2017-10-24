--- 
title: "Utforma en datamodell som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d8a03c4b85666975a7b42d46f3afdd35019e9b93
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="960ac-103">Utforma en datamodell som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="960ac-103">Design data model to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="960ac-104">I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="960ac-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="960ac-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="960ac-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="960ac-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="960ac-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="960ac-107">Skapa en ny datamodell</span><span class="sxs-lookup"><span data-stu-id="960ac-107">Create a new data model</span></span>
1. <span data-ttu-id="960ac-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="960ac-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="960ac-109">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="960ac-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="960ac-110">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="960ac-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="960ac-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="960ac-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="960ac-112">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="960ac-113">Ange "Financial dimensions sample model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="960ac-114">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="960ac-114">Click Create configuration.</span></span>
6. <span data-ttu-id="960ac-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="960ac-115">Click Designer.</span></span>
7. <span data-ttu-id="960ac-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="960ac-117">Ange "Entry" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="960ac-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-118">Click Add.</span></span>
10. <span data-ttu-id="960ac-119">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="960ac-120">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="960ac-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="960ac-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-121">Click Add.</span></span>
    * <span data-ttu-id="960ac-122">Vi ska lägga till en ny postlista till vår modell.</span><span class="sxs-lookup"><span data-stu-id="960ac-122">We will add to our model a new record list.</span></span> <span data-ttu-id="960ac-123">Den här listan kommer att visa inställningarna för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="960ac-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="960ac-124">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens inställning.</span><span class="sxs-lookup"><span data-stu-id="960ac-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="960ac-125">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="960ac-126">Ange "Dimensions setting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="960ac-127">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="960ac-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-128">Click Add.</span></span>
17. <span data-ttu-id="960ac-129">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="960ac-130">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="960ac-131">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="960ac-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-132">Click Add.</span></span>
21. <span data-ttu-id="960ac-133">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="960ac-134">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="960ac-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="960ac-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-135">Click Add.</span></span>
24. <span data-ttu-id="960ac-136">Välj "Entry" i trädet.</span><span class="sxs-lookup"><span data-stu-id="960ac-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="960ac-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="960ac-138">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="960ac-139">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="960ac-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-140">Click Add.</span></span>
29. <span data-ttu-id="960ac-141">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="960ac-142">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="960ac-143">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="960ac-144">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-144">Click Add.</span></span>
33. <span data-ttu-id="960ac-145">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="960ac-146">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="960ac-147">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="960ac-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-148">Click Add.</span></span>
37. <span data-ttu-id="960ac-149">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="960ac-150">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="960ac-151">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="960ac-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-152">Click Add.</span></span>
41. <span data-ttu-id="960ac-153">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="960ac-154">Ange "Debit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="960ac-155">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="960ac-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-156">Click Add.</span></span>
45. <span data-ttu-id="960ac-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="960ac-158">Ange "Credit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="960ac-159">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-159">Click Add.</span></span>
48. <span data-ttu-id="960ac-160">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="960ac-161">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="960ac-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="960ac-162">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="960ac-163">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-163">Click Add.</span></span>
52. <span data-ttu-id="960ac-164">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="960ac-165">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="960ac-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-166">Click Add.</span></span>
55. <span data-ttu-id="960ac-167">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="960ac-168">Ange "Dimensions data" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="960ac-169">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="960ac-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-170">Click Add.</span></span>
    * <span data-ttu-id="960ac-171">Vi har lagt till en ny postlisa i vår modell.</span><span class="sxs-lookup"><span data-stu-id="960ac-171">We added to our model a new record list.</span></span> <span data-ttu-id="960ac-172">Den här listan kommer att visa värdena för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="960ac-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="960ac-173">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens värden.</span><span class="sxs-lookup"><span data-stu-id="960ac-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="960ac-174">Dimensionsnamn visas även i denna post som ett fält som vid behov ska användas för urval.</span><span class="sxs-lookup"><span data-stu-id="960ac-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="960ac-175">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="960ac-176">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="960ac-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="960ac-177">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="960ac-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="960ac-178">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-178">Click Add.</span></span>
63. <span data-ttu-id="960ac-179">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="960ac-180">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="960ac-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="960ac-181">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-181">Click Add.</span></span>
66. <span data-ttu-id="960ac-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="960ac-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="960ac-183">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="960ac-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="960ac-184">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="960ac-184">Click Add.</span></span>
69. <span data-ttu-id="960ac-185">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="960ac-185">Click Save.</span></span>
70. <span data-ttu-id="960ac-186">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="960ac-186">Close the page.</span></span>


