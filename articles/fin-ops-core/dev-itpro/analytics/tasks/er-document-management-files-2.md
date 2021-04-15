---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2 - Utöka datamodellen)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för användning av dokumenthanteringsfiler (bilagor) i ER-utdata. (Del 2)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e79dd0a6c68aa6ba7b857c31c9159c68543d93b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754924"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="9dfb7-104">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2 - Utöka datamodellen)</span><span class="sxs-lookup"><span data-stu-id="9dfb7-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9dfb7-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="9dfb7-106">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="9dfb7-107">För att slutföra dessa steg måste du först avsluta stegen i uppgiftsguiden "ER Use Document Management files in format outputs (Part 1: Prepare data model)".</span><span class="sxs-lookup"><span data-stu-id="9dfb7-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="9dfb7-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="9dfb7-109">Utöka datamodellen för att presentera dokumenthanteringsfilerna i den</span><span class="sxs-lookup"><span data-stu-id="9dfb7-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="9dfb7-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9dfb7-111">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9dfb7-112">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="9dfb7-113">Välj "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="9dfb7-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-114">Click Designer.</span></span>
6. <span data-ttu-id="9dfb7-115">Välj "Customer invoice(InvoiceCustomer)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="9dfb7-116">Vi vill utöka den här datamodell till blottan i den vissa filer som har kopplats till en försäljningsorder, som gäller bearbeta en faktura elektroniskt.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="9dfb7-117">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9dfb7-118">Ange "Invoice attachments" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="9dfb7-119">Fakturabilagor</span><span class="sxs-lookup"><span data-stu-id="9dfb7-119">Invoice attachments</span></span>  
9. <span data-ttu-id="9dfb7-120">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="9dfb7-121">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-121">Click Add.</span></span>
11. <span data-ttu-id="9dfb7-122">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9dfb7-123">Ange "File content" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="9dfb7-124">Filinnehåll</span><span class="sxs-lookup"><span data-stu-id="9dfb7-124">File content</span></span>  
13. <span data-ttu-id="9dfb7-125">Välj "Container" i fältet Item type.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="9dfb7-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-126">Click Add.</span></span>
15. <span data-ttu-id="9dfb7-127">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="9dfb7-128">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="9dfb7-129">Filnamn</span><span class="sxs-lookup"><span data-stu-id="9dfb7-129">File name</span></span>  
17. <span data-ttu-id="9dfb7-130">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="9dfb7-131">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="9dfb7-132">Mappa nya datamodellelement till datakällor</span><span class="sxs-lookup"><span data-stu-id="9dfb7-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="9dfb7-133">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="9dfb7-134">Använd snabbfiltret (Quick Filter) för att filtrera fältet Definition med värdet "InvoiceCustomer".</span><span class="sxs-lookup"><span data-stu-id="9dfb7-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="9dfb7-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="9dfb7-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="9dfb7-136">Vi skapar nya modellelement till lämpliga datakällor.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="9dfb7-137">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-137">Click Designer.</span></span>
4. <span data-ttu-id="9dfb7-138">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="9dfb7-139">Expandera "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="9dfb7-140">Välj "Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="9dfb7-141">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-141">Click Edit.</span></span>
8. <span data-ttu-id="9dfb7-142">Ange "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()" i fromelfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="9dfb7-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="9dfb7-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="9dfb7-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-144">Click Save.</span></span>
10. <span data-ttu-id="9dfb7-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-145">Close the page.</span></span>
11. <span data-ttu-id="9dfb7-146">Välj "Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="9dfb7-147">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-147">Click Edit.</span></span>
13. <span data-ttu-id="9dfb7-148">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="9dfb7-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="9dfb7-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="9dfb7-150">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-150">Click Save.</span></span>
15. <span data-ttu-id="9dfb7-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-151">Close the page.</span></span>
16. <span data-ttu-id="9dfb7-152">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="9dfb7-153">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-153">Click Edit.</span></span>
18. <span data-ttu-id="9dfb7-154">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="9dfb7-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="9dfb7-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="9dfb7-156">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-156">Click Save.</span></span>
20. <span data-ttu-id="9dfb7-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-157">Close the page.</span></span>
21. <span data-ttu-id="9dfb7-158">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-158">Click Save.</span></span>
22. <span data-ttu-id="9dfb7-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-159">Close the page.</span></span>
23. <span data-ttu-id="9dfb7-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-160">Close the page.</span></span>
24. <span data-ttu-id="9dfb7-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-161">Close the page.</span></span>
25. <span data-ttu-id="9dfb7-162">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-162">Click Change status.</span></span>
26. <span data-ttu-id="9dfb7-163">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-163">Click Complete.</span></span>
27. <span data-ttu-id="9dfb7-164">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9dfb7-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]