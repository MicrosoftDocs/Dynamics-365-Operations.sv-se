---
title: Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format
description: I det här avsnittet beskrivs hur rapportformat som har utformats för att generera rapporter som Excel-arbetsböcker kan konfigureras för att generera rapporter som Word-dokument.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 413be634e80b87781444e1c1445c78691f4b4b0b
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944302"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="5d2be-103">Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="5d2be-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d2be-104">För att generera rapporter som Microsoft Word-dokument kan du [konfigurera](../er-design-configuration-word.md) ett nytt [elektronisk rapportering (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="5d2be-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="5d2be-105">Du kan också återanvända ett ER-format som ursprungligen utformats för att generera rapporter som Excel-arbetsböcker.</span><span class="sxs-lookup"><span data-stu-id="5d2be-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="5d2be-106">I så fall måste du ersätta Excel-mallen med en Word-mall.</span><span class="sxs-lookup"><span data-stu-id="5d2be-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="5d2be-107">Följande procedurer visar hur en användare med rollen Systemadministratör eller Elektronisk rapporteringsutvecklare kan konfigurera ett ER-format för att generera rapporter som Word-filer genom att återanvända ett ER-format som har utformats för att generera rapporter som Excel-filer.</span><span class="sxs-lookup"><span data-stu-id="5d2be-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="5d2be-108">Dessa procedurer kan slutföras i GBSI-företaget.</span><span class="sxs-lookup"><span data-stu-id="5d2be-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d2be-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5d2be-109">Prerequisites</span></span>

