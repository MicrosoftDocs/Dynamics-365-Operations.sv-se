---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 4 - Kör format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för användning av dokumenthanteringsfiler i ER-utdata. (Del 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a7c9705d8b53ef13cd3faf13290f3f1b1d1c43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749127"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="0b42a-104">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 4 - Kör format)</span><span class="sxs-lookup"><span data-stu-id="0b42a-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b42a-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="0b42a-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="0b42a-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="0b42a-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="0b42a-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 3: Create format)".</span><span class="sxs-lookup"><span data-stu-id="0b42a-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="0b42a-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="0b42a-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="0b42a-109">Lägg till nödvändiga bilagor för en försäljningsorder för en enstaka faktura</span><span class="sxs-lookup"><span data-stu-id="0b42a-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="0b42a-110">Gå till Kundreskontra > Fakturor > Öppna kundfakturor.</span><span class="sxs-lookup"><span data-stu-id="0b42a-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="0b42a-111">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="0b42a-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0b42a-112">Filtrera till exempel fältet Invoice med värdet "CIV-000148".</span><span class="sxs-lookup"><span data-stu-id="0b42a-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="0b42a-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="0b42a-113">CIV-000148</span></span>  
3. <span data-ttu-id="0b42a-114">Klicka för att följa vald fakturalänk.</span><span class="sxs-lookup"><span data-stu-id="0b42a-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="0b42a-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="0b42a-115">CIV-000148</span></span>  
4. <span data-ttu-id="0b42a-116">Klicka för att följa länken i fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="0b42a-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="0b42a-117">000148</span><span class="sxs-lookup"><span data-stu-id="0b42a-117">000148</span></span>  
5. <span data-ttu-id="0b42a-118">Välj alternativet Header i fältet Lines or header.</span><span class="sxs-lookup"><span data-stu-id="0b42a-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="0b42a-119">Markera Header om du vill ange att detta ska vara målet för att lägga till bilagor.</span><span class="sxs-lookup"><span data-stu-id="0b42a-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="0b42a-120">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="0b42a-120">Click Attach.</span></span>
    * <span data-ttu-id="0b42a-121">Lägga till några filer som bilagor för den här försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="0b42a-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="0b42a-122">Använd filer av de dokumenttyper stöds av dokumenthanteringen (med filtilläggen DOCX, DPF, XML, JPG osv.).</span><span class="sxs-lookup"><span data-stu-id="0b42a-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="0b42a-123">Bläddra och välj de filer som ska bifogas och bearbetas vidare med den relaterade fakturan i det elektroniska meddelandet ER.</span><span class="sxs-lookup"><span data-stu-id="0b42a-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="0b42a-124">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0b42a-124">Click New.</span></span>
8. <span data-ttu-id="0b42a-125">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="0b42a-125">Click File.</span></span>
9. <span data-ttu-id="0b42a-126">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0b42a-126">Click New.</span></span>
10. <span data-ttu-id="0b42a-127">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="0b42a-127">Click File.</span></span>
11. <span data-ttu-id="0b42a-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0b42a-128">Close the page.</span></span>
12. <span data-ttu-id="0b42a-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0b42a-129">Close the page.</span></span>
13. <span data-ttu-id="0b42a-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0b42a-130">Close the page.</span></span>
14. <span data-ttu-id="0b42a-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0b42a-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="0b42a-132">Kör den tidsplanerade rapporten för den valda fakturan</span><span class="sxs-lookup"><span data-stu-id="0b42a-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="0b42a-133">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="0b42a-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="0b42a-134">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="0b42a-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="0b42a-135">Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="0b42a-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="0b42a-136">I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".</span><span class="sxs-lookup"><span data-stu-id="0b42a-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="0b42a-137">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="0b42a-137">Click Run.</span></span>
6. <span data-ttu-id="0b42a-138">Expandera avsnittet Records to include ().</span><span class="sxs-lookup"><span data-stu-id="0b42a-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="0b42a-139">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="0b42a-139">Click Filter.</span></span>
8. <span data-ttu-id="0b42a-140">Markera raden för kundfakturajournalen och fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="0b42a-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="0b42a-141">Ange "000148" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="0b42a-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="0b42a-142">Ange ordernumret 000148 i kriteriefältet "Sales order".</span><span class="sxs-lookup"><span data-stu-id="0b42a-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="0b42a-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0b42a-143">Click OK.</span></span>
11. <span data-ttu-id="0b42a-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0b42a-144">Click OK.</span></span>
    * <span data-ttu-id="0b42a-145">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="0b42a-145">Review the generated output.</span></span> <span data-ttu-id="0b42a-146">Notera att en enda XML-nod skapas för respektive bilaga.</span><span class="sxs-lookup"><span data-stu-id="0b42a-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="0b42a-147">Bilagans innehåll fylls i textformatet för XML-utleverans i MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="0b42a-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]