---
title: Administreringskomponenter för tillägget Elektronisk fakturering
description: Detta ämne innehåller information om de komponenter som är relaterade till administrationen av tillägget Elektronisk fakturering.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104440"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="51e08-103">Administreringskomponenter för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="51e08-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="51e08-104">Detta ämne innehåller information om de komponenter som är relaterade till administrationen av tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="51e08-105">Det ger också information om hur du konfigurerar tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="51e08-106">Azure</span><span class="sxs-lookup"><span data-stu-id="51e08-106">Azure</span></span>

<span data-ttu-id="51e08-107">Använd Microsoft Azure för att skapa hemligheter för nyckelvalv och lagringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="51e08-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="51e08-108">Använd sedan hemligheterna i konfigurationen för tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="51e08-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="51e08-109">Lifecycle Services</span></span>

<span data-ttu-id="51e08-110">Använd Microsoft Dynamics Lifecycle Services (LCS) för att aktivera tillägget för mikrotjänster för ditt LCS-distributionsprojekt.</span><span class="sxs-lookup"><span data-stu-id="51e08-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

<span data-ttu-id="51e08-111">I LCS väljer du panelen **Hantering av funktionen för förhandsgranskning** och aktivera sedan funktionen **E-faktureringstjänst**.</span><span class="sxs-lookup"><span data-stu-id="51e08-111">In LCS, select the **Preview feature management** tile, and then turn on the **e-Invoicing Service** feature.</span></span>

## <a name="regulatory-configuration-services"></a><span data-ttu-id="51e08-112">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="51e08-112">Regulatory Configuration Services</span></span>

<span data-ttu-id="51e08-113">Dynamics 365 Regulatory Configuration Services (RCS) är det gränssnitt som används för att konfigurerar tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-113">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="51e08-114">Resurser som t.ex. miljöer och funktioner för elektronisk fakturering skapas, underhålls och finns i RCS.</span><span class="sxs-lookup"><span data-stu-id="51e08-114">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="51e08-115">När resurserna är klara publiceras de i tilläggstjänsten Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-115">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="51e08-116">Mer information om RCS finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="51e08-116">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="51e08-117">Integrering med tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="51e08-117">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="51e08-118">Innan du kan använda RCS för att konfigurera elektroniska fakturor, måste du konfigurera RCS att det är tillåtet att kommunicera med tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-118">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="51e08-119">Du slutför den här konfigurationen på fliken **Tillägg för elektronisk fakturering** på sidan **Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="51e08-119">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="51e08-120">Slutpunkt för tjänst</span><span class="sxs-lookup"><span data-stu-id="51e08-120">Service endpoint</span></span>

<span data-ttu-id="51e08-121">URL-adressen till tilläggslutpunkten för Elektronisk fakturering kan variera beroende på Azure-datacentrets geografiska område.</span><span class="sxs-lookup"><span data-stu-id="51e08-121">The URL of the Electronic invoicing add-on endpoint can vary according to the Azure datacenter geography.</span></span> <span data-ttu-id="51e08-122">I följande register visas tillgänglighet per region:</span><span class="sxs-lookup"><span data-stu-id="51e08-122">The following table lists the availability per region:</span></span>

| <span data-ttu-id="51e08-123">Geografiskt område för Azure-datacenter</span><span class="sxs-lookup"><span data-stu-id="51e08-123">Azure datacenter geography</span></span> | <span data-ttu-id="51e08-124">URL för tjänstslutpunkt</span><span class="sxs-lookup"><span data-stu-id="51e08-124">Service endpoint URL</span></span>                                                       |
|----------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="51e08-125">Östra USA</span><span class="sxs-lookup"><span data-stu-id="51e08-125">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="51e08-126">Västra USA</span><span class="sxs-lookup"><span data-stu-id="51e08-126">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="51e08-127">Norra EU</span><span class="sxs-lookup"><span data-stu-id="51e08-127">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="51e08-128">Västra EU</span><span class="sxs-lookup"><span data-stu-id="51e08-128">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a><span data-ttu-id="51e08-129">Sökande-ID</span><span class="sxs-lookup"><span data-stu-id="51e08-129">Application ID</span></span>