<span data-ttu-id="5d2be-110">För att slutföra dessa procedurer måste du först följa stegen i uppgiftsguiden [Designa en konfiguration för att skapa rapporter i OPENXML-format](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="5d2be-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="5d2be-111">Du måste också hämta och spara följande mallar lokalt för exempelrapporten:</span><span class="sxs-lookup"><span data-stu-id="5d2be-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="5d2be-112">Mall för betalningsrapport (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="5d2be-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [<span data-ttu-id="5d2be-113">Bunden mall för betalningsrapport (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="5d2be-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

<span data-ttu-id="5d2be-114">Procedurerna gäller för en funktion som lagts till Dynamics 365 for Operations i version 1611 (november 2016).</span><span class="sxs-lookup"><span data-stu-id="5d2be-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="5d2be-115">Markera den befintliga ER-rapportkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="5d2be-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="5d2be-116">I Dynamics 365 Finance, gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="5d2be-117">Kontrollera att konfigurationsleverantören **Litware, Inc.** har markerats som **aktiv**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="5d2be-118">Om den inte är det följer du stegen i uppgiftsguiden [Skapa konfigurationsleverantörer och markera dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="5d2be-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="5d2be-119">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="5d2be-120">Du kommer att återanvända den befintliga ER-konfigurationen som har skapats för att skapa rapportutdata i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="5d2be-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="5d2be-121">På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Betalningsmodell** och väljer sedan **Rapport över exempelkalkylblad**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d2be-122">Utkastversionen av det valda ER-formatet kan redigeras på snabbfliken **Versioner**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="5d2be-123">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-123">Select **Designer**.</span></span>
6. <span data-ttu-id="5d2be-124">På sidan **Formatdesigner**, lägg märke till att titeln på rotformatelementet anger att en Excel-mall för närvarande används.</span><span class="sxs-lookup"><span data-stu-id="5d2be-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Markera den befintliga konfigurationen](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="5d2be-126">Granska den hämtade Word-mallen</span><span class="sxs-lookup"><span data-stu-id="5d2be-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="5d2be-127">I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReport.docx** som du hämtat tidigare.</span><span class="sxs-lookup"><span data-stu-id="5d2be-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="5d2be-128">Verifiera att mallen endast innehåller layouten i det dokument som vi vill generera som ER-utdata.</span><span class="sxs-lookup"><span data-stu-id="5d2be-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![Word-malllayout i skrivbordsprogrammet](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="5d2be-130">Ersätt Excel-mallen med Word-mallen och lägg till en anpassad XML-kod</span><span class="sxs-lookup"><span data-stu-id="5d2be-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="5d2be-131">För närvarande används Excel-dokumentet som en mall för att skapa utdata i OPENXML-format.</span><span class="sxs-lookup"><span data-stu-id="5d2be-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="5d2be-132">Du kommer att ersätta den här mallen med SampleVendPaymDocReport.docx Word-mallfil som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="5d2be-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="5d2be-133">Du vill också utöka Word-mallen genom att lägga till en anpassad XML-kod.</span><span class="sxs-lookup"><span data-stu-id="5d2be-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="5d2be-134">I Finance, på sidan **Formatdesigner** på fliken **Format**, välj **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="5d2be-135">På sidan **Bilagor** väljer du **Ta bort** om du vill ta bort den befintliga Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="5d2be-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="5d2be-136">Välj **Ja** för att bekräfta ändringen.</span><span class="sxs-lookup"><span data-stu-id="5d2be-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="5d2be-137">Välj **Ny** \> **Fil**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d2be-138">Du måste välja en dokumenttyp som har [konfigurerats](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrarna för att ange minne för ER-formatmallar.</span><span class="sxs-lookup"><span data-stu-id="5d2be-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="5d2be-139">Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReport.docx** som du hämtat tidigare.</span><span class="sxs-lookup"><span data-stu-id="5d2be-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="5d2be-140">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-140">Select **OK**.</span></span>
6. <span data-ttu-id="5d2be-141">Stäng sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="5d2be-142">På sidan **Formatdesigner** i fältet **Mall**, ange eller välj filen **SampleVendPaymDocReport.docx** som ska användas i Word-mallen istället för den Excel-mall som tidigare användes.</span><span class="sxs-lookup"><span data-stu-id="5d2be-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="5d2be-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-143">Select **Save**.</span></span>

    <span data-ttu-id="5d2be-144">Förutom att spara konfigurationsändringar, uppdaterar åtgärden **Spara** även den bifogade Word-mallen.</span><span class="sxs-lookup"><span data-stu-id="5d2be-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="5d2be-145">Den hierarkiska strukturen hos det designade formatet läggs till det bifogade Word-dokumentet som en ny, anpassad XML-kod med namnet **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="5d2be-146">Den bifogade Word-mallen innehåller layouten för dokumentet som kommer att genereras som ER-utdata och strukturen för data som ER kommer att ange i den mallen vid körning.</span><span class="sxs-lookup"><span data-stu-id="5d2be-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="5d2be-147">Observera att titeln på rotformatelementet anger att en Word-mall för närvarande används.</span><span class="sxs-lookup"><span data-stu-id="5d2be-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Ersätt Excel-mallen med Word-mallen och lägg till en anpassad XML-kod](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="5d2be-149">Välj **bifogade filer** på fliken **format**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="5d2be-150">Du kan nu mappa elementen i den anpassade **Rapport** XML-koden till innehållskontrollerna i Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="5d2be-151">Om du känner till processen att utforma Word-dokument som formulär som innehåller [innehållskontroll](/office/client-developer/word/content-controls-in-word) som är mappade till delar av [anpassade XML-koder](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), slutföra alla steg i nästa procedur för att skapa dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="5d2be-152">Mer information finns i [Skapa formulär som användare fyller i eller skriver ut i Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="5d2be-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="5d2be-153">Hoppa annars över proceduren.</span><span class="sxs-lookup"><span data-stu-id="5d2be-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="5d2be-154">Hämta ett Word-dokument som har en anpassad XML-kod och mappa data</span><span class="sxs-lookup"><span data-stu-id="5d2be-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="5d2be-155">I Finance, på sidan **Bilagor** välj **Öppna** om du vill hämta den valda mallen från Finance och lagra den lokalt som ett Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="5d2be-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="5d2be-156">Öppna dokumentet du just hämtat i Word-skrivbordsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="5d2be-157">På fliken **Utvecklare**, välj **fönstret för XML-mappning**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d2be-158">Om fliken **Utvecklare** inte visas på menyfliken kan du anpassa den så att den lägger till den.</span><span class="sxs-lookup"><span data-stu-id="5d2be-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="5d2be-159">I fönstret **XML-mappning** i fältet **Anpassad XML-kod**, välj **Rapport** anpassad XML-kod.</span><span class="sxs-lookup"><span data-stu-id="5d2be-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="5d2be-160">Mappa elementen i den valda **Rapport** XML-koden till innehållskontrollerna i Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="5d2be-161">Spara det uppdaterade Word-dokumentet lokalt som **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="5d2be-162">Granska Word-mallen där den anpassade XML-koden mappas till innehållskontroller</span><span class="sxs-lookup"><span data-stu-id="5d2be-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="5d2be-163">I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="5d2be-164">Verifiera att mallen innehåller layouten i det dokument som vi vill generera som ER-utdata.</span><span class="sxs-lookup"><span data-stu-id="5d2be-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="5d2be-165">Innehållskontrollerna som används som platshållare för data som ER kommer att ange i den här mallen vid körning är baserade på mappningarna som är konfigurerade mellan elementen i den anpassade **Rapport** XML-koden och innehållskontrollerna i Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Förhandsgranska Word-mall i skrivbordsprogrammet](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="5d2be-167">Överför Word-mallen där den anpassade XML-koden mappas till innehållskontroller</span><span class="sxs-lookup"><span data-stu-id="5d2be-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="5d2be-168">I Finance, på sidan **Bilagor** välj **Ta bort** för att ta bort Word-mallen som inte har några mappningar mellan elementen i den anpassade **Rapport** XML-koden och innehållskontroller.</span><span class="sxs-lookup"><span data-stu-id="5d2be-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="5d2be-169">Välj **Ja** för att bekräfta ändringen.</span><span class="sxs-lookup"><span data-stu-id="5d2be-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="5d2be-170">Välj **Ny** \> **Fil** för att lägga till en ny mallfil som innehåller mappningar mellan elementen i anpassad **Rapport** XML-koden och innehållskontrollerna.</span><span class="sxs-lookup"><span data-stu-id="5d2be-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d2be-171">Du måste välja en dokumenttyp som har [konfigurerats](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrarna för att ange minne för ER-formatmallar.</span><span class="sxs-lookup"><span data-stu-id="5d2be-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="5d2be-172">Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReportBounded.docx** som du hämtat eller förberett genom att gå igenom proceduren i avsnittet [Hämta ett Word som har anpassad XML-kod till datamappning](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="5d2be-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="5d2be-173">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-173">Select **OK**.</span></span>
5. <span data-ttu-id="5d2be-174">Stäng sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="5d2be-175">På sidan **Formatdesigner** i fältet **Mall**, välj det dokument som du just laddade ner.</span><span class="sxs-lookup"><span data-stu-id="5d2be-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="5d2be-176">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-176">Select **Save**.</span></span>
8. <span data-ttu-id="5d2be-177">Stäng sidan **Formatdesigner**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="5d2be-178">Markera det konfigurerade formatet som körbart</span><span class="sxs-lookup"><span data-stu-id="5d2be-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="5d2be-179">Om du vill köra utkastversionen för det redigerbara formatet måste du göra det [körbart](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="5d2be-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="5d2be-180">I Finance på sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="5d2be-181">I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="5d2be-182">Välj **redigera** för att göra den aktuella sidan klar för redigering.</span><span class="sxs-lookup"><span data-stu-id="5d2be-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="5d2be-183">För den för närvarande valda konfigurationen **Rapport över exempelkalkylblad** ange alternativet **Kör utkast** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="5d2be-184">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="5d2be-185">Kör formatet för att skapa utdata i Word-format</span><span class="sxs-lookup"><span data-stu-id="5d2be-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="5d2be-186">I Finance, gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="5d2be-187">Välj en betalningsjournal som du angav tidigare **Rader**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="5d2be-188">På sidan **Leverantörsbetalningar** markera alla rader i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5d2be-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="5d2be-189">Välj **betalningsstatus** \> **ingen**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-189">Select **Payment status** \> **None**.</span></span>

    ![Betalningar för bearbetning på sidan Leverantörsbetalningar](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="5d2be-191">Välj **Generera betalningar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5d2be-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="5d2be-192">Gör följande i dialogrutan som visas:</span><span class="sxs-lookup"><span data-stu-id="5d2be-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="5d2be-193">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="5d2be-194">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="5d2be-195">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-195">Select **OK**.</span></span>

7. <span data-ttu-id="5d2be-196">I dialogrutan **Parametrar för elektronisk rapportering** väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d2be-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="5d2be-197">De skapade utdata visas i Word-format och innehåller information om de behandlade betalningarna.</span><span class="sxs-lookup"><span data-stu-id="5d2be-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="5d2be-198">Analysera den skapade utleveransen.</span><span class="sxs-lookup"><span data-stu-id="5d2be-198">Analyze the generated output.</span></span>

    ![Genererad utdata i Word-format](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="5d2be-200">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5d2be-200">Additional resources</span></span>

- [<span data-ttu-id="5d2be-201">Utforma en ny ER-konfiguration för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="5d2be-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="5d2be-202">Bädda in bilder och former i dokument som du skapar med ER</span><span class="sxs-lookup"><span data-stu-id="5d2be-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
