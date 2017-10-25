--- 
title: "Generera rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att generera elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.openlocfilehash: 4fa27996e59164126f7900edf4a509ca9273e7c1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="generate-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er"></a><span data-ttu-id="34e36-103">Generera rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="34e36-103">Generate reports in Microsoft Office formats with embedded images for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34e36-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att generera elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder.</span><span class="sxs-lookup"><span data-stu-id="34e36-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="34e36-105">I det här exemplet ska du använda skapade ER-konfigurationer för exempelföretaget, "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="34e36-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="34e36-106">För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 2: Granska konfigurationer)".</span><span class="sxs-lookup"><span data-stu-id="34e36-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="34e36-107">Dessa steg kan utföras i USMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="34e36-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="34e36-108">Kör format med inledande modellmappning</span><span class="sxs-lookup"><span data-stu-id="34e36-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="34e36-109">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="34e36-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="34e36-110">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="34e36-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="34e36-111">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="34e36-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="34e36-112">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="34e36-112">Click Check.</span></span>
5. <span data-ttu-id="34e36-113">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="34e36-113">Click Print test.</span></span>
    * <span data-ttu-id="34e36-114">Kör formatet i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="34e36-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="34e36-115">Välj Ja i fältet Överlåtbart checkformat.</span><span class="sxs-lookup"><span data-stu-id="34e36-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="34e36-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34e36-116">Click OK.</span></span>
    * <span data-ttu-id="34e36-117">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34e36-117">Review the created output.</span></span> <span data-ttu-id="34e36-118">Observera att företagets logotyp visas i rapporten samt den behöriga personens underskrift.</span><span class="sxs-lookup"><span data-stu-id="34e36-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="34e36-119">Signaturbilden hämtas från fältet för datatypen Behållare i checklayoutposten som associeras med det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="34e36-119">The signature image is taken from the field of the ‘Container’ data type of the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="34e36-120">Expandera avsnittet Kopior.</span><span class="sxs-lookup"><span data-stu-id="34e36-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="34e36-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="34e36-121">Click Edit.</span></span>
10. <span data-ttu-id="34e36-122">Ange "Skriv ut vattenstämpel som annullerad" i fältet Vattenstämpel.</span><span class="sxs-lookup"><span data-stu-id="34e36-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="34e36-123">Ändra layoutinställningarna för vattenstämpel för att visa vattenstämpeln när dokument skapas i ett formatelement för Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="34e36-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="34e36-124">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="34e36-124">Click Print test.</span></span>
12. <span data-ttu-id="34e36-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34e36-125">Click OK.</span></span>
    * <span data-ttu-id="34e36-126">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34e36-126">Review the created output.</span></span> <span data-ttu-id="34e36-127">Kontrollera att vattenstämpeln visas i rapporten i enlighet med det valda alternativet.</span><span class="sxs-lookup"><span data-stu-id="34e36-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="34e36-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-128">Close the page.</span></span>
14. <span data-ttu-id="34e36-129">Klicka på Hantera betalningar i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="34e36-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="34e36-130">Klicka på Checkar.</span><span class="sxs-lookup"><span data-stu-id="34e36-130">Click Checks.</span></span>
16. <span data-ttu-id="34e36-131">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="34e36-131">Click Show filters.</span></span>
17. <span data-ttu-id="34e36-132">Använd följande filter: Ange filtervärdet 381, 385, 389 i fältet Checknummer med filteroperatorn "är någon av".</span><span class="sxs-lookup"><span data-stu-id="34e36-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="34e36-133">Markera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="34e36-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="34e36-134">Klicka på Skriv ut checkkopia.</span><span class="sxs-lookup"><span data-stu-id="34e36-134">Click Print check copy.</span></span>
    * <span data-ttu-id="34e36-135">Kör formatet om du vill skriva ut valda checkar igen.</span><span class="sxs-lookup"><span data-stu-id="34e36-135">Run the format to re-print the selected cheques.</span></span>  
    * <span data-ttu-id="34e36-136">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34e36-136">Review the created output.</span></span> <span data-ttu-id="34e36-137">Observera att valda checkar har skrivits ut igen.</span><span class="sxs-lookup"><span data-stu-id="34e36-137">Note that the selected cheques have been re-printed.</span></span> <span data-ttu-id="34e36-138">Företagets logotyp och etiketter skrivs inte ut eftersom de visas på den förtryckta blanketten.</span><span class="sxs-lookup"><span data-stu-id="34e36-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="34e36-139">Ändra mappning av den importerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="34e36-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="34e36-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-140">Close the page.</span></span>
