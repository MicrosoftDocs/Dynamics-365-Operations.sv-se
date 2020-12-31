---
title: Konfiguration för Ekonomiinsikter (förhandsversion)
description: I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 38cdeb9110691e594b4b90fc5bc79e369c9f4707
ms.sourcegitcommit: 1cfd6e0c808341b0f5bafbde7d04b0255b27352f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664100"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="c6a92-103">Konfiguration för Ekonomiinsikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c6a92-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c6a92-104">Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Common Data Service, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Common Data Service, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="c6a92-105">I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="c6a92-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="c6a92-106">Distribuera Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="c6a92-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="c6a92-107">Följ dessa steg för att distribuera miljöerna.</span><span class="sxs-lookup"><span data-stu-id="c6a92-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="c6a92-108">I Microsoft Dynamics Lifecycle Services (LCS), skapa eller uppdatera en Dynamics 365 Finance-miljö.</span><span class="sxs-lookup"><span data-stu-id="c6a92-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="c6a92-109">Miljön kräver programversion 10.0.11/Platform update 35 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="c6a92-110">Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="c6a92-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="c6a92-111">(Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="c6a92-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="c6a92-112">Om du använder Contoso-demo data behöver du ytterligare exempeldata för att kunna använda funktionerna för kundbetalningsförutsägelser, kassaflödesprognoser och budgetprognoser.</span><span class="sxs-lookup"><span data-stu-id="c6a92-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-common-data-service"></a><span data-ttu-id="c6a92-113">Konfigurera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c6a92-113">Configure Common Data Service</span></span>

