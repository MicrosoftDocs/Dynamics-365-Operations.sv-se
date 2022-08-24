---
title: Implementeringsriktlinjer för integreringsprovet för skatteregistreringstjänsten för Österrike (äldre)
description: Denna artikel ger riktlinjer för distribution av exemplet på räkenskapsintegrering för Österrike från Microsoft Dynamics 365 Commerce Retail Software Development kit (SDK).
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 203904f60888464a473cb2997652db497fba6f57
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276113"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-austria-legacy"></a>Implementeringsriktlinjer för integreringsprovet för skatteregistreringstjänsten för Österrike (äldre)

[!include [banner](../includes/banner.md)]

Denna artikel ger riktlinjer för distribution av exemplet på skatteregistreringstjänsten för Österrike från Microsoft Dynamics 365 Commerce Retail Software Development kit (SDK) på en virtuell dator för utvecklare (VM) i Microsoft Dynamics Lifecycle Services (LCS). Mer information om exemplet på räkenskapsintegrering finns i [Exempel på skatteregistreringstjänsten för Österrike](emea-aut-fi-sample.md). 

Exemplet på skatteintegrering för Österrike ingår i Retail SDK. Information om hur du installerar och använder SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md). Exemplet på skatteintegrering består av tillägg för Commerce Runtime (CRT), Hardware Station och kassa. Om du vill köra det här exemplet måste du ändra och bygga CRT, Hardware Station- och kassaprojekt. Vi rekommenderar att du använder en icke-modifierad detaljhandels-SDK för att utföra de ändringar som beskrivs i denna artikel. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Azure DevOps, där inga filer har ändrats ännu.

## <a name="development-environment"></a>Utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.

### <a name="enable-commerce-runtime-extensions"></a>Aktivera Commerce Runtime tillägg

CRT tilläggskomponenter inkluderas i CRT-exemplen. För att slutföra följande procedurer, öppna **CommerceRuntimeSamples.sln** lösningen under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>DocumentProvider.EFRSample-komponent

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.EFRSample** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>DocumentProvider.DataModelEFR-komponent

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.DataModelEFR** och skapa det.
2. I mappen **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Tilläggskonfigurationsfil

1. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

2. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Aktivera tillägg för anslutningsprogram för skatt

