---
title: ER Konfigurera format för att utföra inventering och summering (Del 2 - Konfigurera beräkningar)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6215fe1f32bcb4833bd009b7c33e09edbba17817
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093007"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a><span data-ttu-id="f7aef-104">ER Konfigurera format för att utföra inventering och summering (Del 2 - Konfigurera beräkningar)</span><span class="sxs-lookup"><span data-stu-id="f7aef-104">ER Configure format to do counting and summing (Part 2 - Configure computations)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7aef-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning.</span><span class="sxs-lookup"><span data-stu-id="f7aef-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="f7aef-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="f7aef-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="f7aef-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 1: Create format).</span><span class="sxs-lookup"><span data-stu-id="f7aef-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 1: Create format)" procedure.</span></span>

<span data-ttu-id="f7aef-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="f7aef-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="f7aef-109">Skapa en formatkonfiguration för att lägga till att informationsinventering och -summering</span><span class="sxs-lookup"><span data-stu-id="f7aef-109">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="f7aef-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f7aef-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f7aef-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="f7aef-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f7aef-112">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="f7aef-113">Välj "Intrastat modell\Intrastat (DE)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-113">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="f7aef-114">Låt oss anta att du behöver anpassa det format som tillhandahålls av Microsoft genom att lägga till rader med sammanfattningsinformation i slutet av Intrastatrapporten.</span><span class="sxs-lookup"><span data-stu-id="f7aef-114">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="f7aef-115">Du gör detta genom att härleda din egen instans av Intrastatkonfigurationen från Microsoft-instansen för att genomföra ändringar.</span><span class="sxs-lookup"><span data-stu-id="f7aef-115">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="f7aef-116">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-116">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="f7aef-117">I fältet New anger du "Derive from Name: Intrastat (DE), Microsoft".</span><span class="sxs-lookup"><span data-stu-id="f7aef-117">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="f7aef-118">I namnfältet anger du "Intrastat (DE) with counting & summing".</span><span class="sxs-lookup"><span data-stu-id="f7aef-118">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="f7aef-119">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f7aef-119">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="f7aef-120">Konfigurera denna rapport att utföra inventering och summering baserat på utleveransinformation</span><span class="sxs-lookup"><span data-stu-id="f7aef-120">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="f7aef-121">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f7aef-121">Click Designer.</span></span>
2. <span data-ttu-id="f7aef-122">Välj Yes fältet Collect output details.</span><span class="sxs-lookup"><span data-stu-id="f7aef-122">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="f7aef-123">Denna flagga aktiverar (vid körning) den process som samlar in utmatningsinformation för generering av Intrastat-filen.</span><span class="sxs-lookup"><span data-stu-id="f7aef-123">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="f7aef-124">Du måste genomföra inventering för olika Instrastat-riktningar. Se därför till att lägga till en särskilt avsedd modelluppräkning i datakällans lista för denna formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f7aef-124">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources' list of this format configuration.</span></span>  
3. <span data-ttu-id="f7aef-125">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="f7aef-125">Click the Mapping tab.</span></span>
4. <span data-ttu-id="f7aef-126">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-126">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="f7aef-127">Välj "Data model\Enumeration" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-127">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="f7aef-128">Ange "Direction" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-128">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="f7aef-129">Ange eller välj ett värde i fältet Model enumeration.</span><span class="sxs-lookup"><span data-stu-id="f7aef-129">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="f7aef-130">Välj värdet Direction.</span><span class="sxs-lookup"><span data-stu-id="f7aef-130">Select the value Direction.</span></span>  
8. <span data-ttu-id="f7aef-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7aef-131">Click OK.</span></span>
9. <span data-ttu-id="f7aef-132">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-132">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="f7aef-133">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-133">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="f7aef-134">Ange "$BlockName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-134">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="f7aef-135">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="f7aef-135">Click Edit formula.</span></span>
13. <span data-ttu-id="f7aef-136">Ange "block" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-136">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="f7aef-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-137">Click Save.</span></span>
15. <span data-ttu-id="f7aef-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-138">Close the page.</span></span>
16. <span data-ttu-id="f7aef-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7aef-139">Click OK.</span></span>
17. <span data-ttu-id="f7aef-140">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-140">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="f7aef-141">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-141">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="f7aef-142">Ange "$RecName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-142">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="f7aef-143">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="f7aef-143">Click Edit formula.</span></span>
21. <span data-ttu-id="f7aef-144">Ange "record" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-144">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="f7aef-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-145">Click Save.</span></span>
23. <span data-ttu-id="f7aef-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-146">Close the page.</span></span>
24. <span data-ttu-id="f7aef-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7aef-147">Click OK.</span></span>
25. <span data-ttu-id="f7aef-148">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-148">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="f7aef-149">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-149">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="f7aef-150">Ange "$InvName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-150">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="f7aef-151">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="f7aef-151">Click Edit formula.</span></span>
29. <span data-ttu-id="f7aef-152">Ange "InvoicedAmountEUR" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-152">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="f7aef-153">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-153">Click Save.</span></span>
31. <span data-ttu-id="f7aef-154">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-154">Close the page.</span></span>
32. <span data-ttu-id="f7aef-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f7aef-155">Click OK.</span></span>
33. <span data-ttu-id="f7aef-156">Välj "Intrastat\Data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-156">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="f7aef-157">Klicka på knappen Edit för fältet "Collected data key name"</span><span class="sxs-lookup"><span data-stu-id="f7aef-157">Click Edit button for the 'Collected data key name' field</span></span>
35. <span data-ttu-id="f7aef-158">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f7aef-158">Click Add data source.</span></span>
    * <span data-ttu-id="f7aef-159">$BlockName</span><span class="sxs-lookup"><span data-stu-id="f7aef-159">$BlockName</span></span>  
