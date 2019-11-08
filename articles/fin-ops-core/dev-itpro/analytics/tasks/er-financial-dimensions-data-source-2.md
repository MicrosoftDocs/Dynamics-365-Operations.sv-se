---
title: "\"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)\""
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788564bfd7c3df146266976d8eef6621ff37ca2a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550635"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="611a5-103">"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)"</span><span class="sxs-lookup"><span data-stu-id="611a5-103">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="611a5-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="611a5-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="611a5-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="611a5-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="611a5-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 1: Design data model”.</span><span class="sxs-lookup"><span data-stu-id="611a5-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="611a5-107">Lägg till erforderliga datakällor till modellmappningen</span><span class="sxs-lookup"><span data-stu-id="611a5-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="611a5-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="611a5-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="611a5-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="611a5-110">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="611a5-110">Click Designer.</span></span>
4. <span data-ttu-id="611a5-111">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="611a5-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="611a5-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="611a5-112">Click New.</span></span>
6. <span data-ttu-id="611a5-113">Välj Entry i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="611a5-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="611a5-114">Ange "Dimensions data mapping" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="611a5-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="611a5-115">Ange "Dimensions data mapping" i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="611a5-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="611a5-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="611a5-116">Click Save.</span></span>
10. <span data-ttu-id="611a5-117">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="611a5-117">Click Designer.</span></span>
11. <span data-ttu-id="611a5-118">Välj "Dynamics 365 for Operations\Table" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="611a5-119">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="611a5-119">Click Add root.</span></span>
13. <span data-ttu-id="611a5-120">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="611a5-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="611a5-121">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="611a5-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="611a5-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="611a5-122">Click OK.</span></span>
16. <span data-ttu-id="611a5-123">Välj "Functions\Financial dimensions details" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="611a5-124">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="611a5-124">Click Add root.</span></span>
    * <span data-ttu-id="611a5-125">Datakällan anger hur omfånget av ekonomiska dimensioner ska definieras för alla rapporter som ska använda den här modellen som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="611a5-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="611a5-126">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="611a5-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="611a5-127">Välj Yes i fältet Ask for dimensions.</span><span class="sxs-lookup"><span data-stu-id="611a5-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="611a5-128">Välj Yes om du vill tillåta användaren att välja dimensioner vid körning på användardialogformuläret.</span><span class="sxs-lookup"><span data-stu-id="611a5-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="611a5-129">Om inställt på No kommer ekonomiska dimensioner för den aktuella instansen att användas som standard.</span><span class="sxs-lookup"><span data-stu-id="611a5-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="611a5-130">Välj "Legal entity" i fältet för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="611a5-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="611a5-131">Markera All om du vill tillåta användaren att välja önskedimensioner för den aktuella instansen i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="611a5-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="611a5-132">Markera Legal entity om du vill tillåta användaren att välja dimensioner för företaget i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="611a5-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="611a5-133">Välj Dimension för att tillåta användaren att välja dimensioner med hjälp av en enda dimensionsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="611a5-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="611a5-134">Välj Yes i fältet Ask for main account.</span><span class="sxs-lookup"><span data-stu-id="611a5-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="611a5-135">Ange "Ask for main account" som Yes om du vill låta användare välja huvudkontot som en del i listan över dimensioner.</span><span class="sxs-lookup"><span data-stu-id="611a5-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="611a5-136">Om No kommer huvudkontot inte att inkluderas i listan över dimensioner, och alternativet "Is main account mandatory" aktiveras.</span><span class="sxs-lookup"><span data-stu-id="611a5-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="611a5-137">Om ”Is main account mandatory" anges som Yes, inkludera då huvudkontot i dimensionslistan oavsett användarens urval.</span><span class="sxs-lookup"><span data-stu-id="611a5-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="611a5-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="611a5-138">Click OK.</span></span>
