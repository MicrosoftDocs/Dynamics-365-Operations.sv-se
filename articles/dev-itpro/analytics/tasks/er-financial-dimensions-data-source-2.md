--- 
title: "Mappa modeller som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
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
ms.openlocfilehash: a3eafa7b66dcc0c2481d7eeaf98bed7f58e4be33
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="map-models--to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="41f1f-103">Mappa modeller som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="41f1f-103">Map models  to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="41f1f-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.</span><span class="sxs-lookup"><span data-stu-id="41f1f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="41f1f-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="41f1f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="41f1f-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 1: Design data model”.</span><span class="sxs-lookup"><span data-stu-id="41f1f-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="41f1f-107">Lägg till erforderliga datakällor till modellmappningen</span><span class="sxs-lookup"><span data-stu-id="41f1f-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="41f1f-108">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="41f1f-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="41f1f-109">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="41f1f-110">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="41f1f-110">Click Designer.</span></span>
4. <span data-ttu-id="41f1f-111">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="41f1f-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="41f1f-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="41f1f-112">Click New.</span></span>
6. <span data-ttu-id="41f1f-113">Välj Entry i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="41f1f-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="41f1f-114">Ange "Dimensions data mapping" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="41f1f-115">Ange "Dimensions data mapping" i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="41f1f-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="41f1f-116">Click Save.</span></span>
10. <span data-ttu-id="41f1f-117">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="41f1f-117">Click Designer.</span></span>
11. <span data-ttu-id="41f1f-118">Välj Dynamics 365 for Operations\Table i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="41f1f-119">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="41f1f-119">Click Add root.</span></span>
13. <span data-ttu-id="41f1f-120">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="41f1f-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="41f1f-121">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="41f1f-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="41f1f-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="41f1f-122">Click OK.</span></span>
16. <span data-ttu-id="41f1f-123">Välj "Functions\Financial dimensions details" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="41f1f-124">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="41f1f-124">Click Add root.</span></span>
    * <span data-ttu-id="41f1f-125">Datakällan anger hur omfånget av ekonomiska dimensioner ska definieras för alla rapporter som ska använda den här modellen som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="41f1f-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="41f1f-126">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="41f1f-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="41f1f-127">Välj Yes i fältet Ask for dimensions.</span><span class="sxs-lookup"><span data-stu-id="41f1f-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="41f1f-128">Välj Yes om du vill tillåta användaren att välja dimensioner vid körning på användardialogformuläret.</span><span class="sxs-lookup"><span data-stu-id="41f1f-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="41f1f-129">Om inställt på No kommer ekonomiska dimensioner för den aktuella instansen att användas som standard.</span><span class="sxs-lookup"><span data-stu-id="41f1f-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="41f1f-130">Välj "Legal entity" i fältet för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="41f1f-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="41f1f-131">Markera All om du vill tillåta användaren att välja önskedimensioner för den aktuella instansen i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="41f1f-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="41f1f-132">Markera Legal entity om du vill tillåta användaren att välja dimensioner för företaget i fältet Lookup.</span><span class="sxs-lookup"><span data-stu-id="41f1f-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="41f1f-133">Välj Dimension för att tillåta användaren att välja dimensioner med hjälp av en enda dimensionsuppsättning.</span><span class="sxs-lookup"><span data-stu-id="41f1f-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="41f1f-134">Välj Yes i fältet Ask for main account.</span><span class="sxs-lookup"><span data-stu-id="41f1f-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="41f1f-135">Ange "Ask for main account" som Yes om du vill låta användare välja huvudkontot som en del i listan över dimensioner.</span><span class="sxs-lookup"><span data-stu-id="41f1f-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="41f1f-136">Om No kommer huvudkontot inte att inkluderas i listan över dimensioner, och alternativet "Is main account mandatory" aktiveras.</span><span class="sxs-lookup"><span data-stu-id="41f1f-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="41f1f-137">Om ”Is main account mandatory" anges som Yes, inkludera då huvudkontot i dimensionslistan oavsett användarens urval.</span><span class="sxs-lookup"><span data-stu-id="41f1f-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="41f1f-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="41f1f-138">Click OK.</span></span>
