--- 
title: "Hantera modellmappningskonfigurationer för elektronisk rapportering (ER)"
description: "I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan hantera ER-modellmappningar (elektronisk rapportering) i separata ER-konfigurationer."
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
ms.openlocfilehash: 35fdc1e98897d449ce18fe38cc6b7896ca5c5278
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="manage-model-mapping-configurations-for-electronic-reporting-er"></a><span data-ttu-id="2d653-103">Hantera modellmappningskonfigurationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="2d653-103">Manage model mapping configurations for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d653-104">I följande steg förklaras hur en användare som är tilldelad rollen som systemadministratör eller utvecklare för elektronisk rapportering kan hantera ER-modellmappningar (elektronisk rapportering) i separata ER-konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="2d653-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="2d653-105">I den här uppgiftsguide skapar du de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. För att slutföra uppgiftsguiden måste du först slutföra stegen i uppgiftsguiden ”ER skapa en konfigurationsleverantör” och markera den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="2d653-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, “ER Create a configuration provider” and mark it as active.</span></span> 

<span data-ttu-id="2d653-106">Eftersom ER-konfigurationer delas mellan företag kan du genomföra den här uppgiftsguiden med valfri företagsdatauppsättning.</span><span class="sxs-lookup"><span data-stu-id="2d653-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="2d653-107">Funktionerna för den här uppgiften är tillgängliga om du har installerat någon av följande snabbkorrigeringar: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 för Dynamics AX 7.0 eller https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 för Dynamics 365 for Operations-versionen.</span><span class="sxs-lookup"><span data-stu-id="2d653-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="2d653-108">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="2d653-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="2d653-109">Kontrollera att konfigurationsleverantören för provföretaget "Litware, Inc." är markerad som aktiv och tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2d653-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="2d653-110">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i uppgiftsguiden Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="2d653-110">If you don’t see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="2d653-111">Lägg till en ny konfiguration för ER-modell</span><span class="sxs-lookup"><span data-stu-id="2d653-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="2d653-112">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="2d653-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="2d653-113">Lägg till en ny modellkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-113">Add a new model configuration.</span></span> <span data-ttu-id="2d653-114">Namnet måste vara unikt i konfigurationsträdet.</span><span class="sxs-lookup"><span data-stu-id="2d653-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="2d653-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="2d653-116">Skriv "Sample data model" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2d653-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="2d653-117">Exempel på datamodell</span><span class="sxs-lookup"><span data-stu-id="2d653-117">Sample data model</span></span>  
4. <span data-ttu-id="2d653-118">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-118">Click Create configuration.</span></span>
5. <span data-ttu-id="2d653-119">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-119">Click Designer.</span></span>
6. <span data-ttu-id="2d653-120">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="2d653-121">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2d653-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="2d653-122">Rot</span><span class="sxs-lookup"><span data-stu-id="2d653-122">Root</span></span>  
8. <span data-ttu-id="2d653-123">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2d653-123">Click Add.</span></span>
9. <span data-ttu-id="2d653-124">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="2d653-125">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2d653-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="2d653-126">Företag</span><span class="sxs-lookup"><span data-stu-id="2d653-126">Company</span></span>  
11. <span data-ttu-id="2d653-127">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2d653-127">Click Add.</span></span>
12. <span data-ttu-id="2d653-128">Gå till beskrivningsfältet och skriv texten "Description of the legal entity or company in which a user logged at run-time".</span><span class="sxs-lookup"><span data-stu-id="2d653-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="2d653-129">Beskrivning av den juridiska personen eller företaget som en användare loggat in till under körning.</span><span class="sxs-lookup"><span data-stu-id="2d653-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="2d653-130">Klicka på Rotreferens.</span><span class="sxs-lookup"><span data-stu-id="2d653-130">Click Root reference.</span></span>
14. <span data-ttu-id="2d653-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-131">Click OK.</span></span>
15. <span data-ttu-id="2d653-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2d653-132">Click Save.</span></span>
16. <span data-ttu-id="2d653-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-133">Close the page.</span></span>
17. <span data-ttu-id="2d653-134">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="2d653-134">Click Change status.</span></span>
18. <span data-ttu-id="2d653-135">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="2d653-135">Click Complete.</span></span>
19. <span data-ttu-id="2d653-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="2d653-137">Lägg till en ny konfiguration för ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="2d653-137">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="2d653-138">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="2d653-139">Skriv "Model Mapping based on data model Sample data model" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="2d653-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="2d653-140">Skriv "Sample mapping" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2d653-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="2d653-141">Exempelmappning</span><span class="sxs-lookup"><span data-stu-id="2d653-141">Sample mapping</span></span>  
4. <span data-ttu-id="2d653-142">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-142">Click Create configuration.</span></span>
5. <span data-ttu-id="2d653-143">Expandera avsnittet Förutsättningar.</span><span class="sxs-lookup"><span data-stu-id="2d653-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="2d653-144">Observera att gruppen för implementeringsförutsättningar har lagts till automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2d653-144">Note that the Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="2d653-145">Gruppen innehåller den nödvändiga komponent som refererar till den överordnade datamodellkonfigurationen och markeras som Implementering.</span><span class="sxs-lookup"><span data-stu-id="2d653-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="2d653-146">Detta innebär den här modellmappningskonfigurationen, Sample mapping, tar hänsyn till implementeringen av datamodellen, Sample data model.</span><span class="sxs-lookup"><span data-stu-id="2d653-146">This means that this Sample mapping model mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="2d653-147">Den här komponenten tvingar därför ER att hämta modellmappningskonfigurationen, Sample mapping, från en ER-databas när modellkonfigurationen, Sample data model, hämtas.</span><span class="sxs-lookup"><span data-stu-id="2d653-147">Therefore, this component will force ER to download the model mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="2d653-148">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-148">Click Designer.</span></span>
    * <span data-ttu-id="2d653-149">Observera att den skapade modellmappningskonfigurationen innehåller en tom ny mappning med samma namn som den skapade konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="2d653-149">Note that the created model mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="2d653-150">När en vald överordnad modellkonfiguration innehåller modellmappningar kopieras de till en ny modellmappningskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-150">Be aware that when a selected parent model configuration contains model mappings, they will be copied to a new model mapping configuration.</span></span>   
