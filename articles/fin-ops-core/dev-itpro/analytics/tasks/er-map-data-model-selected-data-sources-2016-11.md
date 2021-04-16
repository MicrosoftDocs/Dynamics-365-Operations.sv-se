---
title: ER mappar datamodeller till utvalda datakällor
description: I det här avsnittet beskrivs hur du mappar en elektronisk rapporteringsmodell (ER) till valda Microsoft Dynamics 365 Finance-datakällor.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0eb7f48a50e32637003c1488d80899a704709068
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751496"
---
# <a name="er-map-data-model-to-selected-data-sources"></a><span data-ttu-id="47b7c-103">ER mappar datamodeller till utvalda datakällor</span><span class="sxs-lookup"><span data-stu-id="47b7c-103">ER Map data model to selected data sources</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47b7c-104">I följande steg beskrivs hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan mappa en datamodell för elektronisk rapportering (ER) till valda datakällor.</span><span class="sxs-lookup"><span data-stu-id="47b7c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can map an Electronic reporting (ER) data model to selected data sources.</span></span> <span data-ttu-id="47b7c-105">Den här modellmappningen kommer senare att användas som en datakälla i en formatkonfiguration som ska användas för att hantera elektroniska betalningsdokument.</span><span class="sxs-lookup"><span data-stu-id="47b7c-105">This model mapping will later be used as a data source in a format configuration that will be used to manage electronic payment documents.</span></span> <span data-ttu-id="47b7c-106">I det här exemplet mappar du en datamodell för exempelföretaget Litware, Inc. till datakällor.</span><span class="sxs-lookup"><span data-stu-id="47b7c-106">In this example, you map a data model for sample company, Litware, Inc. to data sources.</span></span> <span data-ttu-id="47b7c-107">Om du vill slutföra dessa steg måste du först slutföra stegen i proceduren "Välj datakällor för modellmappning".</span><span class="sxs-lookup"><span data-stu-id="47b7c-107">To complete these steps, you must first complete the steps in the "Select data sources for model mapping" procedure.</span></span>


## <a name="open-er-configurations-tree"></a><span data-ttu-id="47b7c-108">Öppna ER-konfigurationsträdet</span><span class="sxs-lookup"><span data-stu-id="47b7c-108">Open ER configurations tree</span></span>
1. <span data-ttu-id="47b7c-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="47b7c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="47b7c-110">Klientkonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="47b7c-110">Click Configurations.</span></span>

## <a name="select-created-model-mapping"></a><span data-ttu-id="47b7c-111">Välj skapad modellmappning</span><span class="sxs-lookup"><span data-stu-id="47b7c-111">Select created model mapping</span></span>
1. <span data-ttu-id="47b7c-112">Välj "Betalningar (förenklad modell)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-112">In the tree, select 'Payments (simplified model)'.</span></span>
    * <span data-ttu-id="47b7c-113">Kontrollera att modellkonfigurationen "Betalningar (förenklad modell") har skapats i förväg.</span><span class="sxs-lookup"><span data-stu-id="47b7c-113">Make sure that the model configuration "Payments (simplified model)" has been created in advance.</span></span> <span data-ttu-id="47b7c-114">Annars avbryter du nu och återvänder när du har slutfört uppgiftsguiden "Skapa en ny konfiguration med datamodellen för den markerade domänen".</span><span class="sxs-lookup"><span data-stu-id="47b7c-114">Otherwise, stop now and return after completion of the task guide 'Create a new configuration with data model of the selected domain'.</span></span>  
2. <span data-ttu-id="47b7c-115">Klicka på Modelldesigner.</span><span class="sxs-lookup"><span data-stu-id="47b7c-115">Click Model designer.</span></span>
3. <span data-ttu-id="47b7c-116">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="47b7c-116">Click Map model to datasource.</span></span>
4. <span data-ttu-id="47b7c-117">Välj posten "CT-mappning".</span><span class="sxs-lookup"><span data-stu-id="47b7c-117">Select the 'CT mapping' record.</span></span>
    * <span data-ttu-id="47b7c-118">CT-mappning</span><span class="sxs-lookup"><span data-stu-id="47b7c-118">CT mapping</span></span>  

