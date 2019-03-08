---
title: ER Skapa en konfiguration för rapportgenerering i OPENXML-format (november 2016)
description: I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att skapa elektroniska betalningsdokument i OPENXML-format.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "326663"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a><span data-ttu-id="72c09-103">ER Skapa en konfiguration för rapportgenerering i OPENXML-format (november 2016)</span><span class="sxs-lookup"><span data-stu-id="72c09-103">ER Design a configuration for generating reports in OPENXML format (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="72c09-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att skapa elektroniska betalningsdokument i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="72c09-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="72c09-105">Denna konfiguration kommer att användas för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="72c09-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="72c09-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i GBSI-företag.</span><span class="sxs-lookup"><span data-stu-id="72c09-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="72c09-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="72c09-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="72c09-108">Du måste även ha en Excel-fil som ska importeras, när du skapar mallen.</span><span class="sxs-lookup"><span data-stu-id="72c09-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="72c09-109">Den här filen kan nås från [Mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="72c09-109">This file can be accessed from the [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="72c09-110">Överför konfigurationen för betalningdatamodellen</span><span class="sxs-lookup"><span data-stu-id="72c09-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="72c09-111">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="72c09-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="72c09-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="72c09-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="72c09-113">Välj konfigurationsleverantören för exempelföretaget "Litware, Inc." Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="72c09-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="72c09-114">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="72c09-114">Click Set active.</span></span>
4. <span data-ttu-id="72c09-115">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="72c09-115">Click Repositories.</span></span>
    * <span data-ttu-id="72c09-116">Välj en databas för resurstypen Verksamhetsresurs, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="72c09-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="72c09-117">Om detta är tillgängligt hoppar du över stegen om att skapa en ny databas.</span><span class="sxs-lookup"><span data-stu-id="72c09-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="72c09-118">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="72c09-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="72c09-119">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="72c09-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="72c09-120">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="72c09-120">Click Create repository.</span></span>
8. <span data-ttu-id="72c09-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-121">Click OK.</span></span>
9. <span data-ttu-id="72c09-122">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="72c09-122">Click Open.</span></span>
10. <span data-ttu-id="72c09-123">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="72c09-124">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="72c09-124">Click Import.</span></span>
    * <span data-ttu-id="72c09-125">Importera den här datamodell.</span><span class="sxs-lookup"><span data-stu-id="72c09-125">Import this data model.</span></span> <span data-ttu-id="72c09-126">Den används som en datakälla i en ny formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="72c09-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="72c09-127">Hoppa över detta steg om den här konfigurationen redan har importerats.</span><span class="sxs-lookup"><span data-stu-id="72c09-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="72c09-128">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="72c09-128">Click Yes.</span></span>
13. <span data-ttu-id="72c09-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-129">Close the page.</span></span>
14. <span data-ttu-id="72c09-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="72c09-131">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="72c09-131">Create a new format configuration</span></span>
1. <span data-ttu-id="72c09-132">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="72c09-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="72c09-133">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="72c09-134">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="72c09-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="72c09-135">Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="72c09-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="72c09-136">Skapa ett format som baseras på datamodellen PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="72c09-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="72c09-137">Skriv "Rapport över exempelkalkylblad" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72c09-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="72c09-138">Rapport över exempelkalkylblad</span><span class="sxs-lookup"><span data-stu-id="72c09-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="72c09-139">Skriv in "Rapport över exempelkalkylblad för leverantörer"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="72c09-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="72c09-140">Rapport över kalkylblad prov för leverantörers betalningar.</span><span class="sxs-lookup"><span data-stu-id="72c09-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="72c09-141">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="72c09-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="72c09-142">Välj definitionen "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="72c09-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="72c09-143">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="72c09-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="72c09-144">Designa ett nytt dokument i OPENXML-kalkylbladformat</span><span class="sxs-lookup"><span data-stu-id="72c09-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="72c09-145">Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="72c09-146">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="72c09-146">Click Designer.</span></span>
3. <span data-ttu-id="72c09-147">Klicka på Importera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="72c09-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="72c09-148">Klicka på Importera från Excel.</span><span class="sxs-lookup"><span data-stu-id="72c09-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="72c09-149">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="72c09-149">Click Attachments.</span></span>
    * <span data-ttu-id="72c09-150">Koppla det befintliga Excel-dokumentet som en mall.</span><span class="sxs-lookup"><span data-stu-id="72c09-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="72c09-151">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="72c09-151">Click New.</span></span>
7. <span data-ttu-id="72c09-152">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="72c09-152">Click File.</span></span>
    * <span data-ttu-id="72c09-153">Peka på den befintliga Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="72c09-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="72c09-154">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-154">Close the page.</span></span>
9. <span data-ttu-id="72c09-155">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="72c09-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="72c09-156">Välj den bifogade Excel-filen som ska användas som en mall.</span><span class="sxs-lookup"><span data-stu-id="72c09-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="72c09-157">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-157">Click OK.</span></span>
    * <span data-ttu-id="72c09-158">Observera att ER-formatkomponenter har skapats i designformatet baserat på strukturen i det refererande MS Excel-dokumentet (namngivna intervall).</span><span class="sxs-lookup"><span data-stu-id="72c09-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="72c09-159">Skapa en ny datakälla för att beräkna summor per valutakoder</span><span class="sxs-lookup"><span data-stu-id="72c09-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="72c09-160">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="72c09-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="72c09-161">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="72c09-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="72c09-162">Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="72c09-163">Ange "PaymentByCurrency" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72c09-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="72c09-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="72c09-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="72c09-165">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="72c09-165">Click Edit group by.</span></span>
6. <span data-ttu-id="72c09-166">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="72c09-167">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="72c09-168">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="72c09-168">Click Add field to.</span></span>
9. <span data-ttu-id="72c09-169">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="72c09-169">Click What to group.</span></span>
10. <span data-ttu-id="72c09-170">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="72c09-171">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="72c09-172">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="72c09-172">Click Add field to.</span></span>
13. <span data-ttu-id="72c09-173">Klicka på Grupperade fält.</span><span class="sxs-lookup"><span data-stu-id="72c09-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="72c09-174">Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="72c09-175">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="72c09-175">Click Add field to.</span></span>
16. <span data-ttu-id="72c09-176">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="72c09-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="72c09-177">Markera ett alternativ i fältet Metod.</span><span class="sxs-lookup"><span data-stu-id="72c09-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="72c09-178">Välj den sammansatta funktionen SUMMA.</span><span class="sxs-lookup"><span data-stu-id="72c09-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="72c09-179">Skriv "TotalInstructuredAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72c09-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="72c09-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="72c09-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="72c09-181">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72c09-181">Click Save.</span></span>
20. <span data-ttu-id="72c09-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-182">Close the page.</span></span>
21. <span data-ttu-id="72c09-183">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="72c09-184">Mappa formatkomponenter till datakällor</span><span class="sxs-lookup"><span data-stu-id="72c09-184">Map format components to data sources</span></span>
1. <span data-ttu-id="72c09-185">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="72c09-186">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="72c09-187">Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="72c09-188">Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="72c09-189">Expandera "Excel\ReportHeader" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="72c09-190">Välj "Excel\ReportHeader\CompanyName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="72c09-191">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-191">Click Bind.</span></span>
8. <span data-ttu-id="72c09-192">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="72c09-193">Expandera "modell\Betalningar\Betalningsmottagare\Identifiering" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="72c09-194">Välj "modell\Betalningar\Betalningsmottagare\Identifiering\Käll-ID(SourceID)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="72c09-195">Expandera "Excel\PaymLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="72c09-196">Välj "Excel\PaymLines\VendAccountName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="72c09-197">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-197">Click Bind.</span></span>
14. <span data-ttu-id="72c09-198">Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="72c09-199">Välj "Excel\PaymLines\VendName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="72c09-200">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-200">Click Bind.</span></span>
17. <span data-ttu-id="72c09-201">Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="72c09-202">Välj "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="72c09-203">Välj "Excel\PaymLines\Bank" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="72c09-204">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-204">Click Bind.</span></span>
21. <span data-ttu-id="72c09-205">Välj "modell\Betalningar\Betalningsmottagaragent\CreditorAgent)\Clearingnummer(RoutingNumber)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="72c09-206">Välj "Excel\PaymLines\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="72c09-207">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-207">Click Bind.</span></span>
24. <span data-ttu-id="72c09-208">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="72c09-209">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="72c09-210">Välj "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="72c09-211">Välj "Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="72c09-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="72c09-212">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-212">Click Bind.</span></span>
29. <span data-ttu-id="72c09-213">Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="72c09-214">Välj "Excel\PaymLines\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="72c09-215">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-215">Click Bind.</span></span>
32. <span data-ttu-id="72c09-216">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="72c09-217">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="72c09-218">Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="72c09-219">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="72c09-220">Välj "Excel\PaymLines\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="72c09-221">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-221">Click Bind.</span></span>
38. <span data-ttu-id="72c09-222">Expandera "PaymentByCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="72c09-223">Expandera "PaymentByCurrency\grupperad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="72c09-224">Välj "PaymentByCurrency\grupperad\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="72c09-225">Expandera "Excel\SummaryLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="72c09-226">Välj "Excel\SummaryLines\SummaryCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="72c09-227">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-227">Click Bind.</span></span>
44. <span data-ttu-id="72c09-228">Expandera "PaymentByCurrency\sammansatt" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="72c09-229">Välj "PaymentByCurrency\sammansatt\TotalInstructuredAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="72c09-230">Välj "Excel\SummaryLines\SummaryAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="72c09-231">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-231">Click Bind.</span></span>
48. <span data-ttu-id="72c09-232">Välj "PaymentByCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="72c09-233">Välj "Excel\SummaryLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="72c09-234">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-234">Click Bind.</span></span>
51. <span data-ttu-id="72c09-235">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="72c09-236">Välj "Excel\PaymLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="72c09-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="72c09-237">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="72c09-237">Click Bind.</span></span>
54. <span data-ttu-id="72c09-238">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72c09-238">Click Save.</span></span>
55. <span data-ttu-id="72c09-239">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="72c09-240">Använd den skapade konfigurationen för bearbetning av betalningar</span><span class="sxs-lookup"><span data-stu-id="72c09-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="72c09-241">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="72c09-241">Click Change status.</span></span>
2. <span data-ttu-id="72c09-242">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="72c09-242">Click Complete.</span></span>
3. <span data-ttu-id="72c09-243">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-243">Click OK.</span></span>
4. <span data-ttu-id="72c09-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-244">Close the page.</span></span>
5. <span data-ttu-id="72c09-245">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-245">Close the page.</span></span>
6. <span data-ttu-id="72c09-246">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="72c09-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="72c09-247">Använd snabbfiltret för att filtrera på Betalsätt med värdet "Elektroniskt".</span><span class="sxs-lookup"><span data-stu-id="72c09-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="72c09-248">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="72c09-248">Electronic</span></span>  
8. <span data-ttu-id="72c09-249">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="72c09-249">Click Edit.</span></span>
9. <span data-ttu-id="72c09-250">Expandera avsnittet Filformat.</span><span class="sxs-lookup"><span data-stu-id="72c09-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="72c09-251">Välj Ja i fältet Allmän elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="72c09-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="72c09-252">Ange eller välj ett värde i fältet Exportera formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="72c09-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="72c09-253">Markera konfigurationen "Rapport över exempelkalkylblad".</span><span class="sxs-lookup"><span data-stu-id="72c09-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="72c09-254">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72c09-254">Click Save.</span></span>
13. <span data-ttu-id="72c09-255">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="72c09-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="72c09-256">Använd den skapade konfigurationen för att testa bearbetning av betalningsjournaler</span><span class="sxs-lookup"><span data-stu-id="72c09-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="72c09-257">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="72c09-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="72c09-258">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="72c09-258">Click New.</span></span>
    * <span data-ttu-id="72c09-259">Skapa en ny betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="72c09-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="72c09-260">Skriv ”VendPay” i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="72c09-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="72c09-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="72c09-261">VendPay</span></span>  
4. <span data-ttu-id="72c09-262">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="72c09-262">Click Lines.</span></span>
5. <span data-ttu-id="72c09-263">Ange värdena "GB_SI_000001" i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="72c09-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="72c09-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="72c09-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="72c09-265">Ställ in debet på "1000".</span><span class="sxs-lookup"><span data-stu-id="72c09-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="72c09-266">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="72c09-266">Click New.</span></span>
8. <span data-ttu-id="72c09-267">Ange värdena "GB_SI_000005" i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="72c09-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="72c09-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="72c09-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="72c09-269">Ställ in debet på "2000".</span><span class="sxs-lookup"><span data-stu-id="72c09-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="72c09-270">Ange "EUR" i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="72c09-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="72c09-271">Euro</span><span class="sxs-lookup"><span data-stu-id="72c09-271">EUR</span></span>  
11. <span data-ttu-id="72c09-272">Ange värdet "GBSI OPER" i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="72c09-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="72c09-273">GBSI-OPERATION</span><span class="sxs-lookup"><span data-stu-id="72c09-273">GBSI OPER</span></span>  
12. <span data-ttu-id="72c09-274">Skriv ett värde i fältet "Elektonisk".</span><span class="sxs-lookup"><span data-stu-id="72c09-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="72c09-275">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="72c09-275">Electronic</span></span>  
13. <span data-ttu-id="72c09-276">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="72c09-276">Click Save.</span></span>
14. <span data-ttu-id="72c09-277">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="72c09-277">Click Generate payments.</span></span>
15. <span data-ttu-id="72c09-278">Skriv ett värde i fältet "Elektonisk".</span><span class="sxs-lookup"><span data-stu-id="72c09-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="72c09-279">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="72c09-279">Electronic</span></span>  
16. <span data-ttu-id="72c09-280">Ange "Betalningar" i fältet för filnamn.</span><span class="sxs-lookup"><span data-stu-id="72c09-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="72c09-281">Skriv till exempel "betalningar".</span><span class="sxs-lookup"><span data-stu-id="72c09-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="72c09-282">Skriv "GBSI OPER" i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="72c09-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="72c09-283">GBSI-OPERATION</span><span class="sxs-lookup"><span data-stu-id="72c09-283">GBSI OPER</span></span>  
18. <span data-ttu-id="72c09-284">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-284">Click OK.</span></span>
19. <span data-ttu-id="72c09-285">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="72c09-285">Click OK.</span></span>
    * <span data-ttu-id="72c09-286">Granska det skapade kalkylbladet, inklusive information om betalningsrader samt summan för varje valutakod som används i detta betalningmeddelande.</span><span class="sxs-lookup"><span data-stu-id="72c09-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  