36. <span data-ttu-id="f7aef-160">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-160">Click Save.</span></span>
37. <span data-ttu-id="f7aef-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-161">Close the page.</span></span>
38. <span data-ttu-id="f7aef-162">Klicka på knappen Edit för fältet Collected data key value.</span><span class="sxs-lookup"><span data-stu-id="f7aef-162">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="f7aef-163">Ange "IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-163">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="f7aef-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span><span class="sxs-lookup"><span data-stu-id="f7aef-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="f7aef-165">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-165">Click Save.</span></span>
41. <span data-ttu-id="f7aef-166">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-166">Close the page.</span></span>
    * <span data-ttu-id="f7aef-167">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="f7aef-167">Count the lines of this sequence.</span></span> <span data-ttu-id="f7aef-168">Resultaten kommer att användas med namnet "block" separat för olika riktningar.</span><span class="sxs-lookup"><span data-stu-id="f7aef-168">The results will be used with the name "block" separately for different directions.</span></span> <span data-ttu-id="f7aef-169">Värdet ”Import” kommer att användas för eventuella Intrastat-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="f7aef-169">Value "Import" will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="f7aef-170">Värdet ”Export” kommer att användas för eventuella Intrastat-transaktioner för utförslar.</span><span class="sxs-lookup"><span data-stu-id="f7aef-170">The value "Export" will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="f7aef-171">Betrakta detta som ett virtuellt Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f7aef-171">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="f7aef-172">För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”.</span><span class="sxs-lookup"><span data-stu-id="f7aef-172">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span>  
42. <span data-ttu-id="f7aef-173">Expandera "Intrastat\Data: Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-173">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="f7aef-174">Välj "Intrastat\Data: Sequence\Arrivals?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-174">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="f7aef-175">Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".</span><span class="sxs-lookup"><span data-stu-id="f7aef-175">Click Edit button for the 'Collected data key name' field.</span></span>
    * <span data-ttu-id="f7aef-176">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="f7aef-176">Count the lines of this sequence.</span></span> <span data-ttu-id="f7aef-177">Klicka på knappen Edit för fältet "Insamlat datanyckelvärde".</span><span class="sxs-lookup"><span data-stu-id="f7aef-177">The results will be memorized using the name "record".</span></span>  
45. <span data-ttu-id="f7aef-178">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-178">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="f7aef-179">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f7aef-179">Click Add data source.</span></span>
47. <span data-ttu-id="f7aef-180">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-180">Click Save.</span></span>
48. <span data-ttu-id="f7aef-181">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-181">Close the page.</span></span>
49. <span data-ttu-id="f7aef-182">Klicka på knappen Redigera för fältet Insamlat datanyckelvärde.</span><span class="sxs-lookup"><span data-stu-id="f7aef-182">Click Edit button for the 'Collected data key value' field</span></span>
50. <span data-ttu-id="f7aef-183">Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-183">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="f7aef-184">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-184">Click Save.</span></span>
52. <span data-ttu-id="f7aef-185">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-185">Close the page.</span></span>
    * <span data-ttu-id="f7aef-186">Räkna raderna i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="f7aef-186">Count the lines of this sequence.</span></span> <span data-ttu-id="f7aef-187">Resultaten kommer att användas med namnet "post" separat för olika varukoder.</span><span class="sxs-lookup"><span data-stu-id="f7aef-187">The results will be used with the name "record" separately for different commodity codes.</span></span> <span data-ttu-id="f7aef-188">Betrakta detta som ett virtuellt Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f7aef-188">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="f7aef-189">För varje transaktion kommer en rad att fyllas i på följande sätt: Det första kolumn-"blocket" fylls i med värdena ”Import" respektive "Export”, och den andra block-"posten" med varans kodvärde.</span><span class="sxs-lookup"><span data-stu-id="f7aef-189">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly and the second block "record" is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="f7aef-190">Välj "Intrastat\Data: Sequence\Dispatches?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-190">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="f7aef-191">Klicka på knappen Edit för fältet "Collected data key name"</span><span class="sxs-lookup"><span data-stu-id="f7aef-191">Click Edit button for the 'Collected data key name' field</span></span>
