---
title: Ändra modeller och mappningar för att skapa dokument som omfattar programdata
description: 'Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)".'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4546de2c5c1773aadce0ec084ee7058ff2ae153
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141889"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="2823e-103">Ändra modeller och mappningar för att skapa dokument som omfattar programdata</span><span class="sxs-lookup"><span data-stu-id="2823e-103">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2823e-104">Om du vill utföra stegen i den här proceduren måste du först slutföra proceduren "ER Skapa dokument med uppdatering av programdata (Del 2: Skapa konfigurationer)".</span><span class="sxs-lookup"><span data-stu-id="2823e-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="2823e-105">Stegen i den här proceduren beskriver hur du utformar ER-konfigurationer (elektronisk rapportering) för att skapa ett elektroniskt dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="2823e-106">I den här proceduren ska du ändra ER-konfigurationerna för att börja använda dem för att skapa elektroniska dokument och uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="2823e-107">Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="2823e-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="2823e-108">Stegen kan utföras med hjälp av datauppsättningen DEMF.</span><span class="sxs-lookup"><span data-stu-id="2823e-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="2823e-109">Ändra datamodell</span><span class="sxs-lookup"><span data-stu-id="2823e-109">Modify data model</span></span>
1. <span data-ttu-id="2823e-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="2823e-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="2823e-111">Välj Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="2823e-112">Du ska utöka hur du använder datamodellen.</span><span class="sxs-lookup"><span data-stu-id="2823e-112">You will extend how you use the data model.</span></span> <span data-ttu-id="2823e-113">Förutom att använda den som datakälla för att skapa Intrastat-rapporten, används datamodellen för att samla in information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="2823e-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="2823e-114">Informationen används sedan för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="2823e-115">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2823e-115">Click Designer.</span></span>
4. <span data-ttu-id="2823e-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="2823e-117">Ange "Modellrot" i fältet "Ny nod som ett fält...".</span><span class="sxs-lookup"><span data-stu-id="2823e-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="2823e-118">Skriv "For application data update" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="2823e-119">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="2823e-119">For application data update</span></span>  
7. <span data-ttu-id="2823e-120">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-120">Click Add.</span></span>
8. <span data-ttu-id="2823e-121">Välj For application data update i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="2823e-122">Det nya rotobjektet läggs till för att ange dataflödet för att flytta data från Intrastat-rapporten (används som datakälla) till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="2823e-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="2823e-123">Observera att olika rotobjekt måste användas för att hämta data som bokförs till det utgående dokumentet och för att hämta data från det dokument som används för att uppdatera programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="2823e-124">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="2823e-125">Skriv "Archive header" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="2823e-126">Arkivrubrik</span><span class="sxs-lookup"><span data-stu-id="2823e-126">Archive header</span></span>  
11. <span data-ttu-id="2823e-127">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="2823e-128">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-128">Click Add.</span></span>
    * <span data-ttu-id="2823e-129">Eftersom du vill skapa en post för alla Intrastat-rapporter som skapas måste du skapa ett nytt objekt för detta.</span><span class="sxs-lookup"><span data-stu-id="2823e-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="2823e-130">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="2823e-131">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="2823e-132">Filnamn</span><span class="sxs-lookup"><span data-stu-id="2823e-132">File name</span></span>  
15. <span data-ttu-id="2823e-133">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="2823e-134">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-134">Click Add.</span></span>
17. <span data-ttu-id="2823e-135">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="2823e-136">Skriv "Number of lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="2823e-137">Antal rader</span><span class="sxs-lookup"><span data-stu-id="2823e-137">Number of lines</span></span>  
19. <span data-ttu-id="2823e-138">Välj Heltal fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="2823e-139">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-139">Click Add.</span></span>
    * <span data-ttu-id="2823e-140">Lägg till det här objektet för att representera antalet Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2823e-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="2823e-141">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="2823e-142">Skriv "Archive lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="2823e-143">Arkivera rader</span><span class="sxs-lookup"><span data-stu-id="2823e-143">Archive lines</span></span>  
23. <span data-ttu-id="2823e-144">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="2823e-145">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-145">Click Add.</span></span>
    * <span data-ttu-id="2823e-146">Lägg till det här objektet för att representera listan med Intrastat-transaktioner som rapporteras under den aktuella rapporteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2823e-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="2823e-147">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="2823e-148">Skriv "Belopp" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2823e-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="2823e-149">Tid</span><span class="sxs-lookup"><span data-stu-id="2823e-149">Amount</span></span>  
