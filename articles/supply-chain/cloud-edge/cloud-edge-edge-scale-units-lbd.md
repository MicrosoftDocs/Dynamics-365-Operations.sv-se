---
title: Distribuera kantskalningsenheter på anpassad maskinvara med hjälp av LBD (förhandsversion)
description: I det här avsnittet beskrivs hur du provision på lokal kantskalningsenheter genom att använda anpassad maskinvara och distribution som baseras på lokala företagsdata (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678991"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Distribuera kantskalningsenheter på anpassad maskinvara med hjälp av LBD (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

Kantskalningsenheter har en viktig roll i den distribuerade topologin för Supply Chain Management. I hybridtopologin kan du fördela arbetsbelastningar mellan ditt Supply Chain Management molnnav och ytterligare skalningsenheter i molnet eller på kanten.

Kantskalningsenheter kan distribueras genom att du skapar en lokal miljö för affärsdata (LBD) [lokal miljö](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) och sedan konfigurerar den till att fungera som skalningsenhet i din distribuerade hybrida topologi för Supply Chain Management. Detta uppnås genom att associera den lokala LBD-miljön med en Supply Chain Management-miljö i molnet, som har konfigurerats för att fungera som ett nav.  

Kantskalningsenheter förhandsgranskas just nu. Därför får du endast använda en miljö av den här typen enligt [förhandsgranskningsvillkoren](https://aka.ms/scmcnepreviewterms).

I det här avsnittet beskrivs hur du ställer in en lokal LBD-miljö som en kantskalningsenhet och kopplar den till ett nav.

## <a name="deployment-overview"></a>Distributionsöversikt

Här finns en översikt av distributionsstegen.

1. **Aktivera en LBD-plats i ditt LBD-projekt i Microsoft Dynamics Lifecycle Services (LCS).**

    Under förhandsgranskningen riktar sig LBD-kantskalningsenheter till befintliga LBD-kunder. Ytterligare en 60-dagars begränsad LBD-plats kommer endast att tillhandahållas i vissa kundsituationer.

1. **Ställ in och distribuera en LBD-miljö med en *tom* databas.**

    Använd LCS för att distribuera LBD-miljön med den senaste topologin och en tom databas. Mer information finns i avsnittet [Ställ in och distribuera en LBD-miljö med en tom databas](#set-up-deploy) längre fram i det här avsnittet. Du måste använda Supply Chain Management version 10.0.19 med plattformsuppdatering 43 eller högre i alla enhetsmiljöer.

1. **Ladda upp målpaket till LBD-projekttillgångar i LCS.**

    Förbered program-, plattforms- och anpassningspaket som du använder i hela hubben och vågen och kantskalningsenhet. För mer information, se avsnittet [Ladda upp målpaket till LBD-projekttillgångar i LCS](#upload-packages) senare i det här avsnittet.

1. **Service av LBD-miljön med målpaketen.**

    Detta steg säkerställer att samma version och anpassningar distribueras på hubb och eker. Mer information finns i avsnittet [Serva LBD-miljön med målpaket](#service-target-packages) längre fram i det här avsnittet.

1. **Slutför konfigurationen av skalningsenhet och arbetsbelastningstilldelningen.**

    Mer information finns i avsnittet [Tilldela din LBD kantskalningsenhet till en hubb](#assign-edge-to-hub) senare i det här ämnet.

Övriga avsnitt i det här avsnittet innehåller mer information om hur du slutför dessa steg.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Ställ in och distribuera en LBD-miljö med en tom databas

Med det här steget skapas en funktionell LBD-miljö. Däremot behöver inte miljön nödvändigtvis ha samma program- och plattformsversioner som hubbmiljö. Dessutom saknar den fortfarande anpassningar och har ännu inte aktiverats som en skalningsenhet.

1. Följ anvisningarna i [Ställa in och distribuera lokala miljöer (plattformsuppdatering 41 och senare)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Du måste använda Supply Chain Management version 10.0.19 med plattformsuppdatering 43 eller högre i alla enhetsmiljöer

    > [!IMPORTANT]
    > Läs resten av det här avsnittet **innan** du går igenom stegen i det avsnittet.

1. Innan du beskriver din konfiguration i filen infrastructure\\ConfigTemplate.xml, kör följande skript:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Det här skriptet tar bort konfigurationer som inte behövs för distribution av kantskalningsenheter.

1. Skapa en databas som innehåller tomma data enligt beskrivningen i [Konfigurera databaser](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Använd den tomma data.bak-filen för det här steget.
1. Ställ in ett fördistributionsskript. För mer information, se [Skripts för lokal agent för fördistribution och efterdistribution](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Kopiera innehållet från mappen **ScaleUnit** i **Infrastrukturskript** till mappen **Skript** i agentfillagringsandelen som konfigurerades i miljön. En typisk sökväg är \\\\lbdiscsi01\\agent\\Scripts.
    2. Skapa det **PreDefordyment.ps1**-skript som aktiverar skripten genom att använda de parametrar som krävs. Fördistributionsskriptet måste finnas i mappen **Skript** i lagringsresursen för agentfilen. Annars kan den inte köras. En typisk sökväg är \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Innehållet i skriptet PreDedemyment.ps1 liknar följande exempel.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Ladda upp målpaket till LBD-projekttillgångar i LCS

Det här steget förbereder applikationsversionen, plattformsversionen och anpassningarna som kommer att överföras till din LBD-skalningsenhetsmiljö.

1. För över samma kombinerade program-/plattformspaket som har tillämpats för arbetsmiljön till tillgångsbiblioteket i LCS-projektet på lokal nivå.
1. Få en kopia av anpassade paket som kan distribueras som har tillämpats för arbetsmiljön och ladda upp det till tillgångsbiblioteket i LCS-projektet på lokal nivå.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Service av LBD-miljön med målpaketen

Det här steget justerar applikationsversionen, plattformsversionen och anpassningarna i din LBD-skalningsenhetsmiljö med hubben.

1. Service av LBD-miljön med det kombinerade program-/plattformspaketet som du överförde i det föregående steget.
1. Service av LBD-miljön med det anpassade paketet som kan distribueras som du överförde i det föregående steget.

    ![Välja Underhåll > Tillämpa uppdateringar i LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Välja Underhåll > Tillämpa uppdateringar i LCS")

    ![Välja ditt anpassningspaket.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Välja ditt anpassningspaket")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Tilldela din LBD-kantskalningsenhet till en hubb

När kantskalningsenheter fortfarande är i förhandsgranskning måste du använda [verktygen för skalningsenhet och konfiguration](https://github.com/microsoft/SCMScaleUnitDevTools) som är tillgängliga i GitHub för att tilldela din LBD-kantskalningsenhet till en hubb. Med hjälp av den här processen kan LBD-konfiguration fungera som en kantskalningsenhet och associerar den med den. Den här processen liknar konfigurering av en utvecklingsmiljö med en ruta.

1. Hämta den senaste versionen av [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) och ta bort innehållet i filen.
1. Skapa en kopia av `UserConfig.sample.xml` filen och ge den ett namn `UserConfig.xml`.
1. Skapa en Microsoft Azure Active Directory (Azure AD) app i din Azure AD klientorganisation som du nämnde i [Implementeringsguide för skalningsenhet och laster](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. När du har skapat det navigerar du till Azure AD programformuläret (SysAADClientTable) på din hubb.
    1. Skapa en ny post och ange **klient-ID** för programmet du skapade. Ställ in **Namn** till *ScaleUnits* och **Användar-ID** till *Admin*.

1. Skapa en Active Directory Federation Service (AD FS) app som nämns i [Riktlinjer för distribution för skalningsenhet och laster](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. När du har skapat det navigerar du till Azure AD programformuläret (SysAADClientTable) på din kantskalningsenhet.
    1. Skapa en ny post och ange **klient-ID** för programmet du skapade. Ange **Användar-ID** till *Admin*.

1. Ändra `UserConfig.xml` filen.
    1. Under avsnittet `InterAOSAADConfiguration` anger du informationen från Azure AD-appen du skapade tidigare.
        - I elementet `AppId` ange app-ID för Azure-appen.
        - I elementet `AppSecret` ange apphemlighet för Azure-appen.
        - Elementet `Authority` måste innehålla URL:en som anger säkerhetsmyndighet för din innehavare.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. Under avsnittet `ScaleUnitConfiguration` för den första `ScaleUnitInstance`, ändra avsnittet `AuthConfiguration`.
        - I elementet `AppId` ange app-ID för Azure-appen.
        - I elementet `AppSecret` ange apphemlighet för Azure-appen.
        - Elementet `Authority` måste innehålla URL:en som anger säkerhetsmyndighet för din innehavare.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Dessutom, för samma `ScaleUnitInstance`, ange följande värden:
        - I `Domain` element ange URL:en för din hubb. Till exempel: `https://cloudhub.sandbox.operations.dynamics.com/`
        - I `EnvironmentType` element, se till att värdet `LCSHosted` anges.

    1. Under avsnittet `ScaleUnitConfiguration` för den andra `ScaleUnitInstance`, ändra avsnittet `AuthConfiguration`.
        - I elementet `AppId` ange app-ID för AD FS-appen.
        - I elementet `AppSecret` ange apphemlighet för AD FS-appen.
        - Elementet `Authority` måste innehålla URL-adressen till AD FS-instansen.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Dessutom, för samma `ScaleUnitInstance`, ange följande värden:
        - I `Domain` element ange URL:en för din kantskalningsenhet. Till exempel: https://ax.contoso.com/
        - I `EnvironmentType` element, se till att värdet LBD anges.
        - I `ScaleUnitId` element, mata in samma värde som du angav för `InstanceId` när du konfigurerar `Configure-CloudandEdge.ps1` fördistributionsskriptet.

        > [!NOTE]
        > Om du inte använder standard-ID:t (@A;) måste du uppdatera ScaleUnitId för varje ConfiguredWorkload under avsnittet Arbetsbelastningar.

1. Öppna PowerShell och navigera till mappen som innehåller `UserConfig.xml` filen.

1. Kör verktyget med det här kommandot.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Efter varje åtgärd måste du starta verktyget igen.

1. I verktyget, välj **2. Förbered miljöer för installation av arbetsbelastning**. Kör sedan följande steg:
    1. Välj **1. Förbered hubben**.
    1. Välj **2. Förbered skalningsenhet**.

    > [!NOTE]
    > Om du inte kör det här kommandot från en ren installation och den misslyckas, ska du utföra följande åtgärder:
    >
    > - Ta bort alla mappar från `aos-storage` mappen (förutom `GACAssemblies`).
    > - Kör följande SQL-kommando på din affärsdatabas (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Kör följande SQL-kommandon på din affärsdatabas (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Kontrollera att spårning av ändringar har aktiverats i din affärsdatabas (AXDB)
    1. Starta SQL Server Management Studio (SSMS).
    1. Högerklicka på din affärsdatabas (AXDB) och välj egenskaper.
    1. Välj **Ändra spårning** i fönstret som öppnas och gör följande inställningar:

        - **Ändringsspårning:** *Sant*
        - **Lagringsperiod:** *7*
        - **Kvarhållningsenheter:** *dagar*
        - **Automatisk rensning:** *Sant*

1. I verktyget, välj **3. Installera laster**. Kör sedan följande steg:
    1. Välj **1. Installera på hubb**.
    1. Välj **2. Installera på skalningsenhet**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
