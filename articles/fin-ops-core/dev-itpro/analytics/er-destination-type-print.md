---
title: ER-målstyp för skrivare
description: Det här ämnet förklarar hur du konfigurerar en skrivardestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument i antingen PDF eller Microsoft Office-format (Excel\Word).
author: NickSelin
manager: AnnBe
ms.date: 01/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58e067baa130458e3a8e788d978604f208140a03
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020007"
---
# <a name="PrinterDestinationType"></a><span data-ttu-id="e34ee-103">Utskriftsmål</span><span class="sxs-lookup"><span data-stu-id="e34ee-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e34ee-104">Du kan skicka ett genererat dokument direkt till en nätverksskrivare för direkt utskrift.</span><span class="sxs-lookup"><span data-stu-id="e34ee-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e34ee-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e34ee-105">Prerequisites</span></span>

<span data-ttu-id="e34ee-106">Innan du börjar måste du installera och konfigurera dokumentflödesagenten och sedan registrera nätverksskrivarna.</span><span class="sxs-lookup"><span data-stu-id="e34ee-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="e34ee-107">Mer information finns i [Installera dokumentflödesagenten för att aktivera nätverksutskrift](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span><span class="sxs-lookup"><span data-stu-id="e34ee-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="e34ee-108">Göra skrivarmålet tillgängligt</span><span class="sxs-lookup"><span data-stu-id="e34ee-108">Make the Printer destination available</span></span>

<span data-ttu-id="e34ee-109">Om du vill göra **skrivarmålet** tillgängligt i den aktuella instansen av Microsoft Dynamics 365 Finance, gå till arbetsytan **Funktionshantering** och aktiverar följande funktioner i den här ordningen:</span><span class="sxs-lookup"><span data-stu-id="e34ee-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="e34ee-110">Konvertera utgående dokument för elektronisk rapportering från Microsoft Office-format till PDF.</span><span class="sxs-lookup"><span data-stu-id="e34ee-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="e34ee-111">Dokumentflödesagenten som mål för utgående dokument vid elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="e34ee-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="e34ee-112">[![Aktivera funktionen för ER-skrivarmål i funktionshantering](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="e34ee-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="e34ee-113">Tillämplighet</span><span class="sxs-lookup"><span data-stu-id="e34ee-113">Applicability</span></span>

<span data-ttu-id="e34ee-114">**Skrivarmålet** kan bara konfigureras för de fil komponenter som används för att generera utdata i antingen utskrivbara PDF-format (PDF-sammanslagning eller PDF-filformat) eller Microsoft Office Excel/Word-format (Excel-fil).</span><span class="sxs-lookup"><span data-stu-id="e34ee-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="e34ee-115">När utdata genereras i PDF-format skickas det till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="e34ee-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="e34ee-116">När utdata genereras i Microsoft Office-format konverteras det automatiskt till PDF-format och skickas sedan till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="e34ee-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="e34ee-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="e34ee-117">Limitations</span></span>

<span data-ttu-id="e34ee-118">Den här funktionen är en förhandsgranskningsfunktion och används för användningsvillkoren som [Extra användningsvillkor för Microsoft Dynamics 365 förhandsgranskningar](https://go.microsoft.com/fwlink/?linkid=2105274).</span><span class="sxs-lookup"><span data-stu-id="e34ee-118">This feature is a preview feature and is subject to the terms of use that are described in [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://go.microsoft.com/fwlink/?linkid=2105274).</span></span>

<span data-ttu-id="e34ee-119">**Skrivarmålet** implementeras endast för molndistributioner.</span><span class="sxs-lookup"><span data-stu-id="e34ee-119">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="e34ee-120">Använd skrivarmål</span><span class="sxs-lookup"><span data-stu-id="e34ee-120">Use the Printer destination</span></span>

1. <span data-ttu-id="e34ee-121">Ställ in alternativet **aktiverade** till **Ja** om du vill skicka ett genererat dokument till en skrivare.</span><span class="sxs-lookup"><span data-stu-id="e34ee-121">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="e34ee-122">I fältet **Skrivarnamn** välj önskad nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="e34ee-122">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="e34ee-123">Ange alternativet **Spara i utskriftsarkivet?** till **Ja** att de genererade utdata ska sparas i utskriftsarkivet så att de blir tillgängliga för utskriften.</span><span class="sxs-lookup"><span data-stu-id="e34ee-123">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="e34ee-124">Om du vill komma åt arkiverade utdata senare **Organisationsadministration** \> **Förfrågningar och rapporter** \> **Rapportarkiv**.</span><span class="sxs-lookup"><span data-stu-id="e34ee-124">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="e34ee-125">[![Använd skrivarmål](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="e34ee-125">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e34ee-126">Alternativet **konvertera till PDF** måste inte vara aktiverat när du konfigurerar **skrivarmålet**.</span><span class="sxs-lookup"><span data-stu-id="e34ee-126">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="e34ee-127">PDF-konverteringen för utskrift sker även om alternativet är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="e34ee-127">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e34ee-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e34ee-128">Additional resources</span></span>

- [<span data-ttu-id="e34ee-129">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="e34ee-129">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="e34ee-130">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="e34ee-130">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
