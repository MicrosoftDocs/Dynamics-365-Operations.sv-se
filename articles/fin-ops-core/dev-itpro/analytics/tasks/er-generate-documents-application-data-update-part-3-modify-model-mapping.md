---
title: Ändra modeller och mappningar för att skapa dokument som omfattar programdata
description: Det här ämnet beskriver hur du utformar rapporteringskonfigurationer för att skapa ett elektroniskt dokument och uppdatera programdata. (Del 2 - Generera dokument).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78b1771d0e01702162192ff20c03facbba4f3513
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751616"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="f9019-104">Ändra modeller och mappningar för att skapa dokument som omfattar programdata</span><span class="sxs-lookup"><span data-stu-id="f9019-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f9019-105">Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)".</span><span class="sxs-lookup"><span data-stu-id="f9019-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="f9019-106">Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="f9019-107">I den här proceduren ska du ändra ER-konfigurationerna för att börja använda dem för att skapa elektroniska dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="f9019-108">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="f9019-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f9019-109">Stegen kan utföras med hjälp av datauppsättningen DEMF.</span><span class="sxs-lookup"><span data-stu-id="f9019-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="f9019-110">Ändra datamodell</span><span class="sxs-lookup"><span data-stu-id="f9019-110">Modify data model</span></span>
1. <span data-ttu-id="f9019-111">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f9019-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f9019-112">Välj Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="f9019-113">Du ska utöka hur du använder datamodellen.</span><span class="sxs-lookup"><span data-stu-id="f9019-113">You will extend how you use the data model.</span></span> <span data-ttu-id="f9019-114">Förutom att använda den som datakälla för att skapa Intrastat-rapporten, används datamodellen för att samla in information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="f9019-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="f9019-115">Informationen används sedan för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="f9019-116">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f9019-116">Click Designer.</span></span>
4. <span data-ttu-id="f9019-117">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="f9019-118">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="f9019-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="f9019-119">Skriv "For application data update" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="f9019-120">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="f9019-120">For application data update</span></span>  
7. <span data-ttu-id="f9019-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-121">Click Add.</span></span>
8. <span data-ttu-id="f9019-122">Välj For application data update i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="f9019-123">Det nya rotobjektet läggs till för att ange dataflödet för att flytta data från Intrastat-rapporten (används som datakälla) till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="f9019-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="f9019-124">Observera att olika rotobjekt måste användas för att hämta data som bokförs till det utgående dokumentet och för att hämta data från det dokument som används för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="f9019-125">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="f9019-126">Skriv "Archive header" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="f9019-127">Arkivrubrik</span><span class="sxs-lookup"><span data-stu-id="f9019-127">Archive header</span></span>  
11. <span data-ttu-id="f9019-128">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="f9019-129">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-129">Click Add.</span></span>
    * <span data-ttu-id="f9019-130">Eftersom du vill skapa en post för alla Intrastat-rapporter som skapas måste du skapa ett nytt objekt för detta.</span><span class="sxs-lookup"><span data-stu-id="f9019-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="f9019-131">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="f9019-132">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="f9019-133">Filnamn</span><span class="sxs-lookup"><span data-stu-id="f9019-133">File name</span></span>  
15. <span data-ttu-id="f9019-134">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="f9019-135">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-135">Click Add.</span></span>
17. <span data-ttu-id="f9019-136">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="f9019-137">Skriv "Number of lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="f9019-138">Antal rader</span><span class="sxs-lookup"><span data-stu-id="f9019-138">Number of lines</span></span>  
19. <span data-ttu-id="f9019-139">Välj Heltal fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="f9019-140">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-140">Click Add.</span></span>
    * <span data-ttu-id="f9019-141">Lägg till det här objektet för att representera antalet Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f9019-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="f9019-142">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="f9019-143">Skriv "Archive lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="f9019-144">Arkivera rader</span><span class="sxs-lookup"><span data-stu-id="f9019-144">Archive lines</span></span>  
23. <span data-ttu-id="f9019-145">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="f9019-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-146">Click Add.</span></span>
    * <span data-ttu-id="f9019-147">Lägg till det här objektet för att representera listan med Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="f9019-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="f9019-148">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="f9019-149">Skriv "Belopp" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f9019-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f9019-150">Tid</span><span class="sxs-lookup"><span data-stu-id="f9019-150">Amount</span></span>  