27. <span data-ttu-id="2823e-150">Välj "Realtal" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="2823e-151">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-151">Click Add.</span></span>
29. <span data-ttu-id="2823e-152">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="2823e-153">Skriv "Commodity rec id" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="2823e-154">Artikelpost-ID</span><span class="sxs-lookup"><span data-stu-id="2823e-154">Commodity rec id</span></span>  
31. <span data-ttu-id="2823e-155">Välj "Int64" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="2823e-156">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-156">Click Add.</span></span>
33. <span data-ttu-id="2823e-157">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2823e-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="2823e-158">Skriv "Item number" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="2823e-159">Artikelnummer</span><span class="sxs-lookup"><span data-stu-id="2823e-159">Item number</span></span>  
35. <span data-ttu-id="2823e-160">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="2823e-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="2823e-161">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-161">Click Add.</span></span>
37. <span data-ttu-id="2823e-162">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2823e-162">Click Save.</span></span>
38. <span data-ttu-id="2823e-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2823e-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="2823e-164">Ändra modellmappning</span><span class="sxs-lookup"><span data-stu-id="2823e-164">Modify model mapping</span></span>
1. <span data-ttu-id="2823e-165">Expandera Intrastat (model) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="2823e-166">Välj Intrastat (model)\Intrastat (mapping) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="2823e-167">Ändra den befintliga modellmappningen om du vill börja använda den för uppdatering av programdata och för att arkivera information om Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="2823e-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="2823e-168">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2823e-168">Click Designer.</span></span>
4. <span data-ttu-id="2823e-169">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="2823e-169">Click New.</span></span>
5. <span data-ttu-id="2823e-170">Skriv "Update archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="2823e-171">Uppdatera arkiv</span><span class="sxs-lookup"><span data-stu-id="2823e-171">Update archive</span></span>  
6. <span data-ttu-id="2823e-172">Välj To mål i fältet Direction.</span><span class="sxs-lookup"><span data-stu-id="2823e-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="2823e-173">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2823e-173">Click Save.</span></span>
    * <span data-ttu-id="2823e-174">Den nya mappningen anger dataflödet för att flytta data (information om Intrastat-rapportering) från datamodellen till programregistren (uppdateringsmålet).</span><span class="sxs-lookup"><span data-stu-id="2823e-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="2823e-175">Observera att den andra modellens rotobjekt måste användas för att hämta data från programmet för rapportering och sedan använda data från datamodellen för uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-175">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="2823e-176">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2823e-176">Click Designer.</span></span>
9. <span data-ttu-id="2823e-177">Välj Data model\Data model i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="2823e-178">Lägg till datakällan som krävs.</span><span class="sxs-lookup"><span data-stu-id="2823e-178">Add the required data source.</span></span> <span data-ttu-id="2823e-179">Detta är den datamodell som innehåller information om de rapporterade Intrastat-transaktioner som måste arkiveras.</span><span class="sxs-lookup"><span data-stu-id="2823e-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="2823e-180">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="2823e-180">Click Add root.</span></span>
11. <span data-ttu-id="2823e-181">Skriv "model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="2823e-182">modell</span><span class="sxs-lookup"><span data-stu-id="2823e-182">model</span></span>  
12. <span data-ttu-id="2823e-183">Ange eller välj ett värde för For application data update i fältet Definition.</span><span class="sxs-lookup"><span data-stu-id="2823e-183">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="2823e-184">För uppdatering av programdata</span><span class="sxs-lookup"><span data-stu-id="2823e-184">For application data update</span></span>  
13. <span data-ttu-id="2823e-185">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2823e-185">Click OK.</span></span>
14. <span data-ttu-id="2823e-186">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="2823e-187">Välj Funktioner/Beräknat fält i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="2823e-188">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="2823e-189">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-189">Click Add.</span></span>
    * <span data-ttu-id="2823e-190">Eftersom du vill räkna upp rapporterade Intrastat-transaktioner för arkivering måste rätt datakälla läggas till.</span><span class="sxs-lookup"><span data-stu-id="2823e-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="2823e-191">Skriv "Enumerated lines" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="2823e-192">Fasta rader</span><span class="sxs-lookup"><span data-stu-id="2823e-192">Enumerated lines</span></span>  
