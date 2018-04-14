--- 
title: "Utforma en konfiguration för rapportgenerering i OpenXML-format för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att generera elektroniska betalningsdokument i OPENXML-format."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 882799e12daf9a3b7b530201c913b8f921fb2ed3
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="97e12-103">Utforma en konfiguration för rapportgenerering i OpenXML-format för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="97e12-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97e12-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa en ny konfiguration för Elektronisk rapportering (ER) som innehåller en mall för att generera elektroniska betalningsdokument i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="97e12-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="97e12-105">Denna konfiguration kommer att användas för att bearbeta leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="97e12-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="97e12-106">I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i GBSI-företag.</span><span class="sxs-lookup"><span data-stu-id="97e12-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="97e12-107">För att slutföra dessa steg måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="97e12-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="97e12-108">Du måste också hämta och spara Microsoft Excel-filen [mall för betalningsrapport](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="97e12-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="97e12-109">Överför konfigurationen för betalningdatamodellen</span><span class="sxs-lookup"><span data-stu-id="97e12-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="97e12-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="97e12-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="97e12-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="97e12-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="97e12-112">Välj konfigurationsleverantören för exempelföretaget "Litware, Inc." Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="97e12-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="97e12-113">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="97e12-113">Click Set active.</span></span>
4. <span data-ttu-id="97e12-114">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="97e12-114">Click Repositories.</span></span>
    * <span data-ttu-id="97e12-115">Välj en databas för resurstypen Verksamhetsresurs, om det är tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="97e12-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="97e12-116">Om detta är tillgängligt hoppar du över stegen om att skapa en ny databas.</span><span class="sxs-lookup"><span data-stu-id="97e12-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="97e12-117">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97e12-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="97e12-118">Ange "Operations resources" i fältet Configuration repository type.</span><span class="sxs-lookup"><span data-stu-id="97e12-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="97e12-119">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="97e12-119">Click Create repository.</span></span>
8. <span data-ttu-id="97e12-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-120">Click OK.</span></span>
9. <span data-ttu-id="97e12-121">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="97e12-121">Click Open.</span></span>
10. <span data-ttu-id="97e12-122">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="97e12-123">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="97e12-123">Click Import.</span></span>
    * <span data-ttu-id="97e12-124">Importera den här datamodell.</span><span class="sxs-lookup"><span data-stu-id="97e12-124">Import this data model.</span></span> <span data-ttu-id="97e12-125">Den används som en datakälla i en ny formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="97e12-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="97e12-126">Hoppa över detta steg om den här konfigurationen redan har importerats.</span><span class="sxs-lookup"><span data-stu-id="97e12-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="97e12-127">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="97e12-127">Click Yes.</span></span>
13. <span data-ttu-id="97e12-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-128">Close the page.</span></span>
14. <span data-ttu-id="97e12-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="97e12-130">Skapa en ny formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="97e12-130">Create a new format configuration</span></span>
1. <span data-ttu-id="97e12-131">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="97e12-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="97e12-132">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="97e12-133">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97e12-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="97e12-134">Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="97e12-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="97e12-135">Skapa ett format som baseras på datamodellen PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="97e12-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="97e12-136">Skriv "Rapport över exempelkalkylblad" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="97e12-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="97e12-137">Rapport över exempelkalkylblad</span><span class="sxs-lookup"><span data-stu-id="97e12-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="97e12-138">Skriv in "Rapport över exempelkalkylblad för leverantörer"i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="97e12-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="97e12-139">Rapport över kalkylblad prov för leverantörers betalningar.</span><span class="sxs-lookup"><span data-stu-id="97e12-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="97e12-140">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="97e12-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="97e12-141">Välj definitionen "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="97e12-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="97e12-142">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="97e12-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="97e12-143">Designa ett nytt dokument i OPENXML-kalkylbladformat</span><span class="sxs-lookup"><span data-stu-id="97e12-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="97e12-144">Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="97e12-145">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="97e12-145">Click Designer.</span></span>
3. <span data-ttu-id="97e12-146">Klicka på Importera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="97e12-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="97e12-147">Klicka på Importera från Excel.</span><span class="sxs-lookup"><span data-stu-id="97e12-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="97e12-148">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="97e12-148">Click Attachments.</span></span>
    * <span data-ttu-id="97e12-149">Koppla det befintliga Excel-dokumentet som en mall.</span><span class="sxs-lookup"><span data-stu-id="97e12-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="97e12-150">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e12-150">Click New.</span></span>
