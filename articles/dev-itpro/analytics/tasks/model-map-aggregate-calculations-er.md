--- 
title: "Använd en konfiguration för modellmappning för att aggregera beräkningar på databasnivå (ER)"
description: "Denna procedur ger information för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4b6533d1ba538bdc115a865f94212b84781e506e
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="use-a-model-mapping-configuration-for-aggregate-calculations-at-the-database-leveler"></a><span data-ttu-id="10df3-103">Använd en konfiguration för modellmappning för att aggregera beräkningar på databasnivå (ER)</span><span class="sxs-lookup"><span data-stu-id="10df3-103">Use a model mapping configuration for aggregate calculations at the database level(ER)</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10df3-104">Denna procedur ger information för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.</span><span class="sxs-lookup"><span data-stu-id="10df3-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="10df3-105">I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="10df3-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="10df3-106">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="10df3-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="10df3-107">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="10df3-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="10df3-108">För att slutföra stegen måste du först slutföra stegen i proceduren ”ER förbättrar effektiviteten av aggregerade beräkningar genom att utföra dem på databasnivå (del 1: förbereda konfigurationer)”.</span><span class="sxs-lookup"><span data-stu-id="10df3-108">To complete these steps, you must first complete the steps in the procedure, “ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations).”</span></span>

1. <span data-ttu-id="10df3-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="10df3-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="10df3-110">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="10df3-111">Välj "Intrastat model\Intrastat sample mapping" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="10df3-112">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="10df3-112">Click Designer.</span></span>
5. <span data-ttu-id="10df3-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="10df3-113">Click Designer.</span></span>
6. <span data-ttu-id="10df3-114">Välj Dynamics 365 for Dynamics 365 for Operations\Table records i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="10df3-115">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="10df3-115">Click Add root.</span></span>
    * <span data-ttu-id="10df3-116">Lägg till en ny datakälla som representerar poster som du vill gruppera.</span><span class="sxs-lookup"><span data-stu-id="10df3-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="10df3-117">Skriv "Transaktioner" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="10df3-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="10df3-118">Transaktioner</span><span class="sxs-lookup"><span data-stu-id="10df3-118">Transactions</span></span>  
9. <span data-ttu-id="10df3-119">Skriv "Intrastat" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="10df3-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="10df3-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="10df3-120">Intrastat</span></span>  
10. <span data-ttu-id="10df3-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="10df3-121">Click OK.</span></span>
11. <span data-ttu-id="10df3-122">Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="10df3-123">Denna typ av datakälla används för att presentera en ny datakälla under körning för att gruppera poster och beräkna aggregeringar som krävs.</span><span class="sxs-lookup"><span data-stu-id="10df3-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="10df3-124">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="10df3-124">Click Add root.</span></span>
13. <span data-ttu-id="10df3-125">I namnfältet anger du "TransactionsGroups".</span><span class="sxs-lookup"><span data-stu-id="10df3-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="10df3-126">TransactionsGroups</span><span class="sxs-lookup"><span data-stu-id="10df3-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="10df3-127">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="10df3-127">Click Edit group by.</span></span>
15. <span data-ttu-id="10df3-128">Välj "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="10df3-129">Välj den tillagda datakällan av typen "Postlista" som motsvarar de poster som du vill gruppera.</span><span class="sxs-lookup"><span data-stu-id="10df3-129">Select the added data source of the ‘Record list’ type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="10df3-130">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="10df3-130">Click Add field to.</span></span>
17. <span data-ttu-id="10df3-131">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="10df3-131">Click What to group.</span></span>
18. <span data-ttu-id="10df3-132">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="10df3-133">Välj "Transactions\Direction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="10df3-134">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="10df3-134">Click Add field to.</span></span>
21. <span data-ttu-id="10df3-135">Klicka på Grupperade fält.</span><span class="sxs-lookup"><span data-stu-id="10df3-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="10df3-136">Välj fältet för att ange grupperingsnivån.</span><span class="sxs-lookup"><span data-stu-id="10df3-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="10df3-137">Baserat på detta val returnerar datakällan vid körning så många grupper för transaktionerna som det finns riktningskoder som ska uppfyllas i Intrastat-registret.</span><span class="sxs-lookup"><span data-stu-id="10df3-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="10df3-138">Välj "Transactions\Invoice amount(AmountMST)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="10df3-139">Välj fältet för att ange källan för beräkningen av aggregering.</span><span class="sxs-lookup"><span data-stu-id="10df3-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="10df3-140">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="10df3-140">Click Add field to.</span></span>
24. <span data-ttu-id="10df3-141">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="10df3-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="10df3-142">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="10df3-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="10df3-143">I fältet Metod väljer du Summa.</span><span class="sxs-lookup"><span data-stu-id="10df3-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="10df3-144">Välj aggregeringstyp.</span><span class="sxs-lookup"><span data-stu-id="10df3-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="10df3-145">I namnfältet anger du "SumOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="10df3-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="10df3-146">Ange namnet på denna aggregering i konfigurerade datakällan.</span><span class="sxs-lookup"><span data-stu-id="10df3-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="10df3-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="10df3-147">Click Save.</span></span>
    * <span data-ttu-id="10df3-148">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i SQL-databasen.</span><span class="sxs-lookup"><span data-stu-id="10df3-148">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="10df3-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="10df3-149">Close the page.</span></span>
