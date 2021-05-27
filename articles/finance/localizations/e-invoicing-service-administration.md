---
title: Administrationskomponenter för Elektronisk fakturering
description: Detta ämne innehåller information om de komponenter som är relaterade till administrationen av Elektronisk fakturering.
author: gionoder
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 081d23c85d3555210b54597920a49e800ffe284b
ms.sourcegitcommit: 35fdcc6501e099c54a58583b1e3aba16f02a5ccc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5980934"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="ba65c-103">Administrationskomponenter för Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="ba65c-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ba65c-104">Detta ämne innehåller information om de komponenter som är relaterade till administrationen av Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="ba65c-105">Det ger också information om hur du konfigurerar Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="ba65c-106">Azure</span><span class="sxs-lookup"><span data-stu-id="ba65c-106">Azure</span></span>

<span data-ttu-id="ba65c-107">Använd Microsoft Azure för att skapa hemligheter för nyckelvalv och lagringsnyckel.</span><span class="sxs-lookup"><span data-stu-id="ba65c-107">Use Microsoft Azure to create the secrets for the Key Vault and storage account.</span></span> <span data-ttu-id="ba65c-108">Använd sedan hemligheterna i konfigurationen för Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="ba65c-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="ba65c-109">Lifecycle Services</span></span>

<span data-ttu-id="ba65c-110">Använd Microsoft Dynamics Lifecycle Services (LCS) för att aktivera för mikrotjänster för ditt LCS-distributionsprojekt.</span><span class="sxs-lookup"><span data-stu-id="ba65c-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="ba65c-111">Installationen av ett mikrotjänst i LCS kräver minst en virtuell dator för nivå 2.</span><span class="sxs-lookup"><span data-stu-id="ba65c-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="ba65c-112">Mer information om miljöplanering finns i [miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="ba65c-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="ba65c-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="ba65c-114">Dynamics 365 Regulatory Configuration Services (RCS) är det gränssnitt som används för att konfigurerar Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="ba65c-115">Resurser som t.ex. miljöer och funktioner för elektronisk fakturering skapas, underhålls och finns i RCS.</span><span class="sxs-lookup"><span data-stu-id="ba65c-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="ba65c-116">När resurserna är klara publiceras de i tjänsten Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="ba65c-117">För registrering av RCS, se [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="ba65c-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="ba65c-118">Mer information om RCS finns i [Regulatory Configuration Services (RCS) – globaliseringsfunktioner](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="ba65c-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="ba65c-119">Integrering med Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="ba65c-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="ba65c-120">Innan du kan använda RCS för att konfigurera elektroniska fakturor, måste du konfigurera RCS att det är tillåtet att kommunicera med Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="ba65c-121">Du slutför den här konfigurationen på fliken **Elektronisk fakturering** på sidan **Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="ba65c-122">Slutpunkt för tjänst</span><span class="sxs-lookup"><span data-stu-id="ba65c-122">Service endpoint</span></span>

<span data-ttu-id="ba65c-123">Elektronisk fakturering är tillgänglig i flera Azure-geografiska datacenterområden.</span><span class="sxs-lookup"><span data-stu-id="ba65c-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="ba65c-124">I följande register visas tillgänglighet per region.</span><span class="sxs-lookup"><span data-stu-id="ba65c-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="ba65c-125">Geografiskt område för Azure-datacenter</span><span class="sxs-lookup"><span data-stu-id="ba65c-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="ba65c-126">USA</span><span class="sxs-lookup"><span data-stu-id="ba65c-126">United States</span></span>              |
| <span data-ttu-id="ba65c-127">Europa</span><span class="sxs-lookup"><span data-stu-id="ba65c-127">Europe</span></span>                     |
| <span data-ttu-id="ba65c-128">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="ba65c-128">United Kingdom</span></span>             |
| <span data-ttu-id="ba65c-129">Asien</span><span class="sxs-lookup"><span data-stu-id="ba65c-129">Asia</span></span>                       |

### <a name="service-environments"></a><span data-ttu-id="ba65c-130">Tjänstmiljöer</span><span class="sxs-lookup"><span data-stu-id="ba65c-130">Service environments</span></span>

<span data-ttu-id="ba65c-131">Tjänstemiljöer är logiska partitioner som skapas för att stödja körning av elektroniska faktureringsfunktioner i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="ba65c-132">Säkerhetshemligheter, digitala certifikat och styrningen (dvs. åtkomstbehörigheter) måste konfigureras på servicemiljönivå.</span><span class="sxs-lookup"><span data-stu-id="ba65c-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="ba65c-133">Kunderna kan skapa så många servicemiljöer som de vill.</span><span class="sxs-lookup"><span data-stu-id="ba65c-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="ba65c-134">Alla servicemiljöer som en kund skapar är oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="ba65c-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="ba65c-135">Servicemiljöer måste skapas och underhållas i RCS.</span><span class="sxs-lookup"><span data-stu-id="ba65c-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="ba65c-136">När tjänstemiljöerna är klara måste de publiceras i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="ba65c-137">Status för tjänstemiljö</span><span class="sxs-lookup"><span data-stu-id="ba65c-137">Service environment status</span></span>

<span data-ttu-id="ba65c-138">Tjänstemiljöer kan hanteras via status.</span><span class="sxs-lookup"><span data-stu-id="ba65c-138">Service environments can be managed through status.</span></span> <span data-ttu-id="ba65c-139">Möjliga alternativ är:</span><span class="sxs-lookup"><span data-stu-id="ba65c-139">The possible options are:</span></span>

- <span data-ttu-id="ba65c-140">**Ej publicerad** – Miljön har skapats men ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="ba65c-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="ba65c-141">**Publicerad** – Miljön har publicerats i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="ba65c-142">**Ändrat** – Attributen för en publicerad miljö har ändrats, men ändringarna har ännu inte publicerats.</span><span class="sxs-lookup"><span data-stu-id="ba65c-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="ba65c-143">Kundhemligheter</span><span class="sxs-lookup"><span data-stu-id="ba65c-143">Customer secrets</span></span>

<span data-ttu-id="ba65c-144">Tjänsten Elektronisk fakturering bär ansvar för lagringen av alla dina affärsdata i de Azure-resurser som företaget äger.</span><span class="sxs-lookup"><span data-stu-id="ba65c-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="ba65c-145">Du måste skapa två huvudresurser för Azure om du vill säkerställa att tjänsten fungerar korrekt och att alla affärsdata som behövs för och genereras av tjänsten elektronisk fakturering endast används av tillägget.</span><span class="sxs-lookup"><span data-stu-id="ba65c-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="ba65c-146">Ett Azure Storage-konto (Blob Storage) som lagrar elektroniska fakturor</span><span class="sxs-lookup"><span data-stu-id="ba65c-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="ba65c-147">Ett Azure-nyckelvalv som lagrar certifikat samt lagringskontots "uniform resource identifier (URI)"</span><span class="sxs-lookup"><span data-stu-id="ba65c-147">An Azure Key Vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>


<span data-ttu-id="ba65c-148">Ett särskilt nyckelvalv och kundlagringskonto måste allokeras specifikt för att användas med Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-148">A dedicated Key Vault and customer storage account must be allocated specifically for use with Electronic Invoicing.</span></span> <span data-ttu-id="ba65c-149">Mer information finns i [Skapa ett Azure-lagringskonto och ett nyckelvalv](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-149">For more information, see [Create an Azure storage account and a Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

<span data-ttu-id="ba65c-150">Om du vill övervaka dina nyckelvalv och ta emot notifieringar konfigurerar du Azure Monitor för nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="ba65c-150">To monitor the health of your Key Vault and receive alerts, configure the Azure Monitor for key Vault.</span></span> <span data-ttu-id="ba65c-151">Genom att aktivera nyckelvalvsloggning kan du övervaka hur, när och av vem dina nyckelvalv ska användas.</span><span class="sxs-lookup"><span data-stu-id="ba65c-151">By enabling Key Vault logging, you can monitor how, when, and by whom your Key Vaults are accessed.</span></span> <span data-ttu-id="ba65c-152">Mer information finns i [Övervakning och notifiering för Azure-nyckelvalv](/azure/key-vault/general/alert) och [Så här aktiverar du nyckelvalvsloggning](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span><span class="sxs-lookup"><span data-stu-id="ba65c-152">For more information, see [Monitoring and alerting for Azure Key Vault](/azure/key-vault/general/alert) and [How to enable Key Vault logging](/azure/key-vault/general/howto-logging?tabs=azure-cli).</span></span>

<span data-ttu-id="ba65c-153">Det rekommenderas att regelbundet ändra hemligheterna.</span><span class="sxs-lookup"><span data-stu-id="ba65c-153">As a best practice, periodically rotate the secrets.</span></span> <span data-ttu-id="ba65c-154">Mer information finns i [Hemlighetsdokumentationen](/azure/key-vault/secrets/).</span><span class="sxs-lookup"><span data-stu-id="ba65c-154">For more information, see [Secrets documentation](/azure/key-vault/secrets/).</span></span>

#### <a name="users"></a><span data-ttu-id="ba65c-155">Användare</span><span class="sxs-lookup"><span data-stu-id="ba65c-155">Users</span></span>

<span data-ttu-id="ba65c-156">Varje servicemiljö måste visa en lista över de användare som kan ansluta från Dynamics 365 Finance och Dynamics 365 Supply Chain Management i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-156">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="ba65c-157">Publicering</span><span class="sxs-lookup"><span data-stu-id="ba65c-157">Publication</span></span>

<span data-ttu-id="ba65c-158">Tjänstemiljöerna måste publiceras i Elektronisk fakturering innan de kan användas.</span><span class="sxs-lookup"><span data-stu-id="ba65c-158">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="ba65c-159">Endast publicerade miljöer kan nås via Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ba65c-159">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="ba65c-160">En tjänstemiljö måste dessutom publiceras innan några uppdateringar av dess attribut börjar gälla för den elektroniska faktureringstjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba65c-160">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="ba65c-161">Anslutna program</span><span class="sxs-lookup"><span data-stu-id="ba65c-161">Connected applications</span></span>

<span data-ttu-id="ba65c-162">Anslutna program är de instanser av Finance och Supply Chain Management som du kanske vill nå via RCS.</span><span class="sxs-lookup"><span data-stu-id="ba65c-162">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="ba65c-163">Förutom program-URL:en och dess klientorganisation innehåller ett anslutet program även de autentiseringsuppgifter som gör att RCS kan ansluta till miljön.</span><span class="sxs-lookup"><span data-stu-id="ba65c-163">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="ba65c-164">Med hjälp av de anslutna programmen kan du konfigurera en del av den elektroniska faktureringsfunktionen i Finance och Supply Chain Management för att få hela den elektroniska faktureringsfunktionen att fungera.</span><span class="sxs-lookup"><span data-stu-id="ba65c-164">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="ba65c-165">Finance och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ba65c-165">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="ba65c-166">Integrering med Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="ba65c-166">Integration with Electronic invoicing</span></span>

<span data-ttu-id="ba65c-167">Innan du kan använda Finance och Supply Chain Management för att utfärda elektroniska fakturor via Elektronisk fakturering, måste tillägget konfigureras att möjliggöra kommunikation med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba65c-167">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="ba65c-168">Integreringsfunktioner för Elektronisk fakturering</span><span class="sxs-lookup"><span data-stu-id="ba65c-168">Electronic invoicing integration feature</span></span>

<span data-ttu-id="ba65c-169">Om du vill aktivera kommunikationen mellan Finance och Supply Chain Management och Elektronisk fakturering måste du aktivera funktionen **Integrering av Elektronisk fakturering** i arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-169">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="ba65c-170">Slutpunkt för tjänst</span><span class="sxs-lookup"><span data-stu-id="ba65c-170">Service endpoint</span></span>

<span data-ttu-id="ba65c-171">Tjänsteslutpunkten är den URL där Elektronisk fakturering finns.</span><span class="sxs-lookup"><span data-stu-id="ba65c-171">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="ba65c-172">Innan du kan utfärda elektroniska fakturor måste tjänsteslutpunkten konfigureras i Finance och Supply Chain Management i syfte att möjliggöra kommunikation med tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ba65c-172">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="ba65c-173">Om du vill konfigurera tjänsteslutpunkten går du till **Organisationsadministration \> Inställningar \> Parameter för elektroniskt dokument** innan du i fliken **Överföringstjänster** och fältet **URL för Elektronisk fakturering** anger URL:en enligt beskrivet i tabellen i avsnittet **Tjänsteslutpunkt**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-173">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="ba65c-174">Miljöer</span><span class="sxs-lookup"><span data-stu-id="ba65c-174">Environments</span></span>

<span data-ttu-id="ba65c-175">Miljönamnet som anges i Finance och Supply Chain Management refererar till namnet på den miljö som skapas i RCS publiceras i Elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="ba65c-175">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="ba65c-176">Miljön måste konfigureras i fliken **Överföringstjänster** på sidan **Parameter för elektroniskt dokument** så att alla begäranden om att utfärda elektroniska fakturor innehåller den miljö där Elektronisk fakturering kan avgöra vilken funktion för elektronisk fakturering som ska bearbeta begäran.</span><span class="sxs-lookup"><span data-stu-id="ba65c-176">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba65c-177">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ba65c-177">Additional resources</span></span>

- [<span data-ttu-id="ba65c-178">Konfigurera elektroniska fakturor i RCS</span><span class="sxs-lookup"><span data-stu-id="ba65c-178">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="ba65c-179">Utfärda elektroniska fakturor i Finance and Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ba65c-179">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