## <a name="bind-created-data-sources-to-data-model-elements"></a><span data-ttu-id="47b7c-119">Koppla skapade datakällor till datamodellelement</span><span class="sxs-lookup"><span data-stu-id="47b7c-119">Bind created data sources to data model elements</span></span>
1. <span data-ttu-id="47b7c-120">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="47b7c-120">Click Designer.</span></span>
2. <span data-ttu-id="47b7c-121">Välj "Datum för tid och bearbetning (ProcessingDateTime)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-121">In the tree, select 'Processing date & time(ProcessingDateTime)'.</span></span>
3. <span data-ttu-id="47b7c-122">Välj "Bearbetningsdatum(ProcessingDateTime)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-122">In the tree, select 'Processing date(ProcessingDateTime)'.</span></span>
4. <span data-ttu-id="47b7c-123">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-123">Click Bind.</span></span>
5. <span data-ttu-id="47b7c-124">Välj "Identifiering av betalningsmeddelande(MessageIdentification)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-124">In the tree, select 'Payment message identification(MessageIdentification)'.</span></span>
6. <span data-ttu-id="47b7c-125">Expandera "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-125">In the tree, expand 'Transactions'.</span></span>
7. <span data-ttu-id="47b7c-126">Välj "Transaktioner\Journalbatchnummer(JournalNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-126">In the tree, select 'Transactions\Journal batch number(JournalNum)'.</span></span>
8. <span data-ttu-id="47b7c-127">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-127">Click Bind.</span></span>
9. <span data-ttu-id="47b7c-128">Välj "Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-128">In the tree, select 'Payments'.</span></span>
10. <span data-ttu-id="47b7c-129">Välj "Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-129">In the tree, select 'Transactions'.</span></span>
11. <span data-ttu-id="47b7c-130">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-130">Click Bind.</span></span>
12. <span data-ttu-id="47b7c-131">Expandera "Betalningar= Transaktioner" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-131">In the tree, expand 'Payments= Transactions'.</span></span>
13. <span data-ttu-id="47b7c-132">Expandera "Betalningar= Transaktioner\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-132">In the tree, expand 'Payments= Transactions\Creditor'.</span></span>
14. <span data-ttu-id="47b7c-133">Expandera "Betalningar= Transaktioner\Betalningsmottagare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-133">In the tree, expand 'Payments= Transactions\Creditor\Account'.</span></span>
15. <span data-ttu-id="47b7c-134">Välj "betalningar= Transaktioner\betalningsmottagare\Konto\Valutakod(Valuta)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-134">In the tree, select 'Payments= Transactions\Creditor\Account\Currency code(Currency)'.</span></span>
16. <span data-ttu-id="47b7c-135">Expandera "Transaktioner\vendBankAccountInTransactionCompany()" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-135">In the tree, expand 'Transactions\vendBankAccountInTransactionCompany()'.</span></span>
17. <span data-ttu-id="47b7c-136">Välj "Transaktioner\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-136">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'.</span></span>
18. <span data-ttu-id="47b7c-137">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-137">Click Bind.</span></span>
19. <span data-ttu-id="47b7c-138">Välj "Betalningar= Transaktioner\Betalningsmottagare\Konto\IBAN-kod(IBAN)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-138">In the tree, select 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'.</span></span>
20. <span data-ttu-id="47b7c-139">Välj "Transaktioner\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-139">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.</span></span>
21. <span data-ttu-id="47b7c-140">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-140">Click Bind.</span></span>
22. <span data-ttu-id="47b7c-141">Välj "Betalningar= Transaktioner\Betalningsmottagare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-141">In the tree, select 'Payments= Transactions\Creditor\Account\Number'.</span></span>
23. <span data-ttu-id="47b7c-142">Välj "Transaktioner\vendBankAccountInTransactionCompany()\Bankkontonummer(AccountNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-142">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'.</span></span>
24. <span data-ttu-id="47b7c-143">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-143">Click Bind.</span></span>
25. <span data-ttu-id="47b7c-144">Expandera "Betalningar= Transaktioner\Betalningsmottagare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-144">In the tree, expand 'Payments= Transactions\Creditor\Agent'.</span></span>
26. <span data-ttu-id="47b7c-145">Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-145">In the tree, select 'Payments= Transactions\Creditor\Agent\Name'.</span></span>
27. <span data-ttu-id="47b7c-146">Välj "Transaktioner\vendBankAccountInTransactionCompany()\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-146">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Name'.</span></span>
28. <span data-ttu-id="47b7c-147">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-147">Click Bind.</span></span>
29. <span data-ttu-id="47b7c-148">Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\Organisationsnummer(RoutingNumber)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-148">In the tree, select 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'.</span></span>
30. <span data-ttu-id="47b7c-149">Välj "Transaktioner\vendBankAccountInTransactionCompany()\Organisationsnummer(RegistrationNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-149">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'.</span></span>
31. <span data-ttu-id="47b7c-150">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-150">Click Bind.</span></span>
32. <span data-ttu-id="47b7c-151">Välj "Betalningar= Transaktioner\Betalningsmottagare\Agent\SWIFT-kod(SWIFT)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-151">In the tree, select 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'.</span></span>
33. <span data-ttu-id="47b7c-152">Välj "Transaktioner\vendBankAccountInTransactionCompany()\SWIFT-kod(SWIFTNo)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-152">In the tree, select 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'.</span></span>
34. <span data-ttu-id="47b7c-153">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-153">Click Bind.</span></span>
35. <span data-ttu-id="47b7c-154">Välj "Betalningar= Transaktioner\Betalningsmottagare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-154">In the tree, select 'Payments= Transactions\Creditor\Name'.</span></span>
36. <span data-ttu-id="47b7c-155">Expandera "Transaktioner\findVendTable()" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-155">In the tree, expand 'Transactions\findVendTable()'.</span></span>
37. <span data-ttu-id="47b7c-156">Välj "Transaktioner\hitta leverantörsregister ()\namn ()" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-156">In the tree, select 'Transactions\findVendTable()\name()'.</span></span>
38. <span data-ttu-id="47b7c-157">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-157">Click Bind.</span></span>
39. <span data-ttu-id="47b7c-158">Välj "Betalningar= Transaktioner\Valutakod(Valuta)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-158">In the tree, select 'Payments= Transactions\Currency code(Currency)'.</span></span>
40. <span data-ttu-id="47b7c-159">Expandera "Transaktioner\>Relationer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-159">In the tree, expand 'Transactions\>Relations'.</span></span>
41. <span data-ttu-id="47b7c-160">Expandera ”Transaktioner\>Relationer\Valutatabell(Valuta) i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-160">In the tree, expand 'Transactions\>Relations\Currency table(Currency)'.</span></span>
42. <span data-ttu-id="47b7c-161">Välj transaktioner ”Transaktioner\>Relationer\Valutatabell(Valuta)\Valutakod(CurrencyCodeISO) i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-161">In the tree, select 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'.</span></span>
43. <span data-ttu-id="47b7c-162">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-162">Click Bind.</span></span>
44. <span data-ttu-id="47b7c-163">Expandera "Betalningar= Transaktioner\Betalare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-163">In the tree, expand 'Payments= Transactions\Debtor'.</span></span>
45. <span data-ttu-id="47b7c-164">Expandera "Betalningar= Transaktioner\Betalare\Konto" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-164">In the tree, expand 'Payments= Transactions\Debtor\Account'.</span></span>
46. <span data-ttu-id="47b7c-165">Välj "Betalningar= Transaktioner\Betalare\Konto\Valutakod(Valuta)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-165">In the tree, select 'Payments= Transactions\Debtor\Account\Currency code(Currency)'.</span></span>
47. <span data-ttu-id="47b7c-166">Välj "Bankkonto(BankAccount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-166">In the tree, select 'Bank Account(BankAccount)'.</span></span>
48. <span data-ttu-id="47b7c-167">Expandera "Bankkonto(BankAccount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-167">In the tree, expand 'Bank Account(BankAccount)'.</span></span>
49. <span data-ttu-id="47b7c-168">Välj "Bankkonto(BankAccount)\Valuta(CurrencyCode)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-168">In the tree, select 'Bank Account(BankAccount)\Currency(CurrencyCode)'.</span></span>
50. <span data-ttu-id="47b7c-169">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-169">Click Bind.</span></span>
51. <span data-ttu-id="47b7c-170">Välj "Bankkonto(BankAccount)\IBAN" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-170">In the tree, select 'Bank Account(BankAccount)\IBAN'.</span></span>
52. <span data-ttu-id="47b7c-171">Välj "Betalningar= Transaktioner\Betalare\Konto\IBAN-kod(IBAN)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-171">In the tree, select 'Payments= Transactions\Debtor\Account\IBAN code(IBAN)'.</span></span>
53. <span data-ttu-id="47b7c-172">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-172">Click Bind.</span></span>
54. <span data-ttu-id="47b7c-173">Välj "Betalningar= Transaktioner\Betalare\Konto\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-173">In the tree, select 'Payments= Transactions\Debtor\Account\Number'.</span></span>
55. <span data-ttu-id="47b7c-174">Välj "Bankkonto(BankAccount)\Bankkontonummer(AccountNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-174">In the tree, select 'Bank Account(BankAccount)\Bank account number(AccountNum)'.</span></span>
56. <span data-ttu-id="47b7c-175">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-175">Click Bind.</span></span>
57. <span data-ttu-id="47b7c-176">Expandera "Betalningar= Transaktioner\Betalare\Agent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-176">In the tree, expand 'Payments= Transactions\Debtor\Agent'.</span></span>
58. <span data-ttu-id="47b7c-177">Välj "Betalningar= Transaktioner\Betalare\Agent\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-177">In the tree, select 'Payments= Transactions\Debtor\Agent\Name'.</span></span>
59. <span data-ttu-id="47b7c-178">Välj "Bankkonto(BankAccount)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-178">In the tree, select 'Bank Account(BankAccount)\Name'.</span></span>
60. <span data-ttu-id="47b7c-179">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-179">Click Bind.</span></span>
61. <span data-ttu-id="47b7c-180">Välj "Betalningar= Transaktioner\Betalare\Agent\Organisationsnummer(RoutingNumber)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-180">In the tree, select 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'.</span></span>
62. <span data-ttu-id="47b7c-181">Välj "Bankkonto(BankAccount)\Organisationsnummer(RegistrationNum)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-181">In the tree, select 'Bank Account(BankAccount)\Routing number(RegistrationNum)'.</span></span>
63. <span data-ttu-id="47b7c-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-182">Click Bind.</span></span>
64. <span data-ttu-id="47b7c-183">Välj "Betalningar= Transaktioner\Betalare\Agent\SWIFT-kod(SWIFT)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-183">In the tree, select 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'.</span></span>
65. <span data-ttu-id="47b7c-184">Välj "Bankkonto(BankAccount)\SWIFT-kod(SWIFTNo)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-184">In the tree, select 'Bank Account(BankAccount)\SWIFT code(SWIFTNo)'.</span></span>
66. <span data-ttu-id="47b7c-185">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-185">Click Bind.</span></span>
67. <span data-ttu-id="47b7c-186">Välj "Betalningar= Transaktioner\Betalare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-186">In the tree, select 'Payments= Transactions\Debtor\Name'.</span></span>
68. <span data-ttu-id="47b7c-187">Välj "Företagsinformation(Företag)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-187">In the tree, select 'Company information(Company)'.</span></span>
69. <span data-ttu-id="47b7c-188">Expandera "Företagsinformation(Företag)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-188">In the tree, expand 'Company information(Company)'.</span></span>
70. <span data-ttu-id="47b7c-189">Välj "Företagsinformation(Företag)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-189">In the tree, select 'Company information(Company)\Name'.</span></span>
71. <span data-ttu-id="47b7c-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-190">Click Bind.</span></span>
72. <span data-ttu-id="47b7c-191">Välj "Betalningar= Transaktioner\Beskrivning" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-191">In the tree, select 'Payments= Transactions\Description'.</span></span>
73. <span data-ttu-id="47b7c-192">Välj "Transaktioner\Beskrivning(Txt)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-192">In the tree, select 'Transactions\Description(Txt)'.</span></span>
74. <span data-ttu-id="47b7c-193">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-193">Click Bind.</span></span>
75. <span data-ttu-id="47b7c-194">Välj "Betalningar= Transaktioner\Slutpunkt till slutpunkt-identifieringskod(End2EndID)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-194">In the tree, select 'Payments= Transactions\End to end identification code(End2EndID)'.</span></span>
76. <span data-ttu-id="47b7c-195">Välj Transactions\$EndToEndID i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-195">In the tree, select 'Transactions\$EndToEndID'.</span></span>
77. <span data-ttu-id="47b7c-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-196">Click Bind.</span></span>
78. <span data-ttu-id="47b7c-197">Välj "Betalningar= Transaktioner\Instruerat belopp(InstructedAmount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-197">In the tree, select 'Payments= Transactions\Instructed amount(InstructedAmount)'.</span></span>
79. <span data-ttu-id="47b7c-198">Välj Transactions\$Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-198">In the tree, select 'Transactions\$Amount'.</span></span>
80. <span data-ttu-id="47b7c-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-199">Click Bind.</span></span>
81. <span data-ttu-id="47b7c-200">Välj "Betalningar= Transaktioner\Transaktionsdatum(TransactionDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-200">In the tree, select 'Payments= Transactions\Transaction date(TransactionDate)'.</span></span>
82. <span data-ttu-id="47b7c-201">Välj "Transaktioner\Datum(TransDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="47b7c-201">In the tree, select 'Transactions\Date(TransDate)'.</span></span>
83. <span data-ttu-id="47b7c-202">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="47b7c-202">Click Bind.</span></span>

