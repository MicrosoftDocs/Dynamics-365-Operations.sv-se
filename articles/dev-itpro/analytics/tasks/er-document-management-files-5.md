--- 
title: "Ändra och kör format för att använda dokumenthanteringsfiler i formatutmatningar"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1c8a71c76b81991e88097c6d043e6ac50b5a3ad9
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="97ac2-103">Ändra och kör format för att använda dokumenthanteringsfiler i formatutmatningar</span><span class="sxs-lookup"><span data-stu-id="97ac2-103">Modify and run format to use Document Management files in format outputs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97ac2-104">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="97ac2-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="97ac2-105">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="97ac2-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="97ac2-106">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 4): Run format".</span><span class="sxs-lookup"><span data-stu-id="97ac2-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="97ac2-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="97ac2-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="97ac2-108">Ändra formatet för att fylla i bilagor så att dessa genererar meddelanden i binärt format</span><span class="sxs-lookup"><span data-stu-id="97ac2-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="97ac2-109">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="97ac2-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="97ac2-110">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="97ac2-111">Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="97ac2-112">I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".</span><span class="sxs-lookup"><span data-stu-id="97ac2-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="97ac2-113">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="97ac2-113">Click Designer.</span></span>
    * <span data-ttu-id="97ac2-114">Du fyller i fakturameddelandet i genererad utmatning som en XML-fil med hjälp av UNICODE-kodning.</span><span class="sxs-lookup"><span data-stu-id="97ac2-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="97ac2-115">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="97ac2-116">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="97ac2-117">Ange "Xml message" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="97ac2-118">Xml-meddelande</span><span class="sxs-lookup"><span data-stu-id="97ac2-118">Xml message</span></span>  
9. <span data-ttu-id="97ac2-119">Skriv "UTF 8" i fältet Kodning.</span><span class="sxs-lookup"><span data-stu-id="97ac2-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="97ac2-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="97ac2-120">UTF-8</span></span>  
10. <span data-ttu-id="97ac2-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-121">Click OK.</span></span>
    * <span data-ttu-id="97ac2-122">Konfigurera de genererade utmatningen som en zippad fil.</span><span class="sxs-lookup"><span data-stu-id="97ac2-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="97ac2-123">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="97ac2-124">Välj "Common\Folder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="97ac2-125">Ange "Zip output" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="97ac2-126">Zip-utleverans</span><span class="sxs-lookup"><span data-stu-id="97ac2-126">Zip output</span></span>  
14. <span data-ttu-id="97ac2-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-127">Click OK.</span></span>
15. <span data-ttu-id="97ac2-128">Välj "Zip output" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="97ac2-129">Lägg till bilagor till den genererade, zippade filen som filer med ursprungliga namn och filtillägg.</span><span class="sxs-lookup"><span data-stu-id="97ac2-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="97ac2-130">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="97ac2-131">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="97ac2-132">Ange "Attached file" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="97ac2-133">Bifogad fil</span><span class="sxs-lookup"><span data-stu-id="97ac2-133">Attached file</span></span>  
19. <span data-ttu-id="97ac2-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-134">Click OK.</span></span>
20. <span data-ttu-id="97ac2-135">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="97ac2-136">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="97ac2-137">Välj "Text\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="97ac2-138">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="97ac2-139">Mappa nya formatelement till datamodell</span><span class="sxs-lookup"><span data-stu-id="97ac2-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="97ac2-140">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="97ac2-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="97ac2-141">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="97ac2-142">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="97ac2-143">Välj "Zip output\Attached file\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="97ac2-144">Välj "model\Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="97ac2-145">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97ac2-145">Click Bind.</span></span>
7. <span data-ttu-id="97ac2-146">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="97ac2-147">Klick på Edit filename.</span><span class="sxs-lookup"><span data-stu-id="97ac2-147">Click Edit filename.</span></span>
9. <span data-ttu-id="97ac2-148">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="97ac2-149">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="97ac2-150">Välj "model\Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="97ac2-151">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="97ac2-151">Click Add data source.</span></span>
13. <span data-ttu-id="97ac2-152">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97ac2-152">Click Save.</span></span>
14. <span data-ttu-id="97ac2-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-153">Close the page.</span></span>
15. <span data-ttu-id="97ac2-154">Välj "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="97ac2-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="97ac2-155">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="97ac2-155">Click Bind.</span></span>
17. <span data-ttu-id="97ac2-156">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="97ac2-156">Click Save.</span></span>
18. <span data-ttu-id="97ac2-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="97ac2-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="97ac2-158">Kör den tidsplanerade rapporten för den valda fakturan</span><span class="sxs-lookup"><span data-stu-id="97ac2-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="97ac2-159">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="97ac2-159">Click Run.</span></span>
2. <span data-ttu-id="97ac2-160">Expandera avsnittet Records to include ().</span><span class="sxs-lookup"><span data-stu-id="97ac2-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="97ac2-161">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="97ac2-161">Click Filter.</span></span>
4. <span data-ttu-id="97ac2-162">Markera raden för kundfakturajournalen och fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="97ac2-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="97ac2-163">Ange ordernummer "000148" i fältet Criteria, i kriteriefältet "Sales order".</span><span class="sxs-lookup"><span data-stu-id="97ac2-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="97ac2-164">000148</span><span class="sxs-lookup"><span data-stu-id="97ac2-164">000148</span></span>  
6. <span data-ttu-id="97ac2-165">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-165">Click OK.</span></span>
7. <span data-ttu-id="97ac2-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="97ac2-166">Click OK.</span></span>
    * <span data-ttu-id="97ac2-167">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="97ac2-167">Review the generated output.</span></span> <span data-ttu-id="97ac2-168">Notera att utöver fakturameddelandet i XML-format har en enda fil skapats för respektive bilaga.</span><span class="sxs-lookup"><span data-stu-id="97ac2-168">Note, in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="97ac2-169">Bilagefilerna fylls i med den zippade utmatningen i binärt format.</span><span class="sxs-lookup"><span data-stu-id="97ac2-169">The attachment files are populated with the zipped output in binary format.</span></span>  


