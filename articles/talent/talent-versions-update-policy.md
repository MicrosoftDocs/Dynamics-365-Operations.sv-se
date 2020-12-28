---
title: Talent systemkrav
description: Det här avsnittet beskrivs kraven för Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
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
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462574"
---
# <a name="talent-system-requirements"></a><span data-ttu-id="fdf4d-103">Talent systemkrav</span><span class="sxs-lookup"><span data-stu-id="fdf4d-103">Talent system requirements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fdf4d-104">I det här avsnittet beskrivs kraven för Microsoft Dynamics 365 Talent, inklusive Attract och Onboard.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-104">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract and Onboard.</span></span> <span data-ttu-id="fdf4d-105">Det visar också de länder och regioner där Talent finns tillgänglig, plus information om språk och lokalisering av Talent data.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-105">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="fdf4d-106">Dessutom ger det här här avsnittet uppdateringsprincipen för Talent.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-106">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="fdf4d-107">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="fdf4d-107">Supported web browsers</span></span>

<span data-ttu-id="fdf4d-108">Microsoft Dynamics 365 Talent går att köra i följande webbläsare som körs på de angivna operativsystemen:</span><span class="sxs-lookup"><span data-stu-id="fdf4d-108">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="fdf4d-109">Microsoft Edge (den senaste tillgängliga versionen) på Windows 10</span><span class="sxs-lookup"><span data-stu-id="fdf4d-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="fdf4d-110">Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7</span><span class="sxs-lookup"><span data-stu-id="fdf4d-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="fdf4d-111">Google Chrome (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="fdf4d-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="fdf4d-112">Apple Safari (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="fdf4d-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="fdf4d-113">Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="fdf4d-114">Om du vill hämta bilder som har skapats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="fdf4d-115">Arbetsflödesredigeraren startas som ett ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="fdf4d-116">Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="fdf4d-117">Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="fdf4d-118">Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="fdf4d-119">Nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="fdf4d-119">Network requirements</span></span>
> * <span data-ttu-id="fdf4d-120">Dynamics 365 Talent har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-120">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="fdf4d-121">Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Talent.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="fdf4d-122">Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure fördröjningstest").</span><span class="sxs-lookup"><span data-stu-id="fdf4d-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="fdf4d-123">Bandbreddskrav för Talent beror på ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-123">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="fdf4d-124">Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).</span><span class="sxs-lookup"><span data-stu-id="fdf4d-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="fdf4d-125">Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="fdf4d-126">Det är mycket svårt att beräkna samtidiga användningen av en viss plats.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="fdf4d-127">Använd en testversion av Talent för kunder som är bekymrade över bandbreddskraven.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-127">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="fdf4d-128">Microsoft Office-program som stöds</span><span class="sxs-lookup"><span data-stu-id="fdf4d-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="fdf4d-129">För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="fdf4d-130">Mer information om kraven på version finns i [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "Felsöka Office-integrering").</span><span class="sxs-lookup"><span data-stu-id="fdf4d-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="fdf4d-131">Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="fdf4d-132">Lokal tillgänglighet, språk och lokalisering</span><span class="sxs-lookup"><span data-stu-id="fdf4d-132">Regional availability, languages, and localization</span></span>

<span data-ttu-id="fdf4d-133">Du kan hämta en PDF-fil för de länder, regioner och språk som Talent stöder med [internationell tillgänglighet på Microsoft Dynamics 365.](https://docs.microsoft.com/dynamics365/get-started/availability)</span><span class="sxs-lookup"><span data-stu-id="fdf4d-133">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="fdf4d-134">När användargränssnittet har lokaliserats till andra språk lagras alla användardata på det språk som det har angetts i.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-134">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="fdf4d-135">Du kan skapa e-postmeddelanden och mallar på andra språk, men data som t.ex. schemaläggningsinformation är bara tillgänglig på engelska för närvarande.</span><span class="sxs-lookup"><span data-stu-id="fdf4d-135">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="fdf4d-136">Om du är en utvecklare som vill skapa lands- eller regionsspecifika anpassningar eller skapa en lösning för ett land eller en region som inte stöds av Microsoft, se [globaliseringsfunktionen.](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region)</span><span class="sxs-lookup"><span data-stu-id="fdf4d-136">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

