---
title: Tillägg för lagersynlighet
description: I det här avsnittet beskrivs hur du installerar och konfigurerar tillägg för lagersynlighet för Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d09c7be5de75511b10d7a69d4b8ac12917b0dbe8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910435"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="94c2b-103">Tillägg för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="94c2b-104">Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="94c2b-105">All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="94c2b-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="94c2b-106">Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="94c2b-107">Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="94c2b-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="94c2b-108">Det går också att uppgradera indexet för att göra lagerfrågeställningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="94c2b-109">Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare.</span><span class="sxs-lookup"><span data-stu-id="94c2b-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="94c2b-110">Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="94c2b-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="94c2b-111">I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).</span><span class="sxs-lookup"><span data-stu-id="94c2b-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="94c2b-112">Installera tillägget för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="94c2b-113">Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="94c2b-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="94c2b-114">LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="94c2b-115">Mer information finns i [Lifecycle Services, resurser](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="94c2b-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="94c2b-116">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="94c2b-116">Prerequisites</span></span>

<span data-ttu-id="94c2b-117">Innan du installerar tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="94c2b-118">Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.</span><span class="sxs-lookup"><span data-stu-id="94c2b-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="94c2b-119">Se till att kraven för att ställa in tillägg som finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="94c2b-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="94c2b-120">Lagersynlighet kräver inte länkning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="94c2b-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="94c2b-121">Kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få följande tre filer:</span><span class="sxs-lookup"><span data-stu-id="94c2b-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="94c2b-122">`Inventory Visibility Integration.zip` (om versionen av Supply Chain Management som du kör är tidigare än version 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="94c2b-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="94c2b-123">Följ instruktionerna i [Snabbstart: Registrera ett program med Microsofts identitetsplattform](/azure/active-directory/develop/quickstart-register-app) om du vill registrera ett program och lägga till en klienthemlighet i AAD i samband med din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="94c2b-123">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
    - [<span data-ttu-id="94c2b-124">Registrera ett program</span><span class="sxs-lookup"><span data-stu-id="94c2b-124">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
    - [<span data-ttu-id="94c2b-125">Lägg till en klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-125">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
    - <span data-ttu-id="94c2b-126">I följande steg används **ID för program (klient)**, **Klienthemlighet** samt **ID för klientorganisation**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-126">The **Application(Client) Id**, **Client Secret** and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="94c2b-127">De länder och regioner som för närvarande stöds är Kanada, USA och Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="94c2b-127">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="94c2b-128">Om du har några frågeställningar om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-128">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="94c2b-129">Ställ in Dataverse</span><span class="sxs-lookup"><span data-stu-id="94c2b-129">Set up Dataverse</span></span>

<span data-ttu-id="94c2b-130">Följ dessa steg för att konfigurera Dataverse.</span><span class="sxs-lookup"><span data-stu-id="94c2b-130">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="94c2b-131">Lägg till en serviceprincip för din innehavare:</span><span class="sxs-lookup"><span data-stu-id="94c2b-131">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="94c2b-132">Installera Azure AD PowerShell modul v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="94c2b-132">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="94c2b-133">Kör följande PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="94c2b-133">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="94c2b-134">Skapa en programanvändare för lagersynlighet i Dataverse:</span><span class="sxs-lookup"><span data-stu-id="94c2b-134">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="94c2b-135">Öppna URL-adressen för din Dataverse miljö.</span><span class="sxs-lookup"><span data-stu-id="94c2b-135">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="94c2b-136">Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare.</span><span class="sxs-lookup"><span data-stu-id="94c2b-136">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="94c2b-137">Använd visningsmenyn för att ändra sidvisningen till **appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-137">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="94c2b-138">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-138">Select **New**.</span></span> <span data-ttu-id="94c2b-139">Ange app-ID till *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="94c2b-139">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="94c2b-140">(Objekt-ID:t läses in automatiskt när du sparar ändringarna.) Du kan anpassa namnet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-140">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="94c2b-141">Du kan till exempel ändra den till *Lagersynlighet*.</span><span class="sxs-lookup"><span data-stu-id="94c2b-141">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="94c2b-142">Välj **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-142">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="94c2b-143">Välj **Tilldela roll** och välj sedan **Systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-143">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="94c2b-144">Om det finns en roll med namnet **Common Data Service Användare** väljer du den också.</span><span class="sxs-lookup"><span data-stu-id="94c2b-144">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="94c2b-145">Mer information finns i [Skapa en appanvändare](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="94c2b-145">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="94c2b-146">Om standardspråket för ditt Dataverse inte är **Engelska**:</span><span class="sxs-lookup"><span data-stu-id="94c2b-146">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="94c2b-147">Gå till **Avancerad inställning \> Administration \> Språk**,</span><span class="sxs-lookup"><span data-stu-id="94c2b-147">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="94c2b-148">Välj **Engelska (LanguageCode=1033)** och sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-148">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="94c2b-149">Importera `Inventory Visibility Dataverse Solution.zip` filen, inklusive Dataverse konfigurationsrelaterade enheter och Power Apps:</span><span class="sxs-lookup"><span data-stu-id="94c2b-149">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="94c2b-150">Gå till sidan **Lösningar**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-150">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="94c2b-151">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-151">Select **Import**.</span></span>

1. <span data-ttu-id="94c2b-152">Importera flödet för flödesutlösaren för konfigurationsuppgradering:</span><span class="sxs-lookup"><span data-stu-id="94c2b-152">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="94c2b-153">Gå till sidan Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="94c2b-153">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="94c2b-154">Se till att den anslutning som kallas *Dataverse (äldre)* finns.</span><span class="sxs-lookup"><span data-stu-id="94c2b-154">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="94c2b-155">(Om den inte finns skapar du den.)</span><span class="sxs-lookup"><span data-stu-id="94c2b-155">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="94c2b-156">Importera `Inventory Visibility Configuration Trigger.zip` filen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-156">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="94c2b-157">När den har importerats visas utlösaren under **Mina flöden**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-157">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="94c2b-158">Initialisera följande fyra variabler baserat på miljöinformation:</span><span class="sxs-lookup"><span data-stu-id="94c2b-158">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="94c2b-159">ID för Azure-innehavare</span><span class="sxs-lookup"><span data-stu-id="94c2b-159">Azure Tenant ID</span></span>
        - <span data-ttu-id="94c2b-160">Klient-ID för Azure-app</span><span class="sxs-lookup"><span data-stu-id="94c2b-160">Azure Application Client ID</span></span>
        - <span data-ttu-id="94c2b-161">Klienthemlighet för Azure-app</span><span class="sxs-lookup"><span data-stu-id="94c2b-161">Azure Application Client Secret</span></span>
        - <span data-ttu-id="94c2b-162">Slutpunkt för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-162">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="94c2b-163">Mer information om den här variabeln finns i avsnittet [Ställa in integration av lagersynlighet](#setup-inventory-visibility-integration) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-163">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="94c2b-164">![Konfigurationsutlösare](media/configuration-trigger.png "Konfigurationsutlösare")</span><span class="sxs-lookup"><span data-stu-id="94c2b-164">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="94c2b-165">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-165">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="94c2b-166">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="94c2b-166">Install the add-in</span></span>

<span data-ttu-id="94c2b-167">För att installera tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-167">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="94c2b-168">Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-168">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="94c2b-169">Välj det projekt där miljön har distribuerats på startsidan.</span><span class="sxs-lookup"><span data-stu-id="94c2b-169">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="94c2b-170">Välj den miljö där du vill installera tillägget på projektsidan.</span><span class="sxs-lookup"><span data-stu-id="94c2b-170">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="94c2b-171">Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform integration** där du hittar Dataverse miljönamnet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-171">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="94c2b-172">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-172">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="94c2b-173">![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")</span><span class="sxs-lookup"><span data-stu-id="94c2b-173">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="94c2b-174">Välj länken **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-174">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="94c2b-175">En lista med tillgängliga tillägg öppnas.</span><span class="sxs-lookup"><span data-stu-id="94c2b-175">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="94c2b-176">Välj **lagersynlighet** i listan.</span><span class="sxs-lookup"><span data-stu-id="94c2b-176">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="94c2b-177">Ange värden för följande fält i miljön:</span><span class="sxs-lookup"><span data-stu-id="94c2b-177">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="94c2b-178">**AAD-program-ID (klient)**</span><span class="sxs-lookup"><span data-stu-id="94c2b-178">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="94c2b-179">**AAD klientorganisationens ID**</span><span class="sxs-lookup"><span data-stu-id="94c2b-179">**AAD tenant ID**</span></span>

    <span data-ttu-id="94c2b-180">![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")</span><span class="sxs-lookup"><span data-stu-id="94c2b-180">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="94c2b-181">Godkänn villkoren genom att markera kryssrutan **villkor**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-181">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="94c2b-182">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-182">Select **Install**.</span></span> <span data-ttu-id="94c2b-183">Tilläggets status visas som **installerar**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-183">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="94c2b-184">När det är klart uppdaterar du sidan så att status ändras till **installerad**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-184">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="94c2b-185">Avinstallera tillägget</span><span class="sxs-lookup"><span data-stu-id="94c2b-185">Uninstall the add-in</span></span>

<span data-ttu-id="94c2b-186">För att avinstallera tillägget, välj **avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-186">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="94c2b-187">När du uppdaterar LCS tas tillägget för lagersynlighet bort.</span><span class="sxs-lookup"><span data-stu-id="94c2b-187">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="94c2b-188">Avinstallationsprocessen tar bort registreringen av tillägget och startar även ett jobb för att rensa alla affärsdata som lagras i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="94c2b-188">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="94c2b-189">Förbruka lagerbehållningsdata från Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="94c2b-189">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="94c2b-190">Distribuera integreringspaketet för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-190">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="94c2b-191">Om du kör Supply Chain Management version 10.0.17 eller tidigare, kontakta supportteamet för inventeringssyn på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få paketfilen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-191">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="94c2b-192">Distribuera sedan paketet i LCS.</span><span class="sxs-lookup"><span data-stu-id="94c2b-192">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="94c2b-193">Om ett versionsfel inträffar under distributionen måste du manuellt importera X++-projektet till din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="94c2b-193">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="94c2b-194">Skapa sedan det paket som kan distribueras i din utvecklingsmiljö och distribuera det i din produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="94c2b-194">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="94c2b-195">Koden ingår i med Supply Chain Management version 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="94c2b-195">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="94c2b-196">Om du kör den versionen eller senare behöver du inte distribuera den.</span><span class="sxs-lookup"><span data-stu-id="94c2b-196">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="94c2b-197">Kontrollera att följande funktioner är aktiverat i din Supply Chain Management-miljö.</span><span class="sxs-lookup"><span data-stu-id="94c2b-197">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="94c2b-198">(Som standard är de aktiverade.)</span><span class="sxs-lookup"><span data-stu-id="94c2b-198">(By default, they are turned on.)</span></span>

| <span data-ttu-id="94c2b-199">Funktionsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="94c2b-199">Feature description</span></span> | <span data-ttu-id="94c2b-200">Kodversion</span><span class="sxs-lookup"><span data-stu-id="94c2b-200">Code version</span></span> | <span data-ttu-id="94c2b-201">Växla klass</span><span class="sxs-lookup"><span data-stu-id="94c2b-201">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="94c2b-202">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSum</span><span class="sxs-lookup"><span data-stu-id="94c2b-202">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="94c2b-203">10.0.11</span><span class="sxs-lookup"><span data-stu-id="94c2b-203">10.0.11</span></span> | <span data-ttu-id="94c2b-204">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="94c2b-204">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="94c2b-205">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="94c2b-205">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="94c2b-206">10.0.12</span><span class="sxs-lookup"><span data-stu-id="94c2b-206">10.0.12</span></span> | <span data-ttu-id="94c2b-207">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="94c2b-207">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="94c2b-208">Konfigurera integrering av lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-208">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="94c2b-209">I Supply Chain Management, öppna arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen **Integrering av lagersynlighet**.</span><span class="sxs-lookup"><span data-stu-id="94c2b-209">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="94c2b-210">Gå till **Lagerhantering \> Ställ in \> Parametrar för integrering av lagersynlighet** och ange webbadressen till den miljö där du kör lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-210">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="94c2b-211">Sök efter din LCS-miljös Azure-region och ange sedan URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-211">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="94c2b-212">URL-adressen har följande formulär:</span><span class="sxs-lookup"><span data-stu-id="94c2b-212">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="94c2b-213">Om du till exempel är i Europa har din miljö någon av följande URL-adresser:</span><span class="sxs-lookup"><span data-stu-id="94c2b-213">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="94c2b-214">Följande regioner är för närvarande tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="94c2b-214">The following regions are currently available.</span></span>

    | <span data-ttu-id="94c2b-215">Azure-region</span><span class="sxs-lookup"><span data-stu-id="94c2b-215">Azure region</span></span> | <span data-ttu-id="94c2b-216">Kortnamn för region</span><span class="sxs-lookup"><span data-stu-id="94c2b-216">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="94c2b-217">Östra Australien</span><span class="sxs-lookup"><span data-stu-id="94c2b-217">Australia east</span></span> | <span data-ttu-id="94c2b-218">eau</span><span class="sxs-lookup"><span data-stu-id="94c2b-218">eau</span></span> |
    | <span data-ttu-id="94c2b-219">Sydöstra Australien</span><span class="sxs-lookup"><span data-stu-id="94c2b-219">Australia southeast</span></span> | <span data-ttu-id="94c2b-220">seau</span><span class="sxs-lookup"><span data-stu-id="94c2b-220">seau</span></span> |
    | <span data-ttu-id="94c2b-221">Centrala Kanada</span><span class="sxs-lookup"><span data-stu-id="94c2b-221">Canada central</span></span> | <span data-ttu-id="94c2b-222">cca</span><span class="sxs-lookup"><span data-stu-id="94c2b-222">cca</span></span> |
    | <span data-ttu-id="94c2b-223">Östra Kanada</span><span class="sxs-lookup"><span data-stu-id="94c2b-223">Canada east</span></span> | <span data-ttu-id="94c2b-224">eca</span><span class="sxs-lookup"><span data-stu-id="94c2b-224">eca</span></span> |
    | <span data-ttu-id="94c2b-225">Nordeuropa</span><span class="sxs-lookup"><span data-stu-id="94c2b-225">North Europe</span></span> | <span data-ttu-id="94c2b-226">neu</span><span class="sxs-lookup"><span data-stu-id="94c2b-226">neu</span></span> |
    | <span data-ttu-id="94c2b-227">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="94c2b-227">West Europe</span></span> | <span data-ttu-id="94c2b-228">weu</span><span class="sxs-lookup"><span data-stu-id="94c2b-228">weu</span></span> |
    | <span data-ttu-id="94c2b-229">Östra USA</span><span class="sxs-lookup"><span data-stu-id="94c2b-229">East US</span></span> | <span data-ttu-id="94c2b-230">eus</span><span class="sxs-lookup"><span data-stu-id="94c2b-230">eus</span></span> |
    | <span data-ttu-id="94c2b-231">Västra USA</span><span class="sxs-lookup"><span data-stu-id="94c2b-231">West US</span></span> | <span data-ttu-id="94c2b-232">wus</span><span class="sxs-lookup"><span data-stu-id="94c2b-232">wus</span></span> |

1. <span data-ttu-id="94c2b-233">Gå till **Lagerhantering \> Periodisk \> Integrering av lagerhantering** och aktivera jobbet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-233">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="94c2b-234">Alla lagerändringshändelser från Supply Chain Management bokförs nu i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-234">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="94c2b-235">Tillägg för lagersynlighet i offentlig API</span><span class="sxs-lookup"><span data-stu-id="94c2b-235">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="94c2b-236">Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-236">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="94c2b-237">Den stöder tre huvudinteraktionstyper:</span><span class="sxs-lookup"><span data-stu-id="94c2b-237">It supports three main interaction types:</span></span>

- <span data-ttu-id="94c2b-238">Bokföring av ändringar för lagerbehållning i tillägget från ett externt system</span><span class="sxs-lookup"><span data-stu-id="94c2b-238">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="94c2b-239">Fråga om aktuell behållning från ett externt system</span><span class="sxs-lookup"><span data-stu-id="94c2b-239">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="94c2b-240">Automatisk synkronisering med lagerbehållning av Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="94c2b-240">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="94c2b-241">Automatisk synkronisering av en del av den offentliga API:t.</span><span class="sxs-lookup"><span data-stu-id="94c2b-241">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="94c2b-242">I stället hanteras den i bakgrunden för miljöer där tillägget lagersynlighet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="94c2b-242">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="94c2b-243">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="94c2b-243">Authentication</span></span>

<span data-ttu-id="94c2b-244">Säkerhetstoken för plattform används för att anropa tillägget lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-244">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="94c2b-245">Därför måste du generera en *Azure Active Directory (Azure AD) token* med hjälp av ditt Azure AD program.</span><span class="sxs-lookup"><span data-stu-id="94c2b-245">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="94c2b-246">Du måste sedan använda Azure AD token för att få *åtkomsttoken* från säkerhetstjänsten.</span><span class="sxs-lookup"><span data-stu-id="94c2b-246">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="94c2b-247">Hämta en säkerhetstjänsttoken genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-247">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="94c2b-248">Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="94c2b-248">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="94c2b-249">Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="94c2b-249">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="94c2b-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="94c2b-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="94c2b-251">**Metod** - `GET`</span><span class="sxs-lookup"><span data-stu-id="94c2b-251">**Method** - `GET`</span></span>
    - <span data-ttu-id="94c2b-252">**Brödtext (formulärdata)**:</span><span class="sxs-lookup"><span data-stu-id="94c2b-252">**Body content (form data)**:</span></span>

        | <span data-ttu-id="94c2b-253">nyckel</span><span class="sxs-lookup"><span data-stu-id="94c2b-253">key</span></span> | <span data-ttu-id="94c2b-254">värde</span><span class="sxs-lookup"><span data-stu-id="94c2b-254">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="94c2b-255">klient-ID</span><span class="sxs-lookup"><span data-stu-id="94c2b-255">client_id</span></span> | <span data-ttu-id="94c2b-256">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="94c2b-256">${aadAppId}</span></span> |
        | <span data-ttu-id="94c2b-257">client_secret</span><span class="sxs-lookup"><span data-stu-id="94c2b-257">client_secret</span></span> | <span data-ttu-id="94c2b-258">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="94c2b-258">${aadAppSecret}</span></span> |
        | <span data-ttu-id="94c2b-259">grant_type</span><span class="sxs-lookup"><span data-stu-id="94c2b-259">grant_type</span></span> | <span data-ttu-id="94c2b-260">client_credentials</span><span class="sxs-lookup"><span data-stu-id="94c2b-260">client_credentials</span></span> |
        | <span data-ttu-id="94c2b-261">resurs</span><span class="sxs-lookup"><span data-stu-id="94c2b-261">resource</span></span> | <span data-ttu-id="94c2b-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="94c2b-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="94c2b-263">Du bör få `aadToken` i svar, som liknar följande exempel.</span><span class="sxs-lookup"><span data-stu-id="94c2b-263">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="94c2b-264">Formulera en JSON-begäran som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-264">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="94c2b-265">Där:</span><span class="sxs-lookup"><span data-stu-id="94c2b-265">Where:</span></span>
    - <span data-ttu-id="94c2b-266">Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="94c2b-266">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="94c2b-267">Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.</span><span class="sxs-lookup"><span data-stu-id="94c2b-267">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="94c2b-268">Ställ in alla andra värden enligt exemplet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-268">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="94c2b-269">Skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="94c2b-269">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="94c2b-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="94c2b-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="94c2b-271">**Metod** - `POST`</span><span class="sxs-lookup"><span data-stu-id="94c2b-271">**Method** - `POST`</span></span>
    - <span data-ttu-id="94c2b-272">**HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)</span><span class="sxs-lookup"><span data-stu-id="94c2b-272">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="94c2b-273">**Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="94c2b-273">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="94c2b-274">Du får ett `access_token` i svar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-274">You will get an `access_token` in response.</span></span> <span data-ttu-id="94c2b-275">Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-275">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="94c2b-276">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="94c2b-276">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="94c2b-277">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="94c2b-277">Sample Request</span></span>

<span data-ttu-id="94c2b-278">För din referens följer här ett exempel på en http-begäran- du kan använda valfritt verktyg eller kodspråk för att skicka denna, begäran, exempelvis ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="94c2b-278">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="94c2b-279">Konfigurera API för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-279">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="94c2b-280">Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="94c2b-280">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="94c2b-281">Konfigurationen kan variera beroende på vad som gäller för din miljö.</span><span class="sxs-lookup"><span data-stu-id="94c2b-281">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="94c2b-282">Den omfattar huvudsakligen fyra delar:</span><span class="sxs-lookup"><span data-stu-id="94c2b-282">It primarily includes four parts:</span></span>

- [<span data-ttu-id="94c2b-283">Partitionering</span><span class="sxs-lookup"><span data-stu-id="94c2b-283">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="94c2b-284">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="94c2b-284">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="94c2b-285">Indexering</span><span class="sxs-lookup"><span data-stu-id="94c2b-285">Indexing</span></span>](#indexing)
- [<span data-ttu-id="94c2b-286">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="94c2b-286">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="94c2b-287">Partitionering</span><span class="sxs-lookup"><span data-stu-id="94c2b-287">Partitioning</span></span>

<span data-ttu-id="94c2b-288">Partitionering kan i stor grad påverka prestandan för API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-288">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="94c2b-289">Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågeställningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-289">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="94c2b-290">`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*.</span><span class="sxs-lookup"><span data-stu-id="94c2b-290">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="94c2b-291">Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.</span><span class="sxs-lookup"><span data-stu-id="94c2b-291">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="94c2b-292">*Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-292">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="94c2b-293">I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="94c2b-293">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="94c2b-294">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="94c2b-294">Dimension configurations</span></span>

<span data-ttu-id="94c2b-295">Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.</span><span class="sxs-lookup"><span data-stu-id="94c2b-295">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="94c2b-296">I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-296">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="94c2b-297">Dimensionstyp</span><span class="sxs-lookup"><span data-stu-id="94c2b-297">Dimension type</span></span> | <span data-ttu-id="94c2b-298">Dimensionsnamn</span><span class="sxs-lookup"><span data-stu-id="94c2b-298">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="94c2b-299">Produkt</span><span class="sxs-lookup"><span data-stu-id="94c2b-299">Product</span></span> | `ColorId` |
| <span data-ttu-id="94c2b-300">Produkt</span><span class="sxs-lookup"><span data-stu-id="94c2b-300">Product</span></span> | `SizeId` |
| <span data-ttu-id="94c2b-301">Produkt</span><span class="sxs-lookup"><span data-stu-id="94c2b-301">Product</span></span> | `StyleId` |
| <span data-ttu-id="94c2b-302">Produkt</span><span class="sxs-lookup"><span data-stu-id="94c2b-302">Product</span></span> | `ConfigId` |
| <span data-ttu-id="94c2b-303">Spårning</span><span class="sxs-lookup"><span data-stu-id="94c2b-303">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="94c2b-304">Spårning</span><span class="sxs-lookup"><span data-stu-id="94c2b-304">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="94c2b-305">Plats</span><span class="sxs-lookup"><span data-stu-id="94c2b-305">Location</span></span> | `LocationId` |
| <span data-ttu-id="94c2b-306">Plats</span><span class="sxs-lookup"><span data-stu-id="94c2b-306">Location</span></span> | `SiteId` |
| <span data-ttu-id="94c2b-307">Lagerstatus</span><span class="sxs-lookup"><span data-stu-id="94c2b-307">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="94c2b-308">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="94c2b-308">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="94c2b-309">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="94c2b-309">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="94c2b-310">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="94c2b-310">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="94c2b-311">Dimensionstypen som visas i föregående tabell är endast referens.</span><span class="sxs-lookup"><span data-stu-id="94c2b-311">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="94c2b-312">Du behöver inte ange dimensionstypen i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-312">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="94c2b-313">Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-313">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="94c2b-314">Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-314">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="94c2b-315">Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-315">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="94c2b-316">Måldimensionerna måste vara en av följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-316">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="94c2b-317">Standarddimensioner vid lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="94c2b-317">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="94c2b-318">Anpassade dimensioner</span><span class="sxs-lookup"><span data-stu-id="94c2b-318">Custom dimensions</span></span>

<span data-ttu-id="94c2b-319">Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågeställningen på dimensioner och bokföringshändelsen med dimensioner.</span><span class="sxs-lookup"><span data-stu-id="94c2b-319">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="94c2b-320">Indexering</span><span class="sxs-lookup"><span data-stu-id="94c2b-320">Indexing</span></span>

<span data-ttu-id="94c2b-321">För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-321">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="94c2b-322">Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-322">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="94c2b-323">För närvarande kan du bara konfigurera index till maximalt fem.</span><span class="sxs-lookup"><span data-stu-id="94c2b-323">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="94c2b-324">Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="94c2b-324">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="94c2b-325">Om du till exempel vill söka efter produkter enligt följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-325">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="94c2b-326">Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.</span><span class="sxs-lookup"><span data-stu-id="94c2b-326">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="94c2b-327">I vissa fall vill du bara fråga den totala produkten.</span><span class="sxs-lookup"><span data-stu-id="94c2b-327">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="94c2b-328">Två index är definierade som följande:</span><span class="sxs-lookup"><span data-stu-id="94c2b-328">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="94c2b-329">Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-329">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="94c2b-330">Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning.</span><span class="sxs-lookup"><span data-stu-id="94c2b-330">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="94c2b-331">I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`.</span><span class="sxs-lookup"><span data-stu-id="94c2b-331">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="94c2b-332">Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-332">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="94c2b-333">Du kan ange frågevillkor i den begärandetext.</span><span class="sxs-lookup"><span data-stu-id="94c2b-333">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="94c2b-334">Här är en exempel fråga på produkten med kombinationen färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="94c2b-334">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="94c2b-335">För fältet `filters` stöder för närvarande bara `ProductId` flera värden.</span><span class="sxs-lookup"><span data-stu-id="94c2b-335">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="94c2b-336">Om matrisen `ProductId` är tom kommer alla produkter att efterfrågas.</span><span class="sxs-lookup"><span data-stu-id="94c2b-336">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="94c2b-337">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="94c2b-337">Custom measurement</span></span>

<span data-ttu-id="94c2b-338">Standardmåttkvantiteterna är kopplade till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="94c2b-338">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="94c2b-339">Det kan dock vara en bra kvantitet som består av en kombination av standardmåtten.</span><span class="sxs-lookup"><span data-stu-id="94c2b-339">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="94c2b-340">För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågeställningarna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-340">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="94c2b-341">Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-341">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="94c2b-342">Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-342">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="94c2b-343">Förbrukningssystem</span><span class="sxs-lookup"><span data-stu-id="94c2b-343">Consumption system</span></span> | <span data-ttu-id="94c2b-344">Beräknade mått</span><span class="sxs-lookup"><span data-stu-id="94c2b-344">Calculated measurers</span></span> | <span data-ttu-id="94c2b-345">Datakälla</span><span class="sxs-lookup"><span data-stu-id="94c2b-345">Data source</span></span> | <span data-ttu-id="94c2b-346">Modifierare</span><span class="sxs-lookup"><span data-stu-id="94c2b-346">Modifier</span></span> | <span data-ttu-id="94c2b-347">Beräkningstyp för modifierare</span><span class="sxs-lookup"><span data-stu-id="94c2b-347">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="94c2b-348">Tillägg</span><span class="sxs-lookup"><span data-stu-id="94c2b-348">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="94c2b-349">Tillägg</span><span class="sxs-lookup"><span data-stu-id="94c2b-349">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="94c2b-350">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="94c2b-350">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="94c2b-351">Tillägg</span><span class="sxs-lookup"><span data-stu-id="94c2b-351">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="94c2b-352">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="94c2b-352">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="94c2b-353">Tillägg</span><span class="sxs-lookup"><span data-stu-id="94c2b-353">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="94c2b-354">Tillägg</span><span class="sxs-lookup"><span data-stu-id="94c2b-354">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="94c2b-355">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="94c2b-355">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="94c2b-356">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="94c2b-356">Subtraction</span></span> |

<span data-ttu-id="94c2b-357">Med detta kommer frågeställningen för den anpassade måttkvantiteten att returnera följande resultat.</span><span class="sxs-lookup"><span data-stu-id="94c2b-357">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="94c2b-358">`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:</span><span class="sxs-lookup"><span data-stu-id="94c2b-358">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="94c2b-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="94c2b-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="94c2b-360">Bokföra lagerbehållningsändringar</span><span class="sxs-lookup"><span data-stu-id="94c2b-360">Posting on-hand changes</span></span>

<span data-ttu-id="94c2b-361">Den exakta URL som händelsen ska skickas till beror på din geografiska region.</span><span class="sxs-lookup"><span data-stu-id="94c2b-361">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="94c2b-362">Formuläret kommer att ha följande format:</span><span class="sxs-lookup"><span data-stu-id="94c2b-362">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="94c2b-363">När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="94c2b-363">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="94c2b-364">En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till.</span><span class="sxs-lookup"><span data-stu-id="94c2b-364">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="94c2b-365">Exempel:</span><span class="sxs-lookup"><span data-stu-id="94c2b-365">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="94c2b-366">Skicka behållningsändringar fråga exempel 1</span><span class="sxs-lookup"><span data-stu-id="94c2b-366">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="94c2b-367">I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="94c2b-367">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="94c2b-368">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="94c2b-368">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="94c2b-369">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-369">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="94c2b-370">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="94c2b-370">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="94c2b-371">Skicka behållningsändringar fråga exempel 2</span><span class="sxs-lookup"><span data-stu-id="94c2b-371">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="94c2b-372">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-372">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="94c2b-373">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="94c2b-373">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="94c2b-374">JSON dokumentfältegenskaper</span><span class="sxs-lookup"><span data-stu-id="94c2b-374">JSON document field properties</span></span>

<span data-ttu-id="94c2b-375">De fält från exempel för JSON-frågeställningar som tidigare har angetts har de egenskaper som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="94c2b-375">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="94c2b-376">Fält-ID</span><span class="sxs-lookup"><span data-stu-id="94c2b-376">Field ID</span></span> | <span data-ttu-id="94c2b-377">beskrivning</span><span class="sxs-lookup"><span data-stu-id="94c2b-377">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="94c2b-378">Ett unikt ID för den specifika ändringshändelsen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-378">A unique ID for the specific change event.</span></span> <span data-ttu-id="94c2b-379">Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-379">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="94c2b-380">Identifierare för den organisation som är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="94c2b-380">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="94c2b-381">Detta mappar till Supply Chain Management organisations eller dataområdes-ID.</span><span class="sxs-lookup"><span data-stu-id="94c2b-381">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="94c2b-382">Den unika identifieraren av produkten i fråga.</span><span class="sxs-lookup"><span data-stu-id="94c2b-382">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="94c2b-383">Kvantiteten som behållningen måste ändras med.</span><span class="sxs-lookup"><span data-stu-id="94c2b-383">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="94c2b-384">Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10.</span><span class="sxs-lookup"><span data-stu-id="94c2b-384">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="94c2b-385">Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3.</span><span class="sxs-lookup"><span data-stu-id="94c2b-385">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="94c2b-386">Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga.</span><span class="sxs-lookup"><span data-stu-id="94c2b-386">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="94c2b-387">Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan.</span><span class="sxs-lookup"><span data-stu-id="94c2b-387">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="94c2b-388">Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-388">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="94c2b-389">Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågeställningarna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-389">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="94c2b-390">En dynamisk uppsättning nyckel/värde-par.</span><span class="sxs-lookup"><span data-stu-id="94c2b-390">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="94c2b-391">Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system.</span><span class="sxs-lookup"><span data-stu-id="94c2b-391">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="94c2b-392">Fråga aktuell behållning</span><span class="sxs-lookup"><span data-stu-id="94c2b-392">Querying current on-hand</span></span>

<span data-ttu-id="94c2b-393">Slutpunkten för att hämta den aktuella behållningen har en liknande URL:</span><span class="sxs-lookup"><span data-stu-id="94c2b-393">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="94c2b-394">Den kommer att frågas med HTTP `POST`-metoden.</span><span class="sxs-lookup"><span data-stu-id="94c2b-394">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="94c2b-395">Aktuellt behållningsexempel 1</span><span class="sxs-lookup"><span data-stu-id="94c2b-395">Current on-hand query example 1</span></span>

<span data-ttu-id="94c2b-396">I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="94c2b-396">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="94c2b-397">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="94c2b-397">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="94c2b-398">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-398">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="94c2b-399">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="94c2b-399">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="94c2b-400">Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="94c2b-400">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="94c2b-401">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="94c2b-401">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="94c2b-402">Aktuellt behållningsexempel 2</span><span class="sxs-lookup"><span data-stu-id="94c2b-402">Current on-hand query example 2</span></span>

<span data-ttu-id="94c2b-403">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="94c2b-403">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="94c2b-404">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="94c2b-404">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="94c2b-405">Exempel på returresultat</span><span class="sxs-lookup"><span data-stu-id="94c2b-405">Example return result</span></span>

<span data-ttu-id="94c2b-406">Frågeställningarna som visas i föregående exempel kan returnera resultatet.</span><span class="sxs-lookup"><span data-stu-id="94c2b-406">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="94c2b-407">Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.</span><span class="sxs-lookup"><span data-stu-id="94c2b-407">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]