---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering för att använda dokumenthanteringsfiler i ER-utmatningar.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 618fabc96bdfeb0c2b577aa686702d9f1257ed70
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550727"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="14326-103">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)</span><span class="sxs-lookup"><span data-stu-id="14326-103">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14326-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="14326-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="14326-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="14326-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="14326-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use Document Management files in format outputs (Part 2: Extend data model".</span><span class="sxs-lookup"><span data-stu-id="14326-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="14326-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="14326-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="14326-108">Skapa ett format för att bearbeta fakturor</span><span class="sxs-lookup"><span data-stu-id="14326-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="14326-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="14326-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="14326-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="14326-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="14326-111">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="14326-112">Välj "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="14326-113">Du kan skapa ett format för att skapa elektroniska meddelanden med information om de filer som har kopplats till en försäljningsorder och som gäller en faktura för elektronisk bearbetning.</span><span class="sxs-lookup"><span data-stu-id="14326-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="14326-114">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="14326-115">Ange "Format based on data model Customer invoice model (custom)" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="14326-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="14326-116">Ange "Electronic invoice sample message" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="14326-117">Provmeddelande för elektronisk faktura</span><span class="sxs-lookup"><span data-stu-id="14326-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="14326-118">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="14326-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="14326-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="14326-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="14326-120">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="14326-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="14326-121">Utforma ett format för att fylla i bilagor så att dessa skapar meddelanden i MIME-format</span><span class="sxs-lookup"><span data-stu-id="14326-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="14326-122">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="14326-122">Click Designer.</span></span>
2. <span data-ttu-id="14326-123">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="14326-124">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="14326-125">Ange "Invoice" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="14326-126">Faktura</span><span class="sxs-lookup"><span data-stu-id="14326-126">Invoice</span></span>  
5. <span data-ttu-id="14326-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-127">Click OK.</span></span>
6. <span data-ttu-id="14326-128">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="14326-129">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="14326-130">Ange "SalesOrder" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="14326-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="14326-131">SalesOrder</span></span>  
9. <span data-ttu-id="14326-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-132">Click OK.</span></span>
10. <span data-ttu-id="14326-133">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="14326-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="14326-134">Ange "InvoiceNumber" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="14326-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="14326-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="14326-136">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-136">Click OK.</span></span>
13. <span data-ttu-id="14326-137">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="14326-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="14326-138">Ange "InvoiceAmount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="14326-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="14326-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="14326-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-140">Click OK.</span></span>
16. <span data-ttu-id="14326-141">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="14326-142">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="14326-143">Ange "EnclosedDocs" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="14326-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="14326-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="14326-145">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-145">Click OK.</span></span>
20. <span data-ttu-id="14326-146">Välj "Invoice\EnclosedDocs" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="14326-147">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="14326-147">Click Add Element.</span></span>
22. <span data-ttu-id="14326-148">Ange "Document" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="14326-149">Dokument</span><span class="sxs-lookup"><span data-stu-id="14326-149">Document</span></span>  
23. <span data-ttu-id="14326-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-150">Click OK.</span></span>
24. <span data-ttu-id="14326-151">Välj "Invoice\EnclosedDocs\Document" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="14326-152">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="14326-153">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="14326-154">Ange "FileName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="14326-155">FileName</span><span class="sxs-lookup"><span data-stu-id="14326-155">FileName</span></span>  
28. <span data-ttu-id="14326-156">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-156">Click OK.</span></span>
29. <span data-ttu-id="14326-157">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="14326-158">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="14326-159">Ange "FileContent" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="14326-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="14326-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="14326-160">FileContent</span></span>  
32. <span data-ttu-id="14326-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-161">Click OK.</span></span>
33. <span data-ttu-id="14326-162">Välj "Invoice\EnclosedDocs\Document\FileContent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="14326-163">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="14326-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="14326-164">Välj "Text\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="14326-165">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="14326-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="14326-166">Mappa formatelement till datamodeller som datakällor</span><span class="sxs-lookup"><span data-stu-id="14326-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="14326-167">Välj "Invoice\SalesOrder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="14326-168">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="14326-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="14326-169">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="14326-170">Välj "model\Sales order number(SalesId)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="14326-171">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-171">Click Bind.</span></span>
6. <span data-ttu-id="14326-172">Välj "Invoice\InvoiceNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="14326-173">Expandera "model\Base invoice(InvoiceBase)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="14326-174">Välj "model\Base invoice(InvoiceBase)\Invoice number(Id)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="14326-175">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-175">Click Bind.</span></span>
10. <span data-ttu-id="14326-176">Välj "Invoice\InvoiceAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="14326-177">Välj "model\Base invoice(InvoiceBase)\Invoice amount(Amount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="14326-178">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-178">Click Bind.</span></span>
13. <span data-ttu-id="14326-179">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="14326-180">Välj "model\Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="14326-181">Välj "Invoice\EnclosedDocs\Document\FileContent\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="14326-182">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-182">Click Bind.</span></span>
17. <span data-ttu-id="14326-183">Välj "model\Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="14326-184">Välj "Invoice\EnclosedDocs\Document\FileName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="14326-185">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-185">Click Bind.</span></span>
20. <span data-ttu-id="14326-186">Välj "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="14326-187">Välj "Invoice\EnclosedDocs\Document" i trädet.</span><span class="sxs-lookup"><span data-stu-id="14326-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="14326-188">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="14326-188">Click Bind.</span></span>
23. <span data-ttu-id="14326-189">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="14326-189">Click Save.</span></span>
24. <span data-ttu-id="14326-190">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="14326-190">Close the page.</span></span>