2. <span data-ttu-id="34e36-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-141">Close the page.</span></span>
3. <span data-ttu-id="34e36-142">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="34e36-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="34e36-143">Välj "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="34e36-144">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="34e36-144">Click Designer.</span></span>
6. <span data-ttu-id="34e36-145">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="34e36-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="34e36-146">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="34e36-146">Click Designer.</span></span>
    * <span data-ttu-id="34e36-147">Vi vill ändra bindningen för datamodellens signaturobjekt för att hämta signaturbilden från filen som har kopplats till checklayoutposten som associeras med det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="34e36-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="34e36-148">Inaktivera Visa detaljer.</span><span class="sxs-lookup"><span data-stu-id="34e36-148">Turn Show details off.</span></span>
9. <span data-ttu-id="34e36-149">Expandera "layout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="34e36-150">Expandera "layout\signature" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="34e36-151">Välj layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="34e36-152">Expandera chequesaccount i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="34e36-153">Expandera "chequesaccount\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="34e36-154">Expandera "chequesaccount\<Relations\BankChequeLayout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="34e36-155">Expandera "chequesaccount\<Relations\BankChequeLayout\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="34e36-156">Expandera chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="34e36-157">Välj "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="34e36-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="34e36-158">Click Bind.</span></span>
19. <span data-ttu-id="34e36-159">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="34e36-159">Click Save.</span></span>
20. <span data-ttu-id="34e36-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-160">Close the page.</span></span>
21. <span data-ttu-id="34e36-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-161">Close the page.</span></span>
22. <span data-ttu-id="34e36-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-162">Close the page.</span></span>
23. <span data-ttu-id="34e36-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="34e36-164">Kör formatet med den justerade modellmappningen</span><span class="sxs-lookup"><span data-stu-id="34e36-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="34e36-165">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="34e36-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="34e36-166">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="34e36-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="34e36-167">Filtrera till exempel fältet Bankkonto med värdet på USMF OPER.</span><span class="sxs-lookup"><span data-stu-id="34e36-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="34e36-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="34e36-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="34e36-169">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="34e36-169">Click Check.</span></span>
5. <span data-ttu-id="34e36-170">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="34e36-170">Click Print test.</span></span>
6. <span data-ttu-id="34e36-171">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34e36-171">Click OK.</span></span>
    * <span data-ttu-id="34e36-172">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34e36-172">Review the created output.</span></span> <span data-ttu-id="34e36-173">Observera att bilden från dokumenthanteringsbilagan visas som underskriften för en behörig person.</span><span class="sxs-lookup"><span data-stu-id="34e36-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="34e36-174">Använd Microsoft Word-dokument som en mall i det importerade formatet</span><span class="sxs-lookup"><span data-stu-id="34e36-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="34e36-175">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-175">Close the page.</span></span>
2. <span data-ttu-id="34e36-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-176">Close the page.</span></span>
3. <span data-ttu-id="34e36-177">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="34e36-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="34e36-178">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="34e36-179">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="34e36-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="34e36-180">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="34e36-180">Click Designer.</span></span>
7. <span data-ttu-id="34e36-181">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="34e36-181">Click Attachments.</span></span>
8. <span data-ttu-id="34e36-182">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="34e36-182">Click Delete.</span></span>
9. <span data-ttu-id="34e36-183">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="34e36-183">Click Yes.</span></span>
10. <span data-ttu-id="34e36-184">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="34e36-184">Click New.</span></span>
11. <span data-ttu-id="34e36-185">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="34e36-185">Click File.</span></span>
    * <span data-ttu-id="34e36-186">Klicka på Bläddra och välj den i förväg hämtade Word.docx-filen för checkmall.</span><span class="sxs-lookup"><span data-stu-id="34e36-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="34e36-187">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-187">Close the page.</span></span>
13. <span data-ttu-id="34e36-188">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="34e36-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="34e36-189">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="34e36-189">Click Save.</span></span>
15. <span data-ttu-id="34e36-190">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-190">Close the page.</span></span>
16. <span data-ttu-id="34e36-191">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="34e36-191">Click Edit.</span></span>
17. <span data-ttu-id="34e36-192">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="34e36-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="34e36-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34e36-193">Close the page.</span></span>
19. <span data-ttu-id="34e36-194">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="34e36-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="34e36-195">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="34e36-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="34e36-196">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="34e36-196">Click Check.</span></span>
22. <span data-ttu-id="34e36-197">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="34e36-197">Click Print test.</span></span>
23. <span data-ttu-id="34e36-198">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34e36-198">Click OK.</span></span>
    * <span data-ttu-id="34e36-199">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34e36-199">Review the created output.</span></span> <span data-ttu-id="34e36-200">Observera att utdata har skapats som ett Microsoft Word-dokument med inbäddade bilder som innehåller företagslogotypen, underskrift av en behörig person och den markerade texten i vattenstämpeln.</span><span class="sxs-lookup"><span data-stu-id="34e36-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  

