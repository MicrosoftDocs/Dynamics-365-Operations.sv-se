---
title: Tillägg för lagersynlighet
description: I det här avsnittet beskrivs hur du installerar och konfigurerar tillägg för lagersynlighet för Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114680"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="e8060-103">Tillägg för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="e8060-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e8060-104">Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="e8060-105">All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="e8060-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="e8060-106">Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.</span><span class="sxs-lookup"><span data-stu-id="e8060-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="e8060-107">Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="e8060-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="e8060-108">Det går också att uppgradera indexet för att göra lagerfrågor.</span><span class="sxs-lookup"><span data-stu-id="e8060-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="e8060-109">Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare.</span><span class="sxs-lookup"><span data-stu-id="e8060-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="e8060-110">Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="e8060-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="e8060-111">I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).</span><span class="sxs-lookup"><span data-stu-id="e8060-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="e8060-112">Installera tillägget för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="e8060-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="e8060-113">Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e8060-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e8060-114">LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="e8060-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="e8060-115">Mer information finns i [Lifecycle Services, resurser](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="e8060-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e8060-116">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e8060-116">Prerequisites</span></span>

<span data-ttu-id="e8060-117">Innan du installerar tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="e8060-118">Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.</span><span class="sxs-lookup"><span data-stu-id="e8060-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="e8060-119">Generera betanycklarna för erbjudandet i LCS.</span><span class="sxs-lookup"><span data-stu-id="e8060-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="e8060-120">Aktivera betanycklarna för ditt erbjudande för din användare i LCS.</span><span class="sxs-lookup"><span data-stu-id="e8060-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="e8060-121">Kontakta Microsoft produktteam för lagersynlighet och ange ett miljö-ID där du vill distribuera tilläggsprogrammet för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="e8060-122">Om du har några frågor om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="e8060-123">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="e8060-123">Install the add-in</span></span>

<span data-ttu-id="e8060-124">För att installera tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="e8060-125">Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.</span><span class="sxs-lookup"><span data-stu-id="e8060-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="e8060-126">Välj det projekt där miljön har distribuerats på startsidan.</span><span class="sxs-lookup"><span data-stu-id="e8060-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="e8060-127">Välj den miljö där du vill installera tillägget på projektsidan.</span><span class="sxs-lookup"><span data-stu-id="e8060-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="e8060-128">Bläddra nedåt på sidan miljö, tills avsnittet **miljötillägg** visas.</span><span class="sxs-lookup"><span data-stu-id="e8060-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="e8060-129">Om avsnittet inte visas kontrollerar du att de nödvändiga betanycklarna har bearbetats fullständigt.</span><span class="sxs-lookup"><span data-stu-id="e8060-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="e8060-130">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="e8060-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="e8060-131">![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")</span><span class="sxs-lookup"><span data-stu-id="e8060-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="e8060-132">Välj länken **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="e8060-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="e8060-133">En lista med tillgängliga tillägg öppnas.</span><span class="sxs-lookup"><span data-stu-id="e8060-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="e8060-134">Välj **lagertjänst** i listan.</span><span class="sxs-lookup"><span data-stu-id="e8060-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="e8060-135">(Observera att detta nu kan vara listat som **Tillägg för lagersynlighet för Dynamics 365 Supply Chain Management**).</span><span class="sxs-lookup"><span data-stu-id="e8060-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="e8060-136">Ange värden för följande fält i miljön:</span><span class="sxs-lookup"><span data-stu-id="e8060-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="e8060-137">**AAD app-ID**</span><span class="sxs-lookup"><span data-stu-id="e8060-137">**AAD application ID**</span></span>
    - <span data-ttu-id="e8060-138">**AAD klientorganisationens ID**</span><span class="sxs-lookup"><span data-stu-id="e8060-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="e8060-139">![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")</span><span class="sxs-lookup"><span data-stu-id="e8060-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="e8060-140">Godkänn villkoren genom att markera kryssrutan **villkor**.</span><span class="sxs-lookup"><span data-stu-id="e8060-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="e8060-141">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="e8060-141">Select **Install**.</span></span> <span data-ttu-id="e8060-142">Tilläggets status visas som **installerar**.</span><span class="sxs-lookup"><span data-stu-id="e8060-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="e8060-143">När det är klart uppdaterar du sidan så att status ändras till **installerad**.</span><span class="sxs-lookup"><span data-stu-id="e8060-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="e8060-144">Hämta en säkerhetstoken för säkerhetstjänst</span><span class="sxs-lookup"><span data-stu-id="e8060-144">Get a security service token</span></span>

