--- 
title: "Skapa uttryck för att anropa programklassmetoder (ER)"
description: "Denna guide ger information om hur du återanvänder befintlig programlogik i konfigurationer för elektronisk rapportering (ER) genom att anropa metoder för programklasser i ER-uttryck."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fa2d85bbb9c8b2fda36883b71a3f540eabc4c1d7
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="design-expressions-to-call-application-class-methods-er"></a><span data-ttu-id="a4b39-103">Skapa uttryck för att anropa programklassmetoder (ER)</span><span class="sxs-lookup"><span data-stu-id="a4b39-103">Design expressions to call application class methods (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a4b39-104">Denna guide ger information om hur du återanvänder befintlig programlogik i konfigurationer för elektronisk rapportering (ER) genom att anropa metoder för programklasser i ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="a4b39-104">This guide provides information about how to reuse the existing application logic in Electronic reporting (ER) configurations by calling required methods of application classes in ER expressions.</span></span> <span data-ttu-id="a4b39-105">Argument för att anropa klasser kan definieras dynamiskt vid körning: exempelvis utifrån information i parsningdokumentet för att säkerställa att de är korrekta.</span><span class="sxs-lookup"><span data-stu-id="a4b39-105">Values of arguments for calling classes can be defined dynamically at run-time: for example, based on information in the parsing document to ensure its correctness.</span></span> <span data-ttu-id="a4b39-106">I den här handboken skapas de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. Proceduren är till för användare med rollen systemadministratör eller utvecklare av elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a4b39-106">In this guide, you will create the required ER configurations for the sample company, Litware, Inc. This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> 

<span data-ttu-id="a4b39-107">Stegen kan utföras med hjälp av valfri datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="a4b39-107">These steps can be completed using any data set.</span></span> <span data-ttu-id="a4b39-108">Måste du också hämta och spara följande fil lokalt: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.</span><span class="sxs-lookup"><span data-stu-id="a4b39-108">You must also download and save the following file locally: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.</span></span>

<span data-ttu-id="a4b39-109">För att slutföra dessa steg måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="a4b39-109">To complete these steps, you must first complete the steps in the procedure, “ER Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="a4b39-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="a4b39-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a4b39-111">Kontrollera att konfigurationsleverantören för provföretaget Litware, Inc. är markerad som aktiv och tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a4b39-111">Verify that the configuration provider for sample company, Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="a4b39-112">Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.</span><span class="sxs-lookup"><span data-stu-id="a4b39-112">If you don’t see this configuration provider, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>   
    * <span data-ttu-id="a4b39-113">Anta att du skapar en process för att parsa inkommande bankutdrag för en uppdatering av programdata.</span><span class="sxs-lookup"><span data-stu-id="a4b39-113">Let’s assume that you are designing a process for parsing incoming bank statements for an application data update.</span></span> <span data-ttu-id="a4b39-114">Inkommande bankutdrag visas som TXT-filer som innehåller IBAN koder.</span><span class="sxs-lookup"><span data-stu-id="a4b39-114">You will receive the incoming bank statements as TXT files that contain IBAN codes.</span></span> <span data-ttu-id="a4b39-115">Som en del av bankutdragets importprocess behöver du kontrollera riktigheten i dessa IBAN-koder med logik som finns i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a4b39-115">As part of the bank statement import process, you need to validate the correctness of this IBAN codes using the logic that is already available in Dynamics 365 for Finance and Operations.</span></span>   

## <a name="import-a-new-er-model-configuration"></a><span data-ttu-id="a4b39-116">Importera en ny konfiguration för ER-modell</span><span class="sxs-lookup"><span data-stu-id="a4b39-116">Import a new ER model configuration</span></span>
1. <span data-ttu-id="a4b39-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a4b39-118">Välj panelen Microsoft provider.</span><span class="sxs-lookup"><span data-stu-id="a4b39-118">Select the Microsoft provider tile.</span></span>  
2. <span data-ttu-id="a4b39-119">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="a4b39-119">Click Repositories.</span></span>
3. <span data-ttu-id="a4b39-120">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="a4b39-120">Click Show filters.</span></span>
4. <span data-ttu-id="a4b39-121">Lägg till ett filterfält "Typnamn".</span><span class="sxs-lookup"><span data-stu-id="a4b39-121">Add a filter field ‘Type name’.</span></span> <span data-ttu-id="a4b39-122">I fältet Namn anger du värdet "resurser", välj filtreringsoperatören "innehåller" och klickar sedan på Tillämpa.</span><span class="sxs-lookup"><span data-stu-id="a4b39-122">In the Name field, enter the value “resources”, select the “contains” filter operator, and then click Apply.</span></span>
5. <span data-ttu-id="a4b39-123">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="a4b39-123">Click Open.</span></span>
6. <span data-ttu-id="a4b39-124">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-124">In the tree, select 'Payment model'.</span></span>
    * <span data-ttu-id="a4b39-125">Om knappen Importera på snabbfliken Versioner inte aktiveras har du redan importerat version 1 i någon av ER-konfigurationen ”betalningsmodell'.</span><span class="sxs-lookup"><span data-stu-id="a4b39-125">If the Import button on the Versions FastTab is not enabled, you have already imported the version 1 one of the ER configuration ‘Payment model’.</span></span> <span data-ttu-id="a4b39-126">Du kan hoppa över resten av stegen i den här underaktivitet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-126">You can skip the rest steps in this sub-task.</span></span>   
7. <span data-ttu-id="a4b39-127">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="a4b39-127">Click Import.</span></span>
8. <span data-ttu-id="a4b39-128">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="a4b39-128">Click Yes.</span></span>
9. <span data-ttu-id="a4b39-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-129">Close the page.</span></span>
10. <span data-ttu-id="a4b39-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-130">Close the page.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="a4b39-131">Lägg till en ny konfiguration för ER-format</span><span class="sxs-lookup"><span data-stu-id="a4b39-131">Add a new ER format configuration</span></span>
1. <span data-ttu-id="a4b39-132">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="a4b39-132">Click Reporting configurations.</span></span>
    * <span data-ttu-id="a4b39-133">Lägg till ett nytt ER-format som du vill dela upp inkommande bankutdrag i TXT-format.</span><span class="sxs-lookup"><span data-stu-id="a4b39-133">Add a new ER format to parse incoming bank statements in TXT format.</span></span>  
2. <span data-ttu-id="a4b39-134">Välj "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-134">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="a4b39-135">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-135">Click Create configuration to open the dialog menu.</span></span>
4. <span data-ttu-id="a4b39-136">Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.</span><span class="sxs-lookup"><span data-stu-id="a4b39-136">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
5. <span data-ttu-id="a4b39-137">I namnfältet anger du "bankutdragsformat för import" (exempel)</span><span class="sxs-lookup"><span data-stu-id="a4b39-137">In the Name field, type 'Bank statement import format (sample)'.</span></span>
    * <span data-ttu-id="a4b39-138">Importformat för bankutdrag (exempel)</span><span class="sxs-lookup"><span data-stu-id="a4b39-138">Bank statement import format (sample)</span></span>  
6. <span data-ttu-id="a4b39-139">Välj Ja i fältet Stöder dataimport.</span><span class="sxs-lookup"><span data-stu-id="a4b39-139">Select Yes in the Supports data import field.</span></span>
7. <span data-ttu-id="a4b39-140">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a4b39-140">Click Create configuration.</span></span>

## <a name="design-the-er-format-configuration---format"></a><span data-ttu-id="a4b39-141">Designa en konfiguration för ER-format</span><span class="sxs-lookup"><span data-stu-id="a4b39-141">Design the ER format configuration - format</span></span>
1. <span data-ttu-id="a4b39-142">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a4b39-142">Click Designer.</span></span>
    * <span data-ttu-id="a4b39-143">Det utformade formatet representerar den externa filens förväntade struktur i TXT-format.</span><span class="sxs-lookup"><span data-stu-id="a4b39-143">The designed format represents the expected structure of the external file in TXT format.</span></span>  
2. <span data-ttu-id="a4b39-144">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-144">Click Add root to open the dialog menu.</span></span>
3. <span data-ttu-id="a4b39-145">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-145">In the tree, select 'Text\Sequence'.</span></span>
4. <span data-ttu-id="a4b39-146">Ange "Root" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-146">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="a4b39-147">Rot</span><span class="sxs-lookup"><span data-stu-id="a4b39-147">Root</span></span>  
5. <span data-ttu-id="a4b39-148">Välj "New line - Windows (CR LF)" i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="a4b39-148">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
    * <span data-ttu-id="a4b39-149">Alternativet "Ny rad – Windows (CR LF)" har valts i fältet för specialtecken.</span><span class="sxs-lookup"><span data-stu-id="a4b39-149">The option ‘New line - Windows (CR LF)’ has been selected in the ‘Special characters’ field.</span></span> <span data-ttu-id="a4b39-150">Utifrån den här inställningen beaktas varje rad i parsingfilen som en separat post.</span><span class="sxs-lookup"><span data-stu-id="a4b39-150">Based on this setting, each line in the parsing file is considered a separate record.</span></span>  
6. <span data-ttu-id="a4b39-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-151">Click OK.</span></span>
7. <span data-ttu-id="a4b39-152">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-152">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="a4b39-153">Välj "Text\Sequence" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-153">In the tree, select 'Text\Sequence'.</span></span>
9. <span data-ttu-id="a4b39-154">Skriv "Rader" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a4b39-154">In the Name field, type 'Rows'.</span></span>
    * <span data-ttu-id="a4b39-155">Rader</span><span class="sxs-lookup"><span data-stu-id="a4b39-155">Rows</span></span>  
10. <span data-ttu-id="a4b39-156">Välj Ett många i fältet Sammansatt.</span><span class="sxs-lookup"><span data-stu-id="a4b39-156">In the Multiplicity field, select 'One many'.</span></span>
    * <span data-ttu-id="a4b39-157">Alternativet ”Ett många” har valts i fältet "Sammansatt".</span><span class="sxs-lookup"><span data-stu-id="a4b39-157">The option ‘One many’ has been selected in the ‘Multiplicity’ field.</span></span> <span data-ttu-id="a4b39-158">Baserat på denna inställning förväntas att minst en rad presenteras i parsningfilen.</span><span class="sxs-lookup"><span data-stu-id="a4b39-158">Based on this setting, it is expected that at least one line will be presented in the parsing file.</span></span>  
11. <span data-ttu-id="a4b39-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-159">Click OK.</span></span>
12. <span data-ttu-id="a4b39-160">Välj "Root\Rows" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-160">In the tree, select 'Root\Rows'.</span></span>
13. <span data-ttu-id="a4b39-161">Klicka på Lägg till sekvens.</span><span class="sxs-lookup"><span data-stu-id="a4b39-161">Click Add Sequence.</span></span>
14. <span data-ttu-id="a4b39-162">Skriv "Fält" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a4b39-162">In the Name field, type 'Fields'.</span></span>
    * <span data-ttu-id="a4b39-163">Fält</span><span class="sxs-lookup"><span data-stu-id="a4b39-163">Fields</span></span>  
15. <span data-ttu-id="a4b39-164">Välj Exakt ett i fältet Sammansatt.</span><span class="sxs-lookup"><span data-stu-id="a4b39-164">In the Multiplicity field, select 'Exactly one'.</span></span>
16. <span data-ttu-id="a4b39-165">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-165">Click OK.</span></span>
17. <span data-ttu-id="a4b39-166">Markera "Root\Rows\Fields" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-166">In the tree, select 'Root\Rows\Fields'.</span></span>
18. <span data-ttu-id="a4b39-167">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-167">Click Add to open the drop dialog.</span></span>
19. <span data-ttu-id="a4b39-168">Välj "Text\Sträng" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-168">In the tree, select 'Text\String'.</span></span>
20. <span data-ttu-id="a4b39-169">Skriv "IBAN" i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a4b39-169">In the Name field, type 'IBAN'.</span></span>
    * <span data-ttu-id="a4b39-170">IBAN</span><span class="sxs-lookup"><span data-stu-id="a4b39-170">IBAN</span></span>  
21. <span data-ttu-id="a4b39-171">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-171">Click OK.</span></span>
    * <span data-ttu-id="a4b39-172">Den har konfigurerats att varje rad i parsningfilen innehåller den enda IBAN-koden.</span><span class="sxs-lookup"><span data-stu-id="a4b39-172">It has been configured that each line in the parsing file contains the only IBAN code.</span></span>  
22. <span data-ttu-id="a4b39-173">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4b39-173">Click Save.</span></span>

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a><span data-ttu-id="a4b39-174">Designa ER-formatkonfigurationen – mappa till datamodellen</span><span class="sxs-lookup"><span data-stu-id="a4b39-174">Design the ER format configuration – mapping to data model</span></span>
1. <span data-ttu-id="a4b39-175">Klicka på Mappa format till modell.</span><span class="sxs-lookup"><span data-stu-id="a4b39-175">Click Map format to model.</span></span>
2. <span data-ttu-id="a4b39-176">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4b39-176">Click New.</span></span>
3. <span data-ttu-id="a4b39-177">I fältet Definition anger du "BankToCustomerDebitCreditNotificationInitiation".</span><span class="sxs-lookup"><span data-stu-id="a4b39-177">In the Definition field, type 'BankToCustomerDebitCreditNotificationInitiation'.</span></span>
    * <span data-ttu-id="a4b39-178">BankToCustomerDebitCreditNotificationInitiation</span><span class="sxs-lookup"><span data-stu-id="a4b39-178">BankToCustomerDebitCreditNotificationInitiation</span></span>  
4. <span data-ttu-id="a4b39-179">ResolveChanges the Definition.</span><span class="sxs-lookup"><span data-stu-id="a4b39-179">ResolveChanges the Definition.</span></span>
5. <span data-ttu-id="a4b39-180">Skriv "Mappning till datamodell" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-180">In the Name field, type 'Mapping to data model'.</span></span>
    * <span data-ttu-id="a4b39-181">Datamodellmappning</span><span class="sxs-lookup"><span data-stu-id="a4b39-181">Mapping to data model</span></span>  
6. <span data-ttu-id="a4b39-182">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4b39-182">Click Save.</span></span>
7. <span data-ttu-id="a4b39-183">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="a4b39-183">Click Designer.</span></span>
8. <span data-ttu-id="a4b39-184">Välj "Dynamics 365 for Operations\Class" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-184">In the tree, select 'Dynamics 365 for Operations\Class'.</span></span>
9. <span data-ttu-id="a4b39-185">Klicka på Lägg till rot.</span><span class="sxs-lookup"><span data-stu-id="a4b39-185">Click Add root.</span></span>
    * <span data-ttu-id="a4b39-186">Lägg till en ny datakälla för att öppna befintliga programlogik för validering av IBAN koder.</span><span class="sxs-lookup"><span data-stu-id="a4b39-186">Add a new data source to call the existing application logic for IBAN codes validation.</span></span>  
10. <span data-ttu-id="a4b39-187">Ange "Checkkoder" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-187">In the Name field, type 'check_codes'.</span></span>
    * <span data-ttu-id="a4b39-188">checkkoder</span><span class="sxs-lookup"><span data-stu-id="a4b39-188">check_codes</span></span>  
11. <span data-ttu-id="a4b39-189">I fältet Klass skriver du "ISO7064".</span><span class="sxs-lookup"><span data-stu-id="a4b39-189">In the Class field, type 'ISO7064'.</span></span>
    * <span data-ttu-id="a4b39-190">ISO7064</span><span class="sxs-lookup"><span data-stu-id="a4b39-190">ISO7064</span></span>  
12. <span data-ttu-id="a4b39-191">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-191">Click OK.</span></span>
13. <span data-ttu-id="a4b39-192">Expandera format i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-192">In the tree, expand 'format'.</span></span>
14. <span data-ttu-id="a4b39-193">Expandera "format\Root: Sequence(Root)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-193">In the tree, expand 'format\Root: Sequence(Root)'.</span></span>
15. <span data-ttu-id="a4b39-194">Välj "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-194">In the tree, select 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)'.</span></span>
16. <span data-ttu-id="a4b39-195">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="a4b39-195">Click Bind.</span></span>
17. <span data-ttu-id="a4b39-196">Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-196">In the tree, expand 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)'.</span></span>
18. <span data-ttu-id="a4b39-197">Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-197">In the tree, expand 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)'.</span></span>
19. <span data-ttu-id="a4b39-198">Välj "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-198">In the tree, select 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.</span></span>
20. <span data-ttu-id="a4b39-199">Expandera "Payments = format.Root.Rows" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-199">In the tree, expand 'Payments = format.Root.Rows'.</span></span>
21. <span data-ttu-id="a4b39-200">Expandera "Payments = format.Root.Rows\Creditor Account(CreditorAccount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-200">In the tree, expand 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)'.</span></span>
22. <span data-ttu-id="a4b39-201">Expandera "Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-201">In the tree, expand 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification'.</span></span>
23. <span data-ttu-id="a4b39-202">Välj "Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-202">In the tree, select 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN'.</span></span>
24. <span data-ttu-id="a4b39-203">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="a4b39-203">Click Bind.</span></span>
25. <span data-ttu-id="a4b39-204">Klicka på fliken Valideringar.</span><span class="sxs-lookup"><span data-stu-id="a4b39-204">Click the Validations tab.</span></span>
26. <span data-ttu-id="a4b39-205">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a4b39-205">Click New.</span></span>
    * <span data-ttu-id="a4b39-206">Lägg till en ny valideringsregel som visar ett felmeddelande för varje rad i filen som innehåller ogiltig IBAN-kod.</span><span class="sxs-lookup"><span data-stu-id="a4b39-206">Add a new validation rule that displays an error for any line in the parsing file that contains invalid IBAN code.</span></span>  