27. <span data-ttu-id="f9019-151">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="f9019-152">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-152">Click Add.</span></span>
29. <span data-ttu-id="f9019-153">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="f9019-154">Skriv "Commodity rec id" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="f9019-155">Artikelpost-ID</span><span class="sxs-lookup"><span data-stu-id="f9019-155">Commodity rec id</span></span>  
31. <span data-ttu-id="f9019-156">Välj "Int64" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="f9019-157">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-157">Click Add.</span></span>
33. <span data-ttu-id="f9019-158">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f9019-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="f9019-159">Skriv "Item number" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="f9019-160">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="f9019-160">Item number</span></span>  
35. <span data-ttu-id="f9019-161">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="f9019-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="f9019-162">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-162">Click Add.</span></span>
37. <span data-ttu-id="f9019-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f9019-163">Click Save.</span></span>
38. <span data-ttu-id="f9019-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f9019-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="f9019-165">Ändra modellmappning</span><span class="sxs-lookup"><span data-stu-id="f9019-165">Modify model mapping</span></span>
1. <span data-ttu-id="f9019-166">Expandera Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="f9019-167">Välj Intrastat (model)\Intrastat (mapping) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="f9019-168">Ändra den befintliga modellmappningen om du vill börja använda den för uppdatering av programdata och för att arkivera information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="f9019-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="f9019-169">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f9019-169">Click Designer.</span></span>
4. <span data-ttu-id="f9019-170">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f9019-170">Click New.</span></span>
5. <span data-ttu-id="f9019-171">Skriv "Update archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="f9019-172">Uppdatera arkiv</span><span class="sxs-lookup"><span data-stu-id="f9019-172">Update archive</span></span>  
6. <span data-ttu-id="f9019-173">Välj To mål i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="f9019-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="f9019-174">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f9019-174">Click Save.</span></span>
    * <span data-ttu-id="f9019-175">Den nya mappningen anger dataflödet för att flytta data (information om Intrastat-rapportering) från datamodellen till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="f9019-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="f9019-176">Observera att den andra modellens rotobjekt måste användas för att hämta data från programmet för rapportering och sedan använda data från datamodellen för uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="f9019-177">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f9019-177">Click Designer.</span></span>
9. <span data-ttu-id="f9019-178">Välj Data model\Data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="f9019-179">Lägg till datakällan som krävs.</span><span class="sxs-lookup"><span data-stu-id="f9019-179">Add the required data source.</span></span> <span data-ttu-id="f9019-180">Detta är den datamodell som innehåller information om de rapporterade Intrastat-transaktioner som måste arkiveras.</span><span class="sxs-lookup"><span data-stu-id="f9019-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="f9019-181">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="f9019-181">Click Add root.</span></span>
11. <span data-ttu-id="f9019-182">Skriv "model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="f9019-183">modell</span><span class="sxs-lookup"><span data-stu-id="f9019-183">model</span></span>  
12. <span data-ttu-id="f9019-184">Ange eller välj ett värde för For application data update i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="f9019-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="f9019-185">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="f9019-185">For application data update</span></span>  
13. <span data-ttu-id="f9019-186">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f9019-186">Click OK.</span></span>
14. <span data-ttu-id="f9019-187">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="f9019-188">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="f9019-189">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="f9019-190">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-190">Click Add.</span></span>
    * <span data-ttu-id="f9019-191">Eftersom du vill räkna upp rapporterade Intrastat-transaktioner för arkivering måste rätt datakälla läggas till.</span><span class="sxs-lookup"><span data-stu-id="f9019-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="f9019-192">Skriv "Enumerated lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="f9019-193">Fasta rader</span><span class="sxs-lookup"><span data-stu-id="f9019-193">Enumerated lines</span></span>  
