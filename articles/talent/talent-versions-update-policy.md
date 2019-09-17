---
title: Systemkrav och uppdateringspolicy för Talent
description: Det här avsnittet beskrivs kraven för Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6c881bf25e7145228ccf7ef73a7ef3637c115a49
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741785"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="419ba-104">Systemkrav och uppdateringspolicy för Talent</span><span class="sxs-lookup"><span data-stu-id="419ba-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="419ba-105">I det här avsnittet beskrivs kraven för Microsoft Dynamics 365 for Talent, inklusive Attract, Onboard och Core HR.</span><span class="sxs-lookup"><span data-stu-id="419ba-105">This topic describes requirements for Microsoft Dynamics 365 for Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="419ba-106">Det visar också de länder och regioner där Talent finns tillgänglig, plus information om språk och lokalisering av Talent data.</span><span class="sxs-lookup"><span data-stu-id="419ba-106">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="419ba-107">Dessutom ger det här här avsnittet uppdateringsprincipen för Talent.</span><span class="sxs-lookup"><span data-stu-id="419ba-107">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="419ba-108">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="419ba-108">Supported web browsers</span></span>

<span data-ttu-id="419ba-109">Webbprogrammet Microsoft Dynamics 365 for Talent går att köra i följande webbläsare som körs på de angivna operativsystemen:</span><span class="sxs-lookup"><span data-stu-id="419ba-109">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="419ba-110">Microsoft Edge (den senaste tillgängliga versionen) på Windows 10</span><span class="sxs-lookup"><span data-stu-id="419ba-110">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="419ba-111">Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7</span><span class="sxs-lookup"><span data-stu-id="419ba-111">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="419ba-112">Google Chrome (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="419ba-112">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="419ba-113">Apple Safari (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="419ba-113">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="419ba-114">Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare.</span><span class="sxs-lookup"><span data-stu-id="419ba-114">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="419ba-115">Om du vill hämta bilder som har skapats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg.</span><span class="sxs-lookup"><span data-stu-id="419ba-115">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="419ba-116">Arbetsflödesredigeraren startas som ett ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="419ba-116">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="419ba-117">Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="419ba-117">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="419ba-118">Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="419ba-118">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="419ba-119">Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="419ba-119">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="419ba-120">Nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="419ba-120">Network requirements</span></span>
> * <span data-ttu-id="419ba-121">Dynamics 365 for Talent har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre.</span><span class="sxs-lookup"><span data-stu-id="419ba-121">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="419ba-122">Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="419ba-122">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="419ba-123">Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span><span class="sxs-lookup"><span data-stu-id="419ba-123">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="419ba-124">Bandbreddskrav för Dynamics 365 for Talent beror på ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="419ba-124">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="419ba-125">Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).</span><span class="sxs-lookup"><span data-stu-id="419ba-125">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="419ba-126">Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs.</span><span class="sxs-lookup"><span data-stu-id="419ba-126">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="419ba-127">Det är mycket svårt att beräkna samtidiga användningen av en viss plats.</span><span class="sxs-lookup"><span data-stu-id="419ba-127">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="419ba-128">Använd en testversion av Dynamics 365 for Talent för kunder som är bekymrade över bandbreddskraven.</span><span class="sxs-lookup"><span data-stu-id="419ba-128">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="419ba-129">Microsoft Office-program som stöds</span><span class="sxs-lookup"><span data-stu-id="419ba-129">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="419ba-130">För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat.</span><span class="sxs-lookup"><span data-stu-id="419ba-130">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="419ba-131">För mer information om versionskrav läs [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "felsökning av Office-integrering+").</span><span class="sxs-lookup"><span data-stu-id="419ba-131">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="419ba-132">Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.</span><span class="sxs-lookup"><span data-stu-id="419ba-132">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="419ba-133">Lokal tillgänglighet, språk och lokalisering</span><span class="sxs-lookup"><span data-stu-id="419ba-133">Regional availability, languages, and localization</span></span>

<span data-ttu-id="419ba-134">Du kan hämta en PDF-fil för de länder, regioner och språk som Talent stöder med [internationell tillgänglighet på Microsoft Dynamics 365.](https://docs.microsoft.com/dynamics365/get-started/availability)</span><span class="sxs-lookup"><span data-stu-id="419ba-134">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="419ba-135">När användargränssnittet har lokaliserats till andra språk lagras alla användardata på det språk som det har angetts i.</span><span class="sxs-lookup"><span data-stu-id="419ba-135">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="419ba-136">Du kan skapa e-postmeddelanden och mallar på andra språk, men data som t.ex. schemaläggningsinformation är bara tillgänglig på engelska för närvarande.</span><span class="sxs-lookup"><span data-stu-id="419ba-136">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="419ba-137">Om du är en utvecklare som vill skapa lands- eller regionsspecifika anpassningar eller skapa en lösning för ett land eller en region som inte stöds av Microsoft, se [globaliseringsfunktionen.](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)</span><span class="sxs-lookup"><span data-stu-id="419ba-137">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

## <a name="update-policy"></a><span data-ttu-id="419ba-138">Uppdatera policy</span><span class="sxs-lookup"><span data-stu-id="419ba-138">Update policy</span></span>

<span data-ttu-id="419ba-139">Microsoft Dynamics 365 for Talent hanteras som ett molnbaserad erbjudande.</span><span class="sxs-lookup"><span data-stu-id="419ba-139">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="419ba-140">Uppdateringar för Dynamics 365 for Talent är kontinuerlig och tillämpas automatiskt av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="419ba-140">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="419ba-141">Uppdateringar släpps regelbundet, uppdateringar sker för alla nätverk.</span><span class="sxs-lookup"><span data-stu-id="419ba-141">Updates are released on a regular cadence and will be made to all environments.</span></span> <span data-ttu-id="419ba-142">Dynamics 365 for Talent stöds enligt [Microsoft Support Lifecycle policy](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av produktsupport.</span><span class="sxs-lookup"><span data-stu-id="419ba-142">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