## <a name="validate-created-mapping"></a><span data-ttu-id="47b7c-203">Validera skapad mappning</span><span class="sxs-lookup"><span data-stu-id="47b7c-203">Validate created mapping</span></span>
1. <span data-ttu-id="47b7c-204">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="47b7c-204">Click Validate.</span></span>
    * <span data-ttu-id="47b7c-205">Bekräfta den nya mappningen för att säkerställa att alla bindningar är korrekta.</span><span class="sxs-lookup"><span data-stu-id="47b7c-205">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="47b7c-206">Klicka på pilen för att Visa eller dölj avsnittet Fellista.</span><span class="sxs-lookup"><span data-stu-id="47b7c-206">Click the arrow to expand or collapse the Error List section.</span></span>
3. <span data-ttu-id="47b7c-207">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="47b7c-207">Click Save.</span></span>
4. <span data-ttu-id="47b7c-208">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="47b7c-208">Close the page.</span></span>
5. <span data-ttu-id="47b7c-209">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="47b7c-209">Close the page.</span></span>
6. <span data-ttu-id="47b7c-210">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="47b7c-210">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a><span data-ttu-id="47b7c-211">Ändra status för den aktuella versionen av modellkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="47b7c-211">Change the status of the current version of model configuration</span></span>
1. <span data-ttu-id="47b7c-212">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="47b7c-212">Click Change status.</span></span>
    * <span data-ttu-id="47b7c-213">Ändra statusen för designad modellkonfiguration från Utkast till Slutfört för att göra den tillgänglig för utformning av betalningsformat.</span><span class="sxs-lookup"><span data-stu-id="47b7c-213">Change the status of designed model configuration – from Draft to Completed to make it available for payment format design.</span></span>  
2. <span data-ttu-id="47b7c-214">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="47b7c-214">Click Complete.</span></span>
    * <span data-ttu-id="47b7c-215">Välj Slutför.</span><span class="sxs-lookup"><span data-stu-id="47b7c-215">Select Complete.</span></span>  
3. <span data-ttu-id="47b7c-216">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="47b7c-216">In the Description field, type a value.</span></span>
    * <span data-ttu-id="47b7c-217">Till exempel "Version 1".</span><span class="sxs-lookup"><span data-stu-id="47b7c-217">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="47b7c-218">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="47b7c-218">Click OK.</span></span>
5. <span data-ttu-id="47b7c-219">Välj den slutförda versionen av den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="47b7c-219">Select the completed version of the current configuration.</span></span>
    * <span data-ttu-id="47b7c-220">Observera att den skapade konfigurationen sparas som slutförd version 1.</span><span class="sxs-lookup"><span data-stu-id="47b7c-220">Note that the created configuration is saved as completed version 1.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]