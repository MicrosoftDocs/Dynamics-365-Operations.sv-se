---
title: "Systemkrav för molndistributioner"
description: "Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och molndistributioner."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="9fa61-103">Systemkrav för molndistributioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9fa61-104">Det här ämnet innehåller en lista med systemkrav för den aktuella versionen av Microsoft Dynamics 365 for Finance and Operations, Enterprise edition för och molndistributioner.</span><span class="sxs-lookup"><span data-stu-id="9fa61-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="9fa61-105">Innan du installerar Finance and Operations, kontrollera vid behov om systemet du arbetar med uppfyller eller överskrider minimikraven för programvara, maskinvara och nätverk.</span><span class="sxs-lookup"><span data-stu-id="9fa61-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="9fa61-106">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-106">Supported web browsers</span></span>
<span data-ttu-id="9fa61-107">Webbprogrammet går att köra i följande webbläsare som körs på de angivna operativsystemen:</span><span class="sxs-lookup"><span data-stu-id="9fa61-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="9fa61-108">Microsoft Edge (den senaste tillgängliga versionen) på Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fa61-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="9fa61-109">Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7</span><span class="sxs-lookup"><span data-stu-id="9fa61-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="9fa61-110">Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 8, Windows 7 eller Google Nexus 10 surfplatta</span><span class="sxs-lookup"><span data-stu-id="9fa61-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="9fa61-111">Apple Safari (senaste tillgängliga versionen) på Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) eller 10.12 (Sierra), eller Apple iPad</span><span class="sxs-lookup"><span data-stu-id="9fa61-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="9fa61-112">Gå till programtillverkarens startsida för att hitta den senaste versionen för varje webbläsare.</span><span class="sxs-lookup"><span data-stu-id="9fa61-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="9fa61-113">Du måste installera en förhandsversion av ett Chrome-tillägg för att aktivera Uppgiftsinspelare för att ta skärmbilder och inkludera dem i genererade Microsoft Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="9fa61-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="9fa61-114">Arbetsflödesredigeraren startas som ett ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="9fa61-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="9fa61-115">Endast Microsoft Edge och Internet Explorer (på en version som stöds av Microsoft Windows) stöder ClickOnce-program.</span><span class="sxs-lookup"><span data-stu-id="9fa61-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="9fa61-116">Arbetsflödesredigeraren ClickOnce-programmet kräver 64-bitars kompatibelt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="9fa61-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="9fa61-117">Rapportdesignern för ekonomisk rapportering startar som ClickOnce-programmet.</span><span class="sxs-lookup"><span data-stu-id="9fa61-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="9fa61-118">Kräver 64-bitars kompatibelt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="9fa61-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="9fa61-119">Om du använder Chrome måste du installera tillägget ClickOnce för att hämta rapportdesignerklienten.</span><span class="sxs-lookup"><span data-stu-id="9fa61-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="9fa61-120">Om du använder Chrome med osynligt läge, se då till att tillägget ClickOnce har aktiverats för osynligt läge.</span><span class="sxs-lookup"><span data-stu-id="9fa61-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="9fa61-121">Om du vill förhandsgranska PDF-filer bör du använda moderna webbläsare såsom Microsoft Edge (senaste tillgängliga versionen) på Windows 10 eller Google Chrome (senaste tillgängliga versionen) på Windows 10, Windows 8.1, Windows 7, Windows 8 eller 10 Google Nexus Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="9fa61-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="9fa61-122">Webbläsare som stöds för molnbaserad kassa för butik</span><span class="sxs-lookup"><span data-stu-id="9fa61-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="9fa61-123">Molnbaserad kassa för butik går att köra i följande webbläsare som körs på de angivna operativsystemen:</span><span class="sxs-lookup"><span data-stu-id="9fa61-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="9fa61-124">Microsoft Edge (den senaste tillgängliga versionen) på Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fa61-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="9fa61-125">Internet Explorer 11 på Windows 10, Windows 8.1 eller Windows 7</span><span class="sxs-lookup"><span data-stu-id="9fa61-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="9fa61-126">Chrome (senaste tillgängliga versionen) i Windows 7, 8.1 för Windows eller Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fa61-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="9fa61-127">Nätverkskrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-127">Network requirements</span></span>
-   <span data-ttu-id="9fa61-128">Finance and Operations har utformats för nätverk med svarstid på 250-300 millisekunder eller mindre.</span><span class="sxs-lookup"><span data-stu-id="9fa61-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="9fa61-129">Denna tidsfördröjning är tidsfördröjning från en webbläsarklient till Microsoft Azure datacenter som är värd för Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9fa61-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="9fa61-130">Vi rekommenderar att du testar nätverksfördröjning vid <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="9fa61-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="9fa61-131">Bandbreddskrav för Finance and Operations är beroende av en viss situation.</span><span class="sxs-lookup"><span data-stu-id="9fa61-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="9fa61-132">Mest typiska scenarier kräver en bandbredd på mer än 50 kB per sekund (KBps).</span><span class="sxs-lookup"><span data-stu-id="9fa61-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="9fa61-133">Scenarier som har höga nyttolastkrav, till exempel scenarier som involverar arbetsytor eller omfattande anpassning, rekommenderas större bandbredd.</span><span class="sxs-lookup"><span data-stu-id="9fa61-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="9fa61-134">I allmänhet är Finance and Operations optimerad för Internet.</span><span class="sxs-lookup"><span data-stu-id="9fa61-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="9fa61-135">Antalet returresor från en webbläsarklient till Azure datacenter är mycket liten och hela nyttolasten komprimeras.</span><span class="sxs-lookup"><span data-stu-id="9fa61-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="9fa61-136">Beräkna inte bandbreddskrav från en klientplats genom att multiplicera antalet användare med den minsta bandbredd som krävs.</span><span class="sxs-lookup"><span data-stu-id="9fa61-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="9fa61-137">Det är mycket svårt att beräkna samtidiga användningen av en viss plats.</span><span class="sxs-lookup"><span data-stu-id="9fa61-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="9fa61-138">Kunder som är bekymrade över bandbreddskraven bör förhandsversion av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9fa61-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="9fa61-139">Krav på .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9fa61-139">.NET Framework requirements</span></span>
<span data-ttu-id="9fa61-140">Finance and Operations kräver Microsoft .NET Framework version 4.6.2 för alla enklicksprogram, t.ex. dokumentflödesagent.</span><span class="sxs-lookup"><span data-stu-id="9fa61-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="9fa61-141">Installationsinstruktioner finns i [installation av .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="9fa61-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="9fa61-142">Microsoft Office-program som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="9fa61-143">Följande Microsoft Office-program stöds i molnet och i lokala distributioner av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9fa61-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="9fa61-144">För att kunna köra Microsoft Excel och Word-tillägg måste du ha Microsoft Office 2016 för Windows eller Mac installerat.</span><span class="sxs-lookup"><span data-stu-id="9fa61-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="9fa61-145">Mer information om kraven på version finns i [felsökning av Office-integrering](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="9fa61-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="9fa61-146">Om du vill visa dokument som har genererats av Export till Excel eller Export till Word-funktioner måste Microsoft Office 2007 eller senare installeras.</span><span class="sxs-lookup"><span data-stu-id="9fa61-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="9fa61-147">Krav på Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="9fa61-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="9fa61-148">Om Modern Retail POS kommer att använda offline-databasen, måste datorn uppfylla alla systemkrav för Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9fa61-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="9fa61-149">En Modern Retail POS offlinedatabasen fungerar på Microsoft SQL Server 2012 med Service Pack 3 eller senare, Microsoft SQL Server 2014 med Service Pack 2 eller senare och Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9fa61-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="9fa61-150">Vi rekommenderar att du alltid använder den senaste versionen som finns och att du installerar de senaste uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="9fa61-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="9fa61-151">Operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-151">Supported operating systems</span></span>

