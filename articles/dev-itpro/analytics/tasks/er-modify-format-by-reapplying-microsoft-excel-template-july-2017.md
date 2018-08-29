--- 
title: "Ändra format genom att återanvända Excel-mallar"
description: "För att slutföra dessa steg i denna procedur måste du först slutföra proceduren ER - designa en konfiguration för att skapa rapporter i OPENXML-format\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 3d5752caba9327475bb28c7bc6b0ee7e072f44f3
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="fce9e-103">Ändra format genom att återanvända Excel-mallar</span><span class="sxs-lookup"><span data-stu-id="fce9e-103">Modify formats by reapplying Excel templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fce9e-104">För att slutföra dessa steg i denna procedur måste du först slutföra proceduren ER - designa en konfiguration för att skapa rapporter i OPENXML-format".</span><span class="sxs-lookup"><span data-stu-id="fce9e-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="fce9e-105">Den här proceduren beskriver hur du ändrar formatkonfigurationen i en elektronisk rapportering (ER) genom att omtillämpa en Microsoft Excel-mall som har ändrats.</span><span class="sxs-lookup"><span data-stu-id="fce9e-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="fce9e-106">I den här proceduren ska du importera en modifierad Excel-mall i ER-formatkonfigurationer som har skapats för exempelföretaget Litware, Inc. och använd dem för att skapa elektroniska dokument.</span><span class="sxs-lookup"><span data-stu-id="fce9e-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="fce9e-107">Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="fce9e-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="fce9e-108">Stegen kan utföras med hjälp av datauppsättningen GBSI.</span><span class="sxs-lookup"><span data-stu-id="fce9e-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="fce9e-109">Innan du börjar, se till att ladda ner och spara filen SampleVendPaymWsReport2.xlsx som listas i hjälpavsnittet Ändra elektroniskt rapporteringsformat genom att återapplicera en Excel-mall (ändra-elektroniskt-rapporteringsformat-återapplicera-excel-mall/).</span><span class="sxs-lookup"><span data-stu-id="fce9e-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="fce9e-110">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="fce9e-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="fce9e-111">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som aktiv och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fce9e-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="fce9e-112">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren Skapa en konfigurationsleverantör och välj den som aktiv.</span><span class="sxs-lookup"><span data-stu-id="fce9e-112">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="fce9e-113">Välj ER-format</span><span class="sxs-lookup"><span data-stu-id="fce9e-113">Select the ER format</span></span>
1. <span data-ttu-id="fce9e-114">Klicka på Reporting configurations.</span><span class="sxs-lookup"><span data-stu-id="fce9e-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="fce9e-115">Expandera "Betalningsmodell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="fce9e-116">Välj ”Betalningmodell\rapport över exempelkalkylblad" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="fce9e-117">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="fce9e-117">Click Attachments.</span></span>
    * <span data-ttu-id="fce9e-118">Observera att Excel-filen SampleVendPaymWsReport.xlsx används som mall för bearbetning av betalningsplansjournal.</span><span class="sxs-lookup"><span data-stu-id="fce9e-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="fce9e-119">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="fce9e-119">Click Open.</span></span>
    * <span data-ttu-id="fce9e-120">Klicka på Öppna för att utforska layouten i Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="fce9e-121">Granska mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-121">Review the template.</span></span> <span data-ttu-id="fce9e-122">Observera att den innehåller följande uppgifter för varje betalningsrad: leverantörskontonummer, leverantörsnamn, bank, organisationsnummer, kontonummer, debet, kredit och valuta.</span><span class="sxs-lookup"><span data-stu-id="fce9e-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="fce9e-123">Vi vill utöka listan genom att lägga till information om betalningsdatum.</span><span class="sxs-lookup"><span data-stu-id="fce9e-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="fce9e-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fce9e-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="fce9e-125">Använd en ny Excel-mall på ER-format</span><span class="sxs-lookup"><span data-stu-id="fce9e-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="fce9e-126">Klicka på Designer.</span><span class="sxs-lookup"><span data-stu-id="fce9e-126">Click Designer.</span></span>
    * <span data-ttu-id="fce9e-127">Öppna utkastversionen av det valda ER-formatet för redigering.</span><span class="sxs-lookup"><span data-stu-id="fce9e-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="fce9e-128">Klicka på Importera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fce9e-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="fce9e-129">Klicka på Uppdatera från Excel.</span><span class="sxs-lookup"><span data-stu-id="fce9e-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="fce9e-130">Klicka på "Uppdatera mall" och välj filen SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="fce9e-130">Click ‘Update template’, and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="fce9e-131">Klicka på Uppdatera mall och bläddra om du vill komma till filen SampleVendPaymWsReport2.xlsx som hämtades tidigare.</span><span class="sxs-lookup"><span data-stu-id="fce9e-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="fce9e-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fce9e-132">Click OK.</span></span>
    * <span data-ttu-id="fce9e-133">Mallen SampleVendPaymWsReport2.xlsx används.</span><span class="sxs-lookup"><span data-stu-id="fce9e-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="fce9e-134">Strukturen för ER-formatet synkroniseras med innehållet i mallen vars element läggs till i ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="fce9e-135">De befintliga element i ER-formatet som inte finns i mallen tas bort från formatdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-135">Any existing elements in the ER format that aren’t included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="fce9e-136">Välj Excel i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="fce9e-137">Observera att fältet Mall nu innehåller en referens till den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="fce9e-138">Klicka på Bilagor.</span><span class="sxs-lookup"><span data-stu-id="fce9e-138">Click Attachments.</span></span>