Du kan aktivera tillägg för anslutningsprogram för skatt i [maskinvarustationen](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) eller [kassaapparaten](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

#### <a name="enable-hardware-station-extensions"></a>Aktivera tilläggen för Hardware Station

Tilläggskomponenterna för Hardware Station ingår i Hardware Station exemplen. För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.

##### <a name="efrsample-component"></a>EFRSample-komponent

1. Leta upp projektet **HardwareStation.Extension.EFRSample** och skapa det.
2. I mappen **Extension.EFRSample\\bin\\Debug** hitta följande sammansättningsfiler:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Kopiera sammansättningsfilerna till Hardware Station-tilläggsmappen:

    - **Delad Hardware Station** : kopiera filerna till **binge**-mappen under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : kopiera filerna till platsen för Modern POS Client Broker.

4. Leta reda på tilläggskonfigurationsfilen för Hardware Station-tillägg. Filen heter **HardwareStation.Extension.config**.

    - **Delad Hardware Station** : filen är under IIS Hardware Station webbplatsen.
    - **Dedikerad Hardware Station på Modern POS** : filen är under platsen för Modern POS Client Broker.

5. Lägg till följande rad i avsnittet **sammansättning** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>Aktivera kassatillägg

Kassatilläggsexemplet finns i mappen **src\\FiscalIntegration\\PosFiscalConnectorSample** i databasen [Dynamics 365 Commerce-lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/).

För att tillämpa exemplet för kassatillägg i äldre SDK, följ dessa steg.

1. Kopiera mappen **Pos.Extension** till mappen **Tillägg** för kassa i äldre SDK (till exempel `C:\RetailSDK\src\POS\Extensions`).
1. Byt namn på kopian av **Pos.Extension**-mappen **PosFiscalConnector**.
1. Ta bort följande mappar och filer från mappen **PosFiscalConnector**:

    - bin
    - DataService
    - devDependencies
    - Bibliotek
    - obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Öppna lösningen **CloudPos.sln** eller **ModernPos.sln**.
1. I projektet **Pos.Extensions** inkluderar du mappen **PosFiscalConnector**.
1. Öppna filen **extensions.json** och lägg till filnamnstillägget **PosFiscalConnector**.
1. Skapa SDK.

### <a name="enable-modern-pos-extension-components"></a>Aktivera tilläggskomponenter för Modern POS

1. Öppna lösningen **ModernPOS.sln** under **RetailSdk\\POS** och se till att den kan kompileras utan fel. Kontrollera dessutom att du kan köra Modern POS från Visual Studio med hjälp av kommandot **kör**.

    > [!NOTE]
    > Modern POS får inte anpassas. Du måste aktivera User Account Control (UAC) och du måste avinstallera tidigare installerade instanser av Modern POS efter behov.

2. Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.

3. Återskapa lösningen.
4. Kör Modern POS i felsökaren och testa funktionen.

### <a name="enable-cloud-pos-extension-components"></a>Aktivera tilläggskomponenter för Cloud POS

1. Öppna lösningen **CloudPOS.sln** under **RetailSdk\\POS** och se till att den kan kompileras utan fel.
2. Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.

3. Återskapa lösningen.
4. Kör lösningen med hjälp av kommandot **kör** och följa stegen i handboken Retail SDK.

## <a name="production-environment"></a>Produktionsmiljö

Föregående procedur aktiverar tilläggen som är komponenter i exemplet på skatteregistreringstjänsten. Förutom att du måste följa dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.

1. Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:

    - I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
        ```

    - I konfigurationsfilen **HardwareStation.Extension.config** lägg till följande rad i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

2. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:

    - Lägg till följande rader om du vill inkludera CRT-tilläggen i de distribuerbara paketen.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Lägg till följande rad om du vill inkludera Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Starta MSBuild-Kommandotolken för Visual Studio-verktyget och **kör MSBuild** under mappen Retail SDK för att skapa distribuerbara paket.
4. Tillämpa paketen via LCS eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Slutför alla inställningsuppgifter som beskrivs i [Ställ in Commerce för Österrike](emea-aut-fi-sample.md#set-up-commerce-for-austria).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av räkenskapsregistreringstjänsten för Österrike baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md). Mer information om design för räkenskapsintegreringslösning finns i [översikt över räkenskapsintegrering för exempeldesign](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera tjänstspecifika dokument och hantera svar från räkenskapsregistreringstjänsten.

CRT-tillägget är **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Begärandehanterare

Det finns två anförfrågningshanterare för dokumentleverantörer:

- **DocumentProviderEFRFiscalAUT** – Den här hanteraren används för att generera skattedokument för räkenskapsregistreringstjänst.
- **DocumentProviderEFRNonFiscalAUT** – Den här hanteraren används för att generera icke-skattedokument för räkenskapsregistreringstjänst.

Dessa hanterare ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetNonFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket icke-skattedokument som ska skapas. Den returnerar ett tjänstspecifikt dokument som ska registreras i räkenskapsregistreringstjänst.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport, utskrift av Z-rapport, insättning på kundkonto, insättning av kundorder, verifieringshändelser och icke-försäljningstransaktioner.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Denna begäran returnerar svaret från skatteregistreringstjänsten. Svaret serialiseras så att det går att spara.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet:

- **DocumentProviderFiscalEFRSampleAustria** – För skattedokument.
- **DocumentProviderNonFiscalEFRSampleAustria** – För icke-skattedokument.

Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- Mappning av momssatser

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget för anslutningsprogram för skatt är att kommunicera med registreringstjänsten för skatt. Tillägget för maskinvarustation kallas **HardwareStation.Extension.EFRSample**. Detta använder HTTP- eller HTTPS-protokoll för att skicka dokument som CRT-tillägget genererar till skatteregistreringstjänsten. Den hanterar också svar som tas emot från räkenskapsregistreringstjänsten.

#### <a name="request-handler"></a>Begärandehanterare

**EFRHandler** begäranhanteraren är startpunkten för hantering av begäranden till räkenskapsregistreringstjänst.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce headquarters.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till räkenskapsregistreringstjänsten och returnerar ett svar från den.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av tjänsten för räkenskapsregistrering.
- **InitializeFiscalDeviceRequest** – den här begäran används för initiera tjänsten för räkenskapsregistrering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- **Slutpunktsadress** – URL:en för skatteregistreringstjänsten.
- **Tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från räkenskapsregistreringstjänst.

### <a name="pos-fiscal-connector-extension-design"></a>Design för kassatillägg för skatteanslutningsprogram

Syftet med kassatillägget för anslutningsprogram för skatt är att kommunicera med registreringstjänsten från kassan. Det använder HTTPS-protokollet för kommunikation.

#### <a name="fiscal-connector-factory"></a>Anslutningsprogram för skatt

Generatorn för anslutningsprogram för skatt mappar namne tpå anslutningsprogrammet till implementeringen av anslutningsprogrammet för skatt och finns i filen **Pos.Extension\\Anslutningsprogram\\FiscalConnectorFactory.ts**. Anslutningsprogrammets namn ska matcha namnet på anslutningsprogrammet för skatt som anges i Commerce headquarters.

#### <a name="efr-fiscal-connector"></a>Anslutningsprogram för EFR-skatt

EFR-anslutningsprogrammet för skatt finns i filen **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Detta implementerar **IFiscalConnector**-gränssnittet som stöder följande begäran:

- **FiscalRegisterSubmitDocumentClientRequest** – Denna begäran skickar dokument till skatteregistreringstjänsten och returnerar ett svar från den.
- **FiscalRegisterIsReadyClientRequest** – Denna begäran används för en hälsokontroll av skatteregistreringstjänsten.
- **FiscalRegisterInitializeClientRequest** – Denna begäran används för att initialisera tjänsten för skatteregistrering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** i databasen [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/). Syftet med filen är att aktivera inställningar för räkenskapskoppling som ska konfigureras från Commerce headquarters. Filformatet justeras med kraven för konfiguration av räkenskapsintegrering. Följande inställningar är tillagda:

- **Slutpunktsadress** – URL:en för skatteregistreringstjänsten.
- **Tidsgräns** – Den tid i millisekunder (ms) som anslutningsprogrammet väntar på ett svar från skatteregistreringstjänsten.
