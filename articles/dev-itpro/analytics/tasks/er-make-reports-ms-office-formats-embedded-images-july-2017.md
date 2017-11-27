--- 
title: "Skapa rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER) (Del 1)"
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
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: f610fe4b7f265c4fc38db89938d5c208b4f7661a
ms.contentlocale: sv-se
ms.lasthandoff: 11/02/2017

---
# <a name="make-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er--part-1"></a><span data-ttu-id="f3e0d-103">Skapa rapporter i Microsoft Office-format med inbäddade bilder för elektronisk rapportering (ER) (Del 1)</span><span class="sxs-lookup"><span data-stu-id="f3e0d-103">Make reports in Microsoft Office formats with embedded images for electronic reporting (ER)  (Part 1)</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3e0d-104">I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan skapa konfigurationer för Elektronisk rapportering (ER) för att generera elektroniska dokument i MS Office-format (Excel och Word) som innehåller inbäddade bilder.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="f3e0d-105">I det här exemplet ska du använda skapade ER-konfigurationer för exempelföretaget, "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="f3e0d-106">För att kunna genomföra stegen måste du först slutföra stegen i uppgiftsguiden "ER Skapa rapporter i MS Office-format med inbäddade bilder (Del 2: Granska konfigurationer)".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="f3e0d-107">Dessa steg kan utföras i USMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="f3e0d-108">Kör format med inledande modellmappning</span><span class="sxs-lookup"><span data-stu-id="f3e0d-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="f3e0d-109">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="f3e0d-110">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="f3e0d-111">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="f3e0d-112">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-112">Click Check.</span></span>
5. <span data-ttu-id="f3e0d-113">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="f3e0d-113">Click Print test.</span></span>
    * <span data-ttu-id="f3e0d-114">Kör formatet i testsyfte.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="f3e0d-115">Välj Ja i fältet Överlåtbart checkformat.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="f3e0d-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-116">Click OK.</span></span>
    * <span data-ttu-id="f3e0d-117">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-117">Review the created output.</span></span> <span data-ttu-id="f3e0d-118">Observera att företagets logotyp visas i rapporten samt den behöriga personens underskrift.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="f3e0d-119">Signaturbilden hämtas från fältet för datatypen Behållare i checklayoutposten som associeras med det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-119">The signature image is taken from the field of the ‘Container’ data type of the check layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="f3e0d-120">Expandera avsnittet Kopior.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="f3e0d-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-121">Click Edit.</span></span>
10. <span data-ttu-id="f3e0d-122">Ange "Skriv ut vattenstämpel som annullerad" i fältet Vattenstämpel.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="f3e0d-123">Ändra layoutinställningarna för vattenstämpel för att visa vattenstämpeln när dokument skapas i ett formatelement för Excel-kalkylblad.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="f3e0d-124">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="f3e0d-124">Click Print test.</span></span>
12. <span data-ttu-id="f3e0d-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-125">Click OK.</span></span>
    * <span data-ttu-id="f3e0d-126">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-126">Review the created output.</span></span> <span data-ttu-id="f3e0d-127">Kontrollera att vattenstämpeln visas i rapporten i enlighet med det valda alternativet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="f3e0d-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-128">Close the page.</span></span>
14. <span data-ttu-id="f3e0d-129">Klicka på Hantera betalningar i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="f3e0d-130">Klicka på Checkar.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-130">Click Checks.</span></span>
16. <span data-ttu-id="f3e0d-131">Klicka på Visa filter.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-131">Click Show filters.</span></span>
17. <span data-ttu-id="f3e0d-132">Använd följande filter: Ange filtervärdet 381, 385, 389 i fältet Checknummer med filteroperatorn "är någon av".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="f3e0d-133">Markera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="f3e0d-134">Klicka på Skriv ut checkkopia.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-134">Click Print check copy.</span></span>
    * <span data-ttu-id="f3e0d-135">Kör formatet om du vill skriva ut valda checkar igen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-135">Run the format to re-print the selected checks.</span></span>  
    * <span data-ttu-id="f3e0d-136">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-136">Review the created output.</span></span> <span data-ttu-id="f3e0d-137">Observera att valda checkar har skrivits ut igen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-137">Note that the selected checks have been re-printed.</span></span> <span data-ttu-id="f3e0d-138">Företagets logotyp och etiketter skrivs inte ut eftersom de visas på den förtryckta blanketten.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="f3e0d-139">Ändra mappning av den importerade datamodellen</span><span class="sxs-lookup"><span data-stu-id="f3e0d-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="f3e0d-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-140">Close the page.</span></span>
