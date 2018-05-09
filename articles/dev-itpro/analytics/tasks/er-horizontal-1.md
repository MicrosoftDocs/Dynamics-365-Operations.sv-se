--- 
title: "Designa ett format för att använda horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter"
description: "Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 81edbccd8d94ea322e80056879a6d4b6caca4555
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="design-a-format-to-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports"></a><span data-ttu-id="c31fc-103">Designa ett format för att använda horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter</span><span class="sxs-lookup"><span data-stu-id="c31fc-103">Design a format to use horizontally-expandable ranges to dynamically add columns in Excel reports</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c31fc-104">Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall.</span><span class="sxs-lookup"><span data-stu-id="c31fc-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="c31fc-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="c31fc-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c31fc-106">För att slutföra dessa steg måste du först avsluta dessa tre uppgiftsguider:</span><span class="sxs-lookup"><span data-stu-id="c31fc-106">To complete these steps, you must first complete these three task guides:</span></span> 

<span data-ttu-id="c31fc-107">"ER Skapa en konfigurationsleverantör och välj den som aktiv"</span><span class="sxs-lookup"><span data-stu-id="c31fc-107">“ER Create a configuration provider and mark it as active”</span></span>

<span data-ttu-id="c31fc-108">"ER Använd ekonomiska dimensioner som en datakälla (Del 1: Designa datamodell)"</span><span class="sxs-lookup"><span data-stu-id="c31fc-108">“ER Use financial dimensions as a data source (Part 1: Design data model)”</span></span>

<span data-ttu-id="c31fc-109">"ER Använd ekonomiska dimensioner som en datakälla (Del 2: Modellmappning)"</span><span class="sxs-lookup"><span data-stu-id="c31fc-109">“ER Use financial dimensions as a data source (Part 2: Model mapping)”</span></span>

