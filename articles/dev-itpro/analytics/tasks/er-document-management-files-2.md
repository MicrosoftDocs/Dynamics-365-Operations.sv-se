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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "320959"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2-extend-data-model"></a><span data-ttu-id="aec4a-103">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2: Utöka datamodellen)</span><span class="sxs-lookup"><span data-stu-id="aec4a-103">ER Use Document Management files in format outputs (Part 2: Extend data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aec4a-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="aec4a-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="aec4a-105">Dessa steg kan utföras på valfritt företag.</span><span class="sxs-lookup"><span data-stu-id="aec4a-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="aec4a-106">För att slutföra dessa steg måste du först avsluta stegen i uppgiftsguiden "ER Use Document Management files in format outputs (Part 1: Prepare data model)".</span><span class="sxs-lookup"><span data-stu-id="aec4a-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="aec4a-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="aec4a-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="aec4a-108">Utöka datamodellen för att presentera dokumenthanteringsfilerna i den</span><span class="sxs-lookup"><span data-stu-id="aec4a-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="aec4a-109">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="aec4a-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="aec4a-110">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="aec4a-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="aec4a-111">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="aec4a-112">Välj "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="aec4a-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="aec4a-113">Click Designer.</span></span>
6. <span data-ttu-id="aec4a-114">Välj "Customer invoice(InvoiceCustomer)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="aec4a-115">Vi vill utöka den här datamodell till blottan i den vissa filer som har kopplats till en försäljningsorder, som gäller bearbeta en faktura elektroniskt.</span><span class="sxs-lookup"><span data-stu-id="aec4a-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="aec4a-116">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="aec4a-117">Ange "Invoice attachments" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="aec4a-118">Fakturabilagor</span><span class="sxs-lookup"><span data-stu-id="aec4a-118">Invoice attachments</span></span>  
9. <span data-ttu-id="aec4a-119">Välj "Postlista" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="aec4a-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="aec4a-120">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="aec4a-120">Click Add.</span></span>
11. <span data-ttu-id="aec4a-121">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="aec4a-122">Ange "File content" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="aec4a-123">Filinnehåll</span><span class="sxs-lookup"><span data-stu-id="aec4a-123">File content</span></span>  
13. <span data-ttu-id="aec4a-124">Välj "Container" i fältet Item type.</span><span class="sxs-lookup"><span data-stu-id="aec4a-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="aec4a-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="aec4a-125">Click Add.</span></span>
15. <span data-ttu-id="aec4a-126">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="aec4a-127">Ange "File name" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="aec4a-128">Filnamn</span><span class="sxs-lookup"><span data-stu-id="aec4a-128">File name</span></span>  
17. <span data-ttu-id="aec4a-129">Välj "Sträng" i fältet Artikeltyp.</span><span class="sxs-lookup"><span data-stu-id="aec4a-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="aec4a-130">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="aec4a-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="aec4a-131">Mappa nya datamodellelement till Dynamics 365 for Finance and Operations, Enterprise Edition-datakällor</span><span class="sxs-lookup"><span data-stu-id="aec4a-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="aec4a-132">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="aec4a-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="aec4a-133">Använd snabbfiltret (Quick Filter) för att filtrera fältet Definition med värdet "InvoiceCustomer".</span><span class="sxs-lookup"><span data-stu-id="aec4a-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="aec4a-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="aec4a-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="aec4a-135">Vi skapar nya modellelement till lämpliga datakällor.</span><span class="sxs-lookup"><span data-stu-id="aec4a-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="aec4a-136">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="aec4a-136">Click Designer.</span></span>
4. <span data-ttu-id="aec4a-137">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="aec4a-138">Expandera "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="aec4a-139">Välj "Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="aec4a-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="aec4a-140">Click Edit.</span></span>
8. <span data-ttu-id="aec4a-141">Ange "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()" i fromelfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="aec4a-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="aec4a-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="aec4a-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aec4a-143">Click Save.</span></span>
10. <span data-ttu-id="aec4a-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-144">Close the page.</span></span>
11. <span data-ttu-id="aec4a-145">Välj "Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="aec4a-146">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="aec4a-146">Click Edit.</span></span>
13. <span data-ttu-id="aec4a-147">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="aec4a-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="aec4a-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="aec4a-149">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aec4a-149">Click Save.</span></span>
15. <span data-ttu-id="aec4a-150">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-150">Close the page.</span></span>
16. <span data-ttu-id="aec4a-151">Välj "Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="aec4a-152">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="aec4a-152">Click Edit.</span></span>
18. <span data-ttu-id="aec4a-153">Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'' i formelfältet.</span><span class="sxs-lookup"><span data-stu-id="aec4a-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="aec4a-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="aec4a-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="aec4a-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aec4a-155">Click Save.</span></span>
20. <span data-ttu-id="aec4a-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-156">Close the page.</span></span>
21. <span data-ttu-id="aec4a-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aec4a-157">Click Save.</span></span>
22. <span data-ttu-id="aec4a-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-158">Close the page.</span></span>
23. <span data-ttu-id="aec4a-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-159">Close the page.</span></span>
24. <span data-ttu-id="aec4a-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aec4a-160">Close the page.</span></span>
25. <span data-ttu-id="aec4a-161">Klicka på Ändra status.</span><span class="sxs-lookup"><span data-stu-id="aec4a-161">Click Change status.</span></span>
26. <span data-ttu-id="aec4a-162">Klicka på Slutför.</span><span class="sxs-lookup"><span data-stu-id="aec4a-162">Click Complete.</span></span>
27. <span data-ttu-id="aec4a-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="aec4a-163">Click OK.</span></span>

