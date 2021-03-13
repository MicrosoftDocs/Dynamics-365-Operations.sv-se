---
title: "\"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)\""
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 2)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02c730d08c411e736a7f8b9e7bad3d6a18cb8e6a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093247"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="dfb15-104">"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)"</span><span class="sxs-lookup"><span data-stu-id="dfb15-104">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dfb15-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="dfb15-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="dfb15-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="dfb15-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="dfb15-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 1: Design data model”.</span><span class="sxs-lookup"><span data-stu-id="dfb15-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 1: Design data model" procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="dfb15-108">Lägg till erforderliga datakällor till modellmappningen</span><span class="sxs-lookup"><span data-stu-id="dfb15-108">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="dfb15-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="dfb15-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="dfb15-110">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="dfb15-111">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="dfb15-111">Click Designer.</span></span>
4. <span data-ttu-id="dfb15-112">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="dfb15-112">Click Map model to datasource.</span></span>
5. <span data-ttu-id="dfb15-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="dfb15-113">Click New.</span></span>
6. <span data-ttu-id="dfb15-114">Välj Entry i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="dfb15-114">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="dfb15-115">Ange "Dimensions data mapping" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-115">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="dfb15-116">Ange "Dimensions data mapping" i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-116">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="dfb15-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dfb15-117">Click Save.</span></span>
10. <span data-ttu-id="dfb15-118">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="dfb15-118">Click Designer.</span></span>
11. <span data-ttu-id="dfb15-119">Välj "Dynamics 365 for Operations\Table" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-119">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="dfb15-120">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="dfb15-120">Click Add root.</span></span>
13. <span data-ttu-id="dfb15-121">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="dfb15-121">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="dfb15-122">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="dfb15-122">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="dfb15-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="dfb15-123">Click OK.</span></span>
16. <span data-ttu-id="dfb15-124">Välj "Functions\Financial dimensions details" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-124">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="dfb15-125">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="dfb15-125">Click Add root.</span></span>
    * <span data-ttu-id="dfb15-126">Datakällan anger hur omfånget av ekonomiska dimensioner ska definieras för alla rapporter som ska använda den här modellen som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="dfb15-126">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="dfb15-127">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="dfb15-127">In the Name field, type a value.</span></span>
