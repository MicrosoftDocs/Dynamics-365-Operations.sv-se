---
title: Definiera ER-modellmappningar och välj datakällor för dem
description: Detta ämne beskriver hur en Systemadministratör eller Utvecklare för elektronisk rapportering kan välja datakällor för en datamodell för elektronisk rapportering.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d88aaa24d61d6768801a84c81002d7a6ab2f316
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755092"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="a82e6-103">Definiera ER-modellmappningar och välj datakällor för dem</span><span class="sxs-lookup"><span data-stu-id="a82e6-103">Define ER model mappings and select data sources for them</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a82e6-104">I följande steg beskrivs hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan välja datakällor för en datamodell för elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="a82e6-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="a82e6-105">Datakällorna kopplas till enskilda komponenter för den valda datamodellen vid designtidpunkten och datamodellen fylls i med affärsdata vid körning.</span><span class="sxs-lookup"><span data-stu-id="a82e6-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="a82e6-106">I det här exemplet ska du skapa välja datakällor för en befintlig datamodell som har skapats för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först avsluta stegen i proceduren "Skapa en ny datamodell".</span><span class="sxs-lookup"><span data-stu-id="a82e6-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Create a new data model" procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="a82e6-107">Öppna trädet för elektroniska rapporteringskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="a82e6-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="a82e6-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a82e6-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="a82e6-109">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="a82e6-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="a82e6-110">Infoga en ny modellmappning</span><span class="sxs-lookup"><span data-stu-id="a82e6-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="a82e6-111">Välj "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="a82e6-112">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a82e6-112">Click Designer.</span></span>
3. <span data-ttu-id="a82e6-113">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="a82e6-114">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a82e6-114">Click New.</span></span>
    * <span data-ttu-id="a82e6-115">Då skapas en ny post som ska mappa datamodellen till datakällorna.</span><span class="sxs-lookup"><span data-stu-id="a82e6-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="a82e6-116">I det här exemplet mappar du datamodellen till datakällorna för önskad betalningstyp: kreditöverföring.</span><span class="sxs-lookup"><span data-stu-id="a82e6-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="a82e6-117">Det går att utforma fler än en mappning för en särskild datamodell.</span><span class="sxs-lookup"><span data-stu-id="a82e6-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="a82e6-118">Du kan till exempel skapa en mappning för olika typer av betalningar, till exempel för debet- eller kreditöverföringar.</span><span class="sxs-lookup"><span data-stu-id="a82e6-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="a82e6-119">I det här exemplet skapar du en mappning för kreditöverföringar.</span><span class="sxs-lookup"><span data-stu-id="a82e6-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="a82e6-120">Skriv "CT-mappning" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="a82e6-121">CT-mappning</span><span class="sxs-lookup"><span data-stu-id="a82e6-121">CT mapping</span></span>  
6. <span data-ttu-id="a82e6-122">Skriv "Betalningsmodell som mappar CT" i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a82e6-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="a82e6-123">Betalningsmodell som mappar CT</span><span class="sxs-lookup"><span data-stu-id="a82e6-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="a82e6-124">I fältet Definition anger du "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="a82e6-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="a82e6-125">CustomerCreditTransferInitiation</span><span class="sxs-lookup"><span data-stu-id="a82e6-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="a82e6-126">ResolveChanges the Definition.</span><span class="sxs-lookup"><span data-stu-id="a82e6-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="a82e6-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a82e6-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="a82e6-128">Definiera obligatoriska datakällor för den aktuella modellmappningen</span><span class="sxs-lookup"><span data-stu-id="a82e6-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="a82e6-129">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a82e6-129">Click Designer.</span></span>
2. <span data-ttu-id="a82e6-130">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="a82e6-131">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="a82e6-131">Click Add root.</span></span>
    * <span data-ttu-id="a82e6-132">Ange den här datakällan för att komma åt betalningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="a82e6-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="a82e6-133">Skriv "Transaktioner" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="a82e6-134">Transaktioner</span><span class="sxs-lookup"><span data-stu-id="a82e6-134">Transactions</span></span>  
5. <span data-ttu-id="a82e6-135">Ange "Transaktioner" i fältet Etikett.</span><span class="sxs-lookup"><span data-stu-id="a82e6-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="a82e6-136">Transaktioner</span><span class="sxs-lookup"><span data-stu-id="a82e6-136">Transactions</span></span>  
6. <span data-ttu-id="a82e6-137">Ange "Redovisningsjournalrader" i fältet Hjälp.</span><span class="sxs-lookup"><span data-stu-id="a82e6-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="a82e6-138">Redovisningsjournalrader</span><span class="sxs-lookup"><span data-stu-id="a82e6-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="a82e6-139">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="a82e6-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a82e6-140">Välj Ja.</span><span class="sxs-lookup"><span data-stu-id="a82e6-140">Select Yes.</span></span>  
8. <span data-ttu-id="a82e6-141">Skriv "LedgerJournalTrans" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="a82e6-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="a82e6-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="a82e6-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="a82e6-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-143">Click OK.</span></span>
    * <span data-ttu-id="a82e6-144">Välj tabellen LedgerJournalTrans som en datakälla för den aktuella datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="a82e6-145">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="a82e6-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a82e6-146">Click Add.</span></span>
    * <span data-ttu-id="a82e6-147">Klicka på Lägg till för att lägga till ett nytt beräknat fält.</span><span class="sxs-lookup"><span data-stu-id="a82e6-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="a82e6-148">Skriv "$EndToEndID" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="a82e6-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="a82e6-149">$EndToEndID</span></span>  
