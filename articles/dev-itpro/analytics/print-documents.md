---
title: Dokumentutskrift
description: "Du kan skriva ut dokument i Microsoft Dynamics 365 for Finance and Operations genom att använda en lokal skrivare eller en nätverksansluten enhet. Den här artikeln innehåller en översikt över hur dokument skrivs ut."
author: TJVass
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: IT Pro, Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 4fd20022ff91fedb6d0323e82fbe3c1acae38e48
ms.contentlocale: sv-se
ms.lasthandoff: 08/13/2018

---

# <a name="document-printing"></a><span data-ttu-id="b790b-104">Dokumentutskrift</span><span class="sxs-lookup"><span data-stu-id="b790b-104">Document printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b790b-105">Du kan skriva ut dokument i Microsoft Dynamics 365 for Finance and Operations genom att använda en lokal skrivare eller en nätverksansluten enhet.</span><span class="sxs-lookup"><span data-stu-id="b790b-105">In Microsoft Dynamics 365 for Finance and Operations, you can print documents by using either a local printer or a network-connected device.</span></span> <span data-ttu-id="b790b-106">Den här artikeln innehåller en översikt över hur dokument skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="b790b-106">This article provides an overview of how documents are printed.</span></span>

## <a name="printing-overview"></a><span data-ttu-id="b790b-107">Översikt över utskrift</span><span class="sxs-lookup"><span data-stu-id="b790b-107">Printing overview</span></span>

<span data-ttu-id="b790b-108">Microsoft Dynamics 365 for Finance and Operations tillhandahåller integrerade tjänster och klientprogram som gör det enklare att skapa, lagra och distribuera dokument som stöder affärsaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="b790b-108">Microsoft Dynamics 365 for Finance and Operations provides integrated services and client applications that make it easy to generate, store, and distribute documents that support business activity.</span></span> <span data-ttu-id="b790b-109">Du kan skriva ut dokument i Finance and Operations genom att använda en lokal skrivare eller en nätverksansluten enhet.</span><span class="sxs-lookup"><span data-stu-id="b790b-109">In Finance and Operations, you can print documents by using either a local printer or a network-connected device.</span></span> <span data-ttu-id="b790b-110">Dessutom kan du exportera Finance and Operations- sidor och -rapporter direkt från klienten, som PDF-filer eller Microsoft Office-dokument.</span><span class="sxs-lookup"><span data-stu-id="b790b-110">In addition, you can export Finance and Operations pages and reports directly from the client, as PDF files or Microsoft Office documents.</span></span> <span data-ttu-id="b790b-111">Slutligen gör den distribuerade arbetsbelastningen att du kan skriva ut affärsdokument direkt från en mobil enhet med hjälp av nätverksresurser.</span><span class="sxs-lookup"><span data-stu-id="b790b-111">Finally, the distributed workload lets you print business documents directly from a mobile device by using network resources.</span></span> <span data-ttu-id="b790b-112">Även om utskriftsbehov varierar måste alla branscher vanligtvis skapa papperskopior av affärsdokument med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b790b-112">Although printing requirements might vary, all industries typically must create hard copies of business documents by using Finance and Operations.</span></span> <span data-ttu-id="b790b-113">Skriva ut dokument på nätverksenheter från värdprogram ger en unik uppsättning utmaningar.</span><span class="sxs-lookup"><span data-stu-id="b790b-113">Printing documents on network devices from hosted applications presents a unique set of challenges.</span></span> <span data-ttu-id="b790b-114">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="b790b-114">Here are some examples:</span></span>

- <span data-ttu-id="b790b-115">Skrivardrivrutiner kanske inte kan användas på användarens enhet.</span><span class="sxs-lookup"><span data-stu-id="b790b-115">Print drivers might not be available on the user's device.</span></span>
- <span data-ttu-id="b790b-116">Användarens enhet kanske inte är ansluten till företagets nätverk.</span><span class="sxs-lookup"><span data-stu-id="b790b-116">The user's device might not be connected to the corporate network.</span></span>

<span data-ttu-id="b790b-117">Genom att använda en särskild värd och följa några enkla steg kan systemadministratörer konfigurera distributioner så att användarna kan skriva ut direkt från företagsprogram på nätverksenheter.</span><span class="sxs-lookup"><span data-stu-id="b790b-117">By using a dedicated host and following a few easy steps, system administrators can configure deployments so that users can print directly from business applications on network devices.</span></span>

### <a name="printing-scenarios-in-finance-and-operations-applications"></a><span data-ttu-id="b790b-118">Utskriftsscenarier i Finance and Operations-program</span><span class="sxs-lookup"><span data-stu-id="b790b-118">Printing scenarios in Finance and Operations applications</span></span>

