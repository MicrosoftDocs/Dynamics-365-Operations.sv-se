---
title: Implementeringsriktlinjer för integrationsexempel för kvittoskrivare för Polen (äldre)
description: Det här ämnet ger riktlinjer för distribution av integrationsexempel för kvittoskrivare för Polen från Microsoft Dynamics 365 Commerce Retail Software Development Kit (SDK).
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 45cae498df8157b9561c54e9859daadcaedd7823
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076998"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Implementeringsriktlinjer för integrationsexempel för kvittoskrivare för Polen (äldre)

[!include[banner](../includes/banner.md)]

Det här ämnet ger riktlinjer för distribution av integrationsexempel för kvittoskrivare för Polen från Microsoft Dynamics 365 Commerce Retail Software Development Kit (SDK) på en virtuell dator för utvecklare i Microsoft Dynamics Lifecycle Services (LCS). Mer information om exemplet på räkenskapsintegrering finns i [Exempel på integrering av kvittoskrivare för Polen](emea-pol-fpi-sample.md). 

Exemplet på skatteintegrering för Polen ingår i Retail SDK. Information om hur du installerar och använder SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md). Det här exemplet består av tillägg för Commerce Runtime (CRT), kassa och Hardware Station. Om du vill köra det här exemplet måste du ändra och bygga CRT och Hardware Station-projekt. Vi rekommenderar att du använder en icke-modifierad Retail SDK för att göra de ändringar som beskrivs i det här avsnittet. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Azure DevOps, där inga filer har ändrats ännu.

## <a name="development-environment"></a>Utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.

### <a name="commerce-runtime-extension-components"></a>Utbyggbarhetskomponenter för Commerce Runtime

CRT tilläggskomponenter inkluderas i Retail SDK. För att slutföra följande procedurer, öppna **CommerceRuntimeSamples.sln** lösningen under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Leta upp projektet **Runtime.Extensions.DocumentProvider.PosnetSample** och skapa det.
2. I mappen **Extensions.DocumentProvider.PosnetSample\\bin\\Debug** hittar du sammansättningsfilen **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Commerce Scale Unit:** kopiera filen till mappen **\\bin\\ext** under Internet Information Services (IIS) Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera filen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Commerce Scale Unit:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Commerce Scale Unit-webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Starta om Commerce-tjänsten:

    - **Commerce Scale Unit:** Starta om Commerce-webbplatsen från IIS Manager.
    - **Klientmäklare:** Avsluta **dllhost.exe** process Uppgiftshanteraren och starta sedan om Modern POS.

### <a name="hardware-station-extension-components"></a>Tilläggskomponenter för Hardware Station

Hardware Station tilläggskomponenter inkluderas i Retail SDK. För att slutföra följande procedurer, öppna lösningen **HardwareStationSamples.sln**, under **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Leta upp projektet **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** och skapa det.
2. I mappen **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Kopiera sammansättningsfilen till en distribuerad Hardware Station-maskinen:

    - **Fjärrstyrd Hardware Station** : kopiera filen till **binge**-mappen under IIS Hardware Station webbplatsen. Kopiera skrivardrivrutinbiblioteken (**libposcmbth.dll**, **libcmbth\_serial.dll** och **cmbth\_pl.lng**).

4. Leta reda på konfigurationsfilen för Hardware Station-tillägg. Filen heter **HardwareStation.Extension.config**:

    - **Fjärrstyrd Hardware Station** : filen finns under IIS Hardware Station webbplatsen.

5. Lägg till följande rad i avsnittet **sammansättning** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Starta om tjänsten Hardware Station:

    - **Fjärrstyrd Hardware Station** : Starta om Hardware Station webbplatsen från IIS Manager.

## <a name="production-environment"></a>Produktionsmiljö

Föregående procedur aktiverar tilläggen som är komponenter i exemplet på skatteregistreringstjänsten. Förutom att du måste följa dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.

1. Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:

    - I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - I konfigurationsfilen **HardwareStation.Extension.config** lägg till följande rad i avsnittet **komposition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings** under **BuildTools**:

    - Lägg till följande rad om du vill inkludera CRT-tilläggen i de distribuerbara paketen.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Lägg till följande rad om du vill inkludera Hardware Station-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Starta MSBuild-Kommandotolken för Visual Studio-verktyget och **kör MSBuild** under mappen Retail SDK för att skapa distribuerbara paket.