7. <span data-ttu-id="97e12-151">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="97e12-151">Click File.</span></span>
    * <span data-ttu-id="97e12-152">Peka på den befintliga Excel-filen.</span><span class="sxs-lookup"><span data-stu-id="97e12-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="97e12-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-153">Close the page.</span></span>
9. <span data-ttu-id="97e12-154">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="97e12-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="97e12-155">Välj den bifogade Excel-filen som ska användas som en mall.</span><span class="sxs-lookup"><span data-stu-id="97e12-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="97e12-156">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-156">Click OK.</span></span>
    * <span data-ttu-id="97e12-157">Observera att ER-formatkomponenter har skapats i designformatet baserat på strukturen i det refererande MS Excel-dokumentet (namngivna intervall).</span><span class="sxs-lookup"><span data-stu-id="97e12-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="97e12-158">Skapa en ny datakälla för att beräkna summor per valutakoder</span><span class="sxs-lookup"><span data-stu-id="97e12-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="97e12-159">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="97e12-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="97e12-160">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97e12-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="97e12-161">Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="97e12-162">Ange "PaymentByCurrency" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="97e12-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="97e12-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="97e12-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="97e12-164">Klicka på Redigera grupp efter.</span><span class="sxs-lookup"><span data-stu-id="97e12-164">Click Edit group by.</span></span>
