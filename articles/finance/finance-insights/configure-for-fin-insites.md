---
title: Konfiguration för Finance-insikter (förhandsversion)
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
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cf29e3c05f9fdcc685017a4c640ef32c40989c73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208567"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="81a60-103">Konfiguration för Finance-insikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="81a60-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="81a60-104">Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Microsoft Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen.</span><span class="sxs-lookup"><span data-stu-id="81a60-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="81a60-105">I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="81a60-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="81a60-106">Distribuera Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="81a60-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="81a60-107">Följ dessa steg för att distribuera miljöerna.</span><span class="sxs-lookup"><span data-stu-id="81a60-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="81a60-108">I Microsoft Dynamics Lifecycle Services (LCS), skapa eller uppdatera en Dynamics 365 Finance-miljö.</span><span class="sxs-lookup"><span data-stu-id="81a60-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="81a60-109">Miljön kräver programversion 10.0.11/Platform update 35 eller senare.</span><span class="sxs-lookup"><span data-stu-id="81a60-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="81a60-110">Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="81a60-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="81a60-111">(Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="81a60-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="81a60-112">Om du använder Contoso-demo data behöver du ytterligare exempeldata för att kunna använda funktionerna för kundbetalningsförutsägelser, kassaflödesprognoser och budgetprognoser.</span><span class="sxs-lookup"><span data-stu-id="81a60-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="81a60-113">Konfigurera Dataverse</span><span class="sxs-lookup"><span data-stu-id="81a60-113">Configure Dataverse</span></span>