<span data-ttu-id="b790b-119">I följande tabell beskrivs de tre primära utskriftscenarierna i Finance and Operations-programmen.</span><span class="sxs-lookup"><span data-stu-id="b790b-119">The following table describes the three primary printing scenarios in Finance and Operations applications.</span></span>

| <span data-ttu-id="b790b-120">Scenario</span><span class="sxs-lookup"><span data-stu-id="b790b-120">Scenario</span></span>                        | <span data-ttu-id="b790b-121">Mål</span><span class="sxs-lookup"><span data-stu-id="b790b-121">Goal</span></span>                                                      | <span data-ttu-id="b790b-122">Lösning</span><span class="sxs-lookup"><span data-stu-id="b790b-122">Solution</span></span> |
|---------------------------------|-----------------------------------------------------------|----------|
| <span data-ttu-id="b790b-123">1. Skriva ut vad du ser</span><span class="sxs-lookup"><span data-stu-id="b790b-123">1. Printing what you see</span></span>        | <span data-ttu-id="b790b-124">Skriv ut vad som visas i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b790b-124">Print what is currently shown in the browser.</span></span>             | <span data-ttu-id="b790b-125">En ”utskriftsvänlig” version av webbsidan skapas för webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b790b-125">A "print-friendly" version of the webpage is generated for the browser.</span></span> |
| <span data-ttu-id="b790b-126">2. Interaktiv utskrift</span><span class="sxs-lookup"><span data-stu-id="b790b-126">2. Interactive printing</span></span>         | <span data-ttu-id="b790b-127">Skriva ut ett precisionsdokument på en lokalt ansluten enhet.</span><span class="sxs-lookup"><span data-stu-id="b790b-127">Print a precision document on a locally connected device.</span></span> | <span data-ttu-id="b790b-128">Du kan exportera en PDF-version av rapporten och överföra den till webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b790b-128">You can export a PDF version of the report and download it to the browser.</span></span> |
| <span data-ttu-id="b790b-129">3. Utskrift på en nätverksenhet</span><span class="sxs-lookup"><span data-stu-id="b790b-129">3. Printing on a network device</span></span> | <span data-ttu-id="b790b-130">Skicka ett precisionsdokument till en skrivare i domänen.</span><span class="sxs-lookup"><span data-stu-id="b790b-130">Send a precision document to a domain printer device.</span></span>     | <span data-ttu-id="b790b-131">Ett precisionsdokument skickas till ett klientprogram som körs på en server som har en värd i kundens domän.</span><span class="sxs-lookup"><span data-stu-id="b790b-131">A precision document is sent to a client application that runs on a server that is hosted in the customer's domain.</span></span> |

<span data-ttu-id="b790b-132">Eftersom lösningen varierar beroende på scenariet, innehåller Finance and Operations-program inbyggda tjänster och verktygsuppsättningar som hjälper användarna att uppnå sina mål:</span><span class="sxs-lookup"><span data-stu-id="b790b-132">Because the solution varies, depending on the scenario, Finance and Operations applications provide built-in services and tooling to help users accomplish their goals:</span></span>

- <span data-ttu-id="b790b-133">**Scenario 1** stöds av webbläsarens återgivning av HTML5-klienten.</span><span class="sxs-lookup"><span data-stu-id="b790b-133">**Scenario 1** is supported by the browser's rendering of the HTML5 client.</span></span>
- <span data-ttu-id="b790b-134">**Scenario 2** använder klientprogram och Microsoft Office 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="b790b-134">**Scenario 2** uses client applications and Microsoft Office 365 services.</span></span>
- <span data-ttu-id="b790b-135">**Scenario 3** kräver stöd från klientprogram och från tjänster som finns i Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b790b-135">**Scenario 3** requires support from client applications and from services that are hosted in Microsoft Azure.</span></span>

<span data-ttu-id="b790b-136">Förutom den plattform som distribueras på Azure-abonnemanget ger Finance and Operations-.program kunderna en integrerad, första part Azure-program som kan användas för att enkelt använda domänhanterade enheter för att skriva ut dokument.</span><span class="sxs-lookup"><span data-stu-id="b790b-136">In addition to the platform that is deployed to the Azure subscription, Finance and Operations applications provide customers with an integrated, first-party Azure application that helps them more easily use domain-hosted devices to print documents.</span></span>