7. <span data-ttu-id="fce9e-139">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="fce9e-139">Click Open.</span></span>
    * <span data-ttu-id="fce9e-140">Klicka på Öppna för att utforska den redigerade Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="fce9e-141">Granska mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-141">Review the template.</span></span> <span data-ttu-id="fce9e-142">Observera att den nu innehåller en rad för betalningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="fce9e-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fce9e-143">Close the page.</span></span>
9. <span data-ttu-id="fce9e-144">Expandera Excel i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="fce9e-145">Expandera "Excel\PaymLines" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="fce9e-146">Välj Excel\PaymLines\PaymDate i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="fce9e-147">Observera att ER-formatet nu innehåller ett till objekt.</span><span class="sxs-lookup"><span data-stu-id="fce9e-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="fce9e-148">En cell, PaymDate, har lagts till Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="fce9e-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="fce9e-149">Klicka på fliken Mappning.</span><span class="sxs-lookup"><span data-stu-id="fce9e-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="fce9e-150">Expandera "modell" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="fce9e-151">Expandera "modell\Betalningar" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="fce9e-152">Välj "modell\Betalningar\Transaktionsdatum(TransactionDate)" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fce9e-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="fce9e-153">Klicka på Bind.</span><span class="sxs-lookup"><span data-stu-id="fce9e-153">Click Bind.</span></span>
    * <span data-ttu-id="fce9e-154">Ange vilka data som läggs till i den nya cellen vid körning.</span><span class="sxs-lookup"><span data-stu-id="fce9e-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="fce9e-155">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fce9e-155">Click Save.</span></span>
18. <span data-ttu-id="fce9e-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fce9e-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="fce9e-157">Aktivera den ändrade utkastversionen av ER-formatet så att den kan användas vid bearbetning av betalningsplansjournal</span><span class="sxs-lookup"><span data-stu-id="fce9e-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="fce9e-158">Klicka på Configurations i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fce9e-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="fce9e-159">Klicka på User parameters.</span><span class="sxs-lookup"><span data-stu-id="fce9e-159">Click User parameters.</span></span>
3. <span data-ttu-id="fce9e-160">Välj Yes i fältet Run settings.</span><span class="sxs-lookup"><span data-stu-id="fce9e-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="fce9e-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fce9e-161">Click OK.</span></span>
5. <span data-ttu-id="fce9e-162">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="fce9e-162">Click Edit.</span></span>
6. <span data-ttu-id="fce9e-163">Välj Yes i fältet Run Draft.</span><span class="sxs-lookup"><span data-stu-id="fce9e-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="fce9e-164">Använd den ändrade utkastversionen av ER-formatet för bearbetning av betalningsplansjournal</span><span class="sxs-lookup"><span data-stu-id="fce9e-164">Use the modified draft version of the ER format for payment journal processing</span></span>
    * <span data-ttu-id="fce9e-165">Granska det skapade kalkylbladet, inklusive den nya detaljen på betalningsraderna – betalningsdatum.</span><span class="sxs-lookup"><span data-stu-id="fce9e-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  