<span data-ttu-id="c31fc-110">Du måste också hämta och spara en lokal kopia av mallen med en exempelrapport som finns här [https://go.microsoft.com/fwlink/?linkid=862266](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="c31fc-110">You must also download and save a local copy of the template with a sample report found here, [https://go.microsoft.com/fwlink/?linkid=862266](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 


<span data-ttu-id="c31fc-111">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="c31fc-111">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-report-configuration"></a><span data-ttu-id="c31fc-112">Skapa en ny rapportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="c31fc-112">Create a new report configuration</span></span>
1. <span data-ttu-id="c31fc-113">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="c31fc-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c31fc-114">Välj "Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-114">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="c31fc-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="c31fc-115">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="c31fc-116">Ange "Format based on data model Financial dimensions sample model" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="c31fc-116">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="c31fc-117">Använd den modell som skapades i förväg som datakälla för den nya rapporten.</span><span class="sxs-lookup"><span data-stu-id="c31fc-117">Use the model created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="c31fc-118">Ange "Sample report with horizontally expandable ranges" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-118">In the Name field, type 'Sample report with horizontally expandable ranges'.</span></span>
    * <span data-ttu-id="c31fc-119">Provrapport med horisontellt expanderbara intervall</span><span class="sxs-lookup"><span data-stu-id="c31fc-119">Sample report with horizontally expandable ranges</span></span>  
6. <span data-ttu-id="c31fc-120">Ange "To make Excel output with dynamically adding columns" i fältet Description.</span><span class="sxs-lookup"><span data-stu-id="c31fc-120">In the Description field, type 'To make Excel output with dynamically adding columns'.</span></span>
    * <span data-ttu-id="c31fc-121">Skapa Excel-utmatningar med dynamiskt tillagda kolumner</span><span class="sxs-lookup"><span data-stu-id="c31fc-121">To make Excel output with dynamically adding columns</span></span>  
7. <span data-ttu-id="c31fc-122">Välj Entry i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="c31fc-122">In the Data model definition field, select Entry.</span></span>
8. <span data-ttu-id="c31fc-123">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c31fc-123">Click Create configuration.</span></span>

## <a name="design-the-report-format"></a><span data-ttu-id="c31fc-124">Designa rapportformatet</span><span class="sxs-lookup"><span data-stu-id="c31fc-124">Design the report format</span></span>
1. <span data-ttu-id="c31fc-125">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="c31fc-125">Click Designer.</span></span>
2. <span data-ttu-id="c31fc-126">Aktivera knappen "Show details".</span><span class="sxs-lookup"><span data-stu-id="c31fc-126">Turn on the ‘Show details’ toggle button.</span></span>
3. <span data-ttu-id="c31fc-127">Klicka på Importera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c31fc-127">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="c31fc-128">Klicka på Importera från Excel.</span><span class="sxs-lookup"><span data-stu-id="c31fc-128">Click Import from Excel.</span></span>
5. <span data-ttu-id="c31fc-129">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="c31fc-129">Click Attachments.</span></span>
    * <span data-ttu-id="c31fc-130">Importera rapportens mall.</span><span class="sxs-lookup"><span data-stu-id="c31fc-130">Import the report’s template.</span></span> <span data-ttu-id="c31fc-131">Använd den Excel-fil du hämtade för detta.</span><span class="sxs-lookup"><span data-stu-id="c31fc-131">Use Excel file that you downloaded for that.</span></span>  
6. <span data-ttu-id="c31fc-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c31fc-132">Click New.</span></span>
7. <span data-ttu-id="c31fc-133">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="c31fc-133">Click File.</span></span>
8. <span data-ttu-id="c31fc-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c31fc-134">Close the page.</span></span>
9. <span data-ttu-id="c31fc-135">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="c31fc-135">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="c31fc-136">Välj den hämtade mallen.</span><span class="sxs-lookup"><span data-stu-id="c31fc-136">Select the downloaded template.</span></span>  
10. <span data-ttu-id="c31fc-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c31fc-137">Click OK.</span></span>
    * <span data-ttu-id="c31fc-138">Lägg till ett nytt intervall för att dynamiskt skapa Excel-utmatning med det antal kolumner du valde (i användardialogformuläret) för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c31fc-138">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="c31fc-139">Varje cell för respektive kolumn representerar namnet på en enskild ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="c31fc-139">Each cell for every column will represent a single financial dimension’s name.</span></span>  
11. <span data-ttu-id="c31fc-140">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="c31fc-140">Click Add to open the drop dialog.</span></span>
12. <span data-ttu-id="c31fc-141">Välj "Excel\Range" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-141">In the tree, select 'Excel\Range'.</span></span>
13. <span data-ttu-id="c31fc-142">Ange "DimNames" i Excel-intervallsfältet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-142">In the Excel range field, type 'DimNames'.</span></span>
    * <span data-ttu-id="c31fc-143">DimNames</span><span class="sxs-lookup"><span data-stu-id="c31fc-143">DimNames</span></span>  
14. <span data-ttu-id="c31fc-144">Ange "Horizontal" i fältet Replication direction.</span><span class="sxs-lookup"><span data-stu-id="c31fc-144">In the Replication direction field, select 'Horizontal'.</span></span>
15. <span data-ttu-id="c31fc-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c31fc-145">Click OK.</span></span>
16. <span data-ttu-id="c31fc-146">Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet</span><span class="sxs-lookup"><span data-stu-id="c31fc-146">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
17. <span data-ttu-id="c31fc-147">Klicka på Flytta upp.</span><span class="sxs-lookup"><span data-stu-id="c31fc-147">Click Move up.</span></span>
18. <span data-ttu-id="c31fc-148">Välj "Excel = "SampleFinDimWsReport"\Cell<DimNames>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-148">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<DimNames>'.</span></span>
19. <span data-ttu-id="c31fc-149">Klicka på Cut.</span><span class="sxs-lookup"><span data-stu-id="c31fc-149">Click Cut.</span></span>
20. <span data-ttu-id="c31fc-150">Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet</span><span class="sxs-lookup"><span data-stu-id="c31fc-150">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
21. <span data-ttu-id="c31fc-151">Klicka på Paste.</span><span class="sxs-lookup"><span data-stu-id="c31fc-151">Click Paste.</span></span>
22. <span data-ttu-id="c31fc-152">Visa "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet</span><span class="sxs-lookup"><span data-stu-id="c31fc-152">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
23. <span data-ttu-id="c31fc-153">Visa "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical" i trädet</span><span class="sxs-lookup"><span data-stu-id="c31fc-153">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
24. <span data-ttu-id="c31fc-154">Expandera "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-154">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
25. <span data-ttu-id="c31fc-155">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-155">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
    * <span data-ttu-id="c31fc-156">Lägg till ett nytt intervall för att dynamiskt skapa Excel-utmatning med det antal kolumner du valde (i användardialogformuläret) för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c31fc-156">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="c31fc-157">Varje cell för respektive kolumn representerar värdet för respektive rapporterande transaktion i en enskild ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="c31fc-157">Each cell for every column will represent a single financial dimension’s value for each reporting transaction.</span></span>  
26. <span data-ttu-id="c31fc-158">Klicka på Add Range.</span><span class="sxs-lookup"><span data-stu-id="c31fc-158">Click Add Range.</span></span>
27. <span data-ttu-id="c31fc-159">Ange "DimValues" i fältet för Excel-intervall.</span><span class="sxs-lookup"><span data-stu-id="c31fc-159">In the Excel range field, type 'DimValues'.</span></span>
    * <span data-ttu-id="c31fc-160">DimValues</span><span class="sxs-lookup"><span data-stu-id="c31fc-160">DimValues</span></span>  
28. <span data-ttu-id="c31fc-161">Ange "Horizontal" i fältet Replication direction.</span><span class="sxs-lookup"><span data-stu-id="c31fc-161">In the Replication direction field, select 'Horizontal'.</span></span>
29. <span data-ttu-id="c31fc-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c31fc-162">Click OK.</span></span>
30. <span data-ttu-id="c31fc-163">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-163">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>'.</span></span>
31. <span data-ttu-id="c31fc-164">Klicka på Cut.</span><span class="sxs-lookup"><span data-stu-id="c31fc-164">Click Cut.</span></span>
32. <span data-ttu-id="c31fc-165">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-165">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
33. <span data-ttu-id="c31fc-166">Klicka på Paste.</span><span class="sxs-lookup"><span data-stu-id="c31fc-166">Click Paste.</span></span>
34. <span data-ttu-id="c31fc-167">Visa "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-167">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>

## <a name="map-format-elements-to-data-sources"></a><span data-ttu-id="c31fc-168">Mappa formatelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="c31fc-168">Map format elements to data sources</span></span>
1. <span data-ttu-id="c31fc-169">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="c31fc-169">Click the Mapping tab.</span></span>
2. <span data-ttu-id="c31fc-170">Expandera "model: Data model Financial dimensions sample model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-170">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="c31fc-171">Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-171">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="c31fc-172">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-172">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="c31fc-173">Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="c31fc-174">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-174">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>'.</span></span>
7. <span data-ttu-id="c31fc-175">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-175">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
8. <span data-ttu-id="c31fc-176">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-176">Click Bind.</span></span>
9. <span data-ttu-id="c31fc-177">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-177">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
10. <span data-ttu-id="c31fc-178">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
11. <span data-ttu-id="c31fc-179">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-179">Click Bind.</span></span>
12. <span data-ttu-id="c31fc-180">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-180">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>'.</span></span>
13. <span data-ttu-id="c31fc-181">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
14. <span data-ttu-id="c31fc-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-182">Click Bind.</span></span>
15. <span data-ttu-id="c31fc-183">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-183">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>'.</span></span>
16. <span data-ttu-id="c31fc-184">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
17. <span data-ttu-id="c31fc-185">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-185">Click Bind.</span></span>
18. <span data-ttu-id="c31fc-186">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-186">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>'.</span></span>
19. <span data-ttu-id="c31fc-187">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
20. <span data-ttu-id="c31fc-188">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-188">Click Bind.</span></span>
21. <span data-ttu-id="c31fc-189">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-189">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>'.</span></span>
22. <span data-ttu-id="c31fc-190">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
23. <span data-ttu-id="c31fc-191">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-191">Click Bind.</span></span>
24. <span data-ttu-id="c31fc-192">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-192">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>'.</span></span>
25. <span data-ttu-id="c31fc-193">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
26. <span data-ttu-id="c31fc-194">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-194">Click Bind.</span></span>
27. <span data-ttu-id="c31fc-195">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-195">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>'.</span></span>
28. <span data-ttu-id="c31fc-196">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
29. <span data-ttu-id="c31fc-197">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-197">Click Bind.</span></span>
30. <span data-ttu-id="c31fc-198">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-198">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
31. <span data-ttu-id="c31fc-199">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
32. <span data-ttu-id="c31fc-200">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-200">Click Bind.</span></span>
33. <span data-ttu-id="c31fc-201">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-201">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>'.</span></span>
34. <span data-ttu-id="c31fc-202">Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
35. <span data-ttu-id="c31fc-203">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-203">Click Bind.</span></span>
36. <span data-ttu-id="c31fc-204">Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-204">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
37. <span data-ttu-id="c31fc-205">Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
38. <span data-ttu-id="c31fc-206">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-206">Click Bind.</span></span>
39. <span data-ttu-id="c31fc-207">Expandera "model: Data model Financial dimensions sample model\Dimensions setting: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-207">In the tree, expand 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
40. <span data-ttu-id="c31fc-208">Välj "model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-208">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String'.</span></span>
41. <span data-ttu-id="c31fc-209">Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-209">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>'.</span></span>
42. <span data-ttu-id="c31fc-210">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-210">Click Bind.</span></span>
43. <span data-ttu-id="c31fc-211">Välj "model: Data model Financial dimensions sample model\Dimensions setting: Record list" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-211">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
44. <span data-ttu-id="c31fc-212">Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet</span><span class="sxs-lookup"><span data-stu-id="c31fc-212">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
45. <span data-ttu-id="c31fc-213">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-213">Click Bind.</span></span>
46. <span data-ttu-id="c31fc-214">Välj "Excel = "SampleFinDimWsReport"\Cell<CompanyName>" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-214">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<CompanyName>'.</span></span>
47. <span data-ttu-id="c31fc-215">Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c31fc-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
48. <span data-ttu-id="c31fc-216">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="c31fc-216">Click Bind.</span></span>
49. <span data-ttu-id="c31fc-217">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c31fc-217">Click Save.</span></span>
50. <span data-ttu-id="c31fc-218">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c31fc-218">Close the page.</span></span>


