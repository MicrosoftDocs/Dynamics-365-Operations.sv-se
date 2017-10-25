--- 
title: "Ändra modell och mappning för att generera dokument med programdatauppdatering för elektronisk rapportering (ER)"
description: "Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren \"ER Generera dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: a29e273e5ef377826c0002a9a0a956defef6aa77
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="modify-model-and-mapping-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a><span data-ttu-id="437ba-103">Ändra modell och mappning för att generera dokument med programdatauppdatering för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="437ba-103">Modify model and mapping to generate documents with application data update for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="437ba-104">Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Generera dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)".</span><span class="sxs-lookup"><span data-stu-id="437ba-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 2: Generate documents)”.</span></span> 

<span data-ttu-id="437ba-105">Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att generera ett elektroniskt dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="437ba-106">I den här proceduren ska du ändra ER-konfigurationerna för att börja använda dem för att skapa elektroniska dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="437ba-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="437ba-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="437ba-108">Stegen kan utföras med hjälp av datauppsättningen DEMF.</span><span class="sxs-lookup"><span data-stu-id="437ba-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="437ba-109">Ändra datamodell</span><span class="sxs-lookup"><span data-stu-id="437ba-109">Modify data model</span></span>
1. <span data-ttu-id="437ba-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="437ba-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="437ba-111">Välj Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="437ba-112">Du ska utöka hur du använder datamodellen.</span><span class="sxs-lookup"><span data-stu-id="437ba-112">You will extend how you use the data model.</span></span> <span data-ttu-id="437ba-113">Förutom att använda den som datakälla för att generera Intrastat-rapporten, används datamodellen för att samla in information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="437ba-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="437ba-114">Informationen används sedan för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="437ba-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="437ba-115">Click Designer.</span></span>
4. <span data-ttu-id="437ba-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="437ba-117">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="437ba-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="437ba-118">Skriv "For application data update" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="437ba-119">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="437ba-119">For application data update</span></span>  
7. <span data-ttu-id="437ba-120">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-120">Click Add.</span></span>
8. <span data-ttu-id="437ba-121">Välj For application data update i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="437ba-122">Det nya rotobjektet läggs till för att ange dataflödet för att flytta data från Intrastat-rapporten (används som datakälla) till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="437ba-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="437ba-123">Observera att olika rotobjekt måste användas för att hämta data som bokförs till det utgående dokumentet och för att hämta data från det dokument som används för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="437ba-124">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="437ba-125">Skriv "Archive header" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="437ba-126">Arkivrubrik</span><span class="sxs-lookup"><span data-stu-id="437ba-126">Archive header</span></span>  
11. <span data-ttu-id="437ba-127">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="437ba-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-128">Click Add.</span></span>
    * <span data-ttu-id="437ba-129">Eftersom du vill skapa en post för alla Intrastat-rapporter som genereras måste du skapa ett nytt objekt för detta.</span><span class="sxs-lookup"><span data-stu-id="437ba-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="437ba-130">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="437ba-131">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="437ba-132">Filnamn</span><span class="sxs-lookup"><span data-stu-id="437ba-132">File name</span></span>  
15. <span data-ttu-id="437ba-133">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="437ba-134">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-134">Click Add.</span></span>
17. <span data-ttu-id="437ba-135">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="437ba-136">Skriv "Number of lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="437ba-137">Antal rader</span><span class="sxs-lookup"><span data-stu-id="437ba-137">Number of lines</span></span>  
19. <span data-ttu-id="437ba-138">Välj Heltal fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="437ba-139">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-139">Click Add.</span></span>
    * <span data-ttu-id="437ba-140">Lägg till det här objektet för att representera antalet Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="437ba-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="437ba-141">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="437ba-142">Skriv "Archive lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="437ba-143">Arkivera rader</span><span class="sxs-lookup"><span data-stu-id="437ba-143">Archive lines</span></span>  
23. <span data-ttu-id="437ba-144">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="437ba-145">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-145">Click Add.</span></span>
    * <span data-ttu-id="437ba-146">Lägg till det här objektet för att representera listan med Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="437ba-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="437ba-147">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="437ba-148">Skriv "Belopp" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="437ba-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="437ba-149">Tid</span><span class="sxs-lookup"><span data-stu-id="437ba-149">Amount</span></span>  
