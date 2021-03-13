---
title: Utforma en ny ER-konfiguration för att generera rapporter i Word-format
description: I det här avsnittet beskrivs hur användare kan konfigurera ett nytt ER-format (elektronisk rapportering) för att generera rapporter som Microsoft Word-dokument.
author: NickSelin
manager: AnnBe
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 535e46eb033bf2796ab8e4b0d2e29767ad0a8cdf
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094164"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a><span data-ttu-id="59dd4-103">Utforma en ny ER-konfiguration för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="59dd4-103">Design a new ER configuration to generate reports in Word format</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59dd4-104">Om du vill generera rapporter som Microsoft Word-dokument måste du designa en mall för rapporterna med hjälp av exempelvis Word-skrivbordsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="59dd4-104">To generate reports as Microsoft Word documents, you must design a template for the reports by using, for example, the Word desktop application.</span></span> <span data-ttu-id="59dd4-105">I följande bild visas exempelmallen för kontrollrapporten som kan genereras för att visa information om bearbetade leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="59dd4-105">The following illustration shows the sample template for the control report that can be generated to show details of processed vendor payments.</span></span>

![Exempelmall för kontrollrapporten i Word-skrivbordsprogrammet](./media/er-design-configuration-word-image1.png)

<span data-ttu-id="59dd4-107">Om du vill använda ett Word-dokument som mall för rapporter i Word-format kan du konfigurera en ny [Elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md).</span><span class="sxs-lookup"><span data-stu-id="59dd4-107">To use a Word document as a template for reports in Word format, you can configure a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="59dd4-108">Den här lösningen måste omfatta en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER [format](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="59dd4-108">This solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span>

> [!NOTE]
> <span data-ttu-id="59dd4-109">När du skapar en ny ER-formatkonfiguration för att generera rapporter i Word-format, måste du antingen välja **Word** som formattyp i dialogrutan **Skapa konfiguration** eller lämna fältet **Formattyp** tomt.</span><span class="sxs-lookup"><span data-stu-id="59dd4-109">When you create a new ER format configuration to generate reports in Word format, you must either select **Word** as the format type in the **Create configuration** drop-down dialog box or leave the **Format type** field blank.</span></span>

![Skapa en anpassad konfiguration av format på sidan konfigurationer](./media/er-design-configuration-word-image2.gif)

<span data-ttu-id="59dd4-111">ER-formatkomponenten i lösningen måste innehålla ormatelementet **Excel\\Fil** och det formatelementet måste länkas till det Word-dokument som ska användas som mall för genererade rapporter vid körning.</span><span class="sxs-lookup"><span data-stu-id="59dd4-111">The ER format component of the solution must contain the **Excel\\File** format element, and that format element must be linked to the Word document that will be used as the template for generated reports at runtime.</span></span> <span data-ttu-id="59dd4-112">Om du vill konfigurera ER-formatkomponenten måste du öppna [utkast](general-electronic-reporting.md#component-versioning) versionen för den skapade ER-konfigurationen i ER-formatdesignern.</span><span class="sxs-lookup"><span data-stu-id="59dd4-112">To configure the ER format component, you must open the [draft](general-electronic-reporting.md#component-versioning) version of the created ER configuration in the ER format designer.</span></span> <span data-ttu-id="59dd4-113">Lägg sedan till elementet **Excel\\Fil**, koppla Word-mallen till det redigerbara ER-formatet och länka mallen till **Excel\\Fil** som du har lagt till.</span><span class="sxs-lookup"><span data-stu-id="59dd4-113">Then add the **Excel\\File** element, attach your Word template to the editable ER format, and link that template to the **Excel\\File** element that you added.</span></span>

> [!NOTE]
> <span data-ttu-id="59dd4-114">När du bifogar en mall manuellt måste du använda en [dokumenttyp](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) som tidigare har [konfigurerats](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) i ER-parametrar för att lagra mallar i ER-format.</span><span class="sxs-lookup"><span data-stu-id="59dd4-114">When you attach a template, you must use a [document type](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) that has previously been [configured](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

![Koppla en mall på sidan Formatdesigner](./media/er-design-configuration-word-image3.gif)

<span data-ttu-id="59dd4-116">Du kan lägga till **Excel\\Intervall** och **Excel\\Cell** kapslade element för elementet **Excel\\Fil** om du vill ange strukturen för data som ska anges i genererade rapporter under körning.</span><span class="sxs-lookup"><span data-stu-id="59dd4-116">You can add **Excel\\Range** and **Excel\\Cell** nested elements for the **Excel\\File** element to specify the structure of data that will be entered in generated reports at runtime.</span></span> <span data-ttu-id="59dd4-117">Därefter måste du knyta dessa element till datakällorna i det redigerbara ER-formatet för att ange de faktiska data som ska anges i genererade rapporter vid körning.</span><span class="sxs-lookup"><span data-stu-id="59dd4-117">You must then bind those elements to data sources of the editable ER format to specify the actual data that will be entered in generated reports at runtime.</span></span>

![Lägga till kapslade element på sidan Format designer](./media/er-design-configuration-word-image4.gif)

<span data-ttu-id="59dd4-119">När du sparar ändringarna i ER-formatet vid tid för designen, lagras den hierarkiska formatstrukturen i den kopplade Word-mallen som en [anpassad XML-del](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) med namnet **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-119">When you save your changes to the ER format at design time, the hierarchical format structure is stored in the attached Word template as a [custom XML part](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) that is named **Report**.</span></span> <span data-ttu-id="59dd4-120">Du måste komma åt den ändrade mallen, hämta den från Finance, lagra den lokalt och öppna den i Word-skrivbordsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="59dd4-120">You must access the modified template, download it from Finance, store it locally, and open it in the Word desktop application.</span></span> <span data-ttu-id="59dd4-121">I följande bild visas den lokalt lagrade exempelmallen för kontrollrapporten som innehåller den **rapport** anpassade XML-delen.</span><span class="sxs-lookup"><span data-stu-id="59dd4-121">The following illustration shows the locally stored sample template for the control report that contains the **Report** custom XML part.</span></span>

![Granska exempel rapportmallen i Word-skrivbordsprogrammet](./media/er-design-configuration-word-image5.gif)

<span data-ttu-id="59dd4-123">När bindningar av formatelementen **Excel\\Intervall** och **Excel\\Cell** körs vid körning, data som varje bindning levererar kommer till det genererade Word-dokumentet som ett enskilt fält i anpassade XML-delen för **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-123">When bindings of **Excel\\Range** and **Excel\\Cell** format elements are run at runtime, the data that every binding delivers comes into the generated Word document as an individual field of the **Report** custom XML part.</span></span> <span data-ttu-id="59dd4-124">För att ange värdena från fälten för den anpassade XML-delen i ett genererat dokument måste du lägga till lämpligt Word [innehållskontroller](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) till din Word-mall som fungerar som platshållare för data som ska fyllas i när de körs.</span><span class="sxs-lookup"><span data-stu-id="59dd4-124">To enter the values from the fields of the custom XML part in a generated document, you must add the appropriate Word [content controls](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) to your Word template to serve as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="59dd4-125">När du vill ange hur innehållskontroller ska fyllas i mappar du alla innehållskontroller till lämpligt fält i den anpassade XML-delen för **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-125">To specify how content controls are filled in, map every content control to the appropriate field of the **Report** custom XML part.</span></span>

![Lägga till och mappa innehållskontroller i Word-skrivbordprogrammet](./media/er-design-configuration-word-image6.gif)

<span data-ttu-id="59dd4-127">Du måste sedan ersätta den ursprungliga Word-mallen i det redigerbara ER-formatet med den modifierade mallen som nu innehåller Word-innehållskontroller som har mappats till fälten i den anpassade XML-delen för **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-127">You must then replace the original Word template of the editable ER format with the modified template that now contains Word content controls that were mapped to the fields of the **Report** custom XML part.</span></span>

![Ersätta en mall på sidan Formatdesigner](./media/er-design-configuration-word-image7.gif)

<span data-ttu-id="59dd4-129">När du kör det konfigurerade ER-formatet används den kopplade Word-mallen för att generera en ny rapport.</span><span class="sxs-lookup"><span data-stu-id="59dd4-129">When you run the configured ER format, the attached Word template is used to generate a new report.</span></span> <span data-ttu-id="59dd4-130">De faktiska data lagras i Word-rapporten som en anpassad XML-del med namnet **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-130">The actual data is stored in the Word report as a custom XML part that is named **Report**.</span></span> <span data-ttu-id="59dd4-131">När den genererade rapporten öppnas fylls Word-innehållskontroller i med data från den anpassade XML-delen för **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="59dd4-131">When the generated report is opened, the Word content controls are filled in with data from the **Report** custom XML part.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="59dd4-132">Vanliga frågor</span><span class="sxs-lookup"><span data-stu-id="59dd4-132">Frequently asked questions</span></span>

<span data-ttu-id="59dd4-133">**Fråga:** Jag konfigurerat ett ER-format för att skriva ut ett Word-dokument som innehåller en företagsadress.</span><span class="sxs-lookup"><span data-stu-id="59dd4-133">**Question:** I configured an ER format to print a Word document that contains a company address.</span></span> <span data-ttu-id="59dd4-134">I Word-mallen för det här ER-formatet infogade jag en RTF-innehållskontroll för att presentera en företagsadress.</span><span class="sxs-lookup"><span data-stu-id="59dd4-134">In the Word template for this ER format, I inserted a rich text content control to present a company address.</span></span> <span data-ttu-id="59dd4-135">I Finance har jag angett företagsadressen som flerradstext och valt **Retur** om du vill lägga till en transportretur för varje rad jag angav.</span><span class="sxs-lookup"><span data-stu-id="59dd4-135">In Finance, I entered the company address as multiline text and selected **Enter** to add a carriage return for every line that I entered.</span></span> <span data-ttu-id="59dd4-136">Därför förväntar jag mig att företagsadressen visas som flerradstext i genererade dokument.</span><span class="sxs-lookup"><span data-stu-id="59dd4-136">Therefore, I expect the company address to appear as multiline text in generated documents.</span></span> <span data-ttu-id="59dd4-137">Adressen visas dock som en enskild textrad som innehåller särskilda symboler istället för returer.</span><span class="sxs-lookup"><span data-stu-id="59dd4-137">However, the address appears as a single line of text that contains special symbols instead of carriage returns.</span></span> <span data-ttu-id="59dd4-138">Vad är det för fel med inställningarna?</span><span class="sxs-lookup"><span data-stu-id="59dd4-138">What is wrong with my settings?</span></span>

<span data-ttu-id="59dd4-139">**Svar:** Istället för att använda en kontroll för innehåll med rik text måste du använda en kontroll för enkel textinnehåll och välja kryssrutan **Tillåt transportreturer (flera paragrafer)** i kontrollens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="59dd4-139">**Answer:** Instead of using a rich text content control, you must use a plain text content control and select the **Allow carriage returns (multiple paragraphs)** check box in the control's properties.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59dd4-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="59dd4-140">Additional resources</span></span>

- [<span data-ttu-id="59dd4-141">Återanvända ER-konfigurationer med Excel-mallar för att generera rapporter i Word-format</span><span class="sxs-lookup"><span data-stu-id="59dd4-141">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="59dd4-142">Bädda in bilder och former i dokument som du skapar med ER</span><span class="sxs-lookup"><span data-stu-id="59dd4-142">Embed images and shapes in documents that you generate by using ER</span></span>](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)