6. <span data-ttu-id="97e12-165">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="97e12-166">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="97e12-167">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="97e12-167">Click Add field to.</span></span>
9. <span data-ttu-id="97e12-168">Klicka på Vad ska grupperas.</span><span class="sxs-lookup"><span data-stu-id="97e12-168">Click What to group.</span></span>
10. <span data-ttu-id="97e12-169">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="97e12-170">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="97e12-171">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="97e12-171">Click Add field to.</span></span>
13. <span data-ttu-id="97e12-172">Klicka på Grupperade fält.</span><span class="sxs-lookup"><span data-stu-id="97e12-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="97e12-173">Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="97e12-174">Klicka på Lägg till fält i.</span><span class="sxs-lookup"><span data-stu-id="97e12-174">Click Add field to.</span></span>
16. <span data-ttu-id="97e12-175">Klicka på Sammansättningsfält.</span><span class="sxs-lookup"><span data-stu-id="97e12-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="97e12-176">Markera ett alternativ i fältet Metod.</span><span class="sxs-lookup"><span data-stu-id="97e12-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="97e12-177">Välj den sammansatta funktionen SUMMA.</span><span class="sxs-lookup"><span data-stu-id="97e12-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="97e12-178">Skriv "TotalInstructuredAmount" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="97e12-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="97e12-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="97e12-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="97e12-180">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e12-180">Click Save.</span></span>
20. <span data-ttu-id="97e12-181">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-181">Close the page.</span></span>
21. <span data-ttu-id="97e12-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="97e12-183">Mappa formatkomponenter till datakällor</span><span class="sxs-lookup"><span data-stu-id="97e12-183">Map format components to data sources</span></span>
1. <span data-ttu-id="97e12-184">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="97e12-185">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="97e12-186">Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="97e12-187">Expandera ”Modell\Betalningar\Initierande part(InitiatingParty)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="97e12-188">Expandera "Excel\ReportHeader" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="97e12-189">Välj "Excel\ReportHeader\CompanyName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="97e12-190">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-190">Click Bind.</span></span>
8. <span data-ttu-id="97e12-191">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="97e12-192">Expandera "modell\Betalningar\Betalningsmottagare\Identifiering" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="97e12-193">Välj "modell\Betalningar\Betalningsmottagare\Identifiering\Käll-ID(SourceID)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="97e12-194">Expandera "Excel\PaymLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="97e12-195">Välj "Excel\PaymLines\VendAccountName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="97e12-196">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-196">Click Bind.</span></span>
14. <span data-ttu-id="97e12-197">Välj "modell\Betalningar\Betalningsmottagare\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="97e12-198">Välj "Excel\PaymLines\VendName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="97e12-199">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-199">Click Bind.</span></span>
17. <span data-ttu-id="97e12-200">Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="97e12-201">Välj "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)\Namn" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="97e12-202">Välj "Excel\PaymLines\Bank" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="97e12-203">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-203">Click Bind.</span></span>
21. <span data-ttu-id="97e12-204">Välj "modell\Betalningar\Betalningsmottagaragent\CreditorAgent)\Clearingnummer(RoutingNumber)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="97e12-205">Välj "Excel\PaymLines\RoutingNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="97e12-206">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-206">Click Bind.</span></span>
24. <span data-ttu-id="97e12-207">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="97e12-208">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="97e12-209">Välj "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)\Identifiering\Nummer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="97e12-210">Välj "Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="97e12-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="97e12-211">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-211">Click Bind.</span></span>
29. <span data-ttu-id="97e12-212">Välj "modell\Betalningar\Instruerat belopp(InstructedAmount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="97e12-213">Välj "Excel\PaymLines\Debit" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="97e12-214">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-214">Click Bind.</span></span>
32. <span data-ttu-id="97e12-215">Expandera "modell\Betalningar\Betalningsmottagare" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="97e12-216">Expandera "modell\Betalningar\Betalningsmottagarens konto(Betalningsmottagarens konto)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="97e12-217">Expandera "modell\Betalningar\Betalningsmottagaragent(CreditorAgent)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="97e12-218">Välj "modell\Betalningar\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="97e12-219">Välj "Excel\PaymLines\Currency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="97e12-220">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-220">Click Bind.</span></span>
38. <span data-ttu-id="97e12-221">Expandera "PaymentByCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="97e12-222">Expandera "PaymentByCurrency\grupperad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="97e12-223">Välj "PaymentByCurrency\grupperad\Valuta" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="97e12-224">Expandera "Excel\SummaryLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="97e12-225">Välj "Excel\SummaryLines\SummaryCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="97e12-226">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-226">Click Bind.</span></span>
44. <span data-ttu-id="97e12-227">Expandera "PaymentByCurrency\sammansatt" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="97e12-228">Välj "PaymentByCurrency\sammansatt\TotalInstructuredAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="97e12-229">Välj "Excel\SummaryLines\SummaryAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="97e12-230">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-230">Click Bind.</span></span>
48. <span data-ttu-id="97e12-231">Välj "PaymentByCurrency" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="97e12-232">Välj "Excel\SummaryLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="97e12-233">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-233">Click Bind.</span></span>
51. <span data-ttu-id="97e12-234">Välj "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="97e12-235">Välj "Excel\PaymLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97e12-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="97e12-236">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97e12-236">Click Bind.</span></span>
54. <span data-ttu-id="97e12-237">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e12-237">Click Save.</span></span>
55. <span data-ttu-id="97e12-238">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="97e12-239">Använd den skapade konfigurationen för bearbetning av betalningar</span><span class="sxs-lookup"><span data-stu-id="97e12-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="97e12-240">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="97e12-240">Click Change status.</span></span>
2. <span data-ttu-id="97e12-241">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="97e12-241">Click Complete.</span></span>
3. <span data-ttu-id="97e12-242">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-242">Click OK.</span></span>
4. <span data-ttu-id="97e12-243">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-243">Close the page.</span></span>
5. <span data-ttu-id="97e12-244">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-244">Close the page.</span></span>
6. <span data-ttu-id="97e12-245">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="97e12-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="97e12-246">Använd snabbfiltret för att filtrera på Betalsätt med värdet "Elektroniskt".</span><span class="sxs-lookup"><span data-stu-id="97e12-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="97e12-247">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="97e12-247">Electronic</span></span>  
8. <span data-ttu-id="97e12-248">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="97e12-248">Click Edit.</span></span>
9. <span data-ttu-id="97e12-249">Expandera avsnittet Filformat.</span><span class="sxs-lookup"><span data-stu-id="97e12-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="97e12-250">Välj Ja i fältet Allmän elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="97e12-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="97e12-251">Ange eller välj ett värde i fältet Exportera formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="97e12-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="97e12-252">Markera konfigurationen "Rapport över exempelkalkylblad".</span><span class="sxs-lookup"><span data-stu-id="97e12-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="97e12-253">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e12-253">Click Save.</span></span>
13. <span data-ttu-id="97e12-254">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97e12-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="97e12-255">Använd den skapade konfigurationen för att testa bearbetning av betalningsjournaler</span><span class="sxs-lookup"><span data-stu-id="97e12-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="97e12-256">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="97e12-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="97e12-257">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e12-257">Click New.</span></span>
    * <span data-ttu-id="97e12-258">Skapa en ny betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="97e12-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="97e12-259">Skriv ”VendPay” i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="97e12-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="97e12-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="97e12-260">VendPay</span></span>  