27. <span data-ttu-id="437ba-150">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="437ba-151">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-151">Click Add.</span></span>
29. <span data-ttu-id="437ba-152">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="437ba-153">Skriv "Commodity rec id" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="437ba-154">Artikelpost-ID</span><span class="sxs-lookup"><span data-stu-id="437ba-154">Commodity rec id</span></span>  
31. <span data-ttu-id="437ba-155">Välj "Int64" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="437ba-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-156">Click Add.</span></span>
33. <span data-ttu-id="437ba-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="437ba-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="437ba-158">Skriv "Item number" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="437ba-159">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="437ba-159">Item number</span></span>  
35. <span data-ttu-id="437ba-160">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="437ba-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="437ba-161">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-161">Click Add.</span></span>
37. <span data-ttu-id="437ba-162">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="437ba-162">Click Save.</span></span>
38. <span data-ttu-id="437ba-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="437ba-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="437ba-164">Ändra modellmappning</span><span class="sxs-lookup"><span data-stu-id="437ba-164">Modify model mapping</span></span>
1. <span data-ttu-id="437ba-165">Expandera Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="437ba-166">Välj Intrastat (model)\Intrastat (mapping) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="437ba-167">Ändra den befintliga modellmappningen om du vill börja använda den för uppdatering av programdata och för att arkivera information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="437ba-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="437ba-168">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="437ba-168">Click Designer.</span></span>
4. <span data-ttu-id="437ba-169">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="437ba-169">Click New.</span></span>
5. <span data-ttu-id="437ba-170">Skriv "Update archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="437ba-171">Uppdatera arkiv</span><span class="sxs-lookup"><span data-stu-id="437ba-171">Update archive</span></span>  
6. <span data-ttu-id="437ba-172">Välj To destination i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="437ba-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="437ba-173">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="437ba-173">Click Save.</span></span>
    * <span data-ttu-id="437ba-174">Den nya mappningen anger dataflödet för att flytta data (information om Intrastat-rapportering) från datamodellen till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="437ba-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="437ba-175">Observera att den andra modellens rotobjekt måste användas för att hämta data från programmet för rapportering och sedan använda data från datamodellen för uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-175">Note that different model’s root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="437ba-176">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="437ba-176">Click Designer.</span></span>
9. <span data-ttu-id="437ba-177">Välj Data model\Data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="437ba-178">Lägg till datakällan som krävs.</span><span class="sxs-lookup"><span data-stu-id="437ba-178">Add the required data source.</span></span> <span data-ttu-id="437ba-179">Detta är den datamodell som innehåller information om de rapporterade Intrastat-transaktioner som måste arkiveras.</span><span class="sxs-lookup"><span data-stu-id="437ba-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="437ba-180">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="437ba-180">Click Add root.</span></span>
11. <span data-ttu-id="437ba-181">Skriv "model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="437ba-182">modell</span><span class="sxs-lookup"><span data-stu-id="437ba-182">model</span></span>  
12. <span data-ttu-id="437ba-183">Ange eller välj ett värde för For application data update i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="437ba-183">In the Definition field, enter or select the value ‘For application data update’.</span></span>
    * <span data-ttu-id="437ba-184">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="437ba-184">For application data update</span></span>  
13. <span data-ttu-id="437ba-185">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="437ba-185">Click OK.</span></span>
14. <span data-ttu-id="437ba-186">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="437ba-187">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="437ba-188">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="437ba-189">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-189">Click Add.</span></span>
    * <span data-ttu-id="437ba-190">Eftersom du vill räkna upp rapporterade Intrastat-transaktioner för arkivering måste rätt datakälla läggas till.</span><span class="sxs-lookup"><span data-stu-id="437ba-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="437ba-191">Skriv "Enumerated lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="437ba-192">Fasta rader</span><span class="sxs-lookup"><span data-stu-id="437ba-192">Enumerated lines</span></span>  