13. <span data-ttu-id="a82e6-150">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="a82e6-150">Click Edit formula.</span></span>
14. <span data-ttu-id="a82e6-151">Välj "Sträng\SAMMANFOGA" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="a82e6-152">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a82e6-152">Click Add function.</span></span>
16. <span data-ttu-id="a82e6-153">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="a82e6-154">Välj "Transaktioner\Verifikation" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="a82e6-155">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-155">Click Add data source.</span></span>
19. <span data-ttu-id="a82e6-156">I formelfältet anger du "CONCATENATE(Transactions.Voucher, "-", ".</span><span class="sxs-lookup"><span data-stu-id="a82e6-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="a82e6-157">Skriv [ , "-", ] i slutet av formeln.</span><span class="sxs-lookup"><span data-stu-id="a82e6-157">Type [ , "-", ] at the end of the formula.</span></span>  
20. <span data-ttu-id="a82e6-158">Välj "Sträng\TEXT" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="a82e6-159">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a82e6-159">Click Add function.</span></span>
22. <span data-ttu-id="a82e6-160">Välj "Transaktioner\Post-ID(RecId)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="a82e6-161">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-161">Click Add data source.</span></span>
24. <span data-ttu-id="a82e6-162">I formelfältet anger du "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".</span><span class="sxs-lookup"><span data-stu-id="a82e6-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="a82e6-163">Skriv [))] i slutet av formeln.</span><span class="sxs-lookup"><span data-stu-id="a82e6-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="a82e6-164">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a82e6-164">Click Save.</span></span>
    * <span data-ttu-id="a82e6-165">Kontrollera att inga fel har upptäckts för den skapade formeln.</span><span class="sxs-lookup"><span data-stu-id="a82e6-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="a82e6-166">Mer information finns i fliken FEL under formelredigeringskontrollen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="a82e6-167">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-167">Close the page.</span></span>
27. <span data-ttu-id="a82e6-168">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-168">Click OK.</span></span>
    * <span data-ttu-id="a82e6-169">Lägga till det beräknade fält till den här datakällan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="a82e6-170">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a82e6-170">Click Add.</span></span>
    * <span data-ttu-id="a82e6-171">Klicka på Lägg till för att lägga till ett nytt beräknat fält.</span><span class="sxs-lookup"><span data-stu-id="a82e6-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="a82e6-172">Skriv "$Amount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="a82e6-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="a82e6-173">$Amount</span></span>  
30. <span data-ttu-id="a82e6-174">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="a82e6-174">Click Edit formula.</span></span>
31. <span data-ttu-id="a82e6-175">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="a82e6-176">Välj "Transaktioner\Debet(AmountCurDebit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="a82e6-177">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-177">Click Add data source.</span></span>
34. <span data-ttu-id="a82e6-178">I formelfältet anger du "Transactions.AmountCurDebit - ".</span><span class="sxs-lookup"><span data-stu-id="a82e6-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="a82e6-179">Skriv[ - ] i slutet av formeln.</span><span class="sxs-lookup"><span data-stu-id="a82e6-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="a82e6-180">Välj "Transaktioner\Kredit(AmountCurCredit)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="a82e6-181">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-181">Click Add data source.</span></span>
37. <span data-ttu-id="a82e6-182">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a82e6-182">Click Save.</span></span>
38. <span data-ttu-id="a82e6-183">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-183">Close the page.</span></span>
39. <span data-ttu-id="a82e6-184">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-184">Click OK.</span></span>
    * <span data-ttu-id="a82e6-185">Då läggs fältet Beräknat $Amount till den valda datakällan för den aktuella datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="a82e6-186">Välj Transactions\$Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="a82e6-187">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="a82e6-188">Expandera eller komprimera Transactions\$Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="a82e6-189">Expandera eller komprimera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="a82e6-190">Välj "Dynamics 365 for Operations\Table records" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="a82e6-191">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="a82e6-191">Click Add root.</span></span>
    * <span data-ttu-id="a82e6-192">Ange den här datakällan för att komma åt företagets bankkontodetaljer.</span><span class="sxs-lookup"><span data-stu-id="a82e6-192">Enter this data source to access the company's bank account details.</span></span>  
