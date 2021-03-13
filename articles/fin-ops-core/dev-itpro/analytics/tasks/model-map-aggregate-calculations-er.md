---
title: Använd konfigurationer för modellmappning för att sammanställa beräkningar på databasnivå
description: Det här ämnet beskriver hur du utformar en ny modellmappningskonfigurationer för elektronisk rapportering och använder inbyggda funktioner för ER för effektiv aggregerade beräkningar.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a392697f6b91bc6555d0d72d09ecd7da32e1a3f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094275"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a><span data-ttu-id="e8750-103">Använd konfigurationer för modellmappning för att sammanställa beräkningar på databasnivå</span><span class="sxs-lookup"><span data-stu-id="e8750-103">Use model mapping configurations for aggregate calculations at the database level</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8750-104">Denna procedur ger information för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.</span><span class="sxs-lookup"><span data-stu-id="e8750-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="e8750-105">I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e8750-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="e8750-106">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="e8750-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="e8750-107">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="e8750-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="e8750-108">För att slutföra stegen måste du först slutföra stegen i proceduren ”ER förbättrar effektiviteten av aggregerade beräkningar genom att utföra dem på databasnivå (del 1: förbereda konfigurationer)”.</span><span class="sxs-lookup"><span data-stu-id="e8750-108">To complete these steps, you must first complete the steps in the procedure, "ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations)."</span></span>

1. <span data-ttu-id="e8750-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="e8750-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e8750-110">Expandera "Intrastat model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="e8750-111">Välj "Intrastat model\Intrastat sample mapping" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="e8750-112">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="e8750-112">Click Designer.</span></span>
5. <span data-ttu-id="e8750-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="e8750-113">Click Designer.</span></span>
6. <span data-ttu-id="e8750-114">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="e8750-115">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="e8750-115">Click Add root.</span></span>
    * <span data-ttu-id="e8750-116">Lägg till en ny datakälla som representerar poster som du vill gruppera.</span><span class="sxs-lookup"><span data-stu-id="e8750-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="e8750-117">Skriv "Transaktioner" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e8750-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="e8750-118">Transaktioner</span><span class="sxs-lookup"><span data-stu-id="e8750-118">Transactions</span></span>  
9. <span data-ttu-id="e8750-119">Skriv "Intrastat" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="e8750-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="e8750-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="e8750-120">Intrastat</span></span>  
10. <span data-ttu-id="e8750-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e8750-121">Click OK.</span></span>
11. <span data-ttu-id="e8750-122">Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="e8750-123">Denna typ av datakälla används för att presentera en ny datakälla under körning för att gruppera poster och beräkna aggregeringar som krävs.</span><span class="sxs-lookup"><span data-stu-id="e8750-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="e8750-124">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="e8750-124">Click Add root.</span></span>
13. <span data-ttu-id="e8750-125">I namnfältet anger du "TransactionsGroups".</span><span class="sxs-lookup"><span data-stu-id="e8750-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="e8750-126">TransactionsGroups</span><span class="sxs-lookup"><span data-stu-id="e8750-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="e8750-127">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="e8750-127">Click Edit group by.</span></span>
15. <span data-ttu-id="e8750-128">Välj "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="e8750-129">Välj den tillagda datakällan av typen "Postlista" som motsvarar de poster som du vill gruppera.</span><span class="sxs-lookup"><span data-stu-id="e8750-129">Select the added data source of the 'Record list' type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="e8750-130">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="e8750-130">Click Add field to.</span></span>
17. <span data-ttu-id="e8750-131">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="e8750-131">Click What to group.</span></span>
18. <span data-ttu-id="e8750-132">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="e8750-133">Välj "Transactions\Direction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="e8750-134">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="e8750-134">Click Add field to.</span></span>
21. <span data-ttu-id="e8750-135">Klicka på Grupperade fält.</span><span class="sxs-lookup"><span data-stu-id="e8750-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="e8750-136">Välj fältet för att ange grupperingsnivån.</span><span class="sxs-lookup"><span data-stu-id="e8750-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="e8750-137">Baserat på detta val returnerar datakällan vid körning så många grupper för transaktionerna som det finns riktningskoder som ska uppfyllas i Intrastat-registret.</span><span class="sxs-lookup"><span data-stu-id="e8750-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="e8750-138">Välj "Transactions\Invoice amount(AmountMST)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="e8750-139">Välj fältet för att ange källan för beräkningen av aggregering.</span><span class="sxs-lookup"><span data-stu-id="e8750-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="e8750-140">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="e8750-140">Click Add field to.</span></span>
24. <span data-ttu-id="e8750-141">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="e8750-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="e8750-142">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e8750-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="e8750-143">I fältet Metod väljer du Summa.</span><span class="sxs-lookup"><span data-stu-id="e8750-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="e8750-144">Välj aggregeringstyp.</span><span class="sxs-lookup"><span data-stu-id="e8750-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="e8750-145">I namnfältet anger du "SumOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="e8750-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="e8750-146">Ange namnet på denna aggregering i konfigurerade datakällan.</span><span class="sxs-lookup"><span data-stu-id="e8750-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="e8750-147">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e8750-147">Click Save.</span></span>
    * <span data-ttu-id="e8750-148">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i SQL-databasen.</span><span class="sxs-lookup"><span data-stu-id="e8750-148">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="e8750-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e8750-149">Close the page.</span></span>