27. <span data-ttu-id="a4b39-207">Klicka på Edit condition.</span><span class="sxs-lookup"><span data-stu-id="a4b39-207">Click Edit condition.</span></span>
28. <span data-ttu-id="a4b39-208">Expandera "checkkoder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-208">In the tree, expand 'check_codes'.</span></span>
29. <span data-ttu-id="a4b39-209">Välj "check_codes\verifyMOD1271_36" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-209">In the tree, select 'check_codes\verifyMOD1271_36'.</span></span>
30. <span data-ttu-id="a4b39-210">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a4b39-210">Click Add data source.</span></span>
31. <span data-ttu-id="a4b39-211">I formelfältet anger du "check_codes.verifyMOD1271_36(".</span><span class="sxs-lookup"><span data-stu-id="a4b39-211">In the Formula field, enter 'check_codes.verifyMOD1271_36('.</span></span>
    * <span data-ttu-id="a4b39-212">check_codes.verifyMOD1271_36(</span><span class="sxs-lookup"><span data-stu-id="a4b39-212">check_codes.verifyMOD1271_36(</span></span>  
32. <span data-ttu-id="a4b39-213">Expandera format i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-213">In the tree, expand 'format'.</span></span>
33. <span data-ttu-id="a4b39-214">Expandera "format\Root: Sequence(Root)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-214">In the tree, expand 'format\Root: Sequence(Root)'.</span></span>
34. <span data-ttu-id="a4b39-215">Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-215">In the tree, expand 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)'.</span></span>
35. <span data-ttu-id="a4b39-216">Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-216">In the tree, expand 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)'.</span></span>
36. <span data-ttu-id="a4b39-217">Välj "format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="a4b39-217">In the tree, select 'format\Root: Sequence(Root)\Rows: Sequence 1..\* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.</span></span>
37. <span data-ttu-id="a4b39-218">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="a4b39-218">Click Add data source.</span></span>
38. <span data-ttu-id="a4b39-219">I formelfältet anger du "check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)".</span><span class="sxs-lookup"><span data-stu-id="a4b39-219">In the Formula field, enter 'check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)'.</span></span>
    * <span data-ttu-id="a4b39-220">check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)</span><span class="sxs-lookup"><span data-stu-id="a4b39-220">check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)</span></span>  
