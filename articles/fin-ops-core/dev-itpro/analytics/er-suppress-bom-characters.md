---
title: Designa ER-konfigurationer för att ignorera strukturlistetecken i genererade filer
description: I det här avsnittet beskrivs hur du konfigurerar ett ER-format (elektronisk rapportering) för att generera rapporter som ignorerar byteordningsmärke.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9fabc308b1b0682c6fdce3e81e7335417846bebd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743543"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="a2e7d-103">Designa ER-konfigurationer för att ignorera strukturlistetecken i genererade filer</span><span class="sxs-lookup"><span data-stu-id="a2e7d-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2e7d-104">Du kan utforma [elektronisk rapportering (ER)](general-electronic-reporting.md) [lösning](er-quick-start1-new-solution.md) för att skapa utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="a2e7d-105">Om du vill generera dokumenten som text- eller XML-filer måste lösningen innehålla en ER [konfiguration](general-electronic-reporting.md#Configuration) som innehåller en komponent för ER [format](general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="a2e7d-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="a2e7d-106">Om du vill ange den [teckenkodning](https://docs.microsoft.com/windows/win32/intl/character-sets) som representerar uppsättningen tecken i genererade filer måste ER-formatet innehålla formatelementet **Vanlig\\Fil**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="a2e7d-107">Om du vill konfigurera ER-formatkomponenten måste du öppna versionen [utkast](general-electronic-reporting.md#component-versioning) för ER-konfigurationen i ER-formatdesignern och lägga till elementet **Vanlig\\Fil**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="a2e7d-108">I fältet **kodning** ange kodning av utgående filer som genereras när programmet körs med hjälp av komponenten.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="a2e7d-109">Om formatet innehåller fel kodningsnamn uppstår ett fel när du sparar ändringarna av formatets inställningar.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Lägga till rotelement på sidan Formatdesigner](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="a2e7d-111">Om du anger **UTF-8**, **UTF-16** eller **UTF-32** som kodning blir alternativet **Undertryck strukturlistetecken** tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="a2e7d-112">Ställ in det här alternativet på **Ja** för att undertrycka [byteordningsmärke (strukturlista) tecken](https://docs.microsoft.com/globalization/encoding/byte-order-mark) i utgående filer som genereras vid körning när det redigerbara ER-formatet körs.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="a2e7d-113">Om du lämnar fältet **Kodning** används standardvärdet **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Ange alternativet Ignorera strukturlistetecken på sidan Formatdesigner](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="a2e7d-115">Om du vill granska funktionen vid körning ska du gå igenom lämplig procedur.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="a2e7d-116">Du kan till exempel utföra stegen i ämnet [Periodisera körning av XML-element i ER-format](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="a2e7d-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="a2e7d-117">När du har utfört stegen i avsnittet [Ändra formatet så att beräkningen baseras på genererade utdata](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) i det ämnet, följ dessa ytterligare steg.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="a2e7d-118">Ange UTF-kodning:</span><span class="sxs-lookup"><span data-stu-id="a2e7d-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="a2e7d-119">Välj elementet **Rapport** av typen **Vanlig\\Fil**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="a2e7d-120">I fältet **Kodning** ange **UTF-8**-kodningen.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="a2e7d-121">Generera en XML-fil som innehåller ett strukturlistetecken:</span><span class="sxs-lookup"><span data-stu-id="a2e7d-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="a2e7d-122">Ange alternativet **Ignorera strukturlistetecken** till **Nej** om du vill inkludera strukturlistetecken i genererade XML-filer.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="a2e7d-123">Slutför stegen i avsnittet [Skjut upp körningen av sammanfattning XML-element så att den beräknade summan används](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) i ämnet [Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md) och spara den genererade filen som **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="a2e7d-124">Generera en XML-fil som inte innehåller ett strukturlistetecken:</span><span class="sxs-lookup"><span data-stu-id="a2e7d-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="a2e7d-125">Ange alternativet **Ignorera strukturlistetecken** till **Ja** om du vill undertrycka strukturlistetecken i genererade XML-filer.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="a2e7d-126">Slutför stegen i avsnittet [Skjut upp körningen av sammanfattning XML-element så att den beräknade summan används](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) i ämnet [Skjuta upp körningen av XML-element i ER-format](er-defer-xml-element.md) och spara den genererade filen som **SampleXmlReport (1).xml**.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="a2e7d-127">Jämför de genererade filerna i ett filjämförelseverktyg.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="a2e7d-128">Den första skillnaden som du kommer att märka finns i filrubriken.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="a2e7d-129">Filen SampleXmlReport.xml innehåller ett strukturlistetecken, där SampleXmlReport(1).xml-filen inte finns.</span><span class="sxs-lookup"><span data-stu-id="a2e7d-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Jämför de genererade filerna med ett filjämförelseverktyg](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="a2e7d-131">Se även</span><span class="sxs-lookup"><span data-stu-id="a2e7d-131">See also</span></span>

- [<span data-ttu-id="a2e7d-132">Skjuta upp körningen av XML-element i ER-format</span><span class="sxs-lookup"><span data-stu-id="a2e7d-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]