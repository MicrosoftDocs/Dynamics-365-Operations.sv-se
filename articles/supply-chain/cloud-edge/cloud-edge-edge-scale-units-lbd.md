---
title: Distribuera kantskalenheter på anpassad maskinvara med hjälp av LBD
description: I denna artikel beskrivs hur du tillhandahåller lokala kantskalningsenheter genom att använda anpassad maskinvara och distribution som baseras på lokala affärsdata (LBD).
author: Mirzaab
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 794de8c0d77949789e4046418ac2b55dba1bee02
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882762"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Distribuera kantskalenheter på anpassad maskinvara med hjälp av LBD

[!include [banner](../includes/banner.md)]

Kantskalningsenheter har en viktig roll i den distribuerade topologin för Supply Chain Management. I hybridtopologin kan du fördela arbetsbelastningar mellan din Supply Chain Management-molnhubb och ytterligare skalningsenheter i molnet eller på kanten.

Kantskalningsenheter kan distribueras genom att du skapar en lokal miljö för affärsdata (LBD) [lokal miljö](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) och sedan konfigurerar den till att fungera som skalningsenhet i din distribuerade hybrida topologi för Supply Chain Management. Detta uppnås genom att associera den lokala LBD-miljön med en Supply Chain Management-miljö i molnet, som har konfigurerats för att fungera somen hubb.  

I denna artikel beskrivs hur du konfigurerar en lokal LBD-miljö som en kantskalningsenhet och sedan associerar den med en hubb.

## <a name="infrastructure-considerations"></a>Att tänka på i infrastruktur

Kantskalningsenheter körs i lokala miljöer, så infrastrukturkraven liknar varandra. Det finns dock vissa skillnader som bör noteras:

- Kantskalningsenheter använder inte Financial Reporting, så de kräver inte Financial Reporting-noder.
- Tillverknings- och lagringsarbetsbelastningarna är inte resurskrävande, så du bör överväga att beräkna datorkraften för AOS-noder på samma sätt.

## <a name="deployment-overview"></a>Distributionsöversikt

Här finns en översikt av distributionsstegen.

1. **Aktivera en LBD-plats i ditt LBD-projekt i Microsoft Dynamics Lifecycle Services (LCS).**