4. <span data-ttu-id="97e12-261">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="97e12-261">Click Lines.</span></span>
5. <span data-ttu-id="97e12-262">Ange värdena "GB_SI_000001" i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="97e12-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="97e12-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="97e12-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="97e12-264">Ställ in debet på "1000".</span><span class="sxs-lookup"><span data-stu-id="97e12-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="97e12-265">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="97e12-265">Click New.</span></span>
8. <span data-ttu-id="97e12-266">Ange värdena "GB_SI_000005" i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="97e12-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="97e12-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="97e12-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="97e12-268">Ställ in debet på "2000".</span><span class="sxs-lookup"><span data-stu-id="97e12-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="97e12-269">Ange "EUR" i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="97e12-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="97e12-270">Euro</span><span class="sxs-lookup"><span data-stu-id="97e12-270">EUR</span></span>  
11. <span data-ttu-id="97e12-271">Ange värdet "GBSI OPER" i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="97e12-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="97e12-272">GBSI-OPERATION</span><span class="sxs-lookup"><span data-stu-id="97e12-272">GBSI OPER</span></span>  
12. <span data-ttu-id="97e12-273">Skriv ett värde i fältet "Elektonisk".</span><span class="sxs-lookup"><span data-stu-id="97e12-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="97e12-274">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="97e12-274">Electronic</span></span>  
13. <span data-ttu-id="97e12-275">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97e12-275">Click Save.</span></span>
14. <span data-ttu-id="97e12-276">Klicka på Generera betalningar.</span><span class="sxs-lookup"><span data-stu-id="97e12-276">Click Generate payments.</span></span>
15. <span data-ttu-id="97e12-277">Skriv ett värde i fältet "Elektonisk".</span><span class="sxs-lookup"><span data-stu-id="97e12-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="97e12-278">Elektronisk</span><span class="sxs-lookup"><span data-stu-id="97e12-278">Electronic</span></span>  
16. <span data-ttu-id="97e12-279">Ange "Betalningar" i fältet för filnamn.</span><span class="sxs-lookup"><span data-stu-id="97e12-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="97e12-280">Skriv till exempel "betalningar".</span><span class="sxs-lookup"><span data-stu-id="97e12-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="97e12-281">Skriv "GBSI OPER" i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="97e12-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="97e12-282">GBSI-OPERATION</span><span class="sxs-lookup"><span data-stu-id="97e12-282">GBSI OPER</span></span>  
18. <span data-ttu-id="97e12-283">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-283">Click OK.</span></span>
19. <span data-ttu-id="97e12-284">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97e12-284">Click OK.</span></span>
    * <span data-ttu-id="97e12-285">Granska det skapade kalkylbladet, inklusive information om betalningsrader samt summan för varje valutakod som används i detta betalningmeddelande.</span><span class="sxs-lookup"><span data-stu-id="97e12-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