<span data-ttu-id="c6a92-114">Du kan slutföra de manuella konfigurationsstegen som följer eller så kan du påskynda konfigurationen med hjälp av det Windows PowerShell-skript som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="c6a92-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="c6a92-115">När PowerShell-skriptet har körts klart får du tillgång till värden som används för att konfigurera Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="c6a92-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="c6a92-116">Kör skriptet genom att öppna PowerShell på datorn.</span><span class="sxs-lookup"><span data-stu-id="c6a92-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="c6a92-117">Du kan behöva PowerShell version 5.</span><span class="sxs-lookup"><span data-stu-id="c6a92-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="c6a92-118">Microsoft Azure CLI-alternativet "Pröva" kanske inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="c6a92-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="c6a92-119">Manuella konfigurationssteg</span><span class="sxs-lookup"><span data-stu-id="c6a92-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="c6a92-120">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/) och skapa en ny Common Data Service-miljö i samma Active Directory-klientorganisation genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="c6a92-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Common Data Service environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="c6a92-121">Öppna sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="c6a92-122">[![Sidan Miljöer](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="c6a92-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="c6a92-123">Välj **Ny miljö**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="c6a92-124">I fältet **Typ**, välj **Sandbox**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="c6a92-125">Ange alternativet **Skapa databas** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="c6a92-126">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-126">Select **Next**.</span></span>
    6. <span data-ttu-id="c6a92-127">Välj språk och valuta för organisationen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="c6a92-128">Acceptera standardvärden i övriga fält.</span><span class="sxs-lookup"><span data-stu-id="c6a92-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="c6a92-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-129">Select **Save**.</span></span>
    9. <span data-ttu-id="c6a92-130">Uppdatera sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="c6a92-131">Vänta tills värdet i **Tillstånd** har uppdaterats till **Klart**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="c6a92-132">Gör en notering om Common Data Service-organisations-ID.</span><span class="sxs-lookup"><span data-stu-id="c6a92-132">Make a note of the Common Data Service organization ID.</span></span>
    12. <span data-ttu-id="c6a92-133">Välj miljön och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="c6a92-134">Välj **Resurser \> Alla äldre inställningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="c6a92-135">Välj **Inställningar** i det övre navigeringsfältet och välj **Anpassningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="c6a92-136">Välj **Utvecklarresurser**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="c6a92-137">Ställ in fältet för **instansens referensensinformations-ID** till organisations-ID-värdet för Common Data Service som du noterade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-137">Set the **Instance Reference Information ID** field to the Common Data Service organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="c6a92-138">Notera URL:en till Common Data Service-organisationen i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="c6a92-138">In the browser's address bar, make a note of the URL for the Common Data Service organization.</span></span> <span data-ttu-id="c6a92-139">URL-adressen kan till exempel vara `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="c6a92-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="c6a92-140">Om du planerar att använda kassaflödesprognoser eller budgetprognoser, följer du dessa steg för att uppdatera anteckningsgränsen för organisationen till minst 50 MB:</span><span class="sxs-lookup"><span data-stu-id="c6a92-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="c6a92-141">Öppna [Power Apps-portal](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="c6a92-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="c6a92-142">Välj den miljö som du just har skapat och välj sedan **Avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="c6a92-143">Välj **Inställningar \> E-postkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="c6a92-144">Ändra värdet för fältet **Maximal filstorlek** till **51 200**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="c6a92-145">(Värdet uttrycks i kilobyte \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="c6a92-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="c6a92-146">Välj **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="c6a92-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="c6a92-147">Konfigurationsskript för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6a92-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="c6a92-148">Konfigurera Azure-inställningen</span><span class="sxs-lookup"><span data-stu-id="c6a92-148">Configure the Azure setup</span></span>

### <a name="enter-the-common-data-service-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="c6a92-149">Ange Common Data Service-katalog-ID och användarens Azure AD-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="c6a92-149">Enter the Common Data Service directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="c6a92-150">Ange Common Data Service-katalog-ID:</span><span class="sxs-lookup"><span data-stu-id="c6a92-150">Enter the Common Data Service directory ID:</span></span>

    1. <span data-ttu-id="c6a92-151">Öppna [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c6a92-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="c6a92-152">Logga in genom att använda det användar-ID som användes för att skapa Common Data Service-miljön.</span><span class="sxs-lookup"><span data-stu-id="c6a92-152">Sign in by using the user ID that was used to create the Common Data Service environment.</span></span>
    3. <span data-ttu-id="c6a92-153">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="c6a92-154">Kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="c6a92-155">Ange användarens Azure Active Directory-objekt-ID (Azure AD):</span><span class="sxs-lookup"><span data-stu-id="c6a92-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="c6a92-156">I [Azure-portalen](https://portal.azure.com), gå till **Användare** och sök efter användaren via e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="c6a92-157">Välj användarens namn.</span><span class="sxs-lookup"><span data-stu-id="c6a92-157">Select the user's name.</span></span>
    3. <span data-ttu-id="c6a92-158">Kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="c6a92-159">Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser</span><span class="sxs-lookup"><span data-stu-id="c6a92-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="c6a92-160">Använd ett Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="c6a92-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="c6a92-161">Ett Windows PowerShell-skript har angetts så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="c6a92-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="c6a92-162">Om du föredrar att göra manuella inställningar hoppar du över den här proceduren och fortsätter med proceduren i avsnittet [Manuell konfiguration](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="c6a92-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="c6a92-163">Kör PowerShell-skriptet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c6a92-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="c6a92-164">Azure CLI-alternativet "Pröva" eller att köra skriptet på datorn fungerar kanske inte.</span><span class="sxs-lookup"><span data-stu-id="c6a92-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="c6a92-165">Följ dessa steg för att konfigurera Azure med hjälp av Windows PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="c6a92-166">Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program.</span><span class="sxs-lookup"><span data-stu-id="c6a92-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="c6a92-167">Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="c6a92-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="c6a92-168">I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="c6a92-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="c6a92-169">Välj knappen **Cloud Shell** till höger om fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="c6a92-170">Välj **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="c6a92-171">Skapa lagringsutrymme om du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="c6a92-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="c6a92-172">Ladda sedan upp Windows PowerShell-skriptet till sessionen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="c6a92-173">Kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-173">Run the script.</span></span>
5. <span data-ttu-id="c6a92-174">Kör skriptet genom att följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="c6a92-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="c6a92-175">Installera tillägget **Exportera till Data Lake** i LCS med hjälp av informationen i skriptets utdata.</span><span class="sxs-lookup"><span data-stu-id="c6a92-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="c6a92-176">Använd informationen från skriptets utdata för att aktivera entitetsarkivet på sidan **Dataanslutningar** i Finance (**Systemadministration \> Systemparametrar \> Dataanslutningar**).</span><span class="sxs-lookup"><span data-stu-id="c6a92-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="c6a92-177">Manuell konfiguration</span><span class="sxs-lookup"><span data-stu-id="c6a92-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="c6a92-178">Lägg till program i Azure AD-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="c6a92-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="c6a92-179">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="c6a92-180">Välj **Hantera \> Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="c6a92-181">Sök efter följande program med app-ID.</span><span class="sxs-lookup"><span data-stu-id="c6a92-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="c6a92-182">Ansökning</span><span class="sxs-lookup"><span data-stu-id="c6a92-182">Application</span></span>                              | <span data-ttu-id="c6a92-183">App-ID</span><span class="sxs-lookup"><span data-stu-id="c6a92-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="c6a92-184">Microsoft Dynamics ERP Microservices</span><span class="sxs-lookup"><span data-stu-id="c6a92-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="c6a92-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="c6a92-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="c6a92-186">Microsoft Dynamics ERP Microservices CDS</span><span class="sxs-lookup"><span data-stu-id="c6a92-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="c6a92-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="c6a92-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="c6a92-188">AI Builder Authorization Service</span><span class="sxs-lookup"><span data-stu-id="c6a92-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="c6a92-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="c6a92-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="c6a92-190">Om du inte hittar något av ovanstående program gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="c6a92-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="c6a92-191">Välj **Start**-menyn och sök efter **powershell** på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="c6a92-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="c6a92-192">Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="c6a92-193">Kör följande kommando för att installera modulen **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="c6a92-194">Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.</span><span class="sxs-lookup"><span data-stu-id="c6a92-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="c6a92-195">Om meddelandet "Untrusted repository" (Ej betrodd lagringsplats) visas väljer du **Y** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="c6a92-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="c6a92-196">Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c6a92-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="c6a92-197">Logga in som Azure AD-administratör när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="c6a92-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="c6a92-198">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="c6a92-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="c6a92-199">Se till att du skapar följande resurser i samma Azure AD-instans som Common Data Service-miljön.</span><span class="sxs-lookup"><span data-stu-id="c6a92-199">Make sure that you create the following resources in the same Azure AD instance as the Common Data Service environment.</span></span> <span data-ttu-id="c6a92-200">Du kan inte använda resurser från en annan Azure AD-instans.</span><span class="sxs-lookup"><span data-stu-id="c6a92-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="c6a92-201">Skapa ett nytt lagringskonto:</span><span class="sxs-lookup"><span data-stu-id="c6a92-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="c6a92-202">Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c6a92-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="c6a92-203">I dialogrutan **Skapa lagringskonto**, ställ in följande fält:</span><span class="sxs-lookup"><span data-stu-id="c6a92-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="c6a92-204">**Plats** – Välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="c6a92-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="c6a92-205">**Prestanda** – Vi rekommenderar att du väljer **Standard**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="c6a92-206">**Kontotyp** – Du måste välja **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="c6a92-207">I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="c6a92-208">Om du inaktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som Power BI-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="c6a92-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="c6a92-209">Välj **Granska och skapa**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-209">Select **Review and create**.</span></span> <span data-ttu-id="c6a92-210">När distributionen har slutförts visas den nya resursen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="c6a92-211">Gå till det lagringskonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="c6a92-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="c6a92-212">Välj **Åtkomstnycklar** i menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="c6a92-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="c6a92-213">Kopiera och spara anslutningssträngen för antingen **Key1** eller **Key2**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="c6a92-214">Kopiera och spara namnet på lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="c6a92-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="c6a92-215">Skapa en ny nyckelvalvresurs:</span><span class="sxs-lookup"><span data-stu-id="c6a92-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="c6a92-216">Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c6a92-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="c6a92-217">I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="c6a92-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="c6a92-218">När nyckelvalvet har skapats väljer du det i listan och väljer sedan **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="c6a92-219">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="c6a92-220">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="c6a92-221">Ange ett namn på hemligheten.</span><span class="sxs-lookup"><span data-stu-id="c6a92-221">Enter a name for the secret.</span></span> <span data-ttu-id="c6a92-222">Anteckna namnet eftersom du kommer att behöva ange det senare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="c6a92-223">I fältet **Värde** anger du den anslutningssträng som du hämtade från lagringskontot i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="c6a92-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="c6a92-224">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="c6a92-225">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="c6a92-226">Gå till **nyckelvalvöversikten** och anteckna DNS-namnet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="c6a92-227">Skapa och registrera ett Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="c6a92-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="c6a92-228">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="c6a92-229">Välj **Ny programregistrering** och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="c6a92-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="c6a92-230">**Namn** – Ange namnet på appen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="c6a92-231">**Programtyp** – Välj **Webb-API**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="c6a92-232">**Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="c6a92-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="c6a92-233">Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="c6a92-234">Du måste ange det här värdet senare när du konfigurerar nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="c6a92-235">Gå till **API-behörigheter** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="c6a92-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="c6a92-236">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="c6a92-237">Välj **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="c6a92-238">När du har valt delegerade behörigheter väljer du **användare\_personifiering**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="c6a92-239">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="c6a92-240">På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="c6a92-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="c6a92-241">Välj **Ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="c6a92-242">Ange ett namn i fältet **Nyckelbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="c6a92-243">Markera en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="c6a92-244">En hemlighet genereras i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="c6a92-245">Kopiera och spara det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="c6a92-246">Skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="c6a92-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="c6a92-247">Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="c6a92-248">Gör så här för varje hemligt namn i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c6a92-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c6a92-249">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="c6a92-250">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="c6a92-251">Skapa det hemliga namnet och värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c6a92-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="c6a92-252">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="c6a92-253">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="c6a92-254">Hemligt namn</span><span class="sxs-lookup"><span data-stu-id="c6a92-254">Secret name</span></span>                       | <span data-ttu-id="c6a92-255">Hemligt värde</span><span class="sxs-lookup"><span data-stu-id="c6a92-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="c6a92-256">program-ID</span><span class="sxs-lookup"><span data-stu-id="c6a92-256">app-id</span></span>                            | <span data-ttu-id="c6a92-257">App-ID för programmet som du skapade tidigare</span><span class="sxs-lookup"><span data-stu-id="c6a92-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="c6a92-258">programhemlighet</span><span class="sxs-lookup"><span data-stu-id="c6a92-258">app-secret</span></span>                        | <span data-ttu-id="c6a92-259">Klienthemligheten som du sparade tidigare</span><span class="sxs-lookup"><span data-stu-id="c6a92-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="c6a92-260">lagringskontonamn</span><span class="sxs-lookup"><span data-stu-id="c6a92-260">storage-account-name</span></span>              | <span data-ttu-id="c6a92-261">Namnet på lagringskontot som du skapade tidigare, t.ex. **lagringskonto1**</span><span class="sxs-lookup"><span data-stu-id="c6a92-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="c6a92-262">lagringskontots anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c6a92-262">storage-account-connection-string</span></span> | <span data-ttu-id="c6a92-263">Den anslutningssträng som du kopierade från sidan **Åtkomstnycklar** för lagringskontot</span><span class="sxs-lookup"><span data-stu-id="c6a92-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="c6a92-264">Auktorisera programmet för att få åtkomst till nyckelvalvet:</span><span class="sxs-lookup"><span data-stu-id="c6a92-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="c6a92-265">I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="c6a92-266">Välj åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="c6a92-266">Select the access policies.</span></span>
    3. <span data-ttu-id="c6a92-267">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c6a92-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c6a92-268">Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="c6a92-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="c6a92-269">I fältet **Hemliga behörigheter**, välj behörigheterna från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c6a92-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="c6a92-270">I fältet **Välj huvudnamn**, sök efter programmets visningsnamn från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c6a92-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="c6a92-271">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-271">Select **Select**.</span></span>
        5. <span data-ttu-id="c6a92-272">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-272">Select **Add**.</span></span>
        6. <span data-ttu-id="c6a92-273">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-273">Select **Save**.</span></span>

        | <span data-ttu-id="c6a92-274">Ansökning</span><span class="sxs-lookup"><span data-stu-id="c6a92-274">Application</span></span>                                              | <span data-ttu-id="c6a92-275">Behörighet</span><span class="sxs-lookup"><span data-stu-id="c6a92-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="c6a92-276">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="c6a92-276">The display name of the new application that you created</span></span> | <span data-ttu-id="c6a92-277">Get, List</span><span class="sxs-lookup"><span data-stu-id="c6a92-277">Get, List</span></span>   |
        | <span data-ttu-id="c6a92-278">**Microsoft Dynamics ERP Microservices**</span><span class="sxs-lookup"><span data-stu-id="c6a92-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="c6a92-279">Get, List</span><span class="sxs-lookup"><span data-stu-id="c6a92-279">Get, List</span></span>   |

6. <span data-ttu-id="c6a92-280">Tilldela roller för åtkomst till lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="c6a92-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="c6a92-281">I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="c6a92-282">Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="c6a92-283">Välj **Lägg till, Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="c6a92-284">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="c6a92-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c6a92-285">Välj rollen bland i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c6a92-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="c6a92-286">Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="c6a92-287">I fältet **Välj**, ange programmet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c6a92-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="c6a92-288">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-288">Select **Save**.</span></span>

        | <span data-ttu-id="c6a92-289">Ansökning</span><span class="sxs-lookup"><span data-stu-id="c6a92-289">Application</span></span>                                              | <span data-ttu-id="c6a92-290">Roll</span><span class="sxs-lookup"><span data-stu-id="c6a92-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="c6a92-291">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="c6a92-291">The display name of the new application that you created</span></span> | <span data-ttu-id="c6a92-292">Ägare</span><span class="sxs-lookup"><span data-stu-id="c6a92-292">Owner</span></span>                       |
        | <span data-ttu-id="c6a92-293">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="c6a92-293">The display name of the new application that you created</span></span> | <span data-ttu-id="c6a92-294">Deltagare</span><span class="sxs-lookup"><span data-stu-id="c6a92-294">Contributor</span></span>                 |
        | <span data-ttu-id="c6a92-295">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="c6a92-295">The display name of the new application that you created</span></span> | <span data-ttu-id="c6a92-296">Lagringskontodeltagare</span><span class="sxs-lookup"><span data-stu-id="c6a92-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="c6a92-297">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="c6a92-297">The display name of the new application that you created</span></span> | <span data-ttu-id="c6a92-298">Storage Blob Data-ägare</span><span class="sxs-lookup"><span data-stu-id="c6a92-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="c6a92-299">**AI Builder Authorization Service**</span><span class="sxs-lookup"><span data-stu-id="c6a92-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="c6a92-300">Storage Blob Data-läsare</span><span class="sxs-lookup"><span data-stu-id="c6a92-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="c6a92-301">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="c6a92-301">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    $defaultSecretExpiryInYear = 1

    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (blank for default)")
    if ($subscriptionId.Trim() -ne '') {
        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }

    $resourceGroupName = (Read-Host -Prompt "Enter the Azure Resource Group name: (blank for 'FinanceDataLake')")
    if ($null -eq $resourceGroupName -or $resourceGroupName.Trim() -eq '') {
        $resourceGroupName = 'FinanceDataLake'
    }
    $resourceGroup = Get-AzResourceGroup -Name $resourceGroupName -ErrorAction SilentlyContinue

    if (-not ($resourceGroup)) {
        $resourceLocation = ''
        $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
        while ($resourceLocation.Trim() -eq '' -or (-not ($resourceLocation -in $azResourceLocations))) {
            $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
            if ($resourceLocation -eq 'help') {
                $azResourceLocations
                $resourceLocation = ''
            }
        }
        $resourceGroup = New-AzResourceGroup -Name $resourceGroupName -Location $resourceLocation
    }
    else {
        $resourceLocation = $resourceGroup.Location
    }

    $clientAppName = (Read-Host -Prompt "Enter the name of the application registration: (blank for 'Finance Data Lake Application')")
    if ($clientAppName.Trim() -eq '') {
        $clientAppName = 'Finance Data Lake Application'
    }

    Write-Output '================================================================================='

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    $MicrosoftDynamicsERPMicroservicesAppObjectId = $service.ObjectId

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesCDSAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Format-Table -AutoSize
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    $aibuilderAuthorizationServiceObjectId = $service.ObjectId

    Write-Output '================================================================================='

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $clientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $clientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($clientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $clientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($defaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    $deployment = New-AzResourceGroupDeployment -ResourceGroupName $resourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId

    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $resourceGroupName)
    }

    Write-Output '================================================================================='

    $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
    Write-Output "Values for LCS Data Lake Add-In:"
    Write-Output ("  Tenant ID:                         " + $subscriptionContext.Context.Subscription.TenantId)
    Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
    Write-Output "  Storage account secret name:       storage-account-name"
    Write-Output "  Application ID secret name:        app-id"
    Write-Output "  Application Secret secret name:    app-secret"
    Write-Warning "Copy this information for the LCS Add-in as it is not saved. Azure Cloud Shell will eventually time out and close."

    Write-Output '================================================================================='
    Write-Output "Values for System parameters > Data connections:"
    Write-Output ("  Application ID:                    " + $clientAppId)
    Write-Output ("  Application Secret:                " + $ClientAppSecret)
    Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
    Write-Output "  Secret name:                       storage-account-connection-string"
    Write-Warning "Copy this information for the System parameters as it is not saved. Azure Cloud Shell will eventually time out and close."
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message
  Write-Warning $_.Exception.StackTrace
  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}

```
---

## <a name="configure-the-entity-store"></a><span data-ttu-id="c6a92-302">Konfigurera entitetsarkivet</span><span class="sxs-lookup"><span data-stu-id="c6a92-302">Configure the entity store</span></span>

<span data-ttu-id="c6a92-303">Följ dessa steg för att konfigurera entitetsarkivet i Finance-miljön.</span><span class="sxs-lookup"><span data-stu-id="c6a92-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="c6a92-304">Gå till **Systemadministration \> Konfigurera \> Systemparametrar \> Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="c6a92-305">Ange alternativet **Aktivera Data Lake-integrering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="c6a92-306">Ange följande nyckelvalvsfält:</span><span class="sxs-lookup"><span data-stu-id="c6a92-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="c6a92-307">**Program-ID (klient)** – Ange programmets klient-ID som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="c6a92-308">**Programhemlighet** – Ange hemligheten som du sparade för programmet du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="c6a92-309">**DNS-namn** – Du hittar DNS-namnet (Domain Name System) på sidan med programinformation för programmet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="c6a92-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="c6a92-310">**Hemligt namn** – Ange **lagringskontots anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="c6a92-311">Konfigurera datasjön</span><span class="sxs-lookup"><span data-stu-id="c6a92-311">Configure the data lake</span></span>

<span data-ttu-id="c6a92-312">Följ dessa steg för att använda LCS för att lägga till Azure Data Lake-tillägget i miljön.</span><span class="sxs-lookup"><span data-stu-id="c6a92-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="c6a92-313">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="c6a92-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="c6a92-314">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="c6a92-315">Välj tillägget **Exportera till data Lake**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="c6a92-316">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="c6a92-316">Enter the following values.</span></span>

    | <span data-ttu-id="c6a92-317">Värde</span><span class="sxs-lookup"><span data-stu-id="c6a92-317">Value</span></span>                                                              | <span data-ttu-id="c6a92-318">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c6a92-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="c6a92-319">Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns</span><span class="sxs-lookup"><span data-stu-id="c6a92-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="c6a92-320">Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns.</span><span class="sxs-lookup"><span data-stu-id="c6a92-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="c6a92-321">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="c6a92-322">Ange DNS-namnet på ditt Key Vault</span><span class="sxs-lookup"><span data-stu-id="c6a92-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="c6a92-323">Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="c6a92-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="c6a92-324">(Det här värdet matchar DNS-namnet som används i entitetsarkivet.)</span><span class="sxs-lookup"><span data-stu-id="c6a92-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="c6a92-325">Ange hemligheten som innehåller namnet på lagringskontot</span><span class="sxs-lookup"><span data-stu-id="c6a92-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="c6a92-326">**lagringskontonamn**</span><span class="sxs-lookup"><span data-stu-id="c6a92-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="c6a92-327">Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake</span><span class="sxs-lookup"><span data-stu-id="c6a92-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="c6a92-328">**program-ID**</span><span class="sxs-lookup"><span data-stu-id="c6a92-328">**app-id**</span></span> |
    | <span data-ttu-id="c6a92-329">Hemligt namn som ska användas med program-ID</span><span class="sxs-lookup"><span data-stu-id="c6a92-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="c6a92-330">**programhemlighet**</span><span class="sxs-lookup"><span data-stu-id="c6a92-330">**app-secret**</span></span> |

5. <span data-ttu-id="c6a92-331">Godkänn villkoren och välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="c6a92-332">Tillägget kommer att installeras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="c6a92-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="c6a92-333">Konfigurera AI Builder</span><span class="sxs-lookup"><span data-stu-id="c6a92-333">Configure AI Builder</span></span>

1. <span data-ttu-id="c6a92-334">Logga in på LCS och öppna sidan **Miljöinformation**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="c6a92-335">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="c6a92-336">De tillägg som redan är installerade i den här miljön bör visas.</span><span class="sxs-lookup"><span data-stu-id="c6a92-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="c6a92-337">Om tillägget **Exportera till Data Lake** inte är bland dem konfigurerar du det här tillägget.</span><span class="sxs-lookup"><span data-stu-id="c6a92-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="c6a92-338">Välj tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="c6a92-339">Ange följande värden på informationssidan för tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="c6a92-340">Värde</span><span class="sxs-lookup"><span data-stu-id="c6a92-340">Value</span></span>                                                    | <span data-ttu-id="c6a92-341">beskrivning</span><span class="sxs-lookup"><span data-stu-id="c6a92-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="c6a92-342">URL för CDS-organisations</span><span class="sxs-lookup"><span data-stu-id="c6a92-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="c6a92-343">Common Data Service-organisationens URL för Common Data Service-instansen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-343">The Common Data Service organization URL of the Common Data Service instance.</span></span> <span data-ttu-id="c6a92-344">Du hittar det här värdet genom att öppna [Power Apps-portalen](https://make.powerapps.com), välja knappen **Inställningar** (kugghjulet) i det övre högra hörnet, välja **Avancerade inställningar** och kopiera URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="c6a92-345">(URL:en slutar med "dynamics.com.")</span><span class="sxs-lookup"><span data-stu-id="c6a92-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="c6a92-346">CDS Org-ID</span><span class="sxs-lookup"><span data-stu-id="c6a92-346">CDS Org ID</span></span>                                               | <span data-ttu-id="c6a92-347">Miljö-ID för Common Data Service-instansen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-347">The environment ID of the Common Data Service instance.</span></span> <span data-ttu-id="c6a92-348">Du hittar det här värdet genom att öppna [Power Apps-portalen](https://make.powerapps.com), välja knappen **Inställningar** (kugghjulet) i det övre högra hörnet, välja **Anpassningar \> Utvecklarresurser \> Instansens referensinformation** och kopiera **ID**-värdet.</span><span class="sxs-lookup"><span data-stu-id="c6a92-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="c6a92-349">CDS klientorganisations-ID (katalog-ID från AAD)</span><span class="sxs-lookup"><span data-stu-id="c6a92-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="c6a92-350">Klientorganisations-ID för Common Data Service-instansen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-350">The tenant ID of the Common Data Service instance.</span></span> <span data-ttu-id="c6a92-351">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="c6a92-352">Ange användarobjekt-ID som har rollen systemadministratör</span><span class="sxs-lookup"><span data-stu-id="c6a92-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="c6a92-353">Azure AD-användarobjekt-ID för användaren i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c6a92-353">The Azure AD user object ID of the user in Common Data Service.</span></span> <span data-ttu-id="c6a92-354">Den här användaren måste vara systemadministratör för Common Data Service-instansen.</span><span class="sxs-lookup"><span data-stu-id="c6a92-354">This user must be a system administrator of the Common Data Service instance.</span></span> <span data-ttu-id="c6a92-355">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory \> Användare**, välja användaren och i avsnittet **Identitet** kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="c6a92-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="c6a92-356">Är det här standard-CDS-miljön för klientorganisationen?</span><span class="sxs-lookup"><span data-stu-id="c6a92-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="c6a92-357">Markera den här kryssrutan om Common Data Service-instansen var den första produktionsinstans som skapades.</span><span class="sxs-lookup"><span data-stu-id="c6a92-357">If the Common Data Service instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="c6a92-358">Avmarkera den här kryss rutan om Common Data Service-instansen skapades manuellt.</span><span class="sxs-lookup"><span data-stu-id="c6a92-358">If the Common Data Service instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="c6a92-359">Feedback och support</span><span class="sxs-lookup"><span data-stu-id="c6a92-359">Feedback and support</span></span>

<span data-ttu-id="c6a92-360">Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.</span><span class="sxs-lookup"><span data-stu-id="c6a92-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="c6a92-361">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="c6a92-361">Privacy notice</span></span>

<span data-ttu-id="c6a92-362">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="c6a92-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
