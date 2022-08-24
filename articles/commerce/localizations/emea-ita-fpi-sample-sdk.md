---
title: Implementeringsriktlinjer för integreringsexempel för kvittoskrivare för Italien (äldre)
description: Denna artikel ger riktlinjer för distribution av integreringsexempel för kvittoskrivare för Italien från utvecklingspaketet för detaljhandelsprogramvara för Microsoft Dynamics 365 Commerce (SDK).
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 9e951c1a1ee5c967d2bd67941ff3d19c62b59ba6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279550"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>Implementeringsriktlinjer för integreringsexempel för kvittoskrivare för Italien (äldre)

[!include[banner](../includes/banner.md)]

Denna artikel ger riktlinjer för distribution av integreringsexempel för kvittoskrivare för Italien från utvecklingspaketet för detaljhandelsprogramvara för Microsoft Dynamics 365 Commerce (SDK) på en virtuell dator för utvecklare i Microsoft Dynamics Lifecycle Services (LCS). Mer information om exemplet på räkenskapsintegrering finns i [Exempel på integrering av kvittoskrivare för Italien](emea-ita-fpi-sample.md). 

Exemplet på skatteintegrering för Italien ingår i Retail SDK. Information om hur du installerar och använder SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md). Det här exemplet består av tillägg för Commerce Runtime (CRT), kassa och Hardware Station. Om du vill köra det här exemplet måste du ändra och bygga CRT och Hardware Station-projekt. Vi rekommenderar att du använder en icke-modifierad detaljhandels-SDK för att utföra de ändringar som beskrivs i denna artikel. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Azure DevOps, där inga filer har ändrats ännu.

## <a name="development-environment"></a>Utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.

### <a name="commerce-runtime-extension-components"></a>Utbyggbarhetskomponenter för Commerce Runtime

CRT tilläggskomponenter inkluderas i Retail SDK. För att slutföra följande procedurer, öppna **CommerceRuntimeSamples.sln** lösningen under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** och skapa det.
2. I mappen **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. Starta om Commerce Scale Unit:

    - **Commerce Scale Unit:** Starta om Commerce Scale Unit-webbplatsen från IIS Manager.
    - **Klientmäklare:** Avsluta **dllhost.exe** process Uppgiftshanteraren och starta sedan om Modern POS.

### <a name="hardware-station-extension-components"></a>Tilläggskomponenter för Hardware Station

Hardware Station tilläggskomponenter inkluderas i Retail SDK. För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Leta upp projektet **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** och skapa det.
2. I mappen **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Kopiera sammansättningsfilen till en distribuerad Hardware Station-maskinen:

    - **Fjärrstyrd Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Lokal Hardware station:** Kopiera filen till Modern POS-klientmäklarplatsen.

4. Leta reda på konfigurationsfilen för Hardware Station-tillägg. Filen heter **HardwareStation.Extension.config**:

    - **Fjärrstyrd Hardware Station** : filen finns under IIS Hardware Station webbplatsen.
    - **Lokal Hardware Station:** filen finns under platsen för Modern POS Client Broker.

5. Lägg till följande avsnitt i avsnittet **sammansättning** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Starta om tjänsten Hardware Station:

    - **Fjärrstyrd Hardware Station** : Starta om Hardware Station webbplatsen från IIS Manager.
    - **Lokal Hardware Station:** Avsluta **dllhost.exe** process Uppgiftshanteraren och starta sedan om Modern POS.

## <a name="production-environment"></a>Produktionsmiljö

För att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö följ dessa steg.

1. Slutför stegen som beskrivs i avsnittet [Utvecklingsmiljö](#development-environment) i denna artikel.
2. Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:

    1. I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    1. I konfigurationsfilen **HardwareStation.Extension.config** lägg till följande rad i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:

    1. Lägg till följande rad om du vill inkludera CRT-tilläggen i de distribuerbara paketen.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    1. Lägg till följande rad om du vill inkludera Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Gör följande ändringar i filen **Sdk.ModernPos.Shared.csproj** under mappen **Packages\_SharedPackagingProjectComponents** för att inkludera resursfilerna för Italien i distributionsbara paket:

    1. Lägg till **ItemGroup**-avsnitt som innehåller noder som pekar på resursfilerna för de önskade översättningarna. Se till att du anger korrekta namnutrymder och exempelnamn. I följande exempel läggs resursnoder till för språken **it** och **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. I avsnittet **Target Name="CopyPackageFiles"** lägger du till en rad för respektive språk enligt följande exempel.

        ```xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it-CH" SkipUnchangedFiles="true" />
        ```

5. Gör följande ändringar i filen **Sdk.RetailServerSetup.proj** under mappen **Packages\_SharedPackagingProjectComponents** för att inkludera resursfilerna för Italien i distributionsbara paket:

    1. Lägg till **ItemGroup**-avsnitt som innehåller noder som pekar på resursfilerna för de önskade översättningarna. Se till att du anger korrekta namnutrymder och exempelnamn. I följande exempel läggs resursnoder till för språken **it** och **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. I avsnittet **Target Name="CopyPackageFiles"** lägger du till en rad för respektive språk enligt följande exempel.

        ``` xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it-CH" SkipUnchangedFiles="true" />
        ```

6. Starta MSBuild-Kommandotolken för Visual Studio-verktyget och kör **msbuild** under mappen Retail SDK för att skapa distribuerbara paket.
7. Tillämpa paketen via LCS eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Design av tilläggen

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera utskriftspecifika dokument och hantera svar från räkenskapsregistreringsutskrift.

CRT-tillägget är **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Mer information om design av lösningen av räkenskapsintegrering finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegrering för kvittoskrivarenheter och tjänster](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Begärandehanterare

**DocumentProviderEpsonFP90III** begäranhanteraren är ingångspunkten för begäran om att generera dokument från kvittoskrivaren.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett utskriftsspecifikt dokument som ska registreras i kvittoskrivaren.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport och utskrift av Z-rapport.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- Mappning av momskoder
- Mappning av momssatser
- Mappning av betalningsmedelstyp
- Streckkodstyp för kvittonummer
- Betalningstyp för insättning

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kvittoskrivare.

Hardware Station-tillägget **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. Tillägg HTTP-protokollet för att skicka dokument som CRT-tillägget genererar till kvittoskrivare. Den hanterar också svar som tas emot från kvittoskrivare.

#### <a name="request-handler"></a>Begärandehanterare

**EpsonFP90IIISample** begäranhanteraren är startpunkten för hantering av begäranden till kringutrustning för räkenskaper.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till skrivare och returnerar svaret från kvittoskrivaren.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av enheten.
- **InitializeFiscalDeviceRequest** – Denna begäran används för skrivarinitiering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med filen är att aktivera inställningar för anslutningsprogram som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- **Slutpunktsadress** – Skrivarens URL.
- **Datum- och tidssynkronisering** – Ett värde som anger om datum och tid för skrivaren måste synkroniseras med den anslutna maskinvaran.