30. <span data-ttu-id="10df3-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="10df3-150">Click OK.</span></span>
31. <span data-ttu-id="10df3-151">Expandera "Totaler" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="10df3-152">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="10df3-153">Expandera "TransactionsGroups\aggregated" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="10df3-154">Välj "TransactionsGroups\aggregated\SumOfAmountMST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="10df3-155">Välj "Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="10df3-156">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="10df3-156">Click Bind.</span></span>
    * <span data-ttu-id="10df3-157">Baserat på denna inställning beräknar datakällan summan av värdena i fältet "AmountMST" för varje grupp av transaktioner.</span><span class="sxs-lookup"><span data-stu-id="10df3-157">Based on this setting, this data source will calculate the sum of values of the ‘AmountMST’ field for each groups of transactions.</span></span> <span data-ttu-id="10df3-158">Denna aggregeringsberäkning blir tillgängliga som TransactionsGroups.aggregated.TotalAmount-objekt.</span><span class="sxs-lookup"><span data-stu-id="10df3-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="10df3-159">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="10df3-160">Välj "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="10df3-161">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="10df3-161">Click Edit.</span></span>
40. <span data-ttu-id="10df3-162">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="10df3-162">Click Edit group by.</span></span>
41. <span data-ttu-id="10df3-163">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="10df3-164">Välj "Transactions\Invoice amount(AmountMST)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="10df3-165">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="10df3-165">Click Add field to.</span></span>
44. <span data-ttu-id="10df3-166">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="10df3-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="10df3-167">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="10df3-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="10df3-168">I fältet Metod väljer du Max.</span><span class="sxs-lookup"><span data-stu-id="10df3-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="10df3-169">I namnfältet anger du "MaxOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="10df3-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="10df3-170">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="10df3-170">Click Save.</span></span>
    * <span data-ttu-id="10df3-171">För närvarande kan utförandet av GROUPBY-datakällor översättas till nivån för SQL-databasen med vissa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="10df3-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="10df3-172">Översättningen kan göras antingen datakällor av typen "Postlista" eller datakällor som representeras av ett uttryck som använder FILTER-funktionen.</span><span class="sxs-lookup"><span data-stu-id="10df3-172">Translation can be done for either data sources of the ‘Record list’ type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="10df3-173">Det kan också göras när endast en aggregering konfigureras för ett enskilt fält av grupperingsposter.</span><span class="sxs-lookup"><span data-stu-id="10df3-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="10df3-174">Observera att även om mer än en aggregering konfigurerades för fältet AmountMST, kommer fältet "körning på" fortfarande ange att denna gruppering ska utföras vid körning i SQL-databasen.</span><span class="sxs-lookup"><span data-stu-id="10df3-174">Note that even though more than one aggregation was configured for the AmountMST field, the ‘Execution at’ field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="10df3-175">Detta beror på att endast en aggregering är bunden till datamodellobjektet och används vid körning så att data hämtas från datakällan.</span><span class="sxs-lookup"><span data-stu-id="10df3-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="10df3-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="10df3-176">Close the page.</span></span>
50. <span data-ttu-id="10df3-177">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="10df3-177">Click OK.</span></span>
51. <span data-ttu-id="10df3-178">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="10df3-179">Expandera "TransactionsGroups\aggregated" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="10df3-180">Välj "TransactionsGroups\aggregated\MaxOfAmountMST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="10df3-181">Välj "Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="10df3-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="10df3-182">Click Bind.</span></span>
56. <span data-ttu-id="10df3-183">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="10df3-184">Välj "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="10df3-185">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="10df3-185">Click Edit.</span></span>
59. <span data-ttu-id="10df3-186">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="10df3-186">Click Edit group by.</span></span>
    * <span data-ttu-id="10df3-187">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet eftersom båda aggregeringarna med samma fält är bundna till datamodellelement.</span><span class="sxs-lookup"><span data-stu-id="10df3-187">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="10df3-188">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="10df3-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="10df3-189">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="10df3-189">Click Delete.</span></span>
62. <span data-ttu-id="10df3-190">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="10df3-190">Click Yes.</span></span>
63. <span data-ttu-id="10df3-191">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="10df3-191">Click Delete.</span></span>
64. <span data-ttu-id="10df3-192">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="10df3-192">Click Yes.</span></span>
65. <span data-ttu-id="10df3-193">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="10df3-193">Click Add field to.</span></span>
66. <span data-ttu-id="10df3-194">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="10df3-194">Click What to group.</span></span>
67. <span data-ttu-id="10df3-195">Expandera "Commodity record(Intrastat)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="10df3-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="10df3-196">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="10df3-196">Click Save.</span></span>
    * <span data-ttu-id="10df3-197">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet även om det inte finns några aggregeringar definierade och den valda datakällan av typen ”registerposter” refererar till samma Intrastat-tabell.</span><span class="sxs-lookup"><span data-stu-id="10df3-197">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of ‘Table records’ type refers to the same ‘Intrastat’ table.</span></span> <span data-ttu-id="10df3-198">Detta beror på att datakällan innehåller vissa beräknade fält som ännu inte kan konverteras till SQL-databasnivå.</span><span class="sxs-lookup"><span data-stu-id="10df3-198">This is because the data source contains some calculated fields which can’t yet be translated to the SQL database level.</span></span>  