46. <span data-ttu-id="a82e6-193">Skriv "BankAccount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="a82e6-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="a82e6-194">BankAccount</span></span>  
47. <span data-ttu-id="a82e6-195">Ange "Bankkonto" i fältet Etikett.</span><span class="sxs-lookup"><span data-stu-id="a82e6-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="a82e6-196">Bankkonto</span><span class="sxs-lookup"><span data-stu-id="a82e6-196">Bank Account</span></span>  
48. <span data-ttu-id="a82e6-197">Ange "Bankkonto" i fältet Hjälp.</span><span class="sxs-lookup"><span data-stu-id="a82e6-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="a82e6-198">Bankkonto</span><span class="sxs-lookup"><span data-stu-id="a82e6-198">Bank Account</span></span>  
49. <span data-ttu-id="a82e6-199">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="a82e6-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a82e6-200">Välj Ja.</span><span class="sxs-lookup"><span data-stu-id="a82e6-200">Select Yes.</span></span>  
50. <span data-ttu-id="a82e6-201">Skriv "BankAccountTable" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="a82e6-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="a82e6-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="a82e6-202">BankAccountTable</span></span>  
51. <span data-ttu-id="a82e6-203">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-203">Click OK.</span></span>
    * <span data-ttu-id="a82e6-204">Välj tabellen BankAccountTable som en datakälla för den aktuella datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="a82e6-205">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="a82e6-205">Click Add root.</span></span>
    * <span data-ttu-id="a82e6-206">Ange den här datakällan för att komma åt företagets förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="a82e6-206">Enter this data source to access the company's requisites.</span></span>  
53. <span data-ttu-id="a82e6-207">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="a82e6-208">Företag</span><span class="sxs-lookup"><span data-stu-id="a82e6-208">Company</span></span>  
54. <span data-ttu-id="a82e6-209">Skriv ett värde i fältet Etikett.</span><span class="sxs-lookup"><span data-stu-id="a82e6-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="a82e6-210">Företagsupplysningar</span><span class="sxs-lookup"><span data-stu-id="a82e6-210">Company information</span></span>  
55. <span data-ttu-id="a82e6-211">Ange "Företagsinformation" i fältet Hjälp.</span><span class="sxs-lookup"><span data-stu-id="a82e6-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="a82e6-212">Företagsupplysningar</span><span class="sxs-lookup"><span data-stu-id="a82e6-212">Company information</span></span>  
56. <span data-ttu-id="a82e6-213">Välj Ja i fältet Fråga efter fråga.</span><span class="sxs-lookup"><span data-stu-id="a82e6-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="a82e6-214">Välj Ja.</span><span class="sxs-lookup"><span data-stu-id="a82e6-214">Select Yes.</span></span>  
57. <span data-ttu-id="a82e6-215">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="a82e6-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="a82e6-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="a82e6-216">CompanyInfo</span></span>  
58. <span data-ttu-id="a82e6-217">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-217">Click OK.</span></span>
    * <span data-ttu-id="a82e6-218">Välj tabellen CompanyInfo som en datakälla för den aktuella datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="a82e6-219">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="a82e6-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="a82e6-220">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="a82e6-220">Click Add root.</span></span>
    * <span data-ttu-id="a82e6-221">Infoga ett beräknat fält som en ny datakälla.</span><span class="sxs-lookup"><span data-stu-id="a82e6-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="a82e6-222">Skriv "ProcessingDateTime" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a82e6-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="a82e6-223">ProcessingDateTime</span><span class="sxs-lookup"><span data-stu-id="a82e6-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="a82e6-224">Ange "Datum och tid för bearbetning" i fältet Etikett.</span><span class="sxs-lookup"><span data-stu-id="a82e6-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="a82e6-225">Bearbetar datum och tid</span><span class="sxs-lookup"><span data-stu-id="a82e6-225">Processing date & time</span></span>  
63. <span data-ttu-id="a82e6-226">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="a82e6-226">Click Edit formula.</span></span>
64. <span data-ttu-id="a82e6-227">I trädet väljer du "Date/time\SESSIONNOW".</span><span class="sxs-lookup"><span data-stu-id="a82e6-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="a82e6-228">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="a82e6-228">Click Add function.</span></span>
66. <span data-ttu-id="a82e6-229">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a82e6-229">Click Save.</span></span>
67. <span data-ttu-id="a82e6-230">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-230">Close the page.</span></span>
68. <span data-ttu-id="a82e6-231">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a82e6-231">Click OK.</span></span>
    * <span data-ttu-id="a82e6-232">Lägg till fältet Beräknat ProcessingDateTime som en datakälla för den aktuella datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a82e6-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="a82e6-233">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a82e6-233">Click Save.</span></span>
70. <span data-ttu-id="a82e6-234">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-234">Close the page.</span></span>
71. <span data-ttu-id="a82e6-235">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-235">Close the page.</span></span>
72. <span data-ttu-id="a82e6-236">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a82e6-236">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]