<span data-ttu-id="e8060-145">Hämta en säkerhetstjänsttoken genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-145">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="e8060-146">Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="e8060-146">Sign in to Azure Portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="e8060-147">Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="e8060-147">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="e8060-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="e8060-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="e8060-149">**Metod** - `GET`</span><span class="sxs-lookup"><span data-stu-id="e8060-149">**Method** - `GET`</span></span>
    - <span data-ttu-id="e8060-150">**Brödtext (formulärdata)**:</span><span class="sxs-lookup"><span data-stu-id="e8060-150">**Body content (form data)**:</span></span>

        | <span data-ttu-id="e8060-151">nyckel</span><span class="sxs-lookup"><span data-stu-id="e8060-151">key</span></span> | <span data-ttu-id="e8060-152">värde</span><span class="sxs-lookup"><span data-stu-id="e8060-152">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="e8060-153">klient-ID</span><span class="sxs-lookup"><span data-stu-id="e8060-153">client_id</span></span> | <span data-ttu-id="e8060-154">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="e8060-154">${aadAppId}</span></span> |
        | <span data-ttu-id="e8060-155">client_secret</span><span class="sxs-lookup"><span data-stu-id="e8060-155">client_secret</span></span> | <span data-ttu-id="e8060-156">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="e8060-156">${aadAppSecret}</span></span> |
        | <span data-ttu-id="e8060-157">grant_type</span><span class="sxs-lookup"><span data-stu-id="e8060-157">grant_type</span></span> | <span data-ttu-id="e8060-158">client_credentials</span><span class="sxs-lookup"><span data-stu-id="e8060-158">client_credentials</span></span> |
        | <span data-ttu-id="e8060-159">resurs</span><span class="sxs-lookup"><span data-stu-id="e8060-159">resource</span></span> | <span data-ttu-id="e8060-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="e8060-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="e8060-161">Du bör få `aadToken` i svar, som liknar följande exempel.</span><span class="sxs-lookup"><span data-stu-id="e8060-161">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="e8060-162">Formulera en JSON-begäran som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-162">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="e8060-163">Där:</span><span class="sxs-lookup"><span data-stu-id="e8060-163">Where:</span></span>
    - <span data-ttu-id="e8060-164">Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="e8060-164">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="e8060-165">Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.</span><span class="sxs-lookup"><span data-stu-id="e8060-165">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="e8060-166">Ställ in alla andra värden enligt exemplet.</span><span class="sxs-lookup"><span data-stu-id="e8060-166">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="e8060-167">Skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="e8060-167">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="e8060-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="e8060-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="e8060-169">**Metod** - `POST`</span><span class="sxs-lookup"><span data-stu-id="e8060-169">**Method** - `POST`</span></span>
    - <span data-ttu-id="e8060-170">**HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)</span><span class="sxs-lookup"><span data-stu-id="e8060-170">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="e8060-171">**Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="e8060-171">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="e8060-172">Du får ett `access_token` i svar.</span><span class="sxs-lookup"><span data-stu-id="e8060-172">You will get an `access_token` in response.</span></span> <span data-ttu-id="e8060-173">Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-173">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="e8060-174">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="e8060-174">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="e8060-175">Avinstallera tillägget</span><span class="sxs-lookup"><span data-stu-id="e8060-175">Uninstall the add-in</span></span>

<span data-ttu-id="e8060-176">För att avinstallera tillägget, välj **avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="e8060-176">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="e8060-177">Uppdatera LCS och tillägget för lagersynlighet tas bort.</span><span class="sxs-lookup"><span data-stu-id="e8060-177">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="e8060-178">Avinstallationsprocessen kommer att ta bort registreringen av tillägget och även starta ett jobb för att rensa alla affärsdata som lagras i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e8060-178">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="e8060-179">Tillägg för lagersynlighet i ofentlig API</span><span class="sxs-lookup"><span data-stu-id="e8060-179">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="e8060-180">Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen.</span><span class="sxs-lookup"><span data-stu-id="e8060-180">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="e8060-181">Den stöder tre huvudinteraktionstyper:</span><span class="sxs-lookup"><span data-stu-id="e8060-181">It supports three main interaction types:</span></span>

- <span data-ttu-id="e8060-182">Bokföring av behållningsändringar i tillägget från ett externt system.</span><span class="sxs-lookup"><span data-stu-id="e8060-182">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="e8060-183">Fråga om aktuell behållning från ett externt system.</span><span class="sxs-lookup"><span data-stu-id="e8060-183">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="e8060-184">Automatisk synkronisering med behållning av Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e8060-184">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="e8060-185">Den automatiska synkroniseringen ingår inte i det offentliga API utan hanteras i stället i bakgrunden för miljöer där tillägget lager synlighet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="e8060-185">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="e8060-186">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="e8060-186">Authentication</span></span>

