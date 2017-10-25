--- 
title: "Konfigurera beräkningar för att utföra inventering och summering för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: f7b9035d8e7baf3c7ecb063b104b9a567be60840
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="configure-computations-to-do-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="fb8cc-103">Konfigurera beräkningar för att utföra inventering och summering för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="fb8cc-103">Configure computations to do counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fb8cc-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="fb8cc-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="fb8cc-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 1: Create format).</span><span class="sxs-lookup"><span data-stu-id="fb8cc-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 1: Create format)” procedure.</span></span>

<span data-ttu-id="fb8cc-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="fb8cc-108">Skapa en formatkonfiguration för att lägga till att informationsinventering och -summering</span><span class="sxs-lookup"><span data-stu-id="fb8cc-108">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="fb8cc-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="fb8cc-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="fb8cc-111">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="fb8cc-112">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-112">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="fb8cc-113">Låt oss anta att du behöver anpassa det format som tillhandahålls av Microsoft genom att lägga till rader med sammanfattningsinformation i slutet av Intrastatrapporten.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-113">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="fb8cc-114">Du gör detta genom att härleda din egen instans av Intrastatkonfigurationen från Microsoft-instansen för att genomföra ändringar.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-114">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="fb8cc-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="fb8cc-116">I fältet New anger du "Derive from Name: Intrastat (DE), Microsoft".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-116">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="fb8cc-117">I namnfältet anger du "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-117">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="fb8cc-118">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-118">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="fb8cc-119">Konfigurera denna rapport att utföra inventering och summering baserat på utleveransinformation</span><span class="sxs-lookup"><span data-stu-id="fb8cc-119">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="fb8cc-120">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-120">Click Designer.</span></span>
2. <span data-ttu-id="fb8cc-121">Välj Yes fältet Collect output details.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-121">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="fb8cc-122">Denna flagga aktiverar (vid körning) den process som samlar in utmatningsinformation för generering av Intrastat-filen.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-122">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="fb8cc-123">Du måste genomföra inventering för olika Instrastat-riktningar. Se därför till att lägga till en särskilt avsedd modelluppräkning i datakällans lista för denna formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-123">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources’ list of this format configuration.</span></span>  
3. <span data-ttu-id="fb8cc-124">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-124">Click the Mapping tab.</span></span>
4. <span data-ttu-id="fb8cc-125">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-125">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="fb8cc-126">Välj "Data model\Enumeration" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-126">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="fb8cc-127">Ange "Direction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-127">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="fb8cc-128">Ange eller välj ett värde i fältet Model enumeration.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-128">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="fb8cc-129">Välj värdet Direction.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-129">Select the value Direction.</span></span>  
8. <span data-ttu-id="fb8cc-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-130">Click OK.</span></span>
9. <span data-ttu-id="fb8cc-131">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-131">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="fb8cc-132">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-132">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="fb8cc-133">Ange "$BlockName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-133">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="fb8cc-134">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-134">Click Edit formula.</span></span>
13. <span data-ttu-id="fb8cc-135">Ange "block" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-135">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="fb8cc-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-136">Click Save.</span></span>
15. <span data-ttu-id="fb8cc-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-137">Close the page.</span></span>
16. <span data-ttu-id="fb8cc-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-138">Click OK.</span></span>
17. <span data-ttu-id="fb8cc-139">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-139">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="fb8cc-140">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-140">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="fb8cc-141">Ange "$RecName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-141">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="fb8cc-142">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-142">Click Edit formula.</span></span>
21. <span data-ttu-id="fb8cc-143">Ange "record" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-143">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="fb8cc-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-144">Click Save.</span></span>
23. <span data-ttu-id="fb8cc-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-145">Close the page.</span></span>
24. <span data-ttu-id="fb8cc-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-146">Click OK.</span></span>
25. <span data-ttu-id="fb8cc-147">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-147">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="fb8cc-148">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-148">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="fb8cc-149">Ange "$InvName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-149">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="fb8cc-150">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-150">Click Edit formula.</span></span>
29. <span data-ttu-id="fb8cc-151">Ange "InvoicedAmountEUR" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-151">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="fb8cc-152">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-152">Click Save.</span></span>
31. <span data-ttu-id="fb8cc-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-153">Close the page.</span></span>
32. <span data-ttu-id="fb8cc-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-154">Click OK.</span></span>
33. <span data-ttu-id="fb8cc-155">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-155">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="fb8cc-156">Klicka på knappen Edit för fältet "Collected data key name"</span><span class="sxs-lookup"><span data-stu-id="fb8cc-156">Click Edit button for the ‘Collected data key name’ field</span></span>
35. <span data-ttu-id="fb8cc-157">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-157">Click Add data source.</span></span>
    * <span data-ttu-id="fb8cc-158">$BlockName</span><span class="sxs-lookup"><span data-stu-id="fb8cc-158">$BlockName</span></span>  