19. <span data-ttu-id="f9019-194">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="f9019-194">Click Edit formula.</span></span>
20. <span data-ttu-id="f9019-195">Välj List\ENUMERATE i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="f9019-196">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f9019-196">Click Add function.</span></span>
22. <span data-ttu-id="f9019-197">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="f9019-198">Expandera model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="f9019-199">Välj model\Archive header\Archive lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="f9019-200">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f9019-200">Click Add data source.</span></span>
26. <span data-ttu-id="f9019-201">Ange ENUMERATE(model.'Archive header'.'Archive lines') i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="f9019-202">ENUMERATE(modell.Archive header.Archive lines)</span><span class="sxs-lookup"><span data-stu-id="f9019-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="f9019-203">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f9019-203">Click Save.</span></span>
28. <span data-ttu-id="f9019-204">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f9019-204">Close the page.</span></span>
29. <span data-ttu-id="f9019-205">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f9019-205">Click OK.</span></span>
30. <span data-ttu-id="f9019-206">Klicka på Lägg till mål.</span><span class="sxs-lookup"><span data-stu-id="f9019-206">Click Add destination.</span></span>
    * <span data-ttu-id="f9019-207">Lägg till programregistren som obligatoriska mål som måste uppdateras för att arkivera information om rapporterade Intrastat-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="f9019-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="f9019-208">Skriv "Archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f9019-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="f9019-209">Arkivera</span><span class="sxs-lookup"><span data-stu-id="f9019-209">Archive</span></span>  
32. <span data-ttu-id="f9019-210">Skriv "IntrastatArchiveGeneral" i fältet för registernamn.</span><span class="sxs-lookup"><span data-stu-id="f9019-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="f9019-211">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="f9019-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="f9019-212">Behåll poståtgärden Infoga så att du kan lägga till poster under informationsarkiveringen av respektive Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="f9019-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="f9019-213">Välj Ja i fältet Postinformationslogg.</span><span class="sxs-lookup"><span data-stu-id="f9019-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="f9019-214">Välj Ja om du vill få information om problem med uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="f9019-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="f9019-215">Välj Ja i fältet Hoppa över validering av poståtgärd.</span><span class="sxs-lookup"><span data-stu-id="f9019-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="f9019-216">Välj Ja om du vill ignorera valideringsfel om det tomma fältet Arkiv-ID - Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f9019-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="f9019-217">Detta görs efter att poster har lagts till, baserat på serienummerinställningarna som har konfigurerats för detta register i formuläret Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="f9019-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="f9019-218">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f9019-218">Click OK.</span></span>
    * <span data-ttu-id="f9019-219">Bind elementen i den tillagda datakällan (den filtrerade modellen som baseras på det valda rotobjektet) till elementen från det tillagda målet.</span><span class="sxs-lookup"><span data-stu-id="f9019-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="f9019-220">Expandera Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="f9019-221">Expandera Archive\<Relations i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="f9019-222">Expandera Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="f9019-223">Välj Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="f9019-224">Expandera model\Archive header\Enumerated lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="f9019-225">Expandera model\Archive header\Enumerated lines\Value i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="f9019-226">Välj model\Archive header\Enumerated lines\Value\Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="f9019-227">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-227">Click Bind.</span></span>
44. <span data-ttu-id="f9019-228">Välj Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="f9019-229">Välj model\Archive header\Enumerated lines\Value\Commodity rec id i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="f9019-230">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-230">Click Bind.</span></span>
47. <span data-ttu-id="f9019-231">Välj Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="f9019-232">Välj model\Archive header\Enumerated lines\Value\Item number i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="f9019-233">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-233">Click Bind.</span></span>
50. <span data-ttu-id="f9019-234">Välj Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="f9019-235">Välj model\Archive header\Enumerated lines\Number i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="f9019-236">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-236">Click Bind.</span></span>
53. <span data-ttu-id="f9019-237">Välj Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="f9019-238">Välj model\Archive header\Enumerated lines.</span><span class="sxs-lookup"><span data-stu-id="f9019-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="f9019-239">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-239">Click Bind.</span></span>
56. <span data-ttu-id="f9019-240">Välj Archive\File name(FileName) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="f9019-241">Välj model\Archive header\File name i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="f9019-242">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-242">Click Bind.</span></span>
59. <span data-ttu-id="f9019-243">Välj Archive\Number of lines(NumberOfLines) i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="f9019-244">Välj model\Archive header\Number of lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="f9019-245">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-245">Click Bind.</span></span>
62. <span data-ttu-id="f9019-246">Välj Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="f9019-247">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="f9019-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="f9019-248">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f9019-248">Click Bind.</span></span>
65. <span data-ttu-id="f9019-249">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f9019-249">Click Save.</span></span>
66. <span data-ttu-id="f9019-250">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f9019-250">Close the page.</span></span>
67. <span data-ttu-id="f9019-251">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f9019-251">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]