23. <span data-ttu-id="41f1f-139">Välj Dynamics 365 for Dynamics 365 for Operations\Table records i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="41f1f-140">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="41f1f-140">Click Add root.</span></span>
25. <span data-ttu-id="41f1f-141">Välj "LedgerJournal" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="41f1f-142">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="41f1f-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="41f1f-143">Ange "LedgerJournalTable" i tabellfältet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="41f1f-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="41f1f-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="41f1f-145">Mappa datamodellelement till tillagda datakällor</span><span class="sxs-lookup"><span data-stu-id="41f1f-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="41f1f-146">Expandera "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="41f1f-147">Expandera "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="41f1f-148">Expandera "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="41f1f-149">Expandera "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="41f1f-150">Expandera "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="41f1f-151">Expandera "LedgerJournal\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="41f1f-152">Expandera "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="41f1f-153">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="41f1f-154">Välj "Journal\Transaction\Voucher" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="41f1f-155">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-155">Click Bind.</span></span>
11. <span data-ttu-id="41f1f-156">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="41f1f-157">Notera att för alla referenser till ekonomiska dimensioner, inställda till exempelvis LedgerDimension, finns en motsvarande datakällartikel (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="41f1f-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="41f1f-158">Denna datakällaartikel erbjuder de ekonomiska dimensionerna för denna dimensionsuppsättning som postens lista.</span><span class="sxs-lookup"><span data-stu-id="41f1f-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="41f1f-159">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="41f1f-160">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="41f1f-161">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="41f1f-162">Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="41f1f-163">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="41f1f-164">Välj "Journal\Transaction\Dimensions data\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="41f1f-165">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-165">Click Bind.</span></span>
19. <span data-ttu-id="41f1f-166">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="41f1f-167">Välj "Journal\Transaction\Dimensions data\Description" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="41f1f-168">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-168">Click Bind.</span></span>
22. <span data-ttu-id="41f1f-169">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="41f1f-170">Välj "Journal\Transaction\Dimensions data\Code" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="41f1f-171">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-171">Click Bind.</span></span>
25. <span data-ttu-id="41f1f-172">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="41f1f-173">Välj "Journal\Transaction\Dimensions data" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="41f1f-174">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-174">Click Bind.</span></span>
28. <span data-ttu-id="41f1f-175">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="41f1f-176">Välj "Journal\Transaction\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="41f1f-177">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-177">Click Bind.</span></span>
31. <span data-ttu-id="41f1f-178">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="41f1f-179">Välj "Journal\Transaction\Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="41f1f-180">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-180">Click Bind.</span></span>
34. <span data-ttu-id="41f1f-181">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="41f1f-182">Välj "Journal\Transaction\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="41f1f-183">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-183">Click Bind.</span></span>
37. <span data-ttu-id="41f1f-184">Välj "LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="41f1f-185">Välj "Journal\Transaction\Credit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="41f1f-186">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-186">Click Bind.</span></span>
40. <span data-ttu-id="41f1f-187">Välj "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="41f1f-188">Välj "Journal\Transaction" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="41f1f-189">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-189">Click Bind.</span></span>
43. <span data-ttu-id="41f1f-190">Välj "LedgerJournal\Journal batch number(JournalNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="41f1f-191">Välj "Journal\Batch" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="41f1f-192">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-192">Click Bind.</span></span>
46. <span data-ttu-id="41f1f-193">Välj "LedgerJournal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="41f1f-194">Välj "Journal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="41f1f-195">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-195">Click Bind.</span></span>
49. <span data-ttu-id="41f1f-196">Expandera "Dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="41f1f-197">Expandera "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="41f1f-198">Expandera "Dimensions\Main account and dimensions\Definition" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="41f1f-199">Välj "Dimensions\Main account and dimensions\Definition\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="41f1f-200">Välj "Dimensions setting\Code".</span><span class="sxs-lookup"><span data-stu-id="41f1f-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="41f1f-201">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-201">Click Bind.</span></span>
55. <span data-ttu-id="41f1f-202">Välj "Dimensions\Main account and dimensions\Definition\Report column name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="41f1f-203">Välj "Dimensions setting\Name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="41f1f-204">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-204">Click Bind.</span></span>
58. <span data-ttu-id="41f1f-205">Välj "Dimensions\Main account and dimensions" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="41f1f-206">Välj "Dimensions setting" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="41f1f-207">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="41f1f-207">Click Bind.</span></span>
61. <span data-ttu-id="41f1f-208">Välj "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="41f1f-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="41f1f-209">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="41f1f-209">Click Edit.</span></span>
63. <span data-ttu-id="41f1f-210">I fältet expressionAsStringText anger du "Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="41f1f-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="41f1f-211">Company.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="41f1f-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="41f1f-212">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="41f1f-212">Click Save.</span></span>
65. <span data-ttu-id="41f1f-213">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="41f1f-213">Close the page.</span></span>
66. <span data-ttu-id="41f1f-214">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="41f1f-214">Click Save.</span></span>
67. <span data-ttu-id="41f1f-215">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="41f1f-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="41f1f-216">Slutför denna utkastmodellversion</span><span class="sxs-lookup"><span data-stu-id="41f1f-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="41f1f-217">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="41f1f-217">Close the page.</span></span>
2. <span data-ttu-id="41f1f-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="41f1f-218">Close the page.</span></span>
3. <span data-ttu-id="41f1f-219">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="41f1f-219">Click Change status.</span></span>
4. <span data-ttu-id="41f1f-220">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="41f1f-220">Click Complete.</span></span>
5. <span data-ttu-id="41f1f-221">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="41f1f-221">Click OK.</span></span>