<span data-ttu-id="51e08-130">Program-ID:t är ID:t för tilläggsprogrammet Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-130">The application ID is the ID of the Electronic invoicing add-on application.</span></span> <span data-ttu-id="51e08-131">I detta fall är värdet fast: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="51e08-131">In this case, the value is fixed: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

#### <a name="lcs-environment-id"></a><span data-ttu-id="51e08-132">ID för LCS-miljö</span><span class="sxs-lookup"><span data-stu-id="51e08-132">LCS environment ID</span></span>

<span data-ttu-id="51e08-133">ID:t för LCS-miljön är ID:t för ditt företags LCS-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="51e08-133">The LCS environment ID is the ID of your organization's LCS subscription.</span></span>

### <a name="service-environments"></a><span data-ttu-id="51e08-134">Tjänstmiljöer</span><span class="sxs-lookup"><span data-stu-id="51e08-134">Service environments</span></span>

<span data-ttu-id="51e08-135">Tjänstemiljöer är logiska partitioner som skapas för att stödja körning av elektroniska faktureringsfunktioner i tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-135">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="51e08-136">Säkerhetshemligheter, digitala certifikat och styrningen (dvs. åtkomstbehörigheter) måste konfigureras på servicemiljönivå.</span><span class="sxs-lookup"><span data-stu-id="51e08-136">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="51e08-137">Kunderna kan skapa så många servicemiljöer som de vill.</span><span class="sxs-lookup"><span data-stu-id="51e08-137">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="51e08-138">Alla servicemiljöer som en kund skapar är oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="51e08-138">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="51e08-139">Servicemiljöer måste skapas och underhållas i RCS.</span><span class="sxs-lookup"><span data-stu-id="51e08-139">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="51e08-140">När tjänstemiljöerna är klara måste de publiceras i tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-140">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="51e08-141">Status för tjänstemiljö</span><span class="sxs-lookup"><span data-stu-id="51e08-141">Service environment status</span></span>

<span data-ttu-id="51e08-142">Tjänstemiljöer kan hanteras via status.</span><span class="sxs-lookup"><span data-stu-id="51e08-142">Service environments can be managed through status.</span></span> <span data-ttu-id="51e08-143">Möjliga alternativ är:</span><span class="sxs-lookup"><span data-stu-id="51e08-143">The possible options are:</span></span>

- <span data-ttu-id="51e08-144">**Ej publicerad** – Miljön har skapats men ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="51e08-144">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="51e08-145">**Publicerad** – Miljön har publicerats i tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-145">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="51e08-146">**Ändrat** – Attributen för en publicerad miljö har ändrats, men ändringarna har ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="51e08-146">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="51e08-147">Kundhemligheter</span><span class="sxs-lookup"><span data-stu-id="51e08-147">Customer secrets</span></span>

<span data-ttu-id="51e08-148">Tilläggstjänsten Elektronisk fakturering bär ansvar för lagringen av alla dina affärsdata i de Azure-resurser som företaget äger.</span><span class="sxs-lookup"><span data-stu-id="51e08-148">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="51e08-149">Du måste skapa två huvudresurser för Azure om du vill säkerställa att tjänsten fungerar korrekt och att alla affärsdata som krävs för och genereras av tilläggstjänsten Elektronisk fakturering endast nås av tillägget.</span><span class="sxs-lookup"><span data-stu-id="51e08-149">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="51e08-150">Ett Azure Storage-konto (Blob Storage) som lagrar elektroniska fakturor</span><span class="sxs-lookup"><span data-stu-id="51e08-150">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="51e08-151">Ett Azure-nyckelvalv som lagrar certifikat, samt lagringskontots "uniform resource identifier (URI)"</span><span class="sxs-lookup"><span data-stu-id="51e08-151">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="51e08-152">Ett särskilt nyckelvalv och kundlagringskonto måste allokeras specifikt för att användas med tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-152">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="51e08-153">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="51e08-153">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="51e08-154">Användare</span><span class="sxs-lookup"><span data-stu-id="51e08-154">Users</span></span>

<span data-ttu-id="51e08-155">Varje servicemiljö måste visa en lista över de användare som kan ansluta från Dynamics 365 Finance och Dynamics 365 Supply Chain Management i tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-155">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="51e08-156">Publicering</span><span class="sxs-lookup"><span data-stu-id="51e08-156">Publication</span></span>

