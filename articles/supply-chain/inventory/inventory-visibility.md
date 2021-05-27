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
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017016"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="17ccc-103">Tillägg för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="17ccc-104">Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="17ccc-105">All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå.</span><span class="sxs-lookup"><span data-stu-id="17ccc-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="17ccc-106">Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="17ccc-107">Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="17ccc-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="17ccc-108">Det går också att uppgradera indexet för att göra lagerfrågeställningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="17ccc-109">Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare.</span><span class="sxs-lookup"><span data-stu-id="17ccc-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="17ccc-110">Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.</span><span class="sxs-lookup"><span data-stu-id="17ccc-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="17ccc-111">I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).</span><span class="sxs-lookup"><span data-stu-id="17ccc-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="17ccc-112">Installera tillägget för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="17ccc-113">Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="17ccc-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="17ccc-114">LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="17ccc-115">Mer information finns i [Lifecycle Services, resurser](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="17ccc-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="17ccc-116">Förutsättningar för tillägg för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="17ccc-117">Innan du installerar tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="17ccc-118">Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.</span><span class="sxs-lookup"><span data-stu-id="17ccc-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="17ccc-119">Se till att kraven för att ställa in tillägg som finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="17ccc-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="17ccc-120">Lagersynlighet kräver inte länkning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="17ccc-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="17ccc-121">Kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få följande tre filer:</span><span class="sxs-lookup"><span data-stu-id="17ccc-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="17ccc-122">`Inventory Visibility Integration.zip` (om versionen av Supply Chain Management som du kör är tidigare än version 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="17ccc-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="17ccc-123">Alternativt kan du kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få Package Deployer-paketen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="17ccc-124">Dessa paket kan användas av ett officiellt Package Deployer-verktyg.</span><span class="sxs-lookup"><span data-stu-id="17ccc-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="17ccc-125">`InventoryServiceApplication.PackageDeployer.zip`(det här paketet innehåller alla ändringar i paketet `InventoryServiceBase`, plus ytterligare programkomponenter för användargränssnittet)</span><span class="sxs-lookup"><span data-stu-id="17ccc-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="17ccc-126">Följ instruktionerna i [Snabbstart: Registrera ett program med Microsofts identitetsplattform](/azure/active-directory/develop/quickstart-register-app) om du vill registrera ett program och lägga till en klienthemlighet i AAD i samband med din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="17ccc-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="17ccc-127">Registrera ett program</span><span class="sxs-lookup"><span data-stu-id="17ccc-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="17ccc-128">Lägg till en klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="17ccc-129">I följande steg används **ID för program (klient)**, **Klienthemlighet** samt **ID för klientorganisation**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="17ccc-130">De länder och regioner som för närvarande stöds är Kanada, USA och Europeiska unionen (EU).</span><span class="sxs-lookup"><span data-stu-id="17ccc-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="17ccc-131">Om du har några frågeställningar om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="17ccc-132">Ställ in Dataverse</span><span class="sxs-lookup"><span data-stu-id="17ccc-132">Set up Dataverse</span></span>

<span data-ttu-id="17ccc-133">Om du vill konfigurera Dataverse för användning med Lagersynlighet måste du först förbereda förutsättningarna och sedan bestämma om du vill konfigurera Dataverse med antingen Package Deployer-verktyget eller genom att importera lösningarna manuellt (du behöver inte göra båda).</span><span class="sxs-lookup"><span data-stu-id="17ccc-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="17ccc-134">Installera sedan tillägget för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="17ccc-135">Följande delgrupper beskriver hur du slutför varje uppgift.</span><span class="sxs-lookup"><span data-stu-id="17ccc-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="17ccc-136">Förbered Dataverse-förutsättningar</span><span class="sxs-lookup"><span data-stu-id="17ccc-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="17ccc-137">Innan du börjar konfigurera Dataverse lägger du till en tjänstprincip i din klientorganisation genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="17ccc-138">Installera Azure AD PowerShell modul v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="17ccc-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="17ccc-139">Kör följande PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="17ccc-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="17ccc-140">Konfigurera Dataverse med hjälp av Package Deployer-verktyget</span><span class="sxs-lookup"><span data-stu-id="17ccc-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="17ccc-141">När du har ställt in förutsättningarna använder du följande procedur om du föredrar att konfigurera Dataverse med hjälp av Package Deployer-verktyget.</span><span class="sxs-lookup"><span data-stu-id="17ccc-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="17ccc-142">Se nästa avsnitt för information om hur du importerar lösningarna manuellt istället (gör inte båda).</span><span class="sxs-lookup"><span data-stu-id="17ccc-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="17ccc-143">Installera utvecklarverktyg enligt beskrivningen i [Hämta verktyg från NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="17ccc-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="17ccc-144">Baserat på dina affärsförutsättningar väljer du `InventoryServiceBase`- eller `InventoryServiceApplication`-paketet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="17ccc-145">Importera lösningarna:</span><span class="sxs-lookup"><span data-stu-id="17ccc-145">Import the solutions:</span></span>
    1. <span data-ttu-id="17ccc-146">För `InventoryServiceBase`-paketet:</span><span class="sxs-lookup"><span data-stu-id="17ccc-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="17ccc-147">Packa upp `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="17ccc-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="17ccc-148">Sök efter mappen `InventoryServiceBase`, filen `[Content_Types].xml`, filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` och filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="17ccc-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="17ccc-149">Kopiera var och en av dessa mappar och filer till katalogen `.\Tools\PackageDeployment`, som skapades när du installerade utvecklarverktygen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="17ccc-150">För `InventoryServiceApplication`-paketet:</span><span class="sxs-lookup"><span data-stu-id="17ccc-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="17ccc-151">Packa upp `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="17ccc-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="17ccc-152">Sök efter mappen `InventoryServiceApplication`, filen `[Content_Types].xml`, filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` och filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="17ccc-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="17ccc-153">Kopiera var och en av dessa mappar och filer till katalogen `.\Tools\PackageDeployment`, som skapades när du installerade utvecklarverktygen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="17ccc-154">Kör `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="17ccc-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="17ccc-155">Importera lösningarna genom att följa anvisningarna på skärmen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="17ccc-156">Tilldela programanvändaren säkerhetsroller.</span><span class="sxs-lookup"><span data-stu-id="17ccc-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="17ccc-157">Öppna URL-adressen för din Dataverse miljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="17ccc-158">Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och hitta användaren med namnet **# InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="17ccc-159">Välj **Tilldela roll** och välj sedan **Systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="17ccc-160">Om det finns en roll med namnet **Common Data Service-användare** väljer du den också.</span><span class="sxs-lookup"><span data-stu-id="17ccc-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="17ccc-161">Konfigurera Dataverse manuellt genom att importera lösningar</span><span class="sxs-lookup"><span data-stu-id="17ccc-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="17ccc-162">När du har ställt in förutsättningarna använder du följande procedur om du föredrar att konfigurera Dataverse manuellt genom att importera lösningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="17ccc-163">Se föregående avsnitt för information om hur du använder Package Deployer-verktyget i stället (gör inte båda).</span><span class="sxs-lookup"><span data-stu-id="17ccc-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="17ccc-164">Skapa en programanvändare för lagersynlighet i Dataverse:</span><span class="sxs-lookup"><span data-stu-id="17ccc-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="17ccc-165">Öppna URL-adressen för din Dataverse miljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="17ccc-166">Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare.</span><span class="sxs-lookup"><span data-stu-id="17ccc-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="17ccc-167">Använd visningsmenyn för att ändra sidvisningen till **appanvändare**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="17ccc-168">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-168">Select **New**.</span></span> <span data-ttu-id="17ccc-169">Ange app-ID till *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="17ccc-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="17ccc-170">(Objekt-ID:t läses in automatiskt när du sparar ändringarna.) Du kan anpassa namnet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="17ccc-171">Du kan till exempel ändra den till *Lagersynlighet*.</span><span class="sxs-lookup"><span data-stu-id="17ccc-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="17ccc-172">Välj **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="17ccc-173">Välj **Tilldela roll** och välj sedan **Systemadministratör**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="17ccc-174">Om det finns en roll med namnet **Common Data Service Användare** väljer du den också.</span><span class="sxs-lookup"><span data-stu-id="17ccc-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="17ccc-175">Mer information finns i [Skapa en appanvändare](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="17ccc-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="17ccc-176">Om standardspråket för ditt Dataverse inte är **Engelska**:</span><span class="sxs-lookup"><span data-stu-id="17ccc-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="17ccc-177">Gå till **Avancerad inställning \> Administration \> Språk**,</span><span class="sxs-lookup"><span data-stu-id="17ccc-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="17ccc-178">Välj **Engelska (LanguageCode=1033)** och sedan **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="17ccc-179">Importera `Inventory Visibility Dataverse Solution.zip` filen, inklusive Dataverse konfigurationsrelaterade enheter och Power Apps:</span><span class="sxs-lookup"><span data-stu-id="17ccc-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="17ccc-180">Gå till sidan **Lösningar**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="17ccc-181">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-181">Select **Import**.</span></span>

1. <span data-ttu-id="17ccc-182">Importera flödet för flödesutlösaren för konfigurationsuppgradering:</span><span class="sxs-lookup"><span data-stu-id="17ccc-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="17ccc-183">Gå till sidan Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="17ccc-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="17ccc-184">Se till att den anslutning som kallas *Dataverse (äldre)* finns.</span><span class="sxs-lookup"><span data-stu-id="17ccc-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="17ccc-185">(Om den inte finns skapar du den.)</span><span class="sxs-lookup"><span data-stu-id="17ccc-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="17ccc-186">Importera `Inventory Visibility Configuration Trigger.zip` filen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="17ccc-187">När den har importerats visas utlösaren under **Mina flöden**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="17ccc-188">Initialisera följande fyra variabler baserat på miljöinformation:</span><span class="sxs-lookup"><span data-stu-id="17ccc-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="17ccc-189">ID för Azure-innehavare</span><span class="sxs-lookup"><span data-stu-id="17ccc-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="17ccc-190">Klient-ID för Azure-app</span><span class="sxs-lookup"><span data-stu-id="17ccc-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="17ccc-191">Klienthemlighet för Azure-app</span><span class="sxs-lookup"><span data-stu-id="17ccc-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="17ccc-192">Slutpunkt för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="17ccc-193">Mer information om den här variabeln finns i avsnittet [Ställa in integration av lagersynlighet](#setup-inventory-visibility-integration) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="17ccc-194">![Konfigurationsutlösare](media/configuration-trigger.png "Konfigurationsutlösare")</span><span class="sxs-lookup"><span data-stu-id="17ccc-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="17ccc-195">Välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="17ccc-196">Installera tillägget</span><span class="sxs-lookup"><span data-stu-id="17ccc-196">Install the add-in</span></span>

<span data-ttu-id="17ccc-197">För att installera tillägget för lagersynlighet måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="17ccc-198">Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="17ccc-199">Välj det projekt där miljön har distribuerats på startsidan.</span><span class="sxs-lookup"><span data-stu-id="17ccc-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="17ccc-200">Välj den miljö där du vill installera tillägget på projektsidan.</span><span class="sxs-lookup"><span data-stu-id="17ccc-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="17ccc-201">Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform integration** där du hittar Dataverse miljönamnet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="17ccc-202">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="17ccc-203">![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")</span><span class="sxs-lookup"><span data-stu-id="17ccc-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="17ccc-204">Välj länken **installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="17ccc-205">En lista med tillgängliga tillägg öppnas.</span><span class="sxs-lookup"><span data-stu-id="17ccc-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="17ccc-206">Välj **lagersynlighet** i listan.</span><span class="sxs-lookup"><span data-stu-id="17ccc-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="17ccc-207">Ange värden för följande fält i miljön:</span><span class="sxs-lookup"><span data-stu-id="17ccc-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="17ccc-208">**AAD-program-ID (klient)**</span><span class="sxs-lookup"><span data-stu-id="17ccc-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="17ccc-209">**AAD klientorganisationens ID**</span><span class="sxs-lookup"><span data-stu-id="17ccc-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="17ccc-210">![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")</span><span class="sxs-lookup"><span data-stu-id="17ccc-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="17ccc-211">Godkänn villkoren genom att markera kryssrutan **villkor**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="17ccc-212">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-212">Select **Install**.</span></span> <span data-ttu-id="17ccc-213">Tilläggets status visas som **installerar**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="17ccc-214">När det är klart uppdaterar du sidan så att status ändras till **installerad**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="17ccc-215">Avinstallera tillägget</span><span class="sxs-lookup"><span data-stu-id="17ccc-215">Uninstall the add-in</span></span>

<span data-ttu-id="17ccc-216">För att avinstallera tillägget, välj **avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="17ccc-217">När du uppdaterar LCS tas tillägget för lagersynlighet bort.</span><span class="sxs-lookup"><span data-stu-id="17ccc-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="17ccc-218">Avinstallationsprocessen tar bort registreringen av tillägget och startar även ett jobb för att rensa alla affärsdata som lagras i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="17ccc-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="17ccc-219">Förbruka lagerbehållningsdata från Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="17ccc-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="17ccc-220">Distribuera integreringspaketet för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="17ccc-221">Om du kör Supply Chain Management version 10.0.17 eller tidigare, kontakta supportteamet för inventeringssyn på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få paketfilen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="17ccc-222">Distribuera sedan paketet i LCS.</span><span class="sxs-lookup"><span data-stu-id="17ccc-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="17ccc-223">Om ett versionsfel inträffar under distributionen måste du manuellt importera X++-projektet till din utvecklingsmiljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="17ccc-224">Skapa sedan det paket som kan distribueras i din utvecklingsmiljö och distribuera det i din produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="17ccc-225">Koden ingår i med Supply Chain Management version 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="17ccc-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="17ccc-226">Om du kör den versionen eller senare behöver du inte distribuera den.</span><span class="sxs-lookup"><span data-stu-id="17ccc-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="17ccc-227">Kontrollera att följande funktioner är aktiverat i din Supply Chain Management-miljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="17ccc-228">(Som standard är de aktiverade.)</span><span class="sxs-lookup"><span data-stu-id="17ccc-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="17ccc-229">Funktionsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="17ccc-229">Feature description</span></span> | <span data-ttu-id="17ccc-230">Kodversion</span><span class="sxs-lookup"><span data-stu-id="17ccc-230">Code version</span></span> | <span data-ttu-id="17ccc-231">Växla klass</span><span class="sxs-lookup"><span data-stu-id="17ccc-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="17ccc-232">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSum</span><span class="sxs-lookup"><span data-stu-id="17ccc-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="17ccc-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="17ccc-233">10.0.11</span></span> | <span data-ttu-id="17ccc-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="17ccc-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="17ccc-235">Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="17ccc-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="17ccc-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="17ccc-236">10.0.12</span></span> | <span data-ttu-id="17ccc-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="17ccc-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="17ccc-238">Konfigurera integrering av lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="17ccc-239">I Supply Chain Management, öppna arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen **Integrering av lagersynlighet**.</span><span class="sxs-lookup"><span data-stu-id="17ccc-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="17ccc-240">Gå till **Lagerhantering \> Ställ in \> Parametrar för integrering av lagersynlighet** och ange webbadressen till den miljö där du kör lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="17ccc-241">Sök efter din LCS-miljös Azure-region och ange sedan URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="17ccc-242">URL-adressen har följande formulär:</span><span class="sxs-lookup"><span data-stu-id="17ccc-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="17ccc-243">Om du till exempel är i Europa har din miljö någon av följande URL-adresser:</span><span class="sxs-lookup"><span data-stu-id="17ccc-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="17ccc-244">Följande regioner är för närvarande tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="17ccc-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="17ccc-245">Azure-region</span><span class="sxs-lookup"><span data-stu-id="17ccc-245">Azure region</span></span> | <span data-ttu-id="17ccc-246">Kortnamn för region</span><span class="sxs-lookup"><span data-stu-id="17ccc-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="17ccc-247">Östra Australien</span><span class="sxs-lookup"><span data-stu-id="17ccc-247">Australia east</span></span> | <span data-ttu-id="17ccc-248">eau</span><span class="sxs-lookup"><span data-stu-id="17ccc-248">eau</span></span> |
    | <span data-ttu-id="17ccc-249">Sydöstra Australien</span><span class="sxs-lookup"><span data-stu-id="17ccc-249">Australia southeast</span></span> | <span data-ttu-id="17ccc-250">seau</span><span class="sxs-lookup"><span data-stu-id="17ccc-250">seau</span></span> |
    | <span data-ttu-id="17ccc-251">Centrala Kanada</span><span class="sxs-lookup"><span data-stu-id="17ccc-251">Canada central</span></span> | <span data-ttu-id="17ccc-252">cca</span><span class="sxs-lookup"><span data-stu-id="17ccc-252">cca</span></span> |
    | <span data-ttu-id="17ccc-253">Östra Kanada</span><span class="sxs-lookup"><span data-stu-id="17ccc-253">Canada east</span></span> | <span data-ttu-id="17ccc-254">eca</span><span class="sxs-lookup"><span data-stu-id="17ccc-254">eca</span></span> |
    | <span data-ttu-id="17ccc-255">Nordeuropa</span><span class="sxs-lookup"><span data-stu-id="17ccc-255">North Europe</span></span> | <span data-ttu-id="17ccc-256">neu</span><span class="sxs-lookup"><span data-stu-id="17ccc-256">neu</span></span> |
    | <span data-ttu-id="17ccc-257">Västeuropa</span><span class="sxs-lookup"><span data-stu-id="17ccc-257">West Europe</span></span> | <span data-ttu-id="17ccc-258">weu</span><span class="sxs-lookup"><span data-stu-id="17ccc-258">weu</span></span> |
    | <span data-ttu-id="17ccc-259">Östra USA</span><span class="sxs-lookup"><span data-stu-id="17ccc-259">East US</span></span> | <span data-ttu-id="17ccc-260">eus</span><span class="sxs-lookup"><span data-stu-id="17ccc-260">eus</span></span> |
    | <span data-ttu-id="17ccc-261">Västra USA</span><span class="sxs-lookup"><span data-stu-id="17ccc-261">West US</span></span> | <span data-ttu-id="17ccc-262">wus</span><span class="sxs-lookup"><span data-stu-id="17ccc-262">wus</span></span> |

1. <span data-ttu-id="17ccc-263">Gå till **Lagerhantering \> Periodisk \> Integrering av lagerhantering** och aktivera jobbet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="17ccc-264">Alla lagerändringshändelser från Supply Chain Management bokförs nu i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="17ccc-265">Tillägg för lagersynlighet i offentlig API</span><span class="sxs-lookup"><span data-stu-id="17ccc-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="17ccc-266">Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="17ccc-267">Den stöder tre huvudinteraktionstyper:</span><span class="sxs-lookup"><span data-stu-id="17ccc-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="17ccc-268">Bokföring av ändringar för lagerbehållning i tillägget från ett externt system</span><span class="sxs-lookup"><span data-stu-id="17ccc-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="17ccc-269">Fråga om aktuell behållning från ett externt system</span><span class="sxs-lookup"><span data-stu-id="17ccc-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="17ccc-270">Automatisk synkronisering med lagerbehållning av Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="17ccc-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="17ccc-271">Automatisk synkronisering av en del av den offentliga API:t.</span><span class="sxs-lookup"><span data-stu-id="17ccc-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="17ccc-272">I stället hanteras den i bakgrunden för miljöer där tillägget lagersynlighet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="17ccc-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="17ccc-273">Äkthetsbevisning</span><span class="sxs-lookup"><span data-stu-id="17ccc-273">Authentication</span></span>

<span data-ttu-id="17ccc-274">Säkerhetstoken för plattform används för att anropa tillägget lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="17ccc-275">Därför måste du generera en *Azure Active Directory (Azure AD) token* med hjälp av ditt Azure AD program.</span><span class="sxs-lookup"><span data-stu-id="17ccc-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="17ccc-276">Du måste sedan använda Azure AD token för att få *åtkomsttoken* från säkerhetstjänsten.</span><span class="sxs-lookup"><span data-stu-id="17ccc-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="17ccc-277">Hämta en säkerhetstjänsttoken genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="17ccc-278">Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.</span><span class="sxs-lookup"><span data-stu-id="17ccc-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="17ccc-279">Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="17ccc-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="17ccc-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="17ccc-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="17ccc-281">**Metod** - `GET`</span><span class="sxs-lookup"><span data-stu-id="17ccc-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="17ccc-282">**Brödtext (formulärdata)**:</span><span class="sxs-lookup"><span data-stu-id="17ccc-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="17ccc-283">nyckel</span><span class="sxs-lookup"><span data-stu-id="17ccc-283">key</span></span> | <span data-ttu-id="17ccc-284">värde</span><span class="sxs-lookup"><span data-stu-id="17ccc-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="17ccc-285">klient-ID</span><span class="sxs-lookup"><span data-stu-id="17ccc-285">client_id</span></span> | <span data-ttu-id="17ccc-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="17ccc-286">${aadAppId}</span></span> |
        | <span data-ttu-id="17ccc-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="17ccc-287">client_secret</span></span> | <span data-ttu-id="17ccc-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="17ccc-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="17ccc-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="17ccc-289">grant_type</span></span> | <span data-ttu-id="17ccc-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="17ccc-290">client_credentials</span></span> |
        | <span data-ttu-id="17ccc-291">resurs</span><span class="sxs-lookup"><span data-stu-id="17ccc-291">resource</span></span> | <span data-ttu-id="17ccc-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="17ccc-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="17ccc-293">Du bör få `aadToken` i svar, som liknar följande exempel.</span><span class="sxs-lookup"><span data-stu-id="17ccc-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="17ccc-294">Formulera en JSON-begäran som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-294">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="17ccc-295">Där:</span><span class="sxs-lookup"><span data-stu-id="17ccc-295">Where:</span></span>
    - <span data-ttu-id="17ccc-296">Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="17ccc-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="17ccc-297">Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.</span><span class="sxs-lookup"><span data-stu-id="17ccc-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="17ccc-298">Ställ in alla andra värden enligt exemplet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="17ccc-299">Skicka en HTTP-begäran med följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="17ccc-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="17ccc-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="17ccc-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="17ccc-301">**Metod** - `POST`</span><span class="sxs-lookup"><span data-stu-id="17ccc-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="17ccc-302">**HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)</span><span class="sxs-lookup"><span data-stu-id="17ccc-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="17ccc-303">**Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.</span><span class="sxs-lookup"><span data-stu-id="17ccc-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="17ccc-304">Du får ett `access_token` i svar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="17ccc-305">Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="17ccc-306">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="17ccc-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="17ccc-307">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="17ccc-307">Sample Request</span></span>

<span data-ttu-id="17ccc-308">För din referens följer här ett exempel på en http-begäran- du kan använda valfritt verktyg eller kodspråk för att skicka denna, begäran, exempelvis ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="17ccc-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

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

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="17ccc-309">Konfigurera API för lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="17ccc-310">Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="17ccc-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="17ccc-311">Konfigurationen kan variera beroende på vad som gäller för din miljö.</span><span class="sxs-lookup"><span data-stu-id="17ccc-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="17ccc-312">Den omfattar huvudsakligen fyra delar:</span><span class="sxs-lookup"><span data-stu-id="17ccc-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="17ccc-313">Partitionering</span><span class="sxs-lookup"><span data-stu-id="17ccc-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="17ccc-314">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="17ccc-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="17ccc-315">Indexering</span><span class="sxs-lookup"><span data-stu-id="17ccc-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="17ccc-316">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="17ccc-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="17ccc-317">Partitionering</span><span class="sxs-lookup"><span data-stu-id="17ccc-317">Partitioning</span></span>

<span data-ttu-id="17ccc-318">Partitionering kan i stor grad påverka prestandan för API för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="17ccc-319">Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågeställningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="17ccc-320">`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*.</span><span class="sxs-lookup"><span data-stu-id="17ccc-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="17ccc-321">Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.</span><span class="sxs-lookup"><span data-stu-id="17ccc-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="17ccc-322">*Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="17ccc-323">I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="17ccc-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="17ccc-324">Dimensionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="17ccc-324">Dimension configurations</span></span>

<span data-ttu-id="17ccc-325">Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.</span><span class="sxs-lookup"><span data-stu-id="17ccc-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="17ccc-326">I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="17ccc-327">Dimensionstyp</span><span class="sxs-lookup"><span data-stu-id="17ccc-327">Dimension type</span></span> | <span data-ttu-id="17ccc-328">Dimensionsnamn</span><span class="sxs-lookup"><span data-stu-id="17ccc-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="17ccc-329">Produkt</span><span class="sxs-lookup"><span data-stu-id="17ccc-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="17ccc-330">Produkt</span><span class="sxs-lookup"><span data-stu-id="17ccc-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="17ccc-331">Produkt</span><span class="sxs-lookup"><span data-stu-id="17ccc-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="17ccc-332">Produkt</span><span class="sxs-lookup"><span data-stu-id="17ccc-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="17ccc-333">Spårning</span><span class="sxs-lookup"><span data-stu-id="17ccc-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="17ccc-334">Spårning</span><span class="sxs-lookup"><span data-stu-id="17ccc-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="17ccc-335">Plats</span><span class="sxs-lookup"><span data-stu-id="17ccc-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="17ccc-336">Plats</span><span class="sxs-lookup"><span data-stu-id="17ccc-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="17ccc-337">Lagerstatus</span><span class="sxs-lookup"><span data-stu-id="17ccc-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="17ccc-338">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="17ccc-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="17ccc-339">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="17ccc-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="17ccc-340">Lagerställespecifik</span><span class="sxs-lookup"><span data-stu-id="17ccc-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="17ccc-341">Dimensionstypen som visas i föregående tabell är endast referens.</span><span class="sxs-lookup"><span data-stu-id="17ccc-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="17ccc-342">Du behöver inte ange dimensionstypen i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="17ccc-343">Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="17ccc-344">Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="17ccc-345">Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="17ccc-346">Måldimensionerna måste vara en av följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="17ccc-347">Standarddimensioner vid lagersynlighet</span><span class="sxs-lookup"><span data-stu-id="17ccc-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="17ccc-348">Anpassade dimensioner</span><span class="sxs-lookup"><span data-stu-id="17ccc-348">Custom dimensions</span></span>

<span data-ttu-id="17ccc-349">Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågeställningen på dimensioner och bokföringshändelsen med dimensioner.</span><span class="sxs-lookup"><span data-stu-id="17ccc-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="17ccc-350">Indexering</span><span class="sxs-lookup"><span data-stu-id="17ccc-350">Indexing</span></span>

<span data-ttu-id="17ccc-351">För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="17ccc-352">Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="17ccc-353">För närvarande kan du bara konfigurera index till maximalt fem.</span><span class="sxs-lookup"><span data-stu-id="17ccc-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="17ccc-354">Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="17ccc-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="17ccc-355">Om du till exempel vill söka efter produkter enligt följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="17ccc-356">Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.</span><span class="sxs-lookup"><span data-stu-id="17ccc-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="17ccc-357">I vissa fall vill du bara fråga den totala produkten.</span><span class="sxs-lookup"><span data-stu-id="17ccc-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="17ccc-358">Två index är definierade som följande:</span><span class="sxs-lookup"><span data-stu-id="17ccc-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="17ccc-359">Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="17ccc-360">Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning.</span><span class="sxs-lookup"><span data-stu-id="17ccc-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="17ccc-361">I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`.</span><span class="sxs-lookup"><span data-stu-id="17ccc-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="17ccc-362">Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="17ccc-363">Du kan ange frågevillkor i den begärandetext.</span><span class="sxs-lookup"><span data-stu-id="17ccc-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="17ccc-364">Här är en exempel fråga på produkten med kombinationen färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="17ccc-364">Here is a sample query on the product with color and size combination.</span></span>

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

<span data-ttu-id="17ccc-365">För fältet `filters` stöder för närvarande bara `ProductId` flera värden.</span><span class="sxs-lookup"><span data-stu-id="17ccc-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="17ccc-366">Om matrisen `ProductId` är tom kommer alla produkter att efterfrågas.</span><span class="sxs-lookup"><span data-stu-id="17ccc-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="17ccc-367">Anpassat mått</span><span class="sxs-lookup"><span data-stu-id="17ccc-367">Custom measurement</span></span>

<span data-ttu-id="17ccc-368">Standardmåttkvantiteterna är kopplade till Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="17ccc-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="17ccc-369">Det kan dock vara en bra kvantitet som består av en kombination av standardmåtten.</span><span class="sxs-lookup"><span data-stu-id="17ccc-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="17ccc-370">För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågeställningarna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="17ccc-371">Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="17ccc-372">Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="17ccc-373">Förbrukningssystem</span><span class="sxs-lookup"><span data-stu-id="17ccc-373">Consumption system</span></span> | <span data-ttu-id="17ccc-374">Beräknade mått</span><span class="sxs-lookup"><span data-stu-id="17ccc-374">Calculated measurers</span></span> | <span data-ttu-id="17ccc-375">Datakälla</span><span class="sxs-lookup"><span data-stu-id="17ccc-375">Data source</span></span> | <span data-ttu-id="17ccc-376">Modifierare</span><span class="sxs-lookup"><span data-stu-id="17ccc-376">Modifier</span></span> | <span data-ttu-id="17ccc-377">Beräkningstyp för modifierare</span><span class="sxs-lookup"><span data-stu-id="17ccc-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="17ccc-378">Tillägg</span><span class="sxs-lookup"><span data-stu-id="17ccc-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="17ccc-379">Tillägg</span><span class="sxs-lookup"><span data-stu-id="17ccc-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="17ccc-380">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="17ccc-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="17ccc-381">Tillägg</span><span class="sxs-lookup"><span data-stu-id="17ccc-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="17ccc-382">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="17ccc-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="17ccc-383">Tillägg</span><span class="sxs-lookup"><span data-stu-id="17ccc-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="17ccc-384">Tillägg</span><span class="sxs-lookup"><span data-stu-id="17ccc-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="17ccc-385">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="17ccc-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="17ccc-386">Subtraktion</span><span class="sxs-lookup"><span data-stu-id="17ccc-386">Subtraction</span></span> |

<span data-ttu-id="17ccc-387">Med detta kommer frågeställningen för den anpassade måttkvantiteten att returnera följande resultat.</span><span class="sxs-lookup"><span data-stu-id="17ccc-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="17ccc-388">`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:</span><span class="sxs-lookup"><span data-stu-id="17ccc-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="17ccc-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="17ccc-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="17ccc-390">Bokföra lagerbehållningsändringar</span><span class="sxs-lookup"><span data-stu-id="17ccc-390">Posting on-hand changes</span></span>

<span data-ttu-id="17ccc-391">Den exakta URL som händelsen ska skickas till beror på din geografiska region.</span><span class="sxs-lookup"><span data-stu-id="17ccc-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="17ccc-392">Formuläret kommer att ha följande format:</span><span class="sxs-lookup"><span data-stu-id="17ccc-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="17ccc-393">När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="17ccc-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="17ccc-394">En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till.</span><span class="sxs-lookup"><span data-stu-id="17ccc-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="17ccc-395">Exempel:</span><span class="sxs-lookup"><span data-stu-id="17ccc-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="17ccc-396">Skicka behållningsändringar fråga exempel 1</span><span class="sxs-lookup"><span data-stu-id="17ccc-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="17ccc-397">I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="17ccc-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="17ccc-398">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="17ccc-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="17ccc-399">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="17ccc-400">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="17ccc-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="17ccc-401">Skicka behållningsändringar fråga exempel 2</span><span class="sxs-lookup"><span data-stu-id="17ccc-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="17ccc-402">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="17ccc-403">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="17ccc-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="17ccc-404">JSON dokumentfältegenskaper</span><span class="sxs-lookup"><span data-stu-id="17ccc-404">JSON document field properties</span></span>

<span data-ttu-id="17ccc-405">De fält från exempel för JSON-frågeställningar som tidigare har angetts har de egenskaper som anges i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="17ccc-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="17ccc-406">Fält-ID</span><span class="sxs-lookup"><span data-stu-id="17ccc-406">Field ID</span></span> | <span data-ttu-id="17ccc-407">beskrivning</span><span class="sxs-lookup"><span data-stu-id="17ccc-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="17ccc-408">Ett unikt ID för den specifika ändringshändelsen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="17ccc-409">Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="17ccc-410">Identifierare för den organisation som är kopplad till händelsen.</span><span class="sxs-lookup"><span data-stu-id="17ccc-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="17ccc-411">Detta mappar till Supply Chain Management organisations eller dataområdes-ID.</span><span class="sxs-lookup"><span data-stu-id="17ccc-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="17ccc-412">Den unika identifieraren av produkten i fråga.</span><span class="sxs-lookup"><span data-stu-id="17ccc-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="17ccc-413">Kvantiteten som behållningen måste ändras med.</span><span class="sxs-lookup"><span data-stu-id="17ccc-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="17ccc-414">Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10.</span><span class="sxs-lookup"><span data-stu-id="17ccc-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="17ccc-415">Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3.</span><span class="sxs-lookup"><span data-stu-id="17ccc-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="17ccc-416">Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga.</span><span class="sxs-lookup"><span data-stu-id="17ccc-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="17ccc-417">Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan.</span><span class="sxs-lookup"><span data-stu-id="17ccc-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="17ccc-418">Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="17ccc-419">Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågeställningarna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="17ccc-420">En dynamisk uppsättning nyckel/värde-par.</span><span class="sxs-lookup"><span data-stu-id="17ccc-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="17ccc-421">Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system.</span><span class="sxs-lookup"><span data-stu-id="17ccc-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="17ccc-422">Fråga aktuell behållning</span><span class="sxs-lookup"><span data-stu-id="17ccc-422">Querying current on-hand</span></span>

<span data-ttu-id="17ccc-423">Slutpunkten för att hämta den aktuella behållningen har en liknande URL:</span><span class="sxs-lookup"><span data-stu-id="17ccc-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="17ccc-424">Den kommer att frågas med HTTP `POST`-metoden.</span><span class="sxs-lookup"><span data-stu-id="17ccc-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="17ccc-425">Aktuellt behållningsexempel 1</span><span class="sxs-lookup"><span data-stu-id="17ccc-425">Current on-hand query example 1</span></span>

<span data-ttu-id="17ccc-426">I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.</span><span class="sxs-lookup"><span data-stu-id="17ccc-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="17ccc-427">Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="17ccc-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="17ccc-428">Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar.</span><span class="sxs-lookup"><span data-stu-id="17ccc-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="17ccc-429">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="17ccc-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="17ccc-430">Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="17ccc-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="17ccc-431">Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.</span><span class="sxs-lookup"><span data-stu-id="17ccc-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="17ccc-432">Aktuellt behållningsexempel 2</span><span class="sxs-lookup"><span data-stu-id="17ccc-432">Current on-hand query example 2</span></span>

<span data-ttu-id="17ccc-433">I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="17ccc-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="17ccc-434">Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.</span><span class="sxs-lookup"><span data-stu-id="17ccc-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="17ccc-435">Exempel på returresultat</span><span class="sxs-lookup"><span data-stu-id="17ccc-435">Example return result</span></span>

<span data-ttu-id="17ccc-436">Frågeställningarna som visas i föregående exempel kan returnera resultatet.</span><span class="sxs-lookup"><span data-stu-id="17ccc-436">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="17ccc-437">Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.</span><span class="sxs-lookup"><span data-stu-id="17ccc-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