39. <span data-ttu-id="a4b39-221">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4b39-221">Click Save.</span></span>
40. <span data-ttu-id="a4b39-222">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-222">Close the page.</span></span>
    * <span data-ttu-id="a4b39-223">Valideringsvillkoren har konfigurerats för att returnera FALSE för någon ogiltig IBAN-kod genom att kalla den befintliga metoden "verifyMOD1271_36" av programklassen "ISO7064".</span><span class="sxs-lookup"><span data-stu-id="a4b39-223">The validation condition has been configured to return FALSE for any invalid IBAN code by calling the existing method ‘verifyMOD1271_36’ of the application class ‘ISO7064’.</span></span> <span data-ttu-id="a4b39-224">Observera att värdet i IBAN-koden definieras dynamiskt vid körning som argument för att anropa metoden baserat på innehållet i parsning TXT-fil.</span><span class="sxs-lookup"><span data-stu-id="a4b39-224">Note that the value of the IBAN code is defined dynamically at run-time as the argument of the calling method based on the content of the parsing TXT file.</span></span>   
41. <span data-ttu-id="a4b39-225">Klicka på Redigera meddelande.</span><span class="sxs-lookup"><span data-stu-id="a4b39-225">Click Edit message.</span></span>
42. <span data-ttu-id="a4b39-226">I formelfältet anger du "'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)".</span><span class="sxs-lookup"><span data-stu-id="a4b39-226">In the Formula field, enter 'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)'.</span></span>
    * <span data-ttu-id="a4b39-227">CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)</span><span class="sxs-lookup"><span data-stu-id="a4b39-227">CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)</span></span>  