<span data-ttu-id="51e08-157">Tjänstemiljöerna måste publiceras i tillägget Elektronisk fakturering innan de kan användas.</span><span class="sxs-lookup"><span data-stu-id="51e08-157">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="51e08-158">Endast publicerade miljöer kan nås via Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="51e08-158">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="51e08-159">En tjänstemiljö måste dessutom publiceras innan några uppdateringar av dess attribut börjar gälla för den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="51e08-159">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="51e08-160">Anslutna program</span><span class="sxs-lookup"><span data-stu-id="51e08-160">Connected applications</span></span>

<span data-ttu-id="51e08-161">Anslutna program är de instanser av Finance och Supply Chain Management som du kanske vill nå via RCS.</span><span class="sxs-lookup"><span data-stu-id="51e08-161">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="51e08-162">Förutom program-URL:en och dess klientorganisation innehåller ett anslutet program även de autentiseringsuppgifter som gör att RCS kan ansluta till miljön.</span><span class="sxs-lookup"><span data-stu-id="51e08-162">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="51e08-163">Med hjälp av de anslutna programmen kan du konfigurera en del av den elektroniska faktureringsfunktionen i Finance och Supply Chain Management för att få hela den elektroniska faktureringsfunktionen att fungera.</span><span class="sxs-lookup"><span data-stu-id="51e08-163">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="51e08-164">Finance och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="51e08-164">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="51e08-165">Integrering med tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="51e08-165">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="51e08-166">Innan du kan använda Finance och Supply Chain Management för att utfärda elektroniska fakturor via tillägget Elektronisk fakturering, måste tillägget konfigureras att möjliggöra kommunikation med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="51e08-166">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="51e08-167">Integreringsfunktioner för tillägget Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="51e08-167">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="51e08-168">Om du vill aktivera kommunikationen mellan Finance och Supply Chain Management och tillägget Elektronisk fakturering måste du aktivera funktionen **Integrering av tillägget Elektronisk fakturering** i arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="51e08-168">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="51e08-169">Slutpunkt för tjänst</span><span class="sxs-lookup"><span data-stu-id="51e08-169">Service endpoint</span></span>

<span data-ttu-id="51e08-170">Tjänsteslutpunkten är den URL där tillägget Elektronisk fakturering finns.</span><span class="sxs-lookup"><span data-stu-id="51e08-170">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="51e08-171">Innan du kan utfärda elektroniska fakturor måste tjänsteslutpunkten konfigureras i Finance och Supply Chain Management i syfte att möjliggöra kommunikation med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="51e08-171">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="51e08-172">Om du vill konfigurera tjänsteslutpunkten går du till **Organisationsadministration \> Inställningar \> Parameter för elektroniskt dokument** innan du i fliken **Överföringstjänster** och fältet **URL för tillägget Elektronisk fakturering** anger URL:en enligt beskrivet i tabellen i avsnittet **Tjänsteslutpunkt**.</span><span class="sxs-lookup"><span data-stu-id="51e08-172">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="51e08-173">Miljöer</span><span class="sxs-lookup"><span data-stu-id="51e08-173">Environments</span></span>

<span data-ttu-id="51e08-174">Miljönamnet som anges i Finance och Supply Chain Management refererar till namnet på den miljö som skapas i RCS publiceras i tillägget Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="51e08-174">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="51e08-175">Miljön måste konfigureras i fliken **Överföringstjänster** på sidan **Parameter för elektroniskt dokument** så att alla begäranden om att utfärda elektroniska fakturor innehåller den miljö där tillägget Elektronisk fakturering kan avgöra vilken funktion för elektronisk fakturering som ska bearbeta begäran.</span><span class="sxs-lookup"><span data-stu-id="51e08-175">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51e08-176">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="51e08-176">Additional resources</span></span>

- [<span data-ttu-id="51e08-177">Konfigurera elektroniska fakturor i RCS</span><span class="sxs-lookup"><span data-stu-id="51e08-177">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="51e08-178">Utfärda elektroniska fakturor i Finance and Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="51e08-178">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
