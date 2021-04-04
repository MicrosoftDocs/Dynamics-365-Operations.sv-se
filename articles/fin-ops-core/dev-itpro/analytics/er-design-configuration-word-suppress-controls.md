---
title: Ignorera Word-innehållskontroller i genererade rapporter
description: I det här avsnittet beskrivs hur du konfigurerar ett ER-format (elektronisk rapportering) för att generera rapporter som Microsoft Word-filer där innehållskontroller utelämnas.
author: NickSelin
manager: AnnBe
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 81ad25514154dd8982aa4f849f0b2bfeb85270f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562128"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="c9f22-103">Ignorera Word-innehållskontroller i genererade rapporter</span><span class="sxs-lookup"><span data-stu-id="c9f22-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9f22-104">Om du vill generera rapporter som Microsoft Word-dokument måste du designa en mall för rapporterna som ett Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="c9f22-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="c9f22-105">Den här mallen måste innehålla Word-innehållskontroll som platshållare för data som ska fyllas i när den körs.</span><span class="sxs-lookup"><span data-stu-id="c9f22-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="c9f22-106">Om du vill använda Word-dokumentet som skapats som en mall för dina rapporter kan du [konfigurera](er-design-configuration-word.md) en ny [Elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md).</span><span class="sxs-lookup"><span data-stu-id="c9f22-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="c9f22-107">Den här lösningen måste omfatta en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER [format](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="c9f22-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="c9f22-108">ER-formatet måste konfigureras så att det använder den utformat mallen för att generera rapporter.</span><span class="sxs-lookup"><span data-stu-id="c9f22-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="c9f22-109">I version 10.0.6 och senare av Dynamics 365 Finance kan du konfigurera formler i ER-formatet för att ignorera vissa Word-innehållskontroller i genererade dokument.</span><span class="sxs-lookup"><span data-stu-id="c9f22-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="c9f22-110">I följande steg förklaras hur en användare som är tilldelad rollen Systemadministratör eller Elektronisk rapportering funktionell konsult kan konfigurera ett ER-format som genererar rapporter som Word-filer och utelämnar vissa av innehållskontrollerna i de genererade rapporter som har konfigurerats med en Word-mall.</span><span class="sxs-lookup"><span data-stu-id="c9f22-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="c9f22-111">Dessa steg kan slutföras i GBSI-företaget.</span><span class="sxs-lookup"><span data-stu-id="c9f22-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9f22-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c9f22-112">Prerequisites</span></span>

<span data-ttu-id="c9f22-113">För att slutföra dessa steg måste du först avsluta dessa steg i följande uppgiftsguider:</span><span class="sxs-lookup"><span data-stu-id="c9f22-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="c9f22-114">Utforma en konfiguration för rapportgenerering i OPENXML-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="c9f22-115">Återanvänd ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="c9f22-116">När du har slutfört stegen i dessa uppgiftsguider förbereds följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="c9f22-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="c9f22-117">Ett **Rapport över exempelkalkylblad** ER-format som är konfigurerat för att generera ett dokument i Word-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="c9f22-118">En [utkast](general-electronic-reporting.md#component-versioning) version av **Rapport över exempelkalkylblad** ER-format som är markerat som **körbart**</span><span class="sxs-lookup"><span data-stu-id="c9f22-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="c9f22-119">En **elektronisk** betalningsmetod som är konfigurerad att använda **Rapport över exempelkalkylblad** ER-format för bearbetning av leverantörsbetalningar</span><span class="sxs-lookup"><span data-stu-id="c9f22-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="c9f22-120">Du måste också ladda ner och spara följande mall för exempelrapporten:</span><span class="sxs-lookup"><span data-stu-id="c9f22-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="c9f22-121">Bunden mall 2 för betalningsrapport (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="c9f22-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="c9f22-122">Granska den hämtade Word-mallen</span><span class="sxs-lookup"><span data-stu-id="c9f22-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="c9f22-123">I Word-skrivbordsprogrammet, öppna mallfilen **SampleVendPaymDocReportBounded2.docx** som du hämtat tidigare.</span><span class="sxs-lookup"><span data-stu-id="c9f22-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="c9f22-124">Kontrollera att mallfilen innehåller ett samlingsavsnitt som visar de totala betalningsbeloppen för varje valutakod som har uppfyllts i de bearbetade betalningarna.</span><span class="sxs-lookup"><span data-stu-id="c9f22-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="c9f22-125">Sammanfattningsavsnittet finns i ett separat register i Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="c9f22-126">Den första raden i registret innehåller tabellkolumnrubrikerna som avsnittsrubrik.</span><span class="sxs-lookup"><span data-stu-id="c9f22-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="c9f22-127">Den andra raden i registret innehåller kontroll av upprepat innehåll som avsnittsdetaljer.</span><span class="sxs-lookup"><span data-stu-id="c9f22-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="c9f22-128">Den här innehållskontrollen mappas till fältet **SummaryLines** på **Rapport** anpassade XML-delen.</span><span class="sxs-lookup"><span data-stu-id="c9f22-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="c9f22-129">Baserat på den här mappningen associeras innehållskontrollen med **SummaryLines** element i det redigerbara ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9f22-130">Den upprepade innehållskontrollen är taggad av **SummaryLines** nyckel som matchar fältet för den anpassade XML-delen som den har mappats till.</span><span class="sxs-lookup"><span data-stu-id="c9f22-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Word-mall layout](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="c9f22-132">Markera den befintliga ER-rapportkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="c9f22-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="c9f22-133">I följande steg återanvänder du den befintliga ER-konfiguration som du konfigurerade när du slutförde stegen i de tidigare nämnda uppgiftsguiderna.</span><span class="sxs-lookup"><span data-stu-id="c9f22-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="c9f22-134">Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="c9f22-135">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="c9f22-136">På sidan **konfigurationer** i konfigurationsträdet expanderar du **Betalningsmodell** och väljer sedan **Rapport över exempelkalkylblad**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="c9f22-137">Välj **Designer** för att redigera utkastversionen för det valda ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="c9f22-138">Byt ut den aktuella mallen mot den nya mallen</span><span class="sxs-lookup"><span data-stu-id="c9f22-138">Replace the current template with the new template</span></span>

<span data-ttu-id="c9f22-139">För närvarande används SampleVendPaymDocReportBounded.docx-filen som en mall för att skapa utdata i Word-format.</span><span class="sxs-lookup"><span data-stu-id="c9f22-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="c9f22-140">I följande steg kommer du att ersätta den här Word-mallen med den nya Word-mallen, SampleVendPaymDocReportBounded2.docx, som du hämtade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c9f22-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="c9f22-141">Välj **Formatdesigner** på sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="c9f22-142">På sidan **Bilagor** väljer du **Ta bort** om du vill ta bort den befintliga mallen.</span><span class="sxs-lookup"><span data-stu-id="c9f22-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="c9f22-143">Välj **Ja** för att bekräfta raderingen.</span><span class="sxs-lookup"><span data-stu-id="c9f22-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="c9f22-144">Välj **Ny** \> **Fil**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="c9f22-145">Välj **Bläddra** och bläddra sedan till och välj filen **SampleVendPaymDocReportBounded2.docx** som du hämtat tidigare.</span><span class="sxs-lookup"><span data-stu-id="c9f22-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="c9f22-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-146">Select **OK**.</span></span>
7. <span data-ttu-id="c9f22-147">Stäng sidan **Bilagor**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="c9f22-148">På sidan **Formatdesigner** i fältet **Mall**, ange eller välj filen **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="c9f22-149">Kör formatet för att skapa Word-utleverans</span><span class="sxs-lookup"><span data-stu-id="c9f22-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="c9f22-150">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="c9f22-151">På sidan **Leverantörsbetalningar** på fliken **Lista** markera alla betalningar.</span><span class="sxs-lookup"><span data-stu-id="c9f22-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="c9f22-152">Välj **betalningsstatus** \> **ingen**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="c9f22-153">Välj **Generera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="c9f22-154">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="c9f22-155">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="c9f22-156">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-156">Select **OK**.</span></span>
8. <span data-ttu-id="c9f22-157">I dialogrutan **Elektroniska rapportparametrar**, välj **OK** och analysera det genererade resultatet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Betalningar för bearbetning på sidan Leverantörsbetalningar](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="c9f22-159">Resultatet presenteras i Word-format och innehåller sammanfattningsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="c9f22-160">Konfigurera det redigerbara formatet om du vill ignorera sammanfattningsavsnittet</span><span class="sxs-lookup"><span data-stu-id="c9f22-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="c9f22-161">Om du vill ignorera samlingsavsnittet i ett genererat dokument, baserat på begäran av en användare som kör det här ER-formatet, måste du ändra det redigerbara ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="c9f22-162">Gå till **Organisationsadministration** \> **Arbetsplatser** \> **Elektronisk rapportering** och öppna utkastversionen av ER-formatet för redigering.</span><span class="sxs-lookup"><span data-stu-id="c9f22-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="c9f22-163">Välj **rapporteringskonfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="c9f22-164">På sidan **Konfigurationer** i konfigurationsträdet expanderar du **Betalningsmodell** \> **Rapport över exempelkalkylblad**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="c9f22-165">Välj **Designer**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-165">Select **Designer**.</span></span>
5. <span data-ttu-id="c9f22-166">På sidan **Formatdesigner**, expandera **Word** och **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="c9f22-167">På fliken **Mappning**, lägg till en ny datakälla för att fråga användaren vid körning om sammanfattningsavsnittet ska undertryckas:</span><span class="sxs-lookup"><span data-stu-id="c9f22-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="c9f22-168">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="c9f22-169">I dialogrutan **Lägg till datakälla**, välj **Allmän\Användarindataparameter** för att öppna dialogrutan **Användarinmatningsparametrarnas datakällegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="c9f22-170">Skriv **statisk** i fältet **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="c9f22-171">I fältet **Etikett**, ange **Avsluta sammanfattningsavsnittet**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="c9f22-172">I fältet **Åtgärdens datatypnamn**, välj eller ange **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="c9f22-173">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-173">Select **OK**.</span></span>

7. <span data-ttu-id="c9f22-174">Lägg till en ny datakälla av **NoYes** appens uppräkningstyp:</span><span class="sxs-lookup"><span data-stu-id="c9f22-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="c9f22-175">Välj **Lägg till rot**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="c9f22-176">I dialogrutan **Lägg till datakälla**, välj **Dynamics 365 for Operations\Uppräkning** om du vill öppna dialogrutan **Uppräkningens datakällegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="c9f22-177">Skriv **Dokument** i fältet **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="c9f22-178">I fältet **Etikett**, ange **Undertryck alternativ**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="c9f22-179">I fältet **Åtgärdens datatypnamn**, välj eller ange **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="c9f22-180">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-180">Select **OK**.</span></span>

8. <span data-ttu-id="c9f22-181">För det valda formatelementet **SummaryLines**, konfigurera formeln för att ange när Word-innehållskontrollen som är associerad med det valda formatelementet ska undertryckas:</span><span class="sxs-lookup"><span data-stu-id="c9f22-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="c9f22-182">PÅ fliken **Mappning** i avsnittet **Borttaget**, välj **Redigera** om du vill öppna sidan **[Formeldesigner](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="c9f22-183">I fältet **Formel** anger du formeln `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="c9f22-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="c9f22-184">Stäng sidan **Spara** och **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9f22-185">Formeln tillämpas på ett genererat dokument när **alla andra formatelement har körts**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="c9f22-186">När du vill använda den här formeln hittas en Word-innehållskontroll som är taggad som ett formatelement som formeln är konfigurerad för (**SummaryLines** i det här fallet) hittas i ett genererat dokument.</span><span class="sxs-lookup"><span data-stu-id="c9f22-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="c9f22-187">Den innehållskontrollen tas då bort helt och hållet, tillsammans med den rad i Word-registret som innehåller kontrollen.</span><span class="sxs-lookup"><span data-stu-id="c9f22-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="c9f22-188">Detaljraden i sammanfattningsavsnittet tas bort från det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="c9f22-189">Vid designtid kan du konfigurera formeln **borttagen** för ett formatelement, även om ingen innehållskontroll i Word-mallen som du använder har en tagg som matchar namnet på ett formatelement som **borttagen** har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="c9f22-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="c9f22-190">När du validerar formatet vid designtid får du en [varning](er-components-inspections.md#i14) om denna inkonsekvens.</span><span class="sxs-lookup"><span data-stu-id="c9f22-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="c9f22-191">Vid körning kastas ett undantag om ingen innehållskontroll i Word-mallen som du använder har en tagg som matchar namnet på ett formatelement som egenskapen **Borttaget** har konfigurerats för.</span><span class="sxs-lookup"><span data-stu-id="c9f22-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="c9f22-192">Ställ in alternativet **Mappning** i avsnittet **Borttaget**, ange alternativet **Med överordnad** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9f22-193">Du måste ställa in alternativet **Ja** om du vill ta bort hela Word-registret som överordnat objekt för raden som innehåller information om sammanfattningsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="c9f22-194">Om du ställer in detta alternativ till **Nej**, finns avsnittsrubrikraden kvar i det genererade dokumentet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="c9f22-195">Välj **Spara** om du vill ändra till redigerbart format.</span><span class="sxs-lookup"><span data-stu-id="c9f22-195">Select **Save** to save your changes to the editable format.</span></span>

    ![Genererad utdata i Word-format](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="c9f22-197">Kör det modifierade formatet för att skapa Word-utleverans</span><span class="sxs-lookup"><span data-stu-id="c9f22-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="c9f22-198">Gå till **Leverantörsreskontra** \> **Betalningar** \> **Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="c9f22-199">Välj betalningsjournalen som du skapade och välj sedan **Rader**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="c9f22-200">På sidan **Leverantörsbetalningar** markera alla rader och välj sedan **Betalningsstatus** \> **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="c9f22-201">Välj **Generera betalningar**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="c9f22-202">I fältet **Betalningsmetod** väljer du **Elektronisk**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="c9f22-203">I fältet **Bankkonto** väljer du **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="c9f22-204">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-204">Select **OK**.</span></span>
8. <span data-ttu-id="c9f22-205">I dialogrutan **Parametrar för elektroniska rapporter** i fältet **Avsluta sammanfattningsavsnittet**, välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c9f22-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="c9f22-206">Välj **OK** och analysera det genererade resultatet.</span><span class="sxs-lookup"><span data-stu-id="c9f22-206">Select **OK**, and analyze the generated output.</span></span>

    ![Genererad utdata i Word-format](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="c9f22-208">Lägg märke till att utdata inte innehåller sammanfattningsavsnittet eftersom det har utelämnats.</span><span class="sxs-lookup"><span data-stu-id="c9f22-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9f22-209">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c9f22-209">Additional resources</span></span>

- [<span data-ttu-id="c9f22-210">Utforma en konfiguration för rapportgenerering i OPENXML-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="c9f22-211">Utforma en ny ER-konfiguration för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="c9f22-212">Återanvänd ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="c9f22-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="c9f22-213">Granska den konfigurerade ER-komponenten för att förhindra körningsproblem</span><span class="sxs-lookup"><span data-stu-id="c9f22-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]