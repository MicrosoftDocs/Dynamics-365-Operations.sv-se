---
title: Utforma ER-konfigurationer för rapportgenerering i Word-format
description: I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering så att detta skapar rapporter som Microsoft Word-filer.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc47d44285af4c720d2f450d11fb1004ef461d0f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551532"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a><span data-ttu-id="34c5a-103">Utforma ER-konfigurationer för rapportgenerering i Word-format</span><span class="sxs-lookup"><span data-stu-id="34c5a-103">Design ER configurations to generate reports in Word format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="34c5a-104">I följande steg beskrivs hur en användare med systemadministratörsroll eller roll som utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) så att detta skapar rapporter som Microsoft Word-filer.</span><span class="sxs-lookup"><span data-stu-id="34c5a-104">The following steps explain how a user in either the System administrator or Electronic reporting developer role can configure an Electronic reporting (ER) formats to generate reports as Microsoft Word files.</span></span> <span data-ttu-id="34c5a-105">Dessa steg kan utföras i GBSI-företaget.</span><span class="sxs-lookup"><span data-stu-id="34c5a-105">These steps can be performed in the GBSI company.</span></span>

<span data-ttu-id="34c5a-106">För att slutföra dessa steg måste du först slutföra stegen i uppgiftsguiden "Skapa en ER-konfiguration för att skapa rapporter i OPENXML-format".</span><span class="sxs-lookup"><span data-stu-id="34c5a-106">To complete these steps, you must first complete the steps in the “Create an ER configuration for generating reports in OPENXML format” task guide.</span></span> <span data-ttu-id="34c5a-107">Du måste också (i förväg) hämta och spara följande mallar lokalt för exempelrapporten:</span><span class="sxs-lookup"><span data-stu-id="34c5a-107">In advance, you must also download and save the following templates locally for the sample report:</span></span>

- [<span data-ttu-id="34c5a-108">Mall för betalningsrapport</span><span class="sxs-lookup"><span data-stu-id="34c5a-108">Template of Payment Report</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="34c5a-109">Bunden mall för betalningsrapport</span><span class="sxs-lookup"><span data-stu-id="34c5a-109">Bounded Template of Payment Report</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)


<span data-ttu-id="34c5a-110">Denna procedur är avsedd för en funktion som lades till i Microsoft Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="34c5a-110">This procedure is for a feature that was added in Microsoft Dynamics 365 for Operations version 1611.</span></span>


## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="34c5a-111">Markera den befintliga ER-rapportkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="34c5a-111">Select the existing ER report configuration</span></span>
1. <span data-ttu-id="34c5a-112">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="34c5a-112">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="34c5a-113">Kontrollera att konfigurationsleverantören "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="34c5a-113">Make sure that the configuration provider ‘Litware, Inc.’</span></span> <span data-ttu-id="34c5a-114">är markerad som aktiv.</span><span class="sxs-lookup"><span data-stu-id="34c5a-114">is selected as active.</span></span>  
2. <span data-ttu-id="34c5a-115">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="34c5a-115">Click Reporting configurations.</span></span>
    * <span data-ttu-id="34c5a-116">Vi kommer att återanvända den befintliga ER-konfigurationen som ursprungligen har skapats för att skapa rapportutdata i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="34c5a-116">We will re-use the existing ER configuration that has been originally designed to generate the report output in OPENXML format.</span></span>  
3. <span data-ttu-id="34c5a-117">Expandera "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34c5a-117">In the tree, expand 'Payment model'.</span></span>
4. <span data-ttu-id="34c5a-118">Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="34c5a-118">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
5. <span data-ttu-id="34c5a-119">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="34c5a-119">Click Designer.</span></span>