-   <span data-ttu-id="9fa61-152">Retail Modern POS är ett 32-bitars program, men körs på både x86 och x64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="9fa61-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="9fa61-153">Retail Modern POS stöds bara på Windows 10 Pro, Enterprise och Enterprise Long Term Servicing Branch (LTSB).</span><span class="sxs-lookup"><span data-stu-id="9fa61-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="9fa61-154">Minsta systemkrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-154">Minimum system requirements</span></span>

-   <span data-ttu-id="9fa61-155">Den lägsta upplösningen som stöds är 1280 × 1024.</span><span class="sxs-lookup"><span data-stu-id="9fa61-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="9fa61-156">Den dator som Retail Modern POS körs på måste uppfylla följande villkor:</span><span class="sxs-lookup"><span data-stu-id="9fa61-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="9fa61-157">Den måste har minst en processor med dubbla kärnor som kör med minst 2 GHz (gigahertz).</span><span class="sxs-lookup"><span data-stu-id="9fa61-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="9fa61-158">Den måste ha minst 3 GB direktminne (RAM).</span><span class="sxs-lookup"><span data-stu-id="9fa61-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="9fa61-159">Den måste ha tillgång till Internet.</span><span class="sxs-lookup"><span data-stu-id="9fa61-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="9fa61-160">Krav på Retail hardware station</span><span class="sxs-lookup"><span data-stu-id="9fa61-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="9fa61-161">Operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-161">Supported operating systems</span></span>

