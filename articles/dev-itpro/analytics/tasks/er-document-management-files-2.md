---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2 - Utöka datamodellen)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb4c58dc86a159a70634c05408a8db471ebcae4c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544825"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2-extend-data-model"></a><span data-ttu-id="46d8f-103">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2: Utöka datamodellen)</span><span class="sxs-lookup"><span data-stu-id="46d8f-103">ER Use Document Management files in format outputs (Part 2: Extend data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46d8f-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="46d8f-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="46d8f-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="46d8f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="46d8f-106">För att slutföra dessa steg måste du först avsluta stegen i uppgiftsguiden "ER Use Document Management files in format outputs (Part 1: Prepare data model)".</span><span class="sxs-lookup"><span data-stu-id="46d8f-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="46d8f-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="46d8f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="46d8f-108">Utöka datamodellen för att presentera dokumenthanteringsfilerna i den</span><span class="sxs-lookup"><span data-stu-id="46d8f-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="46d8f-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="46d8f-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="46d8f-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="46d8f-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="46d8f-111">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="46d8f-112">Välj "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="46d8f-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="46d8f-113">Click Designer.</span></span>
6. <span data-ttu-id="46d8f-114">Välj "Customer invoice(InvoiceCustomer)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="46d8f-115">Vi vill utöka den här datamodell till blottan i den vissa filer som har kopplats till en försäljningsorder, som gäller bearbeta en faktura elektroniskt.</span><span class="sxs-lookup"><span data-stu-id="46d8f-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="46d8f-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="46d8f-117">Ange "Invoice attachments" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="46d8f-118">Fakturabilagor</span><span class="sxs-lookup"><span data-stu-id="46d8f-118">Invoice attachments</span></span>  
9. <span data-ttu-id="46d8f-119">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="46d8f-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="46d8f-120">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="46d8f-120">Click Add.</span></span>
11. <span data-ttu-id="46d8f-121">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="46d8f-122">Ange "File content" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="46d8f-123">Filinnehåll</span><span class="sxs-lookup"><span data-stu-id="46d8f-123">File content</span></span>  
13. <span data-ttu-id="46d8f-124">Välj "Container" i fältet Item type.</span><span class="sxs-lookup"><span data-stu-id="46d8f-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="46d8f-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="46d8f-125">Click Add.</span></span>
15. <span data-ttu-id="46d8f-126">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="46d8f-127">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="46d8f-128">Filnamn</span><span class="sxs-lookup"><span data-stu-id="46d8f-128">File name</span></span>  
17. <span data-ttu-id="46d8f-129">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="46d8f-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="46d8f-130">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="46d8f-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="46d8f-131">Mappa nya datamodellelement till Dynamics 365 for Finance and Operations, Enterprise Edition-datakällor</span><span class="sxs-lookup"><span data-stu-id="46d8f-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="46d8f-132">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="46d8f-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="46d8f-133">Använd snabbfiltret (Quick Filter) för att filtrera fältet Definition med värdet "InvoiceCustomer".</span><span class="sxs-lookup"><span data-stu-id="46d8f-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="46d8f-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="46d8f-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="46d8f-135">Vi skapar nya modellelement till lämpliga datakällor.</span><span class="sxs-lookup"><span data-stu-id="46d8f-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="46d8f-136">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="46d8f-136">Click Designer.</span></span>
4. <span data-ttu-id="46d8f-137">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="46d8f-138">Expandera "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="46d8f-139">Välj "Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="46d8f-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="46d8f-140">Click Edit.</span></span>
8. <span data-ttu-id="46d8f-141">Ange "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()" i fromelfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="46d8f-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="46d8f-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="46d8f-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46d8f-143">Click Save.</span></span>
10. <span data-ttu-id="46d8f-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-144">Close the page.</span></span>
11. <span data-ttu-id="46d8f-145">Välj "Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="46d8f-146">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="46d8f-146">Click Edit.</span></span>
13. <span data-ttu-id="46d8f-147">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="46d8f-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="46d8f-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="46d8f-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46d8f-149">Click Save.</span></span>
15. <span data-ttu-id="46d8f-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-150">Close the page.</span></span>
16. <span data-ttu-id="46d8f-151">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="46d8f-152">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="46d8f-152">Click Edit.</span></span>
18. <span data-ttu-id="46d8f-153">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="46d8f-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="46d8f-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="46d8f-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="46d8f-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46d8f-155">Click Save.</span></span>
20. <span data-ttu-id="46d8f-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-156">Close the page.</span></span>
21. <span data-ttu-id="46d8f-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="46d8f-157">Click Save.</span></span>
22. <span data-ttu-id="46d8f-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-158">Close the page.</span></span>
23. <span data-ttu-id="46d8f-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-159">Close the page.</span></span>
24. <span data-ttu-id="46d8f-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="46d8f-160">Close the page.</span></span>
25. <span data-ttu-id="46d8f-161">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="46d8f-161">Click Change status.</span></span>
26. <span data-ttu-id="46d8f-162">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="46d8f-162">Click Complete.</span></span>
27. <span data-ttu-id="46d8f-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="46d8f-163">Click OK.</span></span>

