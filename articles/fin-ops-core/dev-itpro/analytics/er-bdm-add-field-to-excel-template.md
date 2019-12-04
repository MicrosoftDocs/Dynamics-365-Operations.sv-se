---
title: Lägga till nya fält i en affärsdokumentmall i Microsoft Excel
description: Det här avsnittet innehåller information om hur du lägger till nya fält i en affärsdokumentmall i Microsoft Excel genom att använda funktionen för hantering av affärsdokument.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d6e0f2c914b8d348ef6eac42557fb46c53df04a9
ms.sourcegitcommit: d16d370dab734e09312cb06711beca9cca52d4c9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2019
ms.locfileid: "2809530"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="5b72d-103">Lägga till nya fält i en affärsdokumentmall i Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5b72d-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5b72d-104">Du kan lägga till nya fält i en mall som används för att generera affärsdokument i Microsoft Excel-formatet.</span><span class="sxs-lookup"><span data-stu-id="5b72d-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="5b72d-105">Dessa fält kan läggas till som platshållare som används för att fylla genererade dokument med nödvändig information från programmet.</span><span class="sxs-lookup"><span data-stu-id="5b72d-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="5b72d-106">För varje fält som du lägger till kan du också ange en bindning till datakällorna, där du anger vilka programdata som ska anges i fältet när mallen används för att generera affärsdokument.</span><span class="sxs-lookup"><span data-stu-id="5b72d-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="5b72d-107">Om du vill veta mer om den här funktionen fyller du i exemplet i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5b72d-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="5b72d-108">I det här exemplet visas hur du uppdaterar en mall så att fälten fyller i fritextfakturaformulär som skapas.</span><span class="sxs-lookup"><span data-stu-id="5b72d-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="5b72d-109">Konfigurera affärsdokumenthantering för att redigera mallar</span><span class="sxs-lookup"><span data-stu-id="5b72d-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="5b72d-110">Eftersom Hantering av affärsdokument (BDM) bygger ovanpå ramverket [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md) måste du konfigurera de nödvändiga återställnings- och BDM-parametrarna innan du kan börja arbeta med BDM.</span><span class="sxs-lookup"><span data-stu-id="5b72d-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="5b72d-111">Logga in på instansen av Microsoft Dynamics 365 Finance som systemadministratör.</span><span class="sxs-lookup"><span data-stu-id="5b72d-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="5b72d-112">Slutför följande steg i exemplet i avsnittet [Hantering av affärsdokument – översikt:](er-business-document-management.md):</span><span class="sxs-lookup"><span data-stu-id="5b72d-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="5b72d-113">Konfigurera ER-parametrar.</span><span class="sxs-lookup"><span data-stu-id="5b72d-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="5b72d-114">Starta BDM.</span><span class="sxs-lookup"><span data-stu-id="5b72d-114">Turn on BDM.</span></span>

