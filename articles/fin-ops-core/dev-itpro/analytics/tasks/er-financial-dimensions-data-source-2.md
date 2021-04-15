---
title: "\"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)\""
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 2)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e6f5ffbebdfcd9f945e6237904d80e8734b0220
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752446"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="72791-104">"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)"</span><span class="sxs-lookup"><span data-stu-id="72791-104">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72791-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="72791-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="72791-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="72791-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="72791-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 1: Design data model”.</span><span class="sxs-lookup"><span data-stu-id="72791-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 1: Design data model" procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="72791-108">Lägg till erforderliga datakällor till modellmappningen</span><span class="sxs-lookup"><span data-stu-id="72791-108">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="72791-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="72791-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="72791-110">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="72791-111">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="72791-111">Click Designer.</span></span>
4. <span data-ttu-id="72791-112">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="72791-112">Click Map model to datasource.</span></span>
5. <span data-ttu-id="72791-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="72791-113">Click New.</span></span>
6. <span data-ttu-id="72791-114">Välj Entry i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="72791-114">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="72791-115">Ange "Dimensions data mapping" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="72791-115">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="72791-116">Ange "Dimensions data mapping" i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="72791-116">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="72791-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72791-117">Click Save.</span></span>
10. <span data-ttu-id="72791-118">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="72791-118">Click Designer.</span></span>
11. <span data-ttu-id="72791-119">Välj "Dynamics 365 for Operations\Table" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-119">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="72791-120">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="72791-120">Click Add root.</span></span>
13. <span data-ttu-id="72791-121">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72791-121">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="72791-122">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="72791-122">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="72791-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72791-123">Click OK.</span></span>
16. <span data-ttu-id="72791-124">Välj "Functions\Financial dimensions details" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-124">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="72791-125">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="72791-125">Click Add root.</span></span>
    * <span data-ttu-id="72791-126">Datakällan anger hur omfånget av ekonomiska dimensioner ska definieras för alla rapporter som ska använda den här modellen som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="72791-126">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="72791-127">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72791-127">In the Name field, type a value.</span></span>