<span data-ttu-id="e8060-187">Plattformens säkerhetstoken används för att anropa tillägget för lagersynlighet, så du måste generera en Azure Active Directory token med Azure Active Directory-appen.</span><span class="sxs-lookup"><span data-stu-id="e8060-187">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="e8060-188">Mer information om hur du hämtar säkerhetstoken finns i [installera tillägget för lagersynlighet](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="e8060-188">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="e8060-189">Konfigurera API för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="e8060-189">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="e8060-190">Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="e8060-190">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="e8060-191">Konfigurationen kan variera beroende på vad som gäller för din miljö.</span><span class="sxs-lookup"><span data-stu-id="e8060-191">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="e8060-192">Den omfattar huvudsakligen fyra delar:</span><span class="sxs-lookup"><span data-stu-id="e8060-192">It primarily includes four parts:</span></span>

- [<span data-ttu-id="e8060-193">Partitionering</span><span class="sxs-lookup"><span data-stu-id="e8060-193">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="e8060-194">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="e8060-194">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="e8060-195">Indexering</span><span class="sxs-lookup"><span data-stu-id="e8060-195">Indexing</span></span>](#indexing)
- [<span data-ttu-id="e8060-196">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="e8060-196">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="e8060-197">Partitionering</span><span class="sxs-lookup"><span data-stu-id="e8060-197">Partitioning</span></span>

<span data-ttu-id="e8060-198">Partitionering kan i stor grad påverka prestandan för API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-198">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="e8060-199">Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågor.</span><span class="sxs-lookup"><span data-stu-id="e8060-199">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="e8060-200">`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*.</span><span class="sxs-lookup"><span data-stu-id="e8060-200">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="e8060-201">Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.</span><span class="sxs-lookup"><span data-stu-id="e8060-201">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="e8060-202">*Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-202">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="e8060-203">I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="e8060-203">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="e8060-204">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="e8060-204">Dimension configurations</span></span>

<span data-ttu-id="e8060-205">Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.</span><span class="sxs-lookup"><span data-stu-id="e8060-205">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="e8060-206">I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-206">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="e8060-207">Dimensionstyp</span><span class="sxs-lookup"><span data-stu-id="e8060-207">Dimension type</span></span> | <span data-ttu-id="e8060-208">Dimensionsnamn</span><span class="sxs-lookup"><span data-stu-id="e8060-208">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="e8060-209">Produkt</span><span class="sxs-lookup"><span data-stu-id="e8060-209">Product</span></span> | `ColorId` |
| <span data-ttu-id="e8060-210">Produkt</span><span class="sxs-lookup"><span data-stu-id="e8060-210">Product</span></span> | `SizeId` |
| <span data-ttu-id="e8060-211">Produkt</span><span class="sxs-lookup"><span data-stu-id="e8060-211">Product</span></span> | `StyleId` |
| <span data-ttu-id="e8060-212">Produkt</span><span class="sxs-lookup"><span data-stu-id="e8060-212">Product</span></span> | `ConfigId` |
| <span data-ttu-id="e8060-213">Spårning</span><span class="sxs-lookup"><span data-stu-id="e8060-213">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="e8060-214">Spårning</span><span class="sxs-lookup"><span data-stu-id="e8060-214">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="e8060-215">Plats</span><span class="sxs-lookup"><span data-stu-id="e8060-215">Location</span></span> | `LocationId` |
| <span data-ttu-id="e8060-216">Plats</span><span class="sxs-lookup"><span data-stu-id="e8060-216">Location</span></span> | `SiteId` |
| <span data-ttu-id="e8060-217">Lagerstatus</span><span class="sxs-lookup"><span data-stu-id="e8060-217">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="e8060-218">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="e8060-218">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="e8060-219">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="e8060-219">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="e8060-220">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="e8060-220">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="e8060-221">Dimensionstypen som visas i föregående tabell är endast referens.</span><span class="sxs-lookup"><span data-stu-id="e8060-221">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="e8060-222">Du behöver inte ange dimensionstypen i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-222">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="e8060-223">Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-223">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="e8060-224">Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="e8060-224">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="e8060-225">Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="e8060-225">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="e8060-226">Måldimensionerna måste vara en av följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-226">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="e8060-227">Standarddimensioner vid lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="e8060-227">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="e8060-228">Anpassade dimensioner</span><span class="sxs-lookup"><span data-stu-id="e8060-228">Custom dimensions</span></span>

<span data-ttu-id="e8060-229">Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågan på dimensioner och bokföringshändelsen med dimensioner.</span><span class="sxs-lookup"><span data-stu-id="e8060-229">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="e8060-230">Indexering</span><span class="sxs-lookup"><span data-stu-id="e8060-230">Indexing</span></span>

<span data-ttu-id="e8060-231">För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e8060-231">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="e8060-232">Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e8060-232">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="e8060-233">För närvarande kan du bara konfigurera index till maximalt fem.</span><span class="sxs-lookup"><span data-stu-id="e8060-233">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="e8060-234">Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="e8060-234">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="e8060-235">Om du till exempel vill söka efter produkter enligt följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-235">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="e8060-236">Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.</span><span class="sxs-lookup"><span data-stu-id="e8060-236">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="e8060-237">I vissa fall vill du bara fråga den totala produkten.</span><span class="sxs-lookup"><span data-stu-id="e8060-237">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="e8060-238">Två index är definierade som följande:</span><span class="sxs-lookup"><span data-stu-id="e8060-238">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="e8060-239">Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.</span><span class="sxs-lookup"><span data-stu-id="e8060-239">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="e8060-240">Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning.</span><span class="sxs-lookup"><span data-stu-id="e8060-240">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="e8060-241">I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`.</span><span class="sxs-lookup"><span data-stu-id="e8060-241">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="e8060-242">Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.</span><span class="sxs-lookup"><span data-stu-id="e8060-242">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="e8060-243">Du kan ange frågevillkor i den begärandetext.</span><span class="sxs-lookup"><span data-stu-id="e8060-243">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="e8060-244">Här är en exempel fråga på produkten med kombinationen färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="e8060-244">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="e8060-245">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="e8060-245">Custom measurement</span></span>

<span data-ttu-id="e8060-246">Standardmåttkvantiteterna är kopplade till Supply Chain Management, men du kanske vill ha en kvantitet som består av en kombination av standardmått.</span><span class="sxs-lookup"><span data-stu-id="e8060-246">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="e8060-247">För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågorna.</span><span class="sxs-lookup"><span data-stu-id="e8060-247">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="e8060-248">Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.</span><span class="sxs-lookup"><span data-stu-id="e8060-248">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="e8060-249">Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.</span><span class="sxs-lookup"><span data-stu-id="e8060-249">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="e8060-250">Förbrukningssystem</span><span class="sxs-lookup"><span data-stu-id="e8060-250">Consumption system</span></span> | <span data-ttu-id="e8060-251">Beräknade mått</span><span class="sxs-lookup"><span data-stu-id="e8060-251">Calculated measurers</span></span> | <span data-ttu-id="e8060-252">Datakälla</span><span class="sxs-lookup"><span data-stu-id="e8060-252">Data source</span></span> | <span data-ttu-id="e8060-253">Modifierare</span><span class="sxs-lookup"><span data-stu-id="e8060-253">Modifier</span></span> | <span data-ttu-id="e8060-254">Beräkningstyp för modifierare</span><span class="sxs-lookup"><span data-stu-id="e8060-254">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="e8060-255">Tillägg</span><span class="sxs-lookup"><span data-stu-id="e8060-255">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="e8060-256">Tillägg</span><span class="sxs-lookup"><span data-stu-id="e8060-256">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="e8060-257">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="e8060-257">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="e8060-258">Tillägg</span><span class="sxs-lookup"><span data-stu-id="e8060-258">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="e8060-259">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="e8060-259">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="e8060-260">Tillägg</span><span class="sxs-lookup"><span data-stu-id="e8060-260">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="e8060-261">Tillägg</span><span class="sxs-lookup"><span data-stu-id="e8060-261">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="e8060-262">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="e8060-262">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="e8060-263">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="e8060-263">Subtraction</span></span> |

<span data-ttu-id="e8060-264">Med detta kommer frågan för den anpassade måttkvantiteten att returnera följande resultat.</span><span class="sxs-lookup"><span data-stu-id="e8060-264">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="e8060-265">`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:</span><span class="sxs-lookup"><span data-stu-id="e8060-265">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="e8060-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="e8060-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="e8060-267">Bokföra lagerbehållningsändringar</span><span class="sxs-lookup"><span data-stu-id="e8060-267">Posting on-hand changes</span></span>

<span data-ttu-id="e8060-268">Den exakta URL som händelsen ska skickas till beror på din geografiska region.</span><span class="sxs-lookup"><span data-stu-id="e8060-268">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="e8060-269">Formuläret kommer att ha följande format:</span><span class="sxs-lookup"><span data-stu-id="e8060-269">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="e8060-270">När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e8060-270">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="e8060-271">En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till.</span><span class="sxs-lookup"><span data-stu-id="e8060-271">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="e8060-272">Exempel:</span><span class="sxs-lookup"><span data-stu-id="e8060-272">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="e8060-273">Skicka behållningsändringar fråga exempel 1</span><span class="sxs-lookup"><span data-stu-id="e8060-273">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="e8060-274">I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e8060-274">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="e8060-275">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="e8060-275">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="e8060-276">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor.</span><span class="sxs-lookup"><span data-stu-id="e8060-276">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="e8060-277">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="e8060-277">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="e8060-278">Skicka behållningsändringar fråga exempel 2</span><span class="sxs-lookup"><span data-stu-id="e8060-278">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="e8060-279">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e8060-279">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="e8060-280">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="e8060-280">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="e8060-281">JSON dokumentfältegenskaper</span><span class="sxs-lookup"><span data-stu-id="e8060-281">JSON document field properties</span></span>

<span data-ttu-id="e8060-282">De fält från exempel för JSON-frågor som tidigare har angetts har de egenskaper som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="e8060-282">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="e8060-283">Fält-ID</span><span class="sxs-lookup"><span data-stu-id="e8060-283">Field ID</span></span> | <span data-ttu-id="e8060-284">beskrivning</span><span class="sxs-lookup"><span data-stu-id="e8060-284">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="e8060-285">Ett unikt ID för den specifika ändringshändelsen.</span><span class="sxs-lookup"><span data-stu-id="e8060-285">A unique ID for the specific change event.</span></span> <span data-ttu-id="e8060-286">Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet.</span><span class="sxs-lookup"><span data-stu-id="e8060-286">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="e8060-287">Identifierare för den organisation som är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="e8060-287">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="e8060-288">Detta mappar till Supply Chain Management organisations eller dataområdes-ID.</span><span class="sxs-lookup"><span data-stu-id="e8060-288">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="e8060-289">Den unika identifieraren av produkten i fråga.</span><span class="sxs-lookup"><span data-stu-id="e8060-289">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="e8060-290">Kvantiteten som behållningen måste ändras med.</span><span class="sxs-lookup"><span data-stu-id="e8060-290">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="e8060-291">Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10.</span><span class="sxs-lookup"><span data-stu-id="e8060-291">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="e8060-292">Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3.</span><span class="sxs-lookup"><span data-stu-id="e8060-292">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="e8060-293">Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga.</span><span class="sxs-lookup"><span data-stu-id="e8060-293">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="e8060-294">Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan.</span><span class="sxs-lookup"><span data-stu-id="e8060-294">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="e8060-295">Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e8060-295">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="e8060-296">Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågorna.</span><span class="sxs-lookup"><span data-stu-id="e8060-296">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="e8060-297">En dynamisk uppsättning nyckel/värde-par.</span><span class="sxs-lookup"><span data-stu-id="e8060-297">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="e8060-298">Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system.</span><span class="sxs-lookup"><span data-stu-id="e8060-298">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="e8060-299">Fråga aktuell behållning</span><span class="sxs-lookup"><span data-stu-id="e8060-299">Querying current on-hand</span></span>

<span data-ttu-id="e8060-300">Slutpunkten för att hämta den aktuella behållningen har en liknande URL:</span><span class="sxs-lookup"><span data-stu-id="e8060-300">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="e8060-301">Den kommer att frågas med HTTP `POST`-metoden.</span><span class="sxs-lookup"><span data-stu-id="e8060-301">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="e8060-302">Aktuellt behållningsexempel 1</span><span class="sxs-lookup"><span data-stu-id="e8060-302">Current on-hand query example 1</span></span>

<span data-ttu-id="e8060-303">I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e8060-303">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="e8060-304">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="e8060-304">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="e8060-305">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor.</span><span class="sxs-lookup"><span data-stu-id="e8060-305">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="e8060-306">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="e8060-306">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="e8060-307">Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="e8060-307">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="e8060-308">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="e8060-308">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="e8060-309">Aktuellt behållningsexempel 2</span><span class="sxs-lookup"><span data-stu-id="e8060-309">Current on-hand query example 2</span></span>

<span data-ttu-id="e8060-310">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e8060-310">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="e8060-311">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="e8060-311">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="e8060-312">Exempel på returresultat</span><span class="sxs-lookup"><span data-stu-id="e8060-312">Example return result</span></span>

<span data-ttu-id="e8060-313">Frågorna som visas i föregående exempel kan returnera resultatet.</span><span class="sxs-lookup"><span data-stu-id="e8060-313">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="e8060-314">Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.</span><span class="sxs-lookup"><span data-stu-id="e8060-314">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
