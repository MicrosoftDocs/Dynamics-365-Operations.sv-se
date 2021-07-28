---
title: Konfiguration för Finance Insights – före version 10.0.19
description: I detta ämne beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Finance Insights för versioner före 10.0.19.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 6b578962839a34a1e2ce0311f7d8e7ee57a10927
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357448"
---
# <a name="configuration-for-finance-insights-for-private-preview-preview---before-version-10019"></a>Konfiguration för Finance Insights för privat förhandsgranskning (förhandsversion) – före version 10.0.19.

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Följande procedurer för hur du ställer in Finance Insights gäller för Microsoft Dynamics 365 Finance före version 10.0.19. Mer information om hur du ställer in Finance Insights i version 10.0.20 och senare finns i [Konfiguration för Finance Insights (förhandsversion) – versioner 10.0.20 och senare](configure-for-fin-insites-PubPrvw.md).

Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Microsoft Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen. I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.

## <a name="deploy-dynamics-365-finance"></a>Distribuera Dynamics 365 Finance

Följ dessa steg för att distribuera miljöerna.

1. I Microsoft Dynamics Lifecycle Services (LCS), skapa eller uppdatera en Dynamics 365 Finance-miljö. Miljön kräver programversion 10.0.11/Platform update 35 eller senare.
2. Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö. (Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Om du konfigurerar Finance Insights i en sandbox-miljö måste du kanske kopiera produktionsdata till den miljön för att förutsägelser ska fungera. I modellen för förutsägelse används flera års data för att skapa förutsägelser. Contoso-demodatan innehåller inte tillräckligt historiska data för att mata förutsägelsemodellen tillräckligt mycket. 

## <a name="configure-dataverse"></a>Konfigurera Dataverse

Använd följande steg för att konfigurera Dataverse för Finance insights.

1. Öppna miljösidan i LCS och kontrollera att avsnittet **Power Platform**-integration redan har ställts in.
    1. Om den redan är inställd ska Dataverse-miljön som är länkat till Dynamics 365 Finance-miljön visas i listan. Kopiera namnet på Dataverse-miljön.
    2. Om den inte är inställd följer du dessa steg:
        1. Välj knappen **Inställningar** i avsnittet Power Platform-integrering. Det kan ta upp till en timme innan miljön kan ställas in.
        2. Om Dataverse-miljön har ställts in bör det Dataverse-miljönamn som kopplats till Dynamics 365 Finance-miljön listas. Kopiera namnet på Dataverse-miljön.
> [!NOTE]
> När miljön är klar väljer du **INTE** knappen **Koppla till CDS for Apps**. Detta behövs inte för Finance Insights och kommer att inaktivera möjligheten att slutföra de erforderliga miljötilläggen i LCS.

2. Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/) och skapa en ny Dataverse-miljö i samma Active Directory-klientorganisation genom att följa stegen nedan:

    1. Öppna sidan **Miljöer**.

        [![Sidan Miljöer.](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Välj Dataverse-miljön som skapats ovan och välj sedan **Inställningar**.
    3. Välj **Resurser \> Alla äldre inställningar**.
    4. Välj **Inställningar** i det övre navigeringsfältet och välj **Anpassningar**.
    5. Välj **Utvecklarresurser**.
    6. Kopiera värdet för **Organisations-ID för Dataverse**.
    7. Notera URL:en till Dataverse-organisationen i webbläsarens adressfält. URL-adressen kan till exempel vara `https://org42b2b3d3.crm.dynamics.com`.

3. Om du planerar att använda kassaflödesprognoser eller budgetprognoser, följer du dessa steg för att uppdatera anteckningsgränsen för organisationen till minst 50 MB:

    1. Öppna [Power Apps-portal](https://make.powerapps.com).
    2. Välj den miljö som du just har skapat och välj sedan **Avancerade inställningar**.
    3. Välj **Inställningar \> E-postkonfiguration**.
    4. Ändra värdet för fältet **Maximal filstorlek** till **51 200**. (Värdet uttrycks i kilobyte \[KB\].)
    5. Välj **OK** för att spara ändringarna.

## <a name="configure-the-azure-setup"></a>Konfigurera Azure-inställningen

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Ange Dataverse-katalog-ID och användarens Azure AD-objekt-ID

1. Ange Dataverse-katalog-ID:

    1. Öppna [Azure-portalen](https://portal.azure.com).
    2. Logga in genom att använda det användar-ID som användes för att skapa Dataverse-miljön.
    3. Gå till **Azure Active Directory**.
    4. Kopiera värdet för **Klientorganisations-ID**.

2. Ange användarens Azure Active Directory-objekt-ID (Azure AD):

    1. I [Azure-portalen](https://portal.azure.com), gå till **Användare** och sök efter användaren via e-postadressen.
    2. Välj användarens namn.
    3. Kopiera värdet för **Objekt-ID**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser

# <a name="use-a-windows-powershell-script"></a>[Använd ett Windows PowerShell-skript](#tab/use-a-powershell-script)

Ett Windows PowerShell-skript har angetts så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Om du föredrar att göra manuella inställningar hoppar du över den här proceduren och fortsätter med proceduren i avsnittet [Manuell konfiguration](#manual-setup).

> [!NOTE]
> Kör PowerShell-skriptet genom att följa stegen nedan. Azure CLI-alternativet "Pröva" eller att köra skriptet på datorn fungerar kanske inte.

Följ dessa steg för att konfigurera Azure med hjälp av Windows PowerShell-skriptet. Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program. Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration. Välj knappen **Cloud Shell** till höger om fältet **Sök**.
2. Välj **PowerShell**.
3. Skapa lagringsutrymme om du uppmanas göra det.
4. Gå till fliken **Azure CLI** och välj **Kopiera**.  
5. Öppna Anteckningar och klistra in PowerShell-skriptet. Spara filen som ConfigureDataLake.ps1.
6. Ladda upp Windows PowerShell-skriptet till sessionen med hjälp av menyalternativet för uppladdning Cloud Shell.
7. Kör skriptet .\ConfigureDataLake.ps1.
8. Kör skriptet genom att följa anvisningarna.
9. Installera tillägget **Exportera till Data Lake** i LCS med hjälp av informationen i skriptets utdata.
10. Använd informationen från skriptets utdata för att aktivera entitetsarkivet på sidan **Dataanslutningar** i Finance (**Systemadministration \> Systemparametrar \> Dataanslutningar**).

### <a name="manual-setup"></a>Manuell konfiguration

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Lägg till program i Azure AD-klientorganisationen

1. I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.
2. Välj **Hantera \> Företagsprogram**.
3. Sök efter följande program med app-ID.

    | Ansökning                              | App-ID                               |
    |------------------------------------------|--------------------------------------|
    | Microsoft Dynamics ERP Microservices     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | Microsoft Dynamics ERP Microservices CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | AI Builder Authorization Service         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Om du inte hittar något av ovanstående program gör du på följande sätt.

1. Välj **Start**-menyn och sök efter **powershell** på den lokala datorn.
2. Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.
3. Kör följande kommando för att installera modulen **AzureAD**.

    `Install-Module -Name AzureAD`

4. Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.
5. Om meddelandet "Untrusted repository" (Ej betrodd lagringsplats) visas väljer du **Y** för att fortsätta.
6. Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD. Logga in som Azure AD-administratör när du uppmanas till det.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Skapa Azure-resurser

> [!NOTE]
> Se till att du skapar följande resurser i samma Azure AD-instans som Dataverse-miljön. Du kan inte använda resurser från en annan Azure AD-instans.

1. Skapa ett nytt lagringskonto:

    1. Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).
    2. I dialogrutan **Skapa lagringskonto**, ställ in följande fält:

        - **Plats** – Välj det datacenter där din miljö finns.
        - **Prestanda** – Vi rekommenderar att du väljer **Standard**.
        - **Kontotyp** – Du måste välja **StorageV2**.

    3. I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**. Om du inaktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som Power BI-dataflöden.
    4. Välj **Granska och skapa**. När distributionen har slutförts visas den nya resursen i Azure-portalen.
    5. Gå till det lagringskonto som du har skapat.
    6. Välj **Åtkomstnycklar** i menyn till vänster.
    7. Kopiera och spara anslutningssträngen för antingen **Key1** eller **Key2**.
    8. Kopiera och spara namnet på lagringskontot.

2. Skapa en ny nyckelvalvresurs:

    1. Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).
    2. I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.
    3. När nyckelvalvet har skapats väljer du det i listan och väljer sedan **Hemligheter**.
    4. Välj **Generera/Importera**.
    5. I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
    6. Ange ett namn på hemligheten. Anteckna namnet eftersom du kommer att behöva ange det senare.
    7. I fältet **Värde** anger du den anslutningssträng som du hämtade från lagringskontot i föregående procedur.
    8. Välj **Aktiverat** och välj sedan **Skapa**. Hemligheten skapas och läggs till i nyckelvalvet.
    9. Gå till **nyckelvalvöversikten** och anteckna DNS-namnet.

3. Skapa och registrera ett Azure AD-program:

    1. I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.
    2. Välj **Ny programregistrering** och ange följande fält:

        - **Namn** – Ange namnet på appen.
        - **Programtyp** – Välj **Webb-API**.
        - **Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**. Du måste ange det här värdet senare när du konfigurerar nyckelvalvet.
    4. Gå till **API-behörigheter** och gör så här:

        1. Välj **Lägg till behörighet**.
        2. Välj **Azure Key Vault**.
        3. När du har valt delegerade behörigheter väljer du **användare\_personifiering**.
        4. Välj **Lägg till behörigheter**.

    5. På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:

        1. Välj **Ny klienthemlighet**.
        2. Ange ett namn i fältet **Nyckelbeskrivning**.
        3. Markera en varaktighet och välj sedan **Lägg till**. En hemlighet genereras i fältet **Värde**.
        4. Kopiera och spara det hemliga värdet.

4. Skapa nyckelvalvhemligheter:

    1. Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.
    2. Gör så här för varje hemligt namn i följande tabell:

        1. Välj **Generera/Importera**.
        2. I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
        3. Skapa det hemliga namnet och värdet från följande tabell.
        4. Välj **Aktiverat** och välj sedan **Skapa**. Hemligheten skapas och läggs till i nyckelvalvet.

        | Hemligt namn                       | Hemligt värde                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | program-ID                            | App-ID för programmet som du skapade tidigare                                      |
        | programhemlighet                        | Klienthemligheten som du sparade tidigare                                                    |
        | lagringskontonamn              | Namnet på lagringskontot som du skapade tidigare, t.ex. **lagringskonto1**       |
        | lagringskontots anslutningssträng | Den anslutningssträng som du kopierade från sidan **Åtkomstnycklar** för lagringskontot |

5. Auktorisera programmet för att få åtkomst till nyckelvalvet:

    1. I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.
    2. Välj åtkomstprinciper.
    3. Gör så här för varje program i följande tabell:

        1. Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.
        2. I fältet **Hemliga behörigheter**, välj behörigheterna från följande tabell.
        3. I fältet **Välj huvudnamn**, sök efter programmets visningsnamn från följande tabell.
        4. Välj **Välj**.
        5. Markera **Lägg till**.
        6. Välj **Spara**.

        | Ansökning                                              | Behörighet |
        |----------------------------------------------------------|-------------|
        | Visningsnamnet för det nya program som du skapade | Get, List   |
        | **Microsoft Dynamics ERP Microservices**                 | Get, List   |

6. Tilldela roller för åtkomst till lagringskontot:

    1. I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.
    2. Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.
    3. Välj **Lägg till, Lägg till rolltilldelning**.
    4. Gör så här för varje program i följande tabell:

        1. Välj rollen bland i följande tabell.
        2. Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.
        3. I fältet **Välj**, ange programmet från följande tabell.
        4. Välj **Spara**.

        | Ansökning                                              | Roll                        |
        |----------------------------------------------------------|-----------------------------|
        | Visningsnamnet för det nya program som du skapade | Ägare                       |
        | Visningsnamnet för det nya program som du skapade | Deltagare                 |
        | Visningsnamnet för det nya program som du skapade | Lagringskontodeltagare |
        | Visningsnamnet för det nya program som du skapade | Storage Blob Data-ägare     |
        | **AI Builder Authorization Service**                     | Storage Blob Data-läsare    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a>Konfigurera datasjön

Följ dessa steg för att använda LCS för att lägga till Azure Data Lake-tillägget i miljön.

1. Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.
2. I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.
3. Välj tillägget **Exportera till data Lake**.
4. Ange följande värden.

    | Värde                                                              | beskrivning |
    |--------------------------------------------------------------------|-------------|
    | Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns | Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns. Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**. |
    | Ange DNS-namnet på ditt Key Vault                             | Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`. (Det här värdet matchar DNS-namnet som används i entitetsarkivet.) |
    | Ange hemligheten som innehåller namnet på lagringskontot   | **lagringskontonamn** |
    | Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake          | **program-ID** |
    | Hemligt namn som ska användas med program-ID                                 | **programhemlighet** |

5. Godkänn villkoren och välj **Installera**.

Tillägget kommer att installeras inom några minuter.

## <a name="configure-ai-builder"></a>Konfigurera AI Builder

1. Logga in på LCS och öppna sidan **Miljöinformation**.
2. Bläddra till avsnittet **Miljötillägg**. De tillägg som redan är installerade i den här miljön bör visas. Om tillägget **Exportera till Data Lake** inte är bland dem konfigurerar du det här tillägget.
3. Välj tillägget **Hämta insikter**.
4. Ange följande värden på informationssidan för tillägget **Hämta insikter**.

    | Värde                                                    | beskrivning |
    |----------------------------------------------------------|-------------|
    | URL för CDS-organisations                                     | Dataverse-organisationens URL kopierat från ovan. |
    | CDS Org-ID                                               | Dataverse-organisationens ID kopierat från ovan. |
5. Aktivera **Är detta standardmiljön för din klientorganisation**.

Tillägget kan ta flera minuter att installera.
    
## <a name="configure-the-entity-store"></a>Konfigurera entitetsarkivet

Följ dessa steg för att konfigurera entitetsarkivet i Finance-miljön.

1. Gå till **Systemadministration \> Konfigurera \> Systemparametrar \> Dataanslutningar**.
2. Ange följande nyckelvalvsfält:

    - **Program-ID (klient)** – Ange programmets klient-ID som du skapade tidigare.
    - **Programhemlighet** – Ange hemligheten som du sparade för programmet du skapade tidigare.
    - **DNS-namn** – Du hittar DNS-namnet (Domain Name System) på sidan med programinformation för programmet som du skapade tidigare.
    - **Hemligt namn** – Ange **lagringskontots anslutningssträng**.
3. Aktivera **Aktivera Data Lake-integrering**.
4. Välj **Testa Azure Key Vault** och kontrollera att det inte finns några fel.
5. Välj **Testa Azure-lagring** och kontrollera att det inte finns några fel.

## <a name="feedback-and-support"></a>Feedback och support

Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