36. <span data-ttu-id="fb8cc-159">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-159">Click Save.</span></span>
37. <span data-ttu-id="fb8cc-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-160">Close the page.</span></span>
38. <span data-ttu-id="fb8cc-161">Klicka på knappen Edit för fältet Collected data key value.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-161">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="fb8cc-162">Ange "IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-162">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="fb8cc-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span><span class="sxs-lookup"><span data-stu-id="fb8cc-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="fb8cc-164">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-164">Click Save.</span></span>
41. <span data-ttu-id="fb8cc-165">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-165">Close the page.</span></span>
    * <span data-ttu-id="fb8cc-166">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-166">Count the lines of this sequence.</span></span> <span data-ttu-id="fb8cc-167">Resultaten kommer att användas med namnet "block" separat för olika riktningar.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-167">The results will be used with the name “block” separately for different directions.</span></span> <span data-ttu-id="fb8cc-168">Värdet ”Import” kommer att användas för eventuella Intrastat-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-168">Value “Import” will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="fb8cc-169">Värdet ”Export” kommer att användas för eventuella Intrastat-transaktioner för utförslar.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-169">The value “Export” will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="fb8cc-170">Betrakta detta som ett virtuellt Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-170">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="fb8cc-171">För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-171">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span>  
42. <span data-ttu-id="fb8cc-172">Expandera "Intrastat\Data: Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-172">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="fb8cc-173">Välj "Intrastat\Data: Sequence\Arrivals?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-173">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="fb8cc-174">Klicka på knappen Edit för fältet "Collected data key name".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-174">Click Edit button for the ‘Collected data key name’ field.</span></span>
    * <span data-ttu-id="fb8cc-175">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-175">Count the lines of this sequence.</span></span> <span data-ttu-id="fb8cc-176">Resultatet kommer att memoreras med hjälp av namnet "record".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-176">The results will be memorized using the name “record”.</span></span>  
45. <span data-ttu-id="fb8cc-177">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-177">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="fb8cc-178">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-178">Click Add data source.</span></span>
47. <span data-ttu-id="fb8cc-179">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-179">Click Save.</span></span>
48. <span data-ttu-id="fb8cc-180">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-180">Close the page.</span></span>
49. <span data-ttu-id="fb8cc-181">Klicka på knappen Edit för fältet Collected data key value".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-181">Click Edit button for the ‘Collected data key value’ field</span></span>
50. <span data-ttu-id="fb8cc-182">Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-182">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="fb8cc-183">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-183">Click Save.</span></span>
52. <span data-ttu-id="fb8cc-184">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-184">Close the page.</span></span>
    * <span data-ttu-id="fb8cc-185">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-185">Count the lines of this sequence.</span></span> <span data-ttu-id="fb8cc-186">Resultaten kommer att användas med namnet "record" separat för olika varukoder.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-186">The results will be used with the name “record” separately for different commodity codes.</span></span> <span data-ttu-id="fb8cc-187">Betrakta detta som ett virtuellt Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-187">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="fb8cc-188">För varje transaktion kommer en rad att fyllas i på följande sätt: Det första kolumn-"blocket" fylls i med värdena ”Import" respektive "Export”, och den andra block-"posten" med varans kodvärde.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-188">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly and the second block “record” is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="fb8cc-189">Välj "Intrastat\Data: Sequence\Dispatches?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-189">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="fb8cc-190">Klicka på knappen Edit för fältet "Collected data key name"</span><span class="sxs-lookup"><span data-stu-id="fb8cc-190">Click Edit button for the ‘Collected data key name’ field</span></span>