## <a name="replace-the-excel-template-with-the-word-template"></a><span data-ttu-id="34c5a-120">Byt ut Excel-mallen mot Word-mallen</span><span class="sxs-lookup"><span data-stu-id="34c5a-120">Replace the Excel template with the Word template</span></span>
    * <span data-ttu-id="34c5a-121">För närvarande används Excel-dokumentet som en mall för att skapa utdata i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="34c5a-121">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="34c5a-122">Vi kommer att importera rapportmallen i Word-format.</span><span class="sxs-lookup"><span data-stu-id="34c5a-122">We will import the report’s template in Word format.</span></span>  
1. <span data-ttu-id="34c5a-123">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="34c5a-123">Click Attachments.</span></span>
    * <span data-ttu-id="34c5a-124">Ersätt den befintliga Excel-mallen med den Word-mall som du hämtade förut (SampleVendPaymDocReport.docx).</span><span class="sxs-lookup"><span data-stu-id="34c5a-124">Replace the existing Excel template with the Word template that you downloaded earlier, SampleVendPaymDocReport.docx.</span></span> <span data-ttu-id="34c5a-125">Observera att den här mallen endast innehåller layouten i det dokument som vi vill generera som ER-utdata.</span><span class="sxs-lookup"><span data-stu-id="34c5a-125">Note, this template only contains the layout of the document we want to generate as ER output.</span></span>  
2. <span data-ttu-id="34c5a-126">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="34c5a-126">Click Delete.</span></span>
3. <span data-ttu-id="34c5a-127">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="34c5a-127">Click Yes.</span></span>
4. <span data-ttu-id="34c5a-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="34c5a-128">Click New.</span></span>
5. <span data-ttu-id="34c5a-129">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="34c5a-129">Click File.</span></span>
6. <span data-ttu-id="34c5a-130">Klicka på Bläddra.</span><span class="sxs-lookup"><span data-stu-id="34c5a-130">Click Browse.</span></span> <span data-ttu-id="34c5a-131">Navigera till och välj SampleVendPaymDocReport.docx som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="34c5a-131">Navigate to and select SampleVendPaymDocReport.docx that you previously downloaded.</span></span> <span data-ttu-id="34c5a-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34c5a-132">Click OK.</span></span>
    * <span data-ttu-id="34c5a-133">Välj mallen som du hämtade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="34c5a-133">Select the template that you downloaded in the previous step.</span></span>  
7. <span data-ttu-id="34c5a-134">Ange eller välj ett värde i fältet Template.</span><span class="sxs-lookup"><span data-stu-id="34c5a-134">In the Template field, enter or select a value.</span></span>

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a><span data-ttu-id="34c5a-135">Utöka Word-mallen genom att lägga till en anpassad XML-kod</span><span class="sxs-lookup"><span data-stu-id="34c5a-135">Extend the Word template by adding a custom XML part</span></span>
1. <span data-ttu-id="34c5a-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="34c5a-136">Click Save.</span></span>
    * <span data-ttu-id="34c5a-137">Förutom att spara konfigurationsändringar, uppdaterar åtgärden Spara även den bifogade Word-mallen.</span><span class="sxs-lookup"><span data-stu-id="34c5a-137">In addition to storing configuration changes, the Save action also updates the attached Word template.</span></span> <span data-ttu-id="34c5a-138">Strukturen hos det designade formatet portas till det bifogade Word-dokumentet som en ny, anpassad XML-kod med namnet "Rapport".</span><span class="sxs-lookup"><span data-stu-id="34c5a-138">The structure of the designed format is ported to the attached Word document as a new custom XML part with the name ‘Report’.</span></span> <span data-ttu-id="34c5a-139">Lägg märke till att den bifogade Word-mallen inte bara innehåller layouten i det dokument som vi vill skapa som ER-utdata, utan även den datastruktur som ER fyller den här mallen med under körning.</span><span class="sxs-lookup"><span data-stu-id="34c5a-139">Note that the attached Word template contains not only the layout of the document we want to generate as ER output, it also contains the structure of data that ER will populate into this template at runtime.</span></span>  