7. <span data-ttu-id="2d653-151">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-151">Click Designer.</span></span>
8. <span data-ttu-id="2d653-152">Välj Dynamics 365 for Operations\Table i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="2d653-153">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="2d653-153">Click Add root.</span></span>
10. <span data-ttu-id="2d653-154">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2d653-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="2d653-155">Företag</span><span class="sxs-lookup"><span data-stu-id="2d653-155">Company</span></span>  
11. <span data-ttu-id="2d653-156">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="2d653-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="2d653-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="2d653-157">CompanyInfo</span></span>  
12. <span data-ttu-id="2d653-158">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-158">Click OK.</span></span>
13. <span data-ttu-id="2d653-159">Expandera "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="2d653-160">Expandera Company\find() i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="2d653-161">Välj Company\find()\Name i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="2d653-162">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2d653-162">Click Bind.</span></span>
17. <span data-ttu-id="2d653-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2d653-163">Click Save.</span></span>
18. <span data-ttu-id="2d653-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-164">Close the page.</span></span>
19. <span data-ttu-id="2d653-165">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-165">Close the page.</span></span>
20. <span data-ttu-id="2d653-166">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="2d653-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="2d653-167">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="2d653-167">Click User parameters.</span></span>
22. <span data-ttu-id="2d653-168">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="2d653-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="2d653-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-169">Click OK.</span></span>
24. <span data-ttu-id="2d653-170">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="2d653-170">Click Edit.</span></span>
25. <span data-ttu-id="2d653-171">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="2d653-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="2d653-172">Lägg till en ny konfiguration för ER-format</span><span class="sxs-lookup"><span data-stu-id="2d653-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="2d653-173">Välj "Sample data model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="2d653-174">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="2d653-175">Skriv "Format based on data model Sample data model" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="2d653-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="2d653-176">Skriv "Sample format" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2d653-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="2d653-177">Exempelformat</span><span class="sxs-lookup"><span data-stu-id="2d653-177">Sample format</span></span>  
5. <span data-ttu-id="2d653-178">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-178">Click Create configuration.</span></span>
6. <span data-ttu-id="2d653-179">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-179">Click Designer.</span></span>
7. <span data-ttu-id="2d653-180">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="2d653-181">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="2d653-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-182">Click OK.</span></span>
10. <span data-ttu-id="2d653-183">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="2d653-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="2d653-184">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="2d653-185">Välj model\Company i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="2d653-186">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="2d653-186">Click Bind.</span></span>
14. <span data-ttu-id="2d653-187">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2d653-187">Click Save.</span></span>
15. <span data-ttu-id="2d653-188">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-188">Close the page.</span></span>
    * <span data-ttu-id="2d653-189">Kör utkastversionen av det skapade formatet i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="2d653-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="2d653-190">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="2d653-190">Click Run.</span></span>
    * <span data-ttu-id="2d653-191">Klicka på Kör på snabbfliken Versioner.</span><span class="sxs-lookup"><span data-stu-id="2d653-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="2d653-192">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-192">Click OK.</span></span>
    * <span data-ttu-id="2d653-193">Granska utdata som innehåller namnet på det företaget där användaren som kör den här formatkonfigurationen är inloggad i.</span><span class="sxs-lookup"><span data-stu-id="2d653-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="2d653-194">Observera att den skapade konfigurationen för modellmappning används av denna formatkonfiguration eftersom det bara finns en konfigurationsnyckel som innehåller nödvändiga modellmappningar.</span><span class="sxs-lookup"><span data-stu-id="2d653-194">Note that the created model mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="2d653-195">Lägg till en alternativ konfiguration för ER-modellmappning</span><span class="sxs-lookup"><span data-stu-id="2d653-195">Add alternative ER model mapping configuration</span></span>