2. <span data-ttu-id="f3e0d-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-141">Close the page.</span></span>
3. <span data-ttu-id="f3e0d-142">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="f3e0d-143">Välj "Modell för checkar".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-143">In the tree, select 'Model for checks'.</span></span>
5. <span data-ttu-id="f3e0d-144">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-144">Click Designer.</span></span>
6. <span data-ttu-id="f3e0d-145">Klicka på Mappa modell till datakälla.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="f3e0d-146">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-146">Click Designer.</span></span>
    * <span data-ttu-id="f3e0d-147">Vi vill ändra bindningen för datamodellens signaturobjekt för att hämta signaturbilden från filen som har kopplats till checklayoutposten som associeras med det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="f3e0d-148">Inaktivera Visa detaljer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-148">Turn Show details off.</span></span>
9. <span data-ttu-id="f3e0d-149">Expandera "layout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="f3e0d-150">Expandera "layout\signature" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="f3e0d-151">Välj layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="f3e0d-152">Expandera chequesaccount i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="f3e0d-153">Expandera "chequesaccount\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="f3e0d-154">Expandera "chequesaccount\<Relations\BankChequeLayout" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="f3e0d-155">Expandera "chequesaccount\<Relations\BankChequeLayout\<Relations" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="f3e0d-156">Expandera chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="f3e0d-157">Välj "chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="f3e0d-158">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-158">Click Bind.</span></span>
19. <span data-ttu-id="f3e0d-159">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-159">Click Save.</span></span>
20. <span data-ttu-id="f3e0d-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-160">Close the page.</span></span>
21. <span data-ttu-id="f3e0d-161">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-161">Close the page.</span></span>
22. <span data-ttu-id="f3e0d-162">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-162">Close the page.</span></span>
23. <span data-ttu-id="f3e0d-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="f3e0d-164">Kör formatet med den justerade modellmappningen</span><span class="sxs-lookup"><span data-stu-id="f3e0d-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="f3e0d-165">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="f3e0d-166">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f3e0d-167">Filtrera till exempel fältet Bankkonto med värdet på USMF OPER.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="f3e0d-168">Klicka på Ställ in i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="f3e0d-169">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-169">Click Check.</span></span>
5. <span data-ttu-id="f3e0d-170">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="f3e0d-170">Click Print test.</span></span>
6. <span data-ttu-id="f3e0d-171">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-171">Click OK.</span></span>
    * <span data-ttu-id="f3e0d-172">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-172">Review the created output.</span></span> <span data-ttu-id="f3e0d-173">Observera att bilden från dokumenthanteringsbilagan visas som underskriften för en behörig person.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="f3e0d-174">Använd Microsoft Word-dokument som en mall i det importerade formatet</span><span class="sxs-lookup"><span data-stu-id="f3e0d-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="f3e0d-175">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-175">Close the page.</span></span>
2. <span data-ttu-id="f3e0d-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-176">Close the page.</span></span>
3. <span data-ttu-id="f3e0d-177">Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="f3e0d-178">Expandera "Modell för checkar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="f3e0d-179">Välj Model for cheques\Cheques printing format i trädet.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="f3e0d-180">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-180">Click Designer.</span></span>
7. <span data-ttu-id="f3e0d-181">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-181">Click Attachments.</span></span>
8. <span data-ttu-id="f3e0d-182">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-182">Click Delete.</span></span>
9. <span data-ttu-id="f3e0d-183">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-183">Click Yes.</span></span>
10. <span data-ttu-id="f3e0d-184">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-184">Click New.</span></span>
11. <span data-ttu-id="f3e0d-185">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-185">Click File.</span></span>
    * <span data-ttu-id="f3e0d-186">Klicka på Bläddra och välj den i förväg hämtade Word.docx-filen för checkmall.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="f3e0d-187">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-187">Close the page.</span></span>
13. <span data-ttu-id="f3e0d-188">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="f3e0d-189">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-189">Click Save.</span></span>
15. <span data-ttu-id="f3e0d-190">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-190">Close the page.</span></span>
16. <span data-ttu-id="f3e0d-191">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-191">Click Edit.</span></span>
17. <span data-ttu-id="f3e0d-192">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="f3e0d-193">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-193">Close the page.</span></span>
19. <span data-ttu-id="f3e0d-194">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="f3e0d-195">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="f3e0d-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="f3e0d-196">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-196">Click Check.</span></span>
22. <span data-ttu-id="f3e0d-197">Klicka på Testutskrift</span><span class="sxs-lookup"><span data-stu-id="f3e0d-197">Click Print test.</span></span>
23. <span data-ttu-id="f3e0d-198">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-198">Click OK.</span></span>
    * <span data-ttu-id="f3e0d-199">Granska den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-199">Review the created output.</span></span> <span data-ttu-id="f3e0d-200">Observera att utdata har skapats som ett Microsoft Word-dokument med inbäddade bilder som innehåller företagslogotypen, underskrift av en behörig person och den markerade texten i vattenstämpeln.</span><span class="sxs-lookup"><span data-stu-id="f3e0d-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  


