---
title: Systemkrav och uppdateringspolicy för Talent
description: Det här avsnittet beskrivs kraven för Dynamics 365 for Talent. Det beskriver även uppdateringspolicyn.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
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
ms.openlocfilehash: 2389f00b22ec3b5284eeffb2c015533b7a3d13e0
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "856311"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="d62f7-104">Systemkrav och uppdateringspolicy för Talent</span><span class="sxs-lookup"><span data-stu-id="d62f7-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d62f7-105">Det här avsnittet beskrivs kraven för Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="d62f7-105">This topic lists requirements for Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="d62f7-106">Det beskriver även uppdateringspolicyn.</span><span class="sxs-lookup"><span data-stu-id="d62f7-106">The update policy is outlined, as well.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="d62f7-107">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="d62f7-107">Supported web browsers</span></span>

<span data-ttu-id="d62f7-108">Webbprogrammet Microsoft Dynamics 365 for Talent går att köra i följande webbläsare som körs på de angivna operativsystemen:</span><span class="sxs-lookup"><span data-stu-id="d62f7-108">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="d62f7-109">Microsoft Edge (den senaste tillgängliga versionen) på Windows 10</span><span class="sxs-lookup"><span data-stu-id="d62f7-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="d62f7-110">Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7</span><span class="sxs-lookup"><span data-stu-id="d62f7-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="d62f7-111">Google Chrome (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="d62f7-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="d62f7-112">Apple Safari (den senaste tillgängliga versionen)</span><span class="sxs-lookup"><span data-stu-id="d62f7-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="d62f7-113">Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare.</span><span class="sxs-lookup"><span data-stu-id="d62f7-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="d62f7-114">Om du vill hämta bilder som har skapats från uppgiftsregistrering och inkludera dem i Microsoft Word-dokument måste du ha installerat ett Chrome-tillägg.</span><span class="sxs-lookup"><span data-stu-id="d62f7-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="d62f7-115">Arbetsflödesredigeraren startas som ett ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="d62f7-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="d62f7-116">Endast Microsoft Edgeoch Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="d62f7-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="d62f7-117">Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="d62f7-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="d62f7-118">Om du vill förhandsgranska PDF-filer, bör du använda moderna webbläsare som t.ex. Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="d62f7-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="d62f7-119">Nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="d62f7-119">Network requirements</span></span>
> * <span data-ttu-id="d62f7-120">Dynamics 365 for Talent har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre.</span><span class="sxs-lookup"><span data-stu-id="d62f7-120">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="d62f7-121">Denna svarstid är svarstiden från en webbläsarklient till Microsoft Azure datacenter som är värd för Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="d62f7-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="d62f7-122">Vi rekommenderar att du testar nätverksfördröjning vid [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span><span class="sxs-lookup"><span data-stu-id="d62f7-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="d62f7-123">Bandbreddskrav för Dynamics 365 for Talent beror på ditt scenario.</span><span class="sxs-lookup"><span data-stu-id="d62f7-123">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="d62f7-124">Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).</span><span class="sxs-lookup"><span data-stu-id="d62f7-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="d62f7-125">Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs.</span><span class="sxs-lookup"><span data-stu-id="d62f7-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="d62f7-126">Det är mycket svårt att beräkna samtidiga användningen av en viss plats.</span><span class="sxs-lookup"><span data-stu-id="d62f7-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="d62f7-127">Använd en testversion av Dynamics 365 for Talent för kunder som är bekymrade över bandbreddskraven.</span><span class="sxs-lookup"><span data-stu-id="d62f7-127">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="d62f7-128">Microsoft Office-program som stöds</span><span class="sxs-lookup"><span data-stu-id="d62f7-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="d62f7-129">För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat.</span><span class="sxs-lookup"><span data-stu-id="d62f7-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="d62f7-130">För mer information om versionskrav läs [felsökning av Office-integrering](../dev-itpro/office-integration/office-integration-troubleshooting.md "felsökning av Office-integrering+").</span><span class="sxs-lookup"><span data-stu-id="d62f7-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="d62f7-131">Om du vill visa dokument som har skapats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.</span><span class="sxs-lookup"><span data-stu-id="d62f7-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="update-policy"></a><span data-ttu-id="d62f7-132">Uppdatera policy</span><span class="sxs-lookup"><span data-stu-id="d62f7-132">Update policy</span></span>

<span data-ttu-id="d62f7-133">Microsoft Dynamics 365 for Talent hanteras som ett molnbaserad erbjudande.</span><span class="sxs-lookup"><span data-stu-id="d62f7-133">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="d62f7-134">Uppdateringar för Dynamics 365 for Talent är kontinuerlig och tillämpas automatiskt av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d62f7-134">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="d62f7-135">Uppdateringar släpps regelbundet, uppdateringar sker för alla nätverk.</span><span class="sxs-lookup"><span data-stu-id="d62f7-135">Updates are released on a regular cadence, updates will be made to all environments.</span></span>  <span data-ttu-id="d62f7-136">Dynamics 365 for Talent stöds enligt [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), som ger konsekventa och förutsägbara riktlinjer för tillgängligheten av produktsupport.</span><span class="sxs-lookup"><span data-stu-id="d62f7-136">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