<span data-ttu-id="81a60-114">Du kan slutföra de manuella konfigurationsstegen som följer eller så kan du påskynda konfigurationen med hjälp av det Windows PowerShell-skript som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="81a60-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="81a60-115">När PowerShell-skriptet har körts klart får du tillgång till värden som används för att konfigurera Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="81a60-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="81a60-116">Kör skriptet genom att öppna PowerShell på datorn.</span><span class="sxs-lookup"><span data-stu-id="81a60-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="81a60-117">Du kan behöva PowerShell version 5.</span><span class="sxs-lookup"><span data-stu-id="81a60-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="81a60-118">Microsoft Azure CLI-alternativet "Pröva" kanske inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="81a60-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="81a60-119">Manuella konfigurationssteg</span><span class="sxs-lookup"><span data-stu-id="81a60-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="81a60-120">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/) och skapa en ny Dataverse-miljö i samma Active Directory-klientorganisation genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="81a60-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="81a60-121">Öppna sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="81a60-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="81a60-122">[![Sidan Miljöer](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="81a60-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="81a60-123">Välj **Ny miljö**.</span><span class="sxs-lookup"><span data-stu-id="81a60-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="81a60-124">I fältet **Typ**, välj **Sandbox**.</span><span class="sxs-lookup"><span data-stu-id="81a60-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="81a60-125">Ange alternativet **Skapa databas** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81a60-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="81a60-126">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81a60-126">Select **Next**.</span></span>
    6. <span data-ttu-id="81a60-127">Välj språk och valuta för organisationen.</span><span class="sxs-lookup"><span data-stu-id="81a60-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="81a60-128">Acceptera standardvärden i övriga fält.</span><span class="sxs-lookup"><span data-stu-id="81a60-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="81a60-129">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="81a60-129">Select **Save**.</span></span>
    9. <span data-ttu-id="81a60-130">Uppdatera sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="81a60-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="81a60-131">Vänta tills värdet i **Tillstånd** har uppdaterats till **Klart**.</span><span class="sxs-lookup"><span data-stu-id="81a60-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="81a60-132">Gör en notering om Dataverse-organisations-ID.</span><span class="sxs-lookup"><span data-stu-id="81a60-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="81a60-133">Välj miljön och välj **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="81a60-134">Välj **Resurser \> Alla äldre inställningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="81a60-135">Välj **Inställningar** i det övre navigeringsfältet och välj **Anpassningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="81a60-136">Välj **Utvecklarresurser**.</span><span class="sxs-lookup"><span data-stu-id="81a60-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="81a60-137">Ställ in fältet för **instansens referensensinformations-ID** till organisations-ID-värdet för Dataverse som du noterade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-137">Set the **Instance Reference Information ID** field to the Dataverse organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="81a60-138">Notera URL:en till Dataverse-organisationen i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="81a60-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="81a60-139">URL-adressen kan till exempel vara `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="81a60-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="81a60-140">Om du planerar att använda kassaflödesprognoser eller budgetprognoser, följer du dessa steg för att uppdatera anteckningsgränsen för organisationen till minst 50 MB:</span><span class="sxs-lookup"><span data-stu-id="81a60-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="81a60-141">Öppna [Power Apps-portal](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="81a60-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="81a60-142">Välj den miljö som du just har skapat och välj sedan **Avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="81a60-143">Välj **Inställningar \> E-postkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="81a60-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="81a60-144">Ändra värdet för fältet **Maximal filstorlek** till **51 200**.</span><span class="sxs-lookup"><span data-stu-id="81a60-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="81a60-145">(Värdet uttrycks i kilobyte \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="81a60-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="81a60-146">Välj **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="81a60-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="81a60-147">Konfigurationsskript för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81a60-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

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

## <a name="configure-the-azure-setup"></a><span data-ttu-id="81a60-148">Konfigurera Azure-inställningen</span><span class="sxs-lookup"><span data-stu-id="81a60-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="81a60-149">Ange Dataverse-katalog-ID och användarens Azure AD-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="81a60-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="81a60-150">Ange Dataverse-katalog-ID:</span><span class="sxs-lookup"><span data-stu-id="81a60-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="81a60-151">Öppna [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="81a60-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="81a60-152">Logga in genom att använda det användar-ID som användes för att skapa Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="81a60-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="81a60-153">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="81a60-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="81a60-154">Kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="81a60-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="81a60-155">Ange användarens Azure Active Directory-objekt-ID (Azure AD):</span><span class="sxs-lookup"><span data-stu-id="81a60-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="81a60-156">I [Azure-portalen](https://portal.azure.com), gå till **Användare** och sök efter användaren via e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="81a60-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="81a60-157">Välj användarens namn.</span><span class="sxs-lookup"><span data-stu-id="81a60-157">Select the user's name.</span></span>
    3. <span data-ttu-id="81a60-158">Kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="81a60-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="81a60-159">Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser</span><span class="sxs-lookup"><span data-stu-id="81a60-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="81a60-160">Använd ett Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="81a60-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="81a60-161">Ett Windows PowerShell-skript har angetts så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="81a60-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="81a60-162">Om du föredrar att göra manuella inställningar hoppar du över den här proceduren och fortsätter med proceduren i avsnittet [Manuell konfiguration](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="81a60-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="81a60-163">Kör PowerShell-skriptet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="81a60-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="81a60-164">Azure CLI-alternativet "Pröva" eller att köra skriptet på datorn fungerar kanske inte.</span><span class="sxs-lookup"><span data-stu-id="81a60-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="81a60-165">Följ dessa steg för att konfigurera Azure med hjälp av Windows PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="81a60-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="81a60-166">Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program.</span><span class="sxs-lookup"><span data-stu-id="81a60-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="81a60-167">Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="81a60-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="81a60-168">I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="81a60-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="81a60-169">Välj knappen **Cloud Shell** till höger om fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="81a60-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="81a60-170">Välj **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="81a60-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="81a60-171">Skapa lagringsutrymme om du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="81a60-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="81a60-172">Ladda sedan upp Windows PowerShell-skriptet till sessionen.</span><span class="sxs-lookup"><span data-stu-id="81a60-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="81a60-173">Kör skriptet.</span><span class="sxs-lookup"><span data-stu-id="81a60-173">Run the script.</span></span>
5. <span data-ttu-id="81a60-174">Kör skriptet genom att följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="81a60-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="81a60-175">Installera tillägget **Exportera till Data Lake** i LCS med hjälp av informationen i skriptets utdata.</span><span class="sxs-lookup"><span data-stu-id="81a60-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="81a60-176">Använd informationen från skriptets utdata för att aktivera entitetsarkivet på sidan **Dataanslutningar** i Finance (**Systemadministration \> Systemparametrar \> Dataanslutningar**).</span><span class="sxs-lookup"><span data-stu-id="81a60-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="81a60-177">Manuell konfiguration</span><span class="sxs-lookup"><span data-stu-id="81a60-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="81a60-178">Lägg till program i Azure AD-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="81a60-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="81a60-179">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="81a60-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="81a60-180">Välj **Hantera \> Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="81a60-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="81a60-181">Sök efter följande program med app-ID.</span><span class="sxs-lookup"><span data-stu-id="81a60-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="81a60-182">Ansökning</span><span class="sxs-lookup"><span data-stu-id="81a60-182">Application</span></span>                              | <span data-ttu-id="81a60-183">App-ID</span><span class="sxs-lookup"><span data-stu-id="81a60-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="81a60-184">Microsoft Dynamics ERP Microservices</span><span class="sxs-lookup"><span data-stu-id="81a60-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="81a60-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="81a60-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="81a60-186">Microsoft Dynamics ERP Microservices CDS</span><span class="sxs-lookup"><span data-stu-id="81a60-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="81a60-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="81a60-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="81a60-188">AI Builder Authorization Service</span><span class="sxs-lookup"><span data-stu-id="81a60-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="81a60-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="81a60-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="81a60-190">Om du inte hittar något av ovanstående program gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="81a60-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="81a60-191">Välj **Start**-menyn och sök efter **powershell** på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="81a60-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="81a60-192">Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="81a60-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="81a60-193">Kör följande kommando för att installera modulen **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="81a60-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="81a60-194">Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.</span><span class="sxs-lookup"><span data-stu-id="81a60-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="81a60-195">Om meddelandet "Untrusted repository" (Ej betrodd lagringsplats) visas väljer du **Y** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="81a60-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="81a60-196">Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="81a60-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="81a60-197">Logga in som Azure AD-administratör när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="81a60-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="81a60-198">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="81a60-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="81a60-199">Se till att du skapar följande resurser i samma Azure AD-instans som Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="81a60-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="81a60-200">Du kan inte använda resurser från en annan Azure AD-instans.</span><span class="sxs-lookup"><span data-stu-id="81a60-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="81a60-201">Skapa ett nytt lagringskonto:</span><span class="sxs-lookup"><span data-stu-id="81a60-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="81a60-202">Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="81a60-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="81a60-203">I dialogrutan **Skapa lagringskonto**, ställ in följande fält:</span><span class="sxs-lookup"><span data-stu-id="81a60-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="81a60-204">**Plats** – Välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="81a60-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="81a60-205">**Prestanda** – Vi rekommenderar att du väljer **Standard**.</span><span class="sxs-lookup"><span data-stu-id="81a60-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="81a60-206">**Kontotyp** – Du måste välja **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="81a60-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="81a60-207">I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**.</span><span class="sxs-lookup"><span data-stu-id="81a60-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="81a60-208">Om du inaktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som Power BI-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="81a60-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="81a60-209">Välj **Granska och skapa**.</span><span class="sxs-lookup"><span data-stu-id="81a60-209">Select **Review and create**.</span></span> <span data-ttu-id="81a60-210">När distributionen har slutförts visas den nya resursen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="81a60-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="81a60-211">Gå till det lagringskonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="81a60-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="81a60-212">Välj **Åtkomstnycklar** i menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="81a60-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="81a60-213">Kopiera och spara anslutningssträngen för antingen **Key1** eller **Key2**.</span><span class="sxs-lookup"><span data-stu-id="81a60-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="81a60-214">Kopiera och spara namnet på lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="81a60-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="81a60-215">Skapa en ny nyckelvalvresurs:</span><span class="sxs-lookup"><span data-stu-id="81a60-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="81a60-216">Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="81a60-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="81a60-217">I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="81a60-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="81a60-218">När nyckelvalvet har skapats väljer du det i listan och väljer sedan **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="81a60-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="81a60-219">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="81a60-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="81a60-220">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="81a60-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="81a60-221">Ange ett namn på hemligheten.</span><span class="sxs-lookup"><span data-stu-id="81a60-221">Enter a name for the secret.</span></span> <span data-ttu-id="81a60-222">Anteckna namnet eftersom du kommer att behöva ange det senare.</span><span class="sxs-lookup"><span data-stu-id="81a60-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="81a60-223">I fältet **Värde** anger du den anslutningssträng som du hämtade från lagringskontot i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="81a60-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="81a60-224">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="81a60-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="81a60-225">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="81a60-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="81a60-226">Gå till **nyckelvalvöversikten** och anteckna DNS-namnet.</span><span class="sxs-lookup"><span data-stu-id="81a60-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="81a60-227">Skapa och registrera ett Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="81a60-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="81a60-228">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="81a60-229">Välj **Ny programregistrering** och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="81a60-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="81a60-230">**Namn** – Ange namnet på appen.</span><span class="sxs-lookup"><span data-stu-id="81a60-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="81a60-231">**Programtyp** – Välj **Webb-API**.</span><span class="sxs-lookup"><span data-stu-id="81a60-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="81a60-232">**Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="81a60-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="81a60-233">Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="81a60-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="81a60-234">Du måste ange det här värdet senare när du konfigurerar nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="81a60-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="81a60-235">Gå till **API-behörigheter** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="81a60-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="81a60-236">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="81a60-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="81a60-237">Välj **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="81a60-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="81a60-238">När du har valt delegerade behörigheter väljer du **användare\_personifiering**.</span><span class="sxs-lookup"><span data-stu-id="81a60-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="81a60-239">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="81a60-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="81a60-240">På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="81a60-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="81a60-241">Välj **Ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="81a60-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="81a60-242">Ange ett namn i fältet **Nyckelbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="81a60-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="81a60-243">Markera en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="81a60-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="81a60-244">En hemlighet genereras i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="81a60-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="81a60-245">Kopiera och spara det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="81a60-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="81a60-246">Skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="81a60-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="81a60-247">Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="81a60-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="81a60-248">Gör så här för varje hemligt namn i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="81a60-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="81a60-249">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="81a60-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="81a60-250">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="81a60-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="81a60-251">Skapa det hemliga namnet och värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="81a60-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="81a60-252">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="81a60-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="81a60-253">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="81a60-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="81a60-254">Hemligt namn</span><span class="sxs-lookup"><span data-stu-id="81a60-254">Secret name</span></span>                       | <span data-ttu-id="81a60-255">Hemligt värde</span><span class="sxs-lookup"><span data-stu-id="81a60-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="81a60-256">program-ID</span><span class="sxs-lookup"><span data-stu-id="81a60-256">app-id</span></span>                            | <span data-ttu-id="81a60-257">App-ID för programmet som du skapade tidigare</span><span class="sxs-lookup"><span data-stu-id="81a60-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="81a60-258">programhemlighet</span><span class="sxs-lookup"><span data-stu-id="81a60-258">app-secret</span></span>                        | <span data-ttu-id="81a60-259">Klienthemligheten som du sparade tidigare</span><span class="sxs-lookup"><span data-stu-id="81a60-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="81a60-260">lagringskontonamn</span><span class="sxs-lookup"><span data-stu-id="81a60-260">storage-account-name</span></span>              | <span data-ttu-id="81a60-261">Namnet på lagringskontot som du skapade tidigare, t.ex. **lagringskonto1**</span><span class="sxs-lookup"><span data-stu-id="81a60-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="81a60-262">lagringskontots anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="81a60-262">storage-account-connection-string</span></span> | <span data-ttu-id="81a60-263">Den anslutningssträng som du kopierade från sidan **Åtkomstnycklar** för lagringskontot</span><span class="sxs-lookup"><span data-stu-id="81a60-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="81a60-264">Auktorisera programmet för att få åtkomst till nyckelvalvet:</span><span class="sxs-lookup"><span data-stu-id="81a60-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="81a60-265">I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="81a60-266">Välj åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="81a60-266">Select the access policies.</span></span>
    3. <span data-ttu-id="81a60-267">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="81a60-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="81a60-268">Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="81a60-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="81a60-269">I fältet **Hemliga behörigheter**, välj behörigheterna från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="81a60-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="81a60-270">I fältet **Välj huvudnamn**, sök efter programmets visningsnamn från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="81a60-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="81a60-271">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="81a60-271">Select **Select**.</span></span>
        5. <span data-ttu-id="81a60-272">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="81a60-272">Select **Add**.</span></span>
        6. <span data-ttu-id="81a60-273">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="81a60-273">Select **Save**.</span></span>

        | <span data-ttu-id="81a60-274">Ansökning</span><span class="sxs-lookup"><span data-stu-id="81a60-274">Application</span></span>                                              | <span data-ttu-id="81a60-275">Behörighet</span><span class="sxs-lookup"><span data-stu-id="81a60-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="81a60-276">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="81a60-276">The display name of the new application that you created</span></span> | <span data-ttu-id="81a60-277">Get, List</span><span class="sxs-lookup"><span data-stu-id="81a60-277">Get, List</span></span>   |
        | <span data-ttu-id="81a60-278">**Microsoft Dynamics ERP Microservices**</span><span class="sxs-lookup"><span data-stu-id="81a60-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="81a60-279">Get, List</span><span class="sxs-lookup"><span data-stu-id="81a60-279">Get, List</span></span>   |

6. <span data-ttu-id="81a60-280">Tilldela roller för åtkomst till lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="81a60-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="81a60-281">I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="81a60-282">Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="81a60-283">Välj **Lägg till, Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="81a60-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="81a60-284">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="81a60-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="81a60-285">Välj rollen bland i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="81a60-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="81a60-286">Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.</span><span class="sxs-lookup"><span data-stu-id="81a60-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="81a60-287">I fältet **Välj**, ange programmet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="81a60-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="81a60-288">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="81a60-288">Select **Save**.</span></span>

        | <span data-ttu-id="81a60-289">Ansökning</span><span class="sxs-lookup"><span data-stu-id="81a60-289">Application</span></span>                                              | <span data-ttu-id="81a60-290">Roll</span><span class="sxs-lookup"><span data-stu-id="81a60-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="81a60-291">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="81a60-291">The display name of the new application that you created</span></span> | <span data-ttu-id="81a60-292">Ägare</span><span class="sxs-lookup"><span data-stu-id="81a60-292">Owner</span></span>                       |
        | <span data-ttu-id="81a60-293">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="81a60-293">The display name of the new application that you created</span></span> | <span data-ttu-id="81a60-294">Deltagare</span><span class="sxs-lookup"><span data-stu-id="81a60-294">Contributor</span></span>                 |
        | <span data-ttu-id="81a60-295">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="81a60-295">The display name of the new application that you created</span></span> | <span data-ttu-id="81a60-296">Lagringskontodeltagare</span><span class="sxs-lookup"><span data-stu-id="81a60-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="81a60-297">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="81a60-297">The display name of the new application that you created</span></span> | <span data-ttu-id="81a60-298">Storage Blob Data-ägare</span><span class="sxs-lookup"><span data-stu-id="81a60-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="81a60-299">**AI Builder Authorization Service**</span><span class="sxs-lookup"><span data-stu-id="81a60-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="81a60-300">Storage Blob Data-läsare</span><span class="sxs-lookup"><span data-stu-id="81a60-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="81a60-301">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="81a60-301">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
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

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
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

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
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
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}

```
---

## <a name="configure-the-entity-store"></a><span data-ttu-id="81a60-302">Konfigurera entitetsarkivet</span><span class="sxs-lookup"><span data-stu-id="81a60-302">Configure the entity store</span></span>

<span data-ttu-id="81a60-303">Följ dessa steg för att konfigurera entitetsarkivet i Finance-miljön.</span><span class="sxs-lookup"><span data-stu-id="81a60-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="81a60-304">Gå till **Systemadministration \> Konfigurera \> Systemparametrar \> Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="81a60-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="81a60-305">Ange alternativet **Aktivera Data Lake-integrering** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="81a60-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="81a60-306">Ange följande nyckelvalvsfält:</span><span class="sxs-lookup"><span data-stu-id="81a60-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="81a60-307">**Program-ID (klient)** – Ange programmets klient-ID som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="81a60-308">**Programhemlighet** – Ange hemligheten som du sparade för programmet du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="81a60-309">**DNS-namn** – Du hittar DNS-namnet (Domain Name System) på sidan med programinformation för programmet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="81a60-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="81a60-310">**Hemligt namn** – Ange **lagringskontots anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="81a60-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="81a60-311">Konfigurera datasjön</span><span class="sxs-lookup"><span data-stu-id="81a60-311">Configure the data lake</span></span>

<span data-ttu-id="81a60-312">Följ dessa steg för att använda LCS för att lägga till Azure Data Lake-tillägget i miljön.</span><span class="sxs-lookup"><span data-stu-id="81a60-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="81a60-313">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="81a60-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="81a60-314">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="81a60-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="81a60-315">Välj tillägget **Exportera till data Lake**.</span><span class="sxs-lookup"><span data-stu-id="81a60-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="81a60-316">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="81a60-316">Enter the following values.</span></span>

    | <span data-ttu-id="81a60-317">Värde</span><span class="sxs-lookup"><span data-stu-id="81a60-317">Value</span></span>                                                              | <span data-ttu-id="81a60-318">beskrivning</span><span class="sxs-lookup"><span data-stu-id="81a60-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="81a60-319">Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns</span><span class="sxs-lookup"><span data-stu-id="81a60-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="81a60-320">Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns.</span><span class="sxs-lookup"><span data-stu-id="81a60-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="81a60-321">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="81a60-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="81a60-322">Ange DNS-namnet på ditt Key Vault</span><span class="sxs-lookup"><span data-stu-id="81a60-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="81a60-323">Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="81a60-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="81a60-324">(Det här värdet matchar DNS-namnet som används i entitetsarkivet.)</span><span class="sxs-lookup"><span data-stu-id="81a60-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="81a60-325">Ange hemligheten som innehåller namnet på lagringskontot</span><span class="sxs-lookup"><span data-stu-id="81a60-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="81a60-326">**lagringskontonamn**</span><span class="sxs-lookup"><span data-stu-id="81a60-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="81a60-327">Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake</span><span class="sxs-lookup"><span data-stu-id="81a60-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="81a60-328">**program-ID**</span><span class="sxs-lookup"><span data-stu-id="81a60-328">**app-id**</span></span> |
    | <span data-ttu-id="81a60-329">Hemligt namn som ska användas med program-ID</span><span class="sxs-lookup"><span data-stu-id="81a60-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="81a60-330">**programhemlighet**</span><span class="sxs-lookup"><span data-stu-id="81a60-330">**app-secret**</span></span> |

5. <span data-ttu-id="81a60-331">Godkänn villkoren och välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="81a60-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="81a60-332">Tillägget kommer att installeras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="81a60-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="81a60-333">Konfigurera AI Builder</span><span class="sxs-lookup"><span data-stu-id="81a60-333">Configure AI Builder</span></span>

1. <span data-ttu-id="81a60-334">Logga in på LCS och öppna sidan **Miljöinformation**.</span><span class="sxs-lookup"><span data-stu-id="81a60-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="81a60-335">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="81a60-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="81a60-336">De tillägg som redan är installerade i den här miljön bör visas.</span><span class="sxs-lookup"><span data-stu-id="81a60-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="81a60-337">Om tillägget **Exportera till Data Lake** inte är bland dem konfigurerar du det här tillägget.</span><span class="sxs-lookup"><span data-stu-id="81a60-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="81a60-338">Välj tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="81a60-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="81a60-339">Ange följande värden på informationssidan för tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="81a60-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="81a60-340">Värde</span><span class="sxs-lookup"><span data-stu-id="81a60-340">Value</span></span>                                                    | <span data-ttu-id="81a60-341">beskrivning</span><span class="sxs-lookup"><span data-stu-id="81a60-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="81a60-342">URL för CDS-organisations</span><span class="sxs-lookup"><span data-stu-id="81a60-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="81a60-343">Dataverse-organisationens URL för Dataverse-instansen.</span><span class="sxs-lookup"><span data-stu-id="81a60-343">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="81a60-344">Du hittar det här värdet genom att öppna [Power Apps-portalen](https://make.powerapps.com), välja knappen **Inställningar** (kugghjulet) i det övre högra hörnet, välja **Avancerade inställningar** och kopiera URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="81a60-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="81a60-345">(URL:en slutar med "dynamics.com.")</span><span class="sxs-lookup"><span data-stu-id="81a60-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="81a60-346">CDS Org-ID</span><span class="sxs-lookup"><span data-stu-id="81a60-346">CDS Org ID</span></span>                                               | <span data-ttu-id="81a60-347">Miljö-ID för Dataverse-instansen.</span><span class="sxs-lookup"><span data-stu-id="81a60-347">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="81a60-348">Du hittar det här värdet genom att öppna [Power Apps-portalen](https://make.powerapps.com), välja knappen **Inställningar** (kugghjulet) i det övre högra hörnet, välja **Anpassningar \> Utvecklarresurser \> Instansens referensinformation** och kopiera **ID**-värdet.</span><span class="sxs-lookup"><span data-stu-id="81a60-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="81a60-349">CDS klientorganisations-ID (katalog-ID från AAD)</span><span class="sxs-lookup"><span data-stu-id="81a60-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="81a60-350">Klientorganisations-ID för Dataverse-instansen.</span><span class="sxs-lookup"><span data-stu-id="81a60-350">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="81a60-351">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="81a60-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="81a60-352">Ange användarobjekt-ID som har rollen systemadministratör</span><span class="sxs-lookup"><span data-stu-id="81a60-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="81a60-353">Azure AD-användarobjekt-ID för användaren i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="81a60-353">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="81a60-354">Den här användaren måste vara systemadministratör för Dataverse-instansen.</span><span class="sxs-lookup"><span data-stu-id="81a60-354">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="81a60-355">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory \> Användare**, välja användaren och i avsnittet **Identitet** kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="81a60-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="81a60-356">Är det här standard-CDS-miljön för klientorganisationen?</span><span class="sxs-lookup"><span data-stu-id="81a60-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="81a60-357">Markera den här kryssrutan om Dataverse-instansen var den första produktionsinstans som skapades.</span><span class="sxs-lookup"><span data-stu-id="81a60-357">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="81a60-358">Avmarkera den här kryss rutan om Dataverse-instansen skapades manuellt.</span><span class="sxs-lookup"><span data-stu-id="81a60-358">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="81a60-359">Feedback och support</span><span class="sxs-lookup"><span data-stu-id="81a60-359">Feedback and support</span></span>

<span data-ttu-id="81a60-360">Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.</span><span class="sxs-lookup"><span data-stu-id="81a60-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="81a60-361">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="81a60-361">Privacy notice</span></span>

<span data-ttu-id="81a60-362">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="81a60-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]