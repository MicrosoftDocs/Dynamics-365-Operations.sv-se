--- 
title: "Kör format som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="c7382-103">Kör format som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="c7382-103">Run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c7382-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="c7382-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="c7382-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="c7382-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="c7382-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 3: Create format)".</span><span class="sxs-lookup"><span data-stu-id="c7382-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="c7382-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="c7382-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="c7382-108">Lägg till nödvändiga bilagor för en försäljningsorder för en enstaka faktura</span><span class="sxs-lookup"><span data-stu-id="c7382-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="c7382-109">Gå till Kundreskontra > Fakturor > Öppna kundfakturor.</span><span class="sxs-lookup"><span data-stu-id="c7382-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="c7382-110">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="c7382-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c7382-111">Filtrera till exempel fältet Invoice med värdet "CIV-000148".</span><span class="sxs-lookup"><span data-stu-id="c7382-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="c7382-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="c7382-112">CIV-000148</span></span>  
3. <span data-ttu-id="c7382-113">Klicka för att följa vald fakturalänk.</span><span class="sxs-lookup"><span data-stu-id="c7382-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="c7382-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="c7382-114">CIV-000148</span></span>  
4. <span data-ttu-id="c7382-115">Klicka för att följa länken i fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="c7382-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="c7382-116">000148</span><span class="sxs-lookup"><span data-stu-id="c7382-116">000148</span></span>  
5. <span data-ttu-id="c7382-117">Välj alternativet Header i fältet Lines or header.</span><span class="sxs-lookup"><span data-stu-id="c7382-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="c7382-118">Markera Header om du vill ange att detta ska vara målet för att lägga till bilagor.</span><span class="sxs-lookup"><span data-stu-id="c7382-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="c7382-119">Klicka på Koppla.</span><span class="sxs-lookup"><span data-stu-id="c7382-119">Click Attach.</span></span>
    * <span data-ttu-id="c7382-120">Lägga till några filer som bilagor för den här försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="c7382-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="c7382-121">Använd filer av de dokumenttyper stöds av dokumenthanteringen (med filtilläggen DOCX, DPF, XML, JPG osv.).</span><span class="sxs-lookup"><span data-stu-id="c7382-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="c7382-122">Bläddra och välj de filer som ska bifogas och bearbetas vidare med den relaterade fakturan i det elektroniska meddelandet ER.</span><span class="sxs-lookup"><span data-stu-id="c7382-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="c7382-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c7382-123">Click New.</span></span>
8. <span data-ttu-id="c7382-124">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="c7382-124">Click File.</span></span>
9. <span data-ttu-id="c7382-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c7382-125">Click New.</span></span>
10. <span data-ttu-id="c7382-126">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="c7382-126">Click File.</span></span>
11. <span data-ttu-id="c7382-127">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c7382-127">Close the page.</span></span>
12. <span data-ttu-id="c7382-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c7382-128">Close the page.</span></span>
13. <span data-ttu-id="c7382-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c7382-129">Close the page.</span></span>
14. <span data-ttu-id="c7382-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c7382-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="c7382-131">Kör den tidsplanerade rapporten för den valda fakturan</span><span class="sxs-lookup"><span data-stu-id="c7382-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="c7382-132">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="c7382-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c7382-133">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c7382-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="c7382-134">Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="c7382-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="c7382-135">I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".</span><span class="sxs-lookup"><span data-stu-id="c7382-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="c7382-136">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="c7382-136">Click Run.</span></span>
6. <span data-ttu-id="c7382-137">Expandera avsnittet Records to include ().</span><span class="sxs-lookup"><span data-stu-id="c7382-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="c7382-138">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="c7382-138">Click Filter.</span></span>
8. <span data-ttu-id="c7382-139">Markera raden för kundfakturajournalen och fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="c7382-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="c7382-140">Ange "000148" i fältet Criteria.</span><span class="sxs-lookup"><span data-stu-id="c7382-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="c7382-141">Ange ordernumret 000148 i kriteriefältet "Sales order".</span><span class="sxs-lookup"><span data-stu-id="c7382-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="c7382-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c7382-142">Click OK.</span></span>
11. <span data-ttu-id="c7382-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c7382-143">Click OK.</span></span>
    * <span data-ttu-id="c7382-144">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="c7382-144">Review the generated output.</span></span> <span data-ttu-id="c7382-145">Notera att en enda XML-nod skapas för respektive bilaga.</span><span class="sxs-lookup"><span data-stu-id="c7382-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="c7382-146">Bilagans innehåll fylls i textformatet för XML-utleverans i MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="c7382-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  