2. <span data-ttu-id="34c5a-140">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="34c5a-140">Click Attachments.</span></span>
    * <span data-ttu-id="34c5a-141">Nu måste du binda elementen i den anpassade XML-koden "Rapport" till Word-dokumentets delar.</span><span class="sxs-lookup"><span data-stu-id="34c5a-141">Now you need to bind the elements of the custom XML part ‘Report’ to the Word document parts.</span></span>  
    * <span data-ttu-id="34c5a-142">Om du är bekant med Word-dokument som kan utformas som formulär med innehåll som avgränsas med elementen i anpassade XML-delar, spela då upp alla stegen i nästa underordnade uppgift för att skapa dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="34c5a-142">If you're familiar with Word documents that can be designed as forms containing content controls that are bounded with elements of custom XML parts – play all steps of the next sub-task to create such a document.</span></span> <span data-ttu-id="34c5a-143">Mer information finns via följande länk: https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span><span class="sxs-lookup"><span data-stu-id="34c5a-143">For more details, see this link https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span></span> <span data-ttu-id="34c5a-144">Annars hoppar du över alla steg i nästa underuppgift.</span><span class="sxs-lookup"><span data-stu-id="34c5a-144">Otherwise, skip all the steps in the next sub-task.</span></span>  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a><span data-ttu-id="34c5a-145">Få Word med anpassad XML-kod att utföra databindningar</span><span class="sxs-lookup"><span data-stu-id="34c5a-145">Get Word with custom XML part to do data bindings</span></span>
    * <span data-ttu-id="34c5a-146">Öppna detta dokument i Word och gör följande: - Öppna fliken Word-utvecklare (anpassa menyfliken om denna inte har aktiverats än).</span><span class="sxs-lookup"><span data-stu-id="34c5a-146">Open this document in Word and do the following:  - Open the Word Developer tab (customize the ribbon if it is not enabled yet).</span></span>  <span data-ttu-id="34c5a-147">- Välj fönstret för XML-mappning.</span><span class="sxs-lookup"><span data-stu-id="34c5a-147">- Select XML mapping pane.</span></span>  <span data-ttu-id="34c5a-148">- Välj den anpassade XML-koden "Rapport" i sökningen.</span><span class="sxs-lookup"><span data-stu-id="34c5a-148">- Select the ‘Report’ custom XML part in the lookup.</span></span>  <span data-ttu-id="34c5a-149">- Utför mappningen av elementen i den markerade, anpassade XML-koden och Word-dokumentets innehållskontroller.</span><span class="sxs-lookup"><span data-stu-id="34c5a-149">- Do mapping of the elements of the selected custom XML part and content controls of the Word document.</span></span>  <span data-ttu-id="34c5a-150">- Spara det uppdaterade Word-dokumentet på en lokal enhet.</span><span class="sxs-lookup"><span data-stu-id="34c5a-150">- Save the updated Word document on a local drive.</span></span>  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a><span data-ttu-id="34c5a-151">Överför Word-mallen med anpassad XML-kod bunden till innehållskontroller</span><span class="sxs-lookup"><span data-stu-id="34c5a-151">Upload the Word template with custom XML part bounded to content controls</span></span>
1. <span data-ttu-id="34c5a-152">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="34c5a-152">Click Delete.</span></span>
2. <span data-ttu-id="34c5a-153">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="34c5a-153">Click Yes.</span></span>
    * <span data-ttu-id="34c5a-154">Lägg till ny mall.</span><span class="sxs-lookup"><span data-stu-id="34c5a-154">Add a new template.</span></span> <span data-ttu-id="34c5a-155">Markera det Word-dokument som du har skapat och sparat lokalt, om du har slutfört stegen i föregående underaktivitet.</span><span class="sxs-lookup"><span data-stu-id="34c5a-155">If you competed the steps in the previous subtask, select the Word document that you prepared and saved locally.</span></span> <span data-ttu-id="34c5a-156">Annars väljer du MS Word-mallen SampleVendPaymDocReportBounded.docx som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="34c5a-156">Otherwise, select the SampleVendPaymDocReportBounded.docx MS Word template that you downloaded earlier.</span></span>  