23. <span data-ttu-id="611a5-139">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="611a5-140">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="611a5-140">Click Add root.</span></span>
25. <span data-ttu-id="611a5-141">Välj "LedgerJournal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="611a5-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="611a5-142">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="611a5-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="611a5-143">Ange "LedgerJournalTable" i tabellfältet.</span><span class="sxs-lookup"><span data-stu-id="611a5-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="611a5-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="611a5-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="611a5-145">Mappa datamodellelement till tillagda datakällor</span><span class="sxs-lookup"><span data-stu-id="611a5-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="611a5-146">Expandera "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="611a5-147">Expandera "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="611a5-148">Expandera "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="611a5-149">Expandera "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="611a5-150">Expandera "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="611a5-151">Expandera "LedgerJournal\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="611a5-152">Expandera "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="611a5-153">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="611a5-154">Välj "Journal\Transaction\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="611a5-155">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-155">Click Bind.</span></span>
11. <span data-ttu-id="611a5-156">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="611a5-157">Notera att för alla referenser till ekonomiska dimensioner, inställda till exempelvis LedgerDimension, finns en motsvarande datakällartikel (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="611a5-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="611a5-158">Denna datakällaartikel erbjuder de ekonomiska dimensionerna för denna dimensionsuppsättning som postens lista.</span><span class="sxs-lookup"><span data-stu-id="611a5-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="611a5-159">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="611a5-160">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="611a5-161">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="611a5-162">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="611a5-163">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="611a5-164">Välj "Journal\Transaction\Dimensions data\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="611a5-165">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-165">Click Bind.</span></span>
19. <span data-ttu-id="611a5-166">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="611a5-167">Välj "Journal\Transaction\Dimensions data\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="611a5-168">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-168">Click Bind.</span></span>
22. <span data-ttu-id="611a5-169">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="611a5-170">Välj "Journal\Transaction\Dimensions data\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="611a5-171">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-171">Click Bind.</span></span>
25. <span data-ttu-id="611a5-172">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="611a5-173">Välj "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="611a5-174">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-174">Click Bind.</span></span>
28. <span data-ttu-id="611a5-175">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="611a5-176">Välj "Journal\Transaction\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="611a5-177">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-177">Click Bind.</span></span>
31. <span data-ttu-id="611a5-178">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="611a5-179">Välj "Journal\Transaction\Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="611a5-180">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-180">Click Bind.</span></span>
34. <span data-ttu-id="611a5-181">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="611a5-182">Välj "Journal\Transaction\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="611a5-183">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-183">Click Bind.</span></span>
37. <span data-ttu-id="611a5-184">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="611a5-185">Välj "Journal\Transaction\Credit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="611a5-186">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-186">Click Bind.</span></span>
40. <span data-ttu-id="611a5-187">Välj "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="611a5-188">Välj "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="611a5-189">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-189">Click Bind.</span></span>
43. <span data-ttu-id="611a5-190">Välj "LedgerJournal\Journal batch number(JournalNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="611a5-191">Välj "Journal\Batch" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="611a5-192">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-192">Click Bind.</span></span>
46. <span data-ttu-id="611a5-193">Välj "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="611a5-194">Välj "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="611a5-195">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-195">Click Bind.</span></span>
49. <span data-ttu-id="611a5-196">Expandera "Dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="611a5-197">Expandera "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="611a5-198">Expandera "Dimensions\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="611a5-199">Välj "Dimensions\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="611a5-200">Välj "Dimensions setting\Code".</span><span class="sxs-lookup"><span data-stu-id="611a5-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="611a5-201">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-201">Click Bind.</span></span>
55. <span data-ttu-id="611a5-202">Välj "Dimensions\Main account and dimensions\Definition\Report column name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="611a5-203">Välj "Dimensions setting\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="611a5-204">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-204">Click Bind.</span></span>
58. <span data-ttu-id="611a5-205">Välj "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="611a5-206">Välj "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="611a5-207">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="611a5-207">Click Bind.</span></span>
61. <span data-ttu-id="611a5-208">Välj "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="611a5-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="611a5-209">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="611a5-209">Click Edit.</span></span>
63. <span data-ttu-id="611a5-210">I fältet expressionAsStringText anger du "Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="611a5-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="611a5-211">Company.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="611a5-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="611a5-212">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="611a5-212">Click Save.</span></span>
65. <span data-ttu-id="611a5-213">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="611a5-213">Close the page.</span></span>
66. <span data-ttu-id="611a5-214">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="611a5-214">Click Save.</span></span>
67. <span data-ttu-id="611a5-215">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="611a5-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="611a5-216">Slutför denna utkastmodellversion</span><span class="sxs-lookup"><span data-stu-id="611a5-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="611a5-217">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="611a5-217">Close the page.</span></span>
2. <span data-ttu-id="611a5-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="611a5-218">Close the page.</span></span>
3. <span data-ttu-id="611a5-219">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="611a5-219">Click Change status.</span></span>
4. <span data-ttu-id="611a5-220">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="611a5-220">Click Complete.</span></span>
5. <span data-ttu-id="611a5-221">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="611a5-221">Click OK.</span></span>