55. <span data-ttu-id="fb8cc-191">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-191">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="fb8cc-192">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-192">Click Add data source.</span></span>
57. <span data-ttu-id="fb8cc-193">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-193">Click Save.</span></span>
58. <span data-ttu-id="fb8cc-194">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-194">Close the page.</span></span>
59. <span data-ttu-id="fb8cc-195">Klicka på knappen Edit för fältet "Collected data key value".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-195">Click the Edit button for the ‘Collected data key value’ field.</span></span>
60. <span data-ttu-id="fb8cc-196">Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-196">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="fb8cc-197">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-197">Click Save.</span></span>
62. <span data-ttu-id="fb8cc-198">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-198">Close the page.</span></span>
63. <span data-ttu-id="fb8cc-199">Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-199">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="fb8cc-200">Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="fb8cc-201">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-201">Click the Format tab.</span></span>
66. <span data-ttu-id="fb8cc-202">Välj "Intrastat\Data\Dispatches\Record\Invoice amount EUR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-202">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="fb8cc-203">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-203">Click the Mapping tab.</span></span>
68. <span data-ttu-id="fb8cc-204">Klicka på knappen Edit för fältet "Collected data key name".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-204">Click the Edit button for the ‘Collected data key name’ field.</span></span>
69. <span data-ttu-id="fb8cc-205">Välj "$InvName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-205">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="fb8cc-206">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-206">Click Add data source.</span></span>
71. <span data-ttu-id="fb8cc-207">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-207">Click Save.</span></span>
72. <span data-ttu-id="fb8cc-208">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-208">Close the page.</span></span>
    * <span data-ttu-id="fb8cc-209">Sammanfatta de fakturerade beloppvärdena för rader i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-209">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="fb8cc-210">Resultaten kommer att användas med namnet "InvoicedAmountEUR" separat för olika Intrastat-riktningar och varukoder.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-210">The results will be used with the name “InvoicedAmountEUR” separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="fb8cc-211">Betrakta detta som en virtuell skapelse i ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-211">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="fb8cc-212">För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-212">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span> <span data-ttu-id="fb8cc-213">Det andra blocket ”record” fylls i med varans kodvärde, och den tredje kolumnen " InvoicedAmountEUR ”fylls i med fakturabeloppets värde.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-213">The second block “record” is filled with the commodity code value, and the third column “InvoicedAmountEUR” is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="fb8cc-214">Expandera "Intrastat\Data\Arrivals?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-214">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="fb8cc-215">Expandera "Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-215">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="fb8cc-216">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-216">Click the Format tab.</span></span>
76. <span data-ttu-id="fb8cc-217">Välj "Intrastat\Data\Arrivals\Record\Invoice amount EUR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-217">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="fb8cc-218">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-218">Click the Mapping tab.</span></span>
78. <span data-ttu-id="fb8cc-219">Klicka på knappen Edit för fältet "Collected data key name".</span><span class="sxs-lookup"><span data-stu-id="fb8cc-219">Click the Edit button for the ‘Collected data key name’ field.</span></span>
79. <span data-ttu-id="fb8cc-220">Välj "$InvName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-220">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="fb8cc-221">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-221">Click Add data source.</span></span>
81. <span data-ttu-id="fb8cc-222">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-222">Click Save.</span></span>
82. <span data-ttu-id="fb8cc-223">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-223">Close the page.</span></span>
83. <span data-ttu-id="fb8cc-224">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-224">Click Save.</span></span>
84. <span data-ttu-id="fb8cc-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb8cc-225">Close the page.</span></span>