## <a name="service-overview"></a><span data-ttu-id="b790b-137">Översikt över tjänsten</span><span class="sxs-lookup"><span data-stu-id="b790b-137">Service overview</span></span>
<span data-ttu-id="b790b-138">När dokument som har skapats av värdprogram som väntar på att skrivas ut på en nätverksansluten enhet, förvaras de i Azure blobblagring.</span><span class="sxs-lookup"><span data-stu-id="b790b-138">While documents that are produced by the hosted applications are waiting to be printed on a network-connected device, they are stored in Azure blob storage.</span></span> <span data-ttu-id="b790b-139">[Dokumentflödesagenten](install-document-routing-agent.md) använder Azure-autentisering för att upprätta en säker kanal till Azure-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b790b-139">The [Document Routing Agent](install-document-routing-agent.md) uses Azure authentication to establish a secure channel to the Azure services.</span></span>

<span data-ttu-id="b790b-140">**Körningssekvens**</span><span class="sxs-lookup"><span data-stu-id="b790b-140">**Execution sequence**</span></span>

1. <span data-ttu-id="b790b-141">Rapporten skapas av Microsoft SQL Server Reporting Services (SSRS) och lagras i Azure blobblagring.</span><span class="sxs-lookup"><span data-stu-id="b790b-141">The report is generated by Microsoft SQL Server Reporting Services (SSRS) and stored in Azure blob storage.</span></span> <span data-ttu-id="b790b-142">Kopplade skrivarinställningar sparas tillsammans med dokumentet.</span><span class="sxs-lookup"><span data-stu-id="b790b-142">Attached printer settings are stored together with the document.</span></span>
2. <span data-ttu-id="b790b-143">Dokumentflödesagenten frågar Azure Service Bus-kön efter aktiva jobb.</span><span class="sxs-lookup"><span data-stu-id="b790b-143">The Document Routing Agent queries the Azure Service Bus queue for active jobs.</span></span>
3. <span data-ttu-id="b790b-144">Dokumentet hämtas av dokumentflödesagenten och överförs till nätverksskrivaren.</span><span class="sxs-lookup"><span data-stu-id="b790b-144">The document is downloaded by the Document Routing Agent and spooled to the network printer.</span></span>

<span data-ttu-id="b790b-145">Den klientbaserade lösningen låter kunder hantera omfattningen av deras skrivarbehov.</span><span class="sxs-lookup"><span data-stu-id="b790b-145">The client-based solution lets customers manage the scale of their printing needs.</span></span> <span data-ttu-id="b790b-146">Kunder som har aktiverat utskrifter av stora volymer kan installera många dokumentflödesagenter för att öka antalet samtidiga utskriftsoperationer.</span><span class="sxs-lookup"><span data-stu-id="b790b-146">Customers who have heavy-volume printing workloads can install many Document Routing Agents to increase the number of concurrent printing operations.</span></span> <span data-ttu-id="b790b-147">Alternativt kräver vissa kunder mycket få dokumentflödesagenter för att hantera deras förväntade utskriftsbehov.</span><span class="sxs-lookup"><span data-stu-id="b790b-147">Alternatively, some customers require very few installations of the Document Routing Agent to handle their anticipated printing needs.</span></span>

### <a name="service-components-for-network-printing"></a><span data-ttu-id="b790b-148">Tjänstkomponenter för nätverksutskrift</span><span class="sxs-lookup"><span data-stu-id="b790b-148">Service components for network printing</span></span>

<span data-ttu-id="b790b-149">Diagrammet nedan visar de grundläggande komponenterna som hjälper till att stödja nätverksutskriftoperationer.</span><span class="sxs-lookup"><span data-stu-id="b790b-149">The following diagram shows the basic components that help support network printing operations.</span></span>

<span data-ttu-id="b790b-150">[![tjänstkomponenter för nätverksutskrift\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)</span><span class="sxs-lookup"><span data-stu-id="b790b-150">[![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)</span></span>

<span data-ttu-id="b790b-151">Observera att en skrivare kan registreras med flera dokumentflödesagenter.</span><span class="sxs-lookup"><span data-stu-id="b790b-151">Note that a single printer can be registered with multiple Document Routing Agents.</span></span> <span data-ttu-id="b790b-152">För att lösa skrivarens egenskaper använder värdtjänsten nätverkssökvägen som unikt identifierar alla nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="b790b-152">To resolve the printer preferences, the hosted service uses the network path that uniquely identifies every network printer.</span></span> <span data-ttu-id="b790b-153">Därför visas den som ett alternativ i listan över skrivare som är tillgänglig i Finance and Operations-program även om en skrivare är registrerad med flera klienter.</span><span class="sxs-lookup"><span data-stu-id="b790b-153">As a result, even when a printer is registered by multiple clients, it appears as a single selection in the list of printers available in Finance and Operations applications.</span></span>

