--- 
title: "Utforma datamodeller som använder ekonomiska dimensioner som datakällor"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 9b33d78b60ca4e4813dd4b158febee2323cea476
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="design-data-models-to-use-financial-dimensions-as-data-sources"></a><span data-ttu-id="75acf-103">Utforma datamodeller som använder ekonomiska dimensioner som datakällor</span><span class="sxs-lookup"><span data-stu-id="75acf-103">Design data models to use financial dimensions as data sources</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75acf-104">I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="75acf-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="75acf-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="75acf-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="75acf-106">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.</span><span class="sxs-lookup"><span data-stu-id="75acf-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="75acf-107">Skapa en ny datamodell</span><span class="sxs-lookup"><span data-stu-id="75acf-107">Create a new data model</span></span>
1. <span data-ttu-id="75acf-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="75acf-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="75acf-109">Kontrollera att ”Litware Inc."-leverantören</span><span class="sxs-lookup"><span data-stu-id="75acf-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="75acf-110">är tillgänglig och markerats som aktiv.</span><span class="sxs-lookup"><span data-stu-id="75acf-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="75acf-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="75acf-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="75acf-112">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="75acf-113">Ange "Financial dimensions sample model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="75acf-114">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="75acf-114">Click Create configuration.</span></span>
6. <span data-ttu-id="75acf-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="75acf-115">Click Designer.</span></span>
7. <span data-ttu-id="75acf-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="75acf-117">Ange "Entry" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="75acf-118">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-118">Click Add.</span></span>
10. <span data-ttu-id="75acf-119">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="75acf-120">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="75acf-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="75acf-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-121">Click Add.</span></span>
    * <span data-ttu-id="75acf-122">Vi ska lägga till en ny postlista till vår modell.</span><span class="sxs-lookup"><span data-stu-id="75acf-122">We will add to our model a new record list.</span></span> <span data-ttu-id="75acf-123">Den här listan kommer att visa inställningarna för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="75acf-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="75acf-124">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens inställning.</span><span class="sxs-lookup"><span data-stu-id="75acf-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="75acf-125">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="75acf-126">Ange "Dimensions setting" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="75acf-127">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="75acf-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-128">Click Add.</span></span>
17. <span data-ttu-id="75acf-129">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="75acf-130">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="75acf-131">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="75acf-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-132">Click Add.</span></span>
21. <span data-ttu-id="75acf-133">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="75acf-134">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="75acf-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="75acf-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-135">Click Add.</span></span>
24. <span data-ttu-id="75acf-136">Välj "Entry" i trädet.</span><span class="sxs-lookup"><span data-stu-id="75acf-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="75acf-137">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="75acf-138">Ange "Journal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="75acf-139">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="75acf-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-140">Click Add.</span></span>
29. <span data-ttu-id="75acf-141">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="75acf-142">Ange "Batch" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="75acf-143">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="75acf-144">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-144">Click Add.</span></span>
33. <span data-ttu-id="75acf-145">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="75acf-146">Ange "Transaction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="75acf-147">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="75acf-148">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-148">Click Add.</span></span>
37. <span data-ttu-id="75acf-149">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="75acf-150">Ange "Date" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="75acf-151">Välj "Datum" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="75acf-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-152">Click Add.</span></span>
41. <span data-ttu-id="75acf-153">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="75acf-154">Ange "Debit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="75acf-155">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="75acf-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-156">Click Add.</span></span>
45. <span data-ttu-id="75acf-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="75acf-158">Ange "Credit" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="75acf-159">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-159">Click Add.</span></span>
48. <span data-ttu-id="75acf-160">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="75acf-161">Skriv "Valuta" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="75acf-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="75acf-162">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="75acf-163">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-163">Click Add.</span></span>
52. <span data-ttu-id="75acf-164">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="75acf-165">Ange "Voucher" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="75acf-166">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-166">Click Add.</span></span>
55. <span data-ttu-id="75acf-167">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="75acf-168">Ange "Dimensions data" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="75acf-169">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="75acf-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-170">Click Add.</span></span>
    * <span data-ttu-id="75acf-171">Vi har lagt till en ny postlisa i vår modell.</span><span class="sxs-lookup"><span data-stu-id="75acf-171">We added to our model a new record list.</span></span> <span data-ttu-id="75acf-172">Den här listan kommer att visa värdena för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla).</span><span class="sxs-lookup"><span data-stu-id="75acf-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="75acf-173">Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens värden.</span><span class="sxs-lookup"><span data-stu-id="75acf-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="75acf-174">Dimensionsnamn visas även i denna post som ett fält som vid behov ska användas för urval.</span><span class="sxs-lookup"><span data-stu-id="75acf-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="75acf-175">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="75acf-176">Ange "Code" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="75acf-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="75acf-177">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="75acf-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="75acf-178">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-178">Click Add.</span></span>
63. <span data-ttu-id="75acf-179">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="75acf-180">Skriv "Beskrivning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="75acf-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="75acf-181">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-181">Click Add.</span></span>
66. <span data-ttu-id="75acf-182">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="75acf-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="75acf-183">Skriv "Namn" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="75acf-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="75acf-184">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="75acf-184">Click Add.</span></span>
69. <span data-ttu-id="75acf-185">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="75acf-185">Click Save.</span></span>
70. <span data-ttu-id="75acf-186">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="75acf-186">Close the page.</span></span>