<span data-ttu-id="5b72d-115">Nu kan du börja använda BDM för att redigera mallar för affärsdokument.</span><span class="sxs-lookup"><span data-stu-id="5b72d-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="5b72d-116">Importera ER-lösningar som innehåller en mall</span><span class="sxs-lookup"><span data-stu-id="5b72d-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="5b72d-117">Exemplet i den här proceduren använder den officiellt publicerade ER-lösningen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="5b72d-118">Du måste importera ER-konfigurationer för lösningen till din aktuella Finance-instans.</span><span class="sxs-lookup"><span data-stu-id="5b72d-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="5b72d-119">Konfigurationen för ER-format **Fritextfaktura (Excel)** för den här lösningen innehåller affärsdokumentmallen i Excel-format som kan redigeras med BDM.</span><span class="sxs-lookup"><span data-stu-id="5b72d-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="5b72d-120">Importera den senaste versionen av den här konfigurationen för ER-format från Microsoft Dynamics Lifecycle Service (LCS).</span><span class="sxs-lookup"><span data-stu-id="5b72d-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="5b72d-121">De motsvarande konfigurationerna för ER-datamodell och ER-modellmappning kommer att importeras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5b72d-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="5b72d-122">Mer information om att importera ER-konfigurationer finns i [Hantera livscykeln för konfiguration av elektronisk rapportering](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="5b72d-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Sidan LCS delat tillgångsbibliotek](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="5b72d-124">Redigera ER-lösningsmallen</span><span class="sxs-lookup"><span data-stu-id="5b72d-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="5b72d-125">Logga in som en användare med åtkomst till sidan **arbetsyta för hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="5b72d-126">Öppna arbetsytan för **hantering av affärsdokument**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-126">Open the **Business document management** workspace.</span></span>

    ![Arbetsyta för hantering av affärsdokument](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="5b72d-128">I rutnätet väljer du mallen **fritextfaktura (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="5b72d-129">Välj **ny mall** i det högra fönstret om du vill skapa en ny mall som baseras på den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="5b72d-130">I fältet **rubrik** anger du **fritextfaktura (Excel) Contoso** som rubrik för den nya mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="5b72d-131">Välj **OK** för att bekräfta starten av redigeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="5b72d-132">Sidan BDM-mallredigerare visas.</span><span class="sxs-lookup"><span data-stu-id="5b72d-132">The BDM template editor page appears.</span></span> <span data-ttu-id="5b72d-133">Du kan använda Microsoft Office 365 för att redigera den valda mallen online i den inbäddade kontrollen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-133">You can use Microsoft Office 365 to edit the selected template online in the embedded control.</span></span>

![Sidan BDM-mallredigerare](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="5b72d-135">Lägga till etiketten för ett nytt fält i mallen</span><span class="sxs-lookup"><span data-stu-id="5b72d-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="5b72d-136">På sidan BDM-mallredigerare, på Excel-menyfliken på fliken **Visa**, välj kryssrutan **Rubriker och stödlinjer** för den redigerbara Excel-mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Kryssrutorna rubriker och stödlinjer är markerade](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="5b72d-138">Markera cellerna **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="5b72d-139">I Excel-menyfliksområdet på fliken **Start** välj **Sammanfoga och centrera** om du vill sammanfoga de markerade cellerna till en ny sammanfogad **E8:F8**-cell.</span><span class="sxs-lookup"><span data-stu-id="5b72d-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="5b72d-140">I den sammanfogade cellen **E8:F8**, ange **URL**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="5b72d-141">Markera sammanfogad cell **E7:F7**, välj **Hämta format** och markera sedan sammanfogad cell **E8:F8** om du vill formatera den på samma sätt som den sammanfogade cellen **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Nytt fält har lagts till i mallen](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="5b72d-143">Formatera mallen till att reservera utrymme för ett nytt fält</span><span class="sxs-lookup"><span data-stu-id="5b72d-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="5b72d-144">Välj sammanfogad cell **G8:H8**på sidan BDM mallredigerare.</span><span class="sxs-lookup"><span data-stu-id="5b72d-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="5b72d-145">I Excel-menyfliksområdet på fliken **Start** välj **Sammanfoga och centrera** om du vill sammanfoga de markerade cellerna till en ny sammanfogad **G8:H8**-cell.</span><span class="sxs-lookup"><span data-stu-id="5b72d-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="5b72d-146">Markera sammanfogad cell **G7:H7**, välj **Hämta format** och markera sedan sammanfogad cell **G8:H8** om du vill formatera den på samma sätt som den sammanfogade cellen **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Utrymme reserverat för det nya fältet](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="5b72d-148">I fältet **Namn** välj **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="5b72d-149">Intervallet **CompanyInfo** för den aktuella Excel-mallen innehåller alla fält som används för att fylla rubriken för en genererad rapport med information om det aktuella företaget som säljare.</span><span class="sxs-lookup"><span data-stu-id="5b72d-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![CompanyInfo-intervall har valts](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="5b72d-151">Lägg till ett nytt fält till mallen</span><span class="sxs-lookup"><span data-stu-id="5b72d-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="5b72d-152">På sidan **BDM-mallredigerare** i åtgärdsfönstret, välj **Visa format**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="5b72d-153">I fönstret **Mallstruktur** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b72d-154">Du måste justera avsnittet i den mall som du vill använda som ett nytt fält.</span><span class="sxs-lookup"><span data-stu-id="5b72d-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="5b72d-155">Du har redan gjort denna justering genom att formatera sammanfogad cell **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Lägg till ett nytt fält till mallen](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="5b72d-157">Välj **Excel\Cell** om du vill lägga till ett nytt fält som en cell i mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="5b72d-158">Du kan välja **Excel\intervall** om du vill lägga till ett nytt intervall i mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="5b72d-159">Det angivna intervallet kan innehålla flera celler.</span><span class="sxs-lookup"><span data-stu-id="5b72d-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="5b72d-160">Du kan lägga till dessa celler senare.</span><span class="sxs-lookup"><span data-stu-id="5b72d-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="5b72d-161">Observera att **CompanyInfo** väljs automatiskt i fönstret **mallstruktur**, eftersom det är den mest lämpliga överordnade komponenten i den aktuella mallstrukturlistan för det fält som du lägger till.</span><span class="sxs-lookup"><span data-stu-id="5b72d-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="5b72d-162">I fältet **Excel-intervall** anger du **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="5b72d-163">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-163">Select **OK**.</span></span>

    ![CompanyURL_Value fält som lagts till i mallstrukturlistan](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="5b72d-165">I fönstret **mallstruktur** väljer du ellipsknappen (...) och väljer **Visa bindningar**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Visa valda bindningar](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="5b72d-167">I fönstret **mallstruktur** visas nu de datakällor som är tillgängliga i det underliggande ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="5b72d-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="5b72d-168">Välj **CompanyInfo_Value** som fältet som du vill binda till en datakälla för det underliggande ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="5b72d-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="5b72d-169">I avsnittet **Datakällor** i fönstret **Mallstruktur** expanderar du **Modell \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="5b72d-170">Under **CompanyInfo**väljer du artikeln **WebsiteURI**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Artikeln WebsiteURI har markerats](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="5b72d-172">Välj **bind**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-172">Select **Bind**.</span></span>
11. <span data-ttu-id="5b72d-173">I fönstret **mallstruktur** väljer du **spara** och stänger sedan sidan BDM mallredigerare.</span><span class="sxs-lookup"><span data-stu-id="5b72d-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="5b72d-174">På arbetsytan **Hantering av affärsdokument** visar fliken **Mall** i det högra fönstret den uppdaterade mallen.</span><span class="sxs-lookup"><span data-stu-id="5b72d-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="5b72d-175">I rutnätet observerar du att fältet **Status** för den redigerade mallen har ändrats till **Utkast** och fältet **Ändring** inte längre är tomt.</span><span class="sxs-lookup"><span data-stu-id="5b72d-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="5b72d-176">Dessa ändringar anger att processen för redigering av den här mallen har startats.</span><span class="sxs-lookup"><span data-stu-id="5b72d-176">These changes indicate that the process of editing this template has been started.</span></span>

![Redigerad mall på arbetsytan för hantering av affärsdokument](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="5b72d-178">Granska företagsinställningar</span><span class="sxs-lookup"><span data-stu-id="5b72d-178">Review company settings</span></span>

1.  <span data-ttu-id="5b72d-179">Gå till **Organisationsadministration \> Organisationer \> Juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="5b72d-180">På snabbfliken **kontaktinformation** kontrollerar du att företags-URL:en har angetts.</span><span class="sxs-lookup"><span data-stu-id="5b72d-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![Företags-URL som angetts på sidan juridiska personer](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="5b72d-182">Generera affärsdokument för att testa den uppdaterade mallen</span><span class="sxs-lookup"><span data-stu-id="5b72d-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="5b72d-183">I programmet, ändra företaget till **USMF** och gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="5b72d-184">Välj faktura **FTI-00000002** och välj sedan **Utskriftshantering**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="5b72d-185">I det vänstra fönstret expanderar du **Modul - kundreskontra \> Dokument \> Fritextfaktura**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="5b72d-186">Under **Fritextfaktura**, välj nivån **Originaldokument** för att ange omfånget med fakturor för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="5b72d-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="5b72d-187">I det högra fönstret, i fältet **rapportformat**, väljer du **fritextfaktura (Excel) Contoso**-mallen för angiven dokumentnivå.</span><span class="sxs-lookup"><span data-stu-id="5b72d-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Mallen fritextfaktura (Excel) Contoso har valts](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="5b72d-189">Tryck på **Esc** för att stänga den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="5b72d-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="5b72d-190">Välj **Skriv ut \> Markerade**.</span><span class="sxs-lookup"><span data-stu-id="5b72d-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="5b72d-191">Hämta det genererade dokumentet och öppna det i Excel.</span><span class="sxs-lookup"><span data-stu-id="5b72d-191">Download the generated document, and open it in Excel.</span></span>

    ![Fritextfaktura i Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="5b72d-193">Den modifierade mallen används för att generera fritextfakturarapporten för den valda artikeln.</span><span class="sxs-lookup"><span data-stu-id="5b72d-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="5b72d-194">Om du vill analysera hur den här rapporten påverkas av de ändringar som du har gjort i mallen kan du köra den här rapporten i en programsession direkt efter att du har ändrat mallen i en annan programsession.</span><span class="sxs-lookup"><span data-stu-id="5b72d-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="5b72d-195">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="5b72d-195">Related links</span></span>

[<span data-ttu-id="5b72d-196">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="5b72d-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="5b72d-197">Hantering av affärsdokument – översikt</span><span class="sxs-lookup"><span data-stu-id="5b72d-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="5b72d-198">Utforma en konfiguration för rapportgenerering i OPENXML-format</span><span class="sxs-lookup"><span data-stu-id="5b72d-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)
