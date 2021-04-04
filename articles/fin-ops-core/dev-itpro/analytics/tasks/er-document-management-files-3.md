---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för användning av dokumenthanteringsfiler i ER-utdata. (Del 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1ebc15cd980734aebec63d6758404868c1e36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559759"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="22306-104">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)</span><span class="sxs-lookup"><span data-stu-id="22306-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="22306-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="22306-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="22306-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="22306-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="22306-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use Document Management files in format outputs (Part 2: Extend data model".</span><span class="sxs-lookup"><span data-stu-id="22306-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="22306-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="22306-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="22306-109">Skapa ett format för att bearbeta fakturor</span><span class="sxs-lookup"><span data-stu-id="22306-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="22306-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="22306-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="22306-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="22306-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="22306-112">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="22306-113">Välj "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="22306-114">Du kan skapa ett format för att skapa elektroniska meddelanden med information om de filer som har kopplats till en försäljningsorder och som gäller en faktura för elektronisk bearbetning.</span><span class="sxs-lookup"><span data-stu-id="22306-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="22306-115">Klicka på Skapa konfiguration om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="22306-116">Ange "Format based on data model Customer invoice model (custom)" i fältet New.</span><span class="sxs-lookup"><span data-stu-id="22306-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="22306-117">Ange "Electronic invoice sample message" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="22306-118">Provmeddelande för elektronisk faktura</span><span class="sxs-lookup"><span data-stu-id="22306-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="22306-119">Ange eller välj ett värde i fältet Data model definition.</span><span class="sxs-lookup"><span data-stu-id="22306-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="22306-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="22306-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="22306-121">Klicka på Skapa konfiguration.</span><span class="sxs-lookup"><span data-stu-id="22306-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="22306-122">Utforma ett format för att fylla i bilagor så att dessa skapar meddelanden i MIME-format</span><span class="sxs-lookup"><span data-stu-id="22306-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="22306-123">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="22306-123">Click Designer.</span></span>
2. <span data-ttu-id="22306-124">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="22306-125">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="22306-126">Ange "Invoice" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="22306-127">Faktura</span><span class="sxs-lookup"><span data-stu-id="22306-127">Invoice</span></span>  
5. <span data-ttu-id="22306-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-128">Click OK.</span></span>
6. <span data-ttu-id="22306-129">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="22306-130">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="22306-131">Ange "SalesOrder" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="22306-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="22306-132">SalesOrder</span></span>  
9. <span data-ttu-id="22306-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-133">Click OK.</span></span>
10. <span data-ttu-id="22306-134">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="22306-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="22306-135">Ange "InvoiceNumber" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="22306-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="22306-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="22306-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-137">Click OK.</span></span>
13. <span data-ttu-id="22306-138">Klicka på Add Attribute.</span><span class="sxs-lookup"><span data-stu-id="22306-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="22306-139">Ange "InvoiceAmount" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="22306-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="22306-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="22306-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-141">Click OK.</span></span>
16. <span data-ttu-id="22306-142">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="22306-143">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="22306-144">Ange "EnclosedDocs" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="22306-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="22306-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="22306-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-146">Click OK.</span></span>
20. <span data-ttu-id="22306-147">Välj "Invoice\EnclosedDocs" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="22306-148">Klicka på Add Element.</span><span class="sxs-lookup"><span data-stu-id="22306-148">Click Add Element.</span></span>
22. <span data-ttu-id="22306-149">Ange "Document" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="22306-150">Dokument</span><span class="sxs-lookup"><span data-stu-id="22306-150">Document</span></span>  
23. <span data-ttu-id="22306-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-151">Click OK.</span></span>
24. <span data-ttu-id="22306-152">Välj "Invoice\EnclosedDocs\Document" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="22306-153">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="22306-154">Välj "XML\Attribut" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="22306-155">Ange "FileName" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="22306-156">FileName</span><span class="sxs-lookup"><span data-stu-id="22306-156">FileName</span></span>  
28. <span data-ttu-id="22306-157">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-157">Click OK.</span></span>
29. <span data-ttu-id="22306-158">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="22306-159">Välj "XML\Element" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="22306-160">Ange "FileContent" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="22306-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="22306-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="22306-161">FileContent</span></span>  
32. <span data-ttu-id="22306-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-162">Click OK.</span></span>
33. <span data-ttu-id="22306-163">Välj "Invoice\EnclosedDocs\Document\FileContent" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="22306-164">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="22306-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="22306-165">Välj "Text\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="22306-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="22306-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="22306-167">Mappa formatelement till datamodeller som datakällor</span><span class="sxs-lookup"><span data-stu-id="22306-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="22306-168">Välj "Invoice\SalesOrder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="22306-169">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="22306-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="22306-170">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="22306-171">Välj "model\Sales order number(SalesId)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="22306-172">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-172">Click Bind.</span></span>
6. <span data-ttu-id="22306-173">Välj "Invoice\InvoiceNumber" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="22306-174">Expandera "model\Base invoice(InvoiceBase)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="22306-175">Välj "model\Base invoice(InvoiceBase)\Invoice number(Id)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="22306-176">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-176">Click Bind.</span></span>
10. <span data-ttu-id="22306-177">Välj "Invoice\InvoiceAmount" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="22306-178">Välj "model\Base invoice(InvoiceBase)\Invoice amount(Amount)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="22306-179">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-179">Click Bind.</span></span>
13. <span data-ttu-id="22306-180">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="22306-181">Välj "model\Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="22306-182">Välj "Invoice\EnclosedDocs\Document\FileContent\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="22306-183">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-183">Click Bind.</span></span>
17. <span data-ttu-id="22306-184">Välj "model\Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="22306-185">Välj "Invoice\EnclosedDocs\Document\FileName" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="22306-186">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-186">Click Bind.</span></span>
20. <span data-ttu-id="22306-187">Välj "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="22306-188">Välj "Invoice\EnclosedDocs\Document" i trädet.</span><span class="sxs-lookup"><span data-stu-id="22306-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="22306-189">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="22306-189">Click Bind.</span></span>
23. <span data-ttu-id="22306-190">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="22306-190">Click Save.</span></span>
24. <span data-ttu-id="22306-191">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="22306-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]