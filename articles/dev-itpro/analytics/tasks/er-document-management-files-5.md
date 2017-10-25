--- 
title: "Ändra och kör format som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)"
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
ms.openlocfilehash: 76915a7294e078d76ed3ca9c41755e12b0791f3c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="198af-103">Ändra och kör format som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="198af-103">Modify and run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="198af-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="198af-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="198af-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="198af-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="198af-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 4): Run format".</span><span class="sxs-lookup"><span data-stu-id="198af-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="198af-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="198af-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="198af-108">Ändra formatet för att fylla i bilagor så att dessa genererar meddelanden i binärt format</span><span class="sxs-lookup"><span data-stu-id="198af-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="198af-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="198af-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="198af-110">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="198af-111">Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="198af-112">I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".</span><span class="sxs-lookup"><span data-stu-id="198af-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="198af-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="198af-113">Click Designer.</span></span>
    * <span data-ttu-id="198af-114">Du fyller i fakturameddelandet i genererad utmatning som en XML-fil med hjälp av UNICODE-kodning.</span><span class="sxs-lookup"><span data-stu-id="198af-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="198af-115">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="198af-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="198af-116">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="198af-117">Ange "Xml message" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="198af-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="198af-118">Xml-meddelande</span><span class="sxs-lookup"><span data-stu-id="198af-118">Xml message</span></span>  
9. <span data-ttu-id="198af-119">Skriv "UTF 8" i fältet Kodning.</span><span class="sxs-lookup"><span data-stu-id="198af-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="198af-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="198af-120">UTF-8</span></span>  
10. <span data-ttu-id="198af-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-121">Click OK.</span></span>
    * <span data-ttu-id="198af-122">Konfigurera de genererade utmatningen som en zippad fil.</span><span class="sxs-lookup"><span data-stu-id="198af-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="198af-123">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="198af-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="198af-124">Välj "Common\Folder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="198af-125">Ange "Zip output" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="198af-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="198af-126">Zip-utleverans</span><span class="sxs-lookup"><span data-stu-id="198af-126">Zip output</span></span>  
14. <span data-ttu-id="198af-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-127">Click OK.</span></span>
15. <span data-ttu-id="198af-128">Välj "Zip output" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="198af-129">Lägg till bilagor till den genererade, zippade filen som filer med ursprungliga namn och filtillägg.</span><span class="sxs-lookup"><span data-stu-id="198af-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="198af-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="198af-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="198af-131">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="198af-132">Ange "Attached file" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="198af-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="198af-133">Bifogad fil</span><span class="sxs-lookup"><span data-stu-id="198af-133">Attached file</span></span>  
19. <span data-ttu-id="198af-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-134">Click OK.</span></span>
20. <span data-ttu-id="198af-135">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="198af-136">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="198af-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="198af-137">Välj "Text\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="198af-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="198af-139">Mappa nya formatelement till datamodell</span><span class="sxs-lookup"><span data-stu-id="198af-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="198af-140">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="198af-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="198af-141">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="198af-142">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="198af-143">Välj "Zip output\Attached file\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="198af-144">Välj "model\Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="198af-145">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="198af-145">Click Bind.</span></span>
7. <span data-ttu-id="198af-146">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="198af-147">Klick på Edit filename.</span><span class="sxs-lookup"><span data-stu-id="198af-147">Click Edit filename.</span></span>
9. <span data-ttu-id="198af-148">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="198af-149">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="198af-150">Välj "model\Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="198af-151">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="198af-151">Click Add data source.</span></span>
13. <span data-ttu-id="198af-152">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="198af-152">Click Save.</span></span>
14. <span data-ttu-id="198af-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="198af-153">Close the page.</span></span>
15. <span data-ttu-id="198af-154">Välj "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="198af-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="198af-155">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="198af-155">Click Bind.</span></span>
17. <span data-ttu-id="198af-156">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="198af-156">Click Save.</span></span>
18. <span data-ttu-id="198af-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="198af-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="198af-158">Kör den tidsplanerade rapporten för den valda fakturan</span><span class="sxs-lookup"><span data-stu-id="198af-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="198af-159">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="198af-159">Click Run.</span></span>
2. <span data-ttu-id="198af-160">Expandera avsnittet Records to include ().</span><span class="sxs-lookup"><span data-stu-id="198af-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="198af-161">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="198af-161">Click Filter.</span></span>
4. <span data-ttu-id="198af-162">Markera raden för kundfakturajournalen och fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="198af-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="198af-163">Ange ordernummer "000148" i fältet Criteria, i kriteriefältet "Sales order".</span><span class="sxs-lookup"><span data-stu-id="198af-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="198af-164">000148</span><span class="sxs-lookup"><span data-stu-id="198af-164">000148</span></span>  
6. <span data-ttu-id="198af-165">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-165">Click OK.</span></span>
7. <span data-ttu-id="198af-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="198af-166">Click OK.</span></span>
    * <span data-ttu-id="198af-167">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="198af-167">Review the generated output.</span></span> <span data-ttu-id="198af-168">Notera att: Utöver fakturameddelandet i XML-format har en enda fil skapats för respektive bilaga.</span><span class="sxs-lookup"><span data-stu-id="198af-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="198af-169">Bilagefilerna fylls i med den zippade utmatningen i binärt format.</span><span class="sxs-lookup"><span data-stu-id="198af-169">The attachment files are populated with the zipped output in binary format.</span></span>  