3. <span data-ttu-id="34c5a-157">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="34c5a-157">Click New.</span></span>
4. <span data-ttu-id="34c5a-158">Klicka på Arkiv.</span><span class="sxs-lookup"><span data-stu-id="34c5a-158">Click File.</span></span>
5. <span data-ttu-id="34c5a-159">Klicka på Bläddra.</span><span class="sxs-lookup"><span data-stu-id="34c5a-159">Click Browse.</span></span> <span data-ttu-id="34c5a-160">Navigera till och välj SampleVendPaymDocReportBounded.docx som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="34c5a-160">Navigate to and select SampleVendPaymDocReportBounded.docx that you previously downloaded.</span></span> <span data-ttu-id="34c5a-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34c5a-161">Click OK.</span></span>
6. <span data-ttu-id="34c5a-162">I fältet Mall väljer du mallen som du hämtade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="34c5a-162">In the Template field, select the document that you downloaded in the previous step.</span></span>
7. <span data-ttu-id="34c5a-163">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="34c5a-163">Click Save.</span></span>
8. <span data-ttu-id="34c5a-164">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34c5a-164">Close the page.</span></span>

## <a name="execute-the-format-to-create-word-output"></a><span data-ttu-id="34c5a-165">Kör formatet för att skapa Word-utleverans</span><span class="sxs-lookup"><span data-stu-id="34c5a-165">Execute the format to create Word output</span></span>
1. <span data-ttu-id="34c5a-166">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="34c5a-166">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="34c5a-167">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="34c5a-167">Click User parameters.</span></span>
3. <span data-ttu-id="34c5a-168">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="34c5a-168">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="34c5a-169">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34c5a-169">Click OK.</span></span>
5. <span data-ttu-id="34c5a-170">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="34c5a-170">Click Edit.</span></span>
6. <span data-ttu-id="34c5a-171">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="34c5a-171">Select Yes in the Run Draft field.</span></span>
7. <span data-ttu-id="34c5a-172">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="34c5a-172">Click Save.</span></span>
8. <span data-ttu-id="34c5a-173">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34c5a-173">Close the page.</span></span>
9. <span data-ttu-id="34c5a-174">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="34c5a-174">Close the page.</span></span>
10. <span data-ttu-id="34c5a-175">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="34c5a-175">Go to Accounts payable > Payments > Payment journal.</span></span>
11. <span data-ttu-id="34c5a-176">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="34c5a-176">Click Lines.</span></span>
12. <span data-ttu-id="34c5a-177">Markera eller avmarkera alla rader i listan.</span><span class="sxs-lookup"><span data-stu-id="34c5a-177">In the list, mark or unmark all rows.</span></span>
13. <span data-ttu-id="34c5a-178">Klicka på Betalningsstatus.</span><span class="sxs-lookup"><span data-stu-id="34c5a-178">Click Payment status.</span></span>
14. <span data-ttu-id="34c5a-179">Klicka på Ingen.</span><span class="sxs-lookup"><span data-stu-id="34c5a-179">Click None.</span></span>
15. <span data-ttu-id="34c5a-180">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="34c5a-180">Click Generate payments.</span></span>
16. <span data-ttu-id="34c5a-181">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34c5a-181">Click OK.</span></span>
17. <span data-ttu-id="34c5a-182">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="34c5a-182">Click OK.</span></span>
    * <span data-ttu-id="34c5a-183">Analysera den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="34c5a-183">Analyze the generated output.</span></span> <span data-ttu-id="34c5a-184">Observera att skapade utdata visas i Word-format och innehåller information om de behandlade betalningarna.</span><span class="sxs-lookup"><span data-stu-id="34c5a-184">Note that the created output is presented in Word format and contains the details of the processed payments.</span></span>  