-   <span data-ttu-id="9fa61-162">Retail hardware station är ett 32-bitars program, men körs på både x86 och x64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="9fa61-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="9fa61-163">Retail hardware station stöds i följande operativsystem:</span><span class="sxs-lookup"><span data-stu-id="9fa61-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="9fa61-164">Windows 7 Professional, Enterprise, och Ultimate-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="9fa61-165">Windows 7 stöds endast om Internet Explorer 11 har installerats manuellt i systemet.</span><span class="sxs-lookup"><span data-stu-id="9fa61-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="9fa61-166">Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded</span><span class="sxs-lookup"><span data-stu-id="9fa61-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="9fa61-167">Windows 10 Pro, Enterprise och Enterprise LTSB-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="9fa61-168">Minsta systemkrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-168">Minimum system requirements</span></span>

<span data-ttu-id="9fa61-169">Datorn måste uppfylla alla systemkrav för installation och användning av följande objekt:</span><span class="sxs-lookup"><span data-stu-id="9fa61-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="9fa61-170">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="9fa61-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="9fa61-171">Maskinvara från tredje part</span><span class="sxs-lookup"><span data-stu-id="9fa61-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="9fa61-172">Krav på Retail Store Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="9fa61-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="9fa61-173">Operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-173">Supported operating systems</span></span>

-   <span data-ttu-id="9fa61-174">Retail Store Scale Unit är ett 32-bitars program, men körs på både x86 och x64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="9fa61-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="9fa61-175">Retail Store Scale Unit stöds i följande operativsystem:</span><span class="sxs-lookup"><span data-stu-id="9fa61-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="9fa61-176">Windows 7 Professional, Enterprise, och Ultimate-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="9fa61-177">Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded</span><span class="sxs-lookup"><span data-stu-id="9fa61-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="9fa61-178">Windows 10 Pro, Enterprise och Enterprise LTSB-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="9fa61-179">Minsta systemkrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-179">Minimum system requirements</span></span>

-   <span data-ttu-id="9fa61-180">4 GB RAM</span><span class="sxs-lookup"><span data-stu-id="9fa61-180">4 GB of RAM</span></span>
-   <span data-ttu-id="9fa61-181">1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="9fa61-182">Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="9fa61-183">Rekommenderade systemkrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-183">Recommended system requirements</span></span>

-   <span data-ttu-id="9fa61-184">6 GB RAM</span><span class="sxs-lookup"><span data-stu-id="9fa61-184">6 GB of RAM</span></span>
-   <span data-ttu-id="9fa61-185">2,4 GHz i7 (eller motsvarande) högsta CPU-hastighet per kärna (fyra kärnor rekommenderas).</span><span class="sxs-lookup"><span data-stu-id="9fa61-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="9fa61-186">Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="9fa61-187">Kopplingskrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="9fa61-188">Operativsystem som stöds</span><span class="sxs-lookup"><span data-stu-id="9fa61-188">Supported operating systems</span></span>

-   <span data-ttu-id="9fa61-189">Koppling för Microsoft Dynamics AX har två separata installationsprogram Async Server Connector service och Real-time service för Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="9fa61-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="9fa61-190">Båda komponenterna 32-bitars program, men körs på både x86 och x64-arkitektur.</span><span class="sxs-lookup"><span data-stu-id="9fa61-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="9fa61-191">Båda komponenterna kan användas på följande operativsystem:</span><span class="sxs-lookup"><span data-stu-id="9fa61-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="9fa61-192">Windows 7 Professional, Enterprise, och Ultimate-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="9fa61-193">Windows 8.1 uppdatering 1 Professional, Enterprise och Embedded</span><span class="sxs-lookup"><span data-stu-id="9fa61-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="9fa61-194">Windows 10 Pro, Enterprise och Enterprise LTSB-versioner</span><span class="sxs-lookup"><span data-stu-id="9fa61-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="9fa61-195">Microsoft Windows Server 2012 R2 och Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9fa61-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="9fa61-196">Minsta systemkrav</span><span class="sxs-lookup"><span data-stu-id="9fa61-196">Minimum system requirements</span></span>
-   <span data-ttu-id="9fa61-197">2 GB RAM (4 GB RAM-minne rekommenderas.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="9fa61-198">1,6 GHz högsta CPU-hastighet per kärna (två kärnor är minimum.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="9fa61-199">Minst 10 GB ledigt utrymme (kanaldatabasen kan kräva stora mängder diskutrymme.)</span><span class="sxs-lookup"><span data-stu-id="9fa61-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="9fa61-200">Krav för utveckling av lokala virtuella maskiner</span><span class="sxs-lookup"><span data-stu-id="9fa61-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="9fa61-201">Information om kraven för utveckling av enskilda virtuella datorerna (VMs) finns i [VM körs lokalt](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="9fa61-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="9fa61-202">Se även</span><span class="sxs-lookup"><span data-stu-id="9fa61-202">See also</span></span>

[<span data-ttu-id="9fa61-203">Hämta en utvärderingskopia av Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="9fa61-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