1. Tillämpa paketen via LCS eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Design av tilläggen

Exemplet på integrering av kvittoskrivare för Polen baseras på [räkenskapsintegrationsfunktionen](fiscal-integration-for-retail-channel.md). Mer information om design för räkenskapsintegreringslösning finns i [översikt över räkenskapsintegrering för exempeldesign](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Utbyggbarhetdesign för Commerce Runtime

Syftet med tillägget som är en skattedokument leverantör är att generera utskriftspecifika dokument och hantera svar från räkenskapsregistreringsutskrift.

CRT-tillägget är **Runtime.Extensions.DocumentProvider.PosnetSample**. Det här filnamnstillägget genererar en uppsättning skrivarspecifika kommandon i JSON-format (JavaScript Object Notation) som definieras i POSNET-specifikation 19-3678.

Mer information om design av lösningen av räkenskapsintegration finns i [Process för räkenskapsregistrering och exempel på räkenskapsintegration för kvittoskrivarenheter och tjänster](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Begärandehanterare

**DocumentProviderPosnetProtocol** begäranhanteraren är ingångspunkten för begäran om att generera dokument från skatteskrivaren.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på dokumentprovidern för koppling som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **GetFiscalDocumentDocumentProviderRequest** – den här begäran innehåller information om vilket dokument som ska skapas. Den returnerar ett utskriftsspecifikt dokument som ska registreras i kvittoskrivaren.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – den här begäran returnerar listan över händelser att prenumerera på. För närvarande stöds följande händelser: försäljning, utskrift av X-rapport och utskrift av Z-rapport.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med den här filen är att aktivera inställningar för dokumentprovidern som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration. Följande inställningar är tillagda:

- Mappning av momssatser
- Mappning av betalningsmedelstyp
- Betalningstyp för insättning

### <a name="hardware-station-extension-design"></a>Tilläggsdesign för Hardware Station

Syftet med tillägget som är en räkenskapskoppling är att kommunicera med kvittoskrivare.

Hardware Station-tillägget **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Det här filnamnstillägget anropar POSNET-drivrutinens funktioner för att skicka kommandon som CRT-tillägget genererar till kvittoskrivaren. Den hanterar även enhetsfel.

#### <a name="request-handler"></a>Begärandehanterare

**FiscalPrinterHandler** begäranhanteraren är startpunkten för hantering av begäranden till kringutrustning för räkenskaper.

Den här hanteraren ärvs från gränssnittet **INamedRequestHandler**. Metoden **HandlerName** är ansvarig för att returnera namnet på hanteraren. Hanterarens namn ska matcha namnet på räkenskapskopplingsnamn som anges i Commerce-administration.

Kopplingen stöder följande begäranden:

- **SubmitDocumentFiscalDeviceRequest** – den här begäran skickar dokument till skrivare och returnerar svaret från kvittoskrivaren.
- **IsReadyFiscalDeviceRequest** – den här begäran används för en hälsokontroll av enheten.
- **InitializeFiscalDeviceRequest** – Denna begäran används för skrivarinitiering.

#### <a name="configuration"></a>Konfiguration

Konfigurationsfilen finns i mappen **konfiguration** för tilläggsprojektet. Syftet med filen är att aktivera inställningar för anslutningsprogram som ska konfigureras från Commerce-administration. Filformatet justeras med kraven för konfiguration av räkenskapsintegration. Följande inställningar är tillagda:

- **Anslutningssträng** – En sträng som beskriver detaljerna för anslutningen till enheten i ett format som stöds av drivrutinen. Mer information finns i dokumentationen för POSNET.
- **Datum- och tidssynkronisering** – Ett värde som anger om datum och tid för skrivaren måste synkroniseras med den anslutna maskinvaran.
- **Enhetens tidsgräns** – hur länge, i millisekunder, som drivrutinen väntar på ett svar från enheten. Mer information finns i dokumentationen för POSNET.