19. <span data-ttu-id="72791-128">Välj Yes i fältet Ask for dimensions.</span><span class="sxs-lookup"><span data-stu-id="72791-128">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="72791-129">Välj Yes om du vill tillåta användaren att välja dimensioner vid körning på användardialogformuläret.</span><span class="sxs-lookup"><span data-stu-id="72791-129">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="72791-130">Om inställt på No kommer ekonomiska dimensioner för den aktuella instansen att användas som standard.</span><span class="sxs-lookup"><span data-stu-id="72791-130">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="72791-131">Välj "Legal entity" i fältet för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="72791-131">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="72791-132">Markera All om du vill tillåta användaren att välja önskedimensioner för den aktuella instansen i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="72791-132">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="72791-133">Markera Legal entity om du vill tillåta användaren att välja dimensioner för företaget i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="72791-133">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="72791-134">Välj Dimension för att tillåta användaren att välja dimensioner med hjälp av en enda dimensionsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="72791-134">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="72791-135">Välj Yes i fältet Ask for main account.</span><span class="sxs-lookup"><span data-stu-id="72791-135">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="72791-136">Ange "Ask for main account" som Yes om du vill låta användare välja huvudkontot som en del i listan över dimensioner.</span><span class="sxs-lookup"><span data-stu-id="72791-136">Set 'Ask for main account' to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="72791-137">Om No kommer huvudkontot inte att inkluderas i listan över dimensioner, och alternativet "Is main account mandatory" aktiveras.</span><span class="sxs-lookup"><span data-stu-id="72791-137">If set to No, the main account will not be included to the list of dimensions and the 'Is main account mandatory' option is enabled.</span></span> <span data-ttu-id="72791-138">Om ”Is main account mandatory" anges som Yes, inkludera då huvudkontot i dimensionslistan oavsett användarens urval.</span><span class="sxs-lookup"><span data-stu-id="72791-138">If "Is main account mandatory' is set to Yes, include the main account in the list of dimensions regardless of the user's selection.</span></span>  
22. <span data-ttu-id="72791-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72791-139">Click OK.</span></span>
<span data-ttu-id="72791-140">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping1.png)</span><span class="sxs-lookup"><span data-stu-id="72791-140">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping1.png)</span></span>
23. <span data-ttu-id="72791-141">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-141">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="72791-142">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="72791-142">Click Add root.</span></span>
25. <span data-ttu-id="72791-143">Välj "LedgerJournal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="72791-143">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="72791-144">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="72791-144">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="72791-145">Ange "LedgerJournalTable" i tabellfältet.</span><span class="sxs-lookup"><span data-stu-id="72791-145">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="72791-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72791-146">Click OK.</span></span>
<span data-ttu-id="72791-147">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping2.png)</span><span class="sxs-lookup"><span data-stu-id="72791-147">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping2.png)</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="72791-148">Mappa datamodellelement till tillagda datakällor</span><span class="sxs-lookup"><span data-stu-id="72791-148">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="72791-149">Expandera "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-149">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="72791-150">Expandera "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-150">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="72791-151">Expandera "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-151">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="72791-152">Expandera "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-152">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="72791-153">Expandera "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-153">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="72791-154">Expandera "LedgerJournal\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-154">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="72791-155">Expandera "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-155">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="72791-156">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="72791-157">Välj "Journal\Transaction\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-157">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="72791-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-158">Click Bind.</span></span>
11. <span data-ttu-id="72791-159">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-159">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="72791-160">Notera att för alla referenser till ekonomiska dimensioner, inställda till exempelvis LedgerDimension, finns en motsvarande datakällartikel (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="72791-160">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="72791-161">Denna datakällaartikel erbjuder de ekonomiska dimensionerna för denna dimensionsuppsättning som postens lista.</span><span class="sxs-lookup"><span data-stu-id="72791-161">This data source item offers the financial dimensions of that dimensions set as the record's list.</span></span>  
12. <span data-ttu-id="72791-162">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="72791-163">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-163">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="72791-164">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-164">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="72791-165">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-165">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="72791-166">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="72791-167">Välj "Journal\Transaction\Dimensions data\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-167">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="72791-168">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-168">Click Bind.</span></span>
19. <span data-ttu-id="72791-169">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="72791-170">Välj "Journal\Transaction\Dimensions data\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-170">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="72791-171">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-171">Click Bind.</span></span>
22. <span data-ttu-id="72791-172">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="72791-173">Välj "Journal\Transaction\Dimensions data\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-173">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="72791-174">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-174">Click Bind.</span></span>
25. <span data-ttu-id="72791-175">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="72791-176">Välj "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-176">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="72791-177">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-177">Click Bind.</span></span>
<span data-ttu-id="72791-178">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping3.png)</span><span class="sxs-lookup"><span data-stu-id="72791-178">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping3.png)</span></span>
28. <span data-ttu-id="72791-179">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-179">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="72791-180">Välj "Journal\Transaction\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-180">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="72791-181">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-181">Click Bind.</span></span>
31. <span data-ttu-id="72791-182">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-182">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="72791-183">Välj "Journal\Transaction\Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-183">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="72791-184">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-184">Click Bind.</span></span>
34. <span data-ttu-id="72791-185">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-185">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="72791-186">Välj "Journal\Transaction\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-186">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="72791-187">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-187">Click Bind.</span></span>
37. <span data-ttu-id="72791-188">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-188">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="72791-189">Välj "Journal\Transaction\Credit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-189">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="72791-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-190">Click Bind.</span></span>
40. <span data-ttu-id="72791-191">Välj "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-191">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="72791-192">Välj "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-192">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="72791-193">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-193">Click Bind.</span></span>
43. <span data-ttu-id="72791-194">Välj "LedgerJournal\Journal batch number(JournalNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-194">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="72791-195">Välj "Journal\Batch" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-195">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="72791-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-196">Click Bind.</span></span>
46. <span data-ttu-id="72791-197">Välj "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-197">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="72791-198">Välj "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-198">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="72791-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-199">Click Bind.</span></span>
49. <span data-ttu-id="72791-200">Expandera "Dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-200">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="72791-201">Expandera "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-201">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="72791-202">Expandera "Dimensions\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-202">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="72791-203">Välj "Dimensions\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-203">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="72791-204">Välj "Dimensions setting\Code".</span><span class="sxs-lookup"><span data-stu-id="72791-204">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="72791-205">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-205">Click Bind.</span></span>
55. <span data-ttu-id="72791-206">Välj "Dimensions\Main account and dimensions\Definition\Report column name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-206">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="72791-207">Välj "Dimensions setting\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-207">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="72791-208">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-208">Click Bind.</span></span>
58. <span data-ttu-id="72791-209">Välj "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-209">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="72791-210">Välj "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-210">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="72791-211">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72791-211">Click Bind.</span></span>
61. <span data-ttu-id="72791-212">Välj "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72791-212">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="72791-213">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="72791-213">Click Edit.</span></span>
63. <span data-ttu-id="72791-214">I fältet expressionAsStringText anger du "Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="72791-214">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="72791-215">Company.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="72791-215">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="72791-216">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72791-216">Click Save.</span></span>
<span data-ttu-id="72791-217">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping4.png)</span><span class="sxs-lookup"><span data-stu-id="72791-217">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping4.png)</span></span>
65. <span data-ttu-id="72791-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72791-218">Close the page.</span></span>
66. <span data-ttu-id="72791-219">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72791-219">Click Save.</span></span>
67. <span data-ttu-id="72791-220">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72791-220">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="72791-221">Slutför denna utkastmodellversion</span><span class="sxs-lookup"><span data-stu-id="72791-221">Complete this draft model's version</span></span>
1. <span data-ttu-id="72791-222">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72791-222">Close the page.</span></span>
2. <span data-ttu-id="72791-223">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72791-223">Close the page.</span></span>
3. <span data-ttu-id="72791-224">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="72791-224">Click Change status.</span></span>
4. <span data-ttu-id="72791-225">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="72791-225">Click Complete.</span></span>
5. <span data-ttu-id="72791-226">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72791-226">Click OK.</span></span>
<span data-ttu-id="72791-227">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping5.png)</span><span class="sxs-lookup"><span data-stu-id="72791-227">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping5.png)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]