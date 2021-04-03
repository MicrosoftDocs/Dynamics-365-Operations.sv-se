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
ms.openlocfilehash: 4e588be2ac5aae395ca66e3c9a743a67d71db7c0
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574232"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="4e55e-103">Tillägg för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4e55e-104">Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="4e55e-105">All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="4e55e-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="4e55e-106">Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.</span><span class="sxs-lookup"><span data-stu-id="4e55e-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="4e55e-107">Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="4e55e-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="4e55e-108">Det går också att uppgradera indexet för att göra lagerfrågor.</span><span class="sxs-lookup"><span data-stu-id="4e55e-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="4e55e-109">Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare.</span><span class="sxs-lookup"><span data-stu-id="4e55e-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="4e55e-110">Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="4e55e-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="4e55e-111">I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).</span><span class="sxs-lookup"><span data-stu-id="4e55e-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="4e55e-112">Installera tillägget för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="4e55e-113">Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4e55e-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="4e55e-114">LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="4e55e-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="4e55e-115">Mer information finns i [Lifecycle Services, resurser](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="4e55e-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="4e55e-116">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4e55e-116">Prerequisites</span></span>

<span data-ttu-id="4e55e-117">Innan du installerar tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="4e55e-118">Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.</span><span class="sxs-lookup"><span data-stu-id="4e55e-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="4e55e-119">Se till att kraven för att ställa in tillägg som finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="4e55e-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="4e55e-120">Lagersynlighet kräver inte länkning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="4e55e-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="4e55e-121">Kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få följande tre filer:</span><span class="sxs-lookup"><span data-stu-id="4e55e-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>

    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="4e55e-122">`Inventory Visibility Integration.zip` (om versionen av Supply Chain Management som du kör är tidigare än version 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="4e55e-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>

> [!NOTE]
> <span data-ttu-id="4e55e-123">De länder och regioner som för närvarande stöds är Kanada, USA och Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="4e55e-123">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="4e55e-124">Om du har några frågor om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-124">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="4e55e-125">Ställ in Dataverse</span><span class="sxs-lookup"><span data-stu-id="4e55e-125">Set up Dataverse</span></span>

<span data-ttu-id="4e55e-126">Följ dessa steg för att konfigurera Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4e55e-126">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="4e55e-127">Lägg till en serviceprincip för din innehavare:</span><span class="sxs-lookup"><span data-stu-id="4e55e-127">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="4e55e-128">Installera Azure AD PowerShell modul v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="4e55e-128">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="4e55e-129">Kör följande PowerShell-kommando.</span><span class="sxs-lookup"><span data-stu-id="4e55e-129">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="4e55e-130">Skapa en programanvändare för lagersynlighet i Dataverse:</span><span class="sxs-lookup"><span data-stu-id="4e55e-130">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="4e55e-131">Öppna URL-adressen för din Dataverse miljö.</span><span class="sxs-lookup"><span data-stu-id="4e55e-131">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="4e55e-132">Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare.</span><span class="sxs-lookup"><span data-stu-id="4e55e-132">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="4e55e-133">Använd visningsmenyn för att ändra sidvisningen till **appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-133">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="4e55e-134">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-134">Select **New**.</span></span> <span data-ttu-id="4e55e-135">Ange app-ID till *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="4e55e-135">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="4e55e-136">(Objekt-ID:t läses in automatiskt när du sparar ändringarna.) Du kan anpassa namnet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-136">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="4e55e-137">Du kan till exempel ändra den till *Lagersynlighet*.</span><span class="sxs-lookup"><span data-stu-id="4e55e-137">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="4e55e-138">Välj **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4e55e-138">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="4e55e-139">Välj **Tilldela roll** och välj sedan **Systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-139">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="4e55e-140">Om det finns en roll med namnet **Common Data Service Användare** väljer du den också.</span><span class="sxs-lookup"><span data-stu-id="4e55e-140">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="4e55e-141">Mer information finns i [Skapa en appanvändare](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="4e55e-141">For more information, see [Create an application user](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="4e55e-142">Importera `Inventory Visibility Dataverse Solution.zip` filen, inklusive Dataverse konfigurationsrelaterade enheter och Power Apps:</span><span class="sxs-lookup"><span data-stu-id="4e55e-142">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="4e55e-143">Gå till sidan **Lösningar**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-143">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="4e55e-144">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-144">Select **Import**.</span></span>

1. <span data-ttu-id="4e55e-145">Importera flödet för flödesutlösaren för konfigurationsuppgradering:</span><span class="sxs-lookup"><span data-stu-id="4e55e-145">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="4e55e-146">Gå till sidan Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="4e55e-146">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="4e55e-147">Se till att den anslutning som kallas *Dataverse (äldre)* finns.</span><span class="sxs-lookup"><span data-stu-id="4e55e-147">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="4e55e-148">(Om den inte finns skapar du den.)</span><span class="sxs-lookup"><span data-stu-id="4e55e-148">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="4e55e-149">Importera `Inventory Visibility Configuration Trigger.zip` filen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-149">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="4e55e-150">När den har importerats visas utlösaren under **Mina flöden**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-150">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="4e55e-151">Initialisera följande fyra variabler baserat på miljöinformation:</span><span class="sxs-lookup"><span data-stu-id="4e55e-151">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="4e55e-152">ID för Azure-innehavare</span><span class="sxs-lookup"><span data-stu-id="4e55e-152">Azure Tenant ID</span></span>
        - <span data-ttu-id="4e55e-153">Klient-ID för Azure-app</span><span class="sxs-lookup"><span data-stu-id="4e55e-153">Azure Application Client ID</span></span>
        - <span data-ttu-id="4e55e-154">Klienthemlighet för Azure-app</span><span class="sxs-lookup"><span data-stu-id="4e55e-154">Azure Application Client Secret</span></span>
        - <span data-ttu-id="4e55e-155">Slutpunkt för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-155">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="4e55e-156">Mer information om den här variabeln finns i avsnittet [Ställa in integration av lagersynlighet](#setup-inventory-visibility-integration) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-156">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="4e55e-157">![Konfigurationsutlösare](media/configuration-trigger.png "Konfigurationsutlösare")</span><span class="sxs-lookup"><span data-stu-id="4e55e-157">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="4e55e-158">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-158">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="4e55e-159">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="4e55e-159">Install the add-in</span></span>

<span data-ttu-id="4e55e-160">För att installera tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-160">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="4e55e-161">Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-161">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="4e55e-162">Välj det projekt där miljön har distribuerats på startsidan.</span><span class="sxs-lookup"><span data-stu-id="4e55e-162">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="4e55e-163">Välj den miljö där du vill installera tillägget på projektsidan.</span><span class="sxs-lookup"><span data-stu-id="4e55e-163">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="4e55e-164">Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform integration** där du hittar Dataverse miljönamnet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-164">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="4e55e-165">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-165">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="4e55e-166">![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")</span><span class="sxs-lookup"><span data-stu-id="4e55e-166">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="4e55e-167">Välj länken **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-167">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="4e55e-168">En lista med tillgängliga tillägg öppnas.</span><span class="sxs-lookup"><span data-stu-id="4e55e-168">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="4e55e-169">Välj **lagersynlighet** i listan.</span><span class="sxs-lookup"><span data-stu-id="4e55e-169">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="4e55e-170">Ange värden för följande fält i miljön:</span><span class="sxs-lookup"><span data-stu-id="4e55e-170">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="4e55e-171">**AAD-program-ID (klient)**</span><span class="sxs-lookup"><span data-stu-id="4e55e-171">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="4e55e-172">**AAD klientorganisationens ID**</span><span class="sxs-lookup"><span data-stu-id="4e55e-172">**AAD tenant ID**</span></span>

    <span data-ttu-id="4e55e-173">![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")</span><span class="sxs-lookup"><span data-stu-id="4e55e-173">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="4e55e-174">Godkänn villkoren genom att markera kryssrutan **villkor**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-174">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="4e55e-175">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-175">Select **Install**.</span></span> <span data-ttu-id="4e55e-176">Tilläggets status visas som **installerar**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-176">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="4e55e-177">När det är klart uppdaterar du sidan så att status ändras till **installerad**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-177">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="4e55e-178">Avinstallera tillägget</span><span class="sxs-lookup"><span data-stu-id="4e55e-178">Uninstall the add-in</span></span>

<span data-ttu-id="4e55e-179">För att avinstallera tillägget, välj **avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-179">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="4e55e-180">När du uppdaterar LCS tas tillägget för lagersynlighet bort.</span><span class="sxs-lookup"><span data-stu-id="4e55e-180">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="4e55e-181">Avinstallationsprocessen tar bort registreringen av tillägget och startar även ett jobb för att rensa alla affärsdata som lagras i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4e55e-181">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="4e55e-182">Förbruka lagerbehållningsdata från Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4e55e-182">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="4e55e-183">Distribuera integreringspaketet för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-183">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="4e55e-184">Om du kör Supply Chain Management version 10.0.17 eller tidigare, kontakta supportteamet för inventeringssyn på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få paketfilen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-184">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="4e55e-185">Distribuera sedan paketet i LCS.</span><span class="sxs-lookup"><span data-stu-id="4e55e-185">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="4e55e-186">Om ett versionsfel inträffar under distributionen måste du manuellt importera X++-projektet till din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="4e55e-186">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="4e55e-187">Skapa sedan det paket som kan distribueras i din utvecklingsmiljö och distribuera det i din produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="4e55e-187">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="4e55e-188">Koden ingår i med Supply Chain Management version 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="4e55e-188">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="4e55e-189">Om du kör den versionen eller senare behöver du inte distribuera den.</span><span class="sxs-lookup"><span data-stu-id="4e55e-189">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="4e55e-190">Kontrollera att följande funktioner är aktiverat i din Supply Chain Management-miljö.</span><span class="sxs-lookup"><span data-stu-id="4e55e-190">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="4e55e-191">(Som standard är de aktiverade.)</span><span class="sxs-lookup"><span data-stu-id="4e55e-191">(By default, they are turned on.)</span></span>

| <span data-ttu-id="4e55e-192">Funktionsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="4e55e-192">Feature description</span></span> | <span data-ttu-id="4e55e-193">Kodversion</span><span class="sxs-lookup"><span data-stu-id="4e55e-193">Code version</span></span> | <span data-ttu-id="4e55e-194">Växla klass</span><span class="sxs-lookup"><span data-stu-id="4e55e-194">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="4e55e-195">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSum</span><span class="sxs-lookup"><span data-stu-id="4e55e-195">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="4e55e-196">10.0.11</span><span class="sxs-lookup"><span data-stu-id="4e55e-196">10.0.11</span></span> | <span data-ttu-id="4e55e-197">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="4e55e-197">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="4e55e-198">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="4e55e-198">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="4e55e-199">10.0.12</span><span class="sxs-lookup"><span data-stu-id="4e55e-199">10.0.12</span></span> | <span data-ttu-id="4e55e-200">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="4e55e-200">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="4e55e-201">Konfigurera integrering av lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-201">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="4e55e-202">I Supply Chain Management, öppna arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen **Integrering av lagersynlighet**.</span><span class="sxs-lookup"><span data-stu-id="4e55e-202">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="4e55e-203">Gå till **Lagerhantering \> Ställ in \> Parametrar för integrering av lagersynlighet** och ange webbadressen till den miljö där du kör lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-203">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="4e55e-204">Sök efter din LCS-miljös Azure-region och ange sedan URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-204">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="4e55e-205">URL-adressen har följande formulär:</span><span class="sxs-lookup"><span data-stu-id="4e55e-205">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="4e55e-206">Om du till exempel är i Europa har din miljö någon av följande URL-adresser:</span><span class="sxs-lookup"><span data-stu-id="4e55e-206">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com/`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="4e55e-207">Följande regioner är för närvarande tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="4e55e-207">The following regions are currently available.</span></span>

    | <span data-ttu-id="4e55e-208">Azure-region</span><span class="sxs-lookup"><span data-stu-id="4e55e-208">Azure region</span></span> | <span data-ttu-id="4e55e-209">Kortnamn för region</span><span class="sxs-lookup"><span data-stu-id="4e55e-209">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="4e55e-210">Östra Australien</span><span class="sxs-lookup"><span data-stu-id="4e55e-210">Australia east</span></span> | <span data-ttu-id="4e55e-211">eau</span><span class="sxs-lookup"><span data-stu-id="4e55e-211">eau</span></span> |
    | <span data-ttu-id="4e55e-212">Sydöstra Australien</span><span class="sxs-lookup"><span data-stu-id="4e55e-212">Australia southeast</span></span> | <span data-ttu-id="4e55e-213">seau</span><span class="sxs-lookup"><span data-stu-id="4e55e-213">seau</span></span> |
    | <span data-ttu-id="4e55e-214">Centrala Kanada</span><span class="sxs-lookup"><span data-stu-id="4e55e-214">Canada central</span></span> | <span data-ttu-id="4e55e-215">cca</span><span class="sxs-lookup"><span data-stu-id="4e55e-215">cca</span></span> |
    | <span data-ttu-id="4e55e-216">Östra Kanada</span><span class="sxs-lookup"><span data-stu-id="4e55e-216">Canada east</span></span> | <span data-ttu-id="4e55e-217">eca</span><span class="sxs-lookup"><span data-stu-id="4e55e-217">eca</span></span> |
    | <span data-ttu-id="4e55e-218">Nordeuropa</span><span class="sxs-lookup"><span data-stu-id="4e55e-218">North Europe</span></span> | <span data-ttu-id="4e55e-219">neu</span><span class="sxs-lookup"><span data-stu-id="4e55e-219">neu</span></span> |
    | <span data-ttu-id="4e55e-220">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="4e55e-220">West Europe</span></span> | <span data-ttu-id="4e55e-221">weu</span><span class="sxs-lookup"><span data-stu-id="4e55e-221">weu</span></span> |
    | <span data-ttu-id="4e55e-222">Östra USA</span><span class="sxs-lookup"><span data-stu-id="4e55e-222">East US</span></span> | <span data-ttu-id="4e55e-223">eus</span><span class="sxs-lookup"><span data-stu-id="4e55e-223">eus</span></span> |
    | <span data-ttu-id="4e55e-224">Västra USA</span><span class="sxs-lookup"><span data-stu-id="4e55e-224">West US</span></span> | <span data-ttu-id="4e55e-225">wus</span><span class="sxs-lookup"><span data-stu-id="4e55e-225">wus</span></span> |

1. <span data-ttu-id="4e55e-226">Gå till **Lagerhantering \> Periodisk \> Integrering av lagerhantering** och aktivera jobbet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-226">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="4e55e-227">Alla lagerändringshändelser från Supply Chain Management bokförs nu i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-227">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="4e55e-228">Tillägg för lagersynlighet i offentlig API</span><span class="sxs-lookup"><span data-stu-id="4e55e-228">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="4e55e-229">Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-229">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="4e55e-230">Den stöder tre huvudinteraktionstyper:</span><span class="sxs-lookup"><span data-stu-id="4e55e-230">It supports three main interaction types:</span></span>

- <span data-ttu-id="4e55e-231">Bokföring av ändringar för lagerbehållning i tillägget från ett externt system</span><span class="sxs-lookup"><span data-stu-id="4e55e-231">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="4e55e-232">Fråga om aktuell behållning från ett externt system</span><span class="sxs-lookup"><span data-stu-id="4e55e-232">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="4e55e-233">Automatisk synkronisering med lagerbehållning av Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4e55e-233">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="4e55e-234">Automatisk synkronisering av en del av den offentliga API:t.</span><span class="sxs-lookup"><span data-stu-id="4e55e-234">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="4e55e-235">I stället hanteras den i bakgrunden för miljöer där tillägget lagersynlighet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="4e55e-235">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="4e55e-236">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="4e55e-236">Authentication</span></span>

<span data-ttu-id="4e55e-237">Säkerhetstoken för plattform används för att anropa tillägget lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-237">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="4e55e-238">Därför måste du generera en *Azure Active Directory (Azure AD) token* med hjälp av ditt Azure AD program.</span><span class="sxs-lookup"><span data-stu-id="4e55e-238">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="4e55e-239">Du måste sedan använda Azure AD token för att få *åtkomsttoken* från säkerhetstjänsten.</span><span class="sxs-lookup"><span data-stu-id="4e55e-239">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="4e55e-240">Hämta en säkerhetstjänsttoken genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-240">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="4e55e-241">Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="4e55e-241">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="4e55e-242">Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="4e55e-242">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="4e55e-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="4e55e-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="4e55e-244">**Metod** - `GET`</span><span class="sxs-lookup"><span data-stu-id="4e55e-244">**Method** - `GET`</span></span>
    - <span data-ttu-id="4e55e-245">**Brödtext (formulärdata)**:</span><span class="sxs-lookup"><span data-stu-id="4e55e-245">**Body content (form data)**:</span></span>

        | <span data-ttu-id="4e55e-246">nyckel</span><span class="sxs-lookup"><span data-stu-id="4e55e-246">key</span></span> | <span data-ttu-id="4e55e-247">värde</span><span class="sxs-lookup"><span data-stu-id="4e55e-247">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="4e55e-248">klient-ID</span><span class="sxs-lookup"><span data-stu-id="4e55e-248">client_id</span></span> | <span data-ttu-id="4e55e-249">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="4e55e-249">${aadAppId}</span></span> |
        | <span data-ttu-id="4e55e-250">client_secret</span><span class="sxs-lookup"><span data-stu-id="4e55e-250">client_secret</span></span> | <span data-ttu-id="4e55e-251">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="4e55e-251">${aadAppSecret}</span></span> |
        | <span data-ttu-id="4e55e-252">grant_type</span><span class="sxs-lookup"><span data-stu-id="4e55e-252">grant_type</span></span> | <span data-ttu-id="4e55e-253">client_credentials</span><span class="sxs-lookup"><span data-stu-id="4e55e-253">client_credentials</span></span> |
        | <span data-ttu-id="4e55e-254">resurs</span><span class="sxs-lookup"><span data-stu-id="4e55e-254">resource</span></span> | <span data-ttu-id="4e55e-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="4e55e-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="4e55e-256">Du bör få `aadToken` i svar, som liknar följande exempel.</span><span class="sxs-lookup"><span data-stu-id="4e55e-256">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="4e55e-257">Formulera en JSON-begäran som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-257">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="4e55e-258">Där:</span><span class="sxs-lookup"><span data-stu-id="4e55e-258">Where:</span></span>
    - <span data-ttu-id="4e55e-259">Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="4e55e-259">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="4e55e-260">Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.</span><span class="sxs-lookup"><span data-stu-id="4e55e-260">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="4e55e-261">Ställ in alla andra värden enligt exemplet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-261">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="4e55e-262">Skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="4e55e-262">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="4e55e-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="4e55e-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="4e55e-264">**Metod** - `POST`</span><span class="sxs-lookup"><span data-stu-id="4e55e-264">**Method** - `POST`</span></span>
    - <span data-ttu-id="4e55e-265">**HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)</span><span class="sxs-lookup"><span data-stu-id="4e55e-265">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="4e55e-266">**Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="4e55e-266">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="4e55e-267">Du får ett `access_token` i svar.</span><span class="sxs-lookup"><span data-stu-id="4e55e-267">You will get an `access_token` in response.</span></span> <span data-ttu-id="4e55e-268">Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-268">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="4e55e-269">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="4e55e-269">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="4e55e-270">Konfigurera API för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-270">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="4e55e-271">Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="4e55e-271">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="4e55e-272">Konfigurationen kan variera beroende på vad som gäller för din miljö.</span><span class="sxs-lookup"><span data-stu-id="4e55e-272">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="4e55e-273">Den omfattar huvudsakligen fyra delar:</span><span class="sxs-lookup"><span data-stu-id="4e55e-273">It primarily includes four parts:</span></span>

- [<span data-ttu-id="4e55e-274">Partitionering</span><span class="sxs-lookup"><span data-stu-id="4e55e-274">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="4e55e-275">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="4e55e-275">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="4e55e-276">Indexering</span><span class="sxs-lookup"><span data-stu-id="4e55e-276">Indexing</span></span>](#indexing)
- [<span data-ttu-id="4e55e-277">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="4e55e-277">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="4e55e-278">Partitionering</span><span class="sxs-lookup"><span data-stu-id="4e55e-278">Partitioning</span></span>

<span data-ttu-id="4e55e-279">Partitionering kan i stor grad påverka prestandan för API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-279">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="4e55e-280">Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågor.</span><span class="sxs-lookup"><span data-stu-id="4e55e-280">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="4e55e-281">`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*.</span><span class="sxs-lookup"><span data-stu-id="4e55e-281">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="4e55e-282">Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.</span><span class="sxs-lookup"><span data-stu-id="4e55e-282">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="4e55e-283">*Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-283">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="4e55e-284">I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="4e55e-284">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="4e55e-285">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="4e55e-285">Dimension configurations</span></span>

<span data-ttu-id="4e55e-286">Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.</span><span class="sxs-lookup"><span data-stu-id="4e55e-286">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="4e55e-287">I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-287">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="4e55e-288">Dimensionstyp</span><span class="sxs-lookup"><span data-stu-id="4e55e-288">Dimension type</span></span> | <span data-ttu-id="4e55e-289">Dimensionsnamn</span><span class="sxs-lookup"><span data-stu-id="4e55e-289">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="4e55e-290">Produkt</span><span class="sxs-lookup"><span data-stu-id="4e55e-290">Product</span></span> | `ColorId` |
| <span data-ttu-id="4e55e-291">Produkt</span><span class="sxs-lookup"><span data-stu-id="4e55e-291">Product</span></span> | `SizeId` |
| <span data-ttu-id="4e55e-292">Produkt</span><span class="sxs-lookup"><span data-stu-id="4e55e-292">Product</span></span> | `StyleId` |
| <span data-ttu-id="4e55e-293">Produkt</span><span class="sxs-lookup"><span data-stu-id="4e55e-293">Product</span></span> | `ConfigId` |
| <span data-ttu-id="4e55e-294">Spårning</span><span class="sxs-lookup"><span data-stu-id="4e55e-294">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="4e55e-295">Spårning</span><span class="sxs-lookup"><span data-stu-id="4e55e-295">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="4e55e-296">Plats</span><span class="sxs-lookup"><span data-stu-id="4e55e-296">Location</span></span> | `LocationId` |
| <span data-ttu-id="4e55e-297">Plats</span><span class="sxs-lookup"><span data-stu-id="4e55e-297">Location</span></span> | `SiteId` |
| <span data-ttu-id="4e55e-298">Lagerstatus</span><span class="sxs-lookup"><span data-stu-id="4e55e-298">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="4e55e-299">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="4e55e-299">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="4e55e-300">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="4e55e-300">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="4e55e-301">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="4e55e-301">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="4e55e-302">Dimensionstypen som visas i föregående tabell är endast referens.</span><span class="sxs-lookup"><span data-stu-id="4e55e-302">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="4e55e-303">Du behöver inte ange dimensionstypen i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-303">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="4e55e-304">Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-304">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="4e55e-305">Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="4e55e-305">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="4e55e-306">Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-306">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="4e55e-307">Måldimensionerna måste vara en av följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-307">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="4e55e-308">Standarddimensioner vid lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="4e55e-308">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="4e55e-309">Anpassade dimensioner</span><span class="sxs-lookup"><span data-stu-id="4e55e-309">Custom dimensions</span></span>

<span data-ttu-id="4e55e-310">Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågan på dimensioner och bokföringshändelsen med dimensioner.</span><span class="sxs-lookup"><span data-stu-id="4e55e-310">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="4e55e-311">Indexering</span><span class="sxs-lookup"><span data-stu-id="4e55e-311">Indexing</span></span>

<span data-ttu-id="4e55e-312">För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-312">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="4e55e-313">Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-313">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="4e55e-314">För närvarande kan du bara konfigurera index till maximalt fem.</span><span class="sxs-lookup"><span data-stu-id="4e55e-314">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="4e55e-315">Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="4e55e-315">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="4e55e-316">Om du till exempel vill söka efter produkter enligt följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-316">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="4e55e-317">Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.</span><span class="sxs-lookup"><span data-stu-id="4e55e-317">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="4e55e-318">I vissa fall vill du bara fråga den totala produkten.</span><span class="sxs-lookup"><span data-stu-id="4e55e-318">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="4e55e-319">Två index är definierade som följande:</span><span class="sxs-lookup"><span data-stu-id="4e55e-319">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="4e55e-320">Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-320">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="4e55e-321">Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning.</span><span class="sxs-lookup"><span data-stu-id="4e55e-321">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="4e55e-322">I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`.</span><span class="sxs-lookup"><span data-stu-id="4e55e-322">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="4e55e-323">Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-323">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="4e55e-324">Du kan ange frågevillkor i den begärandetext.</span><span class="sxs-lookup"><span data-stu-id="4e55e-324">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="4e55e-325">Här är en exempel fråga på produkten med kombinationen färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="4e55e-325">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="4e55e-326">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="4e55e-326">Custom measurement</span></span>

<span data-ttu-id="4e55e-327">Standardmåttkvantiteterna är kopplade till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4e55e-327">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="4e55e-328">Det kan dock vara en bra kvantitet som består av en kombination av standardmåtten.</span><span class="sxs-lookup"><span data-stu-id="4e55e-328">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="4e55e-329">För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågorna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-329">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="4e55e-330">Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-330">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="4e55e-331">Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-331">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="4e55e-332">Förbrukningssystem</span><span class="sxs-lookup"><span data-stu-id="4e55e-332">Consumption system</span></span> | <span data-ttu-id="4e55e-333">Beräknade mått</span><span class="sxs-lookup"><span data-stu-id="4e55e-333">Calculated measurers</span></span> | <span data-ttu-id="4e55e-334">Datakälla</span><span class="sxs-lookup"><span data-stu-id="4e55e-334">Data source</span></span> | <span data-ttu-id="4e55e-335">Modifierare</span><span class="sxs-lookup"><span data-stu-id="4e55e-335">Modifier</span></span> | <span data-ttu-id="4e55e-336">Beräkningstyp för modifierare</span><span class="sxs-lookup"><span data-stu-id="4e55e-336">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="4e55e-337">Tillägg</span><span class="sxs-lookup"><span data-stu-id="4e55e-337">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="4e55e-338">Tillägg</span><span class="sxs-lookup"><span data-stu-id="4e55e-338">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="4e55e-339">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="4e55e-339">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="4e55e-340">Tillägg</span><span class="sxs-lookup"><span data-stu-id="4e55e-340">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="4e55e-341">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="4e55e-341">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="4e55e-342">Tillägg</span><span class="sxs-lookup"><span data-stu-id="4e55e-342">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="4e55e-343">Tillägg</span><span class="sxs-lookup"><span data-stu-id="4e55e-343">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="4e55e-344">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="4e55e-344">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="4e55e-345">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="4e55e-345">Subtraction</span></span> |

<span data-ttu-id="4e55e-346">Med detta kommer frågan för den anpassade måttkvantiteten att returnera följande resultat.</span><span class="sxs-lookup"><span data-stu-id="4e55e-346">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="4e55e-347">`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:</span><span class="sxs-lookup"><span data-stu-id="4e55e-347">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="4e55e-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="4e55e-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="4e55e-349">Bokföra lagerbehållningsändringar</span><span class="sxs-lookup"><span data-stu-id="4e55e-349">Posting on-hand changes</span></span>

<span data-ttu-id="4e55e-350">Den exakta URL som händelsen ska skickas till beror på din geografiska region.</span><span class="sxs-lookup"><span data-stu-id="4e55e-350">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="4e55e-351">Formuläret kommer att ha följande format:</span><span class="sxs-lookup"><span data-stu-id="4e55e-351">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="4e55e-352">När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4e55e-352">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="4e55e-353">En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till.</span><span class="sxs-lookup"><span data-stu-id="4e55e-353">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="4e55e-354">Exempel:</span><span class="sxs-lookup"><span data-stu-id="4e55e-354">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="4e55e-355">Skicka behållningsändringar fråga exempel 1</span><span class="sxs-lookup"><span data-stu-id="4e55e-355">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="4e55e-356">I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="4e55e-356">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="4e55e-357">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="4e55e-357">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="4e55e-358">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor.</span><span class="sxs-lookup"><span data-stu-id="4e55e-358">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="4e55e-359">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="4e55e-359">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="4e55e-360">Skicka behållningsändringar fråga exempel 2</span><span class="sxs-lookup"><span data-stu-id="4e55e-360">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="4e55e-361">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-361">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="4e55e-362">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="4e55e-362">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="4e55e-363">JSON dokumentfältegenskaper</span><span class="sxs-lookup"><span data-stu-id="4e55e-363">JSON document field properties</span></span>

<span data-ttu-id="4e55e-364">De fält från exempel för JSON-frågor som tidigare har angetts har de egenskaper som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="4e55e-364">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="4e55e-365">Fält-ID</span><span class="sxs-lookup"><span data-stu-id="4e55e-365">Field ID</span></span> | <span data-ttu-id="4e55e-366">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4e55e-366">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="4e55e-367">Ett unikt ID för den specifika ändringshändelsen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-367">A unique ID for the specific change event.</span></span> <span data-ttu-id="4e55e-368">Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-368">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="4e55e-369">Identifierare för den organisation som är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="4e55e-369">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="4e55e-370">Detta mappar till Supply Chain Management organisations eller dataområdes-ID.</span><span class="sxs-lookup"><span data-stu-id="4e55e-370">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="4e55e-371">Den unika identifieraren av produkten i fråga.</span><span class="sxs-lookup"><span data-stu-id="4e55e-371">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="4e55e-372">Kvantiteten som behållningen måste ändras med.</span><span class="sxs-lookup"><span data-stu-id="4e55e-372">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="4e55e-373">Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10.</span><span class="sxs-lookup"><span data-stu-id="4e55e-373">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="4e55e-374">Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3.</span><span class="sxs-lookup"><span data-stu-id="4e55e-374">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="4e55e-375">Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga.</span><span class="sxs-lookup"><span data-stu-id="4e55e-375">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="4e55e-376">Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan.</span><span class="sxs-lookup"><span data-stu-id="4e55e-376">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="4e55e-377">Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-377">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="4e55e-378">Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågorna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-378">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="4e55e-379">En dynamisk uppsättning nyckel/värde-par.</span><span class="sxs-lookup"><span data-stu-id="4e55e-379">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="4e55e-380">Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system.</span><span class="sxs-lookup"><span data-stu-id="4e55e-380">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="4e55e-381">Fråga aktuell behållning</span><span class="sxs-lookup"><span data-stu-id="4e55e-381">Querying current on-hand</span></span>

<span data-ttu-id="4e55e-382">Slutpunkten för att hämta den aktuella behållningen har en liknande URL:</span><span class="sxs-lookup"><span data-stu-id="4e55e-382">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="4e55e-383">Den kommer att frågas med HTTP `POST`-metoden.</span><span class="sxs-lookup"><span data-stu-id="4e55e-383">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="4e55e-384">Aktuellt behållningsexempel 1</span><span class="sxs-lookup"><span data-stu-id="4e55e-384">Current on-hand query example 1</span></span>

<span data-ttu-id="4e55e-385">I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="4e55e-385">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="4e55e-386">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="4e55e-386">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="4e55e-387">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågor.</span><span class="sxs-lookup"><span data-stu-id="4e55e-387">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="4e55e-388">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="4e55e-388">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="4e55e-389">Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="4e55e-389">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="4e55e-390">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="4e55e-390">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="4e55e-391">Aktuellt behållningsexempel 2</span><span class="sxs-lookup"><span data-stu-id="4e55e-391">Current on-hand query example 2</span></span>

<span data-ttu-id="4e55e-392">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="4e55e-392">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="4e55e-393">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="4e55e-393">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="4e55e-394">Exempel på returresultat</span><span class="sxs-lookup"><span data-stu-id="4e55e-394">Example return result</span></span>

<span data-ttu-id="4e55e-395">Frågorna som visas i föregående exempel kan returnera resultatet.</span><span class="sxs-lookup"><span data-stu-id="4e55e-395">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="4e55e-396">Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.</span><span class="sxs-lookup"><span data-stu-id="4e55e-396">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