19. <span data-ttu-id="2823e-193">Klicka på Redigera formel.</span><span class="sxs-lookup"><span data-stu-id="2823e-193">Click Edit formula.</span></span>
20. <span data-ttu-id="2823e-194">Välj List\ENUMERATE i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="2823e-195">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2823e-195">Click Add function.</span></span>
22. <span data-ttu-id="2823e-196">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="2823e-197">Expandera model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="2823e-198">Välj model\Archive header\Archive lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="2823e-199">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="2823e-199">Click Add data source.</span></span>
26. <span data-ttu-id="2823e-200">Ange ENUMERATE(model.'Archive header'.'Archive lines') i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="2823e-201">ENUMERATE(modell.Archive header.Archive lines)</span><span class="sxs-lookup"><span data-stu-id="2823e-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="2823e-202">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2823e-202">Click Save.</span></span>
28. <span data-ttu-id="2823e-203">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2823e-203">Close the page.</span></span>
29. <span data-ttu-id="2823e-204">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2823e-204">Click OK.</span></span>
30. <span data-ttu-id="2823e-205">Klicka på Lägg till mål.</span><span class="sxs-lookup"><span data-stu-id="2823e-205">Click Add destination.</span></span>
    * <span data-ttu-id="2823e-206">Lägg till programregistren som obligatoriska mål som måste uppdateras för att arkivera information om rapporterade Intrastat-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="2823e-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="2823e-207">Skriv "Archive" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2823e-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="2823e-208">Arkivera</span><span class="sxs-lookup"><span data-stu-id="2823e-208">Archive</span></span>  
32. <span data-ttu-id="2823e-209">Skriv "IntrastatArchiveGeneral" i fältet för registernamn.</span><span class="sxs-lookup"><span data-stu-id="2823e-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="2823e-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="2823e-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="2823e-211">Behåll poståtgärden Infoga så att du kan lägga till poster under informationsarkiveringen av respektive Intrastat-rapportering.</span><span class="sxs-lookup"><span data-stu-id="2823e-211">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="2823e-212">Välj Ja i fältet Postinformationslogg.</span><span class="sxs-lookup"><span data-stu-id="2823e-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="2823e-213">Välj Ja om du vill få information om problem med uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="2823e-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="2823e-214">Välj Ja i fältet Hoppa över validering av poståtgärd.</span><span class="sxs-lookup"><span data-stu-id="2823e-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="2823e-215">Välj Ja om du vill ignorera valideringsfel om det tomma fältet Arkiv-ID - Intrastat.</span><span class="sxs-lookup"><span data-stu-id="2823e-215">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="2823e-216">Detta görs efter att poster har lagts till, baserat på serienummerinställningarna som har konfigurerats för detta register i formuläret Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="2823e-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="2823e-217">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2823e-217">Click OK.</span></span>
    * <span data-ttu-id="2823e-218">Bind elementen i den tillagda datakällan (den filtrerade modellen som baseras på det valda rotobjektet) till elementen från det tillagda målet.</span><span class="sxs-lookup"><span data-stu-id="2823e-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="2823e-219">Expandera Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="2823e-220">Expandera Archive\<Relations i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="2823e-221">Expandera Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="2823e-222">Välj Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="2823e-223">Expandera model\Archive header\Enumerated lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="2823e-224">Expandera model\Archive header\Enumerated lines\Value i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="2823e-225">Välj model\Archive header\Enumerated lines\Value\Amount i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="2823e-226">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-226">Click Bind.</span></span>
44. <span data-ttu-id="2823e-227">Välj Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="2823e-228">Välj model\Archive header\Enumerated lines\Value\Commodity rec id i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="2823e-229">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-229">Click Bind.</span></span>
47. <span data-ttu-id="2823e-230">Välj Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="2823e-231">Välj model\Archive header\Enumerated lines\Value\Item number i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="2823e-232">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-232">Click Bind.</span></span>
50. <span data-ttu-id="2823e-233">Välj Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="2823e-234">Välj model\Archive header\Enumerated lines\Number i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="2823e-235">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-235">Click Bind.</span></span>
53. <span data-ttu-id="2823e-236">Välj Archive\<Relations\IntrastatArchiveDetail i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="2823e-237">Välj model\Archive header\Enumerated lines.</span><span class="sxs-lookup"><span data-stu-id="2823e-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="2823e-238">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-238">Click Bind.</span></span>
56. <span data-ttu-id="2823e-239">Välj Archive\File name(FileName) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="2823e-240">Välj model\Archive header\File name i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="2823e-241">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-241">Click Bind.</span></span>
59. <span data-ttu-id="2823e-242">Välj Archive\Number of lines(NumberOfLines) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="2823e-243">Välj model\Archive header\Number of lines i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="2823e-244">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-244">Click Bind.</span></span>
62. <span data-ttu-id="2823e-245">Välj Archive i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="2823e-246">Välj model\Archive header i trädet.</span><span class="sxs-lookup"><span data-stu-id="2823e-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="2823e-247">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2823e-247">Click Bind.</span></span>
65. <span data-ttu-id="2823e-248">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2823e-248">Click Save.</span></span>
66. <span data-ttu-id="2823e-249">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2823e-249">Close the page.</span></span>
67. <span data-ttu-id="2823e-250">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2823e-250">Close the page.</span></span>

