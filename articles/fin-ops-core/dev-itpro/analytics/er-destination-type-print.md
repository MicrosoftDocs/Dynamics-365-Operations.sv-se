---
title: ER-målstyp för skrivare
description: I det här avsnittet beskrivs hur du konfigurerar en skrivare för varje MAPP- eller FIL-komponent i ett elektroniskt rapporteringsformat (ER).
author: NickSelin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 83081f8c17a903cd447a34596df2e61ebda0cafc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753442"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="75558-103">Skrivardestination</span><span class="sxs-lookup"><span data-stu-id="75558-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75558-104">Du kan skicka ett genererat dokument direkt till en nätverksskrivare för direkt utskrift.</span><span class="sxs-lookup"><span data-stu-id="75558-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75558-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="75558-105">Prerequisites</span></span>

<span data-ttu-id="75558-106">Innan du börjar måste du installera och konfigurera dokumentflödesagenten och sedan registrera nätverksskrivarna.</span><span class="sxs-lookup"><span data-stu-id="75558-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="75558-107">Mer information finns i [Installera dokumentflödesagenten för att aktivera nätverksutskrift](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="75558-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="75558-108">Göra skrivarmålet tillgängligt</span><span class="sxs-lookup"><span data-stu-id="75558-108">Make the Printer destination available</span></span>

<span data-ttu-id="75558-109">Om du vill göra **skrivarmålet** tillgängligt i den aktuella instansen av Microsoft Dynamics 365 Finance, gå till arbetsytan **Funktionshantering** och aktiverar följande funktioner i den här ordningen:</span><span class="sxs-lookup"><span data-stu-id="75558-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="75558-110">Konvertera utgående dokument för elektronisk rapportering från Microsoft Office-format till PDF.</span><span class="sxs-lookup"><span data-stu-id="75558-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="75558-111">Dokumentflödesagenten som mål för utgående dokument vid elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="75558-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="75558-112">[![Aktivera funktionen för ER-skrivarmål i funktionshantering](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="75558-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="75558-113">Tillämplighet</span><span class="sxs-lookup"><span data-stu-id="75558-113">Applicability</span></span>

<span data-ttu-id="75558-114">**Skrivarmålet** kan bara konfigureras för de fil komponenter som används för att generera utdata i antingen utskrivbara PDF-format (PDF-sammanslagning eller PDF-filformat) eller Microsoft Office Excel/Word-format (Excel-fil).</span><span class="sxs-lookup"><span data-stu-id="75558-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="75558-115">När utdata genereras i PDF-format skickas det till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="75558-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="75558-116">När utdata genereras i Microsoft Office-format konverteras det automatiskt till PDF-format och skickas sedan till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="75558-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="75558-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="75558-117">Limitations</span></span>

<span data-ttu-id="75558-118">**Skrivarmålet** implementeras endast för molndistributioner.</span><span class="sxs-lookup"><span data-stu-id="75558-118">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="75558-119">Använd skrivarmål</span><span class="sxs-lookup"><span data-stu-id="75558-119">Use the Printer destination</span></span>

1. <span data-ttu-id="75558-120">Ställ in alternativet **aktiverade** till **Ja** om du vill skicka ett genererat dokument till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="75558-120">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="75558-121">I fältet **Skrivarnamn** välj önskad nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="75558-121">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="75558-122">Ange alternativet **Spara i utskriftsarkivet?** till **Ja** att de genererade utdata ska sparas i utskriftsarkivet så att de blir tillgängliga för utskriften.</span><span class="sxs-lookup"><span data-stu-id="75558-122">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="75558-123">Om du vill komma åt arkiverade utdata senare **Organisationsadministration** \> **Förfrågningar och rapporter** \> **Rapportarkiv**.</span><span class="sxs-lookup"><span data-stu-id="75558-123">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="75558-124">[![Använd skrivarmål](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="75558-124">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="75558-125">Alternativet **konvertera till PDF** måste inte vara aktiverat när du konfigurerar **skrivarmålet**.</span><span class="sxs-lookup"><span data-stu-id="75558-125">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="75558-126">PDF-konverteringen för utskrift sker även om alternativet är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="75558-126">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="75558-127">För att använda en specifik [sidorientering](electronic-reporting-destinations.md#SelectPdfPageOrientation) när du skriver ut ett utgående dokument i Excel-format måste du aktivera alternativet **Konvertera till PDF**.</span><span class="sxs-lookup"><span data-stu-id="75558-127">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="75558-128">När du ställer in alternativet **Konvertera till PDF** till **Ja** blir fältet **Sidorientering** blir tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="75558-128">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="75558-129">Välj önskad **sidorientering** i fältet kan du välja sidorientering.</span><span class="sxs-lookup"><span data-stu-id="75558-129">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75558-130">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="75558-130">Additional resources</span></span>

- [<span data-ttu-id="75558-131">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="75558-131">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="75558-132">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="75558-132">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