30. <span data-ttu-id="e8750-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e8750-150">Click OK.</span></span>
31. <span data-ttu-id="e8750-151">Expandera "Totaler" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="e8750-152">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="e8750-153">Expandera "TransactionsGroups\aggregated" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="e8750-154">Välj "TransactionsGroups\aggregated\SumOfAmountMST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="e8750-155">Välj "Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="e8750-156">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="e8750-156">Click Bind.</span></span>
    * <span data-ttu-id="e8750-157">Baserat på denna inställning beräknar datakällan summan av värdena i fältet "AmountMST" för varje grupp av transaktioner.</span><span class="sxs-lookup"><span data-stu-id="e8750-157">Based on this setting, this data source will calculate the sum of values of the 'AmountMST' field for each groups of transactions.</span></span> <span data-ttu-id="e8750-158">Denna aggregeringsberäkning blir tillgängliga som TransactionsGroups.aggregated.TotalAmount-objekt.</span><span class="sxs-lookup"><span data-stu-id="e8750-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="e8750-159">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="e8750-160">Välj "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="e8750-161">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="e8750-161">Click Edit.</span></span>
40. <span data-ttu-id="e8750-162">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="e8750-162">Click Edit group by.</span></span>
41. <span data-ttu-id="e8750-163">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="e8750-164">Välj "Transactions\Invoice amount(AmountMST)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="e8750-165">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="e8750-165">Click Add field to.</span></span>
44. <span data-ttu-id="e8750-166">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="e8750-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="e8750-167">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e8750-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="e8750-168">I fältet Metod väljer du Max.</span><span class="sxs-lookup"><span data-stu-id="e8750-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="e8750-169">I namnfältet anger du "MaxOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="e8750-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="e8750-170">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e8750-170">Click Save.</span></span>
    * <span data-ttu-id="e8750-171">För närvarande kan utförandet av GROUPBY-datakällor översättas till nivån för SQL-databasen med vissa begränsningar.</span><span class="sxs-lookup"><span data-stu-id="e8750-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="e8750-172">Översättningen kan göras antingen datakällor av typen "Postlista" eller datakällor som representeras av ett uttryck som använder FILTER-funktionen.</span><span class="sxs-lookup"><span data-stu-id="e8750-172">Translation can be done for either data sources of the 'Record list' type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="e8750-173">Det kan också göras när endast en aggregering konfigureras för ett enskilt fält av grupperingsposter.</span><span class="sxs-lookup"><span data-stu-id="e8750-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="e8750-174">Observera att även om mer än en aggregering konfigurerades för fältet AmountMST, kommer fältet "körning på" fortfarande ange att denna gruppering ska utföras vid körning i SQL-databasen.</span><span class="sxs-lookup"><span data-stu-id="e8750-174">Note that even though more than one aggregation was configured for the AmountMST field, the 'Execution at' field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="e8750-175">Detta beror på att endast en aggregering är bunden till datamodellobjektet och används vid körning så att data hämtas från datakällan.</span><span class="sxs-lookup"><span data-stu-id="e8750-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="e8750-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e8750-176">Close the page.</span></span>
50. <span data-ttu-id="e8750-177">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e8750-177">Click OK.</span></span>
51. <span data-ttu-id="e8750-178">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="e8750-179">Expandera "TransactionsGroups\aggregated" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="e8750-180">Välj "TransactionsGroups\aggregated\MaxOfAmountMST" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="e8750-181">Välj "Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="e8750-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="e8750-182">Click Bind.</span></span>
56. <span data-ttu-id="e8750-183">Expandera "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="e8750-184">Välj "TransactionsGroups" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="e8750-185">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="e8750-185">Click Edit.</span></span>
59. <span data-ttu-id="e8750-186">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="e8750-186">Click Edit group by.</span></span>
    * <span data-ttu-id="e8750-187">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet eftersom båda aggregeringarna med samma fält är bundna till datamodellelement.</span><span class="sxs-lookup"><span data-stu-id="e8750-187">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="e8750-188">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="e8750-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="e8750-189">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="e8750-189">Click Delete.</span></span>
62. <span data-ttu-id="e8750-190">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="e8750-190">Click Yes.</span></span>
63. <span data-ttu-id="e8750-191">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="e8750-191">Click Delete.</span></span>
64. <span data-ttu-id="e8750-192">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="e8750-192">Click Yes.</span></span>
65. <span data-ttu-id="e8750-193">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="e8750-193">Click Add field to.</span></span>
66. <span data-ttu-id="e8750-194">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="e8750-194">Click What to group.</span></span>
67. <span data-ttu-id="e8750-195">Expandera "Commodity record(Intrastat)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="e8750-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="e8750-196">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e8750-196">Click Save.</span></span>
    * <span data-ttu-id="e8750-197">Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet även om det inte finns några aggregeringar definierade och den valda datakällan av typen ”registerposter” refererar till samma Intrastat-tabell.</span><span class="sxs-lookup"><span data-stu-id="e8750-197">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of 'Table records' type refers to the same 'Intrastat' table.</span></span> <span data-ttu-id="e8750-198">Detta beror på att datakällan innehåller vissa beräknade fält som ännu inte kan konverteras till SQL-databasnivå.</span><span class="sxs-lookup"><span data-stu-id="e8750-198">This is because the data source contains some calculated fields which can't yet be translated to the SQL database level.</span></span>  