19. <span data-ttu-id="dfb15-128">Välj Yes i fältet Ask for dimensions.</span><span class="sxs-lookup"><span data-stu-id="dfb15-128">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="dfb15-129">Välj Yes om du vill tillåta användaren att välja dimensioner vid körning på användardialogformuläret.</span><span class="sxs-lookup"><span data-stu-id="dfb15-129">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="dfb15-130">Om inställt på No kommer ekonomiska dimensioner för den aktuella instansen att användas som standard.</span><span class="sxs-lookup"><span data-stu-id="dfb15-130">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="dfb15-131">Välj "Legal entity" i fältet för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="dfb15-131">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="dfb15-132">Markera All om du vill tillåta användaren att välja önskedimensioner för den aktuella instansen i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="dfb15-132">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="dfb15-133">Markera Legal entity om du vill tillåta användaren att välja dimensioner för företaget i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="dfb15-133">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="dfb15-134">Välj Dimension för att tillåta användaren att välja dimensioner med hjälp av en enda dimensionsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="dfb15-134">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="dfb15-135">Välj Yes i fältet Ask for main account.</span><span class="sxs-lookup"><span data-stu-id="dfb15-135">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="dfb15-136">Ange "Ask for main account" som Yes om du vill låta användare välja huvudkontot som en del i listan över dimensioner.</span><span class="sxs-lookup"><span data-stu-id="dfb15-136">Set 'Ask for main account' to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="dfb15-137">Om No kommer huvudkontot inte att inkluderas i listan över dimensioner, och alternativet "Is main account mandatory" aktiveras.</span><span class="sxs-lookup"><span data-stu-id="dfb15-137">If set to No, the main account will not be included to the list of dimensions and the 'Is main account mandatory' option is enabled.</span></span> <span data-ttu-id="dfb15-138">Om ”Is main account mandatory" anges som Yes, inkludera då huvudkontot i dimensionslistan oavsett användarens urval.</span><span class="sxs-lookup"><span data-stu-id="dfb15-138">If "Is main account mandatory' is set to Yes, include the main account in the list of dimensions regardless of the user's selection.</span></span>  
22. <span data-ttu-id="dfb15-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="dfb15-139">Click OK.</span></span>
<span data-ttu-id="dfb15-140">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping1.png)</span><span class="sxs-lookup"><span data-stu-id="dfb15-140">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping1.png)</span></span>
23. <span data-ttu-id="dfb15-141">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-141">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="dfb15-142">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="dfb15-142">Click Add root.</span></span>
25. <span data-ttu-id="dfb15-143">Välj "LedgerJournal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-143">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="dfb15-144">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="dfb15-144">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="dfb15-145">Ange "LedgerJournalTable" i tabellfältet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-145">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="dfb15-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="dfb15-146">Click OK.</span></span>
<span data-ttu-id="dfb15-147">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping2.png)</span><span class="sxs-lookup"><span data-stu-id="dfb15-147">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping2.png)</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="dfb15-148">Mappa datamodellelement till tillagda datakällor</span><span class="sxs-lookup"><span data-stu-id="dfb15-148">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="dfb15-149">Expandera "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-149">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="dfb15-150">Expandera "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-150">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="dfb15-151">Expandera "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-151">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="dfb15-152">Expandera "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-152">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="dfb15-153">Expandera "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-153">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="dfb15-154">Expandera "LedgerJournal\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-154">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="dfb15-155">Expandera "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-155">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="dfb15-156">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="dfb15-157">Välj "Journal\Transaction\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-157">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="dfb15-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-158">Click Bind.</span></span>
11. <span data-ttu-id="dfb15-159">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-159">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="dfb15-160">Notera att för alla referenser till ekonomiska dimensioner, inställda till exempelvis LedgerDimension, finns en motsvarande datakällartikel (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="dfb15-160">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="dfb15-161">Denna datakällaartikel erbjuder de ekonomiska dimensionerna för denna dimensionsuppsättning som postens lista.</span><span class="sxs-lookup"><span data-stu-id="dfb15-161">This data source item offers the financial dimensions of that dimensions set as the record's list.</span></span>  
12. <span data-ttu-id="dfb15-162">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="dfb15-163">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-163">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="dfb15-164">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-164">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="dfb15-165">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-165">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="dfb15-166">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="dfb15-167">Välj "Journal\Transaction\Dimensions data\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-167">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="dfb15-168">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-168">Click Bind.</span></span>
19. <span data-ttu-id="dfb15-169">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="dfb15-170">Välj "Journal\Transaction\Dimensions data\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-170">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="dfb15-171">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-171">Click Bind.</span></span>
22. <span data-ttu-id="dfb15-172">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="dfb15-173">Välj "Journal\Transaction\Dimensions data\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-173">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="dfb15-174">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-174">Click Bind.</span></span>
25. <span data-ttu-id="dfb15-175">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="dfb15-176">Välj "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-176">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="dfb15-177">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-177">Click Bind.</span></span>
<span data-ttu-id="dfb15-178">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping3.png)</span><span class="sxs-lookup"><span data-stu-id="dfb15-178">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping3.png)</span></span>
28. <span data-ttu-id="dfb15-179">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-179">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="dfb15-180">Välj "Journal\Transaction\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-180">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="dfb15-181">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-181">Click Bind.</span></span>
31. <span data-ttu-id="dfb15-182">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-182">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="dfb15-183">Välj "Journal\Transaction\Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-183">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="dfb15-184">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-184">Click Bind.</span></span>
34. <span data-ttu-id="dfb15-185">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-185">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="dfb15-186">Välj "Journal\Transaction\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-186">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="dfb15-187">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-187">Click Bind.</span></span>
37. <span data-ttu-id="dfb15-188">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-188">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="dfb15-189">Välj "Journal\Transaction\Credit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-189">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="dfb15-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-190">Click Bind.</span></span>
40. <span data-ttu-id="dfb15-191">Välj "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-191">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="dfb15-192">Välj "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-192">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="dfb15-193">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-193">Click Bind.</span></span>
43. <span data-ttu-id="dfb15-194">Välj "LedgerJournal\Journal batch number(JournalNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-194">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="dfb15-195">Välj "Journal\Batch" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-195">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="dfb15-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-196">Click Bind.</span></span>
46. <span data-ttu-id="dfb15-197">Välj "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-197">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="dfb15-198">Välj "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-198">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="dfb15-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-199">Click Bind.</span></span>
49. <span data-ttu-id="dfb15-200">Expandera "Dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-200">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="dfb15-201">Expandera "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-201">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="dfb15-202">Expandera "Dimensions\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-202">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="dfb15-203">Välj "Dimensions\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-203">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="dfb15-204">Välj "Dimensions setting\Code".</span><span class="sxs-lookup"><span data-stu-id="dfb15-204">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="dfb15-205">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-205">Click Bind.</span></span>
55. <span data-ttu-id="dfb15-206">Välj "Dimensions\Main account and dimensions\Definition\Report column name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-206">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="dfb15-207">Välj "Dimensions setting\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-207">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="dfb15-208">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-208">Click Bind.</span></span>
58. <span data-ttu-id="dfb15-209">Välj "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-209">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="dfb15-210">Välj "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-210">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="dfb15-211">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="dfb15-211">Click Bind.</span></span>
61. <span data-ttu-id="dfb15-212">Välj "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="dfb15-212">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="dfb15-213">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="dfb15-213">Click Edit.</span></span>
63. <span data-ttu-id="dfb15-214">I fältet expressionAsStringText anger du "Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="dfb15-214">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="dfb15-215">Company.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="dfb15-215">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="dfb15-216">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dfb15-216">Click Save.</span></span>
<span data-ttu-id="dfb15-217">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping4.png)</span><span class="sxs-lookup"><span data-stu-id="dfb15-217">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping4.png)</span></span>
65. <span data-ttu-id="dfb15-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dfb15-218">Close the page.</span></span>
66. <span data-ttu-id="dfb15-219">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="dfb15-219">Click Save.</span></span>
67. <span data-ttu-id="dfb15-220">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dfb15-220">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="dfb15-221">Slutför denna utkastmodellversion</span><span class="sxs-lookup"><span data-stu-id="dfb15-221">Complete this draft model's version</span></span>
1. <span data-ttu-id="dfb15-222">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dfb15-222">Close the page.</span></span>
2. <span data-ttu-id="dfb15-223">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="dfb15-223">Close the page.</span></span>
3. <span data-ttu-id="dfb15-224">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="dfb15-224">Click Change status.</span></span>
4. <span data-ttu-id="dfb15-225">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="dfb15-225">Click Complete.</span></span>
5. <span data-ttu-id="dfb15-226">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="dfb15-226">Click OK.</span></span>
<span data-ttu-id="dfb15-227">![Sidan ER-modellmappningsdesigner](../media/er-financial-dimensions-guides-model-mapping5.png)</span><span class="sxs-lookup"><span data-stu-id="dfb15-227">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping5.png)</span></span>