1. **Ställ in och distribuera en LBD-miljö med en *tom* databas.**

    Använd LCS för att distribuera LBD-miljön med den senaste topologin och en tom databas. Mer information finns i avsnittet [Konfigurera och distribuera en LBD-miljö med en tom databas](#set-up-deploy) längre fram i den här artikeln. Du måste använda Supply Chain Management version 10.0.21 eller senare i samtliga hubb- och skalningsenhetsmiljöer.

1. **Ladda upp målpaket till LBD-projekttillgångar i LCS.**

    Förbered program-, plattforms- och anpassningspaket som du använder i hela hubben och vågen och kantskalningsenhet. För mer information, se avsnittet [Ladda upp målpaket till LBD-projekttillgångar i LCS](#upload-packages) senare i den här artikeln.

1. **Service av LBD-miljön med målpaketen.**

    Detta steg säkerställer att samma version och anpassningar distribueras på hubb och eker. Mer information finns i avsnittet [Serva LBD-miljön med målpaket](#service-target-packages) längre fram i den här artikeln.

1. **Slutför konfigurationen av skalningsenhet och arbetsbelastningstilldelningen.**

    Mer information finns i avsnittet [Tilldela din LBD-kantskalningsenhet till en hubb](#assign-edge-to-hub) senare i den här artikeln.

Övriga avsnitt i den här artikeln innehåller mer information om hur du slutför dessa steg.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Ställ in och distribuera en LBD-miljö med en tom databas

Med det här steget skapas en funktionell LBD-miljö. Däremot behöver inte miljön nödvändigtvis ha samma program- och plattformsversioner som hubbmiljö. Dessutom saknar den fortfarande anpassningar och har ännu inte aktiverats som en skalningsenhet.

1. Följ anvisningarna i [Ställa in och distribuera lokala miljöer (plattformsuppdatering 41 och senare)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Du måste använda Supply Chain Management version 10.0.21 eller senare i samtliga hubb- och skalningsenhetsmiljöer. Du måste dessutom använda version 2.12.0 eller senare av infrastrukturskripten. 

    > [!IMPORTANT]
    > Läs resten av det här avsnittet **innan** du går igenom stegen i artikeln.

1. Innan du beskriver din konfiguration i filen infrastructure\\ConfigTemplate.xml, kör följande skript:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Det här skriptet tar bort konfigurationer som inte behövs för distribution av kantskalningsenheter.

1. Skapa en databas som innehåller tomma data enligt beskrivningen i [Konfigurera databaser](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Använd den tomma data.bak-filen för det här steget.
1. När du har slutfört steget [Konfigurera databaser](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) kör du följande skript för att konfigurera Scale Unit Alm Orchestrator-databasen.

    > [!NOTE]
    > Konfigurera inte Financial Reporting-databasen under steget [Konfigurera databaser](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    I skriptet Initialize-Database.ps1 utförs följande åtgärder:

    1. Skapa en tom databas med namnet **ScaleUnitAlmDb**.
    2. Mappa användarna till databasroller, baserat på följande tabell.

        | Användare            | Typ | Databasroll |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_ägare     |

1. Fortsätt med att följa anvisningarna i [Konfigurera och distribuera lokala miljöer (plattformsuppdatering 41 och senare)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. När du har slutfört steget [Konfigurera AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) gör du följande:

    1. Skapa ett nytt AD FS-program (Active Directory Federation Services) som gör det möjligt för Alm-orkestreringstjänsten att kommunicera med programobjektservern (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Skapa ett nytt Azure Active Directory (Azure AD)-program som gör det möjligt för Alm-orkestreringstjänsten att kommunicera med hanteringstjänsten för skalningsenheter.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Fortsätt med att följa anvisningarna i [Konfigurera och distribuera lokala miljöer (plattformsuppdatering 41 och senare)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). När du måste ange konfigurationen för den lokala agenten ska du se till att du aktiverar funktionerna för kantskalningsenhet och tillhandahåller alla parametrar som krävs.

    ![Aktivera funktioner för kantskalningsenhet.](media/EnableEdgeScaleUnitFeatures.png "Aktivera funktioner för kantskalningsenhet.")

1. Innan du distribuerar din miljö från LCS måste du konfigurera fördistributionsskriptet. För mer information, se [Skripts för lokal agent för fördistribution och efterdistribution](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Kopiera skriptet Configure-CloudAndEdge.ps1 från mappen **Skalningsenhet** i **Infrastrukturskript** till mappen **Skript** i agentens fillagringsutrymme som konfigurerats i miljön. En typisk sökväg är \\\\lbdiscsi01\\agent\\Scripts.
    2. Skapa det **PreDefordyment.ps1**-skript som aktiverar skripten genom att använda de parametrar som krävs. Fördistributionsskriptet måste finnas i mappen **Skript** i lagringsresursen för agentfilen. Annars kan den inte köras. En typisk sökväg är \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Innehållet i skriptet PreDedemyment.ps1 liknar följande exempel.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > InstanceId-parametern får endast användas med två tecken. Det första tecknet är @ och det andra kan vara en kapitalbokstav i det engelska alfabetet.
        >
        > - Giltiga värden:
        >   - @D
        >   - @X
        > - Inte giltiga värden:
        >   - @a
        >   - @4
        >   - @#

1. Distribuera miljön genom att använda den senaste bastopologin som finns.
1. Följ dessa steg när miljön har distribuerats:

    1. Kör följande SQL-kommandon på din affärsdatabas (AXDB):

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Öka samtidig maximal batchsession till ett värde som överstiger 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Kontrollera att ändringsspårning har aktiverats i din affärsdatabas (AXDB).

        1. Öppna SQL Server Management Studio (SSMS).
        1. Markera och håll inne (eller högerklicka på) din affärsdatabas (AXDB) och välj sedan **Egenskaper**.
        1. I fönstret som öppnas väljer du **Ändringsspårning** och anger sedan följande värden:

            - **Ändringsspårning:** *Sant*
            - **Lagringsperiod:** *7*
            - **Kvarhållningsenheter:** *dagar*
            - **Automatisk rensning:** *Sant*

    1. Lägg till det program-ID för AD FS som du skapade tidigare (genom att använda skriptet Create-ADFSServerApplicationForEdgeScaleUnits.ps1) i tabellen för Azure AD-program i din skalningsenhet. Du kan utföra detta steg manuellt via användargränssnittet (UI). Alternativt kan du fylla i det via databasen genom att använda följande skript:

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Konfigurera ett Azure Key V och ett Azure AD-program för att aktivera kommunikation mellan skalningsenheter

1. När din miljö har distribuerats skapar du ett ytterligare Azure AD-program för att aktivera betrodd kommunikation mellan din hubb och skalningsenhet.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. När du har skapat programmet måste du skapa en klienthemlighet och spara informationen i ett Azure-nyckelvalv. Dessutom måste du bevilja åtkomst till det Azure AD-program som skapats så att detta kan hämta de hemligheter som lagrats i nyckelvalvet. För att underlätta för dig utför följande skript automatiskt alla nödvändiga åtgärder:

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Om inget nyckelvalv besitter angivet värde för **KeyVaultName** kommer skriptet automatiskt att skapa ett.

1. Lägg till det program-ID för Azure AD som du just skapat (vid användnign av skriptet Create-SpokeToHubAADApplication.ps1) i programtabellen för Azure AD i din hubb. Du kan utföra detta steg manuellt via användargränssnittet.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Ladda upp målpaket till LBD-projekttillgångar i LCS

Det här steget förbereder applikationsversionen, plattformsversionen och anpassningarna som kommer att överföras till din LBD-skalningsenhetsmiljö.

1. För över samma kombinerade program-/plattformspaket som har tillämpats för arbetsmiljön till tillgångsbiblioteket i LCS-projektet på lokal nivå.
1. Få en kopia av anpassade paket som kan distribueras som har tillämpats för arbetsmiljön och ladda upp det till tillgångsbiblioteket i LCS-projektet på lokal nivå.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Service av LBD-miljön med målpaketen

Det här steget justerar applikationsversionen, plattformsversionen och anpassningarna i din LBD-skalningsenhetsmiljö med hubben.

1. Service av LBD-miljön med det kombinerade program-/plattformspaketet som du överförde i det föregående steget.
1. Service av LBD-miljön med det anpassade paketet som kan distribueras som du överförde i det föregående steget.

    ![Tillämpa uppdateringar i LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Tillämpa uppdateringar i LCS")

    ![Välja ditt anpassningspaket.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Välja ditt anpassningspaket")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Tilldela din LBD-kantskalningsenhet till en hubb

Du konfigurerar och hanterar kantskalningsenheten via hanteringsportalen för skalningsenheter. Mer information finns i [Hantera skalningsenheter och arbetsbelastningar med hjälp av hanteringsportalen för skalningsenheter](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