1. <span data-ttu-id="2d653-196">Välj "Sample data model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="2d653-197">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="2d653-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="2d653-198">Skriv "Model Mapping based on data model Sample data model" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="2d653-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="2d653-199">Skriv "Sample mapping (alternative)" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="2d653-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="2d653-200">Exempelmappning (alternativ)</span><span class="sxs-lookup"><span data-stu-id="2d653-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="2d653-201">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2d653-201">Click Create configuration.</span></span>
6. <span data-ttu-id="2d653-202">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-202">Click Designer.</span></span>
7. <span data-ttu-id="2d653-203">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="2d653-203">Click Designer.</span></span>
8. <span data-ttu-id="2d653-204">Välj Dynamics 365 for Operations\Table i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="2d653-205">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="2d653-205">Click Add root.</span></span>
10. <span data-ttu-id="2d653-206">Skriv "Företag" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="2d653-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="2d653-207">Företag</span><span class="sxs-lookup"><span data-stu-id="2d653-207">Company</span></span>  
11. <span data-ttu-id="2d653-208">Skriv "CompanyInfo" i fältet Tabell.</span><span class="sxs-lookup"><span data-stu-id="2d653-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="2d653-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="2d653-209">CompanyInfo</span></span>  
12. <span data-ttu-id="2d653-210">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-210">Click OK.</span></span>
13. <span data-ttu-id="2d653-211">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="2d653-211">Click Edit.</span></span>
14. <span data-ttu-id="2d653-212">Välj "Sträng\SAMMANFOGA" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="2d653-213">Klicka på funktionen Lägg till.</span><span class="sxs-lookup"><span data-stu-id="2d653-213">Click Add function.</span></span>
16. <span data-ttu-id="2d653-214">Expandera "Company" i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="2d653-215">Expandera Company\find() i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="2d653-216">Välj Company\find()\Name i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="2d653-217">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="2d653-217">Click Add data source.</span></span>
20. <span data-ttu-id="2d653-218">Skriv ett värde i fältet Formel.</span><span class="sxs-lookup"><span data-stu-id="2d653-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="2d653-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="2d653-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="2d653-220">Välj Company\find()\Company(DataArea) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="2d653-221">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="2d653-221">Click Add data source.</span></span>
23. <span data-ttu-id="2d653-222">Skriv ett värde i fältet Formel.</span><span class="sxs-lookup"><span data-stu-id="2d653-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="2d653-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="2d653-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="2d653-224">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2d653-224">Click Save.</span></span>
25. <span data-ttu-id="2d653-225">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-225">Close the page.</span></span>
26. <span data-ttu-id="2d653-226">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="2d653-226">Click Save.</span></span>
27. <span data-ttu-id="2d653-227">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-227">Close the page.</span></span>
28. <span data-ttu-id="2d653-228">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2d653-228">Close the page.</span></span>
29. <span data-ttu-id="2d653-229">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="2d653-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="2d653-230">Använd en befintlig konfiguration för ER-mappning</span><span class="sxs-lookup"><span data-stu-id="2d653-230">Use an existing ER model mapping configuration</span></span>
1. <span data-ttu-id="2d653-231">Välj Sample data model\Sample format i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="2d653-232">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="2d653-232">Click Run.</span></span>
    * <span data-ttu-id="2d653-233">Observera att den valda utkastversionen av ER-formatkonfigurationen inte kan köras eftersom det finns mer än en modellmappningskonfiguration för den odefinierade datamodellen som har valts som datakälla för ER-formatet som körs.</span><span class="sxs-lookup"><span data-stu-id="2d653-233">Note that the selected draft version of the ER format configuration can’t be executed because there is more than one model mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="2d653-234">Härnäst ska du definiera den alternativa modellmappningskonfigurationen som den varifrån modellmappningar ska användas som datakällor för ER-formatet som körs.</span><span class="sxs-lookup"><span data-stu-id="2d653-234">Next, you will define the alternative model mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="2d653-235">Välj Sample data model\Sample mapping (alternative) i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="2d653-236">Välj Ja i fältet Standardvärde för modellmappning.</span><span class="sxs-lookup"><span data-stu-id="2d653-236">Select Yes in the Default for model mapping field.</span></span>
5. <span data-ttu-id="2d653-237">Välj Sample data model\Sample format i trädet.</span><span class="sxs-lookup"><span data-stu-id="2d653-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="2d653-238">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="2d653-238">Click Run.</span></span>
7. <span data-ttu-id="2d653-239">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="2d653-239">Click OK.</span></span>
    * <span data-ttu-id="2d653-240">Observera att standardmodellmappningskonfigurationen används i den här formatkonfigurationen för att generera det elektroniska dokumentet (de utdata som skapas innehåller företagskoden).</span><span class="sxs-lookup"><span data-stu-id="2d653-240">Note that the default model mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