55. <span data-ttu-id="f7aef-192">Välj "$RecName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-192">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="f7aef-193">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f7aef-193">Click Add data source.</span></span>
57. <span data-ttu-id="f7aef-194">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-194">Click Save.</span></span>
58. <span data-ttu-id="f7aef-195">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-195">Close the page.</span></span>
59. <span data-ttu-id="f7aef-196">Klicka på knappen Edit för fältet "Insamlat datanyckelvärde".</span><span class="sxs-lookup"><span data-stu-id="f7aef-196">Click the Edit button for the 'Collected data key value' field.</span></span>
60. <span data-ttu-id="f7aef-197">Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-197">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="f7aef-198">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-198">Click Save.</span></span>
62. <span data-ttu-id="f7aef-199">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-199">Close the page.</span></span>
63. <span data-ttu-id="f7aef-200">Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="f7aef-201">Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-201">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="f7aef-202">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="f7aef-202">Click the Format tab.</span></span>
66. <span data-ttu-id="f7aef-203">Välj "Intrastat\Data\Dispatches\Record\Invoice amount EUR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-203">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="f7aef-204">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="f7aef-204">Click the Mapping tab.</span></span>
68. <span data-ttu-id="f7aef-205">Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".</span><span class="sxs-lookup"><span data-stu-id="f7aef-205">Click the Edit button for the 'Collected data key name' field.</span></span>
69. <span data-ttu-id="f7aef-206">Välj "$InvName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-206">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="f7aef-207">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f7aef-207">Click Add data source.</span></span>
71. <span data-ttu-id="f7aef-208">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-208">Click Save.</span></span>
72. <span data-ttu-id="f7aef-209">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-209">Close the page.</span></span>
    * <span data-ttu-id="f7aef-210">Sammanfatta de fakturerade beloppvärdena för rader i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="f7aef-210">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="f7aef-211">Resultaten kommer att användas med namnet "InvoicedAmountEUR" separat för olika Intrastat-riktningar och varukoder.</span><span class="sxs-lookup"><span data-stu-id="f7aef-211">The results will be used with the name "InvoicedAmountEUR" separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="f7aef-212">Betrakta detta som en virtuell skapelse i ett Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f7aef-212">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="f7aef-213">För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”.</span><span class="sxs-lookup"><span data-stu-id="f7aef-213">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span> <span data-ttu-id="f7aef-214">Det andra blocket ”post” fylls i med varans kodvärde, och den tredje kolumnen "InvoicedAmountEUR" fylls i med fakturabeloppets värde.</span><span class="sxs-lookup"><span data-stu-id="f7aef-214">The second block "record" is filled with the commodity code value, and the third column "InvoicedAmountEUR" is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="f7aef-215">Expandera "Intrastat\Data\Arrivals?" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-215">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="f7aef-216">Expandera "Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-216">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="f7aef-217">Klicka på fliken Format.</span><span class="sxs-lookup"><span data-stu-id="f7aef-217">Click the Format tab.</span></span>
76. <span data-ttu-id="f7aef-218">Välj "Intrastat\Data\Arrivals\Record\Invoice amount EUR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-218">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="f7aef-219">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="f7aef-219">Click the Mapping tab.</span></span>
78. <span data-ttu-id="f7aef-220">Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".</span><span class="sxs-lookup"><span data-stu-id="f7aef-220">Click the Edit button for the 'Collected data key name' field.</span></span>
79. <span data-ttu-id="f7aef-221">Välj "$InvName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f7aef-221">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="f7aef-222">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f7aef-222">Click Add data source.</span></span>
81. <span data-ttu-id="f7aef-223">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-223">Click Save.</span></span>
82. <span data-ttu-id="f7aef-224">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-224">Close the page.</span></span>
83. <span data-ttu-id="f7aef-225">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f7aef-225">Click Save.</span></span>
84. <span data-ttu-id="f7aef-226">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f7aef-226">Close the page.</span></span>