19. <span data-ttu-id="437ba-193">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="437ba-193">Click Edit formula.</span></span>
20. <span data-ttu-id="437ba-194">Välj List\ENUMERATE i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="437ba-195">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="437ba-195">Click Add function.</span></span>
22. <span data-ttu-id="437ba-196">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="437ba-197">Expandera model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="437ba-198">Välj model\Archive header\Archive lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="437ba-199">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="437ba-199">Click Add data source.</span></span>
26. <span data-ttu-id="437ba-200">Ange ENUMERATE(model.'Archive header'.'Archive lines') i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="437ba-201">ENUMERATE(modell.Archive header.Archive lines)</span><span class="sxs-lookup"><span data-stu-id="437ba-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="437ba-202">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="437ba-202">Click Save.</span></span>
28. <span data-ttu-id="437ba-203">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="437ba-203">Close the page.</span></span>
29. <span data-ttu-id="437ba-204">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="437ba-204">Click OK.</span></span>
30. <span data-ttu-id="437ba-205">Klicka på Lägg till destination.</span><span class="sxs-lookup"><span data-stu-id="437ba-205">Click Add destination.</span></span>
    * <span data-ttu-id="437ba-206">Lägg till programregistren som obligatoriska mål som måste uppdateras för att arkivera information om rapporterade Intrastat-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="437ba-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="437ba-207">Skriv "Archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="437ba-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="437ba-208">Arkivera</span><span class="sxs-lookup"><span data-stu-id="437ba-208">Archive</span></span>  
32. <span data-ttu-id="437ba-209">Skriv "IntrastatArchiveGeneral" i fältet för registernamn.</span><span class="sxs-lookup"><span data-stu-id="437ba-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="437ba-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="437ba-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="437ba-211">Behåll poståtgärden Infoga så att du kan lägga till poster under informationsarkiveringen av respektive Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="437ba-211">Keep the record action ‘Insert’ so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="437ba-212">Välj Ja i fältet Postinformationslogg.</span><span class="sxs-lookup"><span data-stu-id="437ba-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="437ba-213">Välj Ja om du vill få information om problem med uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="437ba-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="437ba-214">Välj Ja i fältet Hoppa över validering av poståtgärd.</span><span class="sxs-lookup"><span data-stu-id="437ba-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="437ba-215">Välj Ja om du vill ignorera valideringsfel om det tomma fältet Arkiv-ID - Intrastat.</span><span class="sxs-lookup"><span data-stu-id="437ba-215">Select Yes to suppress validation errors about the empty ‘Intrastat archive ID’ field.</span></span> <span data-ttu-id="437ba-216">Detta görs efter att poster har lagts till, baserat på serienummerinställningarna som har konfigurerats för detta register i formuläret Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="437ba-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="437ba-217">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="437ba-217">Click OK.</span></span>
    * <span data-ttu-id="437ba-218">Bind elementen i den tillagda datakällan (den filtrerade modellen som baseras på det valda rotobjektet) till elementen från det tillagda målet.</span><span class="sxs-lookup"><span data-stu-id="437ba-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="437ba-219">Expandera Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="437ba-220">Expandera Archive\<Relations i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="437ba-221">Expandera Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="437ba-222">Välj Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="437ba-223">Expandera model\Archive header\Enumerated lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="437ba-224">Expandera model\Archive header\Enumerated lines\Value i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="437ba-225">Välj model\Archive header\Enumerated lines\Value\Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="437ba-226">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-226">Click Bind.</span></span>
44. <span data-ttu-id="437ba-227">Välj Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="437ba-228">Välj model\Archive header\Enumerated lines\Value\Commodity rec id i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="437ba-229">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-229">Click Bind.</span></span>
47. <span data-ttu-id="437ba-230">Välj Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="437ba-231">Välj model\Archive header\Enumerated lines\Value\Item number i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="437ba-232">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-232">Click Bind.</span></span>
50. <span data-ttu-id="437ba-233">Välj Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="437ba-234">Välj model\Archive header\Enumerated lines\Number i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="437ba-235">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-235">Click Bind.</span></span>
53. <span data-ttu-id="437ba-236">Välj Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="437ba-237">Välj model\Archive header\Enumerated lines.</span><span class="sxs-lookup"><span data-stu-id="437ba-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="437ba-238">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-238">Click Bind.</span></span>
56. <span data-ttu-id="437ba-239">Välj Archive\File name(FileName) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="437ba-240">Välj model\Archive header\File name i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="437ba-241">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-241">Click Bind.</span></span>
59. <span data-ttu-id="437ba-242">Välj Archive\Number of lines(NumberOfLines) i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="437ba-243">Välj model\Archive header\Number of lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="437ba-244">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-244">Click Bind.</span></span>
62. <span data-ttu-id="437ba-245">Välj Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="437ba-246">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="437ba-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="437ba-247">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="437ba-247">Click Bind.</span></span>
65. <span data-ttu-id="437ba-248">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="437ba-248">Click Save.</span></span>
66. <span data-ttu-id="437ba-249">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="437ba-249">Close the page.</span></span>
67. <span data-ttu-id="437ba-250">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="437ba-250">Close the page.</span></span>