43. <span data-ttu-id="a4b39-228">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4b39-228">Click Save.</span></span>
44. <span data-ttu-id="a4b39-229">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-229">Close the page.</span></span>
45. <span data-ttu-id="a4b39-230">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a4b39-230">Click Save.</span></span>
46. <span data-ttu-id="a4b39-231">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a4b39-231">Close the page.</span></span>

## <a name="run-the-format-mapping"></a><span data-ttu-id="a4b39-232">Kör mappning av filformat</span><span class="sxs-lookup"><span data-stu-id="a4b39-232">Run the format mapping</span></span>
<span data-ttu-id="a4b39-233">För testningsändamål, utför formatmappning med den SampleIncomingMessage.txt-fil som du tidigare hämtade.</span><span class="sxs-lookup"><span data-stu-id="a4b39-233">For testing purposes, execute the format mapping using the SampleIncomingMessage.txt file that you downloaded.</span></span> <span data-ttu-id="a4b39-234">Genererade utdata kommer att inkludera data som importeras från den valda TXT-filen och fyller i den anpassade datamodellen när den verkliga importen sker.</span><span class="sxs-lookup"><span data-stu-id="a4b39-234">The generated output includes data that will be imported from the selected TXT file and populated to the custom data model during the real import.</span></span>   
1. <span data-ttu-id="a4b39-235">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="a4b39-235">Click Run.</span></span>
    * <span data-ttu-id="a4b39-236">Klicka på Bläddra och navigera till filen SampleIncomingMessage.txt som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a4b39-236">Click Browse and navigate to the SampleIncomingMessage.txt file that you previously downloaded.</span></span>  
2. <span data-ttu-id="a4b39-237">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a4b39-237">Click OK.</span></span>
    * <span data-ttu-id="a4b39-238">Granska utdata i XML-format, vilket representerar de data som har importerats från den valda filen och integrerats i datamodellen.</span><span class="sxs-lookup"><span data-stu-id="a4b39-238">Review the output in XML format that represents the data that has been imported from the selected file and ported to the data model.</span></span> <span data-ttu-id="a4b39-239">Observera att endast 3 raderna i importerade TXT-filen har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="a4b39-239">Note that only 3 lines of the imported TXT file were processed.</span></span> <span data-ttu-id="a4b39-240">IBAN-kod på rad 4 som inte gäller hoppades över och ett felmeddelande ges i informationsloggen.</span><span class="sxs-lookup"><span data-stu-id="a4b39-240">The IBAN code on line 4 that is not valid was skipped and an error message is provided in the Infolog.</span></span>  


