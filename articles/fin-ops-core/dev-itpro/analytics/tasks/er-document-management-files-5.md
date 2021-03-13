---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 5 - ändra och kör format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för användning av dokumenthanteringsfiler (bilagor) i ER-utdata. (Del 5)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f96189163d5ecac47ade9f713b3fd689e41352d0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092498"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="f63b8-104">ER Använd dokumenthanteringsfiler i formatutmatningar (Del 5 - ändra och kör format)</span><span class="sxs-lookup"><span data-stu-id="f63b8-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f63b8-105">I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.</span><span class="sxs-lookup"><span data-stu-id="f63b8-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="f63b8-106">Dessa steg kan utföras i DEMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="f63b8-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="f63b8-107">För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Använd dokumenthanteringsfiler i formatutmatningar (Del 4: Kör format)".</span><span class="sxs-lookup"><span data-stu-id="f63b8-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="f63b8-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="f63b8-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="f63b8-109">Ändra formatet för att fylla i bilagor så att dessa skapar meddelanden i binärt format</span><span class="sxs-lookup"><span data-stu-id="f63b8-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="f63b8-110">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f63b8-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f63b8-111">Expandera "Customer invoice model" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="f63b8-112">Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="f63b8-113">I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".</span><span class="sxs-lookup"><span data-stu-id="f63b8-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="f63b8-114">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f63b8-114">Click Designer.</span></span>
    * <span data-ttu-id="f63b8-115">Du fyller i fakturameddelandet i skapad utmatning som en XML-fil med hjälp av UNICODE-kodning.</span><span class="sxs-lookup"><span data-stu-id="f63b8-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="f63b8-116">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="f63b8-117">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="f63b8-118">Ange "Xml message" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="f63b8-119">Xml-meddelande</span><span class="sxs-lookup"><span data-stu-id="f63b8-119">Xml message</span></span>  
9. <span data-ttu-id="f63b8-120">Skriv "UTF 8" i fältet Kodning.</span><span class="sxs-lookup"><span data-stu-id="f63b8-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="f63b8-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="f63b8-121">UTF-8</span></span>  
10. <span data-ttu-id="f63b8-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-122">Click OK.</span></span>
    * <span data-ttu-id="f63b8-123">Konfigurera de skapade utmatningen som en zippad fil.</span><span class="sxs-lookup"><span data-stu-id="f63b8-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="f63b8-124">Klicka på Lägg till rot för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="f63b8-125">Välj "Common\Folder" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="f63b8-126">Ange "Zip output" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="f63b8-127">Zip-utleverans</span><span class="sxs-lookup"><span data-stu-id="f63b8-127">Zip output</span></span>  
14. <span data-ttu-id="f63b8-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-128">Click OK.</span></span>
15. <span data-ttu-id="f63b8-129">Välj "Zip output" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="f63b8-130">Lägg till bilagor till den skapade, zippade filen som filer med ursprungliga namn och filtillägg.</span><span class="sxs-lookup"><span data-stu-id="f63b8-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="f63b8-131">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="f63b8-132">Välj "Allmänt\Fil" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="f63b8-133">Ange "Attached file" i namnfältet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="f63b8-134">Bifogad fil</span><span class="sxs-lookup"><span data-stu-id="f63b8-134">Attached file</span></span>  
19. <span data-ttu-id="f63b8-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-135">Click OK.</span></span>
20. <span data-ttu-id="f63b8-136">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="f63b8-137">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="f63b8-138">Välj "Text\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="f63b8-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="f63b8-140">Mappa nya formatelement till datamodell</span><span class="sxs-lookup"><span data-stu-id="f63b8-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="f63b8-141">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="f63b8-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="f63b8-142">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="f63b8-143">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="f63b8-144">Välj "Zip output\Attached file\Base64" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="f63b8-145">Välj "model\Invoice attachments\File content" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="f63b8-146">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f63b8-146">Click Bind.</span></span>
7. <span data-ttu-id="f63b8-147">Välj "Zip output\Attached file" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="f63b8-148">Klick på Edit filename.</span><span class="sxs-lookup"><span data-stu-id="f63b8-148">Click Edit filename.</span></span>
9. <span data-ttu-id="f63b8-149">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="f63b8-150">Expandera "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="f63b8-151">Välj "model\Invoice attachments\File name" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="f63b8-152">Klicka på Lägg till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f63b8-152">Click Add data source.</span></span>
13. <span data-ttu-id="f63b8-153">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f63b8-153">Click Save.</span></span>
14. <span data-ttu-id="f63b8-154">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-154">Close the page.</span></span>
15. <span data-ttu-id="f63b8-155">Välj "model\Invoice attachments" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f63b8-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="f63b8-156">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f63b8-156">Click Bind.</span></span>
17. <span data-ttu-id="f63b8-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f63b8-157">Click Save.</span></span>
18. <span data-ttu-id="f63b8-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f63b8-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="f63b8-159">Kör den tidsplanerade rapporten för den valda fakturan</span><span class="sxs-lookup"><span data-stu-id="f63b8-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="f63b8-160">Klicka på Kör.</span><span class="sxs-lookup"><span data-stu-id="f63b8-160">Click Run.</span></span>
2. <span data-ttu-id="f63b8-161">Expandera avsnittet Records to include ().</span><span class="sxs-lookup"><span data-stu-id="f63b8-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="f63b8-162">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="f63b8-162">Click Filter.</span></span>
4. <span data-ttu-id="f63b8-163">Markera raden för kundfakturajournalen och fältet Sales order.</span><span class="sxs-lookup"><span data-stu-id="f63b8-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="f63b8-164">Ange ordernummer "000148" i fältet Criteria, i kriteriefältet "Sales order".</span><span class="sxs-lookup"><span data-stu-id="f63b8-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="f63b8-165">000148</span><span class="sxs-lookup"><span data-stu-id="f63b8-165">000148</span></span>  
6. <span data-ttu-id="f63b8-166">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-166">Click OK.</span></span>
7. <span data-ttu-id="f63b8-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f63b8-167">Click OK.</span></span>
    * <span data-ttu-id="f63b8-168">Granska den genererade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f63b8-168">Review the generated output.</span></span> <span data-ttu-id="f63b8-169">Notera att: Utöver fakturameddelandet i XML-format har en enda fil skapats för respektive bilaga.</span><span class="sxs-lookup"><span data-stu-id="f63b8-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="f63b8-170">Bilagefilerna fylls i med den zippade utmatningen i binärt format.</span><span class="sxs-lookup"><span data-stu-id="f63b8-170">The attachment files are populated with the zipped output in binary format.</span></span